---
name: frontend-translation-dictionary
delivery: reference
description: |
  Словарь терминологии фронтенд-разработки для перевода технических статей
  с английского и немецкого на русский и унификации терминов в русскоязычных
  материалах VK Tech. Покрывает HTML/CSS/JS, React/Vue/Angular/Svelte/Solid,
  Next.js/Nuxt/Remix, TypeScript, web APIs, бандлеры (Vite, Webpack, esbuild),
  state management, тестирование, accessibility, performance, PWA, Web
  Components. Активируется автоматически по триггерам темы; пригоден любому
  автору и редактору фронтенд-контента, не только модулю перевода. Источники:
  документация React/Vue (RU), переводы Хабра (T-Bank, Yandex, JUG.ru,
  Selectel), Frontend Weekly, MDN на русском.
activation:
  - "frontend"
  - "фронтенд"
  - "front-end"
  - "html"
  - "css"
  - "javascript"
  - "js"
  - "typescript"
  - "ts"
  - "react"
  - "реакт"
  - "vue"
  - "vue.js"
  - "angular"
  - "svelte"
  - "solid"
  - "solidjs"
  - "next.js"
  - "nextjs"
  - "nuxt"
  - "remix"
  - "astro"
  - "qwik"
  - "vite"
  - "webpack"
  - "esbuild"
  - "rollup"
  - "turbopack"
  - "rspack"
  - "tailwind"
  - "css-in-js"
  - "redux"
  - "mobx"
  - "zustand"
  - "pinia"
  - "vuex"
  - "react query"
  - "tanstack"
  - "rtk"
  - "ssr"
  - "ssg"
  - "isr"
  - "csr"
  - "hydration"
  - "spa"
  - "mpa"
  - "pwa"
  - "web components"
  - "shadow dom"
  - "service worker"
  - "indexeddb"
  - "webassembly"
  - "wasm"
  - "webgl"
  - "webgpu"
  - "graphql"
  - "rest api"
  - "dom"
  - "virtual dom"
  - "jsx"
  - "tsx"
  - "хук"
  - "hook"
  - "useeffect"
  - "usestate"
  - "композиция"
  - "props"
  - "пропсы"
  - "роутинг"
  - "роутер"
  - "router"
  - "accessibility"
  - "a11y"
  - "performance"
  - "lighthouse"
  - "core web vitals"
  - "lcp"
  - "fid"
  - "cls"
  - "inp"
  - "ttfb"
---

# Frontend Translation Dictionary

Словарь терминологии фронтенд-разработки. Используется для перевода статей и для унификации терминологии в любых русскоязычных материалах VK Tech.

**Для переводчиков:** все 19 разделов применимы, включая падежные формы и типовые ошибки.
**Для авторов SEO-статей, документации, пресс-релизов:** опирайся в первую очередь на разделы 2-15 (терминологические таблицы по фреймворкам, API, инструментам, инфраструктуре). Разделы 17-19 (падежные формы, типовые ошибки переводчика, чек-лист) специфичны для перевода.

## Принципы

1. **Имена фреймворков и библиотек — оригинал.** React, Vue, Angular, Svelte, Solid, Next.js, Nuxt, Remix, Astro, Qwik, Vite, Webpack, Tailwind. Не «реакт», «вью», «ангуляр» (хотя в разговорной речи допустимо).
2. **Имена API — оригинал.** Fetch API, Web Components, IndexedDB, Service Worker, Shadow DOM. При первом упоминании — расшифровка.
3. **Базовые понятия — переводятся.** «Компонент», «состояние», «свойство» (для props в нарративе), «шаблон», «директива», «событие», «модель».
4. **JS-специфичные термины — оригинал или транслитерация.** `hook` → «хук», `state` → «состояние» или «стейт», `props` → «пропсы» или «свойства», `ref` → «реф» или «ссылка».
5. **CSS-свойства, HTML-теги, JS-методы — никогда не переводятся.** `display: flex`, `<button>`, `Array.prototype.map`.
6. **Аббревиатуры — оригинал.** DOM, BOM, JSX, TSX, SPA, MPA, PWA, SSR, SSG, ISR, CSR, ESM, CJS, AMD, UMD, BEM, OOCSS. Расшифровка при первом упоминании.
7. **В одном тексте — один вариант.** Не смешивай «компонент» и `component`, «хук» и `hook`.

