## Table of Contents 
- []()

### What is LLM?

[YT LINK](https://youtu.be/Q75JgLEXMsM?si=ikzouY33u3Z63LyB)

Large Language Models or Language Models are AI/ML models that are trained on massive amounts of text-based data in order to process and generate natural text/language. They're prediction engines, and a kind of generative AI. 

An input to LLM is generally called "Prompt".  

Examples of LLM are GPT-4, 

### What is RAG? 

RAG stands for 'Retrieval Augmented Generation'. (Retrieval to <i>Augment</i > Generation)
Retrieval - Search 
Generation - LLM
Here, we "Augment" the "Generation" based on the context we get from "Search", which is Retrieval. 

RAG is not a model itself, but a <b>method</b> or <b>pipeline</b> that improves LLM outputs by adding an information retrieval step before text generation.
This information (top-k retrieved documents) are added as "Context" to the original prompt. 

Ex:

Context:
[Relevant Doc1]
[Relevant Doc2]
.... 

Question:
What are the side effects of drug X?

#### What does the Architecture of a RAG Pipeline look like?

                 ┌──────────────────────┐
                 │  User Query          │
                 └────────┬─────────────┘
                          │
                    [Query Embedding]
                          │
                 ┌────────▼────────┐
                 │ Vector Database │ ◄── Preprocessed docs (chunked + embedded)
                 └────────┬────────┘
                          │
              [Top-K Relevant Chunks]
                          │
                 ┌────────▼────────┐
                 │ Prompt Builder  │ ◄─ Combines context + query
                 └────────┬────────┘
                          │
                      [LLM Call]
                          │
                 ┌────────▼────────┐
                 │ Final Answer    │
                 └─────────────────┘
#### Tool Stack 
| Component        | Example Tools/Libraries                       |
| ---------------- | --------------------------------------------- |
| Ingest documents | LangChain, LlamaIndex, Haystack, Unstructured |
| Embeddings       | OpenAI, Cohere, Sentence-BERT, HuggingFace    |
| Vector DB        | FAISS, Pinecone, Weaviate, Chroma, Qdrant     |
| Retrieval        | Dense (cosine), Hybrid (BM25 + vectors)       |
| LLM              | GPT-4, Claude, Mistral, Gemini, LLaMA         |
| Orchestration    | LangChain, LlamaIndex, Haystack               |
| Reranking        | Cohere Rerank, BGE, Cross-Encoder             |
| Evaluation       | RAGAS, LMEval, Promptfoo, human review        |
