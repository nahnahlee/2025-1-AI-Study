# 📚 기초 인공지능 스터디 2주차

## ✅ 개념 정리

### 🔹 이미지의 구성

- **이미지**: 픽셀들의 행과 열로 구성
- **픽셀(Pixel)**: 이미지를 구성하는 최소 단위
- **채널(Channel)**: 픽셀의 색을 구성하는 요소
  - **RGB**: Red, Green, Blue 각각 0~255 범위의 값을 가짐
  - **HSV**: 
    - Hue(색상): 0–360
    - Saturation(채도): 0–100
    - Value(명도): 0–100

📌 **이미지 차원**
- 컬러 이미지: `높이 x 너비 x 3`
- 흑백 이미지: `높이 x 너비 x 1`

---

### 🔹 이미지 처리(Image Processing)

이미지를 이해하고 처리하는 주요 단계:

1. **Image Classification**: 전체 이미지가 무엇인지 분류
2. **Detection**: 이미지 내에서 객체의 위치를 찾아냄
3. **Segmentation**: 픽셀 단위로 어떤 객체에 속하는지 분할
4. **Image Captioning**: 이미지의 의미를 자연어로 설명

⚠️ 이미지 처리에서 마주치는 어려움:
- Viewpoint 변화
- Illumination (조명)
- Deformation (형태 변화)
- Occlusion (가려짐)
- Background clutter (복잡한 배경)
- Intraclass variation (같은 클래스 내의 다양성)

---

### 🔹 손실 함수 (Loss Function)

- 정의: 예측값과 실제값 간의 **오차를 수치화**한 값. 이 값이 작아질수록 예측이 정확함.
- 예시 (MSE: Mean Squared Error) 수식:

\[
L = \frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2
\]

- 손실 함수는 **역전파(backpropagation)**와 **경사 하강법(gradient descent)**을 통해 가중치를 업데이트하는 데 사용됨

---

### 🔹 경사 하강법 (Gradient Descent)

- 목적: 손실 함수 \( L \)을 **최소화**하는 \( W \) (가중치)를 찾는 것
- 수식:

\[
W := W - \alpha \cdot \frac{\partial L}{\partial W}
\]

- \( \alpha \): 학습률 (learning rate) — 얼마나 빠르게 움직일지 결정

---

### 🔹 SVM (Support Vector Machine)

- **클래스 간 margin을 최대화**하는 선형 분류기
- 결정 경계(decision boundary)를 기준으로 데이터를 나누며, 가장 가까운 점들과의 거리를 **마진(margin)**이라 부름
- SVM은 이 마진을 최대화하는 방향으로 학습

---

### 🔹 Softmax 함수

- 다중 클래스 분류에서 출력 점수를 **확률처럼** 바꾸는 함수

\[
\text{Softmax}(z_i) = \frac{e^{z_i}}{\sum_{j=1}^{C} e^{z_j}}
\]

- \( C \): 클래스 수  
- \( z_i \): 각 클래스에 대한 score

📌 출력은 **0~1 사이**의 값이며, 모든 클래스 확률의 합은 1이 됨

---

## 🔸 Regularization (정규화)

- 정의: **과적합(overfitting)**을 방지하기 위해, 손실 함수에 규제항을 추가하는 기법
- 목표: 모델이 너무 복잡해지지 않도록, **가중치에 패널티 부여**

---

### 🔹 L1 Regularization (Lasso)

\[
L_{total} = L + \lambda \sum |W|
\]

- 일부 가중치를 0으로 만들어 **불필요한 특징 제거**
- **희소성(sparsity)**을 유도

---

### 🔹 L2 Regularization (Ridge)

\[
L_{total} = L + \lambda \sum W^2
\]

- 큰 가중치에 더 큰 패널티를 부여하여, 대부분의 특성이 **조금씩** 반영되게 함
- **부드럽고 안정적인 학습**을 유도

---

## ✏️ 정리

| 개념 | 핵심 포인트 |
|------|-------------|
| 이미지 구성 | 픽셀 + 채널 (RGB/HSV) |
| 이미지 처리 | classification → detection → segmentation |
| 손실 함수 | 예측값과 실제값의 차이 |
| 경사 하강법 | 손실 줄이기 위한 가중치 업데이트 방법 |
| SVM | 마진을 최대화하는 분류기 |
| Softmax | score를 확률로 변환 |
| Regularization | 과적합 방지: L1(희소), L2(패널티) |

---

이상입니다! 😊
