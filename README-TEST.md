# Тестовая сборка для SCSS Font-Face Mixin

Быстрая сборка на Vite для тестирования миксина `@font-face` с примерами использования.

## 🚀 Быстрый старт

1. **Установка зависимостей:**
```bash
npm install
```

2. **Запуск dev-сервера:**
```bash
npm run dev
```

3. **Откройте браузер:** http://localhost:3000

## 📁 Структура

```
├── src/
│   ├── scss/
│   │   └── main.scss          # Основной SCSS файл с примерами
│   └── index.html             # HTML с тестовыми примерами
├── dist/                      # Скомпилированные файлы
├── vite.config.js            # Vite конфигурация
├── package.json              # Зависимости
└── _font-face.scss          # Твой миксин
```

## 🔧 Команды

- `npm run dev` - запуск dev-сервера с HMR
- `npm run build` - продакшн сборка
- `npm run preview` - предпросмотр продакшн сборки

## 🧪 Что тестируется

1. **Google Fonts** - Roboto (cyrillic) и Open Sans (latin)
2. **Локальные шрифты** - с fallback и local()
3. **Variable fonts** - с диапазонами weight и stretch
4. **font-display** - проверка в DevTools
5. **unicode-range** - автоматическая генерация для subset
6. **Fallback шрифты** - корректная работа

## 🔍 Проверка в DevTools

1. **Network** - посмотрите загрузку Google Fonts
2. **Elements** - найдите @font-face правила
3. **Console** - проверьте отсутствие ошибок

## 📝 Изменение примеров

Редактируй `src/scss/main.scss` - Vite автоматически перекомпилирует и обновит браузер через HMR (Hot Module Replacement).
