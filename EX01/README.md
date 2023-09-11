# EX01 새로운 데이터셋으로 나만의 이미지 분류기 만들어보기
## used dataset : tensorflow_datasets tf_flowers 

# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 김소연
- 리뷰어 : 임현석


# PRT(Peer Review Template)
- [o]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 해당 조건을 만족하는 코드를 캡쳐해 근거로 첨부

base 모델을 활용한 전이학습이 성공적으로 진행되었는가 [o]
```python
# pre-trained vgg16 을 로드한다.
base_model = VGG16(weights='imagenet', include_top=False, input_shape=(224, 224, 3))
```

시각화자료들을 포함하여 체계적으로 진행되었는가 [o]
```python
# Plot the training and validation accuracy
plt.figure(figsize=(8, 6))
plt.plot(history.history['accuracy'], label='Training Accuracy')
plt.plot(history.history['val_accuracy'], label='Validation Accuracy')
plt.plot(history_fine_tune.history['accuracy'], label='Fine-tuned Training Accuracy')
plt.plot(history_fine_tune.history['val_accuracy'], label='Fine-tuned Validation Accuracy')
plt.xlabel('Epoch')
plt.ylabel('Accuracy')
plt.title('Training and Validation Accuracy')
plt.legend()
plt.grid(True)
plt.show()

# Plot the training and validation loss
plt.figure(figsize=(8, 6))
plt.plot(history.history['loss'], label='Training Loss')
plt.plot(history.history['val_loss'], label='Validation Loss')
plt.plot(history_fine_tune.history['loss'], label='Fine-tuned Training Loss')
plt.plot(history_fine_tune.history['val_loss'], label='Fine-tuned Validation Loss')
plt.xlabel('Epoch')
plt.ylabel('Loss')
plt.title('Training and Validation Loss')
plt.legend()
plt.grid(True)
plt.show()
```
분류모델의 정확도가 85%이상이 나왔는가 [o]
```python
# test accuracy 확인
test_loss, test_accuracy = model.evaluate(test_batches)
print(f"Test accuracy: {test_accuracy}")
23/23 [==============================] - 4s 130ms/step - loss: 0.4292 - accuracy: 0.8842
Test accuracy: 0.8841961622238159
````        
    
- [o]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
```python
2. model build
vgg16으로 분류모델 학습
batch size는 32
import tensorflow_datasets as tfds
import matplotlib.pyplot as plt
import tensorflow as tf
from tensorflow.keras.applications import VGG16
from tensorflow.keras.layers import Dense, Flatten, Dropout
from tensorflow.keras.models import Model
from tensorflow.keras.callbacks import ModelCheckpoint
train_ratio = 0.6
val_ratio = 0.2
test_ratio = 0.2
batch_size = 32
num_examples = info.splits['train'].num_examples
num_train_examples = int(train_ratio * num_examples)
num_val_examples = int(val_ratio * num_examples)
num_test_examples = int(test_ratio * num_examples)
train_dataset = dataset.take(num_train_examples)
val_dataset = dataset.skip(num_train_examples).take(num_val_examples)
test_dataset = dataset.skip(num_train_examples + num_val_examples).take(num_test_examples)
train_batches = train_dataset.shuffle(num_train_examples).batch(batch_size).prefetch(tf.data.experimental.AUTOTUNE)
val_batches = val_dataset.batch(batch_size).prefetch(tf.data.experimental.AUTOTUNE)
test_batches = test_dataset.batch(batch_size).prefetch(tf.data.experimental.AUTOTUNE)
# pre-trained vgg16 을 로드한다.
base_model = VGG16(weights='imagenet', include_top=False, input_shape=(224, 224, 3))
# 사전 훈련된 가중치 유지
for layer in base_model.layers:
    layer.trainable = False
```
        
- [o]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.


```
이미지 전처리시에 생겼던 에러와 수정방법을 잘 설명했습니다.

이미지 데이터의 범위에 문제가 발생하여 이미지가 깨져 나오는 문제 발생, info에서 dtype=tf.uint8
원본 이미지의 픽셀 값 범위에 따라 이 값이 [0, 1] 범위를 벗어난다고 판단, preprocess_image 함수 수정.
이미지의 데이터 타입을 확인하고 필요한 경우 float32로 변환한 다음, 픽셀 값의 범위를 [0, 1]로 조정
```
       
- [o]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.

```python

결과물을 matplotlib으로 시각화하여 잘 나타내주셨습니다.

import matplotlib.pyplot as plt

# Training history for the initial training
accuracy = history.history['accuracy']
val_accuracy = history.history['val_accuracy']
loss = history.history['loss']
val_loss = history.history['val_loss']

# Training history for the fine-tuning
fine_tune_accuracy = history_fine_tune.history['accuracy']
fine_tune_val_accuracy = history_fine_tune.history['val_accuracy']
fine_tune_loss = history_fine_tune.history['loss']
fine_tune_val_loss = history_fine_tune.history['val_loss']

# Combine the training histories
total_epochs = epochs + fine_tune_epochs
total_accuracy = accuracy + fine_tune_accuracy
total_val_accuracy = val_accuracy + fine_tune_val_accuracy
total_loss = loss + fine_tune_loss
total_val_loss = val_loss + fine_tune_val_loss

# Plot accuracy
plt.figure(figsize=(15, 6))
plt.subplot(1, 2, 1)
plt.plot(range(total_epochs), total_accuracy, label='Training Accuracy')
plt.plot(range(total_epochs), total_val_accuracy, label='Validation Accuracy')
plt.xlabel('Epochs')
plt.ylabel('Accuracy')
plt.legend(loc='lower right')
plt.title('Training and Validation Accuracy')

# Plot loss
plt.subplot(1, 2, 2)
plt.plot(range(total_epochs), total_loss, label='Training Loss')
plt.plot(range(total_epochs), total_val_loss, label='Validation Loss')
plt.xlabel('Epochs')
plt.ylabel('Loss')
plt.legend(loc='upper right')
plt.title('Training and Validation Loss')

plt.tight_layout()
plt.show()
```
        
- [o]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.

```python
이미지 전처리 시에 사용하는 함수를 만들어 코드 중복을 최소화 했습니다.

#이미지 크기 resize
def preprocess_image(image, label):
    image = tf.image.resize(image, (224, 224))
    image = tf.cast(image, tf.float32) / 255.0  
    image = tf.clip_by_value(image, 0, 1)
    return image, label


# Apply the preprocessing function to the dataset
dataset = dataset.map(preprocess_image)
```

# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