## Раздел 1. Базовые понятия веба

| English | Русский (рекомендуемый) | Альтернативы | Комментарий |
|---------|-------------------------|--------------|-------------|
| Web / Web development | веб / веб-разработка | — | Через дефис |
| Frontend / Front-end | фронтенд / front-end | — | «Фронтенд» — устоялось |
| Backend | бэкенд | — | — |
| Full-stack | фуллстек / full-stack | — | — |
| Client / Client-side | клиент / клиентская сторона | — | — |
| Server / Server-side | сервер / серверная сторона | — | — |
| Browser | браузер | — | Склоняется: браузера, браузеру |
| User agent | user agent / агент пользователя | — | — |
| Cross-browser | кроссбраузерный | — | Через слитно |
| Responsive design | адаптивный дизайн | — | — |
| Mobile-first | mobile-first | — | Не переводится |
| Progressive enhancement | progressive enhancement / прогрессивное улучшение | — | — |
| Graceful degradation | graceful degradation / постепенная деградация | — | — |

## Раздел 2. HTML

| English | Русский | Комментарий |
|---------|---------|-------------|
| HTML | HTML | Не переводится |
| HTML5 | HTML5 | — |
| Tag | тег | Склоняется |
| Element | элемент | — |
| Attribute | атрибут | — |
| Semantic HTML | семантический HTML | — |
| Markup | разметка | — |
| Template | шаблон | — |
| Form | форма | — |
| Input | input / поле ввода | — |
| Button | кнопка / `<button>` | — |
| Canvas | canvas / `<canvas>` | — |
| SVG | SVG | — |
| iframe | iframe | — |
| Web Components | Web Components | — |
| Custom Element | Custom Element / пользовательский элемент | — |
| Shadow DOM | Shadow DOM | Не переводится |
| Shadow root | shadow root / теневой корень | — |
| HTML template / `<template>` | template / `<template>` | — |
| Slot | slot / слот | Внутри Web Components |
| ARIA | ARIA | Accessible Rich Internet Applications |
| ARIA attributes | ARIA-атрибуты | Через дефис |
| role | role | ARIA-атрибут |
| Microdata, Schema.org, Open Graph | оригинал | — |

## Раздел 3. CSS

| English | Русский | Комментарий |
|---------|---------|-------------|
| CSS | CSS | Не переводится |
| CSS3 | CSS3 | — |
| Stylesheet | таблица стилей / stylesheet | — |
| Selector | селектор | — |
| Property | свойство | — |
| Value | значение | — |
| Declaration | объявление | — |
| Rule | правило | — |
| Specificity | специфичность | — |
| Cascade | каскад | — |
| Inheritance | наследование | — |
| Box model | box model / блочная модель | — |
| Display | display | CSS-свойство, не переводить |
| Position | position | CSS-свойство |
| Float | float | — |
| Flexbox / Flex | Flexbox / flex | Не переводится |
| Grid / CSS Grid | Grid / CSS Grid | Не переводится |
| Container queries | container queries / контейнерные запросы | — |
| Media query | media query / медиа-запрос | — |
| Breakpoint | breakpoint / точка излома | — |
| Viewport | viewport / область просмотра | — |
| Animation | анимация | — |
| Transition | переход / transition | — |
| Transform | трансформация / transform | — |
| Keyframes | keyframes / ключевые кадры | — |
| Pseudo-class / Pseudo-element | псевдокласс / псевдоэлемент | — |
| Custom properties / CSS variables | CSS-переменные / custom properties | — |
| `:root` | `:root` | — |
| BEM (Block Element Modifier) | BEM / БЭМ | Методология |
| OOCSS, SMACSS, Atomic CSS | OOCSS, SMACSS, Atomic CSS | — |
| CSS-in-JS | CSS-in-JS | Не переводится |
| Styled Components | Styled Components | — |
| Tailwind CSS | Tailwind CSS | — |
| Sass / SCSS | Sass / SCSS | — |
| Less | Less | — |
| PostCSS | PostCSS | — |
| Stylelint | Stylelint | — |
| Autoprefixer | Autoprefixer | — |

## Раздел 4. JavaScript / TypeScript

