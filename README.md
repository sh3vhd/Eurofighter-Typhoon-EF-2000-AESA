# EUROFIGHTER TYPHOON EF-2000 — Interactive Website

> Интерактивный информационный сайт / Interactive informational website

---

## 🇷🇺 README — РУССКИЙ

### Описание проекта

Интерактивный веб-сайт, посвящённый многоцелевому истребителю четвёртого поколения+ Eurofighter Typhoon EF-2000 с радаром AESA Captor-E. Сайт создан в образовательных целях и использует исключительно открытые источники данных.

### Возможности

- **3D модель самолёта** — wireframe-рендеринг на HTML5 Canvas
  - Вращение мышью (перетаскивание)
  - Масштабирование колесом мыши
  - Панорамирование (Shift + перетаскивание)
  - Касания на мобильных устройствах (щипок для зума)
  - Предустановленные виды: спереди, сбоку, сверху
  - Авто-вращение с возможностью отключения
  - HUD-дисплей углов поворота и масштаба

- **Технические характеристики (ТТХ)** — три вкладки:
  - Общие данные (производитель, вес, точки подвески)
  - Лётные характеристики (скорость, потолок, радиус)
  - Авионика (радар AESA, IRST PIRATE, HMD Striker II, РЭБ DASS)

- **Сравнение с конкурентами** — Typhoon vs F-35A vs Rafale F4 vs Gripen E vs Су-35С:
  - Таблица с цветовой индикацией (зелёный = лучший, красный = слабый)
  - Столбчатые диаграммы тяговооружённости и боевого радиуса
  - Радарные диаграммы «воздух–воздух» и «воздух–земля»

- **Вооружение** — 8 систем (Meteor, AIM-120, IRIS-T, Storm Shadow, Brimstone, Paveway IV, BK-27, B61-12)

- **Мультиязычность** — 4 языка: Русский / English / Deutsch / Français
  - Переключение одной кнопкой без перезагрузки страницы

### Структура файлов

```
eurofighter.html      — Основной файл сайта (всё в одном)
README.md             — Документация на RU + EN
```

### Техническая реализация

| Технология         | Назначение                              |
|--------------------|-----------------------------------------|
| HTML5 Canvas       | 3D wireframe рендеринг, радарные графики |
| Vanilla JavaScript | Логика вращения, локализация, анимации  |
| CSS3               | Стили, переменные, анимации появления   |
| Google Fonts       | Orbitron, Share Tech Mono, Rajdhani     |
| IntersectionObserver | Анимации появления при прокрутке      |

### 3D модель — подробно

Модель построена как wireframe на основе реальных пропорций EF-2000:

- **Фюзеляж**: 12 опорных точек по оси X=0, от носа (-9) до хвоста (+8)
- **ПГО (Canard)**: 6 точек, трапециевидная форма, стреловидность ≈55°
- **Дельта-крыло**: 10 точек, стреловидность ПК ≈55°, без горизонтального оперения
- **Хвостовые кили**: 8 точек, два наклонных киля
- **Двигатели/сопла**: 6 точек, два двигателя EJ200
- **Воздухозаборники**: 8 точек, два подфюзеляжных канала

Алгоритм рендеринга:
1. Поворот по оси Y (рыскание) и X (тангаж) через матрицы поворота
2. Ортографическая проекция 3D → 2D
3. Псевдо-освещение через яркость, зависящую от Z-координаты
4. Полупрозрачная заливка основных поверхностей

### Как запустить

Откройте файл `eurofighter.html` в любом современном браузере. Не требует сервера, зависимостей или установки.

```bash
# Вариант 1: просто открыть файл
open eurofighter.html

# Вариант 2: локальный сервер
python3 -m http.server 8080
# затем перейти на http://localhost:8080/eurofighter.html
```

### Требования к браузеру

- Chrome 80+ / Firefox 75+ / Safari 14+ / Edge 80+
- JavaScript должен быть включён
- Интернет-соединение требуется только для загрузки шрифтов Google

### Источники данных

Все данные взяты из открытых источников:
- Jane's All the World's Aircraft
- Официальные пресс-релизы Eurofighter GmbH
- NATO unclassified documents
- Wikipedia (en)

> ⚠️ Некоторые технические параметры засекречены. Представленные данные — официальные или оценочные из открытых источников.

