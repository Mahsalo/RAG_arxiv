## 🎯 Project Objective

The goal of this project is to build a **Retrieval-Augmented Generation (RAG)** system capable of answering scientific questions using contextual knowledge from research papers.

### Key Components

- **Context Data**  
  Utilizes the *arXiv Summarization Dataset* as the knowledge base.

- **Query Generation (Test Set)**  
  Synthetic queries are generated from the context using *Mistral-7B*, ensuring alignment between queries and source documents.

- **Embedding Model**  
  Uses *Qwen3-VL-8B* to generate embeddings for both queries and context, enabling semantic similarity search.

- **Vector Storage**  
  *ChromaDB* is used to store embeddings along with associated data and IDs, ensuring that semantically similar content is grouped together.

- **Indexing & Retrieval**  
  *FAISS* is used to efficiently index embeddings and retrieve the top-**K=5** most relevant context chunks for each query.

- **Answer Generation**  
  Retrieved context is passed to *Mistral-7B* to generate final answers.

### Evaluation

- **Retrieval Performance**  
  Achieves **Recall@5 = 99.8%**, **MRR = 99.6%**, driven by the fact that queries are derived from the same context distribution.

- **Answer Quality (Optional)**  
  Response quality can be further evaluated using an LLM-as-a-judge framework.