| English | Русский | Комментарий |
|---------|---------|-------------|
| JavaScript (JS) | JavaScript / JS | Не переводится |
| ECMAScript / ES | ECMAScript / ES | ES2015, ES2024 |
| TypeScript (TS) | TypeScript / TS | — |
| Variable | переменная | — |
| Constant | константа | `const` |
| Function | функция | — |
| Arrow function | стрелочная функция | — |
| Closure | замыкание | — |
| Hoisting | hoisting / поднятие | — |
| Scope | область видимости / scope | — |
| Lexical scope | лексическая область видимости | — |
| Block scope | блочная область видимости | — |
| Object | объект | — |
| Array | массив | — |
| Map / Set / WeakMap / WeakSet | Map / Set / WeakMap / WeakSet | Не переводить |
| Promise | Promise / промис | «Промис» — разг. |
| async / await | async / await | Не переводить |
| Callback | колбэк / callback | — |
| Event loop | event loop / цикл событий | — |
| Task / Microtask | task / microtask | — |
| Iterable / Iterator | итерируемый объект / итератор | — |
| Generator | генератор | — |
| Class | класс | — |
| Prototype | прототип | — |
| Inheritance | наследование | — |
| Mixin | миксин | — |
| Decorator | декоратор | — |
| Symbol | Symbol | Не переводить — встроенный тип |
| Module | модуль | — |
| Import / Export | import / export | — |
| ESM (ECMAScript Modules) | ESM | — |
| CJS (CommonJS) | CommonJS / CJS | — |
| Bundling | бандлинг / сборка | — |
| Bundle | бандл / сборка | — |
| Tree shaking | tree shaking | Не переводится |
| Code splitting | code splitting / разделение кода | — |
| Lazy loading | lazy loading / ленивая загрузка | — |
| Dynamic import | динамический импорт | — |
| Type | тип | — |
| Interface | интерфейс | TS |
| Generic | дженерик / generic | — |
| Type assertion | приведение типа / type assertion | — |
| Type guard | type guard | — |
| Union / Intersection types | union / intersection типы | — |
| Type inference | вывод типов / type inference | — |
| Strict mode | строгий режим | — |
| any / unknown / never | any / unknown / never | Не переводить — встроенные типы |

## Раздел 5. React

| English | Русский | Комментарий |
|---------|---------|-------------|
| React | React | Не переводится |
| Component | компонент | Склоняется: компонента, компоненту |
| Functional component | функциональный компонент | — |
| Class component | классовый компонент | Устар. |
| Server Component | Server Component / серверный компонент | React 19+ |
| Client Component | Client Component / клиентский компонент | — |
| JSX | JSX | Не переводится |
| TSX | TSX | — |
| Props | пропсы / props / свойства | «Пропсы» устоялось |
| State | состояние / стейт | — |
| Hook | хук | Склоняется: хука, хуку, хуков |
| useState | useState | Не переводить |
| useEffect | useEffect | — |
| useContext, useReducer, useMemo, useCallback, useRef, useLayoutEffect | оригинал | — |
| useTransition, useDeferredValue, useId, useSyncExternalStore | оригинал | React 18+ |
| Custom hook | кастомный хук | — |
| Context | контекст | — |
| Provider | Provider / провайдер | — |
| Children | children / дети | В JSX |
| Ref | реф / ref / ссылка | — |
| forwardRef | forwardRef | — |
| Render | рендер / отрисовка | — |
| Rendering | рендеринг | — |
| Re-render | пере-рендер / повторный рендер | — |
| Reconciliation | reconciliation / согласование | — |
| Virtual DOM | Virtual DOM / виртуальный DOM | — |
| Fiber | Fiber | React internals |
| Hydration | гидратация / hydration | SSR |
| Strict Mode (React) | Strict Mode | — |
| Suspense | Suspense | — |
| Error boundary | error boundary / граница ошибок | — |
| Portal | Portal | — |
| Fragment | Fragment / `<>` | — |
| Higher-Order Component (HOC) | HOC / компонент высшего порядка | — |
| Render props | render props | — |
| Controlled / Uncontrolled component | контролируемый / неконтролируемый компонент | — |
| Lifting state up | поднятие состояния | — |
| Memoization | мемоизация | — |
| React.memo | React.memo | — |
| React DevTools | React DevTools | — |
| React Router | React Router | — |
| React Query / TanStack Query | React Query / TanStack Query | — |
| Redux / RTK (Redux Toolkit) | Redux / RTK | — |
| Zustand, Jotai, Recoil, Valtio | оригинал | State managers |
| MobX | MobX | — |

