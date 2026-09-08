Bootcamp Bradesco - GenAI, Dados & Cyber.

<img width="106" height="120" alt="bradesco-bootcamp005" src="https://github.com/user-attachments/assets/3d7d347d-2b12-42d3-969c-2c9a386be64c" />


---

# 📈 Guia Prático de Investimentos com NotebookLM: Do Zero ao Value Investing

[![Bootcamp Bradesco](https://img.shields.io/badge/Bootcamp-Bradesco%20--%20GenAI%2C%20Dados%20%26%20Cyber-red?style=for-the-badge)](https://www.dio.me/)
[![NotebookLM](https://img.shields.io/badge/Powered%20by-Google%20NotebookLM-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://notebooklm.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

> **Projeto Prático do Bootcamp Bradesco - GenAI, Dados & Cyber (DIO)**  
> **Objetivo:** Capagitar investidores iniciantes/leigos a tomarem decisões financeiras corretas, seguras e fundamentadas através do aprendizado ativo utilizando a Inteligência Artificial do Google (NotebookLM).

---

## 🎯 1. Contexto e Objetivos

O universo dos investimentos financeiros muitas vezes parece inacessível para quem está começando devido a termos técnicos complexos, excesso de informações contraditórias e o risco de perdas financeiras por falta de conhecimento.

Este projeto aplica a metodologia de **Aprendizagem Ativa auxiliada por IA** para construir um **Caderno Temático no NotebookLM** focado em educação financeira para iniciantes. A partir da curadoria de fontes oficiais e consagradas (Bradesco, Tesouro Direto, Nubank e os princípios fundamentais de Benjamin Graham / Value Investing), estruturamos um roteiro completo de aprendizado seguro e eficiente.

### Objetivos do Projeto:
* **Mapear o Perfil do Investidor:** Entender a tolerância ao risco e objetivos individuais (Conservador, Moderado, Arrojado).
* **Construir Reserva de Emergência:** Utilizar instrumentos de liquidez e segurança como o Tesouro Selic.
* **Compreender o Value Investing (Investimento em Valor):** Dominar os conceitos de Margem de Segurança e Análise Fundamentalista de Benjamin Graham.
* **Diversificação e Gestão de Carteira:** Estruturar alocações equilibradas e simples para leigos.

---

## 📚 2. Curadoria de Fontes

Foram selecionadas **31 fontes abertas** de alta credibilidade para alimentarem a base de conhecimento (RAG) do NotebookLM, organizadas em 4 pilares:

1. **Fundamentos de Investimento & Value Investing:** Conceitos de Benjamin Graham e Warren Buffett (*C6 Bank, Suno, BTG Pactual, UCLA Economics, Beyond Ben Graham*).
2. **Análise de Perfil de Risco (API):** Metodologias institucionais de adequação (*Banco Bradesco, Santander, Clear, Brasilprev*).
3. **Produtos de Renda Fixa e Segurança:** Documentação oficial do *Tesouro Direto* e produtos do *Bradesco/Bradesco Asset*.
4. **Organização Financeira e Prática:** Orientações de gestão de carteira e planilhas (*Nubank, InvestNews*).

📌 *A lista completa e detalhada dos links encontra-se no arquivo [`docs/curadoria-de-fontes.md`](docs/curadoria-de-fontes.md).*

---

## 🧠 3. Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Para obter respostas de alta fidelidade e sem "alucinações", foram desenvolvidas estratégias de prompt direcionadas, utilizando técnicas como **System Prompting**, **Few-Shot Prompting** e **Restrições de Contexto**.

### Exemplo de Prompt de Risco x Retorno:
> **Prompt:** *"Com base estritamente nas fontes sobre o Banco Bradesco e Tesouro Direto fornecidas, explique para uma pessoa leiga o que é a Reserva de Emergência, onde ela deve ser aplicada e qual a diferença entre taxa Selic e IPCA. Não utilize termos técnicos sem explicá-los em seguida."*

### ⚠️ Cicatrizes e Desafios Encontrados (Troubleshooting):
* **Problema de Alucinação Teórica:** Ao perguntar livremente sobre a "Fórmula de Graham", o modelo misturava a fórmula de valor justo ($VI = \sqrt{22.5 \times LPA \times VPA}$) com métricas genéricas de P/L.
  * **Solução:** Restringimos a busca adicionando a instrução explícita: *"Responda utilizando **apenas** as referências do texto do BTG Pactual e Investing.com sobre Graham presentes no caderno."*
* **Linguagem Muito Rebuscada:** Respostas iniciais utilizavam jargões como *"duration decorrelacionada"* e *"marcação a mercado"*, o que assustava o público leigo.
  * **Solução:** Adicionamos personas nos prompts: *"Atue como um educador financeiro didático explicando para um jovem de 18 anos que vai investir seus primeiros R$ 100."*

📌 *Confira o diário completo de testes em [`docs/engenharia-de-prompts.md`](docs/engenharia-de-prompts.md).*

---

## 📖 4. Miniguia de Estudo (Entrega Final)

### 🔹 Resumo Estruturado dos Pilares Financeiros
1. **Passo 1: Diagnóstico Pessoal** — Antes de investir R\$ 1,00, descubra se seu perfil é Conservador, Moderado ou Experiente/Arrojado através da Análise de Perfil do Investidor (API).
2. **Passo 2: A Fortaleza Financeira** — Construa sua **Reserva de Emergência** equivalente a 6 meses do seu custo de vida no Tesouro Selic ou CDB com liquidez diária (100% do CDI).
3. **Passo 3: A Mente do Investidor de Valor** — Aplique a lição de **Benjamin Graham**: traste o mercado financeiro como um parceiro de negócios ("Sr. Mercado") e compre ativos apenas quando houver **Margem de Segurança** (preço abaixo do valor intrínseco).
4. **Passo 4: Diversificação Inteligente** — Divida seus investimentos entre Renda Fixa (segurança/previsibilidade) e Renda Variável (crescimento no longo prazo).

### 📖 Glossário Essencial para Leigos
* **Liquidez:** A facilidade e rapidez com que você consegue transformar um investimento de volta em dinheiro na sua conta.
* **Taxa Selic:** A taxa básica de juros da economia brasileira. Define o rendimento de aplicações de renda fixa seguras.
* **CDB (Certificado de Depósito Bancário):** Um "empréstimo" que você faz para o banco em troca de render juros diários ou mensais.
* **Margem de Segurança:** Comprar uma ação por um preço consideravelmente menor do que ela realmente vale, minimizando o risco de perda.
* **Value Investing:** Filosofia de investimento focada em comprar boas empresas por preços descontados e mantê-las no longo prazo.

📌 *Veja o glossário expandido e resumos em [`docs/miniguia-de-estudos.md`](docs/miniguia-de-estudos.md).*

---

## 🚀 5. Como Usar o NotebookLM (Passo a Passo)

1. Acesse o [NotebookLM do Google](https://notebooklm.google.com/) e faça login com sua conta Google.
2. Clique em **"Novo Caderno"** e nomeie como `Investimentos para Iniciantes - Value Investing`.
3. Adicione as fontes listadas na pasta [`fuentes/`](fuentes/). Copie as URLs e insira na opção "Website" ou "YouTube".
4. Copie os prompts prontos da pasta [`prompts/`](prompts/) para realizar suas consultas.
5. Gere resumos automáticos em áudio (Audio Overview) e mapas conceituais diretamente na interface.

📌 *Guia de configuração com capturas conceituais em [`docs/passo-a-passo-notebooklm.md`](docs/passo-a-passo-notebooklm.md).*

---


   
**Autor:** Sérgio Santos — Cientista de Dados | Ambientes Críticos e Governança de Dados

[![Portfólio Sérgio Santos](https://img.shields.io/badge/Portfólio-Sérgio_Santos-111827?style=for-the-badge&logo=githubpages&logoColor=00eaff)](https://portfoliosantossergio.vercel.app)
[![LinkedIn Sérgio Santos](https://img.shields.io/badge/LinkedIn-Sérgio_Santos-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/santossergioluiz)
