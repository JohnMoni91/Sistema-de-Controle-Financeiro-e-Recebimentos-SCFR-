# Sistema de Controle Financeiro e Recebimentos (SCFR)

**Relatório de Status do Projeto - Algoritmos 1**

## 🚀 O que já está PRONTO (Implementado e Testado)

A fundação do sistema já foi construída e validada conforme as especificações do projeto:

* 
**Estruturas de Dados (Item A):** As `structs` para `Data`, `Cliente`, `Vendas` e `Parcela` foram criadas e formatadas corretamente.


* 
**Motor de Validações (Item B):** Todas as funções de validação críticas estão operacionais:


* 
`validarCPF`: Usando o cálculo real de dígitos verificadores.


* 
`validarData`: Com suporte ao calendário gregoriano e anos bissextos.


* 
`validarTelefone`: Regras de formatação (iniciar com '0') e tamanho numérico (11 ou 12 dígitos) aplicadas.


* 
`validarCartao`: Implementado usando a lógica matemática vista em aula.


* 
`validarEmail`: Verificação estrutural do '@' e dos pontos de acordo com os requisitos.




* **Cadastro de Clientes (Item C):** A função `cadastroClientes()` foi finalizada com laços de repetição. O sistema valida rigorosamente todos os dados digitados antes de permitir o armazenamento no vetor.


* 
**Busca de Clientes (Item D):** A função `buscarClientes()` permite localizar registros ativamente por CPF, Nome ou Telefone. Quando encontra, exibe a ficha completa do cliente na tela.


* 
**Geração de Parcelas (Item F):** A lógica matemática da função `geradorParcelas()` foi concluída, dividindo corretamente os valores totais e projetando os vencimentos mensais futuros.


* **Relatórios Financeiros Parciais:** Três das métricas financeiras já estão calculando os dados da estrutura de parcelas:
* Total já recebido (`recibos`).


* Total ainda a receber (`aindaReceber`).


* Total financeiro em atraso (`parcelasVencidas`).





---

## 🔧 O que foi MUDADO/LIMPO recentemente (Changelog)

Para garantir nota máxima na avaliação de organização e boas práticas de programação:

* **Correção do Bug do Enter (`\n`):** Foi adicionada a lógica de limpeza de buffer com `strlen` após as capturas com `fgets`. Isso removeu o caractere invisível que estava quebrando as validações e as buscas por *string*.
* **Limpeza de Bibliotecas Externas:** Remoção de bibliotecas que não foram testadas em aula (como `<time.h>` e `<locale.h>`). O código agora utiliza estritamente o que foi autorizado (`stdio.h`, `string.h`, `stdlib.h` e `math.h`) para evitar penalidades.


* **Documentação:** Os comentários informais e anotações de rascunho da equipe foram apagados. Mantivemos apenas os comentários oportunos que explicam a lógica técnica do sistema.


* **Correção de Escopo de Variáveis:** Corrigido o erro lógico de dupla declaração da variável `qtdClientes` na função de busca, garantindo a varredura integral do vetor global.

---

## 🎯 O que AINDA FALTA fazer (To-Do List da Equipe)

O foco agora é conectar o banco de clientes com o faturamento. Precisamos implementar os seguintes blocos lógicos:

* **[ ] Registrar Vendas (Item E):**
* Criar o corpo da função `registroVendas()`.


* 
*Regra de negócio:* A venda obrigatoriamente precisa ser atrelada a um cliente que já existe no sistema.


* 
*Regra de negócio:* Coletar o valor, definir a forma de pagamento e gerar uma prestação única para pagamentos à vista , ou chamar o `geradorParcelas()` para pagamentos a prazo, inicializando as parcelas como "Em Aberto".




* **[ ] Consultar Vendas (Item G):**
* Criar a função `consultarVendas()`.


* 
*Regra de negócio:* Permitir buscar a venda pelo seu identificador ou pelo cliente (que pode ter mais de uma compra). Exibir todos os dados da venda junto com o detalhamento das parcelas geradas.




* **[ ] Finalizar Relatórios Gerenciais:**
* Construir a função `debitosPendentes()` para listar nominalmente os clientes com parcelas vencidas.


* Construir a função `faturamentoTotal()` para somar a receita bruta geral da empresa.




* **[ ] Concluir o Menu Principal (`main`):**
* Vincular as novas funções de venda e relatórios ao nosso `switch-case` principal.
