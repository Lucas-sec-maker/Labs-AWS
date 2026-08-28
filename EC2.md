# Gerenciando uma EC2

<div align="center">
  <img width="570" height="429" alt="image" src="https://github.com/user-attachments/assets/1a86d492-9979-4f64-9695-602a2381aa1c" />
</div>

## 📌 Sumário
- [🔎 Visão Geral](#-uma-visão-geral-de-como-subir-explorar-gerenciar-e-monitorar-uma-instância-ec2)
- [🎯 Objetivos do Laboratório](#-objetivos-do-laboratório)
- [🚀 Formas de Acesso](#vamos-lá-)
  - [1 - Linha de comando](#1---linha-de-comando)
  - [2 - Console AWS](#2---console-aws)
  - [3 - SDKs](#3---sdks)
- [🛠️ Agora, mão na massa!](#agora-mão-na-massa)
  - [Criando a instância](#criando-a-instância)
  - [Configurações de Rede e Proteção](#configurações-de-rede)
  - [Automação com User Data](#automação-com-user-data)
  - [Regras de Segurança (Security Group)](#regras-de-segurança)
- [✅ Instância criada](#-instância-criada)

---

## 🔎 Uma visão geral de como subir, explorar, gerenciar e monitorar uma instância EC2

Em resumo, o **Amazon Elastic Compute Cloud** (ou, para os íntimos, Amazon EC2 😙) é um serviço da AWS (Amazon Web Service) onde você pode usar força computacional sob demanda. 

Você, através da internet, pode ter acesso a um computador muito mais potente que o seu (😴) sem precisar estar com ele fisicamente. Imagina poder jogar aquele jogo pesado diretamente do seu "PC da xuxa"?! Ter uma internet boa já é o suficiente para você ter acesso a esse serviço da AWS. 

> [!NOTE]
> **Mas o que "força computacional sob demanda" quer dizer?**  
> Quer dizer que você usa o tempo que você precisa e, consequentemente, paga apenas pelo que usa e precisa. Segundo por segundo e nada mais!

---

### 🎯 Objetivos do Laboratório
Agora vamos para o que interessa! Esse laboratório tem o objetivo de: 

- [ ] Monitorar sua instância do EC2
- [ ] Modificar o grupo de segurança que seu servidor web está usando para permitir acesso HTTP
- [ ] Redimensionar sua instância do Amazon EC2 de acordo com a necessidade
- [ ] Testar a proteção contra encerramento
- [ ] Terminar a instância do EC2

---

## Vamos lá! 🚀

### 😐 Se o computador está em outro lugar, como que eu vou acessar ele (o serviço EC2) para usar esse "poder computacional" todo?

Para você acessar os serviços da AWS, há três formas:
* 📟 **Linha de comando**
* 🌐 **Console AWS**
* 💻 **SDKs**

---

#### 1 - Linha de comando 

É aquela tela preta que todo computador tem, mas a maioria dos usuários comuns não faz ideia de como usar aquilo. Mas nós, estudantes de tecnologia, sabemos. Não sabemos?!

<img width="648" height="448" alt="image" src="https://github.com/user-attachments/assets/700cd0f3-bd4b-415c-810a-9f67889a9db6" />

> [!TIP]
> **Analogia da API:**  
> É nela que vamos dar os comandos para acessar e chamar os serviços via API. E com API eu quero dizer que, lidando com AWS, é como se você estivesse em uma lanchonete e a API fosse o garçom. A comida só chega em você (no caso, o serviço) se você chamar o garçom.  
> 
> Então você faz o pedido — escreve o comando na tela preta — para o bom moço(a) com a bandeja. Ele(a) vai até a cozinha entregar o seu pedido (a API vai onde os serviços estão hospedados) e traz até você.

---

#### 2 - Console AWS 

É basicamente uma página web, cheia de botões, telas e cores. Bem mais simples de usar.

<img width="1896" height="889" alt="image" src="https://github.com/user-attachments/assets/42a6f901-a24c-46cc-844e-c3cef615d885" />

---

#### 3 - SDKs

Se for um programador, muito provavelmente vai saber do que estou falando. Mas, em resumo, esse acesso serve quando você está escrevendo seu programa ou site e precisa de algum serviço da AWS no meio de tudo isso, interagindo direto com o código que está sendo construído.

<img width="1246" height="705" alt="image" src="https://github.com/user-attachments/assets/16ab54ec-55ef-47c5-b49c-29e1858c40a2" />

---

# Agora, mão na massa! 

## Criando a instância 

Aqui é onde você vai selecionar a imagem do sistema operacional que você quer, o tipo de poder de processamento que ela vai ter e outras coisas mais. Tudo isso vem em um pacote de imagem, que é chamado **AMI (Amazon Machine Image)**, um modelo para criar uma máquina com vários pacotes de programas já instalados.

Ou seja, tem vários "sabores" de CPU, memória, capacidade de rede, armazenamento e outras coisas mais. É o momento que você vai "montar" o seu PC.

Aqui eu vou escolher o Sistema Operacional da Red Hat. Mas poderia ser qualquer outro nesse laboratório.

### Escolhendo o tipo da instância (ou seja, o quão forte ela vai ser):
* **Nome da máquina virtual:** Nome da instância
* **Sistema operacional:** Red Hat

> [!NOTE]
> É possível escolher diversos tipos de Sistemas Operacionais. Vai depender da sua necessidade e do problema que quer resolver.

<img width="1723" height="780" alt="image" src="https://github.com/user-attachments/assets/36435bc6-2b16-4bde-9530-0be2c150b475" />

---

### Configurações de Rede e Proteção

Aqui, em configurações de rede, é onde vou configurar a sub-rede e a VPC da instância. Ou seja, vou atribuir um endereço de IP para ela (sub-rede) e um "terreno" privado para ela dentro da AWS (Virtual Private Cloud).

Além disso, em configurações avançadas, foi ativado o modo de **proteção contra encerramento de instância**, que serve para preservá-la em caso de tentativa de encerramento da mesma por algum tipo de equívoco ou acidente.

<img width="1687" height="809" alt="image" src="https://github.com/user-attachments/assets/aa405333-16d9-4f2f-b0ad-4847bbd59116" />

---

### Automação com User Data

Por último, nas configurações avançadas, existe uma seção chamada **"User Data"**, onde você pode dar alguns comandos para instalar e baixar algumas coisas de forma automatizada assim que a instância é criada:

> **O script fará o seguinte:**
> - [x] Instalará um servidor web Apache (`httpd`).
> - [x] Configurará o servidor web para ser iniciado automaticamente na inicialização.
> - [x] Ativará o servidor web.
> - [x] Criará uma página da web simples.

<img width="1179" height="771" alt="image" src="https://github.com/user-attachments/assets/13845808-feb2-44ad-a16e-0cfe02243730" />

---

### Validação da Instância

A imagem abaixo exibe com sucesso a criação de uma instância:

<img width="1913" height="733" alt="image" src="https://github.com/user-attachments/assets/943674d9-c730-43ce-a061-ed59220ed438" />

Aqui mostra algumas informações da instância e o estado em que ela se encontra:

<img width="1683" height="477" alt="image" src="https://github.com/user-attachments/assets/baea21cd-58e5-49aa-a4e5-0a6767cfcd8b" />

<img width="1621" height="451" alt="image" src="https://github.com/user-attachments/assets/3ff9cf89-bd83-4f8d-83cf-6310a020cc42" />

---

### Regras de Segurança (Security Group)

É hora de criar as regras de segurança dessa máquina. Um filtro onde eu posso dizer quem pode acessar, o que pode sair da minha instância e outras coisas.

Nesse caso, estou configurando regras para quem pode acessar a minha instância. A regra abaixo diz que o acesso deve ser via **HTTP, na porta 80 (via protocolo TCP)**.

> [!WARNING]
> Claro que, para fins de teste, tanto faz a porta ou a forma como vai ser acessado. Em casos reais, JAMAIS usaria HTTP, e muito menos deixaria todo mundo acessar (`0.0.0.0/0`).

> [!NOTE]
> A VPC, por padrão, não vem com acesso direto para a internet, nasce isolada, tendo que criar as regras de entrada e saída, caso necessário.

<img width="1076" height="627" alt="image" src="https://github.com/user-attachments/assets/387213ec-8617-4638-bcbc-1b0d00342d3f" />

---

## ✅ Instância criada

<img width="800" height="600" alt="i-042c457eac6141a8b" src="https://github.com/user-attachments/assets/b3401cd3-0ba6-4513-8f39-cf79b07203b6" />
