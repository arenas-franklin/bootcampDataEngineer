# Introdução  ao Git e ao GitHub

git - ferramenta de versionamento de código 

Benefício do git e Github

- Controle de versão 
- Armazenamento em nuvem
- Trabalho em equipe
- Melhorar seu código
- Reconhecimento

---

## Comandos básicos para  um bom desempenho  no terminal

A forma de interação do git é por linha de comando 

| o que faz                | Windows   | Unix   |
| ------------------------ | --------- | ------ |
| mudar de pasta           | cd        | cd     |
| Listar as pastas         | dir       | ls     |
| Criar pasta/arquivos     | mkdir     | mkdir  |
| Deletar pastas/ arquivos | del/rmdir | rm -rf |





## Entendendo como o GIT funciona por baixo dos panos

### -  SHA1

A sigla SHA significa Secure Hash Algorithm (Algoritmo de Hash Seguro), é um conjunto de funções hash criptográficas projetadas pela NSA (Agência de seGurança Nacional dos EUA).

A encriptação gera  conjunto de characteres identificador  de 40 digitos.

è uma forma curta de representar um arquivo.

```shell
echo "ola mundo" | openssl sha1
> (stdin) = f9fc85e559bb950175f2b7cd7dad61facbe58e7b
```



### - Objetos fundamentais

**BLOBS**

````shell
echo 'conteudo' | git hash-object --stdin
> fc31e91b26cf85a55e072476de7f263c89260eb1

echo -e 'conteudo' | openssl sha1
> 65b0d0dda479cc03cce59528e28961e498155f5c
````

Blob são objetos que guarda meta-dados do git, tipo do objeto, tamanho da string, tamanho do arquivo etc... 

 **TREES**

A Trees armazenas blobs , ela aponta para um blob com sha1 e o nome do arquivo. as trees podem apontar para blobs e outras trees e cada trees possui um sha1 registrado

```shell
Tree
\0
blob 	sa4d8s		text.txt
```

a  *árvore* , que resolve o problema de armazenamento do nome do arquivo e também permite armazenar um grupo de arquivos juntos. Git armazena conteúdo de maneira semelhante a um sistema de arquivos UNIX, mas um pouco simplificado. Todo o conteúdo é armazenado como árvore e objetos de blob, com árvores correspondendo a entradas de diretório UNIX e blobs correspondendo mais ou menos a inodes ou conteúdo de arquivo. Um único objeto de árvore contém uma ou mais entradas, cada uma das quais é o hash SHA-1 de um blob ou subárvore com seu modo, tipo e nome de arquivo associados

**COMMITS**

O objeto commit ele tem os valores das alterações das trees mais o nome do autor, mensagem e um sha1 do commit e um timestamp um carimbo de tempo informando o horário de criação do commit.

```
Commit
tree 		s4aa5sq1
parente 	a98acql
autor		parkies
mensagem 	"inicia ..."
timestamp
```



### - Sistema distribuído e Segurança

​	A git perpetua uma distribuição o código no servidor com os seus desenvolvedor ele permite manter um código atualizado entre todas as partes, ou seja, por uma circunstância houver uma perda do código do servidor existe uma cópia atualizada em outras máquinas.



## Iniciando o Git  e criando um commit

---

### - inicar o GIT

- git init

  ````shell
  git init
  ````

  

### - Iniciar o versionamento 

- git add

  adiciona todas as alterações 

  ````shell
  git add .
  ````

  ou adiciona arquivo especifico

  ```shell
  git add nome_do_arquivo
  ```

  

### - Criar um commit

- git commit 

  ````
  git commit -m "descrição da alteração"
  ````















