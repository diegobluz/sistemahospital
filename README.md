# Sistema Hospitalar

Aplicação desktop desenvolvida em Java para cadastro e consulta de pacientes, com persistência de dados em MySQL e interface gráfica construída com Java Swing.

## Sobre o projeto

O projeto demonstra a construção de uma aplicação desktop organizada em camadas, separando interface gráfica, serviços, acesso a dados, modelos de domínio e persistência.

O sistema trabalha principalmente com pacientes e convênios, utilizando JDBC e o padrão DAO para comunicação com o banco de dados.

## Funcionalidades

- Cadastro de pacientes
- Consulta e listagem de pacientes
- Busca de pacientes com filtros
- Associação de pacientes a convênios
- Persistência dos dados em MySQL
- Interface gráfica desktop com Java Swing

## Tecnologias utilizadas

- Java
- Java Swing
- JDBC
- MySQL
- MySQL Connector/J
- Apache Ant
- NetBeans IDE
- JUnit 4
- Git e GitHub

## Arquitetura e organização

O projeto possui uma separação em pacotes por responsabilidade:

```text
src/
├── dao/
│   ├── ConvenioDAO.java
│   ├── DAOFactory.java
│   └── PacienteDAO.java
├── modelo/
│   ├── Convenio.java
│   └── Paciente.java
├── persistencia/
│   └── ConexaoBanco.java
├── servicos/
│   ├── ConvenioServicos.java
│   ├── PacienteServicos.java
│   └── ServicosFactory.java
└── visao/
    ├── GuiCadPaciente.java
    ├── GuiJTableBuscaPaciente.java
    └── Menu.java
```

### Camadas

**Visão (`visao`)** — telas Swing responsáveis pela interação com o usuário.

**Serviços (`servicos`)** — camada intermediária entre as telas e a persistência.

**DAO (`dao`)** — acesso ao banco de dados e execução das operações SQL.

**Modelo (`modelo`)** — representação das entidades da aplicação, como paciente e convênio.

**Persistência (`persistencia`)** — criação da conexão JDBC com o MySQL.

## Fluxo da aplicação

```text
Java Swing
    │
    ▼
Serviços
    │
    ▼
DAO
    │
    ▼
JDBC
    │
    ▼
MySQL
```

## Dados de paciente

A entidade `Paciente` contém informações como:

- ID
- Nome
- CPF
- RG
- Endereço
- Data de nascimento
- Telefone
- E-mail
- Convênio

## Como executar

### Pré-requisitos

- JDK compatível com o projeto
- MySQL Server
- MySQL Connector/J
- NetBeans IDE ou Apache Ant

### 1. Clone o repositório

```bash
git clone https://github.com/diegobluz/sistemahospital.git
cd sistemahospital
```

### 2. Configure o banco

A aplicação espera um banco MySQL chamado:

```text
hospital_uc12
```

Os parâmetros de conexão estão centralizados em `src/persistencia/ConexaoBanco.java`.

> Para uso em um ambiente real, credenciais de banco não devem ficar diretamente no código-fonte. Prefira variáveis de ambiente ou um arquivo de configuração não versionado.

### 3. Execute a aplicação

A classe principal configurada no projeto é:

```text
visao.Menu
```

O projeto pode ser aberto e executado pelo NetBeans ou compilado com Apache Ant.

## Conceitos praticados

- Programação Orientada a Objetos
- Interfaces gráficas com Swing
- Arquitetura em camadas
- DAO (Data Access Object)
- JDBC
- SQL e `PreparedStatement`
- Persistência de dados
- Separação de responsabilidades
- Tratamento de exceções
- Collections em Java

## Possíveis melhorias

- Externalizar as credenciais do banco de dados
- Adicionar scripts SQL para criação automática do banco
- Ampliar a cobertura de testes automatizados
- Adicionar validação dos dados de entrada
- Modernizar a configuração de dependências com Maven ou Gradle
- Melhorar o tratamento centralizado de erros
- Adicionar operações completas de edição e exclusão

## Autor

**Diego Luz**

Projeto desenvolvido para fins de estudo e prática de desenvolvimento Java.