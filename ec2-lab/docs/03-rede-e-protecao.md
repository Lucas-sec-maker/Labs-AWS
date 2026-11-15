# 03 — Configurações de rede e proteção

## Rede: VPC e sub-rede

Aqui, nas configurações de rede, é onde eu escolho **onde** a instância vai morar:

* **VPC (Virtual Private Cloud):** o "terreno" privado da minha conta dentro da AWS. Uma rede só minha, isolada das redes de outros clientes.
* **Sub-rede:** um "lote" dentro desse terreno. É uma **faixa de endereços IP** da VPC, que fica em uma zona de disponibilidade específica. O IP privado da instância é tirado dessa faixa.

> [!NOTE]
> Se a sub-rede for **pública** (com rota para um internet gateway), a instância também pode receber um IP público e ser acessada pela internet, desde que o Security Group deixe.

## Proteção contra encerramento

Nas configurações avançadas, foi ativada a **proteção contra encerramento**. Ela impede que a instância seja encerrada (excluída) por engano ou acidente: enquanto estiver ativa, o botão de encerrar simplesmente não funciona.

<img width="1000" alt="Configurações de rede e proteção contra encerramento ativada" src="https://github.com/user-attachments/assets/aa405333-16d9-4f2f-b0ad-4847bbd59116" />

> [!TIP]
> **Encerrar ≠ parar.** Parar é desligar o PC: dá para ligar de novo. Encerrar é jogar o PC fora: o disco raiz é apagado por padrão e não tem volta. Por isso a proteção existe.

> [!WARNING]
> **Segurança:** a proteção evita acidentes, mas não substitui permissões bem configuradas. Quem tem permissão para desativar a proteção (`ec2:ModifyInstanceAttribute`) também consegue encerrar a instância depois. O controle de verdade vem do IAM.

[⬅ Voltar ao README](../README.md)
