# Estados TCP
## O QUE SÃO ESTADOS TCP?
Toda conexão TCP, em qualquer lado (seja cliente ou servidor), existe em um estado específico em um momento específico. O 3-way handshake é só a transição entre os primeiros estados. O Diagrama explicativo mostrando como acontece em cada lado pode ser encontrado na pasta "Diagramas e Imagens" tendo o nome de "03 - Estados TCP"
## O SYN_RECEIVED E O SYN_FLOOD
SYN_RECEIVED é o estado "preso no meio" que o SYN_Flood explora: o servidor fica esperando um ACK que nunca chega. Sendo assim, uma ou diversas máquinas podem só dar request na conexão mas nunca enviar o ACK final, esgotando o servidor que espera ele.
## O ENCERRAMENTO DA CONEXÃO (4-Way, não 3-Way)
Encerrar é mais lento que abrir, porque cada lado precisa encerrar sua conexão independentemente. Acontece o seguinte:
1. O Lado A (quem inicia o fechamento) envia FIN até o Lado B. É como se ele falasse "Não tenho nada mais pra entregar"
2. O Lado B envia um ACK pro Lado A. É como se ele falasse "Ok, entendi."
3. Enquanto o B ainda consegue receber dados, ele envia o FIN pro Lado A. "Agora eu terminei também"
4. Dessa vez é o Lado A enviar um ACK pro lado B dizendo que entendeu.
5. O A termina com TIME_WAIT e o B termina com CLOSED. Isso porque o Lado A ainda espera o fechamento pra ver se não vai receber nada.

**CONSULTAR A IMAGEM "ESTADOS DE ENCERRAMENTO"**
## MUITOS SOCKETS EM CLOSE_WAIT
Se isso acumula em massa, não é ataque: é bug de aplicação não fechando socket corretamente, e isso vai esgotar o servidor até ele cair.
## MUITOS SOCKETS EM SYN_RECEIVED
Se muitos sockets estão em SYN_RECEIVED e possuem o mesmo endereço de IP, esse pode ser um índicio forte de SYN Flood. De qualquer forma, o contexto sempre é necessário.

## ÂNGULO DEFENSIVO
Monitorar a distribuição de estados (ss -s) é um hábito que todo deveria ter. TIME_WAIT excessivo pode indicar um servidor sob alta taxa de conexões de curta duração, requer contexto. SYN_RECEIVED alto + mesmo IP de origem = SYN FLOOD.
## ÂNGULO OFENSIVO
SYN Flood explora o tempo de conexão em SYN_RECEIVED. RST Injection é quando um atacante que consegue adivinhar seq/ack pode mandar um RST forjado e derrubar a conexão de terceiros. Connection Exhaustion via slow connections é manter milhares de conexões abertas e ociosas em ESTABLISHED. 