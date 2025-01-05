# Honeypot com Cowrie

## Descrição
Este projeto configura um honeypot utilizando Cowrie, uma ferramenta de código aberto para simular serviços SSH e Telnet vulneráveis. O objetivo é capturar informações sobre atividades maliciosas, como tentativas de login não autorizadas, comandos executados e arquivos transferidos, ajudando na análise de ataques e comportamento de invasores.

---

## Funcionalidades
- Simulação de servidores SSH e Telnet.
- Registro detalhado de tentativas de login.
- Captura de comandos executados por atacantes.
- Coleta de arquivos transferidos via SCP ou wget.
- Armazenamento dos dados capturados em um banco de dados ou arquivos de log.

---

## Tecnologias Usadas
- **Cowrie**: Honeypot SSH/Telnet.
- **Ubuntu/Debian**: Sistema operacional base.
- **ELK Stack (opcional)**: Para visualização de logs.
- **iptables**: Configuração de redirecionamento de portas.

---

## Como Usar

### Pré-requisitos
Certifique-se de ter:
- Sistema operacional Linux.
- Python 3 e pip instalados.
- Acesso root para configurar redirecionamento de portas.

### Instalação

1. Atualize o sistema:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

2. Instale dependências:
   ```bash
   sudo apt install git python3 python3-venv python3-pip -y
   ```

3. Clone o repositório do Cowrie:
   ```bash
   git clone https://github.com/cowrie/cowrie.git
   cd cowrie
   ```

4. Configure o ambiente virtual Python:
   ```bash
   python3 -m venv cowrie-env
   source cowrie-env/bin/activate
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

5. Configure o Cowrie:
   - Copie o arquivo de configuração de exemplo:
     ```bash
     cp cowrie.cfg.dist cowrie.cfg
     ```
   - Edite o arquivo `cowrie.cfg` para ajustar parâmetros, como portas simuladas e modos de operação.

6. Configure o redirecionamento de portas:
   ```bash
   sudo iptables -t nat -A PREROUTING -p tcp --dport 22 -j REDIRECT --to-port 2222
   sudo iptables -t nat -A PREROUTING -p tcp --dport 23 -j REDIRECT --to-port 2223
   ```

7. Inicie o Cowrie:
   ```bash
   ./bin/cowrie start
   ```

---

## Exemplo de Uso
- Um atacante tenta acessar o honeypot via SSH.
- Cowrie registra a tentativa de login, comandos executados e arquivos transferidos.
- Os logs são armazenados em `log/cowrie.log` para análise.

---

## Estrutura do Projeto
```plaintext
honeypot-cowrie/
├── cowrie/             # Arquivos e configuração do Cowrie
├── logs/               # Logs gerados pelo honeypot
├── scripts/            # Scripts para automatização (opcional)
├── docs/               # Documentação adicional
└── README.md           # Este arquivo
```

---

## Aprendizados
- Configuração e operação de um honeypot com Cowrie.
- Captura e análise de atividades maliciosas.
- Uso de redirecionamento de portas para simular serviços vulneráveis.

---

## Próximos Passos
- Integração com ELK Stack para visualização avançada de logs.
- Automação da configuração com Ansible ou Terraform.
- Implementação de alertas em tempo real para atividades suspeitas.

---

## Contribuições
Contribuições são bem-vindas! Para sugerir melhorias ou relatar problemas, abra uma issue ou envie um pull request.
