# Matriz de Rastreabilidade

A matriz de rastreabilidade relaciona os requisitos funcionais, os critérios de aceitação e os respectivos casos de teste. Seu objetivo é garantir que todas as funcionalidades definidas no escopo sejam verificadas durante a execução dos testes.

| Requisito | Critério de aceitação | Caso(s) de teste |
|---|---|---|
| RF01 — Acesso ao sistema | CA01 — Permitir acesso com credenciais válidas. | CT01 e CT02 |
| RF02 — Pesquisa de pacientes | CA02 — Localizar pacientes cadastrados. | CT03 e CT04 |
| RF03 — Exibição dos dados do paciente | CA03 — Apresentar os dados do paciente selecionado. | CT05 |
| RF04 — Consulta ao prontuário | CA04 — Apresentar as informações disponíveis no prontuário. | CT05 |
| RF05 — Inserção de informações | CA05 — Aceitar informações em formatos válidos e identificar dados inválidos. | CT06 e CT09 |
| RF06 — Validação e salvamento | CA06 — Impedir salvamento com campos obrigatórios vazios e confirmar registros realizados. | CT07, CT08 e CT10 |

## Análise da rastreabilidade

A matriz permite verificar se os requisitos funcionais possuem critérios de aceitação e casos de teste correspondentes. Dessa forma, é possível acompanhar a cobertura dos requisitos e identificar funcionalidades que ainda não foram verificadas.

Os casos CT01 a CT10 foram relacionados aos requisitos e critérios de aceitação para garantir que o fluxo de consulta e preenchimento do prontuário eletrônico seja avaliado de maneira organizada.

**Observação:** a rastreabilidade apresentada representa o planejamento dos testes. A cobertura efetiva será confirmada após a execução dos casos de teste.
