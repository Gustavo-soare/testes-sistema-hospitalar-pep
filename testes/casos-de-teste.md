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
- **Pré-condições:** Usuário autenticado e paciente fictício cadastrado com prontuário disponível.
- **Passos para execução:**
  1. Pesquisar um paciente cadastrado.
  2. Selecionar o paciente encontrado.
  3. Acessar a opção de visualizar prontuário.
  4. Verificar as informações apresentadas.
- **Dados de entrada:** Paciente fictício com prontuário cadastrado.
- **Resultado esperado:** O sistema deve apresentar corretamente as informações disponíveis no prontuário.
- **Resultado obtido:** A preencher após execução.
- **Status:** PENDENTE.
- **Evidência:** A inserir.

## CT06 — Preenchimento de informações válidas

- **Funcionalidade:** Preenchimento do prontuário.
- **Pré-condições:** Usuário autenticado e prontuário acessível para edição.
- **Passos para execução:**
  1. Acessar o prontuário de um paciente fictício.
  2. Selecionar a opção de inserir informações.
  3. Preencher os campos disponíveis com dados válidos.
  4. Verificar se os dados foram aceitos pelo sistema.
- **Dados de entrada:** Informações fictícias em formatos aceitos pelos campos.
- **Resultado esperado:** O sistema deve aceitar as informações válidas e permitir o prosseguimento do preenchimento.
- **Resultado obtido:** A preencher após execução.
- **Status:** PENDENTE.
- **Evidência:** A inserir.

## CT07 — Tentativa de salvamento com campo obrigatório vazio

- **Funcionalidade:** Validação de campos obrigatórios.
- **Pré-condições:** Usuário autenticado e formulário de preenchimento aberto.
- **Passos para execução:**
  1. Acessar o formulário do prontuário.
  2. Deixar um campo obrigatório sem preenchimento.
  3. Preencher os demais campos necessários.
  4. Tentar salvar as informações.
- **Dados de entrada:** Formulário com pelo menos um campo obrigatório vazio.
- **Resultado esperado:** O sistema deve impedir o salvamento e indicar qual campo precisa ser preenchido.
- **Resultado obtido:** A preencher após execução.
- **Status:** PENDENTE.
- **Evidência:** A inserir.

## CT08 — Salvamento de informações válidas

- **Funcionalidade:** Salvamento do prontuário.
- **Pré-condições:** Usuário autenticado, prontuário acessível para edição e formulário preenchido corretamente.
- **Passos para execução:**
  1. Acessar o prontuário.
  2. Preencher os campos obrigatórios com dados válidos.
  3. Clicar na opção de salvar.
  4. Verificar a mensagem apresentada pelo sistema.
- **Dados de entrada:** Informações fictícias válidas.
- **Resultado esperado:** O sistema deve salvar as informações e apresentar uma confirmação da operação.
- **Resultado obtido:** A preencher após execução.
- **Status:** PENDENTE.
- **Evidência:** A inserir.

## CT09 — Inserção de informação em formato inválido

- **Funcionalidade:** Validação de dados.
- **Pré-condições:** Usuário autenticado e formulário de preenchimento disponível.
- **Passos para execução:**
  1. Acessar o formulário do prontuário.
  2. Identificar um campo que possua formato definido, como data.
  3. Informar um valor em formato inválido.
  4. Tentar salvar as informações.
- **Dados de entrada:** Valor incompatível com o formato esperado pelo campo.
- **Resultado esperado:** O sistema deve rejeitar o valor inválido e apresentar uma orientação para correção.
- **Resultado obtido:** A preencher após execução.
- **Status:** PENDENTE.
- **Evidência:** A inserir.

## CT10 — Persistência das informações após atualização da página

- **Funcionalidade:** Persistência de dados.
- **Pré-condições:** Usuário autenticado e informações fictícias previamente salvas no prontuário.
- **Passos para execução:**
  1. Acessar o prontuário.
  2. Registrar e salvar informações fictícias.
  3. Atualizar a página.
  4. Consultar novamente as informações registradas.
- **Dados de entrada:** Informações fictícias previamente salvas.
- **Resultado esperado:** As informações devem permanecer registradas e disponíveis após a atualização da página.
- **Resultado obtido:** A preencher após execução.
- **Status:** PENDENTE.
- **Evidência:** A inserir.

---

## Legenda dos resultados

- **PASS:** O comportamento observado corresponde ao resultado esperado.
- **FAIL:** O comportamento observado apresenta divergência em relação ao resultado esperado.
- **PENDENTE:** O teste ainda não foi executado.

## Considerações finais

Os casos de teste foram elaborados considerando diferentes situações de utilização do sistema, incluindo operações válidas, entradas inválidas, validação de campos e persistência das informações. A execução permitirá avaliar se o fluxo selecionado atende aos requisitos funcionais e aos critérios de aceitação definidos para o projeto.
