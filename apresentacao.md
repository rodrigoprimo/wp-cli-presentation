# Gerenciando o WordPress com o WP-CLI

Rodrigo Primo

WordCamp São Paulo 2013

.fx: titleslide

---

# Quem sou eu

* Sócio e desenvolvedor no Hacklab (hacklab.com.br)
* Trabalho com WordPress desde 2009
* Defensor do software livre
* Montanhista e ciclista nas horas vagas

---

# O que é o WP-CLI

* É um conjunto de ferramentas para gerenciar o WordPress a partir da linha de comando.
* Permite atualizar plugins, alterar opções, instalar temas, entre outras funções.
* Construído reaproveitando o código do próprio WP.
* Criado por Cristi Burcă (scribu) e Andreas Creten.

---

# Para que serve

* Automação
* Integração
* Desenvolvimento
* Administração

---

# Requisitos

* Linux ou OS X
    * Suporte não oficial ao Windows através do projeto WP-PowerShell - https://github.com/ericmann/WP-PowerShell
* PHP >= 5.3.2
* WordPress >= 3.4

---

# Como instalar

No terminal:

    !shell-session
    $ curl https://raw.github.com/wp-cli/wp-cli.github.com
    /master/installer.sh | bash

Adicionar as linhas abaixo ao .bash_profile para auto-complete dos comandos:

    !shell-session
    # WP-CLI Bash completions
    source $HOME/.wp-cli/vendor/wp-cli/wp-cli/utils/
    wp-completion.bash

Mais informações em http://wp-cli.org

---

# Arquivo de configuração

Arquivo wp-cli.yml na raiz do repositório

Formato YAML

Exemplo:

    !yaml
    path: src
    require: path/para/comando.php
    disabled_commands:
      - db drop
      - plugin install

---

# Estrutura dos comandos

---
# Uso básico

Lista dos comandos disponíveis:

    !shell-session
    $ wp

Ajuda de um comando específico:

    !shell-session
    $ wp help theme

Ajuda de um sub-comando específico:

    !shell-session
    $ wp help theme list

---

# Exemplos de comandos

---

## Baixar e instalar o WP

Baixar:

    !shell-session
    $ wp core download

Criar o wp-config.php:

    !shell-session
    $ wp core config --dbname=baseDeDados --dbuser=usuario

Instalar:

    !shell-session
    $ wp core install --url=http://wc.dev --title=WC
    --admin_user=admin --admin_password=wc
    --admin_email=wordcamp@wordpress.org

---

## Tarefas de administração 

Verificar a versão do WP:

    !shell-session
    $ wp core version

Atualizar WP:

    !shell-session
    $ wp core update

Atualizar plugins:

    !shell-session
    $ wp plugin update --all

---

## Tarefas de administração

Instalar plugin:

    !shell-session
    $ wp plugin install debug-bar

Instalar tema:

    !shell-session
    $ wp theme install p2

Ativar tema:

    !shell-session
    $ wp theme activate twentytwelve

---

## Tarefas de desenvolvimento

Alterar uma string no banco de dados (em especial a URL do WP):

    !shell-session
    $ wp search-replace textoAntigo textoNovo

Executar código:

    !shell-session
    $ wp shell

Ver o valor de uma opção serializada:

    !shell-session
    $ wp option get sidebars_widgets

---

## Banco de dados

Exporta a base de dados para um arquivo SQL:

    !shell-session
    $ wp db export dump.sql

Importa um arquivo SQL para a base de dados:

    !shell-session
    $ wp db import dump.sql

Roda uma query no banco:

    !shell-session
    $ wp db query "select * from wp_users"

---

## Combinando comandos

Deletar um conjunto de posts:

    !shell-session
    $ wp post delete $(wp post list --post_type='post'
    --format=ids)

---

# O WP-CLI é extensível

* Existe uma API que permite a criação de novos comandos ou subcomandos.
* Um novo comando pode ser distribuído através de um plugin ou pode ser incluído localmente no arquivo de configuração do WP-CLI.
* O wp-super-cache é um exemplo de plugin que pode ser controlado através do WP-CLI.

---

# O WP-CLI é extensível

* Para mais informações sobre como criar um comando: https://github.com/wp-cli/wp-cli/wiki/Commands-Cookbook
* Lista de comandos criados pela comunidade disponível em: https://github.com/wp-cli/wp-cli/wiki/List-of-community-commands

---

# Como contribuir

* http://wp-cli.org
* &#35;wordpress-cli no irc.freenode.net
* https://github.com/wp-cli/wp-cli/issues

---

# Obrigado!


__Rodrigo Primo__

rodrigo@hacklab.com.br

http://rodrigoprimo.com

http://github.com/rodrigoprimo

.fx: titleslide  

