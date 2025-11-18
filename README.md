Análise Exploratória de Dados (EDA) — Students Performance

A Etapa 1 contém a análise exploratória inicial, enquanto a Etapa 2 traz a versão atualizada e corrigida após ajustes e melhorias

Este projeto tem como objetivo realizar a Etapa 1 da análise exploratória de dados (EDA), utilizando o dataset “Students Performance”, que contém informações sobre o desempenho de estudantes com base em diversos fatores socioeducacionais e hábitos de estudo.

⸻

🎯 Motivo da escolha do dataset

Escolhemos o dataset Students Performance porque ele permite entender como diferentes variáveis — como horas de estudo, presença em aula, sono, idade e notas anteriores — influenciam o desempenho final dos alunos.
Esse tipo de análise é interessante porque se aproxima da realidade educacional e pode ajudar a identificar fatores que contribuem para um melhor rendimento acadêmico.

⸻

⚙ Etapas realizadas

Foram realizadas as seguintes etapas na análise:
	1.	Importação e leitura dos dados
	•	Carregamento do arquivo students_performance.csv no ambiente do Google Colab.
	2.	Estatísticas descritivas iniciais
	•	Exibição das primeiras linhas e resumo estatístico (describe()).
	3.	Análise de valores faltantes
	•	Verificação de dados ausentes e duplicados para garantir a qualidade do dataset.
	4.	Visualização das distribuições
	•	Criação de histogramas para observar a distribuição das variáveis numéricas.
	5.	Identificação de outliers (valores fora do padrão)
	•	Uso de boxplots para identificar possíveis outliers nas variáveis.
	6.	Correlação entre variáveis
	•	Construção de uma matriz de correlação com mapa de calor (heatmap) para observar as relações entre fatores como horas de estudo e nota final.
	7.	Conclusão da Etapa 1
	•	Foram encontradas correlações positivas entre tempo de estudo e nota final.
	•	Detectou-se também alguns outliers, especialmente em variáveis como “attendance_rate” e “study_hours_week”.
	•	Os dados estão prontos para seguir para a Etapa 2: tratamento e modelagem dos dados.
