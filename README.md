## 프로젝트 소개
이 프로젝트는 Computer Vision 기반의 Classifier 모델을 훈련하여 왜곡이 포함된 이미지를 정확하게 분류하는 것을 목표로 합니다. 17개 클래스의 이미지를 대상으로 하며, 회전, 뒤집기, 노이즈 등 의도적으로 왜곡된 이미지를 포함합니다.
<br>
<br>
주요 특징:
<br>
- 훈련 데이터: 1,570장
- 평가 데이터: 3,140장
- 클래스 수: 17개
<br>

## 팀원 구성

<div align="center">

| **진주영(팀장)** | **최정은** | **문기중** | **이승민** | **김효원** |
| :------: |  :------: | :------: | :------: | :------: |
|[<img src="https://avatars.githubusercontent.com/u/156163982?v=4" height=150 width=150> <br/> @Github](https://github.com/) |[<img src="https://avatars.githubusercontent.com/u/156163982?v=4" height=150 width=150> <br/> @Github](https://github.com/) |[<img src="https://avatars.githubusercontent.com/u/156163982?v=4" height=150 width=150> <br/> @Github](https://github.com/) |[<img src="https://avatars.githubusercontent.com/u/156163982?v=4" height=150 width=150> <br/> @Github](https://github.com/) |[<img src="https://avatars.githubusercontent.com/u/156163982?v=4" height=150 width=150> <br/> @Github](https://github.com/) |
</div>

<br>

## 개발 환경

- 주 언어 : Python
- 버전 및 이슈관리 : Pytorch 
- 협업 툴 : CUDA

<br>

## 채택한 개발 기술과 브랜치 전략

### 채택한 개발 기술
<br>
1. 데이터 증강 기법:
<br>
- 오프라인 증강(14만장, 20만장, 30만장): Rotation, Flip, Augmentation(class 1,13,14 위주), Transforms 등
<br>
- 온라인 증강: Random Brightness & Contrast, Hue Shift, Gaussian Noise 등
<br>
- Augraphy는 offline 데이터셋으로 먼저 20만장 정도 증강 후 사용했더니 큰 차이 없어 대부분 사용 안함(일부만 사용)
<br>
- Mixup, Cutmix 등 추가 사용
<br>
<br>
2. 모델 아키텍처:
<br>
ResNet (34, 50, 101, 152)
<br>
ResNeXt
<br>
DenseNet121
<br>
EfficientNet (B0, B3, B4)
<br>
Vision Transformer (ViT)
<br>
Swin Transformer
<br>
ConvNeXt1
<br>
<br>
3. 최적화 기법:
<br>
손실 함수: Cross-Entropy Loss, Focal Loss
<br>
옵티마이저: Adam, AdamW
<br>
학습률 스케줄러: StepLR, CosineAnnealingLR1
<br>
그 외: Label smoothing, 클래스별 weights 시도 등
<br>
<br>
4. 앙상블 기법:
Soft Voting, Hard Voting
<br>
<br>

### 브랜치전략     
- 브랜치 전략
  - Git-flow 전략을 기반으로 main, develop 브랜치와 feature 보조 브랜치를 운용했습니다.
  - main, develop, Feat 브랜치로 나누어 개발을 하였습니다.
    - **main** 브랜치는 배포 단계에서만 사용하는 브랜치입니다.
    - **develop** 브랜치는 개발 단계에서 git-flow의 master 역할을 하는 브랜치입니다.
    - **Feat** 브랜치는 기능 단위로 독립적인 개발 환경을 위하여 사용하고 merge 후 각 브랜치를 삭제해주었습니다.


<br>

## 프로젝트 구조
```
project/
│
├─Juyoung
│  ├─CODE
│  │      code_12_loss.ipynb
│  │      code_15(Effi_b3).ipynb
│  │      code_16(Augraphy).ipynb
│  │      code_19(Changes epochs).ipynb
│  │      code_24(Scheduler).ipynb
│  │      code_4.ipynb
│  │      code_7_weights.ipynb
│  │      code_9(K-FOLD).ipynb
│  │      Softvoting_exp_copy.ipynb
│  │      Train_Only_3,7Class.ipynb
│  │      train2.ipynb
│  │      train2_EDA.ipynb
│  │      train3.ipynb
│  │      train4.ipynb
│  │
│  └─EDA
│          EDA(Class, RGB, Resolutions).ipynb
│          EDA(Identify Misclassifications).ipynb
│
├─Jeongeun
│      cv3_code_1106.ipynb
│      cv3_code_ResNet50_1103.ipynb
│      precalculate.ipynb
│      resnet50_fin.ipynb
│
├─Gijung
│      baseline_code_mlflow.ipynb
│      class-metrics2.ipynb
│      cv.ipynb
│      tta-inference-with-model-load.ipynb
│
└─Seungmin
│       [업스테이지AILab] CV 프로젝트 3조 - 발표자료.pdf
│
├─Hyowon
│      online_aug.ipynb
│      swin_tiny_aug_.ipynb
│
└── README.md
...

```
<br>

## 역할 분담

진주영 - 지치지 않는 무한 리액션
<br>
최정은 - 즐겁게 여러가지 시도해보기
<br>
문기중 - 뭔가 더 해보기
<br>
이승민 - 오디오 채우기
<br>
김효원 - 잘 모르는데 일단 해보기
<br>
<br>
## 개발 기간 및 작업 관리

### 개발 기간
- 전체 개발 기간 : 2024-10-29 ~ 2024-11-08
- 기능 구현 : 2024-10-29 ~ 2024-11-08
- 그외 기간 작성
  
<br>
