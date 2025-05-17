# professor-IA
# Assistente de Ensino IA com Google ADK

## Descrição do Projeto

Este projeto implementa um assistente de ensino baseado em Inteligência Artificial utilizando o Google Agent Development Kit (ADK). O objetivo é criar um tutor virtual que pode ajudar usuários a aprenderem sobre diversas matérias, fornecendo mini-aulas, exercícios básicos e respondendo a perguntas.

O assistente utiliza modelos de linguagem do Google Gemini e integra ferramentas para buscar informações, como Google Search e um placeholder para busca no YouTube, para enriquecer o conteúdo didático.

## Funcionalidades (MVP - Produto Mínimo Viável)

* **Seleção de Matéria:** O usuário pode iniciar uma aula sobre uma matéria específica.
* **Mini-Aulas:** O agente gera explicações básicas sobre tópicos dentro da matéria escolhida.
* **Exercícios Básicos:** Geração de exercícios simples (múltipla escolha, verdadeiro/falso) relacionados ao conteúdo da mini-aula.
* **Correção Simplificada:** Feedback básico sobre as respostas dos exercícios.
* **Respostas a Perguntas:** O agente responde a perguntas gerais sobre a matéria.
* **Busca de Informação:** Utiliza a ferramenta Google Search para complementar as respostas. (Placeholder para busca no YouTube incluído, com o código para implementação).

## Tecnologias Utilizadas

* Google Agent Development Kit (ADK)
* Google Gemini API (através da biblioteca `google-genai`)
* Python
* Google Colab (ambiente de desenvolvimento)
* Google Cloud Platform (para obter chaves de API)
* YouTube Data API v3 (para futura integração de busca no YouTube)
* Biblioteca `youtube-transcript-api` (para obter transcrições de vídeos do YouTube)

## Configuração e Execução

Para configurar e executar este projeto, siga os passos abaixo no Google Colab:

1.  **Obtenha uma Chave de API do Google Gemini:**
    * Vá para Google AI Studio ([https://aistudio.google.com/](https://aistudio.google.com/)) e obtenha uma chave de API para a Gemini API.
    * No Google Colab, clique no ícone de chave (🔑) no painel esquerdo.
    * Clique em "Adicionar novo Segredo".
    * Nomeie o segredo como `GOOGLE_API_KEY` e cole sua chave de API obtida do Google AI Studio.

2.  **Obtenha uma Chave de API do YouTube Data API (Opcional para o MVP com placeholder, mas necessária para implementação completa):**
    * Vá para o Google Cloud Console ([https://console.cloud.google.com/](https://console.cloud.google.com/)).
    * Crie um novo projeto ou selecione um existente.
    * No menu de navegação, vá para "APIs e Serviços" > "Biblioteca".
    * Procure por "YouTube Data API v3" e clique em "Ativar".
    * Vá para "APIs e Serviços" > "Credenciais".
    * Clique em "Criar Credenciais" > "Chave de API".
    * Copie a chave de API gerada.
    * No Google Colab, no mesmo painel de Secrets, adicione um novo segredo chamado `YOUTUBE_API_KEY` e cole esta chave.

3.  **Execute os Blocos de Código no Google Colab:**
    Copie e cole o código de cada "Parte" que desenvolvemos em células separadas no seu notebook Colab e execute-as na seguinte ordem:

    * **Parte 1: Instalação e Configuração Inicial (Corrigida Novamente):** Instala as bibliotecas e configura as chaves de API a partir dos Secrets.
    * **Parte 2: Função Auxiliar `call_agent`:** Define a função que auxilia na interação com o agente.
    * **Parte 3: Definição das Ferramentas (Tools):** Define as ferramentas disponíveis para o agente (Google Search e placeholder para YouTube Tool). *Se você implementou a `youtube_tool` real, use esse código*.
    * **Parte 4: Definição do Agente Tutor Essencial (`AgenteTutorEssencial`) (Refatorada):** Define a classe principal do agente com suas instruções e ferramentas. *Lembre-se de adicionar `youtube_tool` à lista `self.tools` se você a implementou na Parte 3 e atualizar a string `self.instruction` para guiar o agente a usar as ferramentas.*
    * **Parte 5: Loop de Interação Principal (Antes da Persistência):** Este é o loop principal que interage com o usuário e o agente.

4.  **Interaja com o Assistente:** Após executar todas as células necessárias, a célula da Parte 5 iniciará o loop de interação. Siga as instruções no console para interagir com o assistente. Digite "sair" para encerrar a conversa de forma segura.

## Estrutura do Projeto (Código em Células)

O código do projeto está organizado nas seguintes partes (em células do Colab):

* **Parte 1:** Setup inicial, instalação de bibliotecas, configuração de API Keys.
* **Parte 2:** Função auxiliar `call_agent`.
* **Parte 3:** Definição das Tools (Google Search, placeholder ou implementação de YouTube Tool).
* **Parte 4:** Definição da classe `AgenteTutorEssencial` (instruções, tools).
* **Parte 5:** Loop principal de interação, inicialização do Runner e gerenciamento da conversa.

## Próximos Passos e Aprimoramentos (Plano Integral)

Este MVP é um ponto de partida. O plano integral do projeto inclui funcionalidades mais avançadas:

* Implementação completa da busca e uso de conteúdo de vídeos do YouTube.
* Sistema robusto de "Ficha do Aluno" com armazenamento persistente de progresso detalhado, notas, exercícios concluídos, etc., possivelmente usando um banco de dados.
* Geração e correção de exercícios mais variados e complexos (dissertativas, práticos).
* Planejamento de grade curricular e geração de aulas mais estruturadas.
* Implementação da arquitetura de múltiplos agentes (Formulador de Plano de Aula, Elaborador de Exercícios, Professor) para orquestrar o fluxo de ensino.
* Mecanismos mais sofisticados de adaptação ao nível e estilo de aprendizado do aluno.

## Licença

[Considere adicionar uma licença de código aberto, como MIT ou Apache 2.0]
