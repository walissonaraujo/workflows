# CI/CD with GitHub Actions

This project contains a series of examples of how to use GitHub Actions to implement CI/CD pipelines.

## Índice

- [Visão Geral](#visão-geral)
- [Java-Springboot](#java-springboot)
- [Frontend-Stack](#frontend-stack)

## Visão Geral

`CI/CD with GitHub Actions` é um projeto que tem como objetivo demonstrar como implementar pipelines de CI/CD utilizando o GitHub Actions.

## Java-Springboot

Este diretório contém um exemplo de como configurar uma pipeline de CI/CD para um projeto Java utilizando o framework Spring Boot.

### Pré-requisitos

Certifique-se de que o JDK (Java Development Kit) está instalado em sua máquina. Você também precisará do arquivo `pom.xml` configurado corretamente para o seu projeto Spring Boot.

### Passos da Pipeline

A pipeline de CI/CD para o projeto Java-Springboot inclui os seguintes passos:

1. **Build**: Compilação do projeto Java utilizando o Maven.
2. **Testes**: Execução dos testes automatizados para garantir a qualidade do código.
3. **Empacotamento**: Empacotamento do aplicativo em um arquivo JAR executável.
4. **Implantação**: Implantação do aplicativo em um servidor de teste ou produção (opcional).

Para implementar a pipeline, você pode usar o arquivo `.github/workflows/java-springboot.github-ci.yml` neste repositório como modelo e personalizá-lo para atender às necessidades do seu projeto.


Este workflow automatiza o processo de build de um projeto Maven com Java 11 sempre que uma nova versão (release) é criada. Você pode copiar e usar esse arquivo como ponto de partida para configurar a pipeline de CI/CD do seu projeto Spring Boot com Maven. Lembre-se de personalizar o arquivo conforme necessário para atender às especificidades do seu projeto.

### Maven Package

Este é um workflow para automatizar o build de um projeto Maven com Java 11 sempre que uma nova versão (release) é criada.

```yaml
on:
  release:
    types: [created]
```
Esta seção especifica **quando** [on] o fluxo de trabalho será acionado. Neste caso, o workflow será executado quando uma nova versão (release) é criada no repositório.

```yaml
jobs:
    build:
        runs-on: ubuntu-latest
```
A seção "jobs" define os trabalhos (jobs) a serem executados. Neste caso, temos um trabalho chamado "build" que será executado na máquina com sistema operacional Ubuntu mais recente (ubuntu-latest).

```yaml
  steps:
  - uses: actions/checkout@v3
  - name: Set up JDK 11
    uses: actions/setup-java@v3
    with:
      java-version: '11'
  - name: Build with Maven
    run: mvn -B package --file pom.xml
```
1 - A seção "steps" lista as etapas do trabalho (job). A primeira etapa usa a ação "actions/checkout@v3" para fazer o checkout do código do repositório.
2 - A segunda etapa configura o ambiente Java JDK 11 usando a ação "actions/setup-java@v3".
3 - A terceira etapa executa o comando "mvn -B package --file pom.xml" para fazer o build do projeto Maven com Java 11.

Novamente, lembre-se de personalizar o arquivo conforme necessário para atender às especificidades do seu projeto.





## Frontend-Stack

Este diretório contém um exemplo de como configurar uma pipeline de CI/CD para uma stack de frontend utilizando a biblioteca React.

### Pré-requisitos

Certifique-se de que o Node.js e o npm (Node Package Manager) estão instalados em sua máquina. Você também precisará do arquivo `package.json` configurado corretamente para o seu projeto React.

### Passos da Pipeline

A pipeline de CI/CD para a stack frontend React inclui os seguintes passos:

1. **Instalação de Dependências**: Instalação das dependências do projeto utilizando o npm.
2. **Build**: Compilação do código React e criação dos arquivos estáticos para produção.
3. **Testes**: Execução dos testes automatizados para garantir a integridade do frontend.
4. **Implantação**: Implantação dos arquivos estáticos em um servidor web ou plataforma de hospedagem (por exemplo, Netlify, Vercel, GitHub Pages, etc.).

Para implementar a pipeline, você pode usar o arquivo `.github/workflows/frontend_stack.github-ci.yml` neste repositório como modelo e personalizá-lo de acordo com as necessidades do seu projeto.

---

Lembre-se de substituir os espaços reservados (como os nomes dos arquivos de pipeline) pelas informações reais do seu projeto. Essas descrições fornecem uma estrutura básica que você pode expandir com mais detalhes e exemplos específicos para o seu caso.
