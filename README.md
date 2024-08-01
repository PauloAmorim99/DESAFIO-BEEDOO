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

Nesse momento, vamos dividir os casos de teste em duas etapas, sendo a primeira os casos de teste relativos ao **Cadastro de Curso** :



```
@cadastro-curso
FUNCIONALIDADE: Cadastro de um curso
  Como um usuário do Beedoo QA Chalenge
  "Paulo" quer cadastrar um novo curso
  Para que esse curso fique disponível na lista de cursos

CONTEXTO:
  DADO que "Paulo" está na página Listar Cursos
```

descrição:
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

descrição:
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

descrição:
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

descrição:
```
@cadastro-curso-inválido-campo-vazio
CENÁRIO: Cadastro inválido por campo vazio
  E ele acessa a página Cadastrar Curso
  E ele preenche os campos com dados válidos 
  E ele deixa de preencher algum ou alguns dos campos 
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO uma mensagem de aviso de curso não cadastrado
  E uma mensagem de aviso indicando os campos não preenchidos deverá ser exibida
```

descrição:
```
@cadastro-curso-inválido-url-imagen
CENÁRIO: Cadastro válido por url da imagem inválida
  E ele acessa a página Cadastrar Curso
  E ele preenche os campos com dados válidos
  E ele preenche o campo Url da imagem de capa com um link inválido
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO uma mensagem de aviso de curso não cadastrado deverá ser exibida
  E uma mensagem de aviso indicando que o campo Url da imagem de capa não possui um link válido deverá ser exibida
```

descrição:
```
@cadastro-curso-inválido-datas
CENÁRIO: Cadastro inválido por datas inválidas
  E ele acessa a página Cadastrar Curso
  E ele preenche os campos com dados válidos 
  E ele preenche os campos com datas inválidas 
  QUANDO ele aciona o botão Cadastrar curso
  ENTÃO uma mensagem de aviso de curso não cadastrado
  E uma mensagem de aviso indicando os campos de data de inicio ou/e data de fim não são válidos
```

