# Sistema Integrado de Gestão de Farmácia “Saúde & Vida”

A rede de farmácias **Saúde & Vida**, presente em diversas cidades e com unidades de portes distintos, decidiu modernizar completamente seus processos operacionais e administrativos. Embora já utilize sistemas simples para atividades pontuais, como consulta de preços e emissão de notas, a operação diária apresenta uma série de limitações: estoques divergentes entre unidades, dificuldades no registro de vendas, falhas em lançamentos financeiros e ausência de integração entre setores.

Para solucionar esses problemas, a diretoria autorizou o desenvolvimento de um **Sistema Integrado de Gestão de Farmácia**, cujo objetivo é controlar de forma centralizada todos os processos relacionados à operação cotidiana: **vendas, estoque, produtos, clientes, compras, contas a pagar, contas a receber e indicadores de desempenho**.  

O novo sistema deverá ser utilizado por atendentes, farmacêuticos, gerentes de unidade e também por setores administrativos da matriz.

---

## 1. Operação da Farmácia e Atendimento ao Cliente

No balcão, atendentes realizam vendas de medicamentos e produtos de conveniência. O processo inicia quando um cliente solicita um item, apresentando — quando necessário — receita médica. Os atendentes pesquisam produtos pelo nome, código de barras ou fabricante. Os produtos possuem características como:  
- descrição  
- preço de venda  
- unidade de medida  
- fabricante  

Uma vez encontrado o produto, o atendente informa a quantidade desejada. O sistema deve verificar se a quantidade existe no estoque daquela unidade, bem como informar valores atualizados. Caso o cliente não possua cadastro, o atendente poderá registrá-lo rapidamente, permitindo vincular compras ao seu histórico.

Alguns clientes realizam compras à vista; outros, especialmente empresas conveniadas ou clientes recorrentes, fazem compras a prazo, o que exige o registro automático em **contas a receber**, com controle de vencimentos e status (Aberta, Recebida, Atrasada).

Ao final de cada venda, o sistema deve emitir um comprovante contendo detalhes da operação.

---

## 2. Gestão de Estoque e Produtos

Cada farmácia mantém seu próprio estoque, contendo a quantidade disponível de cada produto. Os estoques nem sempre estão alinhados com as vendas, pois hoje as atualizações são feitas manualmente, o que frequentemente gera divergências.

Com o novo sistema, cada unidade deve ter seu estoque atualizado **automaticamente** após qualquer:

- venda  
- devolução  
- perda  
- transferência  
- reposição após compra  

Além disso:

- compras feitas aos fornecedores devem alimentar o estoque;  
- produtos sem estoque não podem ser vendidos;  
- o sistema deve alertar quando um produto estiver abaixo de um nível mínimo;  
- gerentes podem cadastrar novos produtos ou atualizar informações.

---

## 3. Compras e Fornecedores

A rede compra produtos de diversos fornecedores. Cada compra deve registrar:

- produto adquirido  
- quantidade  
- data  
- valor total  
- fornecedor  
- unidade da farmácia que está recebendo  

Após uma compra, o estoque da unidade deve ser atualizado e o setor financeiro deve registrar o valor correspondente em **contas a pagar**, com datas de vencimento e status (Aberta, Paga, Atrasada).

---

## 4. Contas a Pagar e Contas a Receber

O novo sistema deve permitir o acompanhamento financeiro de cada unidade.

### Contas a Receber  
Originam-se principalmente de vendas a prazo ou convênios.  
Cada lançamento deve conter:
- descrição  
- valor  
- data de vencimento  
- data de recebimento  
- status (Aberta, Recebida, Atrasada)

### Contas a Pagar  
Incluem pagamentos de fornecedores, despesas da unidade, impostos e serviços.  
Cada lançamento deve conter:
- descrição  
- valor  
- data de vencimento  
- data de pagamento  
- status (Aberta, Paga, Atrasada)

O setor financeiro deve ser capaz de consultar facilmente lançamentos em aberto, atrasados e pagos, além de gerar relatórios.

---

## 5. Relatórios e Indicadores

A matriz deseja ter acesso a relatórios como:

- produtos mais vendidos  
- estoque por unidade  
- vendas totais por dia, semana e mês  
- total comprado por fornecedor  
- contas a pagar e a receber em aberto ou vencidas  
- produtos comprados mas ainda não estocados  
- produtos que nunca foram vendidos  

Esses relatórios serão usados para decisões estratégicas e auditorias internas.

---

## 6. Perfis de Usuários e Permissões

O sistema será utilizado por diferentes perfis de usuários, cada um com funções específicas:

- **Atendente:** registra vendas, consulta produtos e identifica clientes.  
- **Farmacêutico:** valida receitas e autoriza vendas controladas.  
- **Gerente:** cadastra produtos, aprova preços e ajusta estoque.  
- **Financeiro:** controla contas a pagar/receber e gera demonstrativos.  
- **Administrador:** administra usuários, permissões e parâmetros gerais.

Cada operação possui restrições de acesso conforme a função do usuário.

---

## 7. Integração de Processos

Vários processos devem estar integrados, como por exemplo:

- **Venda** → inclui etapas de identificar cliente, consultar produto, verificar estoque, registrar itens e finalizar operação.  
- **Venda a prazo** → estende a venda comum adicionando o registro em contas a receber.  
- **Compra** → inclui atualização de estoque e lançamento em contas a pagar.  
- **Tratamento de exceções** → estoque insuficiente, produto inexistente, cliente não cadastrado etc.

Essas relações deverão ser modeladas pelos alunos utilizando **<<include>>** e **<<extend>>** quando apropriado.

---

## 8. Objetivo do Sistema

A Saúde & Vida espera que o novo sistema:

- aumente a eficiência do atendimento,  
- assegure integridade no controle de estoque,  
- reduza erros manuais,  
- integre vendas, compras e financeiro,  
- forneça dados confiáveis para tomada de decisão.

---

# Entrega do Projeto

Os alunos deverão:

1. Criar um arquivo **NOMEALUNO_RA.md** contendo toda a modelagem solicitada na avaliação, considerando o template **AVALIACAO.md** que está em /docs.  
2. Organizar o conteúdo de maneira clara e bem estruturada.  
3. Enviar o arquivo por meio de **Pull Request (PR)** no repositório da disciplina.

# Avaliação

- Regras de negócio: mínimo 5.
- Requisitos funcionais: mínimo 8.
- Requisitos não funcionais: mínimo 4.
- Casos de uso: minimo 10, sendo obrigatória a utilização de 3 includes e 3 extends. Demonstrar por meio de diagrama de casos de uso.
- Documentação de cada caso de uso (conforme template).
- Diagramas de atividade para cada caso de uso.