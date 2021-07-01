| Deadline  | Folder & Branch name |
|-----------|-------------|
| 23:59 ДД.ММ.2021 | match-match-game |

### Match-Match Game 

## Задача

Ваша задача реализовать игру match-match. Игра часто используется для тренировки памяти. Игровое поле состоит из карточек
с разными рисунками на обратной стороне. Перед началом игровой сессии игроку показывают расположение всех парных карточек, по
истечению 30 секунд их скрывают. Победа засчитывается когда найдены все пары карточек.

### UX прототип

[Базовый UX прототип в figma](https://www.figma.com/file/nE1hG7VIpX8mQ0BbPEF29I/Match-match-game?node-id=1%3A1960)
Дизайн можно менять любым образом, мобильная версия не требуется.  
Разрешается использовать любые препроцессоры.

## Требования к функционалу приложения

* Имя базы данных indexedDb должно соответствовать github-name студента
* Тег body в html документе должен оставаться пустым.
* В приложении должно быть следующие страницы: 
    - Settings
    - About Game
    - Best score
* На странице About Game должна быть представлена краткая инструкция по началу игры
* Приложение должно быть SPA - Генерация новых страниц должна быть реализована через javascript, перезагрузок страниц не должно быть (Перезагрузки инициализируемые из кода для сброса js состояния, например для сброса состояния игры считаются хаком и штрафуются ).
* На странице Best score должен отображаться топ 10 игроков.
* На странице Settings должны находится настройки приложения. Допускаются любые настройки, но две базовые нельзя игнорировать:
    - Настройка сложности игры (4х4, 6х6, 8х8)
    - Настройка типов карточек для сравнений (можно использовать любые типы. Пример: Животные, автомобили и т.п.)

* В приложение должен быть header в котором должны быть реализованна маршрутизация между страницами.
* Активный роут должен быть выделен.
* На главной странице должна быть возможность зарегистрироваться как новый игрок.
* При регистрации должна быть следующее правило проверки вводимых значений:

Имя: 

    - Имя не может быть пустым.
    - Имя не может состоять из цифр.
    - Имя не может содержать служебные символы (~ ! @ # $ % * () _ — + = | : ; " ' ` < > , . ? / ^).

Фамилия: 

    - Фамилия не может быть пустой.
    - Фамилия не может состоять из цифр.
    - Фамилия не может содержать служебные символы. (~ ! @ # $ % * () _ — + = | : ; " ' ` < > , . ? / ^)

email: 

    - email не может быть пустым.
    - должен соответствовать стандартному правилу формированию email [RFC](https://en.wikipedia.org/wiki/Email_address#Standards_documents)

Форма в целом: 

    - Возможно использование любого языка для ввода имени и фамилии.
    - Колличество символов не должно превышать 30 символов включая пробелы
    - В случае несоответствия любого из вышеуказанных правил, необходимо блокировать кнопку создания пользователя
    - Все неправильные поля должны быть подсвечены и иметь соответствующие сообщения об ошибках.
    - После нажатия на кнопку создания игрока страница не должна перезагружаться.
    - После нажатия на кнопку cancel вся ранее заполненная информация должна быть сброшена.

* Если все данные игрока корректны, все правильно заполненные поля должны быть помеченные как правильные.
* После регистрации игрока в header должна появится кнопка позволяющая начать игру
* После нажатия на кнопку старт должен начинаться игровой цикл
* У игрока должна быть возможность остановить игру. 
* Расчет очков игрока должен производиться по следующей формуле: (количество сравнений - количество ошибочных сравнений) * 100 - (время прошедшее с начала в секундах) * 10. При этом количество очков не должно быть меньше 0.  
* На игровом поле должен присутствовать таймер.
* В случае несовпадения карточек, неправильная пара должна быть подсвечена красным.
* Совпавшие пары должны подсвечиваться зеленым.
* После нахождения всех совпадений необходимо показать модальное окно с поздравлениями. После клика на кнопку "ОК" в этом окне
приложение должно перейти на страницу рекордов.

### Нефункциональные требования
#### eslint
`eslint` должен быть настроен.
Запрещено использовать какие-либо аннотации, отключающие правила `eslint` вида `// eslint-disable`

- `eslint` включен в` package.json`,
- вы должны использовать конфигурацию `eslint-config-airbnb-typescript/base`
- весь код должен быть проверен
- проверка eslint выполняется запуском команды `npm run lint`
- должен быть подключен `prettier`

#### Ограничения
- Код должен быть написан на typescript.
- Проект должен использовать webpack.
- Задание должно работать в Chrome
- Использование material design или bootstrap допускается
- Вы НЕ МОЖЕТЕ использовать какие-либо SPA фреймворки, такие как Angular / React / Vue
- Вы можете общаться, переписываться в чате, гуглить и использовать stackoverflow
- Вы можете использовать lodash.js
- Данные должны храниться в indexedDb
- Запрещается обертки indexedDb.

## Требования к коммитам, PR и репозиторию

[Общие требования из stage 2](https://github.com/rolling-scopes-school/docs/blob/master/docs/stage2.md).

## Оценка

Максимальный балл - **160**

### Cross-check review

- [ ] **+10** - Верстка содержит все описанные в требованиях блоки
- [ ] **+20** - Соблюдены все требования к валидации полей для регистрации игрока в приложении.
- [ ] **+20** - Реализован игровой цикл.
- [ ] **+10** - Реализована таблица рекордов.
- [ ] **+10** - Реализована страница settings.
- [ ] **+10** - Реализована страница about game.
- [ ] **+30** - Реализована механика добавления аватара игрока, который хранится в indexedDb в base64 формате и отображается в header и на странице рекордов.  

Итого: **110**

## Cross-check review (Штрафы)
- [ ] **-30** - Отсутствует или не соответствует требованиям валидация формы добавления пользователя.
- [ ] **-10** - Отсутствуют анимации при повороте карточек в игре.

### Проверка задания ментором
- [ ] **+10** - Приложение разбито на отдельные логические модули/слои, повторяющиеся части вынесены в shared.
- [ ] **+10** - В приложении отсутствую магические цифры и строки.
- [ ] **+10** - Методы и функции не превышают 100 строк.
- [ ] **+10** - Имена переменных и функций четко говорят о содержащихся в них данных
- [ ] **+10** - Дублирование кода (Функций и методов) сведено к минимуму

Итого: **50**

### Проверка задания ментором (Штрафы)

- [ ] **-30** - `eslint` не настроен 
- [ ] **-10** - `prettier` не настроен 
- [ ] **-10** Данные хранятся не в indexedDb 
- [ ] **-50** в коде использованы команды как либо воздействующие на `eslint`, вроде `// eslint-disable`
- [ ] **-100** Не использован typescript или используется тип any в typescript коде
- [ ] **-20** Требования к коммитам, репозиторию и PR не выполнены
- [ ] **-20** В приложении отсутствует разбитие на логические модули 
- [ ] **-10** Используется обертка над indexedDb.
- [ ] **-20** в теге body в index.html есть html теги (более одного).
- [ ] **-20** Приложение не SPA (Имеются перезагрузки страницы инициализируемые напрямую из кода).
- [ ] **-30** Имя базы данных indexedDb не соответствует github-name студента


## Дополнительная информация
- загрузка изображения на canvas - https://developer.mozilla.org/ru/docs/Web/API/CanvasRenderingContext2D/drawImage
- indexedDb API - https://developer.mozilla.org/ru/docs/Web/API/IndexedDB_API
- typescript bootstrap tools - https://www.typescriptlang.org/docs/bootstrap
- пример js роутера - https://medium.com/javascript-by-doing/create-a-modern-javascript-router-805fc14d084d
- официальная документация typescript - https://www.typescriptlang.org/
- нативная валидация форм с помощью javascript - https://developer.mozilla.org/ru/docs/Learn/Forms/Form_validation
- html form documentation - https://www.w3schools.com/html/html_forms.asp
- Паки изображений для карточек 
    - https://www.flaticon.com/packs/search?word=animals 
    - https://unsplash.com/s/photos/pack-animal 
    - https://www.shutterstock.com/search/pack+animals 
    - https://all-free-download.com/free-photos/pack-animal.html