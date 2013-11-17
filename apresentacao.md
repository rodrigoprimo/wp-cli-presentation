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
* http://rodrigoprimo.com
* http://github.com/rodrigoprimo

---

# O que é o WP-CLI

É um conjunto de ferramentas para gerenciar o WordPress a partir da linha de comando.

Permite atualizar plugins, alterar opções, instalar temas e muito mais.

Construído reaproveitando o código do próprio WP.

Criado por Cristi Burcă (scribu) e Andreas Creten.

---

# Para que serve

* Automação
* Integração
* Desenvolvimento
* Administração

---

# Requisitos

* Ambiente UNIX-like (Linux, OS X, FreeBSD, Cygwin)
* PHP >= 5.3.2
* WordPress >= 3.4
* Suporte não oficial ao Windows através do projeto WP-PowerShell - https://github.com/ericmann/WP-PowerShell

---

# Como instalar

No terminal:

    !shell-session
    curl https://raw.github.com/wp-cli/wp-cli.github.com
    /master/installer.sh | bash

Adicionar as linhas abaixo ao .bash_profile para auto-complete dos comandos:

    !shell-session
    # WP-CLI Bash completions
    source $HOME/.wp-cli/vendor/wp-cli/wp-cli/utils/
    wp-completion.bash

---

# Uso básico

---

# Exemplos de comandos

---

# Arquivo de configuração

Arquivo wp-cli.yml na raiz do repositório

Formato YAML

Exemplo:

    !yaml
    path: wp-core
    disabled_commands:
      - db drop
      - plugin install

---

# Como contribuir

---

# Referências

* http://wp-cli.org
* &#35;wordpress-cli no irc.freenode.net

---

# Perguntas?

