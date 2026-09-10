Bootcamp Bradesco - GenAI, Dados & Cyber.

<img width="106" height="120" alt="bradesco-bootcamp005" src="https://github.com/user-attachments/assets/3d7d347d-2b12-42d3-969c-2c9a386be64c" />

---

# 📈 Guia Prático de Investimentos com NotebookLM: Do Zero ao Value Investing

[![Bootcamp Bradesco](https://img.shields.io/badge/Bootcamp-Bradesco%20--%20GenAI%2C%20Dados%20%26%20Cyber-red?style=for-the-badge)](https://www.dio.me/)
[![NotebookLM](https://img.shields.io/badge/Powered%20by-Google%20NotebookLM-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://notebooklm.google.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

---

## 1. Problema de Negócio

Investidores leigos que buscam informação sobre finanças pessoais na internet aberta esbarram em três obstáculos recorrentes: **excesso de fontes contraditórias**, **jargão técnico não traduzido** e **risco real de decisões financeiras mal informadas** (aplicações inadequadas ao perfil de risco, ausência de reserva de emergência, compras por impulso especulativo).

O problema de negócio deste projeto não é "explicar investimentos" de forma genérica — é responder a uma pergunta prática: **como transformar um conjunto disperso de fontes institucionais confiáveis em um sistema de estudo confiável, consultável e sem alucinação, que um leigo consiga operar sozinho?**

---

## 2. Contexto

Este é um projeto prático do **Bootcamp Bradesco – GenAI, Dados & Cyber (DIO)**. O desafio proposto foi usar uma ferramenta de IA generativa com recuperação aumentada por contexto (RAG) — o **Google NotebookLM** — para construir um ambiente de estudo restrito a fontes confiáveis, eliminando o risco de a IA "inventar" regras financeiras ou misturar conceitos técnicos de domínios diferentes (o caso mais comum sendo a confusão entre **API financeira** — Análise de Perfil do Investidor — e **API de software**).

O público-alvo do caderno é o investidor iniciante: alguém que ainda não fez seu perfil de risco, não tem reserva de emergência e nunca ouviu falar em margem de segurança.

---

## 3. Baseline

Antes deste projeto, a forma padrão de um leigo estudar investimentos era: buscar termos isolados no Google, consumir vídeos de YouTube sem curadoria e confiar em respostas genéricas de chatbots sem controle de fonte — um processo sujeito a **contradição entre fontes**, **viés de conteúdo patrocinado** e **alucinação de IA** quando o assunto envolve fórmulas técnicas (como a Fórmula de Graham, frequentemente confundida com múltiplos genéricos de P/L).

Esse baseline informal e sem curadoria é o que a solução abaixo substitui.

---

## 4. Premissas

* As respostas do NotebookLM foram tratadas como válidas apenas quando **rastreáveis a uma fonte carregada no caderno** — qualquer resposta sem lastro documental foi descartada ou reformulada via prompt.
* O escopo do projeto é **educacional**, não é recomendação de investimento: os percentuais de alocação apresentados nos prompts são diretrizes pedagógicas, não indicação de compra de ativos.
* A curadoria priorizou fontes institucionais e primárias (Bradesco, Tesouro Direto, Nubank) sobre conteúdo de opinião, reduzindo o risco de viés.

---

## 5. Planejamento da Solução

* **Ferramenta de IA/RAG:** Google NotebookLM.
* **Fontes de conhecimento:** 31 fontes abertas (artigos institucionais + vídeos do YouTube), organizadas em 4 pilares temáticos.
* **Engenharia de prompt:** prompts estruturados com persona, restrição de fonte e formato de saída fixo, versionados e documentados com seus respectivos testes de falha.
* **Entrega:** miniguia de estudo consolidado (roteiro em 4 passos + glossário) como artefato final navegável fora do NotebookLM.

### 🏛️ Pilares da Curadoria de Fontes

1. **Fundamentos de Investimento & Value Investing** — Benjamin Graham e Warren Buffett (C6 Bank, Suno, BTG Pactual, UCLA Economics, Beyond Ben Graham).
2. **Análise de Perfil de Risco (API)** — metodologias institucionais de suitability (Bradesco, Santander, Clear, Brasilprev).
3. **Renda Fixa e Segurança** — documentação oficial do Tesouro Direto e da Bradesco Asset.
4. **Organização Financeira Prática** — gestão de carteira e planilhas (Nubank, InvestNews).

📌 Lista completa em [`docs/curadoria-de-fontes.md`](docs/curadoria-de-fontes.md), [`fontes/textos.md`](fontes/textos.md) e [`fontes/videos.md`](fontes/videos.md).

---

## 6. Decisões Técnicas e Trade-offs

**Restrição de contexto acima de liberdade generativa.** Cada prompt da pasta [`prompts/`](prompts/) inclui a instrução explícita de responder **exclusivamente** com base nas fontes carregadas no caderno. Essa foi uma escolha deliberada: abrir mão de respostas mais "criativas" do modelo em troca de respostas auditáveis e sem alucinação — trade-off aceitável em um domínio onde um erro conceitual pode gerar prejuízo financeiro real ao usuário final.

**Persona fixa nos prompts, não apenas instrução de formato.** Em vez de pedir "explique de forma simples", os prompts assumem persona ("atue como educador financeiro explicando para um jovem investindo seus primeiros R$ 100"). Essa decisão surgiu diretamente de um teste que falhou (ver seção 8) e se mostrou mais eficaz do que ajustar apenas o tom da pergunta.

**Miniguia como artefato independente do NotebookLM.** Em vez de deixar o conhecimento preso à interface do caderno, o projeto consolida um roteiro de 4 passos e um glossário em Markdown ([`docs/miniguia-de-estudos.md`](docs/miniguia-de-estudos.md)), garantindo que o valor do trabalho de curadoria sobreviva independentemente da ferramenta de IA usada.

---

## 7. Engenharia de Prompt: Testes e Cicatrizes (Troubleshooting)

O processo de refinamento de prompts revelou dois modos de falha recorrentes, documentados integralmente em [`docs/engenharia-de-prompts.md`](docs/engenharia-de-prompts.md):

| Falha identificada | Causa raiz | Correção aplicada |
|---|---|---|
| A IA explicou "API" como *Application Programming Interface* | Ambiguidade do termo fora do domínio financeiro | Prompt passou a citar explicitamente as fontes-fonte (Bradesco/Santander) e o significado esperado (Análise de Perfil do Investidor) |
| Explicação de Margem de Segurança genérica e sem aplicação prática | Prompt sem persona nem pedido de analogia | Persona de analista financeiro + exigência de analogia do cotidiano (ex: ponte projetada para 10 toneladas suportando apenas 3) |
| Mistura entre a fórmula de valor justo de Graham e múltiplos de P/L genéricos | Ausência de trava de fonte no prompt | Restrição explícita: responder apenas com as referências de BTG Pactual e Investing.com presentes no caderno |
| Respostas longas demais para o público leigo | Ausência de restrição de formato | Adição de trava de formato: checklist de até 5 tópicos, duas frases cada |

---

## 8. Resultados

A curadoria e a engenharia de prompt geraram um caderno funcional capaz de sustentar quatro entregas de estudo, documentadas em [`docs/passo-a-passo-notebooklm.md`](docs/passo-a-passo-notebooklm.md) e acessível publicamente:

```
https://notebook.google.com/notebook/e47b9a79-3c6d-4123-8ffa-532268f5eff9
```

### Miniguia de Estudo (roteiro de 4 passos)

```
[1. Teste de Perfil (API)] ──► [2. Reserva de Emergência] ──► [3. Renda Fixa Segura] ──► [4. Value Investing (Longo Prazo)]
```

1. **Diagnóstico Pessoal** — identificar o perfil (Conservador, Moderado, Arrojado) via Análise de Perfil do Investidor.
2. **Reserva de Emergência** — 3 a 6 meses de custo de vida em Tesouro Selic ou CDB com liquidez diária (100% do CDI).
3. **Mentalidade de Value Investing** — aplicar a Margem de Segurança de Benjamin Graham e tratar o mercado como "Sr. Mercado".
4. **Diversificação** — equilibrar Renda Fixa e Renda Variável conforme o perfil identificado.

📌 Glossário completo (Liquidez, Selic, CDB, Margem de Segurança, Value Investing) em [`docs/miniguia-de-estudos.md`](docs/miniguia-de-estudos.md).

---

## 9. Impacto

O ganho central deste projeto não é o caderno em si, mas a **redução do risco de decisão financeira mal informada** para o público leigo: ao restringir as respostas da IA a fontes institucionais auditáveis, o caderno elimina a principal fonte de erro observada no baseline (alucinação e mistura de conceitos técnicos), substituindo-a por um roteiro de estudo replicável em 4 passos que qualquer pessoa pode percorrer antes de aplicar o primeiro real.

Como efeito colateral direto do processo de documentação das falhas de prompt (seção 7), o projeto também produz um **playbook reaproveitável de engenharia de prompt para domínios sensíveis a alucinação** — aplicável a qualquer outro caderno de estudo que exija respostas restritas a fonte.

---

## 10. Próximos Passos

* Expandir a curadoria de fontes para produtos de Renda Variável (ações e FIIs), hoje cobertos apenas em nível conceitual via Value Investing.
* Adicionar um quinto pilar de fontes sobre tributação de investimentos para pessoa física.
* Testar a robustez dos prompts com perguntas adversariais (fora do escopo das fontes) para medir a taxa de recusa correta do modelo.
* Estruturar uma versão do miniguia em formato de quiz interativo para reforço de aprendizagem.

---

> "Para virar um resolvedor de problemas, você tem que mostrar que resolve problemas com a ferramenta, e não que apenas usa a ferramenta." — Meigarom Lopes

**Autor:** Sérgio Santos — Cientista de Dados | Ambientes Críticos e Governança de Dados

[![Portfólio Sérgio Santos](https://img.shields.io/badge/Portfólio-Sérgio_Santos-111827?style=for-the-badge&logo=githubpages&logoColor=00eaff)](https://portfoliosantossergio.vercel.app)
[![LinkedIn Sérgio Santos](https://img.shields.io/badge/LinkedIn-Sérgio_Santos-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/santossergioluiz)
