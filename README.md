# 🤖 Descomplica Web 🤖

**Seu assistente para descomplicar a tecnologia!**

Projeto desenvolvido para a Imersão IA da Alura + Google Gemini (2ª Edição - Julho/2024).

## 🎯 Motivação

No mundo de hoje, a tecnologia está em toda parte, mas nem sempre é fácil de entender, especialmente para o público mais jovem que está começando a explorar além das redes sociais. Muitas vezes, conceitos básicos de informática, segurança online e o funcionamento da internet podem parecer um bicho de sete cabeças.

O "Descomplica Web" nasceu da ideia de criar um assistente virtual amigável e acessível para ajudar jovens (especialmente estudantes do ensino médio) a:
*   Entender termos técnicos de forma simples.
*   Aprender sobre segurança digital e como navegar com responsabilidade.
*   Desmistificar o funcionamento de coisas como URLs, formatos de arquivo e senhas.
*   Melhorar suas habilidades de pesquisa online.

Acreditamos que, ao tornar o conhecimento tecnológico mais palatável e menos intimidador, podemos empoderar os jovens a se tornarem usuários mais conscientes, seguros e eficazes da tecnologia.

## ✨ Funcionalidades Principais

O Descomplica Web é um chatbot inteligente que utiliza a API Google Gemini e o framework de agentes Google ADK. Ele pode te ajudar com:

*   **🤓 Agente Tira-Dúvidas Tech:** Explica termos técnicos e conceitos de informática/internet.
    *   *Ex: "O que é cache?"*
*   **🔑 Agente de Senhas:** Dá dicas para criar e gerenciar senhas fortes e seguras.
    *   *Ex: "Como faço uma senha segura?"*
*   **🔗 Agente de URLs:** Desmistifica os endereços da web, explicando cada parte de uma URL.
    *   *Ex: "O que significa https em um link?"*
*   **📂 Agente de Formatos de Arquivo:** Explica para que servem diferentes tipos de arquivos (PDF, JPG, DOCX, etc.).
    *   *Ex: "O que é um arquivo .ZIP?"*
*   **🔍 Agente de Buscas:** Oferece dicas para pesquisar melhor no Google (como através do uso de operadores) e pode até realizar buscas básicas para você.
    *   *Ex: "Como achar informações sobre a Segunda Guerra Mundial?"*
*   **🛡️ Agente de Cidadania Digital:** Dá conselhos sobre segurança online, como identificar fake news e comportamento ético na internet.
    *   *Ex: "É seguro usar meu nome real em jogos online?"*
*   **🤖 Sobre o Bot:** O próprio assistente pode te contar sobre suas capacidades!
    *   *Ex: "Quem é você?" ou "O que você pode fazer?"*

## 🛠️ Tecnologias Utilizadas

*   **Linguagem:** Python
*   **IA Generativa:** Google Gemini API (modelo `gemini-2.0-flash`)
*   **Framework de Agentes:** Google ADK (Agents Development Kit)
*   **Interface do Usuário:** Gradio

## ⚙️ Como Funciona (Arquitetura Simplificada)

1.  **Interface (Gradio):** O usuário digita uma pergunta.
2.  **Agente Roteador:** A pergunta é enviada para um agente principal (o "Roteador"), que usa o Gemini para analisar a intenção do usuário.
3.  **Agentes Especialistas:** Com base na intenção, o Roteador direciona a pergunta para um dos Agentes Especialistas (ex: AgenteDeSenhas, AgenteDeURLs). Cada agente especialista tem instruções (prompts) específicas para lidar com seu domínio de conhecimento.
4.  **Google Gemini:** Os agentes especialistas utilizam o modelo Gemini para gerar respostas informativas e no tom adequado. O AgenteDeBuscas também pode usar a ferramenta `google_search` integrada.
5.  **Resposta ao Usuário:** A resposta gerada pelo agente especialista é exibida de volta na interface Gradio.

## 🚀 Como Executar o Projeto

### Pré-requisitos

*   Python 3.9 ou superior.
*   Uma chave de API do Google Gemini. Você pode obter uma no [Google AI Studio](https://aistudio.google.com/).

### Opção 1: Rodando Localmente

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/SEU_USUARIO/NOME_DO_SEU_REPOSITORIO.git
    cd NOME_DO_SEU_REPOSITORIO
    ```
2.  **Crie um ambiente virtual (recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows: venv\Scripts\activate
    ```
3.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Configure sua chave de API:**
    *   Crie uma variável de ambiente chamada `GOOGLE_API_KEY` com o valor da sua chave.
    *   (Alternativa para desenvolvimento local, **não suba sua chave para o GitHub!**): Você pode modificar o script para ler de um arquivo `.env` usando `python-dotenv`, ou (menos seguro) colar diretamente no código para testes rápidos locais.
5.  **Execute a aplicação:**
    ```bash
    python Descomplica_web.py  # Ou o nome do seu arquivo .py principal
    ```
    A interface Gradio será iniciada e um link local (geralmente `http://127.0.0.1:7860`) será exibido no terminal.

### Opção 2: Rodando no Google Colab (Usando o arquivo `.ipynb`)

1.  Abra o arquivo `descomplica_web_colab_dev.ipynb` (ou similar) no Google Colab.
2.  Configure sua `GOOGLE_API_KEY` nos "Segredos" do Colab (ícone de chave 🔑 na barra lateral esquerda).
3.  Execute as células na ordem.
4.  A interface Gradio será iniciada e um link público (`xxxx.gradio.live`) será gerado para acesso.

## 🔮 Próximos Passos e Possíveis Melhorias

*   **Hospedagem Permanente:** Fazer deploy no Hugging Face Spaces usando `gradio deploy` para um link público estável.
*   **Melhoria Contínua dos Prompts:** Refinar as instruções dos agentes para respostas ainda mais precisas e úteis.
*   **Mais Agentes Especialistas:** Expandir para cobrir outros tópicos relevantes (ex: hardware básico, introdução à programação).
*   **Interface Mais Elaborada:** Explorar mais customizações do Gradio ou até mesmo outras ferramentas de UI.
*   **Avaliação e Feedback:** Coletar feedback de usuários jovens para iterar e melhorar a ferramenta.

## 🙏 Agradecimentos

*   À Alura e ao Google pela iniciativa da Imersão IA.
*   À comunidade de desenvolvedores pelas ferramentas e bibliotecas incríveis.

---
*Este projeto foi desenvolvido como parte de um programa educacional e é fornecido "como está", sem garantias. Use por sua conta e risco, especialmente ao lidar com informações de segurança.*
