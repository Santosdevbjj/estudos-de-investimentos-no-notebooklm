# 🧪 Engenharia de Prompts, Testes e Troubleshooting ("Cicatrizes")

Neste documento registramos o processo iterativo de construção e refinamento dos prompts para garantir respostas de qualidade industrial sem alucinações.

---

## 🔬 Matriz de Teste de Prompts

### Teste 1: Explicação do Perfil API
* **Prompt Ingenro (V1):** *"O que é API nos investimentos?"*
* **Resultado V1:** A IA explicou o conceito de *API (Application Programming Interface)* da área de tecnologia.
* **Diagnóstico:** Ambiguidade no termo "API".
* **Prompt Refinado (V2):** *"Com base nas fontes do Bradesco e Santander, o que significa a sigla API no contexto de investimentos (Análise de Perfil do Investidor) e por que ela é obrigatória antes de investir?"*
* **Resultado V2:** Resposta exata, abordando a regulação da CVM, questionário de tolerância a risco e perfil de suitability.

---

### Teste 2: Aplicação do Conceito "Margem de Segurança"
* **Prompt Ingenro (V1):** *"Como uso a Margem de Segurança do Graham?"*
* **Resultado V1:** A IA deu uma resposta genérica e teórica sem conexão prática com a renda fixa/variável de um leigo.
* **Prompt Refinado (V2):** *"Atue como um analista financeiro instruindo um leigo. Explique o conceito de Margem de Segurança de Benjamin Graham utilizando uma analogia do dia a dia (ex: construir uma ponte ou comprar um produto em promoção) e mostre como aplicar isso ao escolher um investimento seguro hoje."*
* **Resultado V2:** A IA usou a analogia da ponte calculada para suportar 10 toneladas sendo submetida a apenas 3 toneladas, fixando perfeitamente o conceito para o usuário leigo.

---

## 🛠️ Guia de Troubleshooting no NotebookLM

1. **Quando a IA trouxer fontes externas não cadastradas:**  
   * Adicione a cláusula de trava ao prompt: *"Responda utilizando EXCLUSIVAMENTE o conteúdo presente nos documentos carregados no caderno. Se a informação não estiver presente, declare que não possui dados suficentes."*
2. **Quando as respostas forem extensas demais:**  
   * Adicione a restrição de formato: *"Responda em formato de checklist com no máximo 5 tópicos de até duas frases cada."*
