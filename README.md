# mm24blog-front: Element Plus

Selles harus on blogi menüü tehtud Element Plus komponentidega. `app/plugins/element-plus.ts` registreerib plugina ja `nuxt.config.ts` laadib stiilid. Menüüs on `ElMenu` ja `ElMenuItem`.
[Paigaldusjuhend](https://element-plus.org/en-US/guide/quickstart.html). Blogi sisu kasutab endiselt algprojekti Nuxt UI komponente.

Kasuta Node.js 24.15.0 või uuemat 24.x versiooni. Testitud Node.js 26.7.0-ga.

```bash
npm ci
bun run dev
```

Ava `http://localhost:3000`. Menüüs on Postitused (`/`), Cats (`/cats`), Kittens (`/kittens`), Nuustik (`/kittens/nuustik`) ja Miisu (`/kittens/miisu`). Kassipoegade dünaamiline leht `/kittens/[name]` toetab ka muid nimesid. Postituste jaoks peab töötama Laraveli API aadressil `http://localhost:8000/api/posts`; menüü toimib ka ilma API-ta.

Tootmisversiooni kontroll: `npm run build` ja `npm run preview`.

## Tähelepanekud

Element Plus registreeritakse Nuxti pluginas ja selle CSS tuleb laadida eraldi. ElMenu toetab Vue Routerit ja aktiivset menüüvalikut; NuxtLinkid võimaldavad linke ka uuel vahelehel avada. See sobib lihtsale menüüle, kuid mobiilipaigutust tuleb eraldi kujundada.
