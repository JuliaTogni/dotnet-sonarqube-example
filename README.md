# Relatório: Ponderada semana 9 utilizando SonarQube

## Introdução

Este breve resumo aborda o aprimoramento da qualidade e segurança do código através do uso combinado do SonarQube, Docker e .NET Core. O SonarQube serve para detectar falhas de segurança e qualidade no código, enquanto o Docker permite a execução do SonarQube em um ambiente segregado. Nosso enfoque é a análise de uma aplicação ASP.NET Core 3.0 utilizando o SonarQube para identificar e solucionar eventuais falhas no código.

## Ferramentas Empregadas

- **SonarQube**: Ferramenta de análise de código que aponta deficiências de qualidade e segurança.
- **Docker**: Plataforma para o desenvolvimento e execução de aplicativos em contêineres.
- **.NET Core**: Framework opensource mantido pela Microsoft para o desenvolvimento de aplicações modernas e compatíveis com diversas plataformas.
- **Java SDK**: Necessário para o funcionamento do SonarScanner, que analisa o código-fonte.
- **GitHub**: Usado para o armazenamento de código de aplicativos e bibliotecas.

## Conhecimentos Adquiridos

- **Análise de Código com SonarQube**: Compreendemos como o SonarQube destaca falhas de qualidade e segurança no código, tais como bugs, vulnerabilidades e repetições de código.
- **Uso do Docker em Desenvolvimento**: Aprendemos como o Docker facilita a criação de ambientes de desenvolvimento isolados, permitindo executar aplicações e serviços de maneira contida.
- **Análise de Código com SonarScanner**: Demonstramos o uso do SonarScanner para avaliar o código de um projeto .NET Core e enviar os resultados para o SonarQube.
- **Configuração do SonarQube**: Investigamos a personalização do SonarQube para adequá-lo às especificidades de um projeto, incluindo a configuração de regras, exclusão de arquivos/diretórios e ajuste do escopo de análise.

## Resultados

Ao aplicar a análise de código no exemplo de aplicação ASP.NET Core com o SonarQube e Docker, identificamos e corrigimos diversos problemas de qualidade e segurança, como bugs, vulnerabilidades e repetições de código. Aprendemos também a interpretar e utilizar os dados analíticos fornecidos pelo SonarQube para aprimorar a qualidade do código e prevenir falhas futuras.

## Conclusão

A utilização de ferramentas de análise estática de código, como o SonarQube, em combinação com o Docker e .NET Core, contribui significativamente para a melhoria da qualidade e segurança do código. Essa abordagem resulta em aplicativos mais robustos, seguros e fáceis de manter. Este tutorial proporcionou insights valiosos sobre a configuração, execução e interpretação de análises de código, ensinamentos que podem ser aplicados em nosso desenvolvimento do projeto atual, em parceria com a Track.Co.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Analyze Your Code Using SonarQube, Docker and .NET Core

This app is an example app for learning how to use SonarQube on your projects. For more details please read [Analyze Your Code Using SonarQube, Docker and .NET Core](link_to_replace) to see a detailed instruction on how to do that.

**Prerequisites:**

- [Java 11](https://adoptopenjdk.net/)+
- [Docker](https://docs.docker.com/get-docker/)
- [.NET Core](https://dotnet.microsoft.com/download)
- [SonarScanner for .NET Core](https://github.com/SonarSource/sonar-scanner-msbuild/releases/download/4.7.1.2311/sonar-scanner-msbuild-4.7.1.2311-netcoreapp2.0.zip)

**Table of Contents**

- [Getting Started](#getting-started)
- [Help](#help)
- [License](#license)

## Getting Started

Begin with running SonarQube on Docker:
```sh
docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
```

**NOTE:** You'll be able to login with `admin/admin`. After first login, you will be promted to change the default credentials.

In order to run SonarScanner, run the following commands:

```sh
dotnet sonarscanner begin /k:"project-key" /d:sonar.login=admin /d:sonar.password=admin
dotnet build <path_to_solution.sln>
dotnet sonarscanner end /d:sonar.login=admin /d:sonar.password=admin
```

> **NOTE:** Remember to replace "path_to_solution" and "password" with correct ones for your example.

## Help

Please post any questions as comments on the [blog post](link_to_replace), or visit our [Okta Developer Forums](https://devforum.okta.com/). You can also ask them on [Stack Overflow with the `sonarqube` tag](https://stackoverflow.com/tags/sonarqube).

## License

Apache 2.0, see [LICENSE](LICENSE).
