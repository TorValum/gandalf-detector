# 🧙 Gandalf Detector - YOLO Object Detection

Модель для обнаружения Гэндальфа (серый/белый) с использованием YOLOv8.

## Датасет
- **104 изображения** Гэндальфа из "Властелина колец"
- **2 класса**: `gandalf_grey` (0), `gandalf_white` (1)
- **Разделение**: 80% train (83 изображения), 20% val (21 изображение)
- **Разметка**: Вручную размечено в VGG Image Annotator (VIA)

## Как использовать

### 1. Обучение (Google Colab)
```python
!pip install ultralytics
!git clone https://github.com/TorValum/gandalf-detector.git
%cd gandalf-detector

from ultralytics import YOLO
model = YOLO('yolov8n.pt')
model.train(data='data.yaml', epochs=30, device=0)
```

### 2. Тестирование
```python
model = YOLO('runs/detect/train/weights/best.pt')
model('/content/ваше_фото.jpg')[0].show()
```

## Результаты
```
https://github.com/TorValum/gandalf-detector/tree/main/results
```

## Структура проекта
```
gandalf-detector/
├── data.yaml              # Конфигурация датасета
├── train/                 # Обучающие данные
├── val/                   # Валидационные данные
├── results/               # Скриншоты результатов
└── README.md              # Этот файл
```

## Технологии
```
• YOLOv8 (Ultralytics)
• Google Colab (обучение на T4 GPU)
• VGG Image Annotator (разметка)
• GitHub (хранение кода и данных)
```
