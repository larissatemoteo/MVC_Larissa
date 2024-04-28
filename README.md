# MVC - Larissa Temoteo

## 1. Nome do Projeto: Abandono zero

**1.1 Descrição:** O propósito do projeto é criar um site responsivo, adaptável a dispositivos móveis e desktops, para o INSPA (Instituto de Saúde e Psicologia Animal). O site atuará como um formulário destinado a coletar informações sobre os cuidadores de cães, visando utilizá-las em futuras investigações sobre saúde animal. Para alcançar esse objetivo, o site será conectado a um banco de dados, permitindo a coleta e o armazenamento dos dados dos usuários, bem como o registro de suas respostas. Ao final do processo, os pesquisadores terão acesso a um relatório abrangente contendo estatísticas e as respostas dos formulários, simplificando a análise e interpretação dos dados obtidos.

**1.2 Arquitetura:** MVC (Model-View-Controller)

**1.3 Ferramenta de Diagramação:** draw.io

## 2. Modelos (Models):

**2.1 Cadastro**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;O Cadastro é responsável pela interação entre o tutor com o site inicial. Inclui a lógica para armazenar os dados do usuário e é fundamental pois redirenciona para as outras arquiteturas.
1. **Entidade Tutor**: Armazena os dados do usuário.
* Id: Guardar o identificador único de cada usuário
* Nome: Guardar o nome do usuário.
* Email: Guardar o email do usuário.
* Senha: Guardar a senha do usuário.
* Endereço: Guardar o endereço do usuário.


**2.2 Formulários**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A arquitetura de Formulários é centralizada na coleta e processamento de dados dos usuários por meio de formulários. Ela possui a lógica para listar, filtrar e armazenar informações. Essa estrutura é fundamental para a interação dos usuários com a aplicação.
1. **Entidade Formulário Geral**: Guarda as respostas do formulário geral. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 

 2. **Entidade Formulário Tem**: Guarda as respostas do formulário tem cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 

 3. **Entidade Formulário Teve**: Guarda as respostas do formulário teve cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 

 4. **Entidade Formulário Quer ter**: Guarda as respostas do formulário quer ter cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 


 5. **Entidade Formulário Nulo**: Guarda as respostas do formulário não quer ter cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 

**2.2 TelaAdmin**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A estrutura TelaAdmin é voltada para a administração da aplicação. Ela possui recursos para administrar os formulários, relatórios e análises. Essa estrutura é fundamental para a supervisão e controle do sistema, capacitando os administradores a visualizar as estatísticas das pesquisas.

1. **Entidade Usuários**:
* Id: Guardar o identificador único de cada administrador.
* Nome: Guardar o nome do administrador.
* Email: Guardar o email do administrador.
* Senha: Guardar a senha do administrador.

2. **Entidade Relatório**:
* Id: Guarda o identificador único de um relatório, por causa do filtrar.
* Dados: Guarda as informações gerais do relatório relacionado a estatísticas e dados.

3. **Entidade Formulário Geral**: Armazena as respostas do formulário geral. 
 * Id: Armazena o identificador de cada formulário.
 * Respondeu: Registra se o usuário respondeu à pergunta ou a ignorou.

 4. **Entidade Formulário Tem**: Armazena as respostas do formulário tem cachorro. 
 * Id: Armazena o identificador de cada formulário.
 * Respondeu: Registra se o usuário respondeu à pergunta ou a ignorou.

 5. **Entidade Formulário Teve**: Armazena as respostas do formulário teve cachorro. 
  * Id: Armazena o identificador de cada formulário.
 * Respondeu: Registra se o usuário respondeu à pergunta ou a ignorou.

 6. **Entidade Formulário Quer ter**: Armazena as respostas do formulário quer ter cachorro. 
 * Id: Armazena o identificador de cada formulário.
 * Respondeu: Registra se o usuário respondeu à pergunta ou a ignorou.

 7. **Entidade Formulário Nulo**: Armazena as respostas do formulário não quer ter cachorro. 
 * Id: Guarda o id de cada formulário.
 * Id: Armazena o identificador de cada formulário.
 * Respondeu: Registra se o usuário respondeu à pergunta ou a ignorou.


## 3. Controladores (Controllers):

