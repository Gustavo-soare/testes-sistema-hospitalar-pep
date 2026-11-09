# Casos de Teste

Este documento apresenta os casos de teste elaborados para avaliar o fluxo de consulta e preenchimento de informações básicas do prontuário eletrônico do paciente (PEP).

Os testes foram planejados para verificar o funcionamento das principais funcionalidades, incluindo situações normais, entradas inválidas, campos obrigatórios e persistência das informações.

**Observação:** os resultados obtidos, os status e as evidências deverão ser preenchidos somente após a execução real dos testes.

---

## CT01 — Login com credenciais válidas

- **Funcionalidade:** Autenticação.
- **Pré-condições:** Usuário cadastrado e sistema disponível.
- **Passos para execução:**
  1. Acessar a página inicial do sistema.
  2. Informar um usuário válido.
  3. Informar uma senha válida.
  4. Clicar no botão de acesso.
- **Dados de entrada:** Credenciais válidas de teste.
- **Resultado esperado:** Acessar o sistema.
- **Resultado obtido:** O sistema autenticou o usuário e apresentou a tela principal, disponibilizando o calendário e as funcionalidades do OpenEMR.
- **Status:** VALIDO.
- **Evidência:** CT01-login-valido.png.

## CT02 — Login com senha incorreta

- **Funcionalidade:** Autenticação.
- **Pré-condições:** Usuário cadastrado.
- **Passos para execução:**
  1. Acessar a página de login.
  2. Informar um usuário válido.
  3. Informar uma senha incorreta.
  4. Tentar acessar o sistema.
- **Dados de entrada:** Usuário válido e senha incorreta.
- **Resultado esperado:** O sistema deve impedir o acesso e apresentar uma mensagem apropriada.
- **Resultado obtido:** O sistema apresentou uma mensagem informando que o usuário ou a senha estavam incorretos, impedindo a autenticação.
- **Status:** Valido.
- **Evidência:** CT02-login-invalido.png
- **Observação:** Durante a avaliação, também foi realizada uma tentativa de inserir uma entrada semelhante a SQL Injection no campo de usuário. O sistema não permitiu o acesso. Essa observação não comprova a ausência de vulnerabilidades SQL Injection, pois seria necessária uma avaliação de segurança específica e autorizada.
  
## CT03 — Pesquisa de paciente existente

- **Funcionalidade:** Pesquisa de pacientes.
- **Pré-condições:** Usuário autenticado e paciente fictício cadastrado.
- **Passos para execução:**
  1. Acessar a área de pacientes.
  2. Localizar o campo de pesquisa.
  3. Informar um identificador de paciente existente.
  4. Executar a pesquisa.
- **Dados de entrada:** Nome de um paciente cadastrado.
- **Resultado esperado:** O sistema deve localizar e apresentar o paciente correspondente.
- **Resultado obtido:** O sistema apresentou uma lista contendo 14 pacientes cadastrados, com informações de identificação e histórico de consultas.
- **Status:** Valido.
- **Evidência:** CT03-pesquisa-paciente.png
- **Observação:** Ao acessar a funcionalidade de pesquisa sem informar filtros, o sistema apresentou a listagem geral dos pacientes cadastrados. Após informar o nome de um paciente, a aplicação filtrou os resultados e apresentou somente o registro correspondente à pesquisa realizada.

## CT04 — Pesquisa de paciente inexistente

- **Funcionalidade:** Pesquisa de pacientes.
- **Pré-condições:** Usuário autenticado.
- **Passos para execução:**
  1. Acessar a área de pacientes.
  2. Informar um identificador inexistente.
  3. Executar a pesquisa.
- **Resultado esperado:** O sistema deve permitir a pesquisa de pacientes por critérios disponíveis ou apresentar uma alternativa para localizar um paciente específico.
- **Resultado obtido:** Na tela utilizada, não foi identificado um campo para informar o nome de um paciente específico. Ao acessar a pesquisa sem filtros, o sistema apresentou a lista geral de pacientes, conforme observado no CT03.
- **Status:** BLOQUEADO, não foi possível executar a pesquisa de um paciente inexistente devido à ausência de um campo de filtro específico.
- **Evidência:** CT03-pesquisa-paciente.png

## CT05 — Consulta ao prontuário eletrônico

- **Funcionalidade:** Consulta de prontuário.
- **Pré-condições:** Usuário autenticado no OpenEMR e paciente previamente cadastrado.
- **Passos para execução:**
  1. Pesquisar um paciente cadastrado.
  2. Selecionar o paciente encontrado.
  3. Acessar a opção de visualizar prontuário.
  4. Verificar as informações apresentadas.
- **Resultado esperado:** O sistema deve permitir a abertura do prontuário e apresentar as informações correspondentes ao paciente selecionado, incluindo seus dados cadastrais e histórico clínico disponível.
- **Resultado obtido:** A consulta foi realizada com sucesso. O sistema apresentou as informações do paciente cadastrado, incluindo nome, CPF, endereço e histórico de consultas, com os valores e registros disponíveis no prontuário.
- **Status:** Valido.
- **Evidência:** CT05-consulta-prontuario.png

## CT06 — Preenchimento de informações válidas

- **Funcionalidade:** Preenchimento do prontuário.
- **Pré-condições:** Usuário autenticado e prontuário acessível para edição.
- **Passos para execução:**
  1. Acessar a funcionalidade de cadastro ou edição de pacientes.
  2. Informar o nome do paciente como Gustavo.
  3. Preencher os dados solicitados pelo sistema.
  4. Verificar a disponibilidade dos campos cadastrais.
