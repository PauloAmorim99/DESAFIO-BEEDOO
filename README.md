## DESAFIO-BEEDOO
### Desafio : Analista de Qualidade de Software Júnior (Beedoo 2024)

descrever oq é o desafio e porque eu estou participando dele.

#### O DESAFIO:
##### [Descrição Completa do Desafio](https://complex-night-ddb.notion.site/Desafio-Analista-de-Qualidade-de-Software-J-nior-5cef7366f66b41e890aada4d3f47f36f)

#### BEEDOO QA CHALLENGE:
##### [Página do Módulo de Cadastro de Cursos](https://creative-sherbet-a51eac.netlify.app/)

#### DOCUMENTAÇÃO:
##### [Planilha de Detalhamento e Documentação dos Testes](https://docs.google.com/spreadsheets/d/1AWwJzyA0ispSWnwgUwaSR9KUaRqrHIniWLfVfEPoPFA/edit?usp=sharing)

#### RELATÓRIO:
##### [Problemas e Bugs Encontrados (+sugestões de melhorias)](https://docs.google.com/document/d/1X_5GqcO1nqk6s_dMu2F1lu72Q273DV0ngrezRmOqNOE/edit?usp=sharing)
  
## User Story : Cadastro e Listagem de Cursos (Beedoo QA Challenge)

Os casos de teste a seguir foram desenvolvidos a partir do módulo de curso no Beedoo QA Challenge utilizando a linguaguem **Gherkin**. Neste módulo a ser testado, ao menos em teoria, o usuário "Paulo" pode criar, excluir e listar os cursos. 

Nesse momento, vamos dividir os casos de teste em duas etapas, pois serão analisadas **duas funcionalidades** do módulo, sendo a primeira os casos de teste relativos ao **Cadastro de Curso** :


```
@cadastro-curso

FUNCIONALIDADE: Cadastro de um curso
  Como um usuário do Beedoo QA Challenge
  "Paulo" quer cadastrar um novo curso
  Para que esse curso fique disponível na lista de cursos

CONTEXTO:
  DADO que "Paulo" está na página Listar Cursos
  E que "Paulo" tem poder de administrador
```

Nesse cenário, vamos considerar que o usuário preenche todo o formulário de cadastro com **informações válidas**, selecionando a opção **online** no tipo de curso:
```
@cadastro-curso-online-valido

CENÁRIO: Cadastro válido do curso online
  E ele acessa a página Cadastrar Curso
  E ele preenche o formulário com dados válidos
  E ele seleciona no campo de opções Tipo de curso Online
  E ele preenche o campo Link de inscrição com um link válido
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO ele deve ser redirecionado para a página Listar Cursos
  E uma mensagem de aviso de curso cadastrado deverá ser exibida
  E o curso deve ser cadastrado e aparecer na página  Listar de Cursos
```

Nesse outro cenário, vamos considerar que o usuário preenche todo o formulário de cadastro com **informações válidas**, selecionando a opção **presencial** no tipo de curso:
```
@cadastro-curso-presencial-valido

CENÁRIO: Cadastro válido do curso presencial
  E ele acessa a página Cadastrar Curso
  E ele preenche o formulário com dados válidos
  E ele seleciona no campo de opções Tipo de curso Presencial
  E ele preenche o campo Endereço com um texto válido
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO ele deve ser redirecionado para a página Listar Cursos
  E uma mensagem de aviso de curso cadastrado deverá ser exibida
  E o curso deve ser cadastrado e aparecer na página  Listar de Cursos
```

Nesse cenário, vamos considerar que o usuário preenche parte do formulário de cadastro e deixa algum ou alguns **campos sem preenchimento**:
```
@cadastro-curso-invalido-campo-vazio

CENÁRIO: Cadastro inválido por campo vazio
  E ele acessa a página Cadastrar Curso
  E ele preenche os campos com dados válidos 
  E ele deixa de preencher algum ou alguns dos campos 
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO uma mensagem de aviso de curso não cadastrado
  E uma mensagem de aviso indicando os campos não preenchidos deverá ser exibida
```

Nesse cenário, vamos considerar que o usuário preencheu o formulário com informações válidos, porém o campo **Url da imagem de capa** foi preenchido com uma informação **inválida** (ex.: um texto qualquer ou um link que não remeta a uma imagem):
```
@cadastro-curso-invalido-url-imagem

CENÁRIO: Cadastro válido por url da imagem inválida
  E ele acessa a página Cadastrar Curso
  E ele preenche os campos com dados válidos
  E ele preenche o campo Url da imagem de capa com um link inválido
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO uma mensagem de aviso de curso não cadastrado deverá ser exibida
  E uma mensagem de aviso indicando que o campo Url da imagem de capa não possui um link válido deverá ser exibida
```

