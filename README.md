
  # E-commerce Database Schema

Este projeto contém o modelo de banco de dados para um sistema de e-commerce, representado através de um diagrama entidade-relacionamento (ER). O objetivo é fornecer uma estrutura para o gerenciamento de produtos, pedidos, clientes, fornecedores e pagamentos no contexto de um e-commerce.

## Visão do Projeto

O projeto visa criar uma estrutura de banco de dados robusta para um sistema de e-commerce. Este sistema é projetado para gerenciar informações de produtos, fornecedores, clientes, pedidos e pagamentos, garantindo a integridade e consistência dos dados. A estrutura permite um controle eficiente de estoque, processos de pagamento, cadastro de clientes (tanto pessoa física quanto jurídica) e acompanhamento de ordens de serviço. O modelo foi desenvolvido para ser escalável e adaptável a novas funcionalidades, mantendo uma relação clara entre as diversas entidades do sistema.

### Ferramenta Utilizada

O diagrama ER foi criado utilizando o **MySQL Workbench**, uma ferramenta gráfica de modelagem para bancos de dados MySQL.

### Diagrama ER

Abaixo está o diagrama entidade-relacionamento (ER) do banco de dados de e-commerce:

![Diagrama ER - E-commerce](Refinando%20um%20Projeto%20Conceitual%20de%20Banco%20de%20Dados%20%E2%80%93%20E-COMMERCE.png)

## Estrutura do Banco de Dados

O banco de dados foi modelado para atender às necessidades principais de um sistema de e-commerce, incluindo gerenciamento de produtos, controle de estoque, pedidos de clientes, sistema de pagamentos e serviço de atendimento. Abaixo estão descritas as principais entidades e suas relações.

### Entidades Principais e Relações

1. **Fornecedor**
   - Representa os fornecedores de produtos.
   - Atributos:
     - `idFornecedor`: Identificador único.
     - `Razão Social`: Nome legal.
     - `CNPJ`: Cadastro Nacional de Pessoa Jurídica.

2. **Produto**
   - Representa os produtos disponíveis para venda.
   - Atributos:
     - `idProduto`: Identificador único.
     - `Categoria`: Categoria do produto.
     - `Descrição`: Descrição detalhada.
     - `Valor`: Preço do produto.

3. **Estoque Quant**
   - Controla o estoque dos produtos.
   - Atributos:
     - `Produto_idProduto`: Identificador do produto.
     - `Armazenagem_idArmazenagem`: Local de armazenamento.
     - `Quantidade`: Quantidade disponível.
     - `Estoque Quantcol`: Informação adicional sobre o estoque.

4. **Armazenagem**
   - Representa os locais de armazenamento dos produtos.
   - Atributos:
     - `idArmazenagem`: Identificador único.
     - `Local`: Localização do armazenamento.

5. **Pedido**
   - Representa os pedidos realizados pelos clientes.
   - Atributos:
     - `idPedido`: Identificador único.
     - `servico`: Tipo de serviço.
     - `descricao`: Descrição do pedido.
     - `data de solicitação`: Data do pedido.
     - `Cliente_idCliente`: Identificador do cliente.

6. **Pedido_has_Produto**
   - Relação entre pedidos e produtos.
   - Atributos:
     - `Pedido_idPedido`: Identificador do pedido.
     - `Produto_idProduto`: Identificador do produto.

7. **Ordem de Serviço**
   - Representa ordens de serviço associadas aos pedidos.
   - Atributos:
     - `idOrdem de Servico`: Identificador único.
     - `Status da OS`: Status da ordem de serviço.
     - `Pedido_idPedido`: Identificador do pedido.

8. **Cliente**
   - Representa os clientes que realizam compras.
   - Atributos:
     - `idCliente`: Identificador único.
     - `Pedido_idPedido`: Identificador do pedido (relacionado).

9. **Pessoa Física e Pessoa Jurídica**
   - Subtabelas para identificar clientes como Pessoa Física ou Jurídica.
   - Atributos (Pessoa Física):
     - `idPessoa Fisica`, `Nome`, `CPF`, `endereço`
   - Atributos (Pessoa Jurídica):
     - `idPessoa Juridica`, `Nome`, `CNPJ`, `endereço`

10. **Responsável**
    - Responsável pelo pedido ou atendimento.
    - Atributos:
      - `idResponsavel`: Identificador único.
      - `Nivel Helpdesk`, `Nome`, `departamento`

11. **Pagamento**
    - Representa os pagamentos realizados.
    - Atributos:
      - `idPagamento`: Identificador único.
      - `forma de pagamento`: Método utilizado (Cartão, Boleto, etc.).

12. **Tipos de Pagamento**
    - Pagamento com Cartão:
      - `idCartão`, `Data de Pagamento`, `Bandeira do Cartão`, `Numero do Cartão`
    - Pagamento com Boleto:
      - `idBoleto`, `Valor`, `código de barras`, `data de emissão`
    - Pagamento em Espécie:
      - `idEspecie`, `Valor`, `data de pagamento`, `Especiecol`

### Relacionamentos

- **Produto Fornecedor**: Relação entre produtos e fornecedores.
- **Pedido_has_Produto**: Relaciona os pedidos aos produtos comprados.
- **Estoque Quant**: Relaciona produtos com a quantidade em estoque e o local de armazenagem.
- **Responsável_has_Pedido**: Relaciona os responsáveis pelos pedidos.
- **Pagamento**: Contém as informações de diferentes meios de pagamento associados aos pedidos.

## Estrutura e Organização

Este esquema fornece uma visão geral de como o banco de dados de e-commerce pode ser estruturado para suportar diversas operações e funcionalidades, como:

- Cadastro e consulta de produtos e fornecedores.
- Controle de estoque e armazenagem.
- Registro de clientes, pedidos e ordens de serviço.
- Processamento de diferentes formas de pagamento.

## Como Utilizar

Este modelo pode ser implementado em um sistema de gerenciamento de banco de dados (SGBD) como MySQL, PostgreSQL, ou outros. Cada entidade e relação foi projetada para garantir a consistência e integridade dos dados do sistema de e-commerce.

<div align="center"> 
  <a href = "mailto:roberto.smj.ti@gmail.com" target="_blank"><img src="https://img.shields.io/badge/Contato-mail-8B89CC?style=for-the-badge&logo=protonmail&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/roberto-smj/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
</div>
