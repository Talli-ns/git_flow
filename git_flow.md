# Branches do Git Flow
 O Git Flow é um framework que possui diretrizes para a organização das branches, estabelecendo padrões de nomes e funções para cada tipo de branch, sendo elas:

## Master
Contem o nosso código final, ou seja, todos os fontes que foram entregues aos clientes.
Toda entrega ao cliente deverá estar nessa branch.

## Develop 
Contem o código das features que foram desenvolvidas e **testadas**. Conforme as features vão sendo finalizadas elas vão sendo adicionadas nessa branch.

## Feature
São branches para o desenvolvimento de uma nova funcionalidade, por convenção elas tem o nome iniciado por feature/, por exemplo: feature/cadastro_usuarios. Importante ressaltar que ssas branches **são criadas sempre a partir da branch develop**.

## Hotfix
São branches utilizadas para realização de alguma correção crítica encontrada em produção e por isso essas brances **são criadas a partir da master**. Ao final da correção, o hotfix deve ser juntado tanto com a master quanto com a develop.

## Release
Tem uma confiança maior que a branch develop e que se encontra em nível de preparação para ser adicionada a master e a develop (caso alguma coisa tenha sido modificada na branch em questão).


# Iniciando o Git Flow
Dentro do repositório, já no terminal de comando, utilize os comandos:    
<br>**`git pull`** Para atualizar os seus arquivos com base nos arquivos que estão no repositorio do git.
<br>**`git status`** Para verificar o status dos seus arquivos e ver em qual branch está posicionado.
<br>**`git checkout [nome da branch]`** Caso queira mudar para outra branch.
<br>**`git flow init`** Para iniciar o Git Flow.

Algumas perguntas referentes a nomenclatura serão feitas, recomendo apenas apertar _ENTER_, vamos trabalhar com o padrão sugerido.

# Utilizando a Feature
Após iniciar o git flow dentro do repositó, posicionado na **branch develop**, no terminal de comando utilize os comandos: 
<br><br>**`git flow feature start [descrição da tarefa]`**  Por padrão o nome da feature será uma breve descrição da tarefa.

* Exemplos de nomes de features: **inclusao_cadastro**, **atualizacao_layout**, etc.

Realize todo o desenvolvimento necessário e na sequncia os comandos para finalização:
<br><br>**`git add [arquivo alterado]`** Preparando o arquivo para subir no repositório do git.
<br>**`git commit -m ["comentario"]`** Cria o comentário para o arquivo adicionado.
<br>**`git push --set-upstream origin feature`** Faz o link entre o seu arquivo local e o arquivo que esta no git.
<br>**`git flow feature finish [descrição da tarefa]`** Sua feature é finalizada.
<br>**`git push origin develop`** Sobe a sua feature para a branche develop.

# Utilizando a Hotfix
Após iniciar o git flow dentro do repositório, posicionado na **branch master**, no terminal de comando utilize os comandos: 
<br><br>**`git flow hotfix start [descrição da correção]`** Por padão a feature levará a descrição da correção.

* Exemplos de descrição da correção: **correcao_cadastro** ou  **correcao_envio_email**.

Realize todo o desenvolvimento necessário e na sequencia os comandos para finalização:

**`git add [o arquivo alterado]`** Preparando o arquivo para subir no repositório do git.
<br>**`git commit -m ["comentario"]`** Cria o comentário para o arquivo adicionado.
<br>**`git push `** Sobe a sua hotfix para o git.
<br>**`git flow hotfix finish [descrição da tarefa]`** Sua hotfix é finalizada.
<br>**`git push origin master develop`** Sobe a sua hotfix para as branches master e develop

# Utilizando a Release
Após iniciar o git flow dentro do repositório, no terminal de comando utilize os comandos: 
<br><br>**`git flow release start [versão]`** Por padrão a 1.0.0 será a primeira versão utilizada.

Em alguns cenários, após efetuar testes na release algumas mudanças podem ocorrer. Por esse motivo, ao finalizar a release ela é mesclada tanto com a master quanto com a develop.

Para finalizar a release utilizamos o comando:
<br><br>**`git flow release finish [versão]`**
 
O Git Flow abre o editor de texto para que possamos editar a  descrição da tag que será criada (campo obrigatório). Utilizaremos o número da versão como tag na fábrica.

Para incluir esta informação, assim que o editor de textos for aberto utilize os comandos:
<br><br>**`i`** Para habilitar o teclado.
<br>**`[versão da tag]`** 1.0.0 para a primeira versão, por exemplo.
<br>**`esc`** Para desabilitar o teclado.
<br>**`:`**+**`w`**+**`q`** Para salvar a informação digitada.

Neste momento sua Release estará pronta para subir para a Develop e a Master utilize o comando:
<br><br>**`git push origin master develop [versão da tag]`** Sobe a sua release para as branches master e develop.

<br></br>
**Link para download do Git Flow**
<br><https://git-scm.com/download/win>

**Indicação de extensão para visualização das branches no VScode**
<br>Git Graph
