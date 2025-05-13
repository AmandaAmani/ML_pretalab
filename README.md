# 🌸 ML_Pretalab

Projeto desenvolvido durante a aula de **Machine Learning** no curso de **Inteligência Artificial da Pretalab**.  
Aqui, exploramos como modelos de aprendizado de máquina podem ser aplicados em tarefas de **classificação de imagens faciais**, com recorte racial.

## 🎯 Propósito

Construímos um classificador binário que identifica se o rosto presente em uma imagem pertence à classe:

-  **Mulher Negra**
-  **Mulher Branca**

Este trabalho tem fins educativos e experimentais.

---

## 🧠 Como o modelo foi construído

Utilizamos a arquitetura **MobileNetV2**, já treinada em imagens (ImageNet), como base. Em cima dela, adicionamos camadas personalizadas para treinar um modelo simples e direto.

### 🔧 Estrutura da Rede Neural

- **Base:** `MobileNetV2` (congelada)
- **Head customizada:**
  - `Flatten()`
  - `Dense(128, activation='relu')`
  - `Dense(1, activation='sigmoid')`

A camada `sigmoid` final retorna valores entre 0 e 1, permitindo fazer **classificação binária**.

---

## 📁 Organização dos Arquivos

| Arquivo/Função                   | Finalidade                                                                 |
|----------------------------------|---------------------------------------------------------------------------|
| `modelo_classificacao_racial.h5`| Arquivo do modelo treinado e salvo                                        |
| `test_image_from_path_or_url()` | Função que testa imagens locais ou da internet                            |
| `test_paths`                    | Lista com exemplos de imagens para avaliação                              |
| Código principal                | Faz o carregamento do modelo, pré-processamento e inferência nas imagens |

---

## ⚙️ O que você precisa para rodar

Você pode executar tudo direto no [Google Colab](https://colab.research.google.com), ou localmente com as seguintes bibliotecas:

- `TensorFlow` / `Keras`
- `NumPy`
- `Pillow` (PIL)
- `Matplotlib`
- `requests` *(para testar imagens via URL)*

---

## ▶️ Como usar

1. **Abra o notebook no Colab**  
   *(Suba o arquivo no seu GitHub e substitua aqui pelo link)*  
   👉 [Abrir no Google Colab](#)

2. Clique em **Executar tudo** (`Runtime > Run all`)

3. Para testar uma imagem, use:

```python
test_image_from_path_or_url("CAMINHO_OU_URL_DA_IMAGEM")
