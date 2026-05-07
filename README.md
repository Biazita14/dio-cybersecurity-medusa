# dio-cybersecurity-medusa

# Projeto de Auditoria de Segurança: Ataque de Força Bruta com Medusa

## 📝 Descrição
Este projeto faz parte do Bootcamp de Cibersegurança da DIO. O objetivo foi simular um ataque de força bruta contra o serviço FTP para entender a importância de credenciais fortes e configurações de rede seguras.

## 🛠️ Ambiente e Ferramentas
* **Sistema Operacional:** Kali Linux (Máquina Virtual)
* **Ferramenta de Ataque:** Medusa v2.3
* **Alvo:** Serviço FTP local (vsftpd) simulando um ambiente vulnerável.

## 🚀 Execução
1. **Configuração do Alvo:** Instalação e ativação do serviço `vsftpd` no Kali Linux.
2. **Criação de Wordlists:** Geração de arquivos `usuarios.txt` e `senhas.txt` contendo credenciais de teste.
3. **Execução do Ataque:** Utilização do Medusa para testar as combinações via protocolo FTP.

##🛡️ Medidas de Mitigação
Para prevenir este tipo de ataque em ambientes de produção, recomenda-se a implementação das seguintes camadas de segurança:

* **Uso de Protocolos Seguros:** Substituir o protocolo FTP (que transmite dados em texto claro) por alternativas criptografadas como **SFTP** ou **SSH**, garantindo que as credenciais e dados não sejam interceptados.
* **Implementação de Bloqueio Ativo (Fail2Ban):** Utilizar ferramentas de IPS (*Intrusion Prevention System*) que monitorem logs em tempo real e banam automaticamente endereços IP que apresentem múltiplas falhas de autenticação em um curto intervalo de tempo.
* **Políticas de Senhas Fortes:** Adotar requisitos de complexidade (caracteres especiais, números e alternância de caixa alta/baixa) e, obrigatoriamente, implementar **Autenticação de Dois Fatores (2FA)**.
* **Princípio do Menor Privilégio:** Configurar o sistema para desabilitar o acesso remoto direto para a conta `root` e restringir o acesso a serviços críticos apenas para usuários e sub-redes autorizadas através de ACLs ou Firewalls.

**Comando utilizado:**
```bash
medusa -h 127.0.0.1 -u kali -P senhas.txt -M ftp



