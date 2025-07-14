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

### 2. Buscar por Azure Cosmos DB

- Na barra de pesquisa do portal, digite: `Cosmos DB`
- Clique em **Azure Cosmos DB**

---

### 3. Iniciar Criação de uma Instância

- Clique em **Criar**
- Escolha a opção **API do Core (SQL)** para banco NoSQL com estrutura semelhante ao JSON.

---

### 4. Preencher Informações Básicas

- **Assinatura**: Selecione a que estiver ativa
- **Grupo de recursos**: Escolha um existente ou crie um novo (ex: `lab-recursos`)
- **Nome da conta**: Escolha um nome global único (ex: `lab-cosmosdb-demo`)
- **API**: Core (SQL)
- **Localização**: Escolha uma região compatível, como `East US`, `West US 2`, `Brazil South`, etc.
- **Zonas de disponibilidade**: Pode deixar **Desabilitado** para fins de teste ou demonstração.

---

### 5. Selecionar Modo de Capacidade

- Escolha entre:
  - **Serverless** (ideal para testes, baixa demanda e uso pontual)
  - **Taxa de transferência provisionada** (para produção ou maior controle)

> Para esse caso de uso simples e educacional, selecione **Serverless**

---

### 6. Finalizar a Criação

- Clique em **Examinar + Criar**
- Aguarde a validação
- Clique em **Criar**

---

### 7. Criar o Banco de Dados e a Coleção

Após a implantação:

1. Vá até a instância criada do Cosmos DB.
2. No menu lateral, clique em **Data Explorer (Explorador de Dados)**.
3. Clique em **New Container** para criar o banco e coleção:

   - **Database ID**: `escola`
   - **Container ID**: `instrutores`
   - **Partition Key**: `/id` (ou outro campo único)
   - Marque a opção **Throughput** desmarcada (caso serverless)
   - Clique em **OK**

---

### 8. Inserir Dados

1. Clique na coleção criada (`escola > instrutores`)
2. Clique em **New Item**
3. Cole o seguinte JSON:

```json
{
  "id": "1",
  "instrutor": "Débora",
  "cursos": [
    {
      "nome": "Back End",
      "carga_horaria": 80
    },
    {
      "nome": "Administrador de Banco de Dados",
      "carga_horaria": 200
    }
  ]
}
```

### 9. Consultar Dados

1. Vá até a aba Query
2. Escreva a seguinte consulta: 
```json
SELECT * FROM instrutores
```
3. Clique em Execute Query

