# Desafio Consulta Vendas - DevSuperior

[![NPM](https://img.shields.io/npm/l/react)](https://github.com/devsuperior/desafio-consulta-vendas/blob/main/LICENSE) 

Este projeto é a implementação do desafio **"Consulta Vendas"** proposto no curso **Formação Desenvolvedor Moderno** da [DevSuperior](https://devsuperior.com.br).

O objetivo principal deste desafio foi aplicar conhecimentos sobre **JPA, consultas SQL e JPQL**, desenvolvendo endpoints para filtragem, relatórios e sumarização de dados a partir de um banco de dados relacional.

## 💻 Sobre o Projeto

Trata-se de uma API REST de um sistema de vendas (`Sale`) e vendedores (`Seller`). Cada venda está associada a um vendedor, e um vendedor pode ter várias vendas. 

A API disponibiliza dois recursos principais de consulta solicitados pelo desafio:
- **Relatório de vendas**: Listagem paginada de vendas filtrada por período (data inicial e final) e trecho do nome do vendedor.
- **Sumário de vendas por vendedor**: Total de vendas faturadas de cada vendedor num determinado período.

## 🛠 Tecnologias Utilizadas

- **Java**
- **Spring Boot**
- **Spring Data JPA**
- **H2 Database** (banco de dados em memória para testes/desenvolvimento)
- **Maven**

## 🚀 Como Executar o Projeto

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/desafio-consulta-vendas.git
```
2. Importe o projeto na sua IDE de preferência (IntelliJ IDEA, Eclipse, Spring Tool Suite, etc).
3. Aguarde o Maven baixar as dependências.
4. Execute a classe principal `DsmetaApplication`.

A aplicação iniciará localmente na porta `8080`. O banco de dados H2 será automaticamente inicializado com os dados de teste preexistentes no arquivo `import.sql`.

## 📌 Endpoints da API

A coleção do Postman com as requisições de teste fornecidas pela DevSuperior pode ser acessada através do link: [Postman Collection](https://www.getpostman.com/collections/dea7904f994cb87c3d).

### 1. Relatório de Vendas
Retorna uma listagem paginada das vendas em um período, podendo buscar por parte do nome de um vendedor.

**Requisição:**
`GET /sales/report?minDate={minDate}&maxDate={maxDate}&name={name}`

**Regras dos Parâmetros (todos opcionais):**
- `minDate`: Data inicial do período (formato `YYYY-MM-DD`). Se não informado, assume 1 ano antes da `maxDate`.
- `maxDate`: Data final do período (formato `YYYY-MM-DD`). Se não informado, assume a data atual do sistema.
- `name`: Trecho do nome do vendedor. Se não informado, considera texto vazio (busca todos).

### 2. Sumário de Vendas por Vendedor
Retorna o valor total das vendas agrupado por cada vendedor num respectivo período.

**Requisição:**
`GET /sales/summary?minDate={minDate}&maxDate={maxDate}`

**Regras dos Parâmetros (todos opcionais):**
- `minDate`: Data inicial do período (formato `YYYY-MM-DD`). Se não informado, assume 1 ano antes da `maxDate`.
- `maxDate`: Data final do período (formato `YYYY-MM-DD`). Se não informado, assume a data atual do sistema.

## 🤝 Agradecimentos
Ao professor [Nélio Alves](https://github.com/acenelio) e toda a equipe da DevSuperior pela excelente didática e desafios propostos para a evolução de desenvolvedores Back-end.

---
Feito com dedicação 🚀.
