# Classificação Multirrótulo no Domínio Jurídico

## Objetivo
Desenvolver e comparar modelos de classificação multirrótulo para categorizar automaticamente processos jurídicos em múltiplos assuntos (como "contratos", "direito do consumidor", "tributação", entre outros). Essa abordagem é especialmente útil no meio jurídico, onde um único processo pode envolver diversas áreas temáticas, permitindo uma análise mais rica e precisa dos dados.

## Estrutura
O dataset de treino (recebido e baixado pelo código):
1. **x_train**: Textos dos processos jurídicos.
2. **Y_train**: Rótulos que indicam os assuntos associados a cada processo.

### **Pré-processamento**
Aplicação de técnicas de limpeza, normalização e transformação dos textos para garantir que os dados estejam no formato adequado para a extração de features e subsequente modelagem.

### **Divisão de Validação** 
Criação de um conjunto de validação a partir dos dados de treinamento para monitorar e ajustar o desempenho dos modelos durante o desenvolvimento.

### **Modelagem**
Foram exploradas diferentes abordagens para gerar representações dos textos:

- *Embeddings Multilingues*

    Utilização de dois modelos para gerar embeddings:

    - [*paraphrase-multilingual-MiniLM-L12-v2*](https://huggingface.co/sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2)

    - [*all-MiniLM-L6-v2*](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2)

    Esses modelos capturam nuances semânticas dos textos em diversos idiomas, permitindo uma representação vetorial robusta dos processos jurídicos.

- *TF-IDF*

    Abordagem clássica baseada na frequência dos termos, utilizada para comparação com os modelos de embeddings.

### **Avaliação** 
Os modelos foram avaliados utilizando métricas específicas para tarefas de classificação multirrótulo, com ênfase na **F1-Score weighted (ponderada)**. Abaixo, os resultados obtidos para cada abordagem:

#### Modelo 1: paraphrase-multilingual-MiniLM-L12-v2
| Métrica           | Precision | Recall | F1-Score | Suporte |
|--------------------|------------|--------|----------|---------|
| Micro Avg          | 0.65       | 0.29   | 0.40     | 13104   |
| Macro Avg          | 0.40       | 0.15   | 0.19     | 13104   |
| Weighted Avg       | 0.52       | 0.29   | 0.34     | 13104   |
| Samples Avg        | 0.39       | 0.28   | 0.31     | 13104   |

#### Modelo 2: all-MiniLM-L6-v2
| Métrica           | Precision | Recall | F1-Score | Suporte |
|--------------------|------------|--------|----------|---------|
| Micro Avg          | 0.66       | 0.34   | 0.45     | 13104   |
| Macro Avg          | 0.48       | 0.18   | 0.22     | 13104   |
| Weighted Avg       | 0.57       | 0.34   | 0.39     | 13104   |
| Samples Avg        | 0.47       | 0.33   | 0.37     | 13104   |

#### Modelo 3: TF-IDF
| Métrica           | Precision | Recall | F1-Score | Suporte |
|--------------------|------------|--------|----------|---------|
| Micro Avg          | 0.75       | 0.45   | 0.56     | 13104   |
| Macro Avg          | 0.62       | 0.30   | 0.38     | 13104   |
| Weighted Avg       | 0.70       | 0.45   | 0.52     | 13104   |
| Samples Avg        | 0.55       | 0.44   | 0.47     | 13104   |

### **Conclusão**
Os resultados indicam que, para este conjunto de dados, a abordagem baseada em TF-IDF obteve desempenho superior em termos de precisão e F1-Score ponderada, em comparação com os modelos de embeddings multilingues testados. Essa análise reforça a importância de ajustar as técnicas de extração de features conforme as características específicas dos dados e da tarefa de classificação multirrótulo.