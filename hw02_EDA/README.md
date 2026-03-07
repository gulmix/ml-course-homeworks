# HW02: Exploratory Data Analysis — Video Game Sales

## Датасет

[Video Game Sales](https://www.kaggle.com/datasets/gregorut/videogamesales) — 16 598 игр с продажами по регионам (NA, EU, JP, Other) за 1980–2020 годы.

| Признак | Тип | Описание |
|---------|-----|----------|
| Name | str | Название игры |
| Platform | cat | Платформа (PS2, DS, Wii, ...) — 31 уникальная |
| Year | num | Год выпуска |
| Genre | cat | Жанр (Action, Sports, ...) — 12 уникальных |
| Publisher | cat | Издатель — 578 уникальных |
| NA/EU/JP/Other_Sales | num | Продажи по регионам (млн копий) |
| Global_Sales | num | Суммарные мировые продажи (млн копий) |

## Что сделано в ноутбуке

1. **Загрузка данных** — скачивание с Kaggle, распаковка, первичный осмотр (`shape`, `info`, `describe`).
2. **Обработка пропусков** — анализ NaN (Year: 271, Publisher: 58), демонстрация четырёх стратегий: dropna, fillna(mean), fillna(median), fillna(const), fillna(mode).
3. **Статистический анализ** — min/max/mean/median/mode, квантили, дисперсия, асимметрия (skewness), эксцесс (kurtosis).
4. **Кодирование категорий** — One-Hot Encoding (Platform, Genre), Label Encoding (Publisher), Target Encoding, Hashing Encoder.
5. **Feature engineering** — доли региональных продаж (NA_Ratio, EU_Ratio, ...), log-преобразование продаж.
6. **Визуализация** — гистограммы, boxplot, violin, heatmap корреляций, pairplot, barplot топ-платформ/жанров/издателей, интерактивный scatter (Plotly).
7. **Выводы** — ключевые находки, гипотезы, план дальнейшего моделирования.

## Основные находки

- Распределение продаж сильно скошено вправо (медиана 0.17 млн, среднее 0.54 млн).
- NA — доминирующий рынок; JP-рынок ведёт себя принципиально иначе (слабая корреляция с NA/EU).
- Выбросы — реальные хиты Nintendo (Wii Sports: 82.74 млн), а не шум.
- Самые частые жанры (Action) и самые прибыльные (Platform, Shooter) не совпадают.

## Запуск

```bash
pip install numpy pandas matplotlib seaborn plotly scikit-learn category_encoders kaggle
jupyter notebook hw02_EDA.ipynb
```