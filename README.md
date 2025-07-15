# Criando uma Instância do Azure Cosmos DB (API NoSQL)

Este repositório apresenta um guia passo a passo para criar uma instância do **Azure Cosmos DB com API para NoSQL**, ideal para aplicações que trabalham com dados não relacionais como documentos JSON.

---

## ✅ Objetivo

Guiar a criação de um banco NoSQL na nuvem com o **Azure Cosmos DB**, permitindo futuras integrações com aplicações e testes de persistência de dados.

---

## 🧭 Etapas

### 1. Acessar o Portal do Azure

- Acesse: [https://portal.azure.com](https://portal.azure.com)
- Faça login com sua conta Microsoft.

---

## 2. Criar um Grupo de Recursos

<img width="706" height="631" alt="image" src="https://github.com/user-attachments/assets/8866f2f2-07b8-4abc-91bc-ca239a7e4edd" />

Antes de criar o Azure Cosmos DB, é **necessário criar um Grupo de Recursos**. Isso evita erros relacionados à localização durante a criação.

- No Portal do Azure, clique em **Grupos de recursos** no menu lateral esquerdo.
- Clique em **+ Criar**.
- Em **Assinatura**: Selecione sua assinatura ativa (ex: `Azure for Students` ou `Azure subscription 1`)
- Em **Nome do grupo de recursos**: escolha um nome (ex: `lab-cosmosdb`)
- Em **Região**: selecione `West US 2`
- Clique em **Revisar e criar**.
- Clique em **Criar** para finalizar.

> ⚠️ Importante: criar o grupo de recursos antes evita erros de incompatibilidade de localização durante a criação do Cosmos DB.


### 2. Buscar por Azure Cosmos DB

<img width="1051" height="278" alt="cdb" src="https://github.com/user-attachments/assets/5139ea5a-eee7-4cc5-8561-a3aba7b55121" />

- Na barra de pesquisa do portal, digite: `Azure Cosmos DB`
- Clique em **Azure Cosmos DB**
- Na tela principal do Azure Cosmos DB, clique em **Criar**

---

### 3. Iniciar Criação de uma Instância

<img width="877" height="473" alt="nosql" src="https://github.com/user-attachments/assets/7cb5c428-f98a-448d-91a2-d280311e1ec0" />

- Na tela **Create an Azure Cosmos DB account**, em *Recommended APIs*, escolha a opção **Azure Cosmos DB for NoSQL**.
- Clique em **Create**.
- Em **Workload Type**, selecione Learning.
- **Assinatura**: Selecione sua assinatura ativa (ex: `Azure for Students` ou `Azure subscription 1`)
- **Grupo de recursos**: Selecione um existente (ex: `lab-cosmosdb`) ou clique em **Criar novo**
- **Nome da conta**: Escolha um nome global único (ex: `exemplo-cosmosdb`)
- **Availability Zones**: Pode deixar **Desabilitado** para fins de teste ou demonstração
- **Localização**: Escolha uma região próxima ou mais barata (ex: `East US 2`)
- **Modo de capacidade**: Escolha **Serverless** (ideal para testes, baixa demanda e uso pontual)
- Clique em **Examinar + Criar**
- Aguarde a validação
- Clique em **Criar**
- Uma mensagem de **A implantação foi concluída** deve ser exibida ao final do processo
- Após isso clique em **Ir para o recurso**

---

### 4. Criar o Banco de Dados e a Coleção

<img width="1342" height="433" alt="dataexplorer" src="https://github.com/user-attachments/assets/84b0892c-9f18-4309-856c-9c5a9785b69d" />

- No menu lateral, clique em **Data Explorer (Explorador de Dados)**.
- Clique em **New Container** para criar o banco e a coleção.
- Em **Database ID**, marque a opção **Create new** e defina o nome do banco (ex: `alocacao`).
  > 💡 *Caso já tenha um banco criado, selecione a opção **Use existing** e escolha o banco desejado.*
- Em **Container ID**, digite o nome da coleção (ex: `instrutores`).
- Em **Partition key**, defina uma chave de partição (ex: `/id`).
- Clique em **OK** para finalizar a criação.

---

### 5. Selecionando o Ambiente de Dados

<img width="963" height="437" alt="items" src="https://github.com/user-attachments/assets/a41f26f6-1f68-4d26-9eb7-7aee8a0296bd" />

- No menu lateral, clique no banco de dados criado (ex: `alocacao`).
- Em seguida, clique na coleção (ex: `instrutores`).
- Clique em **Items**.
- Depois, clique em **New Item** para adicionar um novo documento.

### 6. Inserindo os Dados

<img width="1077" height="518" alt="image" src="https://github.com/user-attachments/assets/82af221d-65db-4972-9267-f581efcf89cf" />

- Clique na coleção criada (ex: `alocacao`)
- Clique em instrutores
- Clique em Items
- Clique em **New Item**
- Cole o seguinte JSON:

```json
{
  "instrutor": "Mikasa",
  "cursos": [
    {
      "nome": "Back End",
      "carga_horaria": 80
    },
    {
      "nome": "Front End"
    }
  ]
}
```
- Clique em **Save** para adicionar o primeiro registro
- Clique novamente em **New Item**
- Cole o seguinte JSON:

```json
{
  "instrutor": "Eren"
}
```
- Clique em **Save** para adicionar o segundo registro
- Após isso baste clicar em **Apply Filter** para visualizar os registros criados


