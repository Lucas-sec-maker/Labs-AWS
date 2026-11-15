# 04 — Automação com User Data

Por último, nas configurações avançadas, existe uma seção chamada **"User Data"**, onde você pode colocar um script que roda **automaticamente no primeiro boot** da instância. Nada de entrar na máquina e instalar tudo na mão!

**O script faz o seguinte:**

- [x] Instala um servidor web Apache (`httpd`)
- [x] Configura o servidor web para iniciar automaticamente sempre que a máquina ligar
- [x] Inicia o servidor web
- [x] Cria uma página web simples

```bash
#!/bin/bash
# instala o servidor web Apache
dnf install -y httpd
# configura o Apache para iniciar junto com a máquina
systemctl enable httpd
# inicia o Apache agora
systemctl start httpd
# cria uma página web simples
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
```

<img width="1000" alt="Script de User Data nas configurações avançadas da instância" src="https://github.com/user-attachments/assets/13845808-feb2-44ad-a16e-0cfe02243730" />

> [!NOTE]
> **AMI x User Data:** os dois deixam a instância pronta com softwares instalados, mas de jeitos diferentes. Na AMI, o software **já vem pronto** na imagem; no User Data, ele é **instalado no primeiro boot**. Neste lab, a AMI trouxe só o Red Hat e o User Data instalou o Apache.

> [!WARNING]
> **Segurança:** o User Data fica visível para quem tem permissão de ver os detalhes da instância. **Nunca** coloque senhas, tokens ou chaves dentro dele. Segredos ficam em serviços próprios, como o AWS Secrets Manager.

[⬅ Voltar ao README](../README.md)
