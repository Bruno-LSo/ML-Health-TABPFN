# Machine Learning para Predições em Saúde Cardiovascular

Este projeto demonstra a aplicação de algoritmos de machine learning para predição de risco cardiovascular utilizando dados de saúde, com ênfase no modelo TabPFN (Tabular Prior-Data Fitted Networks), uma abordagem baseada em transformers para dados tabulares.

- [Acesse o projeto por aqui.](TABPFNHealth.ipynb)
- [Artigo da Nature sobre o TABPFN](https://www.nature.com/articles/s41586-024-08328-6)

## Sumário
- [Visão Geral](#visão-geral)
- [Conjunto de Dados](#conjunto-de-dados)
- [Metodologia](#metodologia)
- [Algoritmos Implementados](#algoritmos-implementados)
- [Resultados](#resultados)
- [Interpretabilidade](#interpretabilidade)
- [Como Executar](#como-executar)
- [Requisitos](#requisitos)
- [Sobre o LABDAPS](#sobre-o-labdaps-s2)
- [Contato](#contato)

## Visão Geral

Este projeto explora como técnicas avançadas de machine learning podem ser aplicadas para predizer risco cardiovascular, comparando diferentes algoritmos e explorando técnicas de interpretabilidade e seleção de features. O objetivo principal é testarmos o modelo TABPFN.

https://www.nature.com/articles/s41586-024-08328-6

## Conjunto de Dados

Utilizamos um conjunto de dados com informações de saúde de 425.195 pacientes, contendo:
- Variáveis demográficas (idade, gênero, raça)
- Fatores de risco (hipertensão, diabetes, tabagismo)
- Medidas clínicas (IMC, colesterol, pressão arterial)
- Variável alvo: presença ou ausência de doença cardiovascular

Para a análise, focamos em pacientes com idade superior a 55 anos por representarem grupo de maior risco.

## Metodologia

O projeto segue uma abordagem completa de ciência de dados:

1. **Pré-processamento**: Limpeza, transformação e normalização de dados.
2. **Engenharia de Features**: One-hot encoding, label encoding e padronização.
3. **Seleção de Features**: Aplicação do algoritmo Boruta para identificar variáveis mais relevantes.
4. **Modelagem**: Implementação e otimização de múltiplos algoritmos.
5. **Avaliação**: Comparação de modelos usando métricas como acurácia, precisão, recall e AUC-ROC.
6. **Interpretabilidade**: Análise SHAP para entender a contribuição de cada variável no modelo CatBoost.
7. **Persistência**: Exemplo de salvamento e carregamento de modelos treinados.

## Algoritmos Implementados

Comparamos o desempenho de cinco algoritmos de machine learning:

- **Random Forest**: Ensemble de árvores de decisão.
- **XGBoost**: Implementação de gradient boosting otimizada.
- **LightGBM**: Framework de gradient boosting focado em eficiência.
- **CatBoost**: Algoritmo com tratamento nativo para variáveis categóricas.
- **TabPFN**: Modelo baseado em transformers para dados tabulares.

Cada algoritmo foi otimizado usando técnicas de busca de hiperparâmetros (RandomizedSearchCV).

## Resultados

O TabPFN apresentou o melhor desempenho geral:
- **Acurácia**: 76.67%
- **Precisão**: 62.50% 
- **Recall**: 55.56%
- **AUC-ROC**: 0.7884

Além disso, o TabPFN destacou-se por não necessitar de otimização intensiva de hiperparâmetros, mantendo excelente equilíbrio entre precisão e recall.

O algoritmo Boruta identificou apenas quatro variáveis como verdadeiramente relevantes (idade, colesterol total, pressão arterial sistólica e hipertensão), reduzindo significativamente a dimensionalidade do modelo.

## Interpretabilidade

Utilizamos análise SHAP (SHapley Additive exPlanations) para interpretar o comportamento do modelo CatBoost, revelando:

- A pressão arterial sistólica é o preditor mais influente do risco cardiovascular
- Idade e gênero aparecem como segundo e terceiro fatores mais importantes
- Os resultados alinham-se com o conhecimento médico estabelecido sobre fatores de risco cardiovascular

## Como Executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/Bruno-LSo/ML-Health-TABPFN.git
   cd ML-Health-TABPFN
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Execute o Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

4. Abra o notebook `TABPFN.ipynb` e execute as células sequencialmente.

## Requisitos

- Python 3.8+
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- LightGBM
- CatBoost
- TabPFN
- SHAP
- Boruta
- Jupyter Notebook

Todas as dependências estão listadas no arquivo `requirements.txt`.

[Acesse o projeto por aqui.](TABPFNHealth.ipynb)

## Sobre o LABDAPS s2

O [LABDAPS (Laboratório De Big Data E Análise Preditiva Em Saúde)](http://www.fsp.usp.br/labdaps/) da Faculdade de Saúde Pública da USP é um centro de excelência dedicado ao desenvolvimento de pesquisas e aplicações de ciência de dados na área da saúde. O laboratório promove cursos, workshops e projetos colaborativos visando melhorar a tomada de decisão baseada em evidências nos sistemas de saúde.

Agradecimento especial ao [Alexandre Chiavegatto Filho](https://www.linkedin.com/in/alexandre-chiavegatto-filho/) e ao [Gabriel Silva](https://www.linkedin.com/in/gabriel-silva-4258b998/).


## Contato

- [GitHub](https://github.com/Bruno-LSo)
- [LinkedIn](https://www.linkedin.com/in/bruno-lima-ds)
- **Email**: bruno_ls@uol.com.br

---
Obrigado pela atenção!
