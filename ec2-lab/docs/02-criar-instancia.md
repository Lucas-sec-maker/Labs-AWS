# 02 — Criando a instância

Agora, mão na massa! 🛠️

É o momento em que você vai "montar" o seu PC. E para montar um PC você precisa de duas coisas diferentes: **o que vai rodar nele** e **o hardware em que vai rodar**. Na AWS, essas duas coisas têm nomes:

| | AMI (Amazon Machine Image) | Tipo de instância |
|---|---|---|
| O que é | O "pendrive de instalação": sistema operacional + softwares + configurações | O "computador": vCPU, memória, rede |
| Exemplo | Red Hat Enterprise Linux | `t3.micro` |

> [!NOTE]
> A mesma AMI pode rodar em vários tipos de instância. Precisa de mais força? Troca o computador e mantém o mesmo pendrive.

## Configurações escolhidas

* **Nome da instância:** o nome da máquina virtual, para eu achar ela depois
* **AMI (sistema operacional):** Red Hat. Mas poderia ser qualquer outro nesse laboratório (Amazon Linux, Ubuntu, Windows...). Vai depender da sua necessidade e do problema que quer resolver.

<img width="1000" alt="Seleção do nome e da AMI Red Hat na criação da instância" src="https://github.com/user-attachments/assets/36435bc6-2b16-4bde-9530-0be2c150b475" />

> [!WARNING]
> **Segurança:** existem AMIs públicas criadas pela comunidade, e qualquer um pode publicar uma. Elas podem vir desatualizadas ou até com software malicioso. O ideal é usar AMIs oficiais (da AWS ou de fornecedores verificados) ou AMIs próprias.

[⬅ Voltar ao README](../README.md)