## Раздел 6. Vue

| English | Русский | Комментарий |
|---------|---------|-------------|
| Vue / Vue.js | Vue / Vue.js | — |
| Vue 3 | Vue 3 | — |
| Composition API | Composition API | Не переводится |
| Options API | Options API | — |
| ref / reactive | ref / reactive | Vue 3 reactive primitives |
| computed | computed / вычисляемое свойство | — |
| watch / watchEffect | watch / watchEffect | — |
| Composable | composable / композабл | Vue-аналог хуков |
| Directive | директива | `v-if`, `v-for`, `v-model` |
| Template | шаблон | — |
| Slot | slot / слот | — |
| Scoped slots | scoped slots | — |
| Teleport | Teleport | — |
| Provide / Inject | Provide / Inject | — |
| Pinia | Pinia | Современный store |
| Vuex | Vuex | Устар. |
| Vue Router | Vue Router | — |
| Single File Component (SFC) | SFC / однофайловый компонент | `.vue` |
| Vue DevTools | Vue DevTools | — |

## Раздел 7. Angular, Svelte, Solid и другие

| English | Русский | Комментарий |
|---------|---------|-------------|
| Angular | Angular | Не переводится |
| AngularJS | AngularJS | Устар. (Angular 1.x) |
| Module (Angular) | модуль | — |
| Service (Angular) | сервис | — |
| Directive (Angular) | директива | — |
| Pipe | pipe / пайп | — |
| Injectable | Injectable / инжектируемый | — |
| Dependency Injection (DI) | внедрение зависимостей / DI | — |
| RxJS | RxJS | — |
| Observable | Observable | RxJS-primitive |
| Subject / BehaviorSubject | Subject / BehaviorSubject | — |
| NgRx | NgRx | — |
| Svelte | Svelte | — |
| SvelteKit | SvelteKit | — |
| Runes | runes | Svelte 5 |
| Solid / SolidJS | Solid / SolidJS | — |
| Signal | signal / сигнал | Solid, Angular 16+ |
| Effect | effect / эффект | — |
| Qwik | Qwik | — |
| Resumability | resumability / возобновляемость | Qwik-концепция |
| Astro | Astro | — |
| Islands architecture | islands / островная архитектура | — |
| Preact | Preact | — |
| Lit | Lit | Web Components framework |
| Alpine.js | Alpine.js | — |
| HTMX | HTMX | — |
| jQuery | jQuery | Устар. |

## Раздел 8. Метафреймворки (Next.js, Nuxt, Remix)

| English | Русский | Комментарий |
|---------|---------|-------------|
| Next.js | Next.js | — |
| App Router / Pages Router | App Router / Pages Router | Next.js |
| Server Components | Server Components | — |
| Server Actions | Server Actions | — |
| Middleware | middleware | — |
| `getServerSideProps` / `getStaticProps` | оригинал | Pages Router |
| Edge Runtime | Edge Runtime | — |
| Vercel | Vercel | Хостинг |
| Nuxt / Nuxt.js | Nuxt | Vue meta-framework |
| Nitro | Nitro | Nuxt server engine |
| Remix | Remix | — |
| Loader / Action | loader / action | Remix |
| Routes | routes / маршруты | — |
| Catch-all route | catch-all route | — |
| Dynamic route | динамический маршрут | — |
| Layouts | layouts / лейауты | — |

## Раздел 9. Рендеринг и инфраструктура

