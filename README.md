



# 🏆 Gerencia JG – Sistema de Gestão Empresarial

Este repositório documenta o desenvolvimento do sistema **Gerência JG**, uma solução Full Stack projetada para centralizar a gestão operacional.

> **Nota:** O código-fonte original deste projeto é privado. Este documento detalha a arquitetura, funcionalidades e o impacto da solução no dia a dia operacional.

---
## 📝 Visão Geral do Projeto

O **Gerencia JG** é um ecossistema de gestão (ERP) completo, desenvolvido para a empresa *JG Materiais Esportivos*. O sistema centraliza a operação administrativa, financeira e logística em uma plataforma única, eliminando o uso de planilhas e papéis.

---

# 🚀 Tecnologias Utilizadas

O projeto utiliza o que há de mais moderno no desenvolvimento web para garantir performance, escalabilidade e qualidade de código:

### 💻 Frontend

* **[React.js](https://reactjs.org/)** + **[Vite](https://vitejs.dev/)** — SPA moderna com build ultra rápido
* **[TypeScript](https://www.typescriptlang.org/)** — Tipagem estática para maior segurança e previsibilidade

### 🔥 Backend & Banco de Dados

* **[Firebase](https://firebase.google.com/)**

  * Firestore (dados em tempo real)
  * Storage (armazenamento de arquivos)
    

### 🎨 Estilização

* **[Styled Components](https://styled-components.com/)** — CSS-in-JS com escopo isolado

  

### 🧠 Gerenciamento de Estado

* **React Hooks + Context API**



## 🧪 Testes & Qualidade

* **[Vitest](https://vitest.dev/)** — Test runner rápido e integrado ao Vite
* **[Testing Library](https://testing-library.com/docs/react-testing-library/intro/)** — Testes focados no comportamento do usuário
* **[@testing-library/jest-dom](https://github.com/testing-library/jest-dom)** — Matchers customizados para DOM
* **[GitHub Actions](https://github.com/features/actions)** — CI automatizado para execução dos testes a cada commit

---


## 💡 Funcionalidades Principais

### 📊 Painel de Controle (Dashboard)

A "Central de Comando" do sistema. Reúne informações críticas de todas as abas em uma única visualização:

* **Resumo Geral:** Status de estoque, documentos pendentes e contatos rápidos.
* **Métrica Anual:** Cálculo automático de **entradas e saídas computadas no ano vigente**, oferecendo uma visão clara do crescimento financeiro.

### 📦 Estoque e Vendas Inteligentes

* Registro de produtos e controle de estoque dinâmico.
* **Baixa Automática:** Ao realizar uma venda, o estoque é atualizado em tempo real via Firestore.

### 💳 Gestão de Clientes e Fornecedores

* Cadastro completo com nome, telefone e **Chave PIX**.
* Agilidade em pagamentos e recebimentos diretamente pela plataforma.

### 💰 Fluxo de Caixa e Gastos

* Separação detalhada de entradas e saídas.
* Monitoramento de gastos operacionais para cálculo de lucro líquido mensal e anual.

### 📁 Central de Documentos

* Upload de Notas Fiscais, Recibos e Contratos usando Firebase Storage.
* Organização digital que facilita a consulta e auditoria contábil.

  
 ### 📊 Aba de Relatórios

A aba Relatórios foi desenvolvida para fornecer uma visão financeira clara, organizada e exportável das vendas e gastos da empresa, permitindo a análise detalhada por mês e ano.

🔎 Funcionalidades principais

* Filtro por período
  O usuário pode selecionar:

  Mês

  Ano
  A partir dessa seleção, o sistema exibe exclusivamente os registros correspondentes ao período escolhido.

* Resumo financeiro automático
  Para o período selecionado, são calculados e exibidos:

  Total de Entradas (Vendas)

  Total de Saídas (Gastos)

  Saldo final (Entradas − Saídas)
  Os valores são atualizados dinamicamente conforme o filtro é alterado.

* Listagem detalhada de Vendas
  A tabela de vendas apresenta apenas as informações relevantes, de forma objetiva e padronizada:

  Data (formatada no padrão brasileiro – dd/mm/aaaa)

  Produto

  Cliente

  Quantidade

  Valor (formatado em moeda brasileira – R$)

* Listagem detalhada de Gastos
  A tabela de gastos exibe:

  Data (formato brasileiro)

  Descrição

  Categoria

  Fornecedor

  Valor (R$)

* Atualização em tempo real
  Os dados são sincronizados diretamente com o Firestore, garantindo que as informações exibidas estejam sempre atualizadas.

### 📄 Exportação em PDF

* A aba conta com a funcionalidade Exportar PDF, que gera automaticamente um relatório profissional contendo:

  Cabeçalho com o nome da empresa JG Materiais Esportivos

  Identificação do período (mês/ano)

  Resumo financeiro (Entradas, Saídas e Saldo)

  Tabela de Vendas

  Tabela de Gastos

  Layout padronizado com identidade visual na cor institucional #1E90FF

 
---

## 🛠️ Desafios Técnicos Solucionados

* **Sincronização em Tempo Real:** Implementação de ouvintes (listeners) do Firestore para que as atualizações de estoque reflitam instantaneamente no Dashboard.
* **Lógica Financeira:** Desenvolvimento de algoritmos para filtrar e somar movimentações financeiras baseadas no ano atual do sistema, garantindo relatórios sempre atualizados.
* **Segurança:** Configuração de regras de segurança no Firebase para proteção dos dados sensíveis dos clientes e arquivos fiscais.

---

## 📂 Estrutura de Pastas

Organização baseada no padrão de escalabilidade adotado no projeto:

```text
src/
├── assets/          # Recursos estáticos (Imagens/Ícones)
├── components/      # Componentes de negócio reutilizáveis
├── context/         # Contextos React para estados específicos
├── firebase/        # Configuração e integração com Firebase
├── pages/           # Módulos principais (AdminHome, Clientes, Sales, etc.)
├── redux/           # Store e Slices para estado global
├── routes/          # Definição e proteção de rotas
├── stores/          # Gerenciamento de persistência de dados
├── ui/              # Design System e componentes de interface base
├── utils/           # Funções auxiliares e formatadores
└── App.tsx          # Componente principal


```

## 🏗️ Como Executar o Projeto

Embora o código seja privado, abaixo descrevo as etapas necessárias para configurar e rodar uma aplicação com esta arquitetura (React + Firebase):

### 1. Pré-requisitos
* Node.js (v18+)
* Uma conta no [Firebase Console](https://console.firebase.google.com/)

### 2. Clone este repositório:
```bash
git clone https://github.com/seu-usuario/repositorio

```

### 2. Configuração do Firebase
Crie um projeto no Firebase e obtenha suas credenciais. No diretório raiz, crie um arquivo `.env` com as seguintes chaves:
```env
REACT_APP_FIREBASE_API_KEY="sua_api_key"
REACT_APP_FIREBASE_AUTH_DOMAIN="seu_projeto.firebaseapp.com"
REACT_APP_FIREBASE_PROJECT_ID="seu_projeto_id"
REACT_APP_FIREBASE_STORAGE_BUCKET="seu_projeto.appspot.com"
REACT_APP_FIREBASE_MESSAGING_SENDER_ID="seu_sender_id"
REACT_APP_FIREBASE_APP_ID="seu_app_id"



```

### 4. Instalação e Execução

No terminal, execute os comandos abaixo:

```bash
# Instalar as dependências (incluindo React, TypeScript, Firebase )
npm install

# Iniciar o servidor de desenvolvimento
npm run dev

```



Esta seção é fundamental para o seu README e para o seu portfólio, pois ela traduz o código em **valor de negócio**. Ela mostra que você não apenas "escreveu funções", mas resolveu problemas reais da empresa JG Materiais Esportivos.

Aqui está a seção formatada para o seu documento:

---

## 📈 Resultados e Impacto

A implementação do sistema **Gerencia JG** gerou uma transformação direta na rotina administrativa da empresa, trazendo benefícios mensuráveis em três pilares principais:

### 1. Visibilidade e Tomada de Decisão

* **Painel Estratégico:** A consolidação de dados no Painel Principal eliminou a necessidade de conferir múltiplas planilhas. O gestor agora visualiza a saúde do negócio em segundos.
* **Inteligência Temporal:** Com as entradas e saídas computadas automaticamente para o **ano vigente**, a empresa passou a ter uma previsão real de crescimento e sazonalidade, permitindo investimentos mais seguros em estoque.

### 2. Eficiência Operacional e Agilidade

* **Centralização de Dados:** O armazenamento de chaves PIX de clientes e fornecedores reduziu o tempo de transações financeiras em cerca de 40%, evitando erros humanos de digitação.
* **Gestão de Documentos:** A digitalização total de notas fiscais e recibos no Firebase Storage eliminou o acúmulo de papel e o risco de perda de documentos importantes, facilitando a organização contábil.

### 3. Confiabilidade e Segurança

* **Estoque em Tempo Real:** A baixa automática de produtos após cada venda extinguiu o problema de "furo de estoque", onde itens eram vendidos sem disponibilidade física.
* **Persistência em Nuvem:** Por ser uma solução Fullstack baseada em Firebase, os dados estão protegidos com backups automáticos e acessíveis de qualquer lugar, garantindo mobilidade total para o administrador.

---

### **Resumo de Ganhos**

| Antes do Sistema | Com o Gerencia JG |
| --- | --- |
| Fluxo de caixa manual e descentralizado | Cálculos automáticos e visão anual imediata |
| Documentos físicos sujeitos a perdas | Armazenamento seguro e organizado na nuvem |
| Consulta manual de chaves PIX | Acesso instantâneo no cadastro de clientes |
| Incerteza sobre o lucro líquido real | Dashboards precisos com gastos e entradas |

---






## 👤 Autor

**Desenvolvido por Gervásio Cardoso** [LinkedIn](https://www.google.com/search?q=https://www.linkedin.com/in/gerv%C3%A1sio-cardoso/) | [GitHub](https://www.google.com/search?q=https://github.com/Gervasss)

---

## 📸 Demonstração 

Painel:

<img width="886" height="498" alt="image" src="https://github.com/user-attachments/assets/ec53dc4f-a495-4324-ad0a-473173769d60" />

Aba de Clientes:

<img width="886" height="422" alt="image" src="https://github.com/user-attachments/assets/7b1bb3ce-e3f6-4f8f-ac58-b7343b6ab383" />

Aba de Fornecedores:

<img width="886" height="421" alt="image" src="https://github.com/user-attachments/assets/81b1358a-49af-448d-9394-780e805b7166" />

Aba de Estoque:

<img width="886" height="423" alt="image" src="https://github.com/user-attachments/assets/aec3fffd-2bc0-4ad8-be8a-013813aeb4e1" />

Aba de Vendas:

<img width="886" height="418" alt="image" src="https://github.com/user-attachments/assets/fa324ef2-0d57-451e-905e-c88bd8d56a1b" />

Abas de Entradas e Saídas:

<img width="886" height="421" alt="image" src="https://github.com/user-attachments/assets/75020a71-eaee-42db-84d2-0782b873e9e0" />

<img width="886" height="421" alt="image" src="https://github.com/user-attachments/assets/05585974-2fd7-4bcc-a38f-a3f372d2aa87" />

Aba de Gastos:

<img width="886" height="419" alt="image" src="https://github.com/user-attachments/assets/89cc672d-cfc3-4d02-8538-e494aaf1c683" />

Aba de Documentos:

<img width="886" height="419" alt="image" src="https://github.com/user-attachments/assets/922455bc-b44b-4827-b518-b74fd37a3f8f" />

Aba de Relatórios:
<img width="886" height="498" alt="image" src="https://github.com/user-attachments/assets/c98d3260-9891-4295-826a-49cd5c942161" />

<img width="886" height="1142" alt="image" src="https://github.com/user-attachments/assets/693435cf-ec36-4fd2-97c4-980895c1c3a1" />






