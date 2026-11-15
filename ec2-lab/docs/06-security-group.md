# 06 — Regras de segurança (Security Group)

É hora de criar as regras de segurança dessa máquina. O **Security Group** é um firewall virtual da instância: é nele que eu digo **quem pode entrar** e **o que pode sair**.

> [!NOTE]
> **Como o Security Group nasce:**
> * **Entrada:** tudo negado. Só entra o que eu liberar explicitamente.
> * **Saída:** tudo liberado.
>
> Ele também é **stateful**: se uma requisição entrou, a resposta sai automaticamente, sem precisar de regra de saída.

Nesse caso, estou configurando quem pode acessar a minha instância. A regra abaixo diz que o acesso deve ser via **HTTP, na porta 80 (protocolo TCP)**, vindo de qualquer lugar (`0.0.0.0/0`).

<img width="1000" alt="Regra de entrada do Security Group liberando HTTP na porta 80" src="https://github.com/user-attachments/assets/387213ec-8617-4638-bcbc-1b0d00342d3f" />

> [!WARNING]
> **`0.0.0.0/0` é perigoso? Depende da porta!**
> * **Portas de site (80 HTTP / 443 HTTPS):** liberar para todo mundo é normal. Site público é feito para ser acessado por qualquer pessoa.
> * **Portas de administração (22 SSH / 3389 RDP):** **nunca** para `0.0.0.0/0`. É a porta de entrada favorita de ataques de força bruta. O ideal é nem abrir: usar o **Session Manager** ou, no mínimo, liberar só o meu IP.
>
> Num ambiente real, eu também trocaria **HTTP por HTTPS**, para que o tráfego entre o usuário e o site seja criptografado.

---

## ✅ Instância criada

<img width="800" alt="Instância criada e configurada" src="https://github.com/user-attachments/assets/b3401cd3-0ba6-4513-8f39-cf79b07203b6" />

[⬅ Voltar ao README](../README.md)
