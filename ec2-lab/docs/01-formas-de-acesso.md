# 01 — Formas de acessar a AWS

### 😐 Se o computador está em outro lugar, como que eu vou acessar ele para usar esse "poder computacional" todo?

Para você acessar os serviços da AWS, há três formas:

* 📟 **Linha de comando (AWS CLI)**
* 🌐 **Console AWS**
* 💻 **SDKs**

> [!TIP]
> **Analogia da API:**
> Lidando com AWS, é como se você estivesse em uma lanchonete e a API fosse o garçom. A comida (o serviço) só chega em você se você chamar o garçom.
>
> Você faz o pedido, o garçom leva até a cozinha (onde os serviços estão hospedados) e traz o resultado até você.
>
> E aqui vai o detalhe: **as três formas de acesso falam com o mesmo garçom**. Seja clicando no console, digitando na linha de comando ou escrevendo código, por trás de tudo é sempre uma chamada à API da AWS.

---

## 1 - Linha de comando

É aquela tela preta que todo computador tem, mas a maioria dos usuários comuns não faz ideia de como usar. Mas nós, estudantes de tecnologia, sabemos. Não sabemos?!

Com a **AWS CLI** instalada, cada comando digitado vira um pedido para a API.

<img width="648" alt="Terminal com comandos da AWS CLI" src="https://github.com/user-attachments/assets/700cd0f3-bd4b-415c-810a-9f67889a9db6" />

---

## 2 - Console AWS

É basicamente uma página web, cheia de botões, telas e cores. Bem mais simples de usar. Cada clique também vira uma chamada à API.

<img width="1000" alt="Página inicial do Console da AWS" src="https://github.com/user-attachments/assets/42a6f901-a24c-46cc-844e-c3cef615d885" />

---

## 3 - SDKs

Se você for programador, muito provavelmente vai saber do que estou falando. Em resumo, esse acesso serve quando você está escrevendo seu programa ou site e precisa de algum serviço da AWS no meio de tudo isso, interagindo direto com o código (Python, Java, JavaScript...).

<img width="1000" alt="Exemplo de código usando um SDK da AWS" src="https://github.com/user-attachments/assets/16ab54ec-55ef-47c5-b49c-29e1858c40a2" />

---

> [!WARNING]
> **Segurança:** a CLI e os SDKs usam credenciais de acesso (access keys). Elas **nunca** devem ir para dentro do código nem para um repositório público. Robôs varrem o GitHub atrás delas em minutos.

[⬅ Voltar ao README](../README.md)
