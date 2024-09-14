
### Projeto de Consultas em Banco de Dados Relacional com MySQL

#### Descrição
Este projeto visou demonstrar habilidades na criação, manipulação e análise de dados em um banco de dados relacional utilizando MySQL. A tarefa envolveu desde a criação e popularização de tabelas até a execução de consultas básicas e avançadas, com o objetivo de obter insights valiosos a partir dos dados disponíveis.

#### Ferramentas Utilizadas
- MySQL

#### Passos Realizados

1. **Criação e Popularização de Tabelas**
   - **Tabela `clientes`**: Armazena informações detalhadas sobre os clientes, incluindo identificador único, nome, email e data de cadastro.
   - **Tabela `pedidos`**: Registra os pedidos realizados pelos clientes, incluindo identificador do cliente, valor do pedido e data do pedido. Foi estabelecida uma relação de chave estrangeira com a tabela `clientes` para garantir a integridade referencial.

   **Exemplo de Código**
   ```sql
   CREATE TABLE clientes (
       id INT AUTO_INCREMENT PRIMARY KEY,
       nome VARCHAR(100),
       email VARCHAR(100),
       data_cadastro DATE
   );

   INSERT INTO clientes (nome, email, data_cadastro) VALUES
   ('João Silva', 'joao.silva@example.com', '2024-01-15'),
   ('Maria Oliveira', 'maria.oliveira@example.com', '2024-02-20'),
   ('Carlos Souza', 'carlos.souza@example.com', '2024-03-10');
   ```

2. **Execução de Consultas SELECT**
   - Consultas foram realizadas para extrair dados específicos e gerais das tabelas criadas. Exemplos incluem a seleção de todos os registros e a filtragem por data.

   **Exemplo de Código**
   ```sql
   SELECT nome, email FROM clientes WHERE data_cadastro >= '2024-01-01';
   ```

3. **Uso de JOINs**
   - Foi realizada uma junção entre as tabelas `clientes` e `pedidos` para associar os pedidos aos respectivos clientes e obter informações combinadas, proporcionando uma visão completa das transações.

   **Exemplo de Código**
   ```sql
   SELECT c.nome, p.valor, p.data_pedido
   FROM clientes c
   JOIN pedidos p ON c.id = p.cliente_id;
   ```

4. **Utilização de Funções Agregadas**
   - Aplicação de funções agregadas como `SUM`, `AVG`, `COUNT`, `MAX` e `MIN` para análise quantitativa dos dados de pedidos. Isso permitiu calcular a soma e a média dos valores dos pedidos, bem como o total de pedidos por cliente.

   **Exemplos de Código**
   ```sql
   SELECT cliente_id, COUNT(*) AS total_pedidos
   FROM pedidos
   GROUP BY cliente_id;

   SELECT AVG(valor) AS media_pedido
   FROM pedidos;
   ```

#### Resultados
O projeto demonstrou como trabalhar com bancos de dados relacionais, realizando operações fundamentais de manipulação e análise de dados. As consultas e funções agregadas aplicadas possibilitaram uma compreensão aprofundada da relação entre clientes e seus pedidos, fornecendo insights valiosos para a tomada de decisões baseadas em dados.
