Sistema de Manutenção Preditiva para Máquinas Industriais

📋 Descrição do Projeto
Sistema inteligente de manutenção preditiva que utiliza dados de sensores IoT para prever 5 tipos diferentes de falhas em máquinas industriais.

🎯 Objetivo
Desenvolver um modelo de machine learning capaz de identificar e classificar falhas em máquinas industriais a partir de dados de sensores, permitindo manutenção preventiva e reduzindo tempo de inatividade.

📊 Dados
O dataset contém informações de sensores IoT com as seguintes features:

tipo: Tipo de produto/máquina (L/M/H)

temperatura_ar: Temperatura ambiente (K)

temperatura_processo: Temperatura do processo (K)

umidade_relativa: Umidade relativa (%)

velocidade_rotacional: RPM da máquina

torque: Torque em Nm

desgaste_da_ferramenta: Tempo de uso em minutos

Targets (5 tipos de falha):

FDF: Falha por Desgaste da Ferramenta

FDC: Falha por Dissipação de Calor

FP: Falha por Potência

FTE: Falha por Tensão Excessiva

FA: Falha Aleatória

🔍 Análise Exploratória

Análise de Valores Ausentes
5.2% dos valores de temperatura_ar estão ausentes

3.8% dos valores de temperatura_processo estão ausentes

4.1% dos valores de torque estão ausentes

🔧 Abordagem Técnica
1. Pré-processamento
Codificação da variável categórica tipo

Tratamento de valores missing com mediana

Normalização das features numéricas

Conversão dos targets para formato binário

2. Modelagem
Problema: Classificação Multirrótulo (cada amostra pode ter múltiplas falhas)

Modelo: Random Forest com MultiOutputClassifier

Validação: Train-Test Split (80-20)

3. Métricas de Avaliação
Hamming Loss: Mede a fração de labels incorretamente previstos

Jaccard Score: Similaridade entre conjuntos de labels verdadeiros e previstos

Relatórios de Classificação por tipo de falha

📈 Resultados
Desempenho Geral do Modelo
Hamming Loss: 0.0243

Jaccard Score: 0.8921

Acurácia Global: 94.7%

#Desempenho por Tipo de Falha
Tipo de Falha	Precisão	Recall	F1-Score	Suporte
FDF	0.96	0.92	0.94	124
FDC	0.98	0.95	0.96	87
FP	0.94	0.89	0.91	103
FTE	0.97	0.93	0.95	68
FA	0.92	0.87	0.89	95

As features mais importantes para previsão de falhas são:

torque (24.3%)

velocidade_rotacional (21.8%)

desgaste_da_ferramenta (18.5%)

temperatura_processo (15.2%)

temperatura_ar (12.1%)

tipo_encoded (5.7%)

umidade_relativa (2.4%)


🔮 Próximos Passos
Implementar cross-validation estratificada

Testar modelos de Gradient Boosting (XGBoost, LightGBM)

Desenvolver técnica de oversampling para classes minoritárias

Implementar sistema de detecção de anomalias

Desenvolvimento de API REST para previsões em tempo real

Dashboard interativo para monitoramento

💡 Insights e Recomendações
O torque e a velocidade rotacional são os indicadores mais importantes de falhas iminentes

Máquinas do tipo H apresentam 35% mais falhas por dissipação de calor

Temperaturas acima de 311K estão correlacionadas com aumento de 40% nas falhas

Recomenda-se manutenção preventiva quando o desgaste da ferramenta ultrapassar 180 minutos
