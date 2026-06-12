Plano de Fluxo de Trabalho e Ciclo de Vida do Bug
Fluxo de Trabalho do Desenvolvimento (User Stories)
To Do (A Fazer): Tarefas prontas para serem iniciadas.

In Progress (Em Desenvolvimento): O desenvolvedor está atuando no código.

In Review / Pull Request: O código está sendo revisado por outro desenvolvedor.

Ready for Test (Pronto para Teste): A funcionalidade foi desdobrada no ambiente de homologação e está aguardando o QA.

In Testing (Em Testes): O QA está executando os cenários de teste.

Done (Concluído): Funcionalidade testada, aprovada e pronta para produção.

Ciclo de Vida do Bug
New (Novo): Bug reportado pelo QA no Jira.

Triaged (Triado / Analisado): O Product Owner (PO) ou Líder Técnico valida o bug e o prioriza.

In Progress (Em Correção): O desenvolvedor está corrigindo o problema.

Ready for Retest (Pronto para Reteste): Correção aplicada no ambiente de testes.

Verifying (Validando): O QA executa o teste novamente para garantir a correção.

Closed (Fechado): Bug corrigido com sucesso e validado.

Reopened (Reaberto): Caso o bug persista após a tentativa de correção.

User Stories (Mínimo 2)
User Story 01: Autenticação de Usuário (Login)
Como cliente cadastrado na plataforma,  
Quero realizar o login informando meu e-mail e senha cadastrados,  
Para que eu possa acessar minha conta e realizar compras com segurança.

Critérios de Aceitação:

O sistema deve validar se o e-mail possui um formato válido (exemplo@dominio.com).

O campo de senha deve mascarar os caracteres digitados por segurança.

Caso os dados estejam corretos, o usuário deve ser redirecionado para a Home Logada.

Caso o e-mail ou a senha estejam incorretos, o sistema deve exibir a mensagem: "E-mail ou senha inválidos."

User Story 02: Adicionar Produto ao Carrinho
Como usuário navegando pelo e-commerce,  
Quero adicionar um produto selecionado ao meu carrinho de compras,  
Para que eu possa acumular itens e finalizar o pedido posteriormente.

Critérios de Aceitação:

Ao clicar em "Adicionar ao Carrinho", o sistema deve exibir uma notificação de sucesso: "Produto adicionado com sucesso!".

O ícone do carrinho no cabeçalho deve atualizar a quantidade de itens dinamicamente.

Se o produto estiver sem estoque, o botão "Adicionar ao Carrinho" deve ficar desabilitado com o texto "Indisponível".

Casos de Teste Step-by-Step (Mínimo 2)
CT-01: Login efetuado com sucesso (Cenário Positivo)
Pré-condições: Usuário possuir um cadastro ativo no sistema.

Passos:

Acessar a página inicial do e-commerce.

Clicar no botão "Entrar" no cabeçalho.

Digitar um e-mail válido no campo "E-mail".

Digitar a senha correspondente no campo "Senha".

Clicar no botão "Entrar".

Resultado Esperado: O usuário é autenticado com sucesso e redirecionado para a Home, exibindo o texto "Olá, [Nome]".

CT-02: Tentativa de login com senha incorreta (Cenário Negativo)
Pré-condições: Usuário possuir um cadastro ativo no sistema.

Passos:

Acessar a página inicial do e-commerce.

Clicar no botão "Entrar".

Digitar o e-mail cadastrado.

Digitar uma senha incorreta/aleatória.

Clicar no botão "Entrar".

Resultado Esperado: O sistema não realiza o login e exibe a mensagem de alerta: "E-mail ou senha inválidos."

Casos de Teste em BDD (Mínimo 2)


Cenário: Adicionar produto com estoque ao carrinho com sucesso
  Dado que o usuário está na página de detalhes de um produto com estoque disponível
  Quando o usuário clica no botão "Adicionar ao Carrinho"
  Então o sistema deve exibir a mensagem "Produto adicionado com sucesso!"
  E o contador do carrinho no cabeçalho deve incrementar em 1 unidade.
Cenário: Validar comportamento de produto esgotado
  Dado que o usuário está na página de um produto cujo estoque está zerado
  Quando a página é carregada
  Então o botão "Adicionar ao Carrinho" deve estar desabilitado
  E deve exibir o texto "Indisponível".
Mind-map da User Story 01 (Estrutura Mental)
US01: Autenticação de Usuário

Fluxo Principal (Caminho Feliz)

Login com dados válidos

Redirecionamento correto para Home

Fluxos Alternativos / Exceções

E-mail inválido (sem @ ou sem domínio)

Senha incorreta

Campos obrigatórios em branco

Usuário bloqueado por excesso de tentativas incorretas

UI / UX

Visibilidade da senha (ícone de olho para revelar texto)

Responsividade em dispositivos móveis
