[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/kOqwghv0)
# ML Project — Прогнозирование класса пульсара по статистическим характеристикам сигнала

**Студент:** Цой Михаил -

**Группа:** БИВ235


## Оглавление

1. [Описание задачи](#описание-задачи)
2. [Структура репозитория](#структура-репозитория)
3. [Запуски](#быстрый-старт)
4. [Данные](#данные)
5. [Результаты](#результаты)
7. [Отчёт](#отчёт)


## Описание задачи

<!-- Кратко опишите задачу: что предсказываем, какой датасет, метрика качества -->

**Задача:** Классификация

**Датасет:** Бинарная классификация с использованием табличного набора данных пульсаров. Источник: https://www.kaggle.com/competitions/playground-series-s3e10/overview/#site-content

**Целевая метрика:** LogLoss 


## Структура репозитория
Опишите структуру проекта, сохранив при этом верхнеуровневые папки. Можно добавить новые при необходимости.
```
.
├── data
│   ├── processed               # Очищенные и обработанные данные
│   └── raw                     # Исходные файлы
├── models                      # Сохранённые модели 
├── notebooks
│   ├── Data_processing_and_preparation.ipynb
│   └── Modeling_and_Experiments.ipynb
├── presentation                # Презентация для защиты
├── report
│   ├── images                  # Изображения для отчёта
│   └── report.md               # Финальный отчёт
├── src
│   ├── preprocessing.py        # Предобработка данных
│   └── modeling.py             # Обучение и оценка моделей
├── tests
│   └── test.py                 # Тесты пайплайна
├── requirements.txt
└── README.md
```

## Запуск

Этот блок замените способом запуска вашего сервиса.
```bash
# 1. Клонировать репозиторий
git clone https://github.com/hsemlcourse/hseml-group-project-stetmish.git
cd hseml-group-project-stetmish

# 2. Создать виртуальное окружение
python -m venv .venv
# source .venv/bin/activate   # Linux/macOS
.venv\Scripts\activate    # Windows

# 3. Установить зависимости
pip install -r requirements.txt
```

## Данные
- `data/raw/` — исходные файлы
- `data/processed/` — предобработанные данные


## Результаты
Сравнение baseline-моделей

| Модель               | LogLoss   | ROC‑AUC   | F1        | Precision | Recall   |
|----------------------|-----------|-----------|-----------|-----------|----------|
| Linear SVM           | 0.009925  | 0.806066  | 0.100000  | 0.062500  | 0.250000 |
| Gaussian NB          | 0.033321  | 0.780907  | 0.052632  | 0.033333  | 0.125000 |
| KNN (k=5)            | 0.048682  | 0.559479  | 0.048387  | 0.030000  | 0.125000 |
| Decision Tree        | 0.087322  | 0.499533  | 0.002977  | 0.001491  | 1.000000 |
| Logistic Regression  | 0.406711  | 0.810761  | 0.102190  | 0.061947  | 0.291667 |

Лучшая модель: Linear SVM

Linear SVM показывает наименьший LogLoss при высоком ROC‑AUC, что делает его лучшей базовой моделью для данной задачи.

## Отчёт

Финальный отчёт: [`report/report.md`](report/report.md)
