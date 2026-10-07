dir
    # Meu Projeto GitHub

Este arquivo é o README do meu projeto.
# Sessão 1: O Passo a Passo da Criação e Envio

Para colocar um projeto no GitHub, primeiro preciso criar um repositório na plataforma e depois conectar esse repositório com uma pasta do projeto que está no meu computador. Depois dessa conexão, consigo registrar as alterações usando o Git e enviar os arquivos para o GitHub.

Durante esse processo, também percebi que é importante prestar atenção em **qual pasta estou utilizando no terminal**, porque o Git acompanha os arquivos a partir do local onde o repositório foi inicializado.

## 1. O início: criando o repositório no GitHub

Primeiro, acesso o GitHub e faço login na minha conta. Na página inicial, escolho a opção para **criar um novo repositório**.

Ao criar o repositório, preciso definir algumas informações:

* **Nome do repositório:** identifica o meu projeto.
* **Descrição:** posso colocar uma explicação resumida sobre o objetivo do projeto.
* **Visibilidade:** posso escolher se o repositório será **público** ou **privado**.
* **README:** posso criar um README diretamente no GitHub, mas, quando estou trabalhando com uma pasta que já existe no computador, é possível deixar o repositório vazio e criar o README localmente.

Depois dessas configurações, clico em **Create repository**. Nesse momento, tenho um repositório criado no GitHub, mas ainda preciso enviar os arquivos que estão no meu computador.

## 2. A conexão: preparando a pasta local

Depois de criar o repositório, preciso ter uma pasta específica para o projeto no computador.

No meu caso, criei uma pasta chamada:

```text
Atividade0710
```

Depois abri essa pasta no **VS Code** e criei dentro dela o arquivo:

```text
README.md
```

Coloquei inicialmente um conteúdo simples no arquivo para ter um arquivo real para testar o funcionamento do Git.

### Um cuidado importante com a pasta

Durante meu teste, percebi uma coisa importante: inicialmente executei o `git init` em uma pasta muito acima da pasta do projeto. Com isso, o Git passou a identificar várias pastas pessoais do computador, como `Desktop`, `Documents`, `Downloads`, `Pictures` e outras.

Por isso, **não devo executar `git add .` nessa situação**, porque poderia adicionar muitos arquivos que não fazem parte do projeto.

A solução foi entrar na pasta correta usando o terminal. Utilizei comandos como:

```bash
cd
```

para navegar entre as pastas e:

```bash
dir
```

para verificar o conteúdo da pasta atual.

Depois de chegar na pasta correta do projeto, pude inicializar o Git nela.

## 3. Inicializando o Git

Dentro da pasta do projeto, utilizo:

```bash
git init
```

Esse comando transforma aquela pasta em um repositório Git local. A partir desse momento, o Git consegue acompanhar os arquivos e alterações existentes dentro daquele projeto.

Depois posso verificar a situação do repositório utilizando:

```bash
git status
```

Esse comando foi importante para eu entender o que estava acontecendo. Quando o `README.md` ainda não tinha sido adicionado ao Git, ele apareceu como um arquivo **untracked**, ou seja, um arquivo que existe na pasta, mas que ainda não está sendo acompanhado pelo Git.

## 4. Adicionando os arquivos

Depois de confirmar que estava na pasta correta e que o `README.md` era o arquivo que eu queria enviar, utilizei:

```bash
git add .
```

O ponto (`.`) significa que estou adicionando as alterações encontradas na pasta atual.

Depois utilizei novamente:

```bash
git status
```

Nesse momento, o Git mostrou:

```text
Changes to be committed:
    new file: README.md
```

Isso significa que o arquivo estava preparado para fazer o *commit*.

## 5. Criando o primeiro commit

Com o arquivo preparado, fiz o primeiro registro das alterações usando:

```bash
git commit -m "Primeiro commit"
```

O `commit` funciona como um registro ou uma fotografia do estado do projeto naquele momento.

A opção `-m` permite escrever uma mensagem explicando o que foi registrado. Nesse caso, utilizei:

```text
"Primeiro commit"
```

Depois disso, o Git confirmou que o arquivo havia sido registrado.

