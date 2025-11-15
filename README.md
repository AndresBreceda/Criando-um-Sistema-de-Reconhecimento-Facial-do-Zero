# 🧠 Sistema de Detecção e Reconhecimento Facial  
Projeto desenvolvido em Python + TensorFlow + MTCNN

---

## 📌 Descrição do Projeto  
Este projeto implementa um **sistema completo de detecção e reconhecimento facial**, utilizando:

- **MTCNN** → Rede pré-treinada para detecção de faces.  
- **MobileNetV2 (TensorFlow/Keras)** → Rede para extração de características e classificação.  
- **Transfer Learning + Fine-Tuning** para melhorar o desempenho com datasets pequenos.

O sistema é capaz de:

- Detectar múltiplas faces simultaneamente  
- Recortar e preprocessar cada face  
- Classificar a qual pessoa ela pertence  
- Funcionar com imagens ou webcam  
- Treinar usando um dataset fornecido no Google Colab  

---

## 🗂 Estrutura do Dataset

O dataset deve estar organizado assim no Colab:

/content/dataset/
pessoa1/
img1.jpg
img2.jpg
pessoa2/
img1.jpg
img2.jpg
...

Cada pasta representa uma **classe** (identidade).  
O nome da pasta vira automaticamente a label no modelo.

---

## 🚀 Tecnologias Utilizadas

- Python 3  
- TensorFlow / Keras  
- MTCNN  
- OpenCV  
- NumPy  
- Google Colab  

---

## 📦 Instalação

Instale as dependências no Colab:

```bash
!pip install mtcnn opencv-python-headless==4.7.0.72
🧪 Treinamento

O script principal do projeto:

Carrega o dataset

Preprocessa as imagens

Constrói o modelo com MobileNetV2

Treina e valida

Salva o modelo final em:

/content/face_recognizer.h5


Faz fine-tuning opcional

Basta executar o código fornecido no arquivo principal do projeto.

🧠 Arquitetura do Sistema

Etapas:

Detectar faces usando MTCNN

Para cada face detectada:

Recortar

Redimensionar (160×160)

Preprocessar (MobileNetV2)

Classificar com o modelo TensorFlow

Exibir resultado com caixas e nomes

▶️ Como Executar o Reconhecimento em Uma Imagem

Após o treinamento:

img = cv2.imread("/content/teste.jpg")
resultado = recognize_faces_in_image(img, model)
cv2.imwrite("/content/resultado.jpg", resultado)


Isso gera a imagem com as caixas e nomes.

🎥 Webcam (Opcional)

No computador local (não funciona no Colab):

run_webcam_recognition(model)


Pressione Q para sair.

📁 Saídas do Projeto

Após rodar o sistema, você terá:

✔ Modelo Treinado
/content/face_recognizer.h5

✔ Imagem com Detecção e Reconhecimento
/content/result.jpg

📈 Melhorias Possíveis

Trocar MobileNetV2 por FaceNet (embeddings + SVM)

Aumentar número de imagens por pessoa

Usar data augmentation mais forte

Trocar MTCNN por RetinaFace para maior precisão

Implementar interface gráfica ou API REST

👨‍💻 Autor

Projeto desenvolvido como parte da disciplina de Sistemas Inteligentes / Redes Neurais, utilizando bibliotecas estudadas em aula.