| English | Русский | Комментарий |
|---------|---------|-------------|
| SSR (Server-Side Rendering) | SSR / серверный рендеринг | — |
| SSG (Static Site Generation) | SSG / статическая генерация | — |
| ISR (Incremental Static Regeneration) | ISR | — |
| CSR (Client-Side Rendering) | CSR / клиентский рендеринг | — |
| Hydration | гидратация | — |
| Partial hydration | частичная гидратация | — |
| Streaming SSR | streaming SSR / потоковый SSR | — |
| RSC (React Server Components) | RSC | — |
| Edge rendering | edge-рендеринг | — |
| Headless CMS | headless CMS | — |
| Jamstack | Jamstack | — |
| Static site | статический сайт | — |
| SPA (Single Page Application) | SPA / одностраничное приложение | — |
| MPA (Multi Page Application) | MPA / многостраничное приложение | — |
| PWA (Progressive Web App) | PWA / прогрессивное веб-приложение | — |
| Service Worker | Service Worker | — |
| Web App Manifest | Web App Manifest | — |
| Offline-first | offline-first | — |
| Web Workers | Web Workers | — |
| Shared Workers | Shared Workers | — |

## Раздел 10. Бандлеры и инструменты сборки

| English | Русский | Комментарий |
|---------|---------|-------------|
| Bundler | бандлер | — |
| Webpack | Webpack | — |
| Vite | Vite | — |
| esbuild | esbuild | — |
| Rollup | Rollup | — |
| Parcel | Parcel | — |
| Turbopack | Turbopack | — |
| Rspack | Rspack | — |
| SWC | SWC | Speedy Web Compiler |
| Babel | Babel | — |
| Loader (Webpack) | загрузчик / loader | — |
| Plugin | плагин | — |
| HMR (Hot Module Replacement) | HMR / горячая замена модулей | — |
| Live reload | live reload | — |
| Source map | source map / карта исходников | — |
| Minification | минификация | — |
| Compression (gzip, brotli) | сжатие (gzip, brotli) | — |
| Polyfill | полифил / полифилл | — |
| Transpilation | транспиляция | — |
| Compilation | компиляция | — |
| AST (Abstract Syntax Tree) | AST / абстрактное синтаксическое дерево | — |
| Linter | линтер | — |
| ESLint | ESLint | — |
| Prettier | Prettier | — |
| Stylelint | Stylelint | — |
| TypeScript Compiler (tsc) | tsc / TypeScript compiler | — |
| Package manager | пакетный менеджер | — |
| npm / Yarn / pnpm / Bun | npm / Yarn / pnpm / Bun | — |
| node_modules | node_modules | Не переводить |
| package.json | package.json | — |
| Monorepo | монорепо / monorepo | — |
| Turborepo, Nx, Lerna | Turborepo, Nx, Lerna | — |
| Workspace | workspace / воркспейс | — |

## Раздел 11. Web APIs

| English | Русский | Комментарий |
|---------|---------|-------------|
| DOM (Document Object Model) | DOM | Не переводится |
| BOM (Browser Object Model) | BOM | — |
| Virtual DOM | Virtual DOM / виртуальный DOM | — |
| Window, Document, Element | Window, Document, Element | DOM-объекты |
| Event | событие | — |
| Event listener | обработчик событий / event listener | — |
| Event delegation | делегирование событий | — |
| Event bubbling / capturing | всплытие / захват событий | — |
| Fetch API | Fetch API | — |
| XMLHttpRequest (XHR) | XHR | Устар. |
| WebSocket | WebSocket | См. также `networking-translation-dictionary` |
| Server-Sent Events (SSE) | SSE / Server-Sent Events | — |
| Web Storage (localStorage, sessionStorage) | Web Storage / localStorage / sessionStorage | — |
| Cookies | cookies / куки | — |
| IndexedDB | IndexedDB | — |
| Cache API | Cache API | — |
| Web Workers | Web Workers | — |
| Service Worker | Service Worker | — |
| WebAssembly (Wasm) | WebAssembly / Wasm | — |
| WebGL / WebGPU | WebGL / WebGPU | — |
| Canvas API | Canvas API | — |
| Web Animation API (WAAPI) | Web Animation API | — |
| File API | File API | — |
| Drag and Drop | drag and drop | — |
| Geolocation API | Geolocation API | — |
| Notifications API | Notifications API | — |
| Push API | Push API | — |
| Intersection Observer | Intersection Observer | — |
| Mutation Observer | Mutation Observer | — |
| Resize Observer | Resize Observer | — |
| WebRTC | WebRTC | — |
| Web Audio API | Web Audio API | — |
| Speech Synthesis / Recognition | Speech Synthesis / Recognition | — |
| Clipboard API | Clipboard API | — |
| Permissions API | Permissions API | — |
| Web Authentication API (WebAuthn) | WebAuthn | См. также `security-translation-dictionary` |
| Payment Request API | Payment Request API | — |

