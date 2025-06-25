# 🧾 Sistema RAG para Notas Fiscais Eletrônicas

Sistema de consulta inteligente para análise de Notas Fiscais Eletrônicas (NF-e) brasileiras usando RAG (Retrieval-Augmented Generation).

## 🚀 Funcionalidades

- **Consulta em linguagem natural** sobre dados de NF-e
- **Busca híbrida** (específica + semântica) em milhares de registros
- **Análise automática** de emissores, produtos, valores e relacionamentos
- **Extração inteligente** de parâmetros (números de NF, chaves, empresas)

## 🛠️ Tecnologias

- **LangChain** - Framework de orquestração
- **Groq** - LLM (llama-3.1-8b-instant)
- **FAISS** - Vector store para busca eficiente
- **SentenceTransformers** - Embeddings otimizados

## ⚡ Instalação

```bash
pip install langchain langchain-groq sentence-transformers faiss-cpu pandas numpy
```

## 🔧 Configuração

1. Configure sua chave da API Groq:
```bash
export GROQ_API_KEY="sua_chave_aqui"
```

2. Prepare seus dados CSV:
   - `202401_NFs_Cabecalho.csv` - Dados do cabeçalho das NFs
   - `202401_NFs_Itens.csv` - Dados dos itens das NFs

## 📖 Uso

```python
from rag_nf import main, fazer_pergunta_interativa

# Inicializar sistema
processor = main()

# Fazer perguntas
fazer_pergunta_interativa(processor, "Qual o emissor da nota fiscal 3510129?")
fazer_pergunta_interativa(processor, "Quais produtos a COMPANHIA BRASILEIRA vendeu?")
fazer_pergunta_interativa(processor, "Qual o valor total da nota 2525?")
```

## 💡 Exemplos de Perguntas

- "Qual empresa mais vendeu para o governo federal?"
- "Quais são os códigos NCM mais frequentes?"
- "Qual o produto mais caro da base?"
- "Quantas notas fiscais foram emitidas em São Paulo?"

## 📊 Estrutura dos Dados

O sistema processa arquivos CSV com estrutura padrão de NF-e brasileira:
- Chaves de acesso, emissores, destinatários
- Produtos, quantidades, valores, NCM
- Datas, natureza da operação

## 👥 Equipe AutonomIA

Layssa • Andressa • Patrícia • Thomas • Luciano • Paulo Henrique • Ivny • Susan • Amanda

## 📄 Licença

Este projeto é desenvolvido para fins educacionais e de pesquisa.