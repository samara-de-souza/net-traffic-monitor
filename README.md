# Monitor de Tráfego de Rede em Tempo Real

## 📋 Resumo do Trabalho

Este projeto consiste no desenvolvimento de uma ferramenta para monitoramento de tráfego de rede em tempo real utilizando **raw sockets**. A aplicação deve ser capaz de capturar, interpretar e classificar pacotes de rede, fornecendo uma interface de usuário simples para visualizar contadores e estatísticas de tráfego, além de manter um histórico dos pacotes recebidos em arquivos de log.

### 🎯 Objetivos Específicos

- Desenvolvimento de uma aplicação usando sockets raw
- Estudo do funcionamento dos protocolos de rede e relacionamento entre camadas
- Compreensão da estruturação de pacotes de dados e interpretação para extração de informações
- Análise do tráfego de rede local e tipos de protocolos comuns
- Utilização de uma estrutura de rede pré-definida

### 🏗️ Arquitetura da Rede

O sistema funciona em uma rede onde:
- **Clientes** acessam a internet através de um **servidor proxy**
- Ambos residem na mesma LAN
- O acesso externo é feito através de um programa cliente do proxy
- O tráfego é encapsulado em pacotes IP com informações forjadas para segurança
- O monitor executa na máquina servidor proxy

### 📊 Arquivos de Log

A aplicação deve gerar três arquivos CSV em tempo real:

1. **camada2.csv** - Camada de Enlace (Ethernet)
   - Data/hora de captura
   - MAC origem e destino
   - EtherType (protocolo)
   - Tamanho do quadro

2. **camada3.csv** - Camada de Rede (IP)
   - Data/hora de captura
   - Nome do protocolo (IPv4/IPv6)
   - IP origem e destino
   - Número do protocolo
   - Tamanho do pacote

3. **camada4.csv** - Camada de Transporte (TCP/UDP)
   - Data/hora de captura
   - Nome do protocolo (TCP/UDP/etc.)
   - IP origem e destino
   - Portas origem e destino
   - Tamanho do pacote

---


## 🚀 Como Executar

### Modo Servidor Proxy
```bash
sudo ./traffic_tunnel <interface_do_servidor> -s <ip_do_servidor>
```

### Modo Cliente
```bash
sudo ./traffic_tunnel <interface_do_cliente> -c <ip_do_cliente> -t
```

### Verificação da Interface
```bash
ifconfig tun0
# ou
ip addr show tun0
```


## 🔧 Dependências
- Ambiente Linux
- build-essentials
- iptables
- Interface de rede configurada
- Permissões de administrador (sudo) 