## Раздел 12. State management и data fetching

| English | Русский | Комментарий |
|---------|---------|-------------|
| State management | управление состоянием | — |
| Global state | глобальное состояние | — |
| Local state | локальное состояние | — |
| Store | store / стор | — |
| Action | action / экшен | Redux |
| Reducer | reducer / редьюсер | — |
| Selector | селектор | — |
| Middleware | middleware | — |
| Thunk | thunk | Redux |
| Saga | Saga | Redux-Saga |
| Slice | slice / слайс | RTK |
| RTK (Redux Toolkit) | RTK | — |
| Zustand, Jotai, Recoil | Zustand, Jotai, Recoil | — |
| MobX, MobX-state-tree | MobX | — |
| TanStack Query / React Query | TanStack Query | — |
| SWR | SWR | — |
| Apollo Client | Apollo Client | GraphQL |
| URQL | URQL | — |
| Relay | Relay | — |
| Optimistic update | оптимистичное обновление | — |
| Cache | кэш | — |
| Cache invalidation | инвалидация кэша | — |
| Refetch | refetch / повторный запрос | — |
| Polling | polling / опрос | — |

## Раздел 13. Тестирование

| English | Русский | Комментарий |
|---------|---------|-------------|
| Unit test | unit-тест / юнит-тест | — |
| Integration test | интеграционный тест | — |
| E2E test | E2E-тест / end-to-end тест | — |
| Component test | компонентный тест | — |
| Snapshot test | snapshot test / снапшот-тест | — |
| Visual regression test | визуальная регрессия / visual regression | — |
| Vitest, Jest, Mocha, Jasmine | оригинал | Test runners |
| Playwright, Cypress, Selenium, WebdriverIO | оригинал | E2E tools |
| Testing Library | Testing Library | — |
| React Testing Library, Vue Testing Library | оригинал | — |
| Mock | мок | — |
| Spy | spy / шпион | — |
| Stub | stub / стаб | — |
| Fixture | фикстура | — |
| Coverage | покрытие | — |
| Storybook | Storybook | Component dev environment |
| Chromatic | Chromatic | Visual testing |

## Раздел 14. Accessibility (a11y) и i18n

| English | Русский | Комментарий |
|---------|---------|-------------|
| Accessibility (a11y) | доступность / a11y | — |
| WCAG (Web Content Accessibility Guidelines) | WCAG | — |
| Screen reader | скринридер / программа экранного доступа | — |
| Keyboard navigation | клавиатурная навигация | — |
| Focus | фокус | — |
| Focus trap | focus trap / ловушка фокуса | — |
| Tab order | порядок табуляции | — |
| Skip link | skip-ссылка | — |
| ARIA | ARIA | — |
| Color contrast | цветовой контраст | — |
| Alt text | alt-текст / альтернативный текст | — |
| Landmarks | ARIA-ориентиры / landmarks | — |
| Live region | live region / живая область | — |
| axe-core, Lighthouse | axe-core, Lighthouse | Инструменты |
| Internationalization (i18n) | интернационализация / i18n | — |
| Localization (l10n) | локализация / l10n | — |
| Translation | перевод | — |
| Right-to-Left (RTL) | RTL / справа налево | — |
| Pluralization | плюрализация / склонение по числам | — |
| ICU MessageFormat | ICU MessageFormat | — |
| react-i18next, vue-i18n, FormatJS | оригинал | — |

## Раздел 15. Производительность

| English | Русский | Комментарий |
|---------|---------|-------------|
| Performance | производительность | — |
| Core Web Vitals | Core Web Vitals | — |
| LCP (Largest Contentful Paint) | LCP | — |
| FID (First Input Delay) | FID | Заменён на INP |
| INP (Interaction to Next Paint) | INP | Core Web Vital с 2024 |
| CLS (Cumulative Layout Shift) | CLS | — |
| TTFB (Time to First Byte) | TTFB | — |
| FCP (First Contentful Paint) | FCP | — |
| TTI (Time to Interactive) | TTI | — |
| TBT (Total Blocking Time) | TBT | — |
| Lighthouse | Lighthouse | — |
| PageSpeed Insights | PageSpeed Insights | — |
| WebPageTest | WebPageTest | — |
| Profiling | профилирование | — |
| Performance budget | бюджет производительности / performance budget | — |
| Critical CSS / Critical path | critical CSS / критический путь | — |
| Above the fold | above the fold | — |
| Lazy loading (images) | ленивая загрузка изображений | `loading="lazy"` |
| Preload / Prefetch / Preconnect | preload / prefetch / preconnect | — |
| HTTP/2, HTTP/3 push | HTTP/2 push | См. `networking-translation-dictionary` |
| Image optimization | оптимизация изображений | — |
| WebP, AVIF | WebP, AVIF | Форматы |
| Lazy hydration | ленивая гидратация | — |
| Selective hydration | селективная гидратация | — |

