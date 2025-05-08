# Classificao-de-Imagens-com-Transfer-Learning
Este projeto tem como objetivo demonstrar o uso de aprendizado por transferência (Transfer Learning)


```markdown
# 🧠 Classificador de Imagens com Transfer Learning (VGG16)

Este projeto demonstra como aplicar **aprendizado por transferência (transfer learning)** e **fine-tuning** para treinar 
um classificador de imagens eficiente mesmo com uma quantidade relativamente pequena de dados. 
Comparamos um modelo de rede neural convolucional (CNN) customizado do zero com um modelo baseado na arquitetura **VGG16**, 
pré-treinada no dataset ImageNet, e comprovamos os ganhos significativos em acurácia ao usar essa técnica.

---

## 📚 Objetivo

Treinar um classificador de imagens utilizando duas abordagens:
1. Um modelo CNN construído do zero.
2. Um modelo baseado em transfer learning com a arquitetura **VGG16**.

Em seguida, comparar os resultados de desempenho e demonstrar o ganho obtido ao reaproveitar uma rede pré-treinada.

---

## 🛠️ Tecnologias e Bibliotecas

- Python 3.10+
- TensorFlow / Keras
- Matplotlib
- NumPy
- OS (para manipulação de arquivos)
- Dataset: [PetImages (Cães e Gatos)](https://www.microsoft.com/en-us/download/details.aspx?id=54765)

---

## 🧪 Metodologia

### 1. Pré-processamento
- Carregamento de imagens (redimensionadas para 224x224).
- Normalização dos valores de pixel.
- Separação em: treino, validação e teste.

### 2. Modelo Customizado do Zero
- CNN simples criada com camadas `Conv2D`, `MaxPooling2D`, `Dropout` e `Dense`.
- Treinada por 15 épocas.
- Métricas de desempenho visualizadas via gráficos.

### 3. Transfer Learning com VGG16
- Carregamento do modelo **VGG16** com pesos do ImageNet.
- Substituição da camada final por uma nova `Dense` com softmax para as classes do projeto.
- Congelamento das camadas anteriores (extração de características).
- Treinamento somente da última camada (fine-tuning) com taxa de aprendizado reduzida.
- Salvamento do melhor modelo com `ModelCheckpoint`.

### 4. Comparação de Resultados
- Comparação entre os históricos de loss e acurácia dos dois modelos.
- Avaliação nos dados de teste.
- Exibição de melhoria percentual em acurácia com o modelo de transferência.

### 5. Predição com Imagem Externa
- Leitura de imagem externa (`PetImages/Cat/1.jpg`).
- Exibição da imagem com a classe prevista e probabilidades.

---

## 🧾 Resultados

- O modelo treinado do zero teve desempenho razoável, mas limitado.
- Com Transfer Learning (VGG16):
  - **Acurácia significativamente maior**.
  - Treinamento mais rápido e eficiente.
  - Melhor generalização nos dados de teste.

> 💡 A estratégia de fine-tuning permitiu adaptar a VGG16 à nova tarefa com poucas amostras e excelente resultado.

---

## 🖼️ Exemplo de Predição

```

Testando predição para: PetImages/Cat/1.jpg

Predição: Cat
Probabilidades por classe:
Cat: 0.9876
Dog: 0.0124

```

---



## ▶️ Como Executar

1. Clone o repositório:

```bash
git clone https://github.com/seu-usuario/seu-repo.git
cd seu-repo
````

2. Instale as dependências:

```bash
pip install -r requirements.txt
```

3. Execute o notebook:

```bash
jupyter notebook script.ipynb
```

4. Certifique-se de que o diretório `PetImages/` está no mesmo caminho do notebook, contendo as imagens para treino/teste.

---

## 🧠 Aprendizado por Transferência

O aprendizado por transferência envolve reaproveitar redes neurais pré-treinadas em grandes datasets 
(como ImageNet) para resolver novas tarefas. 
Neste projeto, utilizamos a **VGG16**, congelamos suas camadas iniciais (extratoras de características), e ajustamos 
apenas a camada final. 
Isso permitiu treinar com poucos dados, alcançando desempenho excelente, com economia de tempo e recursos computacionais.

---

## 📌 Conclusão

* O modelo VGG16 com fine-tuning superou significativamente o modelo CNN treinado do zero.
* Transfer Learning é uma técnica poderosa para problemas com poucos dados.
* A abordagem é facilmente adaptável para outras tarefas de classificação de imagens com conjuntos similares.

---

## 📷 Referências

* [VGG16 Paper](https://arxiv.org/pdf/1409.1556.pdf)
* [CS231n - Transfer Learning](http://cs231n.github.io/transfer-learning/)
* [Sebastian Ruder - Transfer Learning Overview](http://sebastianruder.com/transfer-learning/)



---

```txt
tensorflow>=2.10.0
numpy>=1.21.0
matplotlib>=3.5.0
```

---

📌 **Notas**:

* A versão do TensorFlow pode ser ajustada conforme sua instalação atual ou compatibilidade de hardware (GPU/CPU).
* Para usar o projeto em um ambiente virtual, você pode criar e ativar um com:

```bash
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate
pip install -r requirements.txt
```

```