**3.1 Cadastro**

* Responsabilidades: Supervisionar as operações de negócios associadas aos tutores, como criar, atualizar, listar e pesquisar tutores.

* Métodos:
    * Criar: Criar um novo registro de tutor no sistema
        * Entrada: Dados do novo tutor.
        * Saída: Objeto Tutor criado ou mensagem de erro.
    * Listar: Retorna uma lista de todos os tutores.
        * Entrada: Nenhuma.
        * Saída: Lista de objetos Tutor.
    * Filtrar: Filtra os tutores com base em critérios específicos, como idade, etc.
        * Entrada: Critérios de filtro.
        * Saída: Lista de objetos Tutor que atendem aos critérios especificados.
    * Atualizar: Busca um tutor específico por nome.
        * Entrada: Nome do tutor.
        * Saída: Objeto Tutor ou mensagem de erro.
    * Pesquisar: Busca um tutor específico por nome
        * Entrada: Nome do tutor.
        * Saída: Objeto Tutor ou mensagem de erro.

**3.2 Formulários**

* Responsabilidades: Gerenciar a interação dos usuários com os formulários, o que inclui a validação e o envio de dados.

* Métodos:
    * Listar: Retorna uma lista de todos os formulários disponíveis.
        * Entrada: Nenhuma.
        * Saída: Lista de objetos Formulário.
    * Filtrar: Filtra as respostas com base em critérios específicos.
        * Entrada: Critérios de filtro.
        * Saída: Lista de filtrados
    * Gravar: Registra um novo formulário no sistema.
        * Entrada: Dados do novo formulário.
        * Saída: Formulário gravado ou mensagem de erro.


**3.3 TelaAdmin**

* Responsabilidades: Supervisionar as operações de negócios relacionadas à administração do sistema, abrangendo a gestão de usuários e o acesso aos painéis de controle.

* Métodos:
    * Admin: Exibe uma lista de todos os usuários administradores.
        * Entrada: Nenhuma.
        * Saída: Lista de objetos Usuário Admin.
    * Dashboard:  Apresenta um painel de controle com informações resumidas do sistema.
        * Entrada: Nenhuma.
        * Saída: Objeto Dashboard.


## 4. Views:

### 4.1 Cadastro

As Views no Sails.js, são integrantes essenciais do padrão MVC (Model-View-Controller) e desempenham o papel de exibir dados ao usuário e moldar a interface com base no modelo de dados. Abaixo segue uma análise das views citadas na imagem:

**4.1.1 Home**

* Navbar: Barra de navegação que fica no topo da tela para facilitar o acesso a diferentes partes do site.

* Carousel: Um carrossel de imagens para destacar conteúdos ou promoções importantes.

* Botão de login: Uma área para que os usuários sejam redirecionados para a área de cadastro.

**4.1.2 Cadastro**

* Navbar: Barra de navegação que fica no topo da tela para facilitar o acesso a diferentes partes do site.

* Quadro de cadastro: Parte da tela em que o usuário irá inserir seus dados.

* Botão de envio: Botão para enviar os dados e finalizar o cadastro.

**4.1.3 Finalizado**

* Navbar: Barra de navegação que fica no topo da tela para facilitar o acesso a diferentes partes do site.

* Imagem: Imagem de verificação informando que cadastro foi respondido.

* Texto: Informção de que o cadastro foi finalizado.


### 4.2 Formulários

**4.2.1 Formulário Geral**

* Navbar: Funciona como um menu de navegação para simplificar o acesso a diversas áreas do site..

* Perguntas: Seção que contém todas as perguntas exibidas na tela.

* Respostas: Local designado para fornecer as respostas às perguntas do questionário.

* Botão enviar: Enviar e mandar as respostas para o model.

**4.2.2 Formulário Tem Cachorro**

* Navbar: Funciona como um menu de navegação para simplificar o acesso a diversas áreas do site..

* Perguntas: Seção que contém todas as perguntas exibidas na tela.

* Respostas: Local designado para fornecer as respostas às perguntas do questionário.

* Botão enviar: Enviar e mandar as respostas para o model.

**4.2.3 Formulário Quer ter cachorro**

* Navbar: Funciona como um menu de navegação para simplificar o acesso a diversas áreas do site..

