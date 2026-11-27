# mm24blog-front: Naive UI

Selles harus on blogi menüü tehtud Naive UI komponentidega. `nuxtjs-naive-ui` moodul lisab serveripoolsete stiilide plugina. Menüüs on `NMenu`, mille valikute sildid on Nuxti lingid.
[Paigaldusjuhend](https://www.naiveui.com/en-US/os-theme/docs/nuxtjs). Blogi sisu kasutab endiselt algprojekti Nuxt UI komponente.

Kasuta Node.js 24.15.0 või uuemat 24.x versiooni. Testitud Node.js 26.7.0-ga.

```bash
npm ci
bun run dev
```

Ava `http://localhost:3000`. Menüüs on Postitused (`/`), Cats (`/cats`), Kittens (`/kittens`), Nuustik (`/kittens/nuustik`) ja Miisu (`/kittens/miisu`). Kassipoegade dünaamiline leht `/kittens/[name]` toetab ka muid nimesid. Postituste jaoks peab töötama Laraveli API aadressil `http://localhost:8000/api/posts`; menüü toimib ka ilma API-ta.

Tootmisversiooni kontroll: `npm run build` ja `npm run preview`.

## Tähelepanekud

Naive UI vajab Nuxtis serveripoolsete stiilide jaoks `nuxtjs-naive-ui` moodulit. NMenu valikute sildid luuakse NuxtLinkidena ja aktiivne valik tuleb marsruudi aadressist. See sobib kompaktseks menüüks; lihtsa lingimassiivi asemel tuleb siiski koostada komponentide renderdusfunktsioonid.
