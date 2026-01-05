# 📘 Resumo de Estudos – Alura

## 📌 Sobre o Repositório
Este repositório reúne resumos das aulas assistidas na plataforma **Alura** sobre **HTTP, APIs, arquitetura web, segurança (HTTPS/TLS)** e uso prático de ferramentas (DevTools, Postman, Telnet, Wireshark).

O objetivo é oferecer um material de **revisão rápida, consulta técnica e apoio aos estudos**. Todas as informações contidas neste README foram extraídas exclusivamente dos resumos das aulas assistidas e organizadas para leitura clara e objetiva.

---

## 📋 Índice
* [📌 Sobre o Repositório](#-sobre-o-repositório)
* [📚 Conteúdos Estudados](#-conteúdos-estudados)
* [Terminal Linux e Edição de Arquivos](#terminal-linux-e-edição-de-arquivos)
* [Editor vi](#editor-vi)
* [Visualização e Filtragem de Arquivos](#visualização-e-filtragem-de-arquivos)
* [Editor Nano e Inspeção de Arquivos](#editor-nano-e-inspeção-de-arquivos)
* [📌 Observações](#-observações)

---

## Terminal Linux e Edição de Arquivos

### Curso: Fundamentos do Terminal Linux
**Plataforma:** Alura

---

## Editor vi

### Conteúdos abordados
* Conceito e finalidade do editor **vi**
* Modos de operação
* Edição, salvamento e saída
* Copiar, colar, recortar
* Busca e substituição de texto

### Resumo das aulas
O **vi** é um editor de texto padrão em muitas distribuições Linux, amplamente utilizado em servidores e acessos remotos, principalmente quando não há permissão para instalar outros editores.

#### Modos principais
* **Modo de comando**: modo padrão ao abrir o vi.
* **Modo de inserção**: permite editar o texto.

#### Comandos essenciais
* `i` → inserir texto antes do cursor
* `A` → inserir texto ao final da linha
* `O` → criar nova linha abaixo
* `Esc` → voltar ao modo de comando

#### Salvamento e saída
* `:w` → salvar arquivo
* `:w nome.txt` → salvar com nome
* `:q` → sair
* `:wq` → salvar e sair
* `:q!` → sair sem salvar

#### Edição de linhas
* `yy` → copiar linha
* `dd` → recortar linha
* `p` → colar conteúdo

#### Busca e substituição
```bash
:/texto
:s/antigo/novo
```
> [!TIP]
> Uso comum em **edição de configurações**, **análise de logs** e **manutenção em servidores**.

## Visualização e Filtragem de Arquivos
### Conteúdos abordados
- Estatísticas de arquivos

- Linhas duplicadas

- Ordenação de dados

- Uso de flags e ajuda


O terminal permite **analisar arquivos de texto sem editá-los**, oferecendo rapidez e eficiência.

Estatísticas com ```wc```

```bash
wc arquivo.txt
```

Retorna:

- Quantidade de linhas

- Quantidade de palavras

- Quantidade de caracteres

### Linhas duplicadas com  ```uniq```
- Remover duplicidade:

```bash
uniq arquivo.txt
```

- Mostrar duplicadas:

```bash
uniq -D arquivo.txt
```
- Contar ocorrências:

```bash
uniq -c arquivo.txt
```

Flags importantes:

- ```-D``` → linhas duplicadas

- ```-c``` → contagem

- ```-i``` → ignora maiúsculas/minúsculas

### Ajuda no terminal
```Bash
uniq --help
```
Fundamental para consultar opções e flags disponíveis.

### Ordenação com ```sort```
```Bash
sort arquivo.txt
```
Ordena o conteúdo, geralmente em ordem alfabética, sem alterar o arquivo original.

## Editor Nano e Inspeção de Arquivos
### Conteúdos abordados
- Uso do editor **Nano**

- Atalhos principais

- Visualização de início e fim de arquivos

### Resumo das aulas
O **Nano** é um editor simples e intuitivo, indicado para edições rápidas e para quem está começando.

### Abrir o Nano
```Bash
nano
```

### Atalhos principais
- ```Ctrl + G``` → ajuda

- ```Ctrl + O``` → salvar

- ```Ctrl + X``` → sair

- ```Ctrl + K``` → recortar

- ```Alt + 6``` → copiar

- ```Ctrl + U``` → colar

O símbolo ```^``` representa a tecla **Ctrl**, e ```M``` representa **Alt**.

### Visualização de arquivos sem abrir editores
### Início do arquivo — ```head```
```Bash
head -c 300 texto.txt
```
Exibe os primeiros caracteres do arquivo.

### Final do arquivo — ```tail```
```Bash

tail -n 2 texto.txt
tail -c 100 texto.txt
```
Permite visualizar linhas ou caracteres finais. Esses comandos são muito usados para **verificação rápida**, **análise de logs** e **automação**.

## Terminal Linux – Fundamentos
**Objetivo:** Aprender a navegar, criar, organizar e manipular arquivos e diretórios utilizando comandos do terminal.

### Navegação e Comandos Básicos
- ```pwd``` Exibe o diretório atual em que o usuário está.

- ```cd``` Permite navegar entre diretórios.

  - ```cd ..``` → volta para o diretório anterior

  - Diretórios com espaço devem ser usados com **aspas simples**:

```Bash
cd 'Área de Trabalho'
```
  - ```.``` → diretório atual

  - ```..``` → diretório pai

- **Autocompletar** (Tab) Completa automaticamente nomes de arquivos e pastas.

### Listagem e Flags do ```ls```
- ```ls``` → Lista arquivos e diretórios.

- ```ls --help``` → Exibe documentação.

- ```ls -a``` → Lista arquivos ocultos (que começam com ```.```).

- ```ls -l``` → Exibe listagem detalhada (permissões, dono, data, tamanho).

- ```ls -la``` → Combina listagem detalhada com arquivos ocultos.

### Criação e Manipulação de Arquivos
- ```mkdir``` — Criar diretórios

```Bash
mkdir estudos
```
- ```touch``` — Criar arquivo vazio

```Bash
touch comandos.txt
```
- ```cat``` — Visualizar conteúdo de arquivos

```Bash
cat comandos.txt
```
### Redirecionamento e Escrita em Arquivos
- ```echo``` — Inserir texto em arquivos

- Operador ```>``` (Cria ou **sobrescreve**):

```Bash

echo "ls lista arquivos" > comandos.txt
```
- Operador ```>>``` (**Adiciona** conteúdo sem apagar):

```Bash

echo "clear - limpa a tela" >> comandos.txt
```
### Remoção e Renomeação
- ```rm``` — Remover arquivos

```Bash
rm exercicios.txt
```
- ```mv``` — Renomear ou mover arquivos

```Bash
mv dicas.txt anotacoes.txt
```
- rmdir — Remover diretórios vazios

```Bash
rmdir estudos
```
### Cópia de Arquivos e Backup
- ```cp``` — Copiar arquivos

```Bash
cp anotacoes.txt 'estudos de terminal'/
```
### Cópia de múltiplos arquivos (caractere curinga)
- ```*``` representa qualquer conjunto de caracteres.

- Copiar todos os arquivos ```.txt```:

```Bash

cp *.txt 'estudos de terminal'
```
- Copiar arquivos de extensões diferentes:

  - ```.log``` → ```*.log```

  - Todas → ```*.*```

### Limpeza do Terminal
- ```clear```→ Limpa a tela do terminal no Linux (equivalente ao ```cls``` no Windows).

## Fundamentos de Terminal, Linux e Ambiente de Desenvolvimento
### Introdução ao Terminal e Linux
- O **terminal** é amplamente utilizado em **servidores** e **aplicações back-end**.

- O **Linux** é um **SO open source**, base para a maioria dos servidores e bancos de dados.

### Máquina Virtual e VirtualBox
- Uma **máquina virtual (VM)** simula um computador dentro de outro.

- O **VirtualBox** gerencia essas VMs.

- Instalação típica do Ubuntu Desktop (LTS) envolve definir:

  - **Memória:** 2048 MB

  - **CPU:** 1 processador

### Primeiros Passos no Terminal Linux
O terminal exibe: ```usuario@maquina:~$```

### Comandos básicos aprendidos
- ```pwd``` → Exibe diretório atual.

- ```ls``` → Lista arquivos.

- ```cd nome_da_pasta``` → Entra em um diretório.

- ```cd ..``` → Retorna ao diretório anterior.

### Estrutura de diretórios
Cada usuário possui um diretório em ```/home/usuario```.

## Terminal Linux – Comandos e Compactação
### Compactação e Descompactação com ZIP
### Compactação
```Bash
zip -r backup.zip backup
```
- A flag ```-r``` é obrigatória para compactar diretórios recursivamente.

Verificação do conteúdo:

```Bash
less backup.zip
```

### Descompactação
```Bash

unzip backup.zip
```
- ```unzip -q backup.zip``` → Execução silenciosa (quiet).

### Remoção de diretórios não vazios
```Bash

rm -r backup
```
> [!WARNING]
> ```rm -r``` remove arquivos de forma recursiva e definitiva.

### Compactação e Descompactação com TAR
### Compactação (```.tar.gz```)
Flags: ```c``` (create), ```z``` (gzip), ```f``` (file).

```Bash
tar -czf backup.tar.gz backup
```
- O ```tar``` trabalha de forma recursiva por padrão.

### Descompactação
Flags: ```x``` (extract), ```z``` (gzip), ```f``` (file).

```Bash
tar -xzf backup.tar.gz
```

## Linux e Terminal: Automação e Pacotes
### Automação de tarefas com scripts (Shell Script)
### Conceito
Scripts ```.sh``` permitem automatizar tarefas repetitivas (backup, cópia de logs, etc.).

### Criação e Permissões
1. Criar arquivo com editor:

```Bash
nano script.sh
```
Conteúdo exemplo:

```Bash
cp /home/usuario/pasta_logs/*.txt /home/usuario/backup
```
2. Dar permissão de execução:

```Bash
chmod +x script.sh
```
3. Executar:

```Bash
./script.sh
```
### Execução de scripts com variáveis de ambiente
### Variável PATH
Define onde o sistema procura executáveis. Adicionar o diretório do script ao PATH permite executá-lo de qualquer lugar.

1. Visualizar PATH:

```Bash

echo $PATH
```
2. Exportar novo caminho:

```Bash
export PATH=$PATH:/home/usuario/script
```
3. Executar apenas pelo nome:

```Bash
bkp.sh
```
### Instalação de aplicações via terminal (APT)
O **APT** gerencia pacotes no Ubuntu. Requer ```sudo``` (permissões administrativas).

- Instalar MySQL:

```Bash
sudo apt install mysql-server
```
- Verificar status do serviço (Systemd):

```Bash
systemctl status mysql
```
### Acesso ao MySQL
```Bash
sudo mysql
```
### Comandos básicos SQL
- Listar bancos:

```SQL

show databases;
```
- Criar banco:

```SQL

CREATE DATABASE TERMINAL;
```
- Sair:

```SQL
exit
```

## 📌 Observações Finais
- Todo o conteúdo foi baseado exclusivamente nos estudos realizados na Alura.

- O foco é compreensão prática para ambientes de desenvolvimento e servidores.

## 🚀 Próximos estudos

- Git e GitHub: dominando controle de versão de código
