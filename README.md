# bushukovee-posts

Статьи для GitHub Pages. Рендер — [Quarto](https://quarto.org).

## Структура

```
.
├── _quarto.yml                 # конфиг сайта (navbar, тема, output-dir: _site)
├── index.qmd                   # листинг всех статей
├── about.qmd
├── posts/
│   └── <slug>/                 # slug статьи, напр. medgemma-install-and-test
│       ├── index.qmd           # сама статья (YAML: title, date, categories, slug)
│       └── media/              # медиафайлы только этой статьи
├── .github/workflows/pages.yml # сборка и деплой в GitHub Pages
└── _site/                      # результат рендера (не коммитится)
```

## Добавить статью

1. `mkdir -p posts/<slug>/media`
2. Создать `posts/<slug>/index.qmd` (см. пример в `posts/medgemma-install-and-test/index.qmd`)
3. Класть картинки/файлы в `posts/<slug>/media/`, в тексте ссылаться относительно: `media/screenshot.png`
4. Когда статья готова — убрать `draft: true`, иначе в публикацию не попадёт

## Локально

```bash
quarto preview
quarto render
```

## Публикация

Push в `master` → GitHub Actions (`quarto render` → deploy в Pages).
В настройках репозитория: Settings → Pages → Source: **GitHub Actions**.
