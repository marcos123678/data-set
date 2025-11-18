1. Objetivo

O objetivo desta etapa é criar, treinar e avaliar um modelo de Regressão Linear capaz de prever a variável final_grade (nota final dos estudantes) com base em diferentes características do dataset.

⸻

2. Pré-processamento dos Dados

2.1 Remoção de colunas irrelevantes

A coluna student_id não agrega valor ao modelo por ser apenas um identificador.
Por isso, foi removida:
df_clean = df.drop(['student_id'], axis=1)

2.2 Transformação de variáveis categóricas

Como algoritmos de Machine Learning trabalham melhor com números, todas as variáveis categóricas foram convertidas com One-Hot Encoding (dummies):
df_encoded = pd.get_dummies(df_clean, drop_first=True)
2.3 Separação da variável alvo
	•	X = variáveis preditoras
	•	y = variável a ser prevista (final_grade)
X = df_encoded.drop("final_grade", axis=1)
y = df_encoded["final_grade"]
2.4 Tratamento de valores ausentes

Valores faltantes em X foram preenchidos pela média da coluna:
X = X.fillna(X.mean())
2.5 Divisão em treino e teste

Os dados foram divididos:
	•	80% para treino
	•	20% para teste
	•	random_state=42 para garantir reprodutibilidade
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

3. Treinamento do Modelo

Foi utilizado o algoritmo de Regressão Linear:
model = LinearRegression()
model.fit(X_train, y_train)

4. Avaliação do Modelo

Após fazer previsões com o conjunto de teste:
y_pred = model.predict(X_test)
Foram calculadas as métricas:
	•	MAE (erro absoluto médio)
	•	MSE (erro quadrático médio)
	•	R² (coeficiente de determinação)
mae = mean_absolute_error(y_test, y_pred)
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)

Resultados Obtidos:
MAE = 4.98
MSE = 31.63
R²  = 0.37

5. Interpretação dos Resultados

MAE = 4.98

O modelo erra, em média, aproximadamente 5 pontos ao prever a nota final.
É um erro razoável, mas ainda alto para um modelo ideal.

MSE = 31.63

Indica que existem erros grandes em alguns casos, pois o MSE penaliza mais erros altos.

R² = 0.37

O modelo explica 37% da variação da nota final.
Isso significa que ele tem um desempenho moderado, capturando parte das relações do dataset, mas ainda com espaço para melhorias.

⸻

6. Conclusão

Nesta etapa foi construído e avaliado um modelo de Regressão Linear.
Apesar de o modelo apresentar um desempenho moderado (R² = 0.37), ele já consegue identificar padrões importantes nos dados.

Para etapas futuras, possíveis melhorias incluem:
	•	Normalização dos dados
	•	Teste de outros algoritmos (Ridge, Lasso, Random Forest)
	•	Ajuste de hiperparâmetros
	•	Análise de correlação entre variáveis
