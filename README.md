# 🚗 Análise de Dados: Satisfação de Alunas em Autoescola Feminina

Projeto de análise exploratória de dados (EDA) desenvolvido como trabalho de faculdade, com o objetivo de identificar os fatores por trás do aumento na taxa de insatisfação das alunas de um centro de treinamento voltado ao público feminino.

## 📌 Contexto

O processo de obtenção da CNH no Brasil é notoriamente desafiador, e mulheres enfrentam barreiras culturais e psicológicas específicas nesse processo — como a **amaxofobia** (medo de dirigir), que segundo estimativas da Abramet atinge cerca de 2 milhões de brasileiros, dos quais 80% a 90% são mulheres.

A autoescola analisada identificou um aumento incomum na taxa de insatisfação entre suas alunas. Este projeto investiga **por que isso está acontecendo** e **quais ações poderiam reverter o problema**.

## 🎯 Perguntas de Negócio

- Existe correlação entre a instrutora responsável e a taxa de satisfação?
- O número de aulas realizadas impacta a satisfação da aluna?
- A idade influencia o número de aulas necessárias?
- Quais são os motivos de insatisfação mais frequentes, e estão concentrados em alguma instrutora?

## 🗂️ Dataset

`data/feedbacks.csv` — 1023 registros de feedback de alunas, com as colunas:

| Coluna | Descrição |
| --- | --- |
| `id_aluna` | Identificador único da aluna |
| `dt_feed` | Data do feedback |
| `age_a` | Idade da aluna |
| `motivo_n_dirige` | Motivo que a levou a buscar o treinamento |
| `dif_area` | Principal dificuldade prática relatada |
| `tot_aulas` | Total de aulas realizadas até o feedback |
| `id_inst` | Instrutora responsável |
| `nota_inst` | Nota dada à instrutora (1-5) |
| `nota_escola` | Nota dada à escola (1-5) |
| `feed` | Sentimento do feedback (Positivo/Negativo) |
| `nota` | Comentário livre da aluna |

## 🔍 Metodologia

O notebook `analise_mulheres_habilitadas.ipynb` percorre as seguintes etapas:

1. **Limpeza e tratamento de dados** — identificação e tratamento de valores nulos
2. **Análise exploratória (EDA)** — desempenho por instrutora, perfil das alunas, evasão vs. satisfação
3. **Análise de correlação** — matriz de correlação entre variáveis numéricas (Pearson)
4. **Análise bivariada** — relação entre dificuldade prática e nota da instrutora
5. **Regressão linear** — capacidade da nota da instrutora em prever o total de aulas realizadas
6. **NLP / Nuvem de palavras** — principais termos nos comentários negativos, para entender a causa raiz

## 💡 Principais Insights

- Uma instrutora concentra a maior parte das notas baixas e dos feedbacks negativos, sendo o principal gargalo identificado
- Alunas insatisfeitas fazem, em média, significativamente menos aulas do que alunas satisfeitas — indicando evasão precoce e perda de receita
- A análise de texto revela que o problema é **comportamental** (impaciência, atrasos), e não técnico
- Os principais motivos de busca pelo treinamento e as maiores dificuldades práticas apontam oportunidades de marketing segmentado

## 🛠️ Tecnologias

- Python
- Pandas
- Matplotlib / Seaborn
- Scikit-learn (regressão linear)
- WordCloud

## ▶️ Como executar

```bash
git clone https://github.com/SEU-USUARIO/NOME-DO-REPOSITORIO.git
cd NOME-DO-REPOSITORIO
pip install -r requirements.txt
jupyter notebook analise_mulheres_habilitadas.ipynb
```

## 📊 Fonte dos dados

Dataset fornecido no contexto do trabalho acadêmico, representando um extrato de matrículas de um centro de treinamento fictício/estudo de caso.
