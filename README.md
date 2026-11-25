# mm24blog-front: Naive UI

Selles harus on blogi menüü tehtud Naive UI komponentidega. `nuxtjs-naive-ui` moodul lisab serveripoolsete stiilide plugina. Menüü kasutab `NButton`-komponente.
[Paigaldusjuhend](https://www.naiveui.com/en-US/os-theme/docs/nuxtjs). Blogi sisu kasutab endiselt algprojekti Nuxt UI komponente.

```bash
npm ci
npm run dev
```

Ava `http://localhost:3000`. Menüü viib avalehele, lehele „Blogist“ ja tunnikoodi GitHubi reposse. Postituste jaoks peab töötama Laraveli API aadressil `http://localhost:8000/api/posts`; menüü toimib ka ilma API-ta.

Tootmisversiooni kontroll: `npm run build` ja `npm run preview`.
