# Assistente de Ensino IA com Google ADK

## Descrição do Projeto

Este projeto implementa um assistente de ensino baseado em Inteligência Artificial utilizando o Google Agent Development Kit (ADK). O objetivo é criar um tutor virtual que pode ajudar usuários a aprenderem sobre diversas matérias, fornecendo mini-aulas, exercícios básicos e respondendo a perguntas.

O assistente utiliza modelos de linguagem do Google Gemini e integra ferramentas para buscar informações, como Google Search e a capacidade de integrar busca no YouTube, para enriquecer o conteúdo didático.

## Funcionalidades (MVP - Produto Mínimo Viável)

O Produto Mínimo Viável (MVP) deste projeto demonstra as funcionalidades essenciais de um assistente de ensino interativo:

* **Seleção de Matéria:** O usuário pode iniciar uma aula sobre uma matéria específica (ex: "iniciar aula sobre Matemática").
* **Mini-Aulas:** O agente gera explicações básicas e concisas sobre tópicos fundamentais dentro da matéria escolhida.
* **Exercícios Básicos:** Geração de 1 ou 2 exercícios simples por mini-aula (como múltipla escolha ou verdadeiro/falso) diretamente relacionados ao conteúdo apresentado.
* **Correção Simplificada:** Fornecimento de feedback básico (ex: correto/incorreto) para as respostas dos exercícios.
* **Respostas a Perguntas:** O agente responde a perguntas pontuais do usuário sobre o conteúdo da matéria, utilizando seu conhecimento e ferramentas de busca.
* **Busca de Informação (Google Search):** O agente é capaz de usar a ferramenta Google Search para buscar informações adicionais que ajudem a gerar conteúdo ou responder a perguntas.
* **Placeholder para Busca no YouTube:** A estrutura para integrar a busca de vídeos educativos no YouTube está presente no código, pronta para ser implementada.

## Tecnologias Utilizadas

* Google Agent Development Kit (ADK)
* Google Gemini API (através da biblioteca `google-genai`)
* Python
* Google Colab (ambiente de desenvolvimento e execução)
* APIs do Google (para funcionalidades como Google Search e, futuramente, busca no YouTube)

## Configuração e Execução

Para configurar e executar este projeto no Google Colab, siga os passos abaixo:

1.  **Obtenha uma Chave de API para o Google Gemini:**
    * Vá para Google AI Studio ([https://aistudio.google.com/](https://aistudio.google.com/)) e obtenha uma chave de API.
    * No Google Colab, clique no ícone de chave (🔑) no painel esquerdo (Secrets).
    * Clique em "Adicionar novo Segredo".
    * Nomeie o segredo como `GOOGLE_API_KEY` e cole sua chave de API obtida.

2.  **Obtenha uma Chave de API para acesso ao YouTube (Opcional para o MVP):**
    * Será necessária uma chave de API com acesso ao YouTube Data API para implementar a funcionalidade completa de busca no YouTube. Esta chave também deve ser armazenada nos Secrets do Colab (ex: como `YOUTUBE_API_KEY`).

3.  **Prepare o Google Colab:**
    * Crie um novo notebook no Google Colab.
    * Crie células separadas para cada "Parte" do código conforme listado na seção "Estrutura do Projeto" abaixo.

4.  **Copie e Execute o Código por Partes:**
    Copie o código de cada "Parte" (conforme desenvolvido e refinado durante o processo de criação do MVP) em suas respectivas células no Colab e execute-as **sequencialmente**. Certifique-se de que cada célula execute sem erros antes de ir para a próxima.

    * **Parte 1:** Instalação e Configuração Inicial.
    * **Parte 2:** Função Auxiliar `call_agent`.
    * **Parte 3:** Definição das Ferramentas (Google Search e placeholder para YouTube).
    * **Parte 4:** Definição da classe `AgenteTutorEssencial` (instruções e ferramentas).
    * **Parte 5:** Loop principal de interação e execução do Runner.

5.  **Interaja com o Assistente:**
    Após executar todas as células, a célula da Parte 5 iniciará o loop de interação no console do Colab. Siga as instruções apresentadas.
    * Comece digitando algo como `iniciar aula sobre [nome da matéria]`.
    * Para encerrar a conversa de forma segura, digite `sair`.

## Estrutura do Projeto (Código em Células do Colab)

O código do projeto está organizado nas seguintes partes, destinadas a serem executadas em células separadas em um notebook Google Colab:

* **Parte 1:** Setup inicial do ambiente, instalação de bibliotecas e configuração das chaves de API.
* **Parte 2:** Definição da função auxiliar `call_agent` para simplificar a interação com os agentes.
* **Parte 3:** Definição das ferramentas (`Google Search` e `youtube_tool` placeholder) que o agente pode utilizar.
* **Parte 4:** Definição da classe `AgenteTutorEssencial` (instruções e ferramentas).
* **Parte 5:** O loop principal do programa que gerencia a interface do usuário, inicializa o Runner para o agente e processa as interações turno a turno.

## Próximos Passos e Aprimoramentos (Plano Integral)

Este MVP funcional serve como base para um projeto mais ambicioso. O plano integral para o Assistente de Ensino IA inclui:

* **Implementação Completa da Ferramenta YouTube:** Desenvolver a lógica na `youtube_tool` para buscar e processar dados de vídeos (títulos, descrições, transcrições) de forma eficaz para uso pelo agente.
* **Sistema Robusto de Ficha do Aluno:** Implementar um sistema de armazenamento persistente (como um banco de dados SQLite ou similar) para a "ficha do aluno", registrando progresso detalhado, tópicos concluídos, desempenho em exercícios e nível do aluno ao longo do tempo.
* **Geração e Correção de Exercícios Avançados:** Expandir a capacidade de gerar tipos de exercícios mais complexos (dissertativas, práticos, baseados em formatos específicos como ENEM) e desenvolver lógica de correção mais sofisticada.
* **Planejamento de Currículo e Aulas Estruturadas:** Permitir que o agente crie planos de estudo e aulas mais detalhadas e sequenciais com base em um currículo definido e no progresso do aluno.
* **Arquitetura Multi-Agente:** Reorganizar o projeto para utilizar múltiplos agentes especializados (por exemplo, um agente para planejamento, um para criação de exercícios, um para correção) trabalhando em conjunto.
* **Adaptação Pedagógica:** Desenvolver mecanismos para que o agente adapte seu estilo de ensino, a dificuldade do conteúdo e os exercícios com base no desempenho e nas necessidades do aluno registradas na ficha.

## Licença

Este projeto está licenciado sob os termos da Licença MIT. Consulte o arquivo `LICENSE` no repositório para detalhes completos.
