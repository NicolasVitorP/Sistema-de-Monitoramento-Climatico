# 🌦 Projeto FrontEnd — Sistema de Monitoramento Climático (ClimaMaster)

Aplicação FrontEnd desenvolvida em **ReactJS** para gerenciamento de **Estações de Medição**, **Estados do Tempo** e **Registros Climáticos**, implementando **CRUDs completos**, **relacionamentos entre entidades** e **relatórios combinados** para análise de dados meteorológicos.

---

## 🌐 Deploy da Aplicação

> 🚀 **Em breve:** Deploy será realizado na Vercel

---

## 📦 Repositório do Projeto

- 🔗 **FrontEnd (ReactJS):**  
  https://github.com/seu-usuario/Sistema-De-Monitoramento-Climatico-ClimaMaster

---

## 🧭 Visão Geral do Projeto

- **Domínio:** Monitoramento Climático  
- **Entidades principais:** Estação de Medição, Estado do Tempo, Registro Climático  
- **Objetivo:** Desenvolver uma aplicação FrontEnd completa para gerenciamento de dados meteorológicos, com CRUDs funcionais, relacionamentos entre entidades e relatórios agregados.  
- **Persistência:** LocalStorage (FrontEnd)  

---

## 🧰 Tecnologias Utilizadas

### FrontEnd
- ReactJS 19.2.3  
- JavaScript (ES6+)  
- Ant Design (AntD) 6.1.0  
- React Router DOM 7.10.1  
- Leaflet & React Leaflet (visualização de mapas)
- Vite (Build Tool)  

---

# 🎯 Funcionalidades Implementadas

O projeto contempla um sistema completo de monitoramento climático com:

- ✅ CRUD de Estações de Medição (com visualização em mapa)  
- ✅ CRUD de Estados do Tempo  
- ✅ CRUD de Registros Climáticos  
- ✅ Relacionamentos entre entidades (1:N)  
- ✅ Relatório Combinado (Médias Climáticas por Estação)  
- ✅ Uso de LocalStorage para persistência de dados  
- ✅ Interface moderna com Ant Design  
- ✅ Visualização de estações em mapa interativo (Leaflet)

---

## 📋 Requisitos Funcionais (RF)

### Estações de Medição
- RF01 — Cadastrar Estação de Medição  
- RF02 — Listar Estações de Medição  
- RF03 — Visualizar detalhes da Estação (incluindo localização no mapa)  
- RF04 — Editar Estação de Medição  
- RF05 — Remover Estação de Medição  

### Estado do Tempo
- RF06 — Cadastrar Estado do Tempo  
- RF07 — Listar Estados do Tempo  
- RF08 — Editar Estado do Tempo  
- RF09 — Remover Estado do Tempo  

### Registros Climáticos
- RF10 — Cadastrar Registro Climático (vinculado a Estação e Estado do Tempo)  
- RF11 — Listar Registros Climáticos  
- RF12 — Editar Registro Climático  
- RF13 — Remover Registro Climático  

### Relatórios
- RF14 — Gerar Relatório Combinado com médias de temperatura e umidade por estação  

---

## ⚙️ Requisitos Não Funcionais (RNF)

- RNF01 — Aplicação desenvolvida em ReactJS com Vite  
- RNF02 — Interface construída com Ant Design  
- RNF03 — Persistência de dados via LocalStorage  
- RNF04 — Uso do padrão DAO para acesso aos dados  
- RNF05 — Interface responsiva para diferentes dispositivos  
- RNF06 — Validação de formulários  
- RNF07 — Código organizado por componentes, models, DAOs e pages  
- RNF08 — Feedback visual (mensagens de sucesso/erro, loaders)  
- RNF09 — Mapas interativos para visualização de estações

---

# 🖼️ Telas da Aplicação

As telas abaixo ilustram as principais funcionalidades do sistema.

### Tela 1 — Dashboard Inicial
> 📸 *Adicione aqui uma captura de tela da tela inicial*  
> Exemplo: `![Dashboard](./screenshots/tela1_dashboard.png)`

### Tela 2 — Cadastro de Estação de Medição
> 📸 *Adicione aqui uma captura de tela do formulário de cadastro de estações*  
> Exemplo: `![Cadastro Estação](./screenshots/tela2_cadastro_estacao.png)`

### Tela 3 — Listagem de Estações
> 📸 *Adicione aqui uma captura de tela da lista com as estações cadastradas*  
> Exemplo: `![Lista Estações](./screenshots/tela3_lista_estacoes.png)`

### Tela 4 — Mapa de Estações
> 📸 *Adicione aqui uma captura de tela do mapa interativo com marcadores*  
> Exemplo: `![Mapa](./screenshots/tela4_mapa_estacoes.png)`

### Tela 5 — Relatório Combinado
> 📸 *Adicione aqui uma captura de tela do relatório com médias climáticas*  
> Exemplo: `![Relatório](./screenshots/tela5_relatorio.png)`

---

# 🧠 Modelagem dos Dados

## 📌 Diagrama de Classes

O diagrama de classes abaixo representa o modelo conceitual utilizado no projeto, mostrando as entidades e seus relacionamentos.

