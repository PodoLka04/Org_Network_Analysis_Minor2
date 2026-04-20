# 🌐 Language / Язык

[🇬🇧 English](#english) | [🇷🇺 Русский](#russian)

---

## <a name="russian"></a> 

# Взаимосвязи в компании: сетевой анализ email-переписки

## 📌 О проекте

Проект выполнен в рамках курса **"Технологии анализа данных"** (Майнор НИУ ВШЭ, 2 семестр).  

**Задача:**  
Изучить структуру взаимодействия сотрудников компании на основе данных об email-переписке (авторы, адресаты, копии).  

**Данные:**  
- 184 сотрудника  
- >120 тыс. писем за 2,5 года  
- В рамках проекта анализируется **один месяц** (период задан преподавателем)

> ⚠️ **Важно:** исходные данные хранились на университетском сервере, доступ к которому в настоящее время отсутствует.  
> Поэтому **Rmd-код не может быть выполнен**, но **результаты исследования сохранены в HTML-отчёте**.

---

## 📁 Содержимое репозитория

| Файл | Описание |
|------|----------|
| `report.html` | **Готовый HTML-отчёт** с визуализациями, расчётами и выводами |
| `analysis.Rmd` | Исходный код на R (не исполняется без доступа к данным) |
| `Задание.png` | Скриншот задания с платформы Smart LMS |
| `Оценка_Отзыв.png` | Скриншот оценки с отзывом с той же платформы |

---

## 🔍 Что было сделано

- Построена и визуализирована сеть взаимодействий за анализируемый месяц  
- Рассчитаны **меры центральности**:  
  - степень (degree)  
  - посредничество (betweenness)  
  - близость (closeness)  
- Выявлены **сообщества** двумя методами:  
  - edge.betweenness  
  - walktrap (выбран как более точный по modularity)  
- Проведён **продвинутый анализ**:  
  - тест ассортативности (влияние должности на связи)  
  - выявление вершин-мостов между сообществами  
- Сформулированы и проверены **два исследовательских вопроса** (см. отчёт)

### Исследовательские вопросы

1. **Кто является «мостами» между сообществами?**  
   → Найдены вершины 6 и 67 (в отчёте приведена их роль и интерпретация)

2. **Влияет ли одинаковая должность на формирование связей?**  
   → Тест ассортативности показал, что **не влияет** (p-value = 0.94, нулевая гипотеза не отвергается)

---

## 🧑‍💼 Анализ конкретного сотрудника

**Сотрудник:** `Lawrence May` (larry.may)  
**Должность:** Director  
**Номер вершины:** 85

### Результаты:

- **Центральность:** выше средней по сети (и по степени, и по посредничеству)  
- **Сообщество:** принадлежит к **сообществу №3** (всего 9 человек)  
- **Интерпретация:** Lawrence May — значимый участник сети, имеет влияние внутри своего сообщества и за его пределами. Через его ближайшее окружение можно оказывать влияние на него самого.

---

## 📊 Основные выводы

1. Выявлены сотрудники с максимальными показателями центральности — ключевые узлы для внутренних коммуникаций.
2. Обнаружены два человека-«моста» (вершины 6 и 67), связывающие разные сообщества. Они играют важную роль в распространении информации и сохранении целостности сети.
3. Должность **не влияет** на формирование email-связей (нет «кластеризации» по должностям).
4. Lawrence May занимает важное место в сети, его окружение — 8 человек из того же сообщества.

---

## 📎 Оценка и отзыв преподавателя

- **Оценка:** 7.70 / 10.00  
- **Преподаватель:** Суворова Алёна Владимировна  
- **Замечание:**  
  > *Много warnings, присутствуют только технические описания. Как интерпретировать для реального мира? Первый исследовательский вопрос сформулирован не как вопрос, это больше какой-то investigating analysis.*

В текущей версии отчёта исследовательские вопросы переформулированы и добавлены содержательные интерпретации.

---

## 🚀 Как просмотреть результат

Просто откройте файл **`report.html`** в любом браузере.

---

## 🛠 Инструменты

- R  
- igraph  
- tidyverse (dplyr, ggplot2, tidyr)  
- ggraph  
- wordcloud2  
- lubridate

---

## 📌 Автор

Подолин Дмитрий  
НИУ ВШЭ, курс "Технологии анализа данных"

---

## <a name="english"></a> 

# Company Interactions: Email Network Analysis

## 📌 About the project

The project was completed as part of the **"Data Analysis Technologies"** course (HSE Minor, 2nd semester).

**Task:**  
Study the interaction structure of company employees based on email correspondence data (authors, recipients, carbon copies).

**Data:**  
- 184 employees  
- >120,000 emails over 2.5 years  
- The project analyzes **one month** (period specified by the instructor)

> ⚠️ **Important:** The original data was stored on a university server that is currently inaccessible.  
> Therefore, **the Rmd code cannot be executed**, but the **research results are preserved in the HTML report**.

---

## 📁 Repository contents

| File | Description |
|------|-------------|
| `report.html` | **Complete HTML report** with visualizations, calculations, and conclusions |
| `analysis.Rmd` | R source code (cannot be executed without data access) |
| `Задание.png` | Screenshot of the assignment from the Smart LMS platform |
| `Оценка_Отзыв.png` | Screenshot of the grade and feedback from the same platform |

---

## 🔍 What was done

- Built and visualized the interaction network for the analyzed month  
- Calculated **centrality measures**:  
  - degree centrality  
  - betweenness centrality  
  - closeness centrality  
- Identified **communities** using two methods:  
  - edge.betweenness  
  - walktrap (selected as more accurate based on modularity)  
- Conducted **advanced analysis**:  
  - assortativity test (impact of position on connections)  
  - identification of bridge vertices between communities  
- Formulated and tested **two research questions** (see report)

### Research questions

1. **Who are the "bridges" between communities?**  
   → Vertices 6 and 67 were identified (their role and interpretation are provided in the report)

2. **Does having the same position affect connection formation?**  
   → The assortativity test showed **no effect** (p-value = 0.94, null hypothesis not rejected)

---

## 🧑‍💼 Analysis of a specific employee

**Employee:** `Lawrence May` (larry.may)  
**Position:** Director  
**Vertex number:** 85

### Results:

- **Centrality:** above average in the network (both degree and betweenness)  
- **Community:** belongs to **community #3** (only 9 people)  
- **Interpretation:** Lawrence May is a significant network participant with influence both within and outside his community. His close circle can be used to influence him.

---

## 📊 Key findings

1. Employees with maximum centrality scores were identified — key nodes for internal communications.
2. Two "bridge" individuals (vertices 6 and 67) connecting different communities were found. They play an important role in information dissemination and maintaining network integrity.
3. Position **does not affect** email connection formation (no clustering by position).
4. Lawrence May holds an important place in the network; his circle includes 8 people from the same community.

---

## 📎 Grade and instructor feedback

- **Grade:** 7.70 / 10.00  
- **Instructor:** Alena V. Suvorova  
- **Comment:**  
  > *Many warnings, only technical descriptions. How to interpret for the real world? The first research question is not formulated as a question, it's more like an investigating analysis.*

In the current version of the report, the research questions have been reformulated and meaningful interpretations have been added.

---

## 🚀 How to view the results

Simply open the **`report.html`** file in any browser.

---

## 🛠 Tools

- R  
- igraph  
- tidyverse (dplyr, ggplot2, tidyr)  
- ggraph  
- wordcloud2  
- lubridate

---

## 📌 Author

Dmitrii Podolin  
HSE University, "Data Analysis Technologies" course
