# 📡 Telecom Churn Prediction: Estratégia de Retenção e Inteligência de Dados

## 💼 Visão de Negócio
No setor de telecomunicações, o custo de aquisição de um novo cliente (CAC) é significativamente maior do que o custo de retenção. O objetivo central deste projeto não é apenas prever se um cliente vai cancelar o contrato (Churn), mas sim **otimizar o retorno financeiro** das ações de retenção.

A solução desenvolvida utiliza Inteligência Artificial para identificar clientes em risco e, mais importante, define uma estratégia financeira para aplicar incentivos (descontos) apenas onde o retorno sobre o investimento (ROI) é positivo.

## ⚙️ Metodologia e Workflow

O projeto segue um fluxo rigoroso de Ciência de Dados, focado em reprodutibilidade, explicabilidade e impacto financeiro:

### 1. Modelagem e Validação Robusta
- **Esteira de Modelos:** Foi implementada uma bateria de testes com diversos algoritmos para estabelecer uma *baseline* sólida e identificar o modelo com melhor capacidade de generalização.
- **Validação Cruzada (Cross-Validation):** Para garantir a robustez estatística e evitar *overfitting*, todos os modelos foram submetidos a validação cruzada estratificada, assegurando performance consistente em diferentes cenários de dados.

### 2. Otimização Bayesiana com Optuna
Ao invés de métodos tradicionais de busca, utilizou-se o **Optuna** para a otimização de hiperparâmetros. Essa abordagem utiliza algoritmos bayesianos para explorar o espaço de parâmetros de forma eficiente, maximizando métricas críticas para o problema, como o *Recall*.

### 3. Explicabilidade do Modelo (SHAP)
Para garantir que o modelo não seja uma "caixa preta", foi utilizada a biblioteca **SHAP (SHapley Additive exPlanations)**. Isso permite entender exatamente quais variáveis (como tipo de contrato, método de pagamento ou tempo de casa) estão impulsionando a decisão do modelo para cada cliente específico, fornecendo insights valiosos para a equipe de marketing e CRM.

## 💰 Estratégia de Threshold (Limiar de Decisão)

Um dos grandes diferenciais deste projeto é a análise personalizada do **Threshold de Classificação**.

Modelos de classificação padrão assumem um limiar de 0.5 para decidir entre "Churn" e "Não Churn". No entanto, em um contexto de negócios, o custo de perder um cliente é diferente do custo de oferecer um desconto desnecessário.

Foi desenvolvida uma análise financeira que simula diferentes limiares de decisão. Ao "trocar o threshold", deslocamos a sensibilidade do modelo para encontrar o ponto ótimo onde o **Lucro Líquido** (Receita Salva - Custo dos Descontos) é maximizado. Essa técnica transforma uma métrica técnica abstrata em resultado financeiro tangível.

## 📊 Resultados Alcançados

A aplicação da estratégia de *Threshold Moving* permitiu calibrar o modelo para operar no seu ponto de eficiência máxima financeira:

* **Threshold Otimizado:** 0.41 (Ajustado para priorizar a captura de clientes em risco).
* **Recall (Sensibilidade):** ~84% (Alta capacidade de detecção de Churn).
* **Impacto Financeiro:** A simulação demonstrou que, com esse ajuste, a estratégia de retenção cobre seus próprios custos operacionais e gera um **Retorno Líquido Positivo**, validando a viabilidade econômica do projeto.

## 🚀 Tecnologias Utilizadas

* **Linguagem:** Python
* **Manipulação de Dados:** Pandas, Numpy
* **Visualização:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-learn
* **Otimização:** Optuna
* **Interpretabilidade:** SHAP

## 🔧 Como Executar

1. Clone este repositório:
   ```bash
   git clone https://github.com/enzoribeirodev/TELECOM_Churn_Prediction