* Perguntas: Seção que contém todas as perguntas exibidas na tela.

* Respostas: Local designado para fornecer as respostas às perguntas do questionário.

* Botão enviar: Enviar e mandar as respostas para o model.

**4.2.4 Formulário Teve cachorro**

* Navbar: Funciona como um menu de navegação para simplificar o acesso a diversas áreas do site..

* Perguntas: Seção que contém todas as perguntas exibidas na tela.

* Respostas: Local designado para fornecer as respostas às perguntas do questionário.

* Botão enviar: Enviar e mandar as respostas para o model.

**4.2.5 Formulário Nulo**

* Navbar: Funciona como um menu de navegação para simplificar o acesso a diversas áreas do site.

* Perguntas: Seção que contém todas as perguntas exibidas na tela.

* Respostas: Local designado para fornecer as respostas às perguntas do questionário.

* Botão enviar: Enviar e mandar as respostas para o model.

**4.2.6 Finalizado**

* Navbar: Funciona como um menu de navegação para simplificar o acesso a diversas áreas do site.

* Imagem: Quando o usuário finalizar todas as perguntas, uma imagem informando que formulário foi respondido aparecerá na tela.

* Texto: Texto informando que o formulário já foi respondido.

* Botão: Botão para finalizar, sair do site ou voltar a Home principal.

### 4.3 TelaAdmin

**4.3.1 Relatório**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Dados_Tutores: Seção em que as informações acerca dos usuários serão exibidas.

* Dados_Cachorros: Seção em que as informações acerca dos cachorros serão exibidas, tais como raça, idade, sexo, etc.

* Gráfico: Exibe os dados da pesquisa em formato de gráfico.

* Dropbox: Caixa de seleção suspensa em formulários ou interfaces de usuário, onde os usuários podem selecionar uma opção a partir de uma lista suspensa de opções disponíveis.

* Estatística: Mostra uma caixa de texto as informações da seção dropbox.

* Botão baixar: Permite baixar os filtros de uma resposta específica ou o formulário completo em formato de arquivo CSV.

## 5. Infraestrutura:
### 5.1 Banco de Dados:
Todas as informações reunidas nos formulários, desde os dados dos usuários até as respostas e relatórios, são armazenadas no banco de dados. Optamos pelo PostgreSQL devido à sua robustez e suporte a transações, fundamentais para a segurança dos dados, considerando critérios como escalabilidade, desempenho e usabilidade.

Os Modelos na arquitetura MVC conectam-se ao banco de dados para executar operações CRUD(Create, Read, Update, Delete). Eles definem a estrutura dos dados, aplicam regras de negócio e controlam o acesso aos dados armazenados, representando as entidades do sistema.

### 5.2 APIs Externas:
A incorporação de APIs externas é essencial para melhorar a funcionalidade e a experiência do usuário no projeto. Dentro da arquitetura MVC, os Controladores desempenham um papel central ao integrar essas APIs. Eles recebem as solicitações do usuário, as processam e, se necessário, fazem chamadas às APIs externas para obter dados adicionais. Posteriormente, os Controladores atualizam os Modelos, refletindo essas mudanças nas Views.

## 6. Implicações da Arquitetura:

A aplicação da arquitetura MVC no Sails.js traz consigo uma estrutura organizada e transparente para o desenvolvimento do projeto, resultando em diversas implicações de grande importância:

* Escalabilidade:  A divisão de responsabilidades entre Model, View e Controller viabiliza que cada componente seja dimensionado de forma independente conforme as demandas do sistema..
* Manutenção: Simplifica a manutenção e atualização do sistema, já que as modificações em um componente não impactam diretamente os demais..
* Testabilidade: A separação do Model e a View facilita os testes em cada parte do sistema de forma isolada e eficiente.
* Segurança: Fortalece a segurança do sistema, protegendo a confidencialidade e integridade das informações dos usuários.

## 7. Recursos Adicionais:
### 7.1 Documentação do Sails.js: https://github.com/balderdashy/sails 
### 7.2 Tutorial do draw.io: https://m.youtube.com/watch?v=w3zm-wbmlpc 
### 7.3 Exemplos de diagramas MVC: https://www.lucidchart.com/pages/templates