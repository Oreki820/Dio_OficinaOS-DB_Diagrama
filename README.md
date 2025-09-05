# 🛠️ Projeto Oficina Mecânica - Modelo Conceitual

Bem-vindo(a) ao meu projeto de **Oficina Mecânica**, onde você poderá visualizar um **diagrama conceitual completo**, pensado para registrar clientes, veículos, ordens de serviço, equipes de mecânicos, serviços, peças e histórico de execução de forma organizada e funcional.

Este projeto foi criado para demonstrar a modelagem de dados de um **sistema de controle e gerenciamento de ordens de serviço em oficina mecânica**, desde a entrada do veículo até a conclusão dos serviços, incluindo múltiplos serviços, peças e histórico de alterações.

---

## 🎯 Objetivo do Projeto

O objetivo deste projeto é:

- Mapear o fluxo de uma oficina mecânica de forma clara e visual.  
- Criar um modelo conceitual que represente **clientes, veículos, mecânicos, equipes, ordens de serviço, serviços e peças**.  
- Registrar histórico e autorizações de execução, com controle de status detalhado.  
- Fornecer uma base para implementação real de banco de dados em **SQL** ou outras ferramentas.  
- Ajudar iniciantes a **entenderem a estrutura de um banco de dados completo para oficina**.

---

## 🗂️ Estrutura do Modelo

O modelo inclui as seguintes entidades:

### 1️⃣ Cliente
- Representa uma pessoa que leva veículos à oficina.  
- Campos principais:
  - `ID_Cliente`: Identificador único.  
  - `Nome`, `Endereco`, `Telefone` e `Email`.  
  - `Data_Criacao` e `Data_Atualizacao` para rastrear alterações.

### 2️⃣ Veículo
- Cada cliente pode possuir um ou mais veículos.  
- Campos principais:
  - `ID_Veiculo`  
  - `Placa`, `Modelo`, `Marca`, `Ano`, `Tipo`  
  - `ID_Cliente` para relacionar o veículo ao proprietário.

### 3️⃣ Mecânico
- Representa cada mecânico da oficina, podendo pertencer a uma ou mais equipes.  
- Campos principais:
  - `ID_Mecanico`, `Nome`, `Endereco`, `Especialidade`

### 4️⃣ Equipe
- Grupo de mecânicos responsáveis por executar ordens de serviço.  
- Campos principais:
  - `ID_Equipe`, `Nome_Equipe`

### 5️⃣ Ordem de Serviço (OS)
- Cada OS é criada para registrar os serviços a serem executados em um veículo.  
- Campos principais:
  - `ID_OS`, `Numero_OS`, `Data_Emissao`, `Data_Conclusao`  
  - `Status`: Aberta, Aguardando Autorização, Em Andamento, Concluída, Cancelada  
  - `Autorizado`: indica se o cliente autorizou a execução  
  - `Valor_Total`: soma dos valores de serviços e peças  
  - `ID_Veiculo` e `ID_Equipe`

### 6️⃣ Serviço
- Serviços realizados na oficina.  
- Campos principais:
  - `ID_Servico`, `Nome_Servico`, `Descricao`, `Valor_Mao_Obra`

### 7️⃣ OS_Servico
- Tabela associativa entre OS e serviços, permitindo múltiplos serviços por OS.  
- Campos principais:
  - `ID_OS`, `ID_Servico`, `Valor` (para aquela OS específica)

### 8️⃣ Peça
- Peças utilizadas nos serviços.  
- Campos principais:
  - `ID_Peca`, `Nome_Peca`, `Valor`

### 9️⃣ OS_Peca
- Tabela associativa entre OS e peças, permitindo múltiplas peças por OS.  
- Campos principais:
  - `ID_OS`, `ID_Peca`, `Quantidade`, `Valor`

### 🔟 Tabela de Referência de Mão-de-Obra
- Consulta de valores padrão de serviços.  
- Campos principais:
  - `ID_Referencia`, `Tipo_Servico`, `Valor`

### 1️⃣1️⃣ Histórico_OS
- Armazena mudanças de status da OS ao longo do tempo.  
- Campos principais:
  - `ID_Historico`, `ID_OS`, `Status_Anterior`, `Status_Novo`, `Data_Alteracao`, `Observacao`

---

## 🔗 Como visualizar o diagrama

Para explorar o **diagrama interativo completo**:

> 🌟 [📊 Diagrama Oficina Mecânica Interativo](https://dbdiagram.io/d/OficinaOS-DB_Diagrama_Dio-68ba6f8361a46d388e91c412)

Dica: você pode **clicar nas tabelas** para ver todos os campos, chaves primárias (PK) e estrangeiras (FK) de cada entidade.

---

## 🧩 Por que esse modelo é útil?

- Facilita o **entendimento do fluxo de dados** em uma oficina mecânica.  
- Permite criar **bancos de dados reais** usando SQL.  
- Registra histórico detalhado de cada OS e controle de autorizações.  
- Serve como base para sistemas completos de **gestão de oficinas**.  
- Ajuda iniciantes a **visualizar relacionamentos complexos** entre tabelas.

---

## 💡 Dica de Exploração

Mesmo que você seja iniciante:

1. Comece olhando a tabela **Cliente** e veja como se relaciona com **Veículo**.  
2. Observe que **Veículo → OS → OS_Servico/OS_Peca**, formando o fluxo de execução dos serviços.  
3. Explore a tabela **Historico_OS** para ver como os status mudam ao longo do tempo.  
4. Clique nas FKs no dbdiagram.io para entender a ligação entre todas as entidades.

---

## 🎨 Considerações finais

Esse projeto é uma **porta de entrada** para quem quer entender modelagem de dados para oficinas mecânicas de forma prática e visual.  
Com ele, você consegue visualizar **fluxo de informações**, entender **relacionamentos e regras de negócio**, e ainda preparar o terreno para **implementações reais em SQL ou sistemas web**.

---

**Bora explorar o diagrama e mergulhar no mundo da gestão de oficinas! 🚀**
