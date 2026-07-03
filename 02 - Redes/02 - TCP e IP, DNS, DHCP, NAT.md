# TCP/IP, DNS, DHCP, NAT
## IP (Internet Protocol)
É o responsável por endereçar e encaminhar os pacotes enviados pela rede. Quando um software precisa enviar dados, acontece o seguinte:
1. O dado é enviado em pequenas partes.
2. Cada parte vira um pacote de IP.
3. O IP adiciona um cabeçalho contendo o IP de origem, de destino e o tempo de vida do pacote, junto com a identificação dele.
4. Ele entrega esse pacote pro Wi-Fi ou pra Ethernet (conexão cabeada). 
5. A placa transforma isso em sinal físico
**PONTO IMPORTANTE:** O IP não verifica se o pacote chegou, quem faz isso é o TCP.
## TCP (Transmission Control Protocol):
É o responsável por garantir que os pacotes cheguem. Ele cria uma conexão com o servidor antes dos dados chegarem pelo Three-Way Handshake, que basicamente funciona como:
1. SYN: A primeira etapa. O cliente envia pro servidor uma flag de SYN (Synchronize), falando "eu quero me conectar, o meu número de sequência é X"
2. SYN-ACK: O servidor responde pro cliente: "Tudo bem, então te espero no próximo número de sequência, que deve ser X+1."
3. ACK: O Cliente confirma o reconhecimento com o servidor. 
Agora a conexão tá estabelecida, os dados são enviados e cada segmento tem um número de sequência, se algo faltar, o TCP reenvia. Ele também pode reorganizar pacotes fora de ordem, controlar o congestionamento e controlar o fluxo.
**PONTO IMPORTANTE:**
- O TCP é mais lento que o UDP. Mesmo que o TCP demore apenas milissegundos, o UDP é mais rápido. Isso porque o TCP envia dados e CONFIRMA que eles foram entregues, enquanto o UDP é mais como uma metralhadora de dados: ele só envia, não confirma se chegaram ou não.

## DNS (Domain Name System):
Ele funciona como um tradutor de IP em nomes legíveis pra humanos. Imagina ter que ficar colocando o IP do Google.com ao invés de só escrever "Google.com". Sem ele, a gente teria que ficar decorando o IP de cada site. O fluxo do DNS é o seguinte:
1. A gente digita o nome de um site e ele pergunta PRIMEIRAMENTE pro Sistema Operacional "sabe o IP disso?", onde o próprio OS verifica no cache do sistema, navegador e arquivos hosts se já sabe. Se ele já sabe, o DNS nem é consultado.
2. Caso ele não saiba, ele pergunta pro servidor DNS do roteador (do Wi-Fi, moldem). Caso ele também não saiba, ele pergunta a um DNS público (8.8.8.8 ou 1.1.1.1).
Depois de acessar, o site é salvo no cache e o navegador sabe pra onde ir a partir dali. 
**PONTO IMPORTANTE:** O DNS não verifica se o site é seguro, por isso existem DNS filtrados, seguros e com bloqueios de malwres. O DoH (DNS over HTTPS) e o DoT (DNS over TLS)são protocolos que criptografam a consulta do DNS. Isso melhora a privacidade, mas fica mais difícil pro SOC analisar a situação.

## DHCP (Dynamic Host Configuration Protocol):
É o cara que entrega identidade de rede pra um dispositivo. O processo do DHCP é chamado de DORA (olha as iniciais):
1. Discover: o computador envia um broadcast pra um servidor DHCP.
2. Offer: O servidor DHCP responde falando "eu tenho esse IP aqui disponível, com máscara de rede, gateway, DNS e X tempo de validade. Vai querer ele?"
3. Request: O computador aceita ou recusa o IP. Caso ele tenha aceito, o DHCP avisa os outros.
4. Ack: O IPs é concedido e passa a ser válido. O cliente pode se comunicar normalmente com outros IPs. 
**PONTO IMPORTANTE:** O DHCP não é seguro por padrão e pode sofrer ataques de negação de IP e envenenamento de rede. Por isso, em redes corporativas se usa o DHCP Snooping, VLANs e Controle de porta.

## NAT (Network Address Translation):
Quando usamos IPs privados dentro da nossa casa como 192.168.x.x, 172.16.x.x, esses IPs não existem na internet pública, então quando enviamos um pacote, o NAT:
1. O roteador troca o seu IP privado pelo seu IP público.
2. Guarda essa tradução na tabela NAT
3. Quando a resposta volta, ele consulta a tabela
4. Entrega pro dispositivo correto
Isso permite que vários IPs privados compartilhem um IP público e a rede interna fique escondida com mais segurança
**PONTO IMPORTANTE:** O NAT também dificulta o rastreamento forense, isso porque quando se usa um IP público identificar a máquina correta que fez X ligação requer muitas linhas de logs com timestamp preciso.


