# mm24blog-front: PrimeVue

Selles harus on blogi menüü tehtud PrimeVue komponentidega. Nuxti moodul käivitab PrimeVue plugina ja kasutab Aura teemat. Menüüs on `Menubar`, mis kitsal ekraanil avaneb nupust.
[Paigaldusjuhend](https://v4.primevue.org/nuxt/). Blogi sisu kasutab endiselt algprojekti Nuxt UI komponente.

Kasuta Node.js 24.15.0 või uuemat 24.x versiooni. Testitud Node.js 26.7.0-ga.

```bash
npm ci
bun run dev
```

Ava `http://localhost:3000`. Menüüs on Postitused (`/`), Cats (`/cats`), Kittens (`/kittens`), Nuustik (`/kittens/nuustik`) ja Miisu (`/kittens/miisu`). Kassipoegade leht kasutab dünaamilist marsruuti `/kittens/[name]`, nii et aadressis võib kasutada ka muud nime. Postituste jaoks peab töötama Laraveli API aadressil `http://localhost:8000/api/posts`; menüü toimib ka ilma API-ta.

Tootmisversiooni kontroll: `npm run build` ja `npm run preview`.

## Tähelepanekud

PrimeVue Nuxti moodul lisab komponendid automaatselt. Aura teema annab menüüle valmis kujunduse; mooduli `useToast` automaatimport on välja lülitatud, et vältida konflikti Nuxt UI samanimelise funktsiooniga. Menubar sobib selle projekti jaoks, sest toetab NuxtLinke ja kitsal ekraanil avatavat menüüd.
