# Pipeline RAG com Milvus & Llama-3: Análise do AI Act 🤖📚

Este repositório contém um notebook desenvolvido para a implementação de um sistema de **Recuperação Aumentada por Geração (RAG)**. O projeto utiliza o banco de dados vetorial **Milvus** e modelos de linguagem de grande escala (LLMs) via **Hugging Face** para realizar consultas inteligentes em documentos técnicos, especificamente o *European AI Act*.

## 🚀 Tecnologias Utilizadas

* **Linguagem:** Python 3.12
* **LLM:** Meta Llama-3-8B-Instruct (via Hugging Face Inference API)
* **Banco de Dados Vetorial:** Milvus Lite (persistência em arquivo `.db`)
* **Embeddings:** `BAAI/bge-small-en-v1.5` (via Sentence-Transformers)
* **Frameworks:** LangChain, PyPDF, e Hugging Face Hub

## 🏗️ Arquitetura do Sistema

O pipeline foi estruturado nas seguintes etapas:
1.  **Ingestão de Dados:** Extração de texto do PDF "The AI Act" utilizando `PyPDFLoader`.
2.  **Fragmentação (Splitting):** Divisão do texto em chunks de 1000 caracteres com sobreposição (overlap) de 200 para preservar o contexto semântico.
3.  **Vetorização:** Conversão de texto em embeddings de 384 dimensões.
4.  **Armazenamento Vetorial:** Criação de coleção no Milvus utilizando a métrica de Produto Interno (IP).
5.  **Recuperação e Geração:** Busca semântica dos 3 vizinhos mais próximos (KNN) e síntese da resposta final pelo Llama-3.



## 📊 Aplicação na Estatística

Este projeto explora conceitos fundamentais de estatística computacional, como:
* **Busca por Similaridade:** Aplicação de K-Nearest Neighbors (KNN) em espaços de alta dimensão.
* **Métricas de Distância:** Uso do Produto Interno (IP) para medir a correlação semântica entre vetores normalizados.
* **Probabilidade Condicional:** Otimização de parâmetros como a `temperature` para controlar a variância das respostas do modelo.

## 🛠️ Como usar

1.  Clone o repositório.
2.  Configure seu `HF_TOKEN` nas variáveis de ambiente ou nos Secrets do Google Colab.
3.  Execute o notebook `RAG_LLMs.ipynb` para processar o documento e realizar consultas.

---
*Graduando em Estatística pela Universidade Federal do Pará (UFPA).*