Nesse cenário, vamos considerar que o usuário preencheu o formulário com informações válidas, porém os campos **Data de inicio** e/ou **Data de fim** foram preenchidos com informações **inválidas** (ex.: data de inicio posterior a data de fim; data de inicio ou fim anterior a data do cadastro):
```
@cadastro-curso-invalido-datas

CENÁRIO: Cadastro inválido por datas inválidas
  E ele acessa a página Cadastrar Curso
  E ele preenche os campos com dados válidos 
  E ele preenche os campos com datas inválidas 
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO uma mensagem de aviso de curso não cadastrado
  E uma mensagem de aviso indicando os campos de data de inicio ou/e data de fim não são válidos
```

Nesse cenário, vamos considerar que o usuário preencheu o formulário com informações válidas, porém o campo **Número de vagas** foi preenchido com uma informação **inválida** (ex.:número de vagas extremamente extenso e irreal; caracteres especiais e/ou letras):
```
@cadastro-curso-invalido-vagas

CENÁRIO: Cadastro inválido por vagas inválidas
  E ele acessa a página Cadastrar Curso
  E ele preenche os campos com dados válidos 
  E ele preenche o campo numeros de vagas com um numéro inválido
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO uma mensagem de aviso de curso não cadastrado
  E uma mensagem de aviso indicando que o campos de Numero de vagas não é válido
```

Nesse cenário, vamos considerar que o usuário preencheu o formulário com informações válidas, porém o campo **Link de inscrição** foi preenchido com uma informação **inválida** (ex.:um texto qualquer; um numero; uma frase; etc):
```
@cadastro-curso-invalido-online

CENÁRIO: Cadastro válido do curso online
  E ele acessa a página Cadastrar Curso
  E ele preenche o formulário com dados válidos
  E ele seleciona no campo de opções Tipo de curso Online
  E ele preenche o campo Link de inscrição com um link inválido
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO uma mensagem de aviso de curso não cadastrado
  E uma mensagem de aviso indicando que o campo Link de inscrição não é válido
```

Agora, vamos analisar a segunda funcionalidadedo módulo, sendo os casos de teste relativos a **Listar Cursos** :

```
@listar-cursos
FUNCIONALIDADE: Listagem de curso

  Como um usuário do Beedoo QA Challenge
  "Paulo" quer listar os cursos cadastrados
  Para que possa organizar, filtrar, visualisar e gerenciar esses cursos

CONTEXTO:
  DADO que "Paulo" está na página Listar Cursos
  E que "Paulo" tem poder de administrador
```

Nesse cenário, vamos considerar que o usuário está diante da página da lista de cursos cadastrados, e deseja **visualizar mais informações** a respeito dos cursos cadastrados que se aprensentam em card:
```
@listar-curso-visualisar-cadastrado

CENÁRIO: Visualizar curso cadastrado
  E ele acessa a página Listar Cursos
  E ele escolhe um dos cursos cadastrados
  QUANDO ele clica sobre o card do curso cadastrado
  ENTÃO ele deve ter um retorno na tela em pop-up contendo as informações completas cadastradas sobre esse curso
  E uma opção de edição é apresentada nesse retorno
  E uma opção de exclusão é apresentada nesse retorno
  E uma opção de suspenção é apresentada nesse retorno
  E uma opção para minimizar esse retorno ou retornar para a tela inicial é apresentada
```

Nesse cenário, vamos considerar que o usuário está diante da página da lista de cursos cadastrados, e deseja **excluir um curso cadastrada** a partir do card:
```
@listar-curso-excluir

CENÁRIO: Excluir curso cadastrado
  E ele acessa a página Listar Cursos
  E ele escolhe um dos cursos cadastrados
  QUANDO ele clica sobre o botão Excluir curso no card do curso cadastrado
  ENTÃO ele deve ter um retorno solicitando uma confirmação se a exclusão é mesmo desejada
  E caso confirme o curso deverá ser apagado da página
  E o usuário deve ser redirecionado para a página Lista de cursos atualizada
  E um retorno dando a opção de desfazer a exclusão deve ser exibido na tela por alguns segundos
```