- **Resultado esperado:** O sistema deve permitir o preenchimento e a edição das informações cadastrais do paciente.
- **Resultado obtido:** O cadastro foi realizado com sucesso. O sistema permitiu informar o nome Gustavo e preencher os dados solicitados nos campos cadastrais.
- **Status:** Valido.
- **Evidência:** CT06-edicao-cadastral.png

## CT07 — Tentativa de salvamento com campo obrigatório vazio

- **Funcionalidade:** Validação de campos obrigatórios.
- **Pré-condições:** Usuário autenticado e formulário de preenchimento aberto.
- **Passos para execução:**
  1. Acessar o formulário do prontuário.
  2. Deixar um campo obrigatório sem preenchimento.
  3. Preencher os demais campos necessários.
  4. Tentar salvar as informações.
  5. Observar o comportamento apresentado pelo sistema.
- **Dados de entrada:** Formulário com pelo menos um campo obrigatório vazio.
- **Resultado esperado:** O sistema deve impedir o salvamento do cadastro quando os campos obrigatórios não forem preenchidos, indicando quais informações precisam ser informadas.
- **Resultado obtido:** O sistema impediu o salvamento do cadastro. O campo obrigatório não preenchido foi destacado em vermelho, indicando a necessidade de preenchimento. Não foi apresentada uma mensagem textual de erro.
- **Status:** Valido.
- **Evidência:** CT07-campo-obrigatorio.png

## CT08 — Validação e alteração dos dados cadastrais

- **Funcionalidade:** Salvamento do prontuário.
- **Objetivo:** Verificar os dados informados no cadastro do paciente são mantidos corretamente e se o sistema realiza a validação adequada das informações inseridas.
- **Pré-condições:** Usuário autenticado no OpenEMR e acesso à funcionalidade de cadastro ou edição de pacientes.
- **Passos para execução:**
  1. Acessar o prontuário.
  2. Informar ou alterar um dado em um campo de texto.
  3. Observar o comportamento do sistema durante o preenchimento.
  4. Verificar se os dados são mantidos corretamente.
  5. Analisar possíveis alterações inesperadas nas informações cadastrais.
- **Resultado esperado:** O sistema deve preservar os dados informados corretamente e apresentar uma mensagem de validação ou aviso quando uma informação incompatível com o campo for inserida, evitando alterações indevidas no cadastro.
- **Resultado obtido:** Durante o teste, foi observado que, ao inserir uma informação em um campo de texto relacionado ao cadastro, o sistema realizou uma alteração inesperada, atribuindo a data atual de 2026 a um campo relacionado à data de nascimento. Não foi apresentada uma mensagem de erro ou confirmação da alteração.
- **Status:** Erro.
- **Evidência:** CT08-validacao-dados.png

## CT09 — Persistência das informações após atualização da página

- **Funcionalidade:** Persistência de dados.
- **Pré-condições:** Usuário autenticado e informações fictícias previamente salvas no prontuário.
- **Passos para execução:**
  1. Acessar o prontuário.
  2. Registrar e salvar informações fictícias.
  3. Atualizar a página.
  4. Realizar novamente a autenticação no sistema.
  5. Consultar o prontuário e verificar as informações registradas.
- **Dados de entrada:** Informações fictícias previamente salvas.
- **Resultado esperado:** As informações devem permanecer registradas e disponíveis após a atualização da página.
- **Resultado obtido:** As informações cadastradas permaneceram salvas após a atualização da página. Entretanto, foi observado que o sistema encerrou a sessão do usuário, exigindo uma nova autenticação para continuar utilizando suas funcionalidades.
- **Status:** Valido.
- **Evidência:** CT09-persistencia-dados.png
- **Observação:** Embora a persistência das informações tenha funcionado corretamente, o encerramento da sessão após a atualização da página representa um comportamento inesperado durante a utilização do sistema, que merece investigação complementar.

## CT10 — Agendamento de consulta pelo calendário

- **Funcionalidade:** Agendamento de consultas.
- **Pré-condições:** Usuário autenticado no OpenEMR e paciente previamente cadastrado.
- **Passos para execução:**
  1. Acessar o calendário do OpenEMR.
  2. Localizar a opção para adicionar ou agendar um novo evento
  3. Selecionar um paciente previamente cadastrado.
  4. Informar uma data e um horário para a consulta.
  5. Preencher os demais campos solicitados pelo sistema.
  6. Salvar o agendamento.
  7. Verificar se a consulta aparece no calendário.
- **Dados de entrada:** Paciente fictício previamente cadastrado, data e horário de consulta.
- **Resultado esperado:** O sistema deve permitir realizar o agendamento e apresentar a consulta registrada no calendário na data e no horário selecionados.
- **Resultado obtido:** A preencher após execução.
- **Status:** PENDENTE.
- **Evidência:** A inserir.

---

## Legenda dos resultados

- **Valido:** O comportamento observado corresponde ao resultado esperado.
- **Erro:** O comportamento observado apresenta divergência em relação ao resultado esperado.
- **PENDENTE:** O teste ainda não foi executado.

## Considerações finais

Os casos de teste foram elaborados considerando diferentes situações de utilização do sistema, incluindo operações válidas, entradas inválidas, validação de campos e persistência das informações. A execução permitirá avaliar se o fluxo selecionado atende aos requisitos funcionais e aos critérios de aceitação definidos para o projeto.
