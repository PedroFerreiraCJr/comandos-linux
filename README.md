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
