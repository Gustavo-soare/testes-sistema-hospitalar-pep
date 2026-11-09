# Checklist de Testes

O checklist a seguir apresenta as verificações realizadas durante a execução dos casos de teste no sistema OpenEMR.

- [ ] O usuário consegue acessar o sistema com credenciais válidas?
- [ ] O sistema rejeita o acesso quando são informadas credenciais incorretas?
- [ ] O sistema disponibiliza a funcionalidade de pesquisa de pacientes?
- [ ] É possível localizar um paciente previamente cadastrado?
- [ ] O sistema apresenta resultados compatíveis com os critérios de pesquisa informados?
- [ ] É possível consultar os dados cadastrais do paciente selecionado?
- [ ] O prontuário eletrônico apresenta as informações clínicas e o histórico de atendimentos disponíveis?
- [ ] O sistema permite cadastrar e editar informações básicas do paciente?
- [ ] Os campos obrigatórios são identificados pelo sistema?
- [ ] O sistema realiza a validação dos dados informados nos campos cadastrais?
- [ ] O sistema permite salvar as informações preenchidas corretamente?
- [ ] Os dados permanecem registrados após a atualização da página?
- [ ] O sistema permite realizar agendamentos pelo calendário?
- [ ] O agendamento apresenta corretamente o paciente, o profissional, a data e o horário selecionados?

## Observações da execução

Durante os testes, foram identificados comportamentos que merecem atenção:

- Na pesquisa de pacientes, foi possível realizar a busca específica, mas a tela utilizada não disponibilizou o campo necessário para executar a pesquisa de um paciente inexistente.
- Na validação cadastral, o sistema impediu o salvamento quando um campo obrigatório permaneceu vazio, destacando-o em vermelho.
- Durante a edição cadastral, foi observada uma alteração inesperada relacionada à data de nascimento, sem apresentação de mensagem de validação.
- Após a atualização da página, as informações permaneceram salvas, mas o sistema solicitou uma nova autenticação.
- O agendamento de consultas foi realizado com sucesso por meio do calendário.
