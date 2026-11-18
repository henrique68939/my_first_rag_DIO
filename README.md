# my_first_rag_DIO
Sistema RAG com LlamaIndex, ChromaDB e Google Gemini para consulta de dados em linguagem natural. Projeto do Bootcamp Santander na DIO.

# 🤖 Meu Primeiro RAG — Conectando Dados à IA Generativa

Projeto desenvolvido como parte do **Bootcamp Santander — RAG com ChromaDB, LlamaIndex e Python** na plataforma [DIO](https://dio.me).

---

## 📌 Sobre o Projeto

Este projeto demonstra a construção de um sistema **RAG (Retrieval-Augmented Generation)** do zero, conectando dados reais de uma loja de suprimentos de informática a um modelo de linguagem generativa (Gemini).

Em vez de o modelo responder apenas com base no que aprendeu durante o treinamento, o RAG permite que ele **consulte uma base de dados própria** antes de responder — tornando as respostas muito mais precisas e relevantes.

---

## 🧠 O que é RAG?

**RAG (Retrieval-Augmented Generation)** é uma técnica que combina dois componentes:

1. **Recuperação (Retrieval):** busca os trechos mais relevantes de uma base de dados usando similaridade semântica (vetores)
2. **Geração (Generation):** usa um modelo de linguagem (LLM) para gerar uma resposta em linguagem natural com base nos trechos recuperados
3. 
---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Função |
|---|---|
| **Python** | Linguagem principal |
| **LlamaIndex** | Framework de orquestração do RAG |
| **ChromaDB** | Banco de dados vetorial (armazena os embeddings) |
| **Google Gemini** | Modelo de linguagem para geração de respostas |
| **HuggingFace Sentence Transformers** | Geração de embeddings (vetorização do texto) |
| **Google Colab** | Ambiente de execução |

---


---

## 🚀 Como Executar

### Pré-requisitos

- Conta no [Google Colab](https://colab.research.google.com)
- Chave de API do [Google AI Studio](https://aistudio.google.com) (gratuita)

### Passo a passo

**1. Abra o notebook no Google Colab**

Clique no arquivo `.ipynb` do repositório e abra com o Colab.

**2. Configure seu Secret**

No painel esquerdo do Colab, clique no ícone 🔑 (Secrets) e adicione:
- **Name:** `GOOGLE_API_KEY`
- **Value:** sua chave do Google AI Studio

**3. Execute as células em ordem**

| Célula | O que faz |
|---|---|
| Célula 1 | Instala os pacotes necessários |
| Célula 2 | Configura o Gemini e o modelo de embeddings |
| Célula 3 | Cria o arquivo CSV com os dados da loja |
| Célula 4 | Indexa os dados no ChromaDB e executa consultas |

---

## 💬 Exemplos de Consultas

**Pergunta:** *Quais produtos da categoria Periféricos foram vendidos?*
> Os produtos da categoria Periféricos que foram vendidos são: Mouse Logitech MX Master 3, Teclado Mecânico Redragon Kumara, Webcam Logitech C920, Mousepad Gamer XL, Fone Headset Hyperx Cloud e Teclado Sem Fio Logitech K380.

**Pergunta:** *Qual foi a venda de maior valor total?*
> A venda de maior valor total foi a da **Placa de Vídeo GTX 1650**, no valor de **R$ 1.200,00**, realizada para o cliente Diego Martins em 02/02/2024.

**Pergunta:** *Quais produtos de armazenamento foram vendidos e por quanto?*
> SSD Kingston 480GB (R$ 540,00), HD Externo Seagate 1TB (R$ 640,00), Pendrive Sandisk 64GB (R$ 330,00) e SSD NVMe 1TB WD Black (R$ 960,00).

---

## 🔐 Segurança

A chave de API nunca é exposta no código. O projeto usa o sistema de **Secrets do Google Colab**:

```python
from google.colab import userdata
os.environ["GOOGLE_API_KEY"] = userdata.get("GOOGLE_API_KEY")
