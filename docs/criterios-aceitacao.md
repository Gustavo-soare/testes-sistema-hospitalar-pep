# Critérios de Aceitação

Os critérios de aceitação estabelecem as condições que deverão ser atendidas pelo sistema para que os requisitos funcionais sejam considerados implementados corretamente. Eles servem como referência para a elaboração e execução dos casos de teste, permitindo verificar se as funcionalidades disponibilizadas pelo OpenEMR apresentam os comportamentos esperados.

| ID | Critério de aceitação |
|---|---|
| CA01 | O sistema deve permitir a autenticação do usuário quando forem informadas credenciais válidas, direcionando-o à página principal da aplicação. |
| CA02 | O sistema deve impedir a autenticação quando forem informadas credenciais inválidas, apresentando uma mensagem que indique a falha no acesso. |
| CA03 | O sistema deve permitir a pesquisa de pacientes cadastrados, apresentando os registros correspondentes aos critérios informados e disponibilizando a listagem geral quando não forem aplicados filtros. |
| CA04 | O sistema deve permitir a localização de pacientes por meio de critérios de pesquisa e apresentar os resultados correspondentes, sem exibir registros incompatíveis com os dados informados. |
| CA05 | O sistema deve permitir a consulta ao prontuário eletrônico do paciente selecionado, apresentando suas informações cadastrais e os registros clínicos disponíveis. |
| CA06 | O sistema deve permitir o cadastro e a edição das informações dos pacientes, disponibilizando os campos necessários para o preenchimento dos dados cadastrais. |
| CA07 | O sistema deve impedir o salvamento de cadastros quando os campos obrigatórios não estiverem preenchidos, identificando os campos que necessitam de informação. |
| CA08 | O sistema deve validar os dados informados nos campos cadastrais, considerando os formatos e tipos de informação esperados, evitando alterações indevidas e apresentando orientações quando forem identificadas informações inválidas.|
| CA09 | O sistema deve manter as informações cadastradas após o salvamento, permitindo sua consulta novamente mesmo depois da atualização da página ou de um novo acesso ao prontuário. |
| CA10 | O sistema deve permitir o agendamento de consultas, possibilitando a seleção do paciente, do profissional responsável, da data e do horário, apresentando o agendamento realizado no calendário. |

## Observação

Os critérios de aceitação foram definidos com base nos requisitos funcionais e nas funcionalidades selecionadas para avaliação do OpenEMR. Eles contemplam operações de autenticação, pesquisa e consulta de pacientes, gerenciamento de informações cadastrais, validação de dados, persistência de informações e agendamento de consultas.

Durante a execução dos casos de teste, os critérios serão utilizados para comparar os resultados esperados com os comportamentos efetivamente apresentados pelo sistema. Dessa forma, será possível identificar funcionalidades que atendem às condições estabelecidas, bem como limitações e inconsistências observadas durante os testes.
