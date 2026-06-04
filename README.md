[![Code coverage badge](https://img.shields.io/badge/coverage-100%25-brightgreen)](https://stryker-mutator.io/robo-coasters-example/reports/coverage/lcov-report/index.html)
[![Mutation testing badge](https://img.shields.io/endpoint?style=flat&url=https%3A%2F%2Fbadge-api.stryker-mutator.io%2Fgithub.com%2Fstryker-mutator%2Frobo-coasters-example%2Fmaster)](https://dashboard.stryker-mutator.io/reports/github.com/stryker-mutator/robo-coasters-example/master)

# PGATS - CI

## Pré-requisitos

1. Instale o [git](https://git-scm.com)
2. Instale o [nodejs](https://nodejs.org/)
3. Instale o Yarn - `npm install -g yarn`
4. Faça um _Fork_ do projeto
5. Clone o repositório para sua máquina (seu fork)
6. Instale as dependências
   ```shell
   cd pgats-ci
   yarn
   ```
7. Execute os testes de unidade - isso vai gerar um relatório
   ```shell
   yarn run test
   ```
8. Abra o relatório de cobertura de código em `reports/coverage/lcov-report`
9. Execute os testes de mutação com o Stryker
   ```shell
   yarn run test:mutation
   ```
10. Abra o relatório de mutação em `reports/mutation`
11. Instale os navegadores do Playwright
    ```shell
    yarn playwright install
    ```
12. Execute os testes end-to-end com o Playwright
    ```shell
    yarn run e2e
    ```
13. Execute a aplicação com `yarn start`
14. Acesse a aplicação publicada [neste link](https://pgats-ci-example.netlify.app)

--- 

# Desafio da Aula de da Pós-graduação


1) Use os conceitos e exemplos praticados em aula e aplique em outra ferramenta de integração Contínua. Sugestões:
- Azure DevOps
- CircleCI
- Gitlab CI
- Jenkins

2) Explore os plugins disponíveis no Marketplace e escolha um que pode agregar ao fluxo de trabalho como: relatórios, notificações, IA, etc.

3) Leia sobre self-hosted runners/agents. Tente executar os pipelines criados usando um. 
Avalie: Quando faz sentido usar esse recurso? 
Outras plataformas oferecem recursos similires? 


## Azure DevOps Pipeline

A ferramenta escolhida para este projeto foi o Azure DevOps, com o objetivo de ampliar meus conhecimentos em uma tecnologia que faz parte da stack utilizada no meu trabalho atual. Para configurar a integração contínua, foi criado o arquivo `azure-pipelines.yml` na raiz do projeto, responsável por definir e automatizar o fluxo de execução da pipeline.

Na segunda parte do desafio, optei por realizar a instalação do plugin do Allure Reports, que pode ser instalado por meio da documentação oficial [neste link](https://allurereport.org/docs/integrations-azure/]).

Após a execução da pipeline, é possível baixar o arquivo do relatório para visualizá-lo localmente em sua máquina ou acessar os resultados diretamente pelo Azure DevOps, facilitando a análise e o acompanhamento da execução dos testes.

## self-hosted runners/agents

Os Self-Hosted Runners permitem a execução de pipelines de CI/CD em infraestrutura própria, oferecendo maior flexibilidade e controle sobre o ambiente de execução. Com essa abordagem, é possível definir configurações personalizadas de hardware, software, rede e segurança, de acordo com as necessidades do projeto.

#### Principais casos de uso:

* Execução de aplicações que dependem de softwares ou bibliotecas específicas;
* Acesso a recursos internos da organização, como bancos de dados e serviços restritos;
* Otimização de desempenho por meio de recursos computacionais dedicados;
* Execução de testes que exigem infraestrutura especializada;
* Atendimento a requisitos de segurança, governança e conformidade;
* Possibilidade de redução de custos operacionais, dependendo do volume de execuções.

#### Plataformas que utilizam self-hosted runners/agents

| Plataforma          | Nome utilizado                 |
| ------------------- | ------------------------------ |
| GitHub              | Self-hosted Runners            |
| Microsoft           | Self-hosted Agents             |
| GitLab              | GitLab Runners                 |
| Atlassian           | Self-hosted Runners            |
| JetBrains           | Build Agents                   |
| CloudBees / Jenkins | Agents/Nodes                   |
| CircleCI            | Self-hosted Runners            |
| Buildkite           | Build Agents                   |
| Travis CI           | Self-hosted Enterprise Workers |

#### Demostração da execução utilizando self-hosted
<img width="1102" height="595" alt="azure" src="https://github.com/user-attachments/assets/8c1e7163-c53a-4ff5-8ecf-e23fcd237173" />
