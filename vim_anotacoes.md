
# **Configuração padrão**
Dependendo do pacote vim que é instalado, existe um arquivo ~/.vimrc onde são as configurações que o vim carrega antes de inicializar. Exemplo:
```shell
$ cat ~/.vimrc
syntax on
set number
```

# **Comandos**

* **Inserção e edição:**

`i (Insert)`: Entra no modo de inserção

`I`: Entra no modo de inserção na primeira linha

`~` : [n]~

	muda o caso (aBc -> AbC) do caractere abaixo do cursor mais n caracteres seguintes

`x` : [n]x

	Apaga n-1 caracteres a esquerda de caractere onde o cursor estiver posicionado, este caractere inclusive.

`X` : [n]X

	Apaga n-1 caracteres a direita de caractere onde o cursor estiver posicionado, este caractere inclusive.

`s` : Apaga o caractere na posição do cursor e entra no modo cursor

`S` : Apaga a linha toda e entra no modo de inserção

`u` : Desfaz alterações

`ctrl+r` : Refaz alterações

* **Navegação e autolocalização(?):**

`[hjkl]` : Move o cursor, igual às setas do teclado

`r (Replace)` : [n]rc

	O comando r substitui n caracteres abaix o do cursor pelo caractere c.

`w` : move o cursor uma palavra da esquerda pra direita

`b` : move o cursor uma palavra da esquerda pra direita

`H (high)` : move o cursor para o começo da tela

`L (low)` : move o cursor para o final da tela

`G` : [n]G

	Move o cursor para a linha n do arquivo, ou para o final, caso o n não for dado.

`0 ou <home>` : coloca o cursor pro inicio da linha

`$ ou <end>` : coloca o cursor pro inicio da linha

`^` : movimenta o cursor para o primeiro caracter não-espaço ou não-tab

`ctrl+d (down)` : movimenta meia tela para baixo

`ctrl+u (up)` : movimenta meita tela para cima

`ctrl+g` : mostra a linha atual, a porcentagem e algumas informações sobre o arquivo

`set number` : mostra as linhas

`set nonumber` : desmostra as linhas AUHEUEAH

* **Copiar, colar e recortar**

`y (yank)`: y[n][c][y]

	`yn` copia a linha atual e mais n linhas para baixo;
	`yc` onde c é um comando de movimentação, e irá copiar de acordo com o comando. Por exemplo, "yw" irá copiar a palavra seguinte
	`yy ou Y` copia a linha atual inteira

`p (paste)`: Cola o que foi copiado após a posição atual do cursor

`P (paste)`: Cola o que foi copiado antes da posição atual do cursor

`dd` : [n]dd ou dd[c]

	Recorna n linhas do texto; Ou recorta de acordo com o comando c

`D` : Recorta a linha apartir da posição do cursor até o final

`cc` : Recorta a linha e entra no modo de inserção

* **VI geral**

`:w (write)` : salva

`:q` : sair

`:q!` : força saída

`:wq` : salva e sai

`:x ou ZZ` : salva e sai

`:help` help [ comando ]

	Ajuda padrão do vi. Ao dar um comando como argumento (ex.: :help u), ele traz a ajuda do comando especificado.

	:q sai da ajuda

	Há um comando de tutorial do vim: vimtutor


* **Opções do set**

*:set*

`autowrite`      aw    salva a cada alteração

`backspace`      bs    comportamento backspace(1 ou 2) 

`errorbell`      eb    campainha de erro

`expandtab`      et    troca tab por espacos

`fileformat=dos` ff    converte o arquivo para DOS

`hidden`         hid   preserva buffer

`hlsearch`       hls   ilumina a última procura

`ignorecase`     ic    case insensitive na busca

`incsearch`      is    ilumina procura enquanto digita

`laststatus=2`         mostra linha de estado

`lazyredraw`     lz    não redesenha em macros

`lines=N`              número de linhas na tela

`magic`                usar mágicas na procura de padrões

`number`         nu    mostra núm da linha

`report=N`             mostra aviso quando N linhas mudaram (0=sempre)

`showcmd`              mostra o comando que se está fazendo

`showmatch`      sm    mostra o casamento de {},[],()

`smartcase`      scs   assume "noic" quando tiver maiúsculas

`textwidth=N`          quebra de linha do texto

`undolevels`     ul=N  guarde os N últimos comandos p/desfazer (padrão=1000)

`vbt_vb=`             retira o "beep" de erro

* **Caracteres Especiais**

`:digraphs` : Mostra todos os caracteres especiais disponíveis

	Para inserir um caractere especial, deve-se entrar no modo de inserção e pressionar ctrl+k e o código do caractere.

* **Workflow Example**


1. :cd into the toplevel directory of my project.

2. To open file foo/bar/baz:

* Simplest scenario: type :e f<tab>b<tab>b<tab><enter>.

* If there are more than one file starting with b in one of those directories you might have to do a <left> or <right> or another <tab> on the keyboard to jump between them (or type a few more letters to disambiguate).

* Worst-case scenario there are files and directories that share a name and you need to drill down into the directory. In this case tab-complete the directory name and then type *<tab> to drill down.

3. Open 2 or 3 windows and open files in all of them as needed.

4. Once a file is open in a buffer, don't kill the buffer. Leave it open in the background when you open new files. Just :e a new file in the same window.

5. Then, use :b <tab> to cycle through buffers that are already open in the background. If you type :b foo<tab> it will match only against currently-open files that match foo.


