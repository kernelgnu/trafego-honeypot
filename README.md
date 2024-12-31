# Projeto: Honeypot com Cowrie

## Arquitetura do Projeto

O fluxo do projeto pode ser descrito da seguinte forma:

### 1. Atacantes:

- Representam agentes maliciosos que tentam explorar vulnerabilidades em sistemas, conectando-se a serviços simulados como SSH e Telnet.

- Esses atacantes interagem diretamente com o honeypot, fornecendo dados valiosos sobre comportamentos e estratégias de ataque.

### 2. Honeypot (Cowrie):

- Uma ferramenta especializada em simular serviços SSH/Telnet para capturar atividades maliciosas.

- Registra as seguintes informações:

    - Comandos executados pelos atacantes.

    - Credenciais utilizadas em tentativas de login.

    - Transferências de arquivos maliciosos realizadas.

- Proporciona um ambiente controlado para estudo de táticas utilizadas por invasores.

### 3. Logs:

- Todos os dados capturados pelo honeypot são registrados em arquivos de log detalhados.

- Os logs incluem informações como:

    - IPs de origem das conexões.

    - Comandos digitados.

    - Horários das atividades.

- Esses registros podem ser armazenados localmente ou enviados para serviços de arquivamento seguro, como AWS S3 ou servidores externos.

### 4. Análise de Dados:

- Os logs são analisados para identificar padrões de comportamento e classificar os tipos de ataques.

- Ferramentas como Kibana ou Splunk podem ser utilizadas para:

    - Criar dashboards interativos para monitoramento em tempo real.

    - Gerar relatórios com insights sobre os ataques registrados.

- Conexão com bancos de dados de inteligência de ameaças permite identificar IPs e métodos associados a agentes maliciosos conhecidos.

## Objetivo do Projeto

Criar um ambiente seguro para capturar, estudar e compreender o comportamento de atacantes, utilizando o Cowrie como honeypot e integrando ferramentas de análise para monitoramento e registro de dados.

## Possíveis Expansões

    1. Implementar alertas em tempo real para detecção de atividades suspeitas.

    2. Automatizar a classificação de ameaças com scripts Python.

    3. Expandir a infraestrutura para suportar múltiplos honeypots distribuídos em diferentes regiões.

## Habilidades Demonstradas

- Configuração e personalização de honeypots.

- Integração de ferramentas de monitoramento (Kibana/Splunk).

- Análise de logs e identificação de padrões de comportamento.

- Armazenamento seguro e organização de registros para estudos futuros.

## Como Executar o Projeto

Para mais detalhes sobre como configurar e executar este honeypot, consulte os arquivos de documentação abaixo:


