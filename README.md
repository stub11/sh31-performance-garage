# SH31 Performance Garage — Tuqo test site

A static, preview-only landing page for the separately created website
`https://sh31-performance-garage.tuqo.ru/`.

**Not the existing production website `https://sh31online.tuqo.ru/`.**

## Publishing with Tuqo Git CD

1. Create a **new, separate GitHub repository** `sh31-performance-garage`.
2. Put `index.html` and `robots.txt` in its **root** on `main`.
3. Tuqo → project `Танцующий Пингвин` → site `SH31 Performance Garage` → `Git CD`.
4. Connect GitHub via OAuth, select the NEW repository, branch `main`.
5. Click `Привязать репозиторий` / `Link repository`, then `Задеплоить сейчас` / `Deploy now` for the first deployment.
6. Confirm that the site is available at `https://sh31-performance-garage.tuqo.ru/`.

Tuqo handles repository webhook setup and deploy automatically on subsequent pushes. Since this
is pure static HTML (no `package.json`), there is no build command, output folder or CI pipeline.

## Security guardrails

- The site has no booking, login or phone form, and makes no API calls to foreign backends.
- Contact phone numbers are intentionally absent.
- SEO indexing is disabled (`noindex,nofollow` and `robots.txt`).
- Do not publish user records, API tokens, provider OAuth secrets, `.env` files or Supabase credentials.
- Do not link this Git repository to `sh31online.tuqo.ru`; the original site remains untouched.
- Before re-enabling online booking, migrate auth, PostgreSQL, logs and backups to Russian infrastructure and test the full workflow.