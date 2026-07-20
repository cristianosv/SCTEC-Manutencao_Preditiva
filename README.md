# SCTEC-Manutencao_Preditiva
Estruturação de pipeline preditivo para monitoramento de falhas mecanicas em uma indústria

## Descrição do Projeto
Projeto Final do Curso SCTEC - Trilha de Inteligência Artificial - Fundamentos de Dados, Programação e Análise Preditiva com Python.
Utilizar dados históricos de sensores instalados em máquinas em um ambiente industrial, aplicando técnicas de Análise Exploratória de Dados (EDA), preparação de dados, engenharia de tributos, balanceamento de classes e treinamento de modelos de Machine Learning (ML), para prever a ocorrência de falhas mecânicas e evitar paradas da produção.
Avaliar os algoritmos de ML **K-Nearest Neighbors (KNN)** e **Árvore de Decisão** com a base de dados disponível e verificar qual dos modelos terá melhor desempenho nos conjuntos de teste.

## Objetivo Geral
Desenvolver pipeline completo de ML que possa prever falhas em equipamentos industriais através de dados históricos capturados por sensores instalados nas máquinas do ambiente industrial.

## Objetivos Específicos
- Realizar Análise Exploratória de Dados (EDA);
- Identificar e tratar valores ausentes e/ou duplicados;
- Avaliar se há outliers (valores atípicos) nas variáveis estudadas;
- Construir uma nova variável pela Engenharia de Atributos;
- Preparar os dados para treinamento dos modelos de ML;
- Aplicar técnicas de balanceamento de dados para reduzir o efeito de desbalanceamento das classes;
- Treinar modelos de classificação utilizando KNN e Árvore de Decisão;
- Comparar o desempenho dos modelos através de métrics de avaliação;
- Selecionar o modelo mais adequado para utilização em um cenário de manutenção preditiva.

## Dataset
O conjunto de dados disponível simula um ambiente de **manutenção preditiva**, utilizando sensores que medem características operacionais de equipamentos industriais, senod constituído de **10.000 registros e 14 variáveis originais**, com informações de temperatura, torque, velocidade de rotação, desgaste da ferramenta, tipo de equipamento e indicadores de falhas.
A variável alvo deste projeto é:
- **0:** Equipamento em operação (sem falha);
- **1:** Equipamento com falha.
Na etapa de **Engenharia de Atributos (Feature Engineering)**, uma nova variável **potencia** foi criada a partir do produto entre velocidade de rotação (RPM) e torque (Nm) como forma de acrescentar uma nova característica da operação e auxiliar no treinamento dos modelos de Machine Learning.

## Tecnologias Utilizadas
Foram utilizadas as seguintes linguagens, bibliotecas e ferramentas:
- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Imbalanced-Learn (SMOTE)
- Jupyter Notebook
- Git
- GitHub

## Pipeline de Ciência de Dados
Todas as etapas necessárias para o desenvolvimento de um modelo de manutenção preditiva baseado em Machine Learning foram desenvolvidas conforme o pipeline estruturado de Ciência de Dados:
```text
Leitura da Base de Dados
          │
          ▼
Análise Exploratória dos Dados (EDA)
          │
          ▼
Limpeza e Tratamento dos Dados
          │
          ▼
Engenharia de Atributos
          │
          ▼
Divisão em Treino e Teste
          │
          ▼
Balanceamento das Classes (SMOTE)
          │
          ▼
Escalonamento das Variáveis (KNN)
          │
          ▼
Treinamento dos Modelos
(KNN e Árvore de Decisão)
          │
          ▼
Ajuste de Hiperparâmetros
          │
          ▼
Comparação dos Modelos
          │
          ▼
Avaliação do Modelo Final
(Matriz de Confusão e Classification Report)
          │
          ▼
Conclusão
```

## Estrutura do Repositório
```text
📦 Projeto
│
├── 📁 data/
│   └── predictive_maintenance.csv
│
├── 📄 notebook.ipynb
├── 📄 README.md
├── 📄 requirements.txt
│
└── 📁 imagens/
```