Durante esse processo também apareceu uma mensagem relacionada à configuração de identidade do Git. Isso aconteceu porque o computador ainda não tinha algumas informações do usuário configuradas globalmente. Mesmo assim, o commit foi realizado corretamente.

## 6. Conectando o projeto ao GitHub

Depois de criar o commit localmente, precisei conectar o repositório do computador com o repositório que havia criado no GitHub.

Para isso, utilizei:

```bash
git remote add origin https://github.com/WeCode1Ds/Atividade-Documentando-o-Fluxo-de-Versionamento.git
```

Nesse comando, `origin` é o nome utilizado para identificar o repositório remoto principal.

Depois confirmei se a conexão estava correta utilizando:

```bash
git remote -v
```

O Git mostrou o endereço do repositório tanto para operações de `fetch` quanto de `push`. Isso confirmou que a pasta local estava conectada ao repositório correto no GitHub.

## 7. Definindo a branch principal

Antes de fazer o primeiro envio, utilizei:

```bash
git branch -M main
```

Esse comando define o nome da branch principal como `main`.

Uma *branch* pode ser entendida como uma linha de desenvolvimento do projeto. No meu caso, estou utilizando `main` como a principal.

## 8. O primeiro envio para o GitHub

Com o projeto conectado ao repositório remoto e o commit já criado, finalmente fiz o envio utilizando:

```bash
git push -u origin main
```

O comando `push` é responsável por enviar os commits que estão no computador para o repositório remoto no GitHub.

Durante esse processo, apareceu a mensagem:

```text
info: please complete authentication in your browser...
```

Isso significa que foi necessário realizar a autenticação da minha conta do GitHub pelo navegador.

Depois da autenticação, o terminal mostrou que a branch `main` havia sido enviada para o GitHub:

```text
[new branch] main -> main
```

Também apareceu:

```text
branch 'main' set up to track 'origin/main'
```

Isso significa que a branch `main` do meu computador ficou relacionada à branch `main` do repositório remoto.

Depois disso, pude atualizar a página do meu repositório no GitHub e verificar que o arquivo `README.md` estava disponível na nuvem.

## 9. Entendendo os comandos e as letras maiúsculas e minúsculas

Uma coisa que também percebi durante o processo é que é importante prestar atenção na forma como os comandos e nomes dos arquivos são escritos.

Por exemplo:

```bash
git add .
```

e:

```bash
git Add .
```

não devem ser tratados como a mesma coisa. Os comandos do Git são escritos seguindo uma sintaxe específica, normalmente utilizando **letras minúsculas**.

Também é importante prestar atenção aos nomes de arquivos e pastas. Por exemplo:

```text
README.md
```

não é a mesma escrita que:

```text
readme.md
```

Dependendo do sistema e da situação, diferenças entre letras maiúsculas e minúsculas podem causar problemas ou fazer referência a nomes diferentes. Por isso, durante o uso do Git, procuro escrever os comandos e nomes exatamente como foram definidos.

Também aprendi que as mensagens exibidas pelo terminal entre parênteses ou como explicações do Git **não são necessariamente comandos para serem digitados**. Por exemplo, quando o Git mostra uma mensagem explicando `git rm --cached`, aquilo é uma orientação do próprio programa e não significa que eu preciso executar aquele comando naquele momento.

## 10. Resumindo o primeiro envio

Depois da experiência prática, consegui entender o processo completo da seguinte maneira:

**Criar o repositório no GitHub → criar ou abrir a pasta do projeto → criar o README.md → inicializar o Git → verificar o status → adicionar os arquivos → criar o commit → conectar ao repositório remoto → definir a branch principal → fazer o push.**

Os principais comandos utilizados foram:

```bash
git init
git status
git add .
git commit -m "Primeiro commit"
git remote add origin URL_DO_REPOSITORIO
git remote -v
git branch -M main
git push -u origin main
```

Com isso, consegui pegar um arquivo que estava no meu computador, registrar sua primeira versão usando o Git e finalmente enviá-lo para o GitHub. Essa experiência também mostrou que é importante verificar a pasta em que estou trabalhando antes de executar os comandos, principalmente o `git add .`, para evitar adicionar arquivos que não pertencem ao projeto.
