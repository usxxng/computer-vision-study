# Image Segmentation 이란?

- 이미지의 영역을 분할해서 각 Object에 맞게 합쳐주는 것

Image Segmentation의 대표적인 예

![image1]('./imgs/seg_1.png')

Semantic Segmentation은 Object Segmentation을 하되 같은 Class인 Object들은 
같은 영역 혹은 색으로 분할 - Class의 위치를 인식(Localization)하고 판별(Classification)

반대로, Instance Segmentation은 같은 Class이여도 서로 다른 instance로 구분해주는 것
- 각 Object의 위치를 정확히 식별하는 객체 인식 (Object Detection)

따라서 Object가 겹쳤을 때, 각각의 Object를 구분해주지 못하는 Semantic Segmentation에서의
문제를 Instance Segmentation을 통해 해결할 수 있다.

### **Simple Example**

![image2]('./imgs/seg_2.png')

## Semantic Segmentation

Semantic Segmentation은 각 픽셀 별로 어떤 Class에 속하는지 Label을 구해줘야 함

![image3]('./imgs/seg_3.png')

One-Hot encoding으로 각 Class에 대해 Class 개수만큼 출력채널 생성

그 후 argmax를 통해 위 이미지처럼 하나의 output을 계산

![image4]('./imgs/seg_4.png')

이러한 Semantic Segmentation은 pixel들이 각 Class에 대해 binary하게 포함되는지 여부만 따진다.

![image5]('./imgs/seg_5.png')

Semantic Segmentation은 같은 class의 object들에 대해 서로 구분지을 수 없다는 단점

(ex. 위의 그림을 보면 몇대의 차가 어떻게 겹쳐있는지 알 수 없음)

![image6]('./imgs/seg_6.png')

Instance Segmentation은 각 픽셀 별로 어떤 카테고리에 속하는지 계산하는 것이 아닌 각 픽셀 별로 Object가 있는지 없는지 여부만 계산