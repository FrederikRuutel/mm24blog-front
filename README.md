# mm24blog-front: PrimeVue

Selles harus on blogi menüü tehtud PrimeVue komponentidega. Nuxti moodul käivitab PrimeVue plugina ja kasutab Aura teemat. Menüü kasutab `Button`-komponente.
[Paigaldusjuhend](https://v4.primevue.org/nuxt/). Blogi sisu kasutab endiselt algprojekti Nuxt UI komponente.

Kasuta Node.js 24.15.0 või uuemat 24.x versiooni. Testitud Node.js 26.7.0-ga.

```bash
npm ci
npm run dev
```

Ava `http://localhost:3000`. Menüü viib avalehele, lehele „Blogist“ ja tunnikoodi GitHubi reposse. Postituste jaoks peab töötama Laraveli API aadressil `http://localhost:8000/api/posts`; menüü toimib ka ilma API-ta.

Tootmisversiooni kontroll: `npm run build` ja `npm run preview`.
