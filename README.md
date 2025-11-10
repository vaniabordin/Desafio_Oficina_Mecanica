# Desafio_Oficina_Mecanica
📌 Sistema de Controle de Ordens de Serviço — Oficina Mecânica

Desafio de Projeto:

- Este repositório apresenta a modelagem conceitual criada para um sistema de controle e gerenciamento de execução de ordens de serviço (OS) em uma oficina mecânica.

✅ Descrição do Contexto:

- Agora você irá criar um esquema conceitual do zero. A partir da narrativa fornecida você será capaz de criar todas as entidades, relacionamentos e atributos. Caso encontre algo que não foi definido na narrativa, utilize a sua compreensão do contexto e deixe uma descrição no README do seu github. para verificação.

Objetivo:

Cria o esquema conceitual para o contexto de oficina com base na narrativa fornecida
Narrativa:

•	Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica.

•	Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões  periódicas.

•	Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega.

•	A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra.

•	O valor de cada peça também irá compor a OSO cliente autoriza a execução dos serviços.

•	A mesma equipe avalia e executa os serviços.

•	Os mecânicos possuem código, nome, endereço e especialidade.

•	Cada OS possui: n°, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

A narrativa define diversos elementos essenciais para a modelagem, que foram traduzidos no modelo conceitual abaixo.

✅ Modelo Conceitual (Entidade-Relacionamento)

📍 Entidades e Atributos

- Cliente

idCliente (PK)

Nome

Telefone

Endereco

- Veículo

idVeiculo (PK)

Placa

Modelo

Ano

idCliente (FK)

- Equipe

idEquipe (PK)

Descrição

- Mecânico

CódigoMecanico (PK)

Nome

Endereço

Especialidade

idEquipe (FK)

- Ordem de Serviço (OS)

NumeroOrdem de Serviço (PK)

Data de Emissão

Data de Conclusão

Data de entrega

Valor Total

Status

idVeiculo (FK)

idEquipe (FK)

- Mão de Obra

idMão de Obra (PK)

Descricao do Serviço

Valor da Mão de Obra

- Serviço Executado OS

idServiço Executado OS (PK)

Quantidade

Valor Unitário

Valor Total

idMão de Obra (FK)

NumeroOrdem de Serviço  (FK)

- Peças

idPeça (PK)

Descrição

Valor Unitário

- Peça Utilizada no Serviço

idPeça Utilizada no Serviço (PK)

Quantidade

Valor Total

NumeroOrdem de Serviço  (FK)

idPeça (FK)

✅ Relacionamentos Principais

Cliente (1) — (N) Veículo

Veículo (1) — (N) Ordem de Serviço

Equipe (1) — (N) Mecânico

Equipe (1) — (N) Ordem de Serviço

Ordem de Serviço (1) — (N) Serviço Executado OS

Mao De Obra (1) — (N) Serviço Executado OS

Ordem de Serviço (1) — (N) Peca Utilizada no Serviço

Peça (1) — (N) Peca Utilizada no Serviço


✅ Decisões de Modelagem:

Alguns pontos precisaram ser interpretados:

Equipe foi modelada como entidade própria, pois a narrativa indica que os mecânicos trabalham em equipes e que cada veículo/Ordem de Serviço é atribuído a uma delas.

"Conserto" e "Revisão" não são tipos de OS, mas tipos de serviços, representados na tabela Mão de Obra.