## Раздел 16. Глаголы и действия

| English | Русский | Комментарий |
|---------|---------|-------------|
| to render | отрисовать / отрендерить | «Отрендерить компонент» |
| to re-render | пере-рендерить / отрендерить заново | — |
| to mount | смонтировать | «Смонтировать компонент» |
| to unmount | размонтировать | — |
| to update | обновить | — |
| to fetch | запросить / зафетчить | — |
| to dispatch | задиспатчить / отправить (action) | — |
| to subscribe / unsubscribe | подписаться / отписаться | — |
| to bind | привязать / забиндить | — |
| to debounce / throttle | дебаунсить / троттлить | — |
| to memoize | мемоизировать | — |
| to bundle | собрать в бандл | — |
| to lint | линтить / прогнать линтер | — |
| to format | форматировать (Prettier) | — |
| to compile | скомпилировать | — |
| to transpile | транспилировать | — |
| to deploy | задеплоить / развернуть | — |

## Раздел 17. Падежные формы (для переводчиков)

### Компонент / Хук / Бандл / Стор

- **Компонент** (м.р.): компонента, компоненту, компонентом; мн.ч. компоненты, компонентов
- **Хук** (м.р.): хука, хуку, хуком; мн.ч. хуки, хуков
- **Бандл** (м.р.): бандла, бандлу, бандлом
- **Стор** (м.р.): стора, стору, стором
- **Реф** (м.р.): рефа, рефу, рефом
- **Пропс** (м.р.): пропса, пропсу; мн.ч. пропсы, пропсов

### React / Vue / Angular / Svelte / Next.js

**Не склоняются.** «В React», «для Vue», «через Angular», «на Next.js». НЕ «в Реакте».

### DOM / JSX / SPA / SSR / PWA / API

**Не склоняются.** «В DOM», «через JSX», «у SSR». В составных — через дефис: «DOM-дерево», «JSX-выражение», «SSR-рендеринг», «PWA-приложение», «API-вызов».

### npm / Yarn / pnpm / Bun

**Не склоняются**, строчные. «Через npm», «командой `pnpm install`».

### Webpack / Vite / esbuild / Turbopack

**Не склоняются.** «В Webpack», «с Vite», «через esbuild».

### CSS-свойства, JS-методы, HTML-теги

Никогда не переводятся, не склоняются: `display: flex`, `Array.map`, `<button>`, `data-attribute`.

## Раздел 18. Типовые ошибки переводчика (для переводчиков)

### 1. Перевод имён фреймворков

```
✗ «Реакт», «Вью», «Ангуляр», «Свелт», «Нюкст»
✓ «React», «Vue», «Angular», «Svelte», «Nuxt»
```

### 2. Перевод имён API

```
✗ «API получения», «интерфейс рабочего сервиса»
✓ «Fetch API», «Service Worker»
```

### 3. Перевод JS-методов и HTML-тегов

```
✗ «массив.карта()», «<кнопка>»
✓ «Array.map()», «<button>»
```

### 4. Калька «является компонентом»

```
✗ «Header является компонентом верхнего уровня»
✓ «Header — компонент верхнего уровня»
```

### 5. Перевод «render» / «rendering»

`Render` (verb) — «отрисовать» / «отрендерить». `Rendering` (noun) — «рендеринг» / «отрисовка». В одном тексте — один вариант.

### 6. «State» vs «состояние» vs «стейт»

Оба перевода используются. «Состояние» — официальное, «стейт» — разговорное. В технических статьях допустимы оба, в одном тексте — один вариант.

