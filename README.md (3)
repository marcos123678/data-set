📘 Etapa 3 — Modelagem com Regressão Linear
🎯 Objetivo

Criar, treinar e avaliar um modelo de Regressão Linear capaz de prever a variável final_grade (nota final dos estudantes) com base em diferentes características do dataset.

🧹 1. Pré-processamento dos Dados
1.1 Remoção de colunas irrelevantes

A coluna student_id foi removida por não contribuir para o modelo (apenas identificador).

df_clean = df.drop(["student_id"], axis=1)

1.2 Transformação de variáveis categóricas

Variáveis categóricas foram convertidas para números usando One-Hot Encoding:

df_encoded = pd.get_dummies(df_clean, drop_first=True)

1.3 Separação da variável alvo

X: variáveis preditoras

y: variável alvo (final_grade)

X = df_encoded.drop("final_grade", axis=1)
y = df_encoded["final_grade"]

1.4 Tratamento de valores ausentes

Valores faltantes foram preenchidos com a média de cada coluna:

X = X.fillna(X.mean())

1.5 Divisão em treino e validação

Os dados foram divididos em:

80% treino

20% validação

random_state=42 para reprodutibilidade

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

🤖 2. Treinamento do Modelo

Foi utilizado o algoritmo Regressão Linear:

model = LinearRegression()
model.fit(X_train, y_train)

📊 3. Avaliação do Modelo

Após o treinamento, foram feitas previsões:

y_pred = model.predict(X_test)


Foram calculadas as métricas:

MSE – Erro Quadrático Médio

RMSE – Raiz do Erro Quadrático Médio

MAE – Erro Absoluto Médio

R² – Coeficiente de Determinação

📈 4. Resultados Obtidos
🔵 Métricas no Treino
Métrica	Valor
MSE	34.42
RMSE	5.87
MAE	4.58
R²	0.40
🟢 Métricas na Validação
Métrica	Valor
MSE	29.68
RMSE	5.45
MAE	4.38
R²	0.39
🧠 5. Interpretação dos Resultados
MAE ≈ 4.3 a 4.5

O modelo erra, em média, cerca de 4 a 5 pontos na previsão da nota final.

R² ≈ 0.39–0.40

O modelo explica aproximadamente 39% a 40% da variação das notas dos alunos.
É um desempenho moderado: o modelo identifica padrões, mas ainda há espaço para evolução.

Conclusão sobre desempenho

A Regressão Linear capturou parte das relações entre as variáveis e a nota final, mas ainda existem fatores que não foram totalmente explicados.

🚀 6. Conclusão

Nesta etapa foi desenvolvido um modelo completo de Regressão Linear, passando por:

Limpeza dos dados

Conversão de variáveis categóricas

Tratamento de valores ausentes

Divisão treino/validação

Treinamento do modelo

Avaliação com múltiplas métricas

Geração de gráficos e análise

Apesar de apresentar desempenho moderado (R² ≈ 0.40), o modelo cumpre o objetivo da etapa e fornece uma boa base para análises futuras.

🔧 7. Possíveis Melhorias (para etapas futuras)

Normalização ou padronização dos dados

Testar modelos mais avançados (Lasso, Ridge, Random Forest, XGBoost)

Feature Engineering

Seleção de features

Ajuste de hiperparâmetros
