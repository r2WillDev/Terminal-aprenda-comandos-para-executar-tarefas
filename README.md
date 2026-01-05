<p align="center">
  <h1>📘 Resumo de Estudos — Alura</h1>
  <p>Material de revisão e consultas rápidas sobre Terminal Linux, edição de arquivos, compactação, automação e comandos úteis.</p>

  <!-- Badges -->

  <p>
  <img alt="Linux" src="https://img.shields.io/badge/Linux-000000?style=flat-square&logo=linux" />
  <img alt="Bash" src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnu-bash" />
  <img alt="Shell Script" src="https://img.shields.io/badge/Shell_Script-3C873A?style=flat-square&logo=gnu" />
  <img alt="Git" src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git" />
  <img alt="Alura" src="https://img.shields.io/badge/Alura-1A73E8?style=flat-square" />
  </p>
</p>

---

## 📋 Índice

* [📌 Sobre o Repositório](#-sobre-o-repositório)
* [🔧 Visão Geral e Objetivo](#-visão-geral-e-objetivo)
* [🖥️ Fundamentos do Terminal Linux](#️-fundamentos-do-terminal-linux)

  * [Navegação e comandos básicos](#navegação-e-comandos-básicos)
  * [Listagem — `ls`](#listagem---ls)
  * [Criação, cópia, remoção e renomeação](#criação-cópia-remissão-e-renomeação)
  * [Redirecionamento e variáveis de ambiente](#redirecionamento-e-variáveis-de-ambiente)
* [📁 Manipulação e inspeção de arquivos](#️-manipulação-e-inspeção-de-arquivos)

  * [`wc`, `sort`, `uniq` — estatísticas e filtragem](#wc-sort-uniq---estatísticas-e-filtragem)
  * [`head`, `tail`] (#head-tail)
* [📝 Editores de texto (vi e nano)](#-editores-de-texto-vi-e-nano)

  * [Editor `vi` — resumo e atalhos](#editor-vi---resumo-e-atalhos)
  * [Editor `nano` — resumo e atalhos](#editor-nano---resumo-e-atalhos)
* [🗜️ Compactação e backup (`zip`, `tar`)](#️-compactação-e-backup-zip-tar)
* [⚙️ Automação com Shell Script e PATH](#️-automação-com-shell-script-e-path)
* [📚 Comandos SQL e Acesso MySQL](#-comandos-sql-e-acesso-mysql)
* [🧭 Dicas práticas para DevOps](#-dicas-práticas-para-devops)
* [📌 Observações finais](#-observações-finais)

---

## 📌 Sobre o Repositório

Este repositório reúne resumos das aulas assistidas na plataforma **Alura** sobre **HTTP, APIs, arquitetura web, segurança (HTTPS/TLS)** e uso prático de ferramentas (DevTools, Postman, Telnet, Wireshark). O objetivo é oferecer material de **revisão rápida, consulta técnica e apoio aos estudos**.

---

## 🔧 Visão Geral e Objetivo

Fornecer um guia enxuto e prático com comandos, exemplos e atalhos usados no dia a dia de desenvolvimento e administração de sistemas — foco em velocidade de consulta e aplicação em ambientes Linux e VMs.

---

# 🖥️ Fundamentos do Terminal Linux

**Objetivo:** Navegar, criar, organizar e manipular arquivos e diretórios usando comandos do terminal.

### Navegação e comandos básicos

```bash
pwd            # mostra diretório atual
cd /caminho    # entra em um diretório
cd ..          # volta para o diretório pai
cd 'Área de Trabalho'  # usar aspas para nomes com espaços
# Autocompletar: Tab
```

### Listagem — `ls`

```bash
ls              # lista arquivos
ls -a           # mostra arquivos ocultos
ls -l           # listagem detalhada (permissões, dono, data, tamanho)
ls -la          # combinação: detalhado + ocultos
ls --help       # ajuda
```

### Criação, cópia, remoção e renomeação

```bash
mkdir estudos                 # criar diretório
touch comandos.txt            # criar arquivo vazio
cat comandos.txt              # visualizar conteúdo
cp arquivo.txt destino/       # copiar arquivo
cp *.txt 'estudos de terminal'/  # curinga
mv dicas.txt anotacoes.txt    # renomear/mover
rm exercicios.txt             # remover arquivo
rmdir pasta_vazia             # remover diretório vazio
rm -r pasta_com_conteudo      # remover diretório com conteúdo (cuidado!)
```

> [!WARNING]
> `rm -r` remove arquivos recursivamente e de forma definitiva. Use com muito cuidado.

### Redirecionamento e escrita em arquivos

```bash
# sobrescrever (cria/replace)
echo "ls lista arquivos" > comandos.txt

# adicionar sem apagar
echo "clear - limpa a tela" >> comandos.txt
```

---

# 📁 Manipulação e inspeção de arquivos

### `wc` — estatísticas de arquivo

```bash
wc arquivo.txt    # linhas, palavras e caracteres
wc -l arquivo.txt # apenas linhas
```

### `uniq` — linhas duplicadas / contagem

```bash
uniq arquivo.txt        # remove duplicatas consecutivas
uniq -D arquivo.txt     # mostra duplicadas
uniq -c arquivo.txt     # conta ocorrências
uniq -i arquivo.txt     # ignora case
# ajuda
uniq --help
```

### `sort` — ordenação

```bash
sort arquivo.txt    # ordena (saída padrão)
```

> [!TIP]
> Para identificar duplicatas corretamente combine `sort` + `uniq`:
>
> ```bash
> sort arquivo.txt | uniq -c | sort -nr
> ```
>
> Esse pipeline ordena, conta e exibe as linhas mais frequentes primeiro.

### `head` / `tail` — visualização parcial

```bash
head -n 10 arquivo.txt      # primeiras 10 linhas
head -c 300 texto.txt       # primeiros 300 bytes/caracteres

tail -n 2 arquivo.txt       # últimas 2 linhas
tail -c 100 arquivo.txt     # últimos 100 bytes/caracteres
```

---

# 📝 Editores de texto (vi e nano)

Organizados para consulta rápida: modos, comandos essenciais, atalhos e exemplos.

## Editor `vi` — resumo e atalhos

**Quando usar:** ambiente de servidores, acesso remoto e quando não é possível instalar outros editores.

### Modos principais

* **Modo de comando** — padrão ao abrir o `vi`.
* **Modo de inserção** — permite inserir/editar texto (pressione `i`, `A` etc.).

### Comandos essenciais (resumo)

```text
i    → inserir antes do cursor
A    → inserir ao final da linha
O    → nova linha abaixo
Esc  → voltar ao modo de comando
```

### Salvamento e saída

```text
:w           # salvar
:w nome.txt  # salvar como
:q           # sair
:wq          # salvar e sair
:q!          # sair sem salvar
```

### Edição de linhas

```text
yy  → copiar (yank) linha
dd  → recortar (delete) linha
p   → colar
```

### Busca e substituição

```bash
:/texto            # busca por "texto"
:s/antigo/novo     # substitui a primeira ocorrência na linha atual
:%s/antigo/novo/g  # substitui globalmente no arquivo
```

> [!TIP]
> Uso comum em **edição de configurações**, **análise de logs** e **manutenção em servidores**.

### Tabela de atalhos — `vi`

| Tecla / Comando | Ação                       |
| --------------- | -------------------------- |
| `i`             | Entrar em modo de inserção |
| `A`             | Inserir ao final da linha  |
| `O`             | Nova linha abaixo          |
| `Esc`           | Voltar ao modo de comando  |
| `:w`            | Salvar                     |
| `:q`            | Sair                       |
| `:wq`           | Salvar e sair              |
| `:q!`           | Sair sem salvar            |
| `yy`            | Copiar linha               |
| `dd`            | Recortar linha             |
| `p`             | Colar                      |

---

## Editor `nano` — resumo e atalhos

**Quando usar:** edições rápidas, iniciantes ou situações com interface simplificada.

```bash
nano arquivo.txt
```

### Atalhos principais

|         Tecla | Ação                 |
| ------------: | -------------------- |
| `^G` (Ctrl+G) | Ajuda                |
| `^O` (Ctrl+O) | Salvar (Write Out)   |
| `^X` (Ctrl+X) | Sair                 |
| `^K` (Ctrl+K) | Recortar linha (cut) |
| `M-6` (Alt+6) | Copiar (mark + copy) |
| `^U` (Ctrl+U) | Colar                |

> [!TIP]
> No `nano`, `^` representa `Ctrl` e `M` representa `Alt`.

---

# 🗜️ Compactação e backup (`zip`, `tar`)

### `zip` (compactar diretórios)

```bash
zip -r backup.zip backup/   # -r para recursivo (diretórios)
less backup.zip             # verificar conteúdo (modo leitura)
```

### `unzip` (descompactar)

```bash
unzip backup.zip
unzip -q backup.zip   # execução silenciosa (quiet)
```

### `tar` (tar.gz)

```bash
# compactar (create + gzip + file)
tar -czf backup.tar.gz backup/

# descompactar (extract + gzip + file)
tar -xzf backup.tar.gz
```

> [!WARNING]
> Comandos de remoção e operações de compressão devem ser testados em cópias/ambientes controlados antes de rodar em produção.

---

# ⚙️ Automação com Shell Script e PATH

### Criando um script simples

```bash
# criar arquivo
nano script.sh

# exemplo de conteúdo
cp /home/usuario/pasta_logs/*.txt /home/usuario/backup/

# dar permissão de execução
chmod +x script.sh

# executar
./script.sh
```

### Variável `PATH` e execução por nome

```bash
echo $PATH
export PATH=$PATH:/home/usuario/script
# agora é possível executar apenas pelo nome
bkp.sh
```

---

# 📚 Comandos SQL e Acesso MySQL

```bash
sudo mysql       # acessar MySQL como root
```

```sql
SHOW DATABASES;   -- listar bancos
CREATE DATABASE TERMINAL;  -- criar banco
EXIT;             -- sair
```

---

# 🧭 Dicas práticas para DevOps

* Priorize comandos que não alterem arquivos quando estiver em investigação (`cat`, `less`, `head`, `tail`, `wc`, `grep`, `sort`, `uniq`).
* Use scripts para padronizar rotinas (backup, coleta de logs, rotação). Mantenha logs de execução.
* Teste `rm -r` e scripts de remoção em ambientes de teste. Prefira `rm -i` para confirmar interativamente quando necessário.
* Versione scripts e arquivos de configuração com Git. Inclua `README` e comentários nos scripts.

---

## 📌 Observações finais

* Todo o conteúdo foi consolidado a partir dos estudos realizados na Alura.
* O foco deste material é proporcionar compreensão prática para ambientes de desenvolvimento, servidores e rotinas de DevOps.

---

## 🚀 Próximos estudos

* Git e GitHub: domínio de controle de versão e fluxo de trabalho (branches, PRs, CI/CD).

---

> Arquivo gerado automaticamente com base em resumos de aula. Aguarde revisões e sugestões de melhoria.
