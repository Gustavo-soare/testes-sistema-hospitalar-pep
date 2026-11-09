# Software — Sistema Hospitalar PEP

**Aluno:** Gustavo Henrique Soares  
**Disciplina:** SF022 — Engenharia de Software  
**Professor:** Luís Felipe Schons Silva

## 1. Apresentação

Este projeto tem como finalidade aplicar os conceitos e práticas de Engenharia de Software na avaliação de um sistema hospitalar com funcionalidade de Prontuário Eletrônico do Paciente (PEP).

A proposta consiste em analisar as funcionalidades disponibilizadas pelo sistema, considerando aspectos relacionados à autenticação de usuários, ao gerenciamento de pacientes, à consulta de informações clínicas, ao preenchimento e à atualização de dados cadastrais, à persistência das informações e ao agendamento de consultas.

## 2. Aplicação analisada

O sistema utilizado para a realização dos testes foi o **OpenEMR**, uma aplicação de código aberto voltada ao gerenciamento de informações e processos relacionados à área da saúde.

Foi utilizada a versão 8.5.0, disponibilizada em ambiente de demonstração online, com acesso por meio do perfil Physician (médico).

A avaliação foi realizada diretamente pela interface do sistema, utilizando exclusivamente dados fictícios, sem alterações no código-fonte ou acesso direto ao banco de dados.

## 3. Objetivo

Avaliar o funcionamento das principais funcionalidades do OpenEMR relacionadas ao gerenciamento de pacientes e ao prontuário eletrônico, verificando se os comportamentos apresentados correspondem aos requisitos funcionais e aos critérios de aceitação estabelecidos.

A avaliação também busca identificar possíveis falhas, limitações e comportamentos inesperados durante a execução dos testes.

## 4. Escopo do projeto

O projeto contempla a avaliação das seguintes funcionalidades:

- Autenticação de usuários;
- Validação de credenciais;
- Pesquisa e localização de pacientes;
- Visualização de dados cadastrais;
- Consulta ao prontuário eletrônico;
- Cadastro e edição de informações dos pacientes;
- Validação de campos obrigatórios;
- Validação dos dados informados;
- Salvamento e persistência das informações;
- Agendamento de consultas por meio do calendário.

As funcionalidades relacionadas a prescrições, exames, diagnósticos, faturamento, gestão financeira e integração com sistemas externos não fazem parte do escopo de testes executados.

## 5. Documentação do projeto

A documentação foi organizada em arquivos específicos, com o objetivo de facilitar a compreensão, o planejamento e o acompanhamento das atividades realizadas.

| Documento | Descrição |
|---|---|
| Escopo do projeto | Define os limites e as funcionalidades avaliadas. |
| Requisitos funcionais | Apresenta as funcionalidades esperadas do sistema. |
| Critérios de aceitação | Estabelece as condições necessárias para considerar cada requisito atendido. |
| Plano de testes | Descreve os objetivos, o ambiente, os tipos de testes e os critérios de conclusão. |
| Checklist | Apresenta as verificações gerais realizadas durante os testes. |
| Casos de teste | Documenta os procedimentos, resultados esperados, resultados obtidos e evidências. |
| Matriz de rastreabilidade | Relaciona os requisitos funcionais aos critérios de aceitação e casos de teste. |

## 6. Ambiente de testes

As configurações utilizadas durante a avaliação foram:

- **Aplicação:** OpenEMR.
- **Versão:** 8.5.0.
- **Ambiente:** Demonstração online.
- **Navegador:** Opera.
- **Sistema operacional:** Windows.
- **Perfil de acesso:** Physician (médico).
- **Dados utilizados:** Pacientes fictícios.

## 7. Resultados dos testes

Foram elaborados e executados dez casos de teste (CT01 a CT10), abrangendo as funcionalidades definidas no escopo do projeto.

Os testes contemplaram situações de acesso válido e inválido, pesquisa de pacientes, consulta ao prontuário, edição cadastral, validação de informações, persistência dos dados e agendamento de consultas.

Durante a execução, foram identificadas situações que merecem atenção, como limitações na pesquisa específica de pacientes, comportamento inesperado durante a validação cadastral e necessidade de uma nova autenticação após a atualização da página.

Os resultados individuais, incluindo os procedimentos executados, os comportamentos observados e as evidências correspondentes, estão documentados no arquivo `testes/casos-de-teste.md`.

## 8. Evidências

As capturas de tela utilizadas para comprovar a execução dos testes estão organizadas na pasta `evidencias`.

As evidências permitem visualizar os procedimentos realizados, as mensagens apresentadas pelo sistema e os resultados obtidos durante a avaliação.

## 9. Estrutura do repositório

A organização dos arquivos do projeto está distribuída da seguinte maneira:

```text
Software-Sistema-Hospitalar-PEP/
│
├── README.md
│
├── documentacao/
│   ├── escopo.md
│   ├── requisitos.md
│   └── criterios-aceitacao.md
│
├── testes/
│   ├── checklist.md
│   ├── casos-de-teste.md
│   ├── rastreabilidade.md
│   └── plano-de-testes.md
│
└── evidencias/
    ├── CT01/
    ├── CT02/
    ├── CT03/
    ├── CT04/
    ├── CT05/
    ├── CT06/
    ├── CT07/
    ├── CT08/
    ├── CT09/
    └── CT10/
```

## 10. Considerações finais

A realização deste projeto possibilitou aplicar conceitos de Engenharia de Software por meio da definição de requisitos funcionais, elaboração de critérios de aceitação, planejamento e execução de casos de teste.

A avaliação do OpenEMR permitiu observar o comportamento de funcionalidades relacionadas ao gerenciamento de pacientes e ao prontuário eletrônico, identificando tanto situações em conformidade com o esperado quanto limitações e comportamentos inesperados.

Dessa forma, o projeto demonstra a importância da documentação, da rastreabilidade e da execução sistemática de testes para avaliar a qualidade e a confiabilidade de sistemas hospitalares.
