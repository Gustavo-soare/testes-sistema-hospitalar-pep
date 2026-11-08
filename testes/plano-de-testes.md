# Plano de Testes

## Objetivo

Verificar o funcionamento do fluxo de consulta e
preenchimento de informações básicas do prontuário.

## Funcionalidades testadas

- Autenticação;
- Pesquisa de pacientes;
- Consulta ao prontuário;
- Preenchimento de informações;
- Validação de campos;
- Salvamento de informações.

## Funcionalidades não testadas

- Prescrições;
- Exames;
- Agendamentos;
- Faturamento;
- Diagnósticos.

## 4. Ambiente de testes

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

- Testes funcionais;
- Testes de validação;
- Testes negativos;
- Testes de persistência dos dados;
- Testes de fluxo alternativo.

## Critérios de conclusão

Todos os casos planejados deverão ser executados
e documentados com seus respectivos resultados.
