# 📘 Sistema de Predição e Inserção Automática de Evasão Acadêmica  
**Desenvolvido por: Davi Ferreira Freitas**

---

## 🧠 Sobre o Projeto
Este projeto foi desenvolvido para prever a evasão de alunos de uma instituição de ensino nos turnos **EAD**, **Híbrido** e **Presencial**, utilizando modelos avançados de Machine Learning.

Além da predição, o sistema também **insere automaticamente os resultados no banco de dados**, garantindo integração total entre análise e operação.

O projeto combina:
- Engenharia de dados  
- Modelagem estatística  
- Machine Learning (LightGBM, CatBoost e RandomForest)  
- Automação de processos internos

---

## 🏗 Estrutura Geral do Sistema
O sistema é composto por **4 notebooks principais**, cada um desempenhando uma função crucial no pipeline:


---

### **1. INSERE_TODOS_ALUNOS.ipynb**
Responsável por:
- Carregar a lista completa de alunos da instituição  
- Normalizar e padronizar colunas  
- Sincronizar com o banco de dados  
- Criar a base unificada que alimenta todos os modelos  

---

### **2. MachineLearning_LightGBM.ipynb**  
Modelo otimizado para **alunos do ensino Presencial**.  
Contém:
- Preparação dos dados  
- Feature engineering  
- Treinamento com LightGBM  
- Avaliação completa  
- Seleção de threshold  
- Exportação do modelo final  
- Relatórios e métricas de qualidade  

---

### **3. MachineLearning_CatBoost.ipynb**  
Modelo otimizado para **alunos do ensino Híbrido**.  
Inclui:
- Preparação de dados  
- Treinamento com CatBoost  
- Melhor desempenho para dados categóricos  
- Ajustes para perfis heterogêneos  
- Exportação do modelo final  

---

### **4. MachineLearning_RandomForest.ipynb**  
Modelo otimizado para **alunos do ensino EAD**.  
Inclui:
- Treinamento com RandomForest  
- Alta interpretabilidade  
- Melhor recall encontrado para o público EAD  
- Exportação do modelo final  

---
## 🔍 Modelos de Machine Learning Utilizados
O projeto utilizou **3 algoritmos principais**:

### 🟦 RandomForest  
- Escolhido como **melhor modelo para EAD**  
- Bom desempenho em dados variados  
- Fácil interpretação de features  

### 🟩 CatBoost  
- Melhor modelo para **alunos do ensino Híbrido**  
- Excelente para lidar com categorias sem necessidade de encoding  
- Estável e com ótimo recall em perfis diversos  

### 🟧 LightGBM (modelo com melhor resultado geral)  
- Melhor modelo para **ensino Presencial**  
- Excelente relação velocidade/performance  
- Menor custo computacional  
- Ótimo AUC e Recall  
- Suporta grandes volumes de dados  

---

## 🧩 Engenharia de Atributos
As principais variáveis criadas incluem:
- Frequência do aluno  
- Notas e reprovações  
- Número de disciplinas matriculadas  
- Turno (EAD / Híbrido / Presencial)  
- Dados socioeconômicos  
- Histórico financeiro (inadimplência / pagamentos)  
- Tempo de vínculo acadêmico  

---

## 📊 Divisão de Dados e Métricas
Ajustado conforme o períodos dos alunos


Métricas avaliadas:
- Accuracy  
- Precision  
- Recall  
- F1-score  
- AUC  
- Curva Precision vs Recall  

Threshold final utilizado:  
```python
threshold = 0.34
```

---

## 💾 Exportação dos Modelos

Cada modelo foi exportado em formato .pkl contendo:

- Estrutura completa do pipeline

- Pré-processamento

- Threshold ideal

- Função interna de previsão

Exemplo:
```
modelo_lgb_com_threshold_034_real.pkl
```

---

## 🏫 Funcionamento por Turno de Ensino

**EAD**

- Maior risco estrutural de evasão

- RandomForest apresentou melhor recall

**Híbrido**

- Perfis heterogêneos

- CatBoost teve melhor adaptação aos dados

**Presencial**

- Forte dependência do histórico disciplinar

- LightGBM teve melhor desempenho geral

---

🧩 Benefícios para a Instituição


- Identificação antecipada de alunos com risco de evasão

- Base integrada e confiável

- Redução de retrabalho manual

- Melhor tomada de decisão pelos coordenadores

- Ações preventivas mais direcionadas e eficazes

---

## 👨‍💻 Autor

Davi Ferreira Freitas
Desenvolvedor responsável pela engenharia de dados, construção dos modelos e automação de integração com o banco de dados.

---

## 📌 Observação

Este projeto faz parte de uma solução interna utilizada em ambiente corporativo.
Os dados utilizados não estão presentes neste repositório por motivos de privacidade e LGPD.
