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
Criando o ambiente de desenvolvimento web Ruby on Rails

Olá, antes de começar o tutorial vou contar uma pequena experiência nessa instalação de ambiente. Quando comecei com ruby on rails alguns anos atrás sofri bastante com a preparação deste ambiente, minhas primeiras tentativas de configuração foram horríveis, sempre dava erro, sem falar que existem milhões de tutoriais explicando como configurar esse ambiente e nenhum tinha feedback, até mesmo agora quando troquei de computador precisei correr atrás de um tutorial para criar esse ambiente. Então não se preocupe se não conseguir de primeira ou se você não entendeu algo, meu e-mail está à disposição para suas dúvidas, vou explicar de uma forma simples e bem didática, espero que gostem!!!

Para funcionar o Ruby on Rails em nossas máquinas precisamos configurar com algumas dependências que fazem com que RoR possa funcionar perfeitamente em sua máquina e ajudar muito no seu dia dia, mas não estranhe quando se deparar com outras dependências, pois ao longo do tutorial vou explicando as funcionalidades.

Instalando o Ruby on rails com dependências necessárias Antes, você precisa atualizar seu Debian
``````
sudo apt update
sudo apt upgrade
``````
Isso vai atualizar seu sistema e deixar ele redondo para o resto das instalações

Próximo passo é para o git.

sudo apt install git
O que é git?

Git é um sistema de controle de versão de arquivos e através deles podemos desenvolver projetos nos quais diversas pessoas podem contribuir simultaneamente no mesmo projeto, e como seria? Editando e criando novos arquivos e permitindo que os mesmos possam existir sem o risco de suas alterações serem subescritas.

após a instalação vamos para configuração
``````
git config ---global user.name "seu nome"
git config –global user.email "seu email"
``````
essa configuração é para o git entender de quem é os commits e se tem autorização. Caso você não entendeu, vou falar mais sobre git na próximo tutorial.

O que é nodejs?

Node.js é uma plataforma construída sobre o motor JavaScript do Google Chrome para facilmente construir aplicações de rede rápidas e escaláveis. Node.js usa um modelo de I/O direcionada a evento não bloqueante que o torna leve e eficiente, ideal para aplicações em tempo real com troca intensa de dados através de dispositivos distribuídos.

Antes de instalar o nodejs precisamos do repositório
``````
sudo curl -sSL https://deb.nodesource.com/setup_16.x | sudo bash -
``````
agora vamos a instalação
``````
sudo apt install nodejs
``````
O que é Yarn

É um gerenciador ( dependências) de pacotes javascript que podemos via linha de comandos, baixar pacotes para nossa aplicação que foram desenvolvidos por outras pessoas, além de poder compartilhar também, além de ser uma alternativa ao npm.

Agora vamos instalar o Yarn, como você vai ver aqui, essa instalação é um pouco complexa porque vai precisar de uma chave GPG

O que é GPG?

GPG é uma criptografia assimétrica, ou seja, emprega um par de chaves para alcançar seu objetivo – uma chave pública e uma chave privada.
``````
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add
``````
também vamos adicionar o repositório do Yarn
``````
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
``````
Finalmente vamos a instalação do yarn

O Yarn usa o mesmo package.json que já temos no projeto em JavaScript e não adiciona nenhuma outra dependência,utilizando o mesmo repositório que o NPM já roda.

Qual a vantagem do Yarn?

Uma das vantagens do Yarn é ele ser mais rápido, tende a resolver alguns conflitos de versão de módulo, cria um cash local para caso você já tenha utilizado algum módulo qualquer com Yarn, essa versão específica já fica salva na sua máquina e caso você precise usar em outro projeto, ela utiliza do cash e não precisa baixar um novo, além disso, resolve algumas coisas interessantes como, por exemplo, é muito comum fazermos:
``````
sudo apt install yarn
``````
Agora vamos para o tão esperado rvm

O que é o RVM?

RVM é acrônimo para Ruby Version Manager, uma ferramenta de linha de comando que possibilita instalar e gerenciar diversas versões do Ruby e suas gems. Usar o RVM facilita a transição entre versões do Ruby e versões das gems. Usar o RMV é muito simples, o único requisito básico é um ambiente POSIX (linux, bsd, etc), nesse tutorial vou instalar no Mac, basta abrir o terminal e executar o comando abaixo:

