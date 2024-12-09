# Classificação Multirrótulo no Domínio Jurídico

## Objetivo
Desenvolver modelos de classificação multirrótulo para classificar automaticamente processos jurídicos em diferentes categorias de assuntos. Isso é especialmente útil no contexto jurídico, onde um único processo pode estar relacionado a múltiplos temas (rótulos), como "contratos", "direito do consumidor" ou "tributação".

## Estrutura
O dataset de treino (recebido e baixado pelo código):
1. **x_train**: Conjunto de dados de treinamento contendo os textos dos processos.
2. **Y_train**: Conjunto de rótulos de treinamento indicando os assuntos associados a cada processo em `X_train`.

### **Pré-processamento**
Experimentação e avaliação de diferentes técnicas de pré-processamento para preparar os textos dos processos jurídicos para os modelos de classificação.

### **Divisão de Validação** 
Geração de um conjunto de validação a partir de uma amostra de `X_train` para avaliar o desempenho dos modelos de classificação durante o desenvolvimento.

### **Modelagem**
Exploraração e teste de diferentes algoritmos de classificação multirrótulo para identificar quais funcionam melhor neste domínio.

### **Avaliação** 
Avaliar os modelos utilizando métricas de classificação multirrótulo, com destaque para a F1-Score weighted, que será a métrica principal para identificar o modelo com melhor desempenho.

## Conclusões
Descubra