### Лицензия

Создано в образовательных целях. Данные из открытых источников.

---

## 🇬🇧 README — ENGLISH

### Project Description

An interactive website dedicated to the Eurofighter Typhoon EF-2000 fourth-generation+ multirole fighter featuring the AESA Captor-E radar. Built for educational purposes using exclusively open-source data.

### Features

- **3D Aircraft Model** — wireframe rendering on HTML5 Canvas
  - Mouse drag rotation
  - Mouse wheel zoom
  - Pan mode (Shift + drag)
  - Mobile touch support (pinch to zoom)
  - Preset views: front, side, top
  - Auto-rotation with toggle
  - HUD display of rotation angles and zoom level

- **Technical Specifications** — three switchable tabs:
  - General data (manufacturer, weight, hardpoints)
  - Flight performance (speed, ceiling, radius)
  - Avionics (AESA radar, PIRATE IRST, Striker II HMD, DASS EW)

- **Competitor Comparison** — Typhoon vs F-35A vs Rafale F4 vs Gripen E vs Su-35S:
  - Color-coded table (green = best, red = poor)
  - Bar charts for thrust-to-weight and combat radius
  - Spider/radar charts for air-to-air and air-to-ground roles

- **Weapons** — 8 systems (Meteor, AIM-120, IRIS-T, Storm Shadow, Brimstone, Paveway IV, BK-27, B61-12)

- **Multilingual UI** — 4 languages: Russian / English / Deutsch / Français
  - One-click switching, no page reload

### File Structure

```
eurofighter.html      — Main site file (self-contained, all-in-one)
README.md             — Documentation in RU + EN
```

### Technical Implementation

| Technology         | Purpose                                  |
|--------------------|------------------------------------------|
| HTML5 Canvas       | 3D wireframe rendering, radar charts     |
| Vanilla JavaScript | Rotation logic, i18n, animations         |
| CSS3               | Styles, custom properties, scroll reveal |
| Google Fonts       | Orbitron, Share Tech Mono, Rajdhani      |
| IntersectionObserver | Scroll-triggered animations           |

### 3D Model — Details

The model is a wireframe based on real EF-2000 proportions:

- **Fuselage**: 12 key vertices along centerline X=0, nose (-9) to tail (+8)
- **Canard foreplanes**: 6 vertices, trapezoidal, LE sweep ≈55°
- **Delta wing**: 10 vertices, LE sweep ≈55°, no horizontal tail (pure delta)
- **Twin tail fins**: 8 vertices, two canted vertical stabilisers
- **Engine nozzles**: 6 vertices, twin EJ200 positions
- **Chin intakes**: 8 vertices, twin underfuselage intake channels

Rendering algorithm:
1. Rotate around Y axis (yaw) then X axis (pitch) via rotation matrices
2. Orthographic projection 3D → 2D
3. Pseudo-lighting via Z-depth-dependent brightness
4. Semi-transparent fills for main aerodynamic surfaces

### How to Run

Open `eurofighter.html` in any modern browser. No server, dependencies, or installation required.

```bash
# Option 1: open directly
open eurofighter.html

# Option 2: local server
python3 -m http.server 8080
# then visit http://localhost:8080/eurofighter.html
```

### Browser Requirements

- Chrome 80+ / Firefox 75+ / Safari 14+ / Edge 80+
- JavaScript must be enabled
- Internet connection required only for Google Fonts loading

### Code Structure

The JavaScript is organised into 6 clearly commented blocks:

| Block | Description                                  |
|-------|----------------------------------------------|
| 1     | Localisation — all UI strings in 4 languages |
| 2     | 3D Viewer — model geometry, rotation, render |
| 3     | Radar Charts — spider chart drawing          |
| 4     | Tabs — specs panel switching                 |
| 5     | Scroll Reveal — IntersectionObserver setup   |
| 6     | Initialization — default language, DOMReady  |

### Data Sources

All data from open sources:
- Jane's All the World's Aircraft
- Official Eurofighter GmbH press releases
- NATO unclassified documents
- Wikipedia (en)

> ⚠️ Some technical parameters are classified. Data shown is either officially released or estimated from open sources.

### License

Created for educational purposes. Data from open sources.

---

*Eurofighter Typhoon EF-2000 — AESA Captor-E Variant — Interactive Reference*
