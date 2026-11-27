# DS_SF_Selery

Проект по анализу данных о резюме соискателей: очистка и преобразование признаков, исследовательский анализ и визуализация зарплат.

## Структура репозитория

| Файл / папка | Описание |
|---|---|
| `project.ipynb` | Основной ноутбук: загрузка, очистка, преобразование данных, анализ |
| `plots/` | Интерактивные графики Plotly в формате HTML |
| `README.md` | Описание проекта |

## Данные

Файл `data.csv` с резюме соискателей. Основные признаки:

- Пол, возраст
- Город, переезд, командировки
- Образование и ВУЗ
- Опыт работы
- Желаемая зарплата, занятость, график работы

> Файлы с данными в репозиторий не включены. Чтобы запустить ноутбук, положите `data.csv` и `ExchangeRates.csv` рядом с `project.ipynb`.
Ссылка для скачивания: 
1. https://drive.google.com/file/d/16ebmDGTYLM435Q1txVnkhcrH20nvpJIB/view?usp=sharing
2. https://drive.google.com/file/d/1-I1BUD0JwcKFVGDyZqZR-0UtOQReryyM/view?usp=sharing
## Что сделано

1. **Исследование структуры данных**: типы, пропуски (`data.info()`).
2. **Преобразование признаков**:
   - `Пол, возраст` → отдельные признаки «Пол» (М/Ж) и «Возраст» (целое число);
   - `Образование и ВУЗ` → «Образование» (высшее, неоконченное высшее, среднее специальное, среднее);
   - `Опыт работы` → опыт в месяцах;
   - `Город, переезд, командировки` → «Город» (Москва, Санкт-Петербург, город-миллионник, другие), готовность к переезду и к командировкам.
3. **Очистка данных**: удаление выбросов (по возрасту и зарплате).
4. **Визуализация**: распределения признаков, медианная зарплата по категориям, зависимости между признаками.

## Графики

Все графики интерактивные (Plotly), открываются в браузере через GitHub Pages.

### Распределения

| График | Ссылка |
|---|---|
| Гистограмма возраста | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/age_histogram.html) |
| Коробчатая диаграмма возраста | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/age_boxplot.html) |
| Гистограмма опыта работы | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/experience_histogram.html) |
| Коробчатая диаграмма опыта работы | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/experience_boxplot.html) |
| Гистограмма желаемой зарплаты | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/salary_histogram.html) |
| Коробчатая диаграмма желаемой зарплаты | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/salary_boxplot.html) |

### Зарплата в разрезе категорий

| График | Ссылка |
|---|---|
| Медианная зарплата по виду занятости | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/salary_by_employment.html) |
| Медианная зарплата по графику работы | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/salary_by_schedule.html) |
| Медианная зарплата по образованию | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/salary_by_education.html) |
| Медианная зарплата по городам | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/salary_by_city_bar.html) |
| Распределение зарплаты по городам | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/salary_by_city_boxplot.html) |
| Медианная зарплата по готовности к переезду и командировкам | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/salary_by_relocation_trips.html) |

### Взаимосвязи признаков

| График | Ссылка |
|---|---|
| Зависимость опыта работы от возраста | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/experience_vs_age_scatter.html) |
| Средняя зарплата по возрасту и образованию (тепловая карта) | [открыть](https://realeastboy.github.io/DS_SF_Selery/plots/salary_age_education_heatmap.html) |

## Основные выводы

- Медианная зарплата различается умеренно: от 40k (стажировка) до 60k (полная занятость, проектная работа).
- Удалённая работа оплачивается на уровне полного дня (60k).
- Гибкий график и частичная занятость дают чуть более низкую медиану (50–55k).
- Заметной надбавки за сменный график и вахту в медиане нет (50k).

Ограничения: медиана не показывает разброс и размер групп, а выводы описывают корреляцию, а не причинно-следственную связь.

## Запуск

```bash
pip install pandas numpy plotly seaborn matplotlib jupyter
jupyter notebook project.ipynb
```

## Стек

Python, pandas, NumPy, Plotly, seaborn, matplotlib.