# Matriz de Rastreabilidade

A matriz de rastreabilidade relaciona os requisitos funcionais, os critérios de aceitação e os respectivos casos de teste. Seu objetivo é garantir que as funcionalidades definidas no escopo sejam verificadas durante a execução dos testes, permitindo acompanhar a cobertura dos requisitos e identificar possíveis falhas ou limitações do sistema.

| **Requisito** | **Critério de aceitação** | **Caso(s) de teste** |
|---|---|---|
| RF01 — Acesso ao sistema | CA01 — Permitir o acesso ao sistema mediante credenciais válidas. | CT01 |
| RF02 — Validação de credenciais | CA02 — Impedir o acesso ao sistema quando forem informadas credenciais inválidas. | CT02 |
| RF03 — Pesquisa de pacientes | CA03 — Permitir a localização de pacientes cadastrados no sistema. | CT03 e CT04 |
| RF04 — Exibição dos dados do paciente | CA04 — Apresentar os dados cadastrais do paciente selecionado. | CT05 |
| RF05 — Consulta ao prontuário | CA05 — Disponibilizar as informações clínicas e o histórico de atendimento registrados no prontuário. | CT05 |
| RF06 — Inserção e edição de informações | CA06 — Permitir o cadastro ou a alteração das informações cadastrais do paciente. | CT06 |
| RF07 — Validação de campos obrigatórios | CA07 — Impedir o salvamento de registros quando os campos obrigatórios não estiverem preenchidos. | CT07 |
| RF08 — Validação dos dados informados | CA08 — Verificar os formatos e tipos de dados inseridos, evitando alterações ou registros incorretos. | CT08 |
| RF09 — Salvamento e persistência dos dados | CA09 — Garantir que as informações salvas permaneçam disponíveis após a atualização da página ou novo acesso ao sistema. | CT09 |
| RF10 — Agendamento de consultas | CA10 — Permitir o agendamento de consultas, associando paciente, profissional, data e horário. | CT10 |

## Análise da rastreabilidade

A matriz permite verificar a correspondência entre os requisitos funcionais, os critérios de aceitação e os casos de teste desenvolvidos. Essa relação facilita o acompanhamento da cobertura dos requisitos e permite identificar quais funcionalidades foram verificadas durante a execução dos testes.

Os casos de teste CT01 a CT10 foram relacionados aos respectivos requisitos e critérios de aceitação, abrangendo funcionalidades de autenticação, pesquisa e consulta de pacientes, preenchimento e validação de informações, persistência dos dados e agendamento de consultas.

Durante a execução, foram identificadas algumas limitações e ocorrências, como a impossibilidade de realizar a pesquisa específica prevista no CT04, o comportamento inesperado observado no CT08 e a necessidade de realizar uma nova autenticação após a atualização da página no CT09. Essas situações foram consideradas na análise dos resultados, sem deixar de distinguir os casos concluídos daqueles que apresentaram impedimentos ou comportamentos diferentes do esperado.

**Observação:** a matriz apresenta a relação entre os requisitos, os critérios de aceitação e os casos de teste. A situação efetiva de cada funcionalidade deve ser considerada em conjunto com os resultados registrados nos respectivos casos de teste.
