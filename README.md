Análise de Modelos de Aprendizado de Máquina para Detecção de Desequilíbrio em Conjuntos de Dados

A detecção de desequilíbrio em conjuntos de dados é um desafio significativo no campo do aprendizado de máquina. Este estudo avalia a eficácia de diferentes modelos de aprendizado de máquina e técnicas de balanceamento, com foco nas abordagens de Undersampling e SMOTE (Synthetic Minority Over-sampling Technique). Para cada técnica, foram utilizados os algoritmos Random Forest, Decision Tree, XGBoost e SVM, e suas performances foram avaliadas por meio de métricas de acurácia, precisão, recall e F1-score.

Avaliação dos Modelos com Undersampling

Com a técnica de Undersampling, as acurácias médias obtidas com o método Shuffle Split foram 0.81 para Random Forest e XGBoost, 0.80 para SVM e 0.67 para Decision Tree. Resultados similares foram obtidos com k-fold CV, indicando a consistência dos modelos. No entanto, ao analisar as métricas detalhadas, o modelo Decision Tree apresentou uma precisão de 0.86, recall de 0.37 e F1-score de 0.41, enquanto em outra execução, obteve precisão de 0.83, recall de 0.38 e F1-score de 0.45. O modelo XGBoost, por sua vez, apresentou precisão de 0.86, recall de 0.39 e F1-score de 0.43. O modelo SVM obteve precisão de 0.87, mas um recall baixo de 0.17, resultando em um F1-score de apenas 0.09.

Avaliação dos Modelos com SMOTE

Por outro lado, a utilização do SMOTE revelou-se mais eficiente, com acurácias médias significativamente melhores. O Random Forest obteve uma acurácia média de 0.93 (Shuffle Split) e 0.92 (k-fold CV). O Decision Tree apresentou acurácia média de 0.86 para ambas as técnicas, enquanto o XGBoost teve acurácias de 0.85 e 0.83, respectivamente. Analisando as métricas de precisão, recall e F1-score, o modelo Decision Tree com SMOTE mostrou resultados robustos: precisão de 0.79, recall de 0.84 e F1-score de 0.81 em uma execução, e precisão de 0.78, recall de 0.77 e F1-score de 0.77 em outra. O modelo XGBoost também apresentou excelente desempenho, com precisão de 0.82, recall de 0.85 e F1-score de 0.82.

Importância das Features

Para entender melhor o desempenho dos modelos, é essencial analisar as importâncias das features utilizadas. No Random Forest, as variáveis mais importantes foram:

- BMI: 0.112900
- GenHlth: 0.099018
- Age: 0.096214
- HighBP: 0.092469
- Income: 0.075575

Estas features indicam que aspectos de saúde geral, idade e indicadores de pressão arterial alta têm um impacto significativo na previsão do modelo. No XGBoost, as variáveis mais importantes foram:

- HighBP: 0.198543
- HighChol: 0.118974
- GenHlth: 0.068545
- Sex: 0.066399
- Smoker: 0.059789

Aqui, observa-se uma ênfase maior em fatores relacionados à pressão arterial alta e colesterol, além de fatores de saúde geral e hábitos de fumar.

Comparação e Discussão

A comparação entre as duas técnicas de balanceamento revela que o SMOTE é superior ao Undersampling, especialmente em termos de acurácia e equilíbrio das métricas de desempenho. O Undersampling, embora eficiente para certos modelos, mostrou-se limitado, especialmente para o SVM, que teve um F1-score muito baixo devido ao recall insuficiente. Em contraste, o SMOTE melhorou significativamente as performances, equilibrando a precisão e o recall, resultando em F1-scores mais elevados.

O modelo Random Forest com SMOTE obteve a melhor acurácia geral (0.93 Shuffle Split e 0.92 k-fold CV), indicando sua robustez e eficácia na detecção de desequilíbrio. Além disso, os modelos Decision Tree e XGBoost com SMOTE também apresentaram F1-scores elevados, demonstrando um bom compromisso entre precisão e recall. A análise da importância das features mostra que, tanto no Random Forest quanto no XGBoost, fatores de saúde e demográficos são cruciais para a performance dos modelos.

Conclusão

Com base nos resultados apresentados, conclui-se que o uso de SMOTE proporciona uma melhoria substancial na performance dos modelos de aprendizado de máquina em conjuntos de dados desbalanceados. O Random Forest emergiu como o modelo mais eficaz, seguido de perto pelo Decision Tree e XGBoost quando aplicados em conjunto com SMOTE. Estas descobertas destacam a importância de escolher técnicas de balanceamento adequadas para melhorar a detecção e a precisão dos modelos de aprendizado de máquina em cenários de dados desbalanceados, promovendo análises mais robustas e confiáveis. Além disso, a análise das importâncias das features oferece insights valiosos sobre os fatores que mais influenciam as previsões, auxiliando na interpretação e aplicação prática dos modelos.
