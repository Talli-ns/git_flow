# Branches do Git Flow
 O Git Flow � um framework que possui diretrizes para a organiza��o das branches, estabelecendo padr�es de nomes e fun��es para cada tipo de branch, sendo elas:

## Master
Contem o nosso c�digo final, ou seja, todos os fontes que foram entregues aos clientes.
Toda entrega ao cliente dever� estar nessa branch.

## Develop 
Contem o c�digo das features que foram desenvolvidas e **testadas**. Conforme as features v�o sendo finalizadas elas v�o sendo adicionadas nessa branch.

## Feature
S�o branches para o desenvolvimento de uma nova funcionalidade, por conven��o elas tem o nome iniciado por feature/, por exemplo: feature/cadastro_usuarios. Importante ressaltar que ssas branches **s�o criadas sempre a partir da branch develop**.

## Hotfix
S�o branches utilizadas para realiza��o de alguma corre��o cr�tica encontrada em produ��o e por isso essas brances **s�o criadas a partir da master**. Ao final da corre��o, o hotfix deve ser juntado tanto com a master quanto com a develop.

## Release
Tem uma confian�a maior que a branch develop e que se encontra em n�vel de prepara��o para ser adicionada a master e a develop (caso alguma coisa tenha sido modificada na branch em quest�o).


# Iniciando o Git Flow
Dentro do reposit�rio, j� no terminal de comando, utilize os comandos:    
<br>**`git pull`** Para atualizar os seus arquivos com base nos arquivos que est�o no repositorio do git.
<br>**`git status`** Para verificar o status dos seus arquivos e ver em qual branch est� posicionado.
<br>**`git checkout [nome da branch]`** Caso queira mudar para outra branch.
<br>**`git flow init`** Para iniciar o Git Flow.

Algumas perguntas referentes a nomenclatura ser�o feitas, recomendo apenas apertar _ENTER_, vamos trabalhar com o padr�o sugerido.

# Utilizando a Feature
Ap�s iniciar o git flow dentro do reposit�, posicionado na **branch develop**, no terminal de comando utilize os comandos: 
<br><br>**`git flow feature start [descri��o da tarefa]`**  Por padr�o o nome da feature ser� uma breve descri��o da tarefa.

* Exemplos de nomes de features: **inclusao_cadastro**, **atualizacao_layout**, etc.

Realize todo o desenvolvimento necess�rio e na sequncia os comandos para finaliza��o:
<br><br>**`git add [arquivo alterado]`** Preparando o arquivo para subir no reposit�rio do git.
<br>**`git commit -m ["comentario"]`** Cria o coment�rio para o arquivo adicionado.
<br>**`git push --set-upstream origin feature`** Faz o link entre o seu arquivo local e o arquivo que esta no git.
<br>**`git flow feature finish [descri��o da tarefa]`** Sua feature � finalizada.
<br>**`git push origin develop`** Sobe a sua feature para a branche develop.

# Utilizando a Hotfix
Ap�s iniciar o git flow dentro do reposit�rio, posicionado na **branch master**, no terminal de comando utilize os comandos: 
<br><br>**`git flow hotfix start [descri��o da corre��o]`** Por pad�o a feature levar� a descri��o da corre��o.

* Exemplos de descri��o da corre��o: **correcao_cadastro** ou  **correcao_envio_email**.

Realize todo o desenvolvimento necess�rio e na sequencia os comandos para finaliza��o:

**`git add [o arquivo alterado]`** Preparando o arquivo para subir no reposit�rio do git.
<br>**`git commit -m ["comentario"]`** Cria o coment�rio para o arquivo adicionado.
<br>**`git push `** Sobe a sua hotfix para o git.
<br>**`git flow hotfix finish [descri��o da tarefa]`** Sua hotfix � finalizada.
<br>**`git push origin master develop`** Sobe a sua hotfix para as branches master e develop

# Utilizando a Release
Ap�s iniciar o git flow dentro do reposit�rio, no terminal de comando utilize os comandos: 
<br><br>**`git flow release start [vers�o]`** Por padr�o a 1.0.0 ser� a primeira vers�o utilizada.

Em alguns cen�rios, ap�s efetuar testes na release algumas mudan�as podem ocorrer. Por esse motivo, ao finalizar a release ela � mesclada tanto com a master quanto com a develop.

Para finalizar a release utilizamos o comando:
<br><br>**`git flow release finish [vers�o]`**
 
O Git Flow abre o editor de texto para que possamos editar a  descri��o da tag que ser� criada (campo obrigat�rio). Utilizaremos o n�mero da vers�o como tag na f�brica.

Para incluir esta informa��o, assim que o editor de textos for aberto utilize os comandos:
<br><br>**`i`** Para habilitar o teclado.
<br>**`[vers�o da tag]`** 1.0.0 para a primeira vers�o, por exemplo.
<br>**`esc`** Para desabilitar o teclado.
<br>**`:`**+**`w`**+**`q`** Para salvar a informa��o digitada.

Neste momento sua Release estar� pronta para subir para a Develop e a Master utilize o comando:
<br><br>**`git push origin master develop [vers�o da tag]`** Sobe a sua release para as branches master e develop.

<br></br>
**Link para download do Git Flow**
<br><https://git-scm.com/download/win>

**Indica��o de extens�o para visualiza��o das branches no VScode**
<br>Git Graph
