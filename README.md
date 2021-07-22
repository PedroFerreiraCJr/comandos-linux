<h1 align="center">Comandos Básicos do Linux</h1>
  Repositório contendo uma referência a comandos básicos utilizados no dia a dia no terminal linux.
<br/>

<p align="center">
  <img width="460" height="300" src="https://upload.wikimedia.org/wikipedia/commons/6/66/Openlogo-debianV2.svg">
</p>


## pwd
O comando **pwd** tem como saída o diretório atual do usuário.
```bash
$ pwd
```

## ls
O comando **ls** tem como saída uma listagem de arquivos e diretórios que estão contidos na pasta atual do usuário. Esse comando opcionalmente, recebe como parâmetro o diretório onde o usuário quer que o comando seja executado.
```bash
$ ls /home/$USER
```
O comando acima, lista os arquivos e diretórios contidos na pasta informada como parâmtro.

## echo
O comando **echo** tem como saída a mensagem que foi passada como parâmetro de sua invocação.
```bash
$ echo "Seja bem-vindo ao terminal do Linux."
```

Um exemplo de uso desse comando é quando de deseja salvar o parâmetro desse comando como uma texto em um arquivo. Para isso é utilizado o operador de redirecionamento de saída (**>**) para a direita.
```bash
$ echo "Seja bem-vindo ao terminal do Linux" > file.txt
```
O comando acima, salva o texto no arquivo informado.

## cat
O comando **cat** mostra na saída padrão o conteúdo do arquivo informado como parâmtro.
```bash
$ cat file.txt
```
O comando **cat** lê o arquivo e mostra o conteúdo dele na saída padrão.

## clear
O comando **clear** limpa a tela do terminal.
```bash
$ clear
```

## man
O comando **man** recebe como parâmetro o nome do comando que se está querendo obter mais informações, portanto, o comando **main** mostra uma ajuda ou manual do comando informado.
```bash
$ man pwd
```

## whoami
O comando **whoami** mostra na saída padrão o nome do usuário atual.
```bash
$ whoami
```