## Metodologia
O modelo foi desenvolvido conforme as etapas:
1. Análise exploratória dos dados para compreensão da distribuição das variáveis e identificação de padrões.
2. Tratamento de valores ausentes pela média, definida pela distribuição das variáveis.
3. Busca de registros duplicados.
4. Identificação e análise de outliers por meio de análise gráfica (boxplots).
5. Engenharia de atributos com a criação da variável **potencia**.
6. Transformação da variável categórica utilizando One-Hot Encoding.
7. Separação dos dados em treino (80%) e teste (20%) utilizando estratificação da variável alvo conforme documentação da engenharia.
8. Balanceamento das classes via SMOTE exclusivamente ao conjunto de treinamento.
9. Padronização das variáveis contínuas para o modelo KNN utilizando StandardScaler.
10. Treinamento e ajuste dos modelos KNN e Árvore de Decisão.
11. Comparação dos modelos e definição da melhor solução.
12. Avaliação final utilizando Matriz de Confusão e Classification Report.

## Resultados Obtidos
Com o treinamento e ajuste dos modelos de Machine Learning, os algoritmos **K-Nearest Neighbors (KNN) e Árvore de Decisão** foram os escolhidos para comparação, e a métrica de avaliação escolhida foi a acurácia no conjunto de teste.

### Comparação dos Modelos
| Modelo                                         | Acurácia Treino | Acurácia Teste |
|------------------------------------------------|----------------:|---------------:|
| KNN (K = 3)                                    |      96,93%     |     90,65%     |
| Árvore de Decisão (Sem limite de profundidade) |      99,56%     |   **94,20%**   |

Os resultados mostram que a Árvore de Decisão teve um melhor desempenho com o conjunto teste, sendo escolhida como modelo ideal para o projeto, quando comparado com o KNN.

### Avaliação do Modelo Selecionado
Com a definição da Árvore de Decisão como modelo selecionado para o projeto, foi possível avaliar a Matriz de Confusão e o Classification Report e verificar seu desempenho.
| Métrica          | Resultado  |
|------------------|-----------:|
| Acurácia         | **94,20%** |
| Precisão (Falha) |    0,33    |
| Recall (Falha)   |    0,71    |
| F1-Score (Falha) |    0,45    |

## Como executar o Projeto

### 1. Clone este repositório

```bash
git clone [https://github.com/cristianosv/SCTEC-Manutencao_Preditiva.git](https://github.com/cristianosv/SCTEC-Manutencao_Preditiva.git)
```
### 2. Acesse a pasta do projeto
```bash
cd SCTEC-Manutencao_Preditiva
```

### 3. Instale as dependências
```bash
pip install -r requirements.txt
```

### 4. Execute o Notebook
Abra o arquivo manutencao_preditiva.ipynb utilizano o Jupyter Notebook, Google Colab ou Visual Studio COde e execute as céluas na sequência apresentada

## Melhorias Futuras
Entende-se que o projeto apresenta todos os requisitos necessários para sua realização. entretanto, seguem sugestões para sua evolução em desenvolvimento:
- Avaliar outros algoritmos de ML como, por exemplo, Random Forest, XGBoost e LightGBM que também podem ser utilizados para a análise preditiva de falhas;
- Desenvolver a seleção automática de atributos para identificar variáveis de maior impacto na previsão de falhas;
- Utilizar técnicas de otimização de hiperparâmetros como GridSearch ou Random Search;
- Desenvolver API para liberar o modelo em ambiente de produção;
- Construir dashboard interativo para análise e monitoramento em tempo real;
- Validar o modelo com outrs conjuntos de dados com origem em outros equipamentos industriais.

## Conclusão
Com o projeto, foi possível aplicar os conhecimentos nas etapas de um pipeline de Ciência de Dados com objetvo de estudar problemas de classificação.
Junto a construção de um modelo de Machine Learning, foi possível realizar análises exploratórias, preparação de dados, engenharia de atributos, balanceamento de classes e avaliação de resultados para a escolha da opção mais adequada ao problema em questão (análise preditiva de manutenção).
Conhecendo os modelos de KNN e Árvore de Decisão, foi possível constatar que a acurácia de **94,20%** do modelo Árvore de Decisão foi o mais adequado, confirmando com as avaliações posteriores com a Matriz de Confusão e o Classification Report, que demonstraram que o modelo está adequado para o que foi proposto.

## Autor

**Cristiano Saldanha Vargas**
Desenvolvido como Projeto final do SCTEC - Carreira Tech - Trinha Inteligência Artificial Fundamentos de Dados, Programação e Análise Preditiva com Python 
GitHub: https://github.com/cristianosv
