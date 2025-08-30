# Sistema de Manutenção Preditiva - Classificação de Falhas

## 🎯 Objetivo
Classificar 5 tipos de falhas em máquinas industriais com base em dados de sensores IoT.

## 📊 Dados
**Variáveis de entrada**: temperatura_ar, temperatura_processo, umidade_relativa, velocidade_rotacional, torque, desgaste_da_ferramenta

**Variáveis-alvo (multilabel)**:
- falha_maquina: Indica se houve falha na máquina
- FDF: Falha por Desgaste da Ferramenta  
- FDC: Falha por Dissipação de Calor
- FP: Falha por Potência
- FTE: Falha por Tensão Excessiva
- FA: Falha Aleatória

## 📈 Métricas de Avaliação
- Acurácia por classe
- F1-score (macro e weighted)
- Precision e Recall
- Matriz de confusão multilabel

