# 🧰 BWPanel CLI

CLI oficial para gerenciamento de usuários e sites do **BWPanel**, desenvolvido para ser executado via terminal (Linux).

## 🚀 Instalação

```bash
git clone https://github.com/arthurbonora/bwpanel.git /opt/bwpanel
cd /opt/bwpanel
chmod +x bwpanel-*
```

Crie links simbólicos:
```bash
ln -sf /opt/bwpanel/bwpanel-adduser /usr/local/bin/bwpanel-adduser
ln -sf /opt/bwpanel/bwpanel-deluser /usr/local/bin/bwpanel-deluser
ln -sf /opt/bwpanel/bwpanel-help /usr/local/bin/bwpanel-help
ln -sf /opt/bwpanel/bwpanel-version /usr/local/bin/bwpanel-version
ln -sf /opt/bwpanel/bwpanel-update /usr/local/bin/bwpanel-update
```

## ⚙️ Configuração

Edite o arquivo:
```bash
nano /opt/bwpanel/config.conf
```

## 🧩 Comandos disponíveis

| Comando | Descrição |
|----------|------------|
| bwpanel-adduser <usuario> <email> <senha> <domínio> | Cria novo site e usuário |
| bwpanel-deluser <usuario> | Remove usuário e site |
| bwpanel-help | Mostra ajuda e versão atual |

## 📦 Estrutura

Sites em `/home/bwpanel/sites`, logs e `public_html`.

## 📜 Licença

MIT License © 2025 [Arthur Bonora](https://github.com/arthurbonora)
