# Предсказание опасных астероидов (NASA NEO)
**Выполнил:** Adylov Arsen

## О проекте
Система оценки потенциальной опасности астероидов на реальных
данных NASA (NEO — Near-Earth Objects). Полный цикл ML-проекта:
от первичного анализа данных до интерпретируемой модели и демо.

## Обоснование выбора датасета
- **Реальные данные NASA** (JPL Small-Body Database).
- Две задачи: классификация (pha — опасен/не опасен) и
  регрессия (diameter — диаметр в км).
- Выраженный дисбаланс классов (~0.22% опасных).
- Смешанные типы признаков и большое число пропусков.

## Структура репозитория
- `data/raw/` — датасет NASA (не входит в git, см. .gitignore;
  скачать: Kaggle "Asteroid Dataset" — https://www.kaggle.com/datasets/sakhawat18/asteroid-dataset)
- `data/processed/corpus_wiki.csv` — корпус Википедии для ПР-6
- `notebooks/PR1_first_look.ipynb` — первичный анализ (ПР-1)
- `notebooks/PR2_EDA.ipynb` — разведочный анализ: пропуски, выбросы,
  гипотезы, корреляции (ПР-2)
- `notebooks/PR3_pipeline.ipynb` — пайплайн предобработки (ПР-3)
- `notebooks/PR4_regression.ipynb` — регрессия diameter,
  log-трансформация, градиентный спуск на NumPy (ПР-4)
- `notebooks/PR5_classification.ipynb` — классификация pha,
  дисбаланс, подбор порога (ПР-5)
- `notebooks/PR6_texts.ipynb` — классификация текстов,
  корпус Википедии, BoW vs TF-IDF (ПР-6)
- `notebooks/PR7_random_forest.ipynb` — случайный лес,
  важность признаков: impurity/permutation/SHAP (ПР-7)
- `notebooks/demo_asteroid_guard.ipynb` — интерактивное демо:
  ввод параметров астероида → вердикт модели
- `reports/data_dictionary.md` — описание признаков
- `models/` — обученные модели (не входят в git из-за размера,
  создаются кодом ПР-7)

## Запуск
pip install -r requirements.txt

Демо: выполнить ячейки сохранения модели в ПР-7, затем
Restart Kernel & Run All в demo_asteroid_guard.ipynb.