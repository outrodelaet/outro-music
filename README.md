# outro-music
an app where VK Music is separate from the social network
 # OUTRO MUSIC 0.1 — PC Music Edition

Эта сборка открывает **музыкальный раздел VK напрямую** (`https://vk.ru/audio`) в главном окне Windows-приложения.

## Что изменено

- Приложение стартует сразу с музыкального каталога VK.
- Вместо стартовой страницы `music.vk.com` открывается прямой адрес музыкального раздела `vk.ru/audio`.
- Добавлен адаптер интерфейса: он определяет левую социальную колонку по пунктам «Профиль», «Лента», «Мессенджер», «Друзья», «Сообщества» и «Фото», скрывает её и пытается растянуть музыкальную область на освободившееся место.
- Глобальная верхняя шапка VK также скрывается, если адаптер может надёжно распознать её по бренду VK и полю общего поиска.
- Адаптер повторно запускается после загрузки страницы и при изменениях интерфейса VK.
- Вход и само воспроизведение остаются на стороне сайта VK; приложение не извлекает аудиоссылки и не использует закрытый аудио API.
- Локальные аудиофайлы доступны отдельно через «Загрузить свои треки» и «Мои файлы».

## Запуск

1. Распакуйте архив в отдельную папку.
2. Убедитесь, что установлен Node.js LTS (с npm).
3. Запустите `install-and-run.bat`.
4. При первом запуске скрипт установит зависимости и проверит наличие `electron.exe`.

Если вы переносите `node_modules` из уже рабочей сборки, сначала закройте приложение, затем скопируйте эту папку в новую папку проекта и запустите `npm start`.

## Создание установщика

Запустите `build-installer.bat`. Готовый установщик появится в `release`.

## Важное ограничение

VK меняет HTML/CSS веб-интерфейса. Автоопределение социальной колонки основано на видимых названиях разделов и размерах DOM-элементов, а не на недокументированном аудио API. Если VK полностью изменит названия/структуру страницы, потребуется обновить адаптер. Некоторые страницы авторизации могут временно показывать собственную шапку VK, необходимую для входа.

# OUTRO MUSIC 0.1 — PC Music Edition

This build opens the **VK Music section directly** ([https://vk.ru/audio](https://vk.ru/audio)) in the main window of the Windows application.

## What's Changed

- The application launches directly into the VK Music catalog.
- Instead of the `music.vk.com` landing page, the application opens the direct VK Music URL: `vk.ru/audio`.
- Added a UI adapter that detects the left social sidebar using menu items such as "Profile", "Feed", "Messenger", "Friends", "Communities", and "Photos". It hides this sidebar and attempts to expand the music area to fill the available space.
- The global VK header is also hidden when the adapter can reliably identify it by the VK brand and global search field.
- The adapter runs again after the page loads and whenever the VK interface changes.
- Login and audio playback remain handled by the VK website. The application does not extract audio URLs or use VK's private audio API.
- Local audio files are available separately through "Upload Your Tracks" and "My Files".

## How to Run

1. Extract the archive into a separate folder.
2. Make sure Node.js LTS (including npm) is installed.
3. Run `install-and-run.bat`.
4. On the first launch, the script will install the dependencies and check whether `electron.exe` is present.

If you are copying `node_modules` from an already working build, close the application first, then copy that folder into the new project directory and run `npm start`.

## Building the Installer

Run `build-installer.bat`. The finished installer will be created in the `release` folder.

## Important Limitation

VK may change the HTML and CSS of its web interface. Automatic sidebar detection is based on visible menu labels and DOM element dimensions, not on an undocumented audio API. If VK completely changes the page structure or menu labels, the adapter will need to be updated.

Some authentication pages may temporarily display their own VK header, which is required for the login process.
