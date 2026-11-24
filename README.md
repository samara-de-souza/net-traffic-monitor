# net-traffic-monitor

Ferramenta em C para monitoramento de tráfego de rede em tempo real, que captura e classifica pacotes usando raw sockets.

## Objetivo

Entender como os protocolos de rede se relacionam entre as camadas e como um pacote é estruturado, interpretando seus campos diretamente a partir dos bytes capturados.

## O que foi feito

- Captura de pacotes em tempo real com raw sockets
- Interpretação e classificação dos pacotes nas camadas de enlace, rede e transporte
- Interface simples com contadores e estatísticas de tráfego
- Histórico dos pacotes em três logs CSV: camada 2 (Ethernet), camada 3 (IPv4/IPv6) e camada 4 (TCP/UDP)
- Análise do tráfego de uma LAN em que os clientes acessam a internet por um servidor proxy, com o monitor rodando no servidor

## Tecnologias e conceitos

C, raw sockets, Linux, modelo de camadas (Ethernet, IP, TCP/UDP), captura e análise de pacotes, iptables.

## Resultados

- Monitor funcional que registra o tráfego em tempo real, separado por camada
- Visão prática dos protocolos mais comuns em uma rede local e de como cada camada encapsula a seguinte