### 7. «Hook» — только «хук»

Не «крючок», не «зацепка». В контексте React/Vue — устоявшийся термин «хук».

### 8. Перевод названий хуков

```
✗ «использовать состояние»
✓ «useState»
```

Имена хуков (`useState`, `useEffect`, `useContext`) — оригинал.

### 9. Web APIs — оригинал

```
✗ «теневое DOM», «работник сервиса»
✓ «Shadow DOM», «Service Worker»
```

### 10. «Mount» vs «крепить»

```
✗ «прикрепить компонент»
✓ «смонтировать компонент»
```

«Монтирование» — устоявшийся перевод lifecycle-метода `mount`.

### 11. «Bundle» — «бандл» или «сборка»

Оба варианта. «Бандл» — устоявшаяся транслитерация в фронтенд-сообществе. «Сборка» — официальный перевод. В одном тексте — один вариант.

### 12. «Browser» как «обозреватель»

```
✗ «Веб-обозреватель не поддерживает...»
✓ «Браузер не поддерживает...»
```

«Обозреватель» — устар. перевод 90-х. Сейчас всегда «браузер».

## Раздел 19. Чек-лист + источники

### Чек-лист переводчика

- [ ] **Имена фреймворков** (React, Vue, Angular, Svelte, Solid, Next.js, Nuxt, Remix, Astro, Qwik) — оригинал
- [ ] **Имена API** (Fetch API, Service Worker, IndexedDB, Web Components, Shadow DOM) — оригинал
- [ ] **Имена бандлеров** (Webpack, Vite, esbuild, Rollup, Turbopack, Rspack) — оригинал
- [ ] **JS-методы и HTML-теги** не переведены
- [ ] **Имена хуков** (useState, useEffect, useContext, useMemo, useCallback) — оригинал
- [ ] **CSS-свойства** не переведены (`display: flex`, `position: absolute`)
- [ ] **Аббревиатуры** (DOM, JSX, SPA, SSR, SSG, PWA, ESM, BEM, ARIA, WCAG, INP, LCP, CLS) — оригинал
- [ ] **«Браузер» вместо «обозреватель»**
- [ ] **«Компонент/хук/бандл/стор»** — единый вариант для каждого
- [ ] **React/Vue/Angular/Webpack/Vite** не склоняются
- [ ] **Калек избегли** — нет «является»
- [ ] **Кавычки** — «ёлочки»

### Источники

| Источник | Назначение |
|----------|-----------|
| React Docs (RU) — https://ru.react.dev/ | Эталонная русская локализация React |
| Vue Docs (RU) — https://ru.vuejs.org/ | Эталонная русская локализация Vue |
| MDN на русском — https://developer.mozilla.org/ru/ | HTML/CSS/JS/Web APIs справочник |
| Tinkoff/T-Bank на Хабре — https://habr.com/ru/companies/tbank/ | Современный фронтенд-контент |
| Yandex на Хабре — https://habr.com/ru/companies/yandex/ | — |
| JUG.ru на Хабре — https://habr.com/ru/companies/jugru/ | Конференции HolyJS, JPoint |
| Selectel Blog | DevOps + frontend |
| Frontend Weekly (RU) | Дайджесты |
| Альянс ПРО (tran.su) | Методология |

Версия: **2026-05-16 v1.0**.

## Связь с другими словарями

- **Frontend + Networking** — статья про WebRTC, WebSocket, HTTP/3 → frontend + networking
- **Frontend + Security** — статья про XSS, CSRF, CSP, WebAuthn → frontend + security
- **Frontend + DevOps** — статья про CI/CD для фронта, Vercel/Netlify → frontend + devops
- **Frontend + ML/AI** — статья про AI-чат UI, embedding в React, WebGPU для ML → frontend + ml-ai

Приоритеты при конфликте — в `translation-standards.md`.

## Использование вне модуля перевода

Этот словарь подключается не только субагентами `article-translation-agent`, но и любыми авторами/редакторами русскоязычного фронтенд-контента (SEO-статьи, документация, пресс-релизы, дайджесты). Чтобы подключить словарь к другому субагенту, добавь в его frontmatter:

```yaml
skills:
  - frontend-translation-dictionary
```

Активация — автоматическая по триггерам (см. `activation:` в начале файла).
