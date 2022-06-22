<h1 align="center">API-Banco-Digital 💰</h1>

<p align="center">Nesta API encontrará as funções essenciais relacionadas ao gerenciamento de contas bancárias</p>

<p align="center">Navegue pelo sumário abaixo</p>
<p align="center">
 <a href="#inicio">Inicio</a> •
 <a href="#pré-requisitos">Pré Requisitos (Instalação)</a> •
 <a href="#como-executar-o-projeto">Como Executar o projeto</a> •
 <a href="#testar-no-swagger">Testar no Swagger</a> •
 <a href="#testar-no-postman">Testar no Postman</a> •
 <a href="#tecnologias">Tecnologias</a> •
 <a href="#autor">Autor</a>
</p>

---
- [x] O teste da API pode ser feito pelo Swagger ou Postman • Sugestão do autor: Swagger

### Inicio
#### 🚀 Regra de negócio

- [x] Para abrir uma conta é necessário apenas o nome completo e CPF da pessoa, mas só é permitido uma conta por pessoa
- [x] Com essa conta é possível realizar transferências para outras contas e depositar
- [x] Não aceitamos valores negativos nas contas
- [x] Por questão de segurança cada transação de depósito não pode ser maior do que R$2.000
- [x] Este Projeto foi Documentado com Swagger para facilitar os testes
 
### Pré-requisitos
#### 🔧 Instalação e configuração

⚠️ As ferramentas informadas aqui foram as que eu utilizei, fique a vontade para escolher a que for mais familiar a você.

