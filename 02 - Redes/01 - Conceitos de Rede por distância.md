# Conceitos de rede por extensão geográfica
## PAN (Personal Area Network)
A rede com menor alcance que vou cobrir aqui. Normalmente com um alcance de 10 metros, ela é usada para dispositivos pessoais, como o nosso bluetooth, mouse e teclados sem fio, etc. Tem um **BAIXO** consumo de energia.
## LAN (Local Area Network)
Tem um alcance de 1-2km. Cobre uma área física limitada, como uma casa, escola ou laboratório. Redes de Wi-Fi residenciais e redes cabeadas em escolas ou em laboratórios  de informática são um exemplo disso. Tem uma alta velocidade e baixa latência junto com controle administrativo local.  
**Ponto Importante:** Em uma rede LAN, os dispositivos usam IPs privados para não haver confusão ou conflitos quando forem se comunicar com a internet pública. Antigamente, usavam classes de IP distintas para cada um (Classe A, B e C). Hoje em dia se usa o CIDR (Classless Inter-Domain Routing), onde o que define a rede é a máscara de sub-rede.
## MAN (Metropolitan Area Network)
Tem um alcance de 5-50km. Na maioria das vezes, é a responsável por ligar várias redes LANs em uma única cidade ou campus universitário. Pode usar diferentes tecnologias como fibra óptica e rádios. 
## WAN (Wide Area Network)
Não tem distância fixa. É a responsável por interligar cidades, países ou até continentes. Muitas redes multinacionais e conexões entre filiais em diferentes estados ou países utilizam ela. Ela pode utilizar Internet, satélites, cabos submarinos, MPLs e até VPNs. Obviamente, apresenta uma latência maior, e justamente por ser descentralizada apresenta menor controle administrativo direto.
## SAN (Storage Area Network)
É uma rede utilizada exclusivamente pra armazenamento de dados. Ela conecta servidores e dispositivos de armazenamento. É bem comum em ambientes corporativos e data centers. Normalmente usada pra backups, servidores e bancos de dados de alto desempenho.
**Ponto Importante:**  Se um ransomware atingir a SAN, ele pode criptografar backups e servidores inteiros.
