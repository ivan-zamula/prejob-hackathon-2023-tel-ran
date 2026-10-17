# PreJob — хакатон Tel-Ran (2023)

[English](README.md) | [Русский](README.ru.md)

Каталог видео о профессиях, созданный на хакатоне Tel-Ran. Пользователь может просматривать видео, искать их по названию или профессии и выбирать фильтры по категориям. Наша команда выиграла хакатон.

Этот репозиторий — мой форк общего проекта [tel-ran-de/career_team_2](https://github.com/tel-ran-de/career_team_2).

## Мой вклад и команда

Я отвечал за бэкенд и работал вместе с еще одним бэкенд-разработчиком. В команде было пять человек: два бэкенд-разработчика, два frontend-разработчика и тестировщик.

Бэкенд предоставляет REST API, модели данных и запросы для интерфейса на React. Он включает поиск профессий и видео, фильтрацию по категориям, документацию OpenAPI и интеграционные тесты.

## Стек и структура

Java 19, Spring Boot 3.0.4, Spring Data JPA, H2, Gson, Lombok, OpenAPI, React 18 и SCSS.

| Путь | Содержимое |
| --- | --- |
| [backend](backend) | Приложение Spring Boot и настройки Maven |
| [controllers](backend/src/main/java/de/telran/backend/controller) | API видео, категорий и профессий |
| [entities](backend/src/main/java/de/telran/backend/entity) | Видео, профессии и категории |
| [repositories](backend/src/main/java/de/telran/backend/repository) | Доступ к базе данных и поисковые запросы |
| [tests](backend/src/test/java/de/telran/backend) | Тесты приложения и интеграционные тесты API |
| [backend/src/doc](backend/src/doc) | JavaDoc и архитектурные схемы |
| [frontend](frontend) | Интерфейс React и общие компоненты UI |

## Запуск бэкенда

Установите JDK 19 и Maven; команды `java` и `mvn` должны быть доступны в терминале.

```bash
git clone https://github.com/ivan-zamula/prejob-hackathon-2023-tel-ran.git
cd prejob-hackathon-2023-tel-ran
```

```bash
cd backend
mvn spring-boot:run
```

Стандартный адрес — `http://localhost:8080`. Бэкенд включает готовую сборку frontend. Документация API доступна в [Swagger UI](http://localhost:8080/swagger-ui/index.html). Настройки базы и примеры данных находятся в [backend/src/main/resources](backend/src/main/resources); H2 работает в памяти.

## Отдельный запуск frontend

Установите Node.js и npm. Для локальной разработки задайте `domain` в [domain.js](frontend/src/requests/domain.js) равным `http://localhost:8080` и тот же адрес в поле `proxy` файла [package.json](frontend/package.json). Бэкенд должен быть запущен.

Из корня репозитория:

```bash
cd frontend
npm ci
npm start
```

Откройте [http://localhost:3000](http://localhost:3000).

## API

| Метод | Путь | Назначение |
| --- | --- | --- |
| GET | `/video` | Список видео |
| POST | `/video` | Поиск видео и фильтрация по категориям |
| GET | `/category` | Список категорий |
| GET | `/category_types` | Группы категорий |
| GET | `/profession` | Список профессий |
| GET | `/profession/search?name={value}` | Поиск профессий |

Реализация и сведения об участниках находятся в [исходниках бэкенда](backend/src/main/java/de/telran/backend). Форк сохраняет авторство команды и историю общего проекта.
