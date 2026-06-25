### Sistema de Controle Financeiro e Recebimentos (SCFR)

### Relatório de Status do Projeto - Algoritmos 1

#### 🚀 O que já está PRONTO (Implementado e Testado)

A fundação do sistema já foi construída e várias lógicas de negócio pesadas foram finalizadas:

**Estruturas de Dados (Item A):** As *structs* para Data, Cliente, Vendas e Parcela foram definidas no padrão exigido.

**Motor de Validações (Item B):** Todas as funções de validação críticas estão operacionais (CPF, Data, Telefone, Cartão de Crédito e E-mail).

**Gestão de Clientes (Itens C e D):** As funções `cadastroClientes()` e `buscarClientes()` estão implementadas e realizando as validações antes do armazenamento.

* **Registrar Vendas (Item E):** A função `registroVendas()` foi concluída. Ela vincula a venda a um cliente já existente no sistema e coleta a forma de pagamento corretamente.

**Geração de Parcelas (Item F):** A função `geradorParcelas()` consegue dividir os valores e projetar os vencimentos mensais mantendo o dia base.

**Consultar Vendas (Item G):** Implementada a visualização dos dados da venda junto com as informações de suas respectivas parcelas geradas.

**Identificar Atrasos (Item H):** A função `identificarParcelasAtraso()` varre o vetor, cruza os vencimentos com a data inserida e atualiza corretamente o status para 'Vencida'.

**Quitar Parcela (Item I):** A função localiza a próxima prestação a vencer e permite efetuar o pagamento, calculando automaticamente a multa de 2% e os juros de 0,08% ao dia em caso de atraso.

**Menu Principal:** A função `main` já suporta um menu interativo conectando a maioria das funcionalidades exigidas.

#### 🚧 O que está PENDENTE NO CÓDIGO (Atenção a Bugs)

**Erro na `liquidarDivida` (Item J):** A função foi declarada no topo e inserida na opção 7 do menu, mas **o corpo da função não foi criado**. Se rodarem a opção 7 agora, o código vai dar erro de compilação.

**Variável Lixo na Geração de Parcelas:** Dentro de `geradorParcelas()`, a variável `valorBase` está sendo usada na fórmula de juros compostos de 1% sem ter sido inicializada com um valor prévio. É necessário corrigir isso para o cálculo não puxar lixo de memória.

* **Falta de Cabeçalho:** Não se esqueçam de colocar os comentários no topo do código com a identificação dos autores. É critério de avaliação de boas práticas do professor.

#### 🎯 O que AINDA FALTA fazer (To-Do List da Equipe)

O foco agora deve ser escrever as lógicas que estão faltando e focar totalmente nos relatórios visuais que têm grande peso na nota final:

**[ ] Escrever a função `liquidarDivida()` (Item J):** Implementar a lógica que identifica uma compra, acha as parcelas e quita todas as dívidas pendentes de uma vez.

**[ ] Situação Financeira Diária (Item K):** Montar a apresentação consolidada exibindo, para cada dia, os totais de vendas realizadas, o que foi recebido, o que falta receber e as pendências.

**[ ] Situação Financeira Mensal (Item L):** Replicar a mesma lógica de relatório do item K, mas consolidando os valores organizados por mês.

* **[ ] Painel Financeiro / Dashboard (Item M):** Essa função vale 10% da nota. É preciso criar uma visualização organizada e criativa mostrando os principais indicadores financeiros da empresa separando os valores mês a mês.
