# SCSS Font-Face Mixin

Универсальный SCSS миксин для подключения любых шрифтов с поддержкой:

- Static fonts (woff, woff2, ttf, otf)
- Variable fonts (woff2-variations)
- Локальных шрифтов через `local()`
- Подключения через Google Fonts API
- Fallback шрифтов
- Subsetting (`latin`, `cyrillic`, `greek`) с автоматическим `unicode-range`
- Смарт `font-display` с глобальным дефолтным значением

---

## 🔹 Установка

Скопируйте файл `_font-face.scss` в ваш проект и импортируйте в основной SCSS файл:

```scss
@import "path/to/_font-face.scss";
```

## 🔹 Использование миксина
- Минимальный вызов

```scss
@include font-face("Roboto", "roboto-regular");
```
- Локальный шрифт с fallback

```scss
@include font-face(
  $family: "Roboto Flex",
  $file: "roboto-flex",
  $path: "/fonts/",
  $weight: "100 1000",
  $stretch: "75% 125%",
  $variable: true,
  $fallback: sans-serif,
  $local: "Roboto Flex Local",
  $subset: latin
);
```

- Подключение Google Fonts

```scss
@include font-face(
  $family: "Open Sans",
  $weight: "400;700",
  $display: swap,
  $google: true,
  $subset: cyrillic
);
```

- Variable font без subset

```scss
@include font-face(
  $family: "Lato Variable",
  $file: "lato-variable",
  $weight: "200 900",
  $stretch: "80% 120%",
  $variable: true
);
```

## 🔹 Параметры миксина

| Параметр        | Тип           | Описание                              |
| --------------- | ------------- | ------------------------------------- |
| \$family        | String        | Имя шрифта (обязательный)             |
| \$file          | String        | Имя файла без расширения              |
| \$path          | String        | Путь к файлам                         |
| \$format        | String        | Формат файла (`woff2` по умолчанию)   |
| \$weight        | Number/String | Вес или диапазон (`100 900`)          |
| \$style         | String        | Стиль шрифта (`normal`, `italic`)     |
| \$stretch       | String/Number | Ширина (`normal`, `%`, диапазон)      |
| \$unicode-range | String        | Диапазон Unicode                      |
| \$variable      | Bool          | Variable font (`true`)                |
| \$display       | String        | `font-display` (смарт-логика)         |
| \$fallback      | String        | Fallback шрифт (`sans-serif`)         |
| \$local         | String        | Локальное имя шрифта                  |
| \$google        | Bool          | Подключение через Google Fonts API    |
| \$subset        | String        | Subset (`latin`, `cyrillic`, `greek`) |

## 🔹 Особенности

1. Автоматический unicode-range при указании subset
2. Смарт font-display: $display → $font-display-default → swap
3. Локальный шрифт через local()
4. Fallback шрифт при необходимости
5. Поддержка Google Fonts с генерацией @import url(...)
6. Variable fonts с диапазонами weight и stretch

## 🔹 Примеры

```scss
// Google Font с subset и display
@include font-face(
  $family: "Roboto",
  $weight: "400;700",
  $display: swap,
  $google: true,
  $subset: cyrillic
);

// Локальный variable font с fallback и subset
@include font-face(
  $family: "Roboto Flex",
  $file: "roboto-flex",
  $path: "/fonts/",
  $weight: "100 1000",
  $stretch: "75% 125%",
  $variable: true,
  $fallback: sans-serif,
  $local: "Roboto Flex Local",
  $subset: latin
);
```

## 🔹 Лицензия

MIT License. Можно использовать как в коммерческих, так и в личных проектах.
