# Classificador de Imagens

Este notebook implementa um classificador de imagens utilizando Support Vector Machines (SVM) com a biblioteca `scikit-learn`. Ele realiza as seguintes etapas:

## Etapas do Notebook

### 1. Importação de Bibliotecas
As bibliotecas necessárias são importadas, incluindo:
- `os` e `pickle` para manipulação de arquivos e serialização.
- `dotenv` para carregar variáveis de ambiente.
- `skimage` para leitura e transformação de imagens.
- `numpy` para manipulação de arrays.
- `scikit-learn` para treinamento e avaliação do modelo.

### 2. Preparação dos Dados
Os dados de entrada são carregados a partir de um diretório especificado na variável de ambiente `INPUT_DIR`. As imagens são redimensionadas para 15x15 pixels e transformadas em arrays unidimensionais.

### 3. Divisão dos Dados
Os dados são divididos em conjuntos de treino e teste utilizando `train_test_split` com estratificação.

### 4. Treinamento do Modelo
Um modelo SVM é treinado utilizando `GridSearchCV` para encontrar os melhores hiperparâmetros (`gamma` e `C`).

### 5. Avaliação do Modelo
O modelo é avaliado no conjunto de teste, e a precisão é calculada utilizando `accuracy_score`.

### 6. Salvamento do Modelo
O modelo treinado é salvo em um arquivo chamado `model.p` utilizando `pickle`.

### 7. Teste com Imagens
Imagens individuais podem ser testadas utilizando o modelo salvo. O caminho da imagem pode ser especificado diretamente ou carregado a partir de uma variável de ambiente `IMAGE_PATH`.

## Variáveis de Ambiente
- `INPUT_DIR`: Diretório contendo as imagens de treino.
- `IMAGE_PATH`: Caminho da imagem para teste.

## Exemplo de Uso
### Teste com uma imagem:
1. Defina o caminho da imagem no arquivo `.env`:
   ```
   IMAGE_PATH=C:\Users\mborges\Downloads\image classifier\img\carro.jpg
   ```
2. Execute as células para carregar o modelo e fazer a previsão.

### Resultado:
O notebook exibirá a categoria prevista para a imagem, como `empty` ou `not_empty`.

## Dependências
Certifique-se de instalar as seguintes bibliotecas antes de executar o notebook:
- `scikit-image`
- `numpy`
- `scikit-learn`
- `python-dotenv`

## Observações
- Certifique-se de que as imagens de teste sejam redimensionadas para 15x15 pixels para evitar erros de dimensionalidade.
- O arquivo `.env` deve estar configurado corretamente para carregar os caminhos das imagens e dados.
- link para baixar as imagens usadas para treino e teste: https://drive.google.com/drive/folders/1CjEFWihRqTLNUnYRwHXxGAVwSXF2k8QC
