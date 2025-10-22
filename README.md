# 🧰 BWPanel CLI

CLI oficial para gerenciamento de usuários e sites do **BWPanel**, desenvolvido para ser executado via terminal (Linux).

## ⚠️ Pré-requisitos do Servidor

Antes de rodar o BWPanel, certifique-se de que o servidor possui:

- **Sistema Operacional:** Ubuntu 22.04 LTS ou Debian 12/13
- **Banco de Dados:** MariaDB 10.6+ ou MySQL 8.x  
  - Necessário acesso root para criar o banco `bwpanel` durante a instalação
- **PHP:** Versão 8.4 com as seguintes extensões instaladas:
  - `php8.4-mysql`
  - `php8.4-fpm`
  - `php8.4-mbstring`
  - `php8.4-xml`
  - `php8.4-curl`
  - `php8.4-gd`
  - `php8.4-zip`
  - `php8.4-bcmath`

> Observação: Os demais diretórios e usuários do banco (`bwuser`) serão criados automaticamente pelo `bwpanel-install`.




## 🚀 Instalação

```bash
# 1. Subir os scripts para o servidor (ou clonar do GitHub)
git clone https://github.com/arthurbonora/bwpanel.git /opt/bwpanel
cd /opt/bwpanel

# 2. Tornar todos os scripts executáveis
chmod +x bwpanel-*
```

## ⚙️ Instalação completa com bwpanel-install

O comando `bwpanel-install` faz tudo de uma vez:

- Cria diretório `/opt/bwpanel`  
- Cria arquivo de configuração `config.conf` inicial  
- Cria banco de dados principal `bwpanel` e usuário `bwuser`  
- Cria as tabelas iniciais: `users`, `clients`, `sites`  
- Instala os scripts e cria links simbólicos  

```bash
sudo ./bwpanel-install
```

Após isso, todos os comandos estarão disponíveis.

---

## 🧩 Comandos disponíveis

| Comando | Descrição |
|----------|------------|
| bwpanel-install | Instala BWPanel do zero, cria banco, usuário e tabelas iniciais |
| bwpanel-adduser <usuario> <email> <senha> <dominio> | Cria novo site e usuário |
| bwpanel-deluser <usuario> | Remove usuário e site |
| bwpanel-help | Mostra ajuda e versão atual |
| bwpanel-version | Mostra versão do BWPanel e checa atualizações |
| bwpanel-update | Atualiza scripts BWPanel do repositório oficial |

---

## ⚙️ Configuração

O arquivo de configuração principal está em:

```bash
/opt/bwpanel/config.conf
```

### Principais variáveis:

- `SITES_PATH` → Diretório onde os sites serão criados (`/home/bwpanel/sites`)  
- `DB_USER` / `DB_PASS` → Usuário e senha do banco BWPanel  
- `DB_NAME` → Nome do banco principal (`bwpanel`)  
- `NGINX_AVAILABLE` / `NGINX_ENABLED` → Diretórios de configuração Nginx  
- `PHP_FPM_POOL_DIR` → Diretório dos pools do PHP-FPM  

> **Importante:** Após a instalação, altere `DB_PASS` para uma senha segura.

---

## 📦 Estrutura

- Sites em `/home/bwpanel/sites`  
- Logs de acesso e erro dentro de cada pasta do site (`logs/`)  
- Arquivos públicos em `public_html/`  

---

## 📜 Licença

MIT License © 2025 [Arthur Bonora](https://github.com/arthurbonora)
