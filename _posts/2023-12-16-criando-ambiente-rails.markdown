---
title: "Criando um ambiente Rails"
categories:
  - iniciante
  - rails
  - ruby
  - postgresql
  - linux
  - git
tags:
  - rails
  - ruby
  - postgresql
  - git
---

# Criando o Ambiente de Desenvolvimento Web Ruby on Rails

Olá! Antes de começarmos o tutorial, gostaria de compartilhar uma experiência pessoal na instalação do ambiente. Quando comecei com Ruby on Rails, enfrentei desafios na configuração do ambiente. Minhas primeiras tentativas foram complicadas, com erros frequentes. Encontrar tutoriais com feedback era difícil, e mesmo ao trocar de computador, precisei buscar um novo tutorial para configurar o ambiente. Então, não se preocupe se não conseguir na primeira vez ou se houver dúvidas. Estou disponível por e-mail para responder às suas perguntas. Vamos explicar de forma simples e didática. Espero que gostem!

## Instalando o Ruby on Rails com Dependências Necessárias

Antes de tudo, é necessário atualizar o Debian:

```bash
sudo apt update
sudo apt upgrade
```

Agora, instale o Git:

```bash
sudo apt install git
```

Configure o Git com seu nome e e-mail:

```bash
git config --global user.name "seu nome"
git config --global user.email "seu email"
```

Node.js é uma plataforma construída sobre o motor JavaScript do Google Chrome. Instale-o:

```bash
sudo curl -sSL https://deb.nodesource.com/setup_16.x | sudo bash -
sudo apt install nodejs
```

Instale o Yarn, um gerenciador de pacotes JavaScript:

```bash
sudo curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt install yarn
```

Agora, instale o RVM (Ruby Version Manager):

```bash
\curl -sSL https://get.rvm.io | bash
source ~/.rvm/scripts/rvm
rvm install 3.2.2
rvm use 3.2.2
```

O RubyGems é um gerenciador de pacotes para Ruby. Ele já está incluído na instalação do Ruby.

## Configuração do PostgreSQL

Instale o PostgreSQL e uma dependência da gem pg:

```bash
sudo apt install postgresql libpq-dev
```

Altere a configuração do PostgreSQL:

```bash
sudo nano /etc/postgresql/9.6/main/pg_hba.conf
```

Altere a linha para:

```bash
local        all      postgres                  md5
```

Salve e reinicie o PostgreSQL:

```bash
sudo service postgresql restart
```

Conecte-se ao PostgreSQL e configure a senha para o usuário postgres:

```bash
psql -U postgres
ALTER USER postgres WITH ENCRYPTED PASSWORD 'suasenha';
\q
```

Altere novamente o arquivo `pg_hba.conf`:

```bash
sudo nano /etc/postgresql/9.6/main/pg_hba.conf
```

Altere a linha para:

```bash
local        all      postgres                  md5
```

Salve e reinicie o PostgreSQL.

Crie seu usuário e conceda permissões:

```bash
psql -U postgres -W
CREATE USER fulano WITH ENCRYPTED PASSWORD 'senha';
ALTER USER fulano WITH SUPERUSER;
```

## Instalando o Redis

Baixe e instale o Redis:

```bash
wget https://download.redis.io/redis-stable.tar.gz
tar xvzf redis-stable.tar.gz
cd redis-stable
make
sudo make install
redis-server --daemonize yes
```

## Instalando o Rails

Instale o Rails:

```bash
gem search '^rails$' --all
gem install rails -v 5.2.0
```

Teste a instalação criando uma nova aplicação:

```bash
rails new teste --database=postgresql
cd teste
rails s
```

Pronto! Seu ambiente está configurado e pronto para o desenvolvimento Ruby on Rails.