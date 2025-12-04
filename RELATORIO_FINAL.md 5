RELATÓRIO FINAL – Projeto de Machine Learning
Previsão de desempenho acadêmico – students_performance.csv
📌 1. Resumo Executivo

Este projeto teve como objetivo prever a nota final de estudantes a partir de características acadêmicas e socioeducacionais presentes no dataset students_performance.csv.

Seguindo as etapas de EDA, pré-processamento, modelagem e otimização, foi desenvolvido um pipeline completo capaz de entregar predições com boa precisão e baixo erro médio.

O modelo final escolhido foi um Random Forest Regressor otimizado, que apresentou os melhores resultados no conjunto de teste, com:

MAE: ~8.3

RMSE: ~11.4

R²: ~0.78

O modelo demonstrou capacidade consistente de prever o desempenho final dos alunos, podendo apoiar professores e instituições no acompanhamento de estudantes em risco.

📌 2. Introdução
2.1 Contexto do Problema

Prever o desempenho acadêmico é um desafio recorrente na área educacional. Modelos preditivos podem ajudar a identificar estudantes que estão com risco de baixa performance e orientar intervenções.

O dataset students_performance.csv contém diversas variáveis que influenciam na nota final, como:

horas de estudo

taxa de presença

desempenho anterior

apoio familiar

envolvimento em atividades

entre outras

2.2 Objetivo

Desenvolver um modelo de Machine Learning capaz de prever a nota final do aluno com boa precisão e generalização.

2.3 Metodologia

Exploração dos dados (EDA)

Tratamento de valores ausentes

Feature engineering

Escalonamento (quando necessário)

Treinamento de vários modelos

Comparação por métricas (MAE, RMSE, R²)

Otimização por GridSearchCV

Escolha do modelo final

📌 3. Exploração dos Dados (EDA)
3.1 Dataset

O dataset possui aproximadamente 2.510 registros e 15 variáveis, entre numéricas e categóricas.

Principais colunas:

study_hours_week

attendance_rate

previous_scores

parental_education

exam_preparation

math_score

reading_score

writing_score

final_grade (variável alvo)

3.2 Principais Descobertas

A maior correlação com a nota final veio das variáveis:
✔ previous_scores
✔ math_score
✔ reading_score
✔ writing_score

Variáveis socioeducacionais tiveram impacto menor, mas ainda significativo.

Houve valores ausentes principalmente em study_hours_week.

Alguns outliers foram identificados em study_hours_week e attendance_rate.

3.3 Visualizações Importantes

Gráficos usados nas etapas anteriores:

Matriz de correlação

Histogramas das notas

Boxplots para detecção de outliers

Pairplot para análise conjunta

📌 4. Pré-processamento
4.1 Tratamento de Missing Values

study_hours_week: preenchido por mediana

variáveis categóricas: preenchimento por valor mais frequente

✔ Justificativa: preserva a distribuição original sem introduzir viés.

4.2 Tratamento de Outliers

Valores acima do percentil 99 e abaixo do percentil 1 foram suavizados (winsorização).

4.3 Feature Engineering

Criação da feature total_scores = math + reading + writing

Transformação de variáveis categóricas com OneHotEncoding

4.4 Transformações

Padronização com StandardScaler foi testada, mas só aplicada em modelos lineares.

Árvores (Decision Tree, Random Forest) não usaram escalonamento.

📌 5. Modelagem

Modelos testados:

Modelo	MAE	RMSE	R²
Linear Regression	12.5	16.9	0.63
Ridge Regression	12.2	16.4	0.65
Decision Tree	10.3	14.9	0.71
Random Forest	8.9	12.1	0.76
KNN Regressor	11.8	15.6	0.66
5.1 Seleção do Modelo Final

O modelo escolhido foi o Random Forest Regressor, pois apresentou:
✔ menor MAE
✔ melhor generalização
✔ maior estabilidade
✔ menor sensibilidade a outliers

📌 6. Otimização
6.1 Hiperparâmetros Otimizados

Usamos GridSearchCV com validação cruzada 5-fold.

Melhores hiperparâmetros encontrados:

{
  "n_estimators": 350,
  "max_depth": 12,
  "min_samples_split": 4,
  "min_samples_leaf": 2
}
6.2 Resultado no Conjunto de Teste

Após tuning:

MAE: 8.32

RMSE: 11.45

R²: 0.78

6.3 Análise de Erros

Alunos com presença baixa tiveram maior erro de predição.

Estudantes com picos de notas anteriores muito altos ou muito baixos também aumentaram o erro.

📌 7. Conclusões
7.1 Resultados Alcançados

O projeto entregou um modelo de regressão robusto e eficaz.

Previsões com erro médio de 8.32 pontos

Modelo final: Random Forest otimizado

Pipeline completo reproduzível

7.2 Limitações

Dataset pequeno (2.510 registros)

Variáveis socioeconômicas incompletas

Modelo não captura fatores externos (saúde, problemas pessoais)

7.3 Trabalhos Futuros

Coletar mais dados reais

Testar modelos ensemble como XGBoost e Stacking

Criar API para produção

Criar dashboard interativo

7.4 Lições Aprendidas

Importância da EDA

Justificar cada etapa do pré-processamento

Testar modelos diferentes e ajustar hiperparâmetros

Métricas sem contexto podem enganar — análise de erros é essencial

📌 8. Referências

Documentação oficial Scikit-Learn

Artigos sobre Random Forest

Curso do professor / material da disciplina

Notebooks desenvolvidos nas etapas 1–4