## cd
Com o comando **cd** é possível fazer a navegação nos diretórios do sistema linux.
```bash
$ cd /
```
O comando acima faz com que o diretório atual seja alterado para o (**/**), ou diretório raiz do sistema.

```bash
$ cd $HOME
```
O comando acima navega para o diretório que é a raiz do usuário atual. O mesmo resultado pode ser obtido simplesmente digitando somente **cd** no terminal, por padrão, o comando **cd** volta para o diretório que é o *home* do usuário atual logado no sistema.
```bash
$ cd ..
```
O comando acima, navega para o diretório acima do diretório atual.

## mkdir
O comando **mkdir** cria um diretório na pasta atual do usuário.
```bash
$ mkdir workspace
```
O comando acima cria o diretório *workspace* na pasta atual.

## rmdir
O comando **rmdir** remove o diretório informado como parâmetro do comando.
```bash
$ rmdir workspace
```
O comando acima remove o diretório *workspace* informado, caso esteja vazio.


## rm
O comando **rm** remove o arquivo/diretório informado como parâmetro do comando.
```bash
$ rm file.txt
```
O comando acima remove o arquivo *file.txt*, informado.

O comando **rm** ainda pode receber como parâmetro **-r** para apagar o diretório informado de forma recursiva, ou seja, os diretório internos a pasta informada serão apagados, e posteriormente o diretório informado para o comando.
```bash
$ rm -r workspace
```
O comando acima remove o diretório workspace totalmente, mesmo que contenha arquivos ou pastas dentro dele.

Os símbolos **?**, **\***, são interpretados de forma diferente, pois são considerador wildcards, ou simbolos especiais que podem denotar, *um caracter*, ou *multiplos caracteres* respectivamente.
Por exemplo, para apagar todos os arquivos com a extensão *.txt* no diretório workspace, segue o comando:
```bash
$ rm workspace/*.txt
```
O comando acima remove todos os arquivos com a extensão *.txt*, mas não remove a pasta.

## cp
Com o comando **cp** é possível fazer a cópia de arquivos ou diretórios. O comando **cp** recebe dois parâmetros, o primeiro é o arquivo/diretório de origem, e o segundo o nome do arquivo/diretório de destino.
```bash
$ cp file.txt file_copy.txt
```
O comando acima faz uma cópia do arquivo *file.txt* para o arquivo *file_copy.txt*

```bash
$ cp -r workspace/ workspace-bkp/
```
O comando acima faz uma cópia do diretório *workspace/* para o diretório *workspace-bkp/*

## mv
O comando **mv**, move os arquivos informados como parâmetro de linha de comando para o diretório de destino. Condicionalmente, o comando também renomeia o arquivo/diretório informado. Quando o primeiro parâmetro é um arquivo, e o destino é uma pasta, o arquivo informado é movido para a pasta. Quando o primeiro parâmetro é um arquivo e o segundo parâmetro não é uma pasta encontrada no sistema de arquivos, o arquivo é renomeado. Quando o primeiro parâmetro é um diretório, e o segundo parâmetro também é um diretório, o diretório de origem vai ser movido para o de destino.
```bash
$ mv file.txt workspace/
```
O comando acima, move o arquivo *file.txt* para o diretório *workspace/*.

```bash
$ mv -r workspace/ bkp/
```
O comando acima, move o diretório *workspace/* para o diretório *bkp/*.

## zip
Com o comando **zip** é possível criar arquivos compactados no formato .zip.
```bash
$ zip -r work.zip workspace/
```
O comando acima, cria um arquivo compactado chamado *work.zip*, contendo todo o conteúdo do diretório *workspace/*, e para cada arquivo que deve ser processado, gera uma saída no console.

```bash
$ zip -qr work.zip workspace/
```
O comando acima, cria um arquivo compactado chamado *work.zip*, contendo todo o conteúdo do diretório *workspace/*, mas sem gerar saída no console.

## unzip
Com o comando **unzip** é possível visualizar, e extrair arquivos compactados no formato .zip.
```bash
$ unzip -l work.zip
```
O comando acima, lista os arquivos e diretórios contidos no arquivo *work.zip*.

```bash
$ unzip work.zip
```
O comando acima, extrai os arquivos e diretórios contidos no arquivo *work.zip*.

```bash
$ unzip -q work.zip
```
O comando acima, extrai os arquivos e diretórios contidos no arquivo *work.zip*, mas sem gerar saída no console.

## tar
O comando **tar** é semelhante ao comando **zip**, no entanto, o comando **zip** é mais utilizado em plataformas *Windows*. Para criar um arquivo compactado com o utilitário **tar**, use o seguite:
```bash
$ tar -cz workspace/ -f workspace.tar.gz
```
O comando acima gera um arquivo compactado no formato *tar.gz* a partir do diretório *workspace/*, tendo como resultado o arquivo *workspace.tar.gz*.

Vale lembrar que, por padrão, o comando **tar** já é recursivo.

Outra forma muito utilizada desse comando é com o redirecionamento da saída para um arquivo, ao invés de fornecer a flag *-f*.
```bash
$ tar -cz workspace/ > workspace.tar.gz
```

O comando **tar** também serve para fazer a extração de arquivos no formato *tar.gz*.
```bash
$ tar -xz < workspace.tar.gz
```
O comando acima, extrai o arquivo que foi fornecido a partir da entrada padrão do sistema.

Outra altenativas seria:
```bash
$ tar -xzf workspace.tar.gz
```
O comando acima recebe o parâmetro *-f* indicando que o próximo valor informado é o arquivo que deve ser extraído.

Por padrão o comando **tar** é silencioso, portanto, para alterar o nível de logging do comando, utiliza-se o parâmetro *-v*. Segue exemplo:
```bash
$ tar -vxzf workspace.tar.gz
```
O comando acima recebe o parâmetro *-v* indicando que deve gerar um log avisando sobre qual arquivo está sendo processado no momento.

Para utilizar a compactação no formato *.bzip2* simplesmente altere o parâmetro *-z*, por *-j*, no comando de compactação utilizando o utilitário **tar**.
```bash
$ tar -cjf workspace.tar.bz2 workspace/
```
Compacta o diretório *workspace* de forma recursiva utilizando gerando o arquivo *workspace.tar.bz2*.

## touch
O comando **touch** serve para alterar a data da última modificação no arquivo fornecido em linha de comando, por exemplo, para o momento atual.
```bash
$ touch arquivo.txt
```
É possível visualizar a alteração na data, utilizando o comando **ls**.

## date
Com o comando **date** serve para visualizar ou alterar a data atual do sistema.
```bash
$ date
```
Para visualizar a data em um formato diferente, é possível formatar a data. Segue exemplo:
```bash
$ date "+%d/%m/%Y"
```
Mostra a data no formato *dia/mes/ano*.

## head
Com o comando **head** lê um arquivo a partir do começo do arquivo, mas com uma leitura limitada a *10 linhas*, por padrão.
```bash
$ head arquivo.txt
```
Lê as 10 primeiras linhas do arquivo.

```bash
$ head -n 30 arquivo.txt
```
Lê as 30 primeiras linhas do *arquivo.txt*. O parâmetro *-n* é utilizado para indicar a quantidade de linhas a serem lidas.

## tail
O comando **tail** lê um arquivo a partir do começo do final, mas com uma leitura limitada a *10 linhas*, por padrão.
```bash
$ tail arquivo.txt
```
Lê as 10 últimas linhas do arquivo.

```bash
$ tail -n 30 arquivo.txt
```
Lê as 30 últimas linhas do *arquivo.txt*. O parâmetro *-n* é utilizado para indicar a quantidade de linhas a serem lidas.

## less
O comando **less** serve para navegar no arquivo, lendo o arquivo no terminal, utilizando as setas para ir para o início do arquivo e para o final do arquivo.
```bash
$ less arquivo.txt
```
Abre o arquivo e permite interação com o usuário utilizando as setas do teclado para navegar no *arquivo.txt*.