> 📊 *Adicione aqui o diagrama UML do sistema*  
> Exemplo: `![Diagrama de Classes](./docs/diagrama_classes.png)`
> 
> **Sugestão:** Use ferramentas como [PlantUML](https://plantuml.com/), [Mermaid](https://mermaid.js.org/), ou [Draw.io](https://draw.io) para criar o diagrama.

---

## 📌 Entidades e Relacionamentos

### 1. Estação de Medição
**Campos:**
- `id` (número)
- `nome` (string)
- `latitude` (número)
- `longitude` (número)
- `cidade` (string)
- `pais` (string)

**Relacionamento:** 1:N com Registros Climáticos  
*(Uma Estação gera Muitos Registros)*

---

### 2. Estado do Tempo
**Campos:**
- `id` (número)
- `condicaoGeral` (string - Ex: "Ensolarado", "Nublado", "Chuva Forte")
- `temperatura` (número)
- `umidade` (número)
- `precipitacaoMM` (número)
- `velocidadeVento` (número)
- `iconeURL` (string - URL do ícone)

**Relacionamento:** 1:N com Registros Climáticos  
*(Um Estado do Tempo pode ser referenciado em Muitos Registros)*

---

### 3. Registro Climático
**Campos:**
- `id` (número)
- `estacaoId` (chave estrangeira → Estação de Medição)
- `estadoTempoId` (chave estrangeira → Estado do Tempo)
- `dataHora` (timestamp)
- `temperatura` (número - °C)
- `umidade` (número - %)
- `pressaoAtmosferica` (número - hPa)

**Relacionamento:**  
- N:1 com Estação de Medição  
- N:1 com Estado do Tempo

---

## 📊 Relatório Combinado

**Nome:** Médias Climáticas por Estação

**Entidades Combinadas:**
- Estações de Medição
- Registros Climáticos

**Métricas:**
- Temperatura Média por Estação
- Umidade Média por Estação
- Total de Registros por Estação

**Objetivo:**  
Identificar qual estação registrou as maiores médias de temperatura e umidade em um período, utilizando agrupamento e agregação de dados.

---

## 📂 Estrutura do Projeto

```bash
src/
├── pages/              # Páginas da aplicação (Forms e Listas)
│   ├── EstacaoForm.jsx
│   ├── EstacaoLista.jsx
│   ├── EstadoDoTempoForm.jsx
│   ├── EstadoDoTempoLista.jsx
│   ├── RegistroForm.jsx
│   ├── RegistroLista.jsx
│   └── RelatorioCombinado.jsx
├── components/         # Componentes reutilizáveis
├── models/             # Modelos de dados
│   ├── EstacaoMedicao.mjs
│   ├── EstadoDoTempo.mjs
│   └── RegistroClimatico.mjs
├── daos/               # Data Access Objects (LocalStorage)
│   ├── EstacaoMedicaoDAO.mjs
│   ├── EstadoDoTempoDAO.mjs
│   └── RegistroClimaticoDAO.mjs
├── services/           # Serviços auxiliares
├── assets/             # Recursos estáticos
├── App.jsx             # Componente principal com rotas
└── main.jsx            # Ponto de entrada da aplicação
```

---

## ▶️ Execução Local

### Instalação de Dependências

#### Instalação Completa (Recomendado)
```bash
npm install
```

#### Instalação Individual de Dependências

**Dependências de Produção:**
```bash
# Ant Design - Framework UI
npm install antd@^6.1.0

# Ícones do Ant Design
npm install @ant-design/icons@^6.1.0

# React e React DOM
npm install react@^19.2.3 react-dom@^19.2.3

# React Router para navegação
npm install react-router-dom@^7.10.1

# Leaflet - Biblioteca de mapas
npm install leaflet@^1.9.4

# React Leaflet - Componentes React para Leaflet
npm install react-leaflet@^5.0.0
```

**Dependências de Desenvolvimento:**
```bash
# Vite - Build Tool
npm install -D vite@^7.2.4

# Plugin React para Vite
npm install -D @vitejs/plugin-react@^5.1.1

# ESLint e plugins
npm install -D eslint@^9.39.1
npm install -D @eslint/js@^9.39.1
npm install -D eslint-plugin-react-hooks@^7.0.1
npm install -D eslint-plugin-react-refresh@^0.4.24

# Types (para melhor IntelliSense)
npm install -D @types/react@^19.2.7
npm install -D @types/react-dom@^19.2.3

# Globals para ESLint
npm install -D globals@^16.5.0
```

### Executar em Modo de Desenvolvimento
```bash
npm run dev
```

### Build para Produção
```bash
npm run build
```

### Preview do Build
```bash
npm run preview
```

### Lint do Código
```bash
npm run lint
```

---

## 🎨 Principais Componentes

### 1. Sistema de Rotas
- Navegação via React Router DOM
- Menu lateral responsivo com Ant Design
- Rotas protegidas e organizadas

### 2. CRUDs Completos
- Formulários com validação
- Tabelas com busca e filtros
- Operações de Create, Read, Update e Delete

### 3. Visualização de Mapas
- Integração com Leaflet
- Marcadores interativos mostrando localização das estações
- Popups com informações detalhadas

### 4. Relatórios Agregados
- Agrupamento de dados por estação
- Cálculo de médias (temperatura e umidade)
- Exportação de dados em formato tabular

---

## 👥 Autoria

- **Autor:** Nicolas Vitor Pereira Da Paz  
- **Projeto:** Sistema de Monitoramento Climático (ClimaMaster)  
- **Área:** Desenvolvimento FrontEnd  
- **Instituição:** Instituto Federal de Educação, Ciência e Tecnologia de Brasília (IFB) - Campus Taguatinga

---

## 📌 Considerações Finais

Este projeto demonstra:
- Domínio dos conceitos de CRUD e relacionamentos entre entidades
- Aplicação de padrões de projeto (DAO, Models)
- Organização de código em estrutura escalável
- Uso de bibliotecas modernas do ecossistema React
- Implementação de relatórios com dados agregados
- Interface responsiva e moderna com Ant Design
- Integração de mapas interativos para visualização geográfica

---

**Desenvolvido com ❤️ e ReactJS**
