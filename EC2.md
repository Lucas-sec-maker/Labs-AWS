# Gerenciando uma EC2

## 🔎 Aqui vai mais uma visão geral de como subir, explorar, gerenciar e monitorar uma instância EC2
<img width="570" height="429" alt="image" src="https://github.com/user-attachments/assets/1a86d492-9979-4f64-9695-602a2381aa1c" />


Em resumo, o Amazon Elastic Compute Cloud (ou, para os íntimos, Amazon EC2 😙) é um serviço da AWS (Amazon Web Service) onde você pode usar força computacional sob demanda. 
Você.através da internet, pode ter acesso à um computador muito mais potente que o seu (😴) sem precisar estar com ele fisicamente. Imagina poder jogar aquele jogo pesado diretamente do seu "PC da xuxa"?!
Ter uma internet boa já é o suficiente para você ter acesso à esse serviço da AWS. 

Mas o que "força computacional sobre demanda" quer dizer? Quer dizer que você usa o tempo que você precisa, e ,consequentemente, paga apenas pelo que usa e precisa. Segundo por segundo e nada mais!

Agora vamos para o que interessa!
Esse laboratório tem o objetivo de: 


    Monitorar sua instância do EC2

    Modificar o grupo de segurança que seu servidor web está usando para permitir acesso HTTP

    Redimensionar sua instância do Amazon EC2 de acordo com a necessidade

    Testar a proteção contra encerramento

    Terminar a instância do EC2


## Vamos la!🚀

## 😐 Se o computador está em outro lugar, como que eu vou acessar ele (o serviço EC2) para usar esse "poder computacional" todo?
- Para você acessar os serviços da AWS,há três formas:

      -Linha de comando
      -Console AWS
      -SDK's

### 1- Linha de comando 

É aquela tela preta que todo computador tem, mas a maioria dos usuários comuns não faz ideia de como usar aquilo. Mas,nós,estudantes de tecnologia, sabemos. Não sabemos?!

<img width="648" height="448" alt="image" src="https://github.com/user-attachments/assets/700cd0f3-bd4b-415c-810a-9f67889a9db6" />

É nela que vamos dar os comandos para acessar e chamar os serviços via API. E com API eu quero dizer que, lidando com AWS, é como se você tivesse em uma lanchonete e a API fosse o garçom. A comida só chega
em você (no caso, o serviço) se você chamar o garçom. Então você faz o pedido - escreve o comando na tela preta - para o bom moço(a)o com a bandeja. Ele(a) vai até a cozinha entregar o seu pedido( a API vai
onde os serviços estão hospedados) e traz até você.

### 2 - Console AWS 

É basicamente uma página web, cheia de botão, telas e cores. Bem mais simples de usar.

<img width="1896" height="889" alt="image" src="https://github.com/user-attachments/assets/42a6f901-a24c-46cc-844e-c3cef615d885" />

### 3 - SDK's

Se for um programador, muito provavelmente vai saber do que estou falando. Mas,em resumo,esse acesso serve quando você está escrevendo seu programa ou site e precisa de algum serviço da AWS no meio de tudo isso
interagindo direto com o código que está sendo construído

<img width="1246" height="705" alt="image" src="https://github.com/user-attachments/assets/16ab54ec-55ef-47c5-b49c-29e1858c40a2" />

# Agora,mão na massa! 

## Criando a instância 

Aqui é onde você vai selecionar a imagem do sistema operacional que você quer, o tipo de poder de processamento que ela vai ter e outras coisas mais.Tudo isso vem em um pacote de imagem,
que é chamado AMI (Amazon Machine Image), um modelo para criar uma máquina com vários pacotes de programas já instalados
Ou seja, tem vários "sabores" e CPU, memória, capacidade de redes, armazenamento e outras coisas mais. É o momento que você vai "montar" o seu PC.

Aqui eu vou escolher o Sistema Operacional da Red Hat. Mas poderia ser qualquer outro nesse laboratório.


### Escolhendo o tipo da instância.Ou seja, o quão forte ela vai ser.
    - Aqui vai o nome da máquina virtual (instância)
    - O sistema operacional (no meu caso, o Red Hat)

É possível escolher diversos tipos de Sistemas Operacionais.Vai depender da sua necessidade e do problema que quer resolver.

 <img width="1723" height="780" alt="image" src="https://github.com/user-attachments/assets/36435bc6-2b16-4bde-9530-0be2c150b475" />

 <img width="1687" height="809" alt="image" src="https://github.com/user-attachments/assets/aa405333-16d9-4f2f-b0ad-4847bbd59116" />

 <img width="1913" height="733" alt="image" src="https://github.com/user-attachments/assets/943674d9-c730-43ce-a061-ed59220ed438" />

 <img width="1683" height="477" alt="image" src="https://github.com/user-attachments/assets/baea21cd-58e5-49aa-a4e5-0a6767cfcd8b" />

 <img width="1621" height="451" alt="image" src="https://github.com/user-attachments/assets/3ff9cf89-bd83-4f8d-83cf-6310a020cc42" />

 <img width="1621" height="451" alt="image" src="https://github.com/user-attachments/assets/939879d1-a8eb-4298-a1e7-dbe556efcdcf" />























 
