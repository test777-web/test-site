# AutoGlob — сайт (v5)

Усі файли лежать пласко, без підпапок.

## Що нового в v5

### SEO
- **robots.txt** і **sitemap.xml** — додано, з посиланням на всі 8 сторінок сайту
- **Canonical** теги на кожній сторінці
- **Schema.org JSON-LD**: Organization (усюди), BreadcrumbList (усюди), NewsArticle (на 4 статтях), FAQPage (на 4 статтях)
- **FAQ-блоки** додані в кінець кожної статті (3 питання-відповіді), видимі для читачів і розмічені як FAQPage

### Технічне SEO
- `loading="lazy"` на зображеннях нижче першого екрану
- `loading="eager" fetchpriority="high"` на головному зображенні кожної сторінки (LCP)
- Explicit `width`/`height` на всіх фото — прибирає зсув верстки при завантаженні
- Фото перестиснуті (JPEG quality 72, progressive) — загальна вага зменшена на ~32%

### Нові інструменти (3 нові сторінки)
- **`tools.html`** — 10 калькуляторів: Tire Size, Wheel Offset, Wheel Fitment (bolt pattern), Fuel Cost, Loan, Insurance (орієнтовний), EV Charging Cost, CO2 Emissions, Braking Distance, Depreciation. Усі рахують у браузері, без бекенду.
- **`vin-decoder.html`** — безкоштовний VIN-декодер на базі публічного API NHTSA vPIC (уряд США, без ключа). Дані запитуються напряму з браузера користувача.
- **`compare.html`** — таблиця порівняння 4 авто із сайту (GR86, Polestar 2, Audi A8, BMW 335i)

Посилання на всі три — у футері головної сторінки та в новому промо-блоці одразу під заголовком "Reviews".

## Що НЕ реалізовано (і чому)

- **Повноцінний каталог шин/авто/двигунів** — потребує тисяч записів з платного API (MarketCheck, Edmunds тощо) або багатьох годин ручного наповнення. Зараз є лише invalid comparison на 4 наших авто.
- **VIN Lookup (історія ДТП)** — на відміну від VIN Decoder (безкоштовні технічні характеристики), це платні сервіси на кшталт Carfax. Безкоштовного публічного аналога немає.
- **Автогенерація SEO-сторінок** — має сенс тільки після появи реальних даних з попереднього пункту.

## Структура файлів

```
index.html, article-gr86-review.html, news-polestar-us-ban.html,
audi-a8-discontinued-investment.html, bmw-n54-known-issues.html   — контент
tools.html, vin-decoder.html, compare.html                        — нові інструменти
style.css, site.js, calculators.js                                 — стилі й логіка
robots.txt, sitemap.xml                                             — SEO
logo.png, hero-*.jpg, card-*.jpg                                    — зображення
```

## Кеш-бастинг

Версія піднята до `?v=5` — після заливання переконайся, що бачиш саме її (DevTools → Network → site.js).
