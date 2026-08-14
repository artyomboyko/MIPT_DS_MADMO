# MIPT_DS_MADMO

Учебный репозиторий с выполненными практическими работами и итоговым проектом по курсу [**«Методы анализа данных и машинного обучения» МФТИ**](https://fpmidpo.mipt.ru/programs/ppk/ml-course).

Материалы охватывают два основных блока курса:

- **Модуль 1 — Базовые алгоритмы машинного обучения**
- **Модуль 2 — Глубокое обучение**

Все работы выполнены в формате Jupyter Notebook. Репозиторий показывает практику работы с табличными данными, классическими ML-алгоритмами, NLP, компьютерным зрением и нейросетевыми моделями, а также содержит отдельный end-to-end проект по обработке видео и речи.

## Содержание

### Модуль 1 — Базовые алгоритмы машинного обучения

- **[Homework 1](Part_1/Homework_1.ipynb)** - классификация риска заболевания сердца на датасете **[Heart Attack Analysis & Prediction Dataset](https://www.kaggle.com/datasets/rashikrahmanpritom/heart-attack-analysis-prediction-dataset)**: EDA, предобработка и кодирование признаков, подбор гиперпараметров и сравнение моделей `Logistic Regression`, `SVC`, `Random Forest` и `KNN`; лучший результат - **SVC, F1-score ≈ 0.904**.
- **[Homework 2](Part_1/Homework_2.ipynb)** - детекция мошеннических транзакций на сильно несбалансированном датасете **[Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)**: EDA и предобработка данных, подбор гиперпараметров `Logistic Regression` с помощью `GridSearchCV`, исследование class weighting, методов under-sampling и over-sampling (`RandomUnderSampler`, `TomekLinks`, `NeighbourhoodCleaningRule`, `RandomOverSampler`, `SMOTE`, `ADASYN`) и сравнение с `BalancedRandomForestClassifier`; в итоговом сравнении лучшим подходом с учётом дисбаланса выбран **Balanced Random Forest**.
- **[Homework 3](Part_1/Homework_3.ipynb)** - NLP-классификация твитов на датасете **[Twitter Sentiment Analysis](https://www.kaggle.com/datasets/arkhoshghalb/twitter-sentiment-analysis-hatred-speech)** от Analytics Vidhya для выявления расистских и сексистских высказываний: очистка и лемматизация текста, анализ дисбаланса классов, `CountVectorizer` и `TF-IDF` с N-граммами, сравнение методов over-/under-sampling и подбор гиперпараметров `Multinomial Naive Bayes` через `GridSearchCV`; **macro F1-score ≈ 0.81**. Дополнительно исследованы Transformer-эмбеддинги на базе `sberbank-ai/sbert_large_nlu_ru`.
- **[Homework 4](Part_1/Homework_4.ipynb)** - прогнозирование оттока держателей кредитных карт на датасете **[Credit Card Customers](https://www.kaggle.com/datasets/sakshigoyal7/credit-card-customers)**: EDA и анализ дисбаланса классов, отбор информативных признаков с помощью `mutual_info_classif`, обучение `CatBoostClassifier` с нативной обработкой категориальных признаков и подбором гиперпараметров через 5-fold grid search; **accuracy ≈ 0.98, macro F1-score ≈ 0.96, F1-score класса оттока ≈ 0.93**.

### Модуль 2 — Глубокое обучение

- **[Homework 5](Part_2/Homework_5/Homework_5.ipynb)** — практическая работа по построению и обучению нейронных сетей.
- **[Homework 6](Part_2/Homework_6.ipynb)** — Computer Vision на PyTorch: transfer learning, работа с архитектурами ResNet, ResNeXt, MobileNet и DenseNet, подбор гиперпараметров с Optuna, квантизация и экспорт/инференс через ONNX.
- **[Homework 7](Part_2/Homework_7.ipynb)** — практическая работа по глубокому обучению.

## Итоговый проект

Мой итоговый проект в рамках завершения программы переподготовки ["Data Scientist"](https://fpmidpo.mipt.ru/programs/ppp/datascience)

### Автоматическое создание и перевод субтитров для видео

**[Открыть итоговую работу](FINAL_WORK/FINAL_WORK.ipynb)**

Итоговая работа объединяет несколько этапов обработки мультимедиа в единый pipeline:

1. загрузка видео и извлечение аудиодорожки;
2. автоматическое распознавание речи с помощью **Whisper**;
3. оценка качества распознавания метрикой **WER (Word Error Rate)**;
4. машинный перевод субтитров на русский язык с использованием моделей **Transformers / Helsinki-NLP**;
5. формирование субтитров и сборка итогового видео.

В проекте используются Whisper, Transformers, `jiwer`, FFmpeg и `yt-dlp`.

## Основные технологии

`Python` · `Jupyter Notebook` · `pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `scikit-learn` · `NLTK` · `PyTorch` · `torchvision` · `Optuna` · `ONNX` · `Whisper` · `Transformers` · `FFmpeg`

## Структура репозитория

```text
MIPT_DS_MADMO/
├── Part_1/       # базовые алгоритмы машинного обучения
├── Part_2/       # глубокое обучение
├── FINAL_WORK/   # итоговый проект
└── README.md
```

## О репозитории

Этот репозиторий служит учебным портфолио по курсу МФТИ и демонстрирует последовательный переход от анализа данных и классических методов машинного обучения к глубокому обучению и сборке прикладного ML-пайплайна из нескольких моделей и инструментов.
