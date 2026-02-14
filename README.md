# Формы Jira для Telegram-бота (GitHub Pages)

Один файл `jira_form.html` — Mini App с формами запросов в Jira. Открывается из бота по HTTPS.

## Что сделать, чтобы формы открывались из бота

### 1. Создать репозиторий на GitHub

- Зайди на [github.com](https://github.com) → **New repository**.
- Имя, например: `jira-form-bot` (или любое).
- **Public**, без README (или с — не важно).
- **Create repository**.

### 2. Залить файл в репозиторий

**Вариант А — через веб-интерфейс:**

1. В репозитории нажми **Add file** → **Upload files**.
2. Перетащи сюда файл `jira_form.html` из папки `jira-form-pages` (рядом с этим README).
3. **Commit changes**.

**Вариант Б — через Git в терминале:**

```bash
cd путь/к/папке/jira-form-pages
git init
git add jira_form.html
git commit -m "Add Jira form Mini App"
git branch -M main
git remote add origin https://github.com/ТВОЙ_ЛОГИН/jira-form-bot.git
git push -u origin main
```

(подставь свой логин и имя репозитория вместо `jira-form-bot`.)

### 3. Включить GitHub Pages

1. В репозитории: **Settings** → слева **Pages**.
2. В блоке **Build and deployment**:
   - **Source**: Deploy from a branch.
   - **Branch**: `main` (или `master`), папка **/ (root)**.
3. **Save**. Через 1–2 минуты сайт поднимется.

### 4. Узнать URL формы

Страница будет доступна по адресу:

- **https://ТВОЙ_ЛОГИН.github.io/ИМЯ_РЕПОЗИТОРИЯ/jira_form.html**

Пример: репозиторий `jira-form-bot`, логин `mycompany`:

- **https://mycompany.github.io/jira-form-bot/jira_form.html**

### 5. Прописать URL в боте

В проекте бота в файле **`.env`** добавь (или измени):

```env
JIRA_FORM_APP_URL=https://ТВОЙ_ЛОГИН.github.io/ИМЯ_РЕПОЗИТОРИЯ/jira_form.html
```

Подставь свой URL из шага 4. Перезапусти бота.

После этого по нажатию кнопок форм в Telegram будет открываться эта страница (Mini App), а не портал Jira.

---

Если правишь формы — меняй `jira_form.html` в этой папке, затем заливай обновлённый файл в тот же репозиторий (через сайт или `git add` → `commit` → `push`). Можно также держать актуальную копию в `gamelistBOT/webapp/jira_form.html` и при выкладке копировать оттуда в `jira-form-pages`.
