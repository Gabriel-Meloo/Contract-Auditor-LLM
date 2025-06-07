# 📜 Contract Auditor LLM – Avaliação Automática de Contratos com Base em Livro de Regras

Este projeto visa **automatizar a análise contratual**, utilizando técnicas de **RAG (Retrieval-Augmented Generation)** para que uma **LLM (Large Language Model)** avalie se os contratos estão em conformidade com um conjunto de regras contratuais previamente definidas.

---

## 🎯 Objetivo

Permitir que qualquer usuário possa:

1. Subir um **livro de regras contratuais** (documento base).
2. Carregar um **contrato específico**.
3. Receber uma **avaliação automática**, indicando:
   - Quais regras estão sendo cumpridas
   - Quais regras estão ausentes ou violadas
   - Trechos do contrato que justificam a resposta

---

## ⚙️ Tecnologias Utilizadas

| Ferramenta         | Função                                                 |
|--------------------|--------------------------------------------------------|
| **Groq (LLM)**     | Modelo de linguagem que executa a análise contextual   |
| **LlamaIndex**     | Framework para conectar os dados estruturados ao LLM   |
| **ChromaDB**       | Banco de dados vetorial para armazenar embeddings      |
| **Python**         | Backend para ingestão de dados, chunking e avaliação   |

---

## 🔍 Como Funciona

1. **Ingestão das Regras**:
   - O sistema processa o "livro de regras contratuais"
   - Divide o texto em chunks e gera embeddings (armazenados no Chroma)

2. **Upload do Contrato**:
   - O usuário carrega um contrato em PDF ou texto
   - Também é convertido em chunks e vetorizado

3. **Processo de Análise (RAG)**:
   - A LLM compara os trechos do contrato com cada regra
   - Emite um parecer por regra, indicando se:
     - ✅ Está presente e em conformidade
     - ❌ Está ausente ou incorreta
     - 🟡 É ambígua ou insuficiente

4. **Resposta**:
   - Relatório textual com justificativas(PDF)

---