Sem mais delogas vamos direto para instalação
``````
\curl -sSL https://get.rvm.io | bash
``````
agora vamos dar um endereço para o seu bash executar o rvm no
``````
source ~/.rvm/scripts/rvm
``````
Source port é o nome dado à portabilização de um programa que é geralmente apenas um arquivo executável que foi modificado a partir do código de fonte do programa original e substituiu o executável original, para que possa ser rodado em uma outra plataforma para a qual não foi originalmente escrito.

vou falar mais sobre rvm e suas versões no próximo tutorial, no momento vamos instalar essa versão
``````
rvm install 3.2.2
``````
Vamos usar essa versão
``````
rvm use 3.2.2
``````
Os Ideais do Criador do Ruby

O Ruby é uma linguagem com um cuidadoso equilíbrio. O seu criador, Yukihiro “Matz” Matsumoto, uniu partes das suas linguagens favoritas (Perl, Smalltalk, Lisp e outros) para formar uma nova linguagem que equilibra a programação funcional com a programação imperativa. Ele disse com frequência que está “tentando tornar o Ruby natural, não simples”, de uma forma que reflita a vida. Elaborando sobre isto, acrescenta: O Ruby é simples na aparência, mas muito complexo no interior, tal como o corpo humano.

RubyGems

RubyGems é um gerenciador de pacotes para a linguagem de programação Ruby que provê um formato padrão para a distribuição de programas Ruby e bibliotecas em um formato auto-suficiente chamado de gem (“jóia”, do inglês), uma ferramenta projetada para gerenciar facilmente a instalação de gems, e um servidor para distribuí-los. RubyGems foi criado em volta de novembro de 2003 e agora faz parte da biblioteca padrão do Ruby versão 1.9 a diante.

Redis Isso deve ser novo pra você certo ou não?

vamos usar o redis nesse ambiente nos próximos tutoriais, vou me aprofundar nesse banco não relacional,

a instalação dele é meia complexa, mais é só seguir meus passos que você vai conseguir

Redis: o que é, e para que serve?

um banco de dados não relacional, também conhecido por NOSQL (Not Only SQL), que foi criado por Salvatore Sanfiippo e liberado em forma open-source em 2009. Redis significa REmote DIctionary Server, e pelo seu significado, já podemos ter uma ideia de como ele trabalha e armazena os dados. Os dados são armazenados na forma de chave-valor, lembrando a estrutura do Dictionary do .net e do Map do Java. Um ponto importante que vale chamar a atenção aqui, é que o valor utilizado como chave no Redis pode possuir diferentes formatos, podendo ser strings, hashes, lists, sets e sets ordenados.z vai fazer o download
``````
wget https://download.redis.io/redis-stable.tag.gz
``````
logo em seguida vamos descompactar o aquivo baixado
``````
tar xvzf redis-stable.tar.gz
``````
você precisa entrar no diretório da pasta redis-stable
``````
cd redis-stable
``````
já dentro da pasta vamos a instalação
``````
make
make test
``````
Aguarde…☕
``````
sudo make install
``````
tudo certo?

Agora vamos executar
``````
redis-server –daemonize yes
``````
O Redis é extremamente rápido, tanto para escrita como para leitura dos dados, graças ao fato de armazenar seus dados em memória. Apesar disso, o Redis permite que os dados sejam persistidos fisicamente caso desejado.

Agora vamos para a instalação do postgresql

bom vou usar esse banco de dados para nossas aulas, mais caso queira usar outro banco fique a vontade. Por padrão o Rails usa o SQLite3 pois é bem simples, versátil e consegue se comportar bem em um ambiente de desenvolvimento.

Instalação do postgresql
``````
sudo apt install postgresql
``````
O que é o PostgreSQL?

O PostgreSQL é um sistema de gerenciamento de banco de dados objeto-relacional baseado no POSTGRES Versão 4.2 desenvolvido pelo Departamento de Ciência da Computação da Universidade da Califórnia em Berkeley. O POSTGRES foi pioneiro de vários conceitos que somente se tornaram disponíveis muito mais tarde em alguns sistemas de banco de dados comerciais.

O PostgreSQL é um descendente de código fonte aberto deste código original de Berkeley, que suporta grande parte do padrão SQL e oferece muitas funcionalidades modernas, como:

