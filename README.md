# 🧠 GNN for Obesity Classification (PyTorch Geometric)

Este projeto implementa um modelo preditivo baseado em **Graph Neural Networks (GNNs)** utilizando a biblioteca **PyTorch Geometric**, com o objetivo de classificar indivíduos em **níveis de obesidade** com base em características de estilo de vida e saúde.

## 📊 Dataset

O dataset utilizado está disponível no [Kaggle - Obesity Levels dataset](https://www.kaggle.com/datasets/mendozateresita/obesity-levels-dataset), contendo variáveis relacionadas a:

- Idade, sexo
- Hábitos alimentares
- Frequência de exercícios
- Consumo de água
- Histórico familiar
- Consumo de álcool
- Modo de transporte
- Entre outras

---

## 🎯 Transformação das Classes Originais

O dataset original possui 7 classes-alvo:

- `Insufficient_Weight`
- `Normal_Weight`
- `Overweight_Level_I`
- `Overweight_Level_II`
- `Obesity_Type_I`
- `Obesity_Type_II`
- `Obesity_Type_III`

Para simplificar a tarefa de classificação, as classes foram **reagrupadas** da seguinte forma:

| Classes Originais              | Nova Classe   |
|-------------------------------|---------------|
| Insufficient_Weight + Normal_Weight | `normal`      |
| Obesity_Type_I + II + III     | `obesos`      |
| Overweight_Level_I + II       | **Removidas** |

Assim, a nova tarefa é uma **classificação binária**, com os seguintes rótulos:

- `0`: normal
- `1`: obesos

---

## 🧮 Objetivo

Construir um **modelo de classificação binária** que prediz se um indivíduo se encontra em condição de peso normal ou obeso, com base em dados de estilo de vida e saúde, representados em forma de grafo.

---

## 🧱 Organização do Projeto

O código está contido no notebook:

📄 [`Model_GNN_Obesity.ipynb`](https://github.com/raphaelp-silva/GNN_Pytorch_geometric/blob/main/Model_GNN_Obesity.ipynb)

### Etapas principais:
1. **Importação das bibliotecas**
2. **Carregamento e limpeza dos dados**
3. **Transformação das classes e filtragem**
4. **Conversão dos dados tabulares em um grafo**
   - Cada nó representa um indivíduo
   - Conexões (arestas) são baseadas em similaridades entre indivíduos
5. **Criação do `Data` object do PyTorch Geometric**
6. **Definição do modelo GNN**
   - Arquitetura simples com camadas `GCNConv`
7. **Treinamento do modelo**
   - Utiliza CrossEntropyLoss e otimização com Adam
8. **Avaliação do modelo**
   - Métrica principal: acurácia

---

## 🧠 Tecnologias Utilizadas

- Python 3.10+
- [PyTorch](https://pytorch.org/)
- [PyTorch Geometric](https://pytorch-geometric.readthedocs.io/)
- Pandas / NumPy / Scikit-learn
- Matplotlib

---

## 📈 Resultados Esperados

O modelo é capaz de aprender padrões nos dados e classificar corretamente se o indivíduo pertence à categoria `normal` ou `obesos`. Resultados podem variar conforme os critérios de construção do grafo e a arquitetura da rede utilizada.

---

## 📌 Melhorias Futuras

- Experimentar outras arquiteturas GNN (GraphSAGE, GAT, GIN)
- Ajuste fino de hiperparâmetros
- Inclusão de métricas adicionais de avaliação
- Expansão para predição de riscos associados à obesidade
- Utilização de GNNExplainer ou GNNShap para interpretar a importância das conexões

---

## 🙋‍♂️ Autor

**Raphael da Silva**

- Graduando em Ciência da Computação
- Pesquisador bolsista CNPq
- Interesse em Data Science, GNN, Saúde Pública e Inteligência Artificial
- GitHub: [@raphaelp-silva](https://github.com/raphaelp-silva)

---

## 🤝 Contribuições

Pull requests são bem-vindos! Para mudanças maiores, abra uma issue primeiro para discutir o que você gostaria de modificar.

---

## 📜 Licença

Este projeto está licenciado sob a **MIT License**. Veja o arquivo `LICENSE` para mais detalhes.
