# Nome do Projeto
**Hellper Bot** - Um assistente que atua no suporte ao desenvolvedor.

## 👨‍🎓 Integrantes
- Thiago Trajano Farias
- Luiza Bruna Apolinário
- Lucas Nogueira Aiello

## 💡 Ideia Principal
Criar uma assistente de análise contextual de código que auxilie no desenvolvimento, combinando o conhecimento técnico do programador com as regras de negócio da aplicação.

## 🎯 Objetivos
- Guiar o programador no desenvolvimento de uma issue/task, explicando a regra de negócio e como ela se aplica na base de código.

## 👥 Público-Alvo
- Desenvolvedores que atuam em projetos com regras de negócio específicas, que normalmente demandam a presença de especialistas para orientar o desenvolvimento.

## 🤖 Agentes Envolvidos
- **Agente de Regra de Negócio**: Recebe, processa e interpreta dados relacionados às regras de negócio do projeto por meio de um fluxo RAG.
- **Agente Especialista em Código**: Analisa a base de código, identifica trechos relevantes e fornece orientações técnicas considerando o contexto da regra de negócio.

## 🧱 Tecnologias utilizadas
- **Langflow** – Ferramenta visual para criar e gerenciar fluxos de IA com LLMs, utilizada para implementar o pipeline de RAG e orquestrar a interação entre agentes.
- **n8n** – Plataforma de automação e orquestração de workflows, usada para integrar diferentes sistemas e disparar execuções automatizadas.
- **Ollama** – Plataforma para rodar modelos de linguagem localmente, utilizada para gerar embeddings com o modelo `nomic-embed-text`.

# Guia para Rodar o Projeto com Langflow, n8n e Ollama

## 1. Pré-requisitos
Antes de começar, você precisa ter:
- **Docker** instalado e funcionando  
- **Ollama** instalado na sua máquina  
- A pasta do repositório `projeto-aiap` clonada ou acessível  

---

## 2. Preparar o Ollama
O **Ollama** é responsável por fornecer o modelo de embeddings para o Langflow.

1. **Iniciar o servidor do Ollama**:
   ```bash
   ollama serve
   ollama pull nomic-embed-text
   ollama run nomic-embed-text


## 3. Para rodar o langflow no docker
`docker run --rm -it   --network=host   -v <path_ate_a_raiz_do_repositorio>/projeto-aiap/RAG:/app/data   -v <path_ate_a_raiz_do_repositorio>/projeto-aiap/langflow-data/flows:/app/flows   -e OLLAMA_BASE_URL=http://localhost:11434   langflowai/langflow:latest` 

## 4. Para rodar o n8n no docker
`docker run --network=host docker.n8n.io/n8nio/n8n:latest`