comandos complexos
chaves estrangeiras
gatilhos
visões
integridade transacional
controle de simultaneidade multiversão
Além disso, o PostgreSQL pode ser ampliado pelo usuário de muitas maneiras como, por exemplo, adicionando novos tipos de dado, funções, operadoresfunções de agregação, métodos de índice, linguagens procedurais -Devido à sua licença liberal, o PostgreSQL pode ser utilizado, modificado e distribuído por qualquer pessoa para qualquer finalidade, seja particular, comercial ou acadêmica, livre de encargos.
Antes de irmos para outros passos precisamos instalar uma dependência da
``````
gem pg
``````
``````
sudo apt install libpq-dev
``````
Bom para que funcione precisamos configura-lo para que o mesmo rode perfeitamente no seu ambiente, antes de mais nada vamos verificar qual é a versão que foi instalado no seu ambiente, não importa qual é a sua versão que está instalado no seu ambiente, essa configuração vai funcionar em quase todas versões anteriores essa configuração é um pouco complexa, mais você fazendo com calma e com atenção você consegue primeiro vamos ao .conf

O pg_hba.conf controla as que máquinas terão acesso ao PostgreSQL e a autenticação dessas máquinas clientes (sem autenticação ou através de outras formas, trust, md5, crypt, etc). Quando é especificada a autenticação trust, o PostgreSQL assume que qualquer um que possa se conectar ao servidor está autorizado a acessar o banco de dados como qualquer usuário que seja especificado (incluindo o superusuário do banco de dados). Os métodos de autenticação baseados em senha são md5, crypt e password. Estes métodos operam de forma semelhante, exceto com relação à forma como a senha é enviada através da conexão, mas somente o método md5 suporta senhas criptografadas armazenadas no catálogo do sistema.

Vamos á alteração
``````
sudo nano /etc/postgresql/9.6/main/pg_hba.conf
``````
Indentifique as linhas abaixo, com elas que vamos fazer á alteração

# Database administrative login by Unix domain socket
``````
    local        all       postgres              peer
    ``````
Altere para trust


# Database administrative login by Unix domain socket
``````
     local        all      postgres                  trust
``````
pronto!

Salva e vamos reiniciar o postgresql
``````
/etc/init.d/postgresql restart ou service postgresql restart
``````
vamos conectar
``````
psql -U postgres
``````
precisamos de uma senha para o usuário postgres certo?
``````
ALTER USER postgres WITH ENCRYPTED PASSWORD ‘suasenha’;
``````
agora vamos sair do postgres
``````
\q
``````
novamente vamos alterar o socket
``````
sudo nano /etc/postgresql/9.6/main/pg_hba.conf
``````
indentifique as linhas abaixo, com elas que vamos fazer á alteração


# Database administrative login by Unix domain socket
``````
     local        all      postgres                  trust
``````
altere a para


# Database administrative login by Unix domain socket
``````
     local        all      postgres                  md5
``````
pronto!

Salva e vamos reiniciar o postgresql
``````
/etc/init.d/postgresql restart ou service postgresql restart
``````
Vamos acessar novamente o postgres
``````
psql -U postgres -W
``````
digite sua senha

pronto o usuario postgres está ok, agora vamos para seu usuário, o que você vai usar no seu ambiente
``````
CREATE USER fulano WITH ENCRYPTED PASSWORD ‘senha’;
``````
observe que você criou seu usuário, agora vamos dar as permissões para ele como um super user
``````
ALTER USER fulano WITH SUPERUSER;
``````
Pronto seu postgresql está funcionando perfeitamente!

Rails

O que é rails?

Ruby on Rails é um framework que faz o desenvolvimento, implantação e manutenção de uma aplicação web mais fácil e essa utiliza uma linguagem orientada à objeto conhecida como Ruby. Para introduzi-lo é preciso que o desenvolvedor conheça algumas de suas filosofias. Essas são:

a instalação dele é bem simples

verifique todas as versões do rails
``````
gem search '^rails$' --all
gem install rails -v 5.2.0
``````
pronto seu ambiente está todo configurado!

Vamos testar?

Vamos criar uma aplicação
``````
rails new teste --database=postgresql
cd /teste
rails s
``````

Pronto! Seu ambiente está configurado e pronto para o desenvolvimento Ruby on Rails.