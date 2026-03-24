# Как выложить CyberGipsy на GitHub Pages с доменом cybergipsy.ru

## Шаг 1 — Создай репозиторий

1. Зайди на https://github.com/new
2. Имя репозитория: `cybergipsy`
3. Выбери **Public**
4. Нажми **Create repository**

## Шаг 2 — Загрузи файлы

Вариант А — через браузер (просто):

1. В новом репо нажми **uploading an existing file**
2. Перетащи 3 файла из скачанной папки:
   - `index.html`
   - `CNAME`
   - `README.md`
3. Нажми **Commit changes**

Вариант Б — через терминал:

```bash
cd cybergipsy-site
git init
git add .
git commit -m "Initial commit: CyberGipsy landing"
git branch -M main
git remote add origin https://github.com/ТВОЙ_USERNAME/cybergipsy.git
git push -u origin main
```

## Шаг 3 — Включи GitHub Pages

1. Зайди в **Settings** → **Pages** (в меню слева)
2. Source: выбери **Deploy from a branch**
3. Branch: выбери **main** / **(root)**
4. Нажми **Save**
5. GitHub увидит файл CNAME и автоматически привяжет домен cybergipsy.ru

## Шаг 4 — Настрой DNS у регистратора домена cybergipsy.ru

Зайди в панель управления DNS (там, где покупал домен) и добавь записи:

### Для корневого домена (cybergipsy.ru):

Добавь 4 записи типа **A**:

| Тип | Хост | Значение |
|-----|------|----------|
| A   | @    | 185.199.108.153 |
| A   | @    | 185.199.109.153 |
| A   | @    | 185.199.110.153 |
| A   | @    | 185.199.111.153 |

### Для www (www.cybergipsy.ru):

| Тип   | Хост | Значение |
|-------|------|----------|
| CNAME | www  | ТВОЙ_USERNAME.github.io |

> Замени `ТВОЙ_USERNAME` на свой логин GitHub.

## Шаг 5 — Включи HTTPS

1. Подожди 5–30 минут, пока DNS пропишется
2. Зайди в **Settings** → **Pages**
3. Поставь галочку **Enforce HTTPS**

## Готово!

Через несколько минут сайт будет доступен по адресу:
- https://cybergipsy.ru
- https://www.cybergipsy.ru

---

### Если что-то не работает:

- DNS может распространяться до 24 часов (обычно 5–30 мин)
- Проверь DNS: https://dnschecker.org/#A/cybergipsy.ru
- В Settings → Pages должно быть зелёное сообщение "Your site is live at..."
