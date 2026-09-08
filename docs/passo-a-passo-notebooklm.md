# 🛠️ Passo a Passo: Criando o Caderno Prático de Investimentos no NotebookLM

Este guia descreve como montar e operacionalizar o seu ambiente de estudos dentro do NotebookLM no nível de excelência exigido para o projeto.

---

## Passo 1: Acesso e Criação do Espaço de Trabalho
1. Acesse a plataforma oficial: [notebooklm.google.com](https://notebooklm.google.com/).
2. Faça autenticação com sua conta do Google.
3. Clique no botão **`+ Criar novo caderno`** no canto superior esquerdo.
4. Clique no título padrão e altere para:  
   `Investimentos do Zero: Reserva de Emergência ao Value Investing`.

---

## Passo 2: Ingestão e Curadoria de Fontes (RAG)
O NotebookLM permite até 50 fontes por caderno. Para este projeto, utilizaremos o limite ideal de alta performance (Fontes de Texto + Canais do YouTube).

1. Na barra lateral esquerda ("Fontes"), clique em **`Adicionar fontes`**.
2. Selecione a opção **`Link / Website`** e insira sequencialmente as URLs de leitura obrigatória:
   * Portal Bradesco Investimentos (Prime e Classic).
   * Regulamento do Tesouro Direto.
   * Filosofia de Benjamin Graham (BTG / C6 Bank / Suno).
3. Selecione a opção **`YouTube`** e insira os links dos vídeos sobre fundamentos de Graham e Perfil de Investidor.
4. Aguarde a indexação do NotebookLM (ele lerá os textos e gerará as transcrições automáticas dos vídeos).

---

## Passo 3: Geração de Insights com Guia do Caderno
Após carregar as fontes:
1. No painel central, você verá o botão **`Guia do Caderno`**.
2. Clique em **`FAQ`** para que o NotebookLM gere automaticamente as 10 perguntas mais comuns respondidas pelas fontes.
3. Clique em **`Documento de Estudo`** para criar uma síntese executiva.
4. Utilize a função **`Visão Geral em Áudio (Audio Overview)`** para escutar um podcast gerado por IA discutindo as fontes carregadas.

---

## Passo 4: Execução da Engenharia de Prompts
1. Abra a caixa de bate-papo inferior.
2. Utilize os templates criados na pasta `/prompts` do repositório para interagir com o caderno.
3. Sempre fixe os "cards" de notas importantes que a IA responder clicando no ícone de alfinete (**Pin**), salvando-os no painel direito.
