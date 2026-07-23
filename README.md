# 👋 Hi, I'm Muhammad Yassa

🎓 **Computer Science @ CUNY Queens College** · Expected May 2027
📍 **New York City**
💻 **Backend / Full-Stack Engineer** — moving toward data & AI engineering

I build production systems end to end: designing the API, writing the tests, running the pipeline, and shipping it to a server I maintain. I care most about the parts that don't demo well — idempotent pipelines, token rotation done correctly, caches that invalidate when they should.

---

## 🚀 Projects

### 🎬 [WatchMate](https://mywatchmate.us) — Movie & TV Tracking Platform
**Live:** [mywatchmate.us](https://mywatchmate.us) · **Code:** [github.com/muhammadyassa/WatchMate](https://github.com/muhammadyassa/WatchMate)

A full-stack media tracking application, built and deployed solo. Ran a three-week beta with 10 users who tracked 134 titles and logged 1,148 episode watches.

- **65 REST endpoints across 13 controllers** in Java 21 / Spring Boot, organized in vertical feature slices, documented with OpenAPI/Swagger
- **Asynchronous job processing** — `202 Accepted` + `Location`/`Retry-After` polling contract with a scheduled worker, moving multi-season TMDB hydration off the request thread
- **Stateless JWT auth with rotating refresh tokens** — SHA-256 hashed at rest, atomically rotated per use with ownership verification, BCrypt hashing, Bucket4j rate limiting
- **Redis caching layer** over the TMDB API with centralized eviction and explicit timeout/connection handling
- **CI/CD via GitHub Actions** — full JUnit 5 / Testcontainers suite (~90% line coverage, JaCoCo) on every push, deploying via Docker Compose to an OCI VM behind Caddy with automatic HTTPS
- **React 19 / TypeScript SPA** (Vite, TanStack Query, Zustand, Tailwind) with route-level code splitting and single-flight JWT refresh that deduplicates concurrent 401s

`Java 21` `Spring Boot` `Spring Security` `MySQL` `Redis` `Docker` `React` `TypeScript` `GitHub Actions`

---

### 🏙️ NYC Housing Intelligence Platform — *in progress*

Currently building a platform that makes NYC's public housing data actually usable. It ingests 311 service requests, HPD violations and complaints, and PLUTO tax-lot records, then resolves complaints to specific buildings so you can look up an address and see its real complaint history, open violations, and how it compares to similar buildings nearby.

The interesting problem is record linkage: 311 records carry a typed-in address string rather than a building ID, so matching them to real buildings takes address normalization, blocking, and fuzzy matching.

- Incremental, idempotent ETL over NYC Open Data
- PostgreSQL + PostGIS for geospatial search and peer-group comparison
- Seasonally-adjusted anomaly detection (a building with heat complaints in January is normal — one with triple its own baseline isn't)
- Explainable, auditable risk scoring with a per-factor breakdown
- Grounded LLM summaries constrained to verified structured facts

`Python` `FastAPI` `PostgreSQL/PostGIS` `Redis` `pandas` `scikit-learn`

---

### 🧩 Sudoku Mobile App — *Software Engineering Intern, DNR Events LLC*

Shipped a production Sudoku experience into a public Android app serving ~200 daily active users.

- 9×9 board with editable cells, notes, conflict detection, undo/redo, and completion validation (.NET MAUI + MVVM)
- Randomized backtracking generator producing valid boards and the 81-cell answer key, removing cells by difficulty
- Authenticated ASP.NET Core REST API with a Quartz-scheduled job generating the daily puzzle at midnight, served from a 24-hour `IMemoryCache`

`C#` `.NET MAUI` `XAML` `ASP.NET Core` `Quartz`

---

## 🛠️ Tech Stack

**Languages** — Java · Python · TypeScript · C# · SQL

**Backend** — Spring Boot · Spring Security · JPA/Hibernate · FastAPI · ASP.NET Core

**Frontend** — React 19 · TypeScript · TanStack Query · Zustand · Tailwind · Vite

**Data** — PostgreSQL/PostGIS · MySQL · Redis · pandas · scikit-learn

**Testing** — JUnit 5 · Mockito · Testcontainers · Vitest · React Testing Library · JaCoCo · pytest

**Infra & Tools** — Docker · Docker Compose · GitHub Actions · Caddy · Linux · Git · Maven · Flyway · Alembic · OpenAPI/Swagger

---

## 📫 Reach me

[LinkedIn](https://linkedin.com/in/muhammadyassa) · muhammedyassa2004@gmail.com

*Open to Summer 2027 new-grad roles and fall/spring co-ops in NYC.*
