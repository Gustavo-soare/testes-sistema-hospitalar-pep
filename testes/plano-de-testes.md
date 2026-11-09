# Plano de Testes

## Objetivo

Verificar o funcionamento das principais funcionalidades do sistema OpenEMR relacionadas à autenticação, pesquisa e consulta de pacientes, preenchimento e atualização de informações cadastrais, validação dos dados, persistência das informações e agendamento de consultas. A avaliação busca identificar se os comportamentos apresentados pelo sistema correspondem aos requisitos funcionais e aos critérios de aceitação estabelecidos para o projeto.

## Funcionalidades testadas

- Autenticação de usuários;
- Pesquisa e localização de pacientes;
- Consulta ao prontuário eletrônico;
- Visualização de informações cadastrais e clínicas;
- Cadastro e edição de informações dos pacientes;
- Validação de campos obrigatórios;
- Validação dos formatos das informações inseridas;
- Salvamento e persistência dos dados;
- Agendamento de consultas por meio do calendário.

## Funcionalidades não testadas

- Prescrição de medicamentos;
- Solicitação e interpretação de exames;
- Registro e elaboração de diagnósticos médicos;
- Faturamento e cobrança de serviços hospitalares;
- Gestão financeira da instituição;
- Integração com sistemas externos.

## Ambiente de testes

Os testes serão realizados na versão 8.5.0 do OpenEMR, utilizando o ambiente de demonstração disponibilizado publicamente na internet.

As configurações utilizadas durante a execução dos testes são:

- **Aplicação:** OpenEMR.
- **Versão:** 8.5.0.
- **Ambiente:** Demonstração online.
- **Navegador:** Opera.
- **Sistema operacional:** Windows.
- **Perfil de acesso:** Physician (médico).
- **Dados utilizados:** Pacientes fictícios.

Os testes serão realizados por meio das funcionalidades normalmente disponíveis na interface do sistema, sem alterações no código-fonte ou acesso direto ao banco de dados.

Por se tratar de um ambiente público de demonstração, serão utilizados exclusivamente dados fictícios, considerando também a possibilidade de alterações ou reinicializações dos registros existentes.

## Tipos de teste

- **Testes funcionais:** verificam o funcionamento das funcionalidades disponibilizadas pelo sistema.
- **Testes de validação:** avaliam o comportamento dos campos e a consistência das informações inseridas.
- **Testes negativos:** verificam a resposta do sistema diante de entradas inválidas ou situações não permitidas.
- **Testes de persistência dos dados:** verificam se as informações permanecem registradas após o salvamento e a atualização da página.
- **Testes de fluxo alternativo:** avaliam comportamentos diferentes do fluxo principal de utilização, como pesquisas sem filtros e tentativas de preenchimento incompleto.

## Critérios de conclusão

Os casos de teste planejados deverão ser executados e documentados com seus respectivos procedimentos, resultados obtidos, situações identificadas e evidências. A avaliação será realizada por meio da comparação entre os resultados esperados e os comportamentos efetivamente apresentados pelo sistema, permitindo identificar funcionalidades aprovadas, falhas observadas e limitações que impeçam a execução de determinados testes.
