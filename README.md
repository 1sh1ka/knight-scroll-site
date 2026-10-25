# Последний рыцарь

Кинематографичный сайт: прокрутка колесом мыши или пальцем управляет фильмом — битва → рыцарь в поле → всадник над долиной.

Это готовая статическая сборка для GitHub Pages: залейте содержимое этой папки в корень репозитория (или в папку `docs/`) и включите Pages в настройках (Settings → Pages → Deploy from a branch). Все пути относительные, поэтому сайт работает по адресу вида `https://<user>.github.io/<repo>/`.

- `index.html`, `assets/` — страница, стили, скрипт, шрифты (Yeseva One и Manrope, лицензия SIL OFL)
- `frames/d/` — 600 кадров для ПК (1280×720, WebP)
- `frames/m/` — 600 кадров для телефона (540×960, WebP)
- `.nojekyll` — отключает обработку Jekyll

## Как выложить на GitHub Pages (бесплатно)

В архиве 1216 файлов (из них 1200 кадров в `frames/`). Веб-загрузка GitHub принимает **не больше 100 файлов за раз**, поэтому удобнее всего способ А.

### Способ А — GitHub Desktop (рекомендуется, всё за один раз)
1. Установите GitHub Desktop (desktop.github.com) и войдите в свой аккаунт.
2. File → New repository → имя, например `knight-scroll` → Create repository.
3. Repository → Show in Explorer/Finder — откроется папка репозитория. Скопируйте в неё **всё содержимое архива** (`index.html` должен лежать прямо в корне, рядом с папками `assets` и `frames`; файл `.nojekyll` тоже — он скрытый, включите показ скрытых файлов).
4. В GitHub Desktop: внизу слева напишите «Сайт» → Commit to main → Publish repository (снимите галочку «Keep this code private», если аккаунт бесплатный — Pages на бесплатном тарифе работает только для публичных репозиториев).
5. Дальше шаг «Включить Pages» ниже.

### Способ Б — через браузер, партиями
1. github.com → New repository → имя `knight-scroll`, Public → Create repository.
2. «uploading an existing file» (или Add file → Upload files): перетащите `index.html`, `README.md`, `favicon.png`, `apple-touch-icon.png`, `.nojekyll` и папку `assets` → Commit changes.
3. Кадры (1200 файлов) заливайте партиями по 100. Окно загрузки сохраняет папки, поэтому: на компьютере создайте пустую папку `frames` с подпапкой `d`, положите в `frames/d` кадры `000–099`, перетащите папку `frames` в окно Add file → Upload files → Commit changes. Затем очистите `frames/d`, положите `100–199`, снова загрузите — и так до `599`. То же самое для `frames/m`. Всего 12 партий. В итоге в репозитории должны быть пути `frames/d/000.webp` … `frames/d/599.webp` и `frames/m/000.webp` … `frames/m/599.webp`.
4. Проверьте, что в репозитории есть `.nojekyll`; если веб-загрузка его пропустила — Add file → Create new file → имя `.nojekyll`, содержимое пустое → Commit.

### Включить Pages
Settings → Pages → Build and deployment → Source: **Deploy from a branch** → Branch: **main**, папка **/ (root)** → Save. Через 1–3 минуты сайт откроется по адресу `https://<ваш-логин>.github.io/knight-scroll/`.
