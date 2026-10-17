# PreJob — Tel-Ran hackathon (2023)

[English](README.md) | [Русский](README.ru.md)

A career video catalogue built for the Tel-Ran hackathon. Users can browse videos, search by title or profession, and select category filters. Our team won the hackathon.

A shared team project: [tel-ran-de/career_team_2](https://github.com/tel-ran-de/career_team_2).

## My role and team

I was responsible for the backend and worked with one other backend developer. The five-person team had two backend developers, two frontend developers and one tester.

The backend provides the REST API, database models and queries used by the React interface. It includes profession search, video search and category filtering, OpenAPI documentation and integration tests.

## Stack and structure

Java 19, Spring Boot 3.0.4, Spring Data JPA, H2, Gson, Lombok, OpenAPI, React 18 and SCSS.

| Path | Content |
| --- | --- |
| [backend](backend) | Spring Boot application and Maven configuration |
| [controllers](backend/src/main/java/de/telran/backend/controller) | Video, category and profession API |
| [entities](backend/src/main/java/de/telran/backend/entity) | Videos, professions and categories |
| [repositories](backend/src/main/java/de/telran/backend/repository) | Database access and search queries |
| [tests](backend/src/test/java/de/telran/backend) | Application and API integration tests |
| [backend/src/doc](backend/src/doc) | JavaDoc and architecture diagrams |
| [frontend](frontend) | React interface and reusable UI components |

## Run the backend

Install JDK 19 and Maven, with `java` and `mvn` available in your terminal.

```bash
git clone https://github.com/ivan-zamula/prejob-hackathon-2023-tel-ran.git
cd prejob-hackathon-2023-tel-ran
```

```bash
cd backend
mvn spring-boot:run
```

The default address is `http://localhost:8080`. The backend includes a bundled frontend. API documentation is available in [Swagger UI](http://localhost:8080/swagger-ui/index.html). Database settings and sample data are in [backend/src/main/resources](backend/src/main/resources); H2 runs in memory.

## Run the frontend separately

Install Node.js and npm. For local development, set `domain` in [domain.js](frontend/src/requests/domain.js) to `http://localhost:8080` and set the `proxy` field in [package.json](frontend/package.json) to the same address. Keep the backend running.

From the repository root:

```bash
cd frontend
npm ci
npm start
```

Open [http://localhost:3000](http://localhost:3000).

## API

| Method | Path | Purpose |
| --- | --- | --- |
| GET | `/video` | List videos |
| POST | `/video` | Search videos and apply category filters |
| GET | `/category` | List categories |
| GET | `/category_types` | List category groups |
| GET | `/profession` | List professions |
| GET | `/profession/search?name={value}` | Search professions |

The implementation and contributor notes are in the [backend source](backend/src/main/java/de/telran/backend). The repository preserves team authorship and the shared project history.
