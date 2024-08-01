# DESAFIO-BEEDOO
## Desafio : Analista de Qualidade de Software Júnior (Beedoo 2024)


### O DESAFIO:
#### [Descrição Completa do Desafio](https://complex-night-ddb.notion.site/Desafio-Analista-de-Qualidade-de-Software-J-nior-5cef7366f66b41e890aada4d3f47f36f)

### BEEDOO QA CHALENGE:
#### [Página do Módulo de Cadastro de Cursos](https://creative-sherbet-a51eac.netlify.app/)

### DOCUMENTAÇÃO:
#### [Planilha de Detalhamento e Documentação dos Testes](https://www.google.com.br/)

### RELATÓRIO:
#### [Problemas e Bugs Encontrados (+sugestões de melhorias)](https://www.google.com.br/)
  
## User Story : Cadastro e Listagem de Cursos (Beedoo QA Chalenge)
Os casos de teste a seguir foram desenvolvidos a partir do módulo de curso no Beedoo QA Chalenge utilizando a linguaguem **Gherkin**. Neste módulo a ser testado, ao menos em teoria, o usuário "Paulo" pode criar, excluir e listar os cursos. 



```
@cadastro-curso
FUNCIONALIDADE: Cadastro de um curso
  Como um usuário do Beedoo QA Chalenge
  "Paulo" quer cadastrar um novo curso
  Para que esse curso fique disponível na lista de cursos

CONTEXTO:
  DADO que "Paulo" está na página Listar Cursos
```

```
@cadastro-curso-BASE
CENÁRIO: Cadastro válido
  E ele acessa a página Cadastrar Curso
  E ele preenche o campo Nome do curso com um texto válido
  E ele preenche o campo Descrição do curso com um texto válido
  E ele preenche o campo Instrutor com um texto válido
  E ele preenche o campo Url da imagem com um link válido
  E ele preenche o campo Data de inicio com uma data válida
  E ele preenche o campo Data de fim com uma data válida
  E ele preenche o campo Número de vagas com um número válido
  E ele seleciona no campo de opções Tipo de curso Online
  E ele preenche o campo Link de inscrição com um link válido
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO ele deve ser redirecionado para a página Listar Cursos
  E uma mensagem de aviso de curso cadastrado deverá ser exibida
  E o curso deve ser cadastrado e aparecer na página  Listar de Cursos
```

```
@cadastro-curso-online-valido
CENÁRIO: Cadastro válido
  E ele acessa a página Cadastrar Curso
  E ele preenche o formulário com dados válidos
  E ele seleciona no campo de opções Tipo de curso Online
  E ele preenche o campo Link de inscrição com um link válido
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO ele deve ser redirecionado para a página Listar Cursos
  E uma mensagem de aviso de curso cadastrado deverá ser exibida
  E o curso deve ser cadastrado e aparecer na página  Listar de Cursos
```

 ```
@cadastro-curso-presencial-valido
CENÁRIO: Cadastro válido
  E ele acessa a página Cadastrar Curso
  E ele preenche o formulário com dados válidos
  E ele seleciona no campo de opções Tipo de curso Presencial
  E ele preenche o campo Endereço com um texto válido
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO ele deve ser redirecionado para a página Listar Cursos
  E uma mensagem de aviso de curso cadastrado deverá ser exibida
  E o curso deve ser cadastrado e aparecer na página  Listar de Cursos
```
