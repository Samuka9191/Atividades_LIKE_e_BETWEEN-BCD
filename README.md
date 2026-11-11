# ATIVIDADE LIKE

````
1-SELECT * FROM produto WHERE nome_produto LIKE "D%";

2-SELECT nome_produto, estoque, marca FROM produto WHERE marca LIKE "%E";

3-SELECT nome_produto, preco_unitario, marca FROM produto WHERE nome_produto LIKE "%Gamer%";

4-SELECT * FROM cliente WHERE nome_cliente LIKE "%Barbosa%";

5-SELECT cliente.nome_cliente, venda.data_venda, produto.preco_unitario, venda.forma_pagamento
FROM cliente, produto, venda WHERE nome_cliente LIKE "C%";

6-SELECT nome_produto, preco_unitario, id_venda, forma_pagamento
FROM produto
INNER JOIN venda ON produto.id_produto = venda.id_produto
WHERE (forma_pagamento = "PIX" OR forma_pagamento = "Boleto")
AND nome_produto LIKE "%Polegada%";

7-SELECT nome_produto, nome_cliente, desconto_percentual, forma_pagamento
FROM produto
INNER JOIN venda ON produto.id_produto = venda.id_produto
INNER JOIN cliente ON venda.id_cliente = cliente.id_cliente
WHERE nome_produto LIKE "%Placa%"
   OR nome_produto LIKE "%Notebook%"
   OR nome_cliente LIKE "%Ana%"
ORDER BY desconto_percentual ASC,
         forma_pagamento ASC;
````

# ATIVIDADE BETWEEN

````
1-SELECT * FROM cliente WHERE data_cadastro BETWEEN "2024-03-01" AND "2024-03-31";

2-SELECT nome_produto, marca, estoque, data_cadastro FROM produto WHERE  data_cadastro BETWEEN "2024-01-01" AND "2024-03-31";

3-SELECT * FROM cliente WHERE data_cadastro BETWEEN "2023-01-01" AND "2024-01-31";

4-SELECT nome_cliente, email, cidade, estado, data_cadastro FROM cliente WHERE data_cadastro BETWEEN "2023-06-01" AND "2023-06-15";

5-SELECT * FROM venda WHERE data_venda BETWEEN "2025-03-01" AND "2025-03-31";

6-SELECT cliente.nome_cliente, venda.data_venda, produto.preco_unitario, venda.forma_pagamento 
FROM venda,cliente,produto WHERE data_venda 
BETWEEN "2024-12-24" AND "2026-01-15" AND venda.id_cliente = cliente.id_cliente 
AND venda.id_produto = produto.id_produto
ORDER BY venda.data_venda DESC;

7-SELECT cliente.nome_cliente, cliente.email, produto.nome_produto, produto.marca, produto.categoria, venda.forma_pagamento, venda.data_venda, venda.status_venda
FROM venda, cliente, produto
WHERE data_venda BETWEEN "2025-12-01" AND "2025-12-31"
AND venda.id_cliente = cliente.id_cliente
AND venda.id_produto = produto.id_produto
AND venda.status_status IN ("Cancelada", "Concluída")
ORDER BY produto.preco_unitario DESC;
````