Antes de começar, você vai precisar ter instalado em sua máquina as seguintes ferramentas:
- [IntelliJ IDEA Community Edition](https://www.jetbrains.com/pt-br/idea/download/#section=windows) para executar o projeto de maneira local; 
- [JDK 17.0.1](https://jdk.java.net/17/);
- [MySQL 8.0.27](https://dev.mysql.com/downloads/installer/);
- Opcional [MySQL Workbench](https://dev.mysql.com/downloads/installer/), caso deseje visualizar o banco de dados;
- Opcional [Postman](https://www.postman.com/downloads/) opcional caso queira visualizar com o postman.

Você também precisará fazer a seguinte configuração (siga o caminho abaixo)
- Clique com o botão direito em "Meu Computador";
- Clique em "Propriedades";
- Clique em "Configurações Avançadas do Sistema";
- Clique em "Variáveis de Ambiente";
- Copie o caminho para onde você fez o download do [JDK 17.0.1](https://jdk.java.net/17/);
- Em "Variáveis de Ambiente>Variáveis do Sistema" clique em "novo" e insira o nome da variável como sendo "JAVA_HOME" e insira o caminho do [JDK 17.0.1](https://jdk.java.net/17/) que você copiou e clique em "OK";
- Ainda em "Variáveis de Ambiente>Variáveis do Sistema" clique em "novo" e insira o nome da variável como sendo "CLASSPATH" e no valor coloque um ponto "." e depois clique em "OK";
- Em "Variáveis do Sistema" localize o "Path" e dê um duplo clique sobre ele, e adicione "%JAVA_HOME%\bin" e mova-o para cima e depois clique em "OK" e novamente em "OK";

- [x] Para validar a instalação do JDK abra o cmd e digite "java -version" e aparecerá a versão do java instalado.

### Como Executar o projeto
#### ⚙️ Executando e Instalando as Dependências

```bash
# Clone este repositório
$ git clone https://github.com/ergonlima/API-Banco-Digital/tree/main/desafio-rest-api
```
- Abra o [IntelliJ IDEA Community Edition](https://www.jetbrains.com/pt-br/idea/download/#section=windows) que você instalou e depois abra o projeto;
- Localize na parte direita superior lateral uma aba chamada "Maven" e a abra;
- Clique em "Reload All Maven Projects" para sincronizar e baixar as dependências do Maven;
- Após isso, basta clicar na seta verde ou apertar "shift+F10" e a API já estará executando.

### Testar no Swagger
#### 📝 Siga todos os Passos para realizar os testes
-*Todas as Mensagens de Exceção são exibidas no log da IDE*

Cole no seu navegador o link abaixo ou [Clique Aqui](http://localhost:8080/swagger-ui/#/conta-bancaria-controller)
```bash
# http://localhost:8080/swagger-ui/#/conta-bancaria-controller
```
<p align="left">A tela abaixo será apresentada</p>

<img alt="1_swagger" src="./imgs-readme/1_swagger.JPG" height="425" />

##### Função Busca por Id
-*Antes de inserir o Parâmetro solicitado, sempre aperte em "Try it out" EM TODOS OS MÉTODOS*

<img alt="2_swagger" src="./imgs-readme/2_swagger.JPG"/>

-*Depois insira o id e clique em "Execute", O resultado será exibido abaixo em forma de JSON*

<img alt="3_swagger" src="./imgs-readme/3_swagger.JPG"/>

##### Função Busca Todos

-*Clique em "Execute", O resultado será exibido abaixo em forma de JSON*

<img alt="4_swagger" src="./imgs-readme/4_swagger.JPG"/>

##### Função Cadastrar Conta
-*Insira o CPF e o nome do Cliente do Banco, não é possível inserir dois usuários com o mesmo CPF, cumprindo assim a regra de não cadastrar a mesma pessoa duas vezes*

-*Depois Clique em "Execute" e o usuário estará cadastrado se retornar status 200 OK*

<img alt="5_swagger" src="./imgs-readme/5_swagger.JPG"/>

##### Função Deletar Conta
-*Insira o Id e Clique em "Execute", após isso a conta será excluída"*

<img alt="6_swagger" src="./imgs-readme/6_swagger.JPG"/>

##### Função Depositar na Conta através do Id
-*Insira o Id da conta que deseja depositar o dinheiro e depois informe o valor e Clique em "Execute", após isso o dinheiro será depositado, é possível ver o resultado usando a função de busca por Id*

-*Só é possível realizar depósitos entre R$ 0,00 e R$ 2000,00*

<img alt="7_swagger" src="./imgs-readme/7_swagger.JPG"/>

##### Função Trasferência entre duas contas informando idDestino, idOrigem e Valor da transferência
-*Insira o Id de quem receberá o dinheiro (idDestino)*

-*Insira o Id de quem Enviará o dinheiro (idOrigem)*

-*Insira o Valor da Transferência*

*Só é possível realizar transferências entre R$ 0,00 e R$ 2000,00 e o cliente não pode enviar valores a mais do que possui*

<img alt="8_swagger" src="./imgs-readme/8_swagger.JPG"/>

### Testar no Postman
#### 📝 Siga todos os Passos para realizar os testes
-*Todas as Mensagens de Exceção são exibidas no log da IDE*

```bash
# Clone este repositório da collection do Postman
$ https://github.com/ergonlima/API-Banco-Digital/tree/main/collection-postman
```
Após isso, importe o arquivo .json para o Postman
<p align="left">A collection ficará assim </p>

<img alt="9_postman" src="./imgs-readme/9_postman.JPG"/>

##### Função Cadastrar Conta
-*Insira o CPF e o nome do Cliente do Banco, não é possível inserir dois usuários com o mesmo CPF, cumprindo assim a regra de não cadastrar a mesma pessoa duas vezes*

-*Depois Clique em "Send" e o usuário estará cadastrado se retornar status 200 OK*

<img alt="10_postman" src="./imgs-readme/10_postman.JPG"/>

##### Função Busca por Id

-*Insira o id na url e clique em "Send", O resultado será exibido abaixo em forma de JSON*

<img alt="11_postman" src="./imgs-readme/11_postman.JPG"/>

##### Função Depositar na Conta através do Id
-*Insira o Id da conta que deseja depositar o dinheiro e depois informe o valor e Clique em "Send", após isso o dinheiro será depositado, é possível ver o resultado usando a função de busca por Id*

-*Só é possível realizar depósitos entre R$ 0,00 e R$ 2000,00*

<img alt="12_postman" src="./imgs-readme/12_postman.JPG"/>

##### Função Trasferência entre duas contas informando idDestino, idOrigem e Valor da transferência
-*Insira o Id de quem receberá o dinheiro (idDestino)*

-*Insira o Id de quem Enviará o dinheiro (idOrigem)*

-*Insira o Valor da Transferência*

*Só é possível realizar transferências entre R$ 0,00 e R$ 2000,00 e o cliente não pode enviar valores a mais do que possui*

<img alt="13_postman" src="./imgs-readme/13_postman.JPG"/>

##### Função Deletar Conta
-*Insira o Id e Clique em "Send", após isso a conta será excluída"*

<img alt="14_postman" src="./imgs-readme/14_postman.JPG"/>

##### Função Busca Todos

-*Clique em "Send", O resultado será exibido abaixo em forma de JSON*

<img alt="15_postman" src="./imgs-readme/15_postman.JPG"/>

### Tecnologias
#### 🛠️ Ferramentas

As seguintes ferramentas foram usadas na construção do projeto:

- [IntelliJ IDEA Community Edition](https://www.jetbrains.com/pt-br/idea/download/#section=windows)
- [JDK 17.0.1](https://jdk.java.net/17/);
- [MySQL 8.0.27](https://dev.mysql.com/downloads/installer/);
- [Postman](https://www.postman.com/downloads/)
- [Swagger](https://swagger.io/)

---

### Autor

Made by Ergon Zamarian Lima 👋😁
