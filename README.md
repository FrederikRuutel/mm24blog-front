# Komponendiraamistikud praktikas

Kolm menüüd samale Nuxti blogile. Iga lahendus on oma harus:

| Haru | Menüü | Muudatused |
| --- | --- | --- |
| [primevue](https://github.com/FrederikRuutel/mm24blog-front/tree/primevue) | `Menubar`, telefonis avatav menüü | [Võrdle algkoodiga](https://github.com/FrederikRuutel/mm24blog-front/compare/8ec7561...primevue) |
| [element-plus](https://github.com/FrederikRuutel/mm24blog-front/tree/element-plus) | `ElMenu` ja `ElMenuItem`, aktiivne leht eristub | [Võrdle algkoodiga](https://github.com/FrederikRuutel/mm24blog-front/compare/8ec7561...element-plus) |
| [naive-ui](https://github.com/FrederikRuutel/mm24blog-front/tree/naive-ui) | `NMenu`, lingid menüü valikutes | [Võrdle algkoodiga](https://github.com/FrederikRuutel/mm24blog-front/compare/8ec7561...naive-ui) |

Kõigis kolmes harus on raamistikuga tehtud menüü linkidega avalehele (`/`), Cats (`/cats`), Kittens (`/kittens`), Nuustik (`/kittens/nuustik`) ja Miisu (`/kittens/miisu`). `<NuxtPage />` asub menüü all. Dünaamiline `/kittens/[name]` leht töötab ka teiste nimedega.

## Käivitamine

Vaja on Node.js 24.15.0 või uuemat 24.x versiooni. Vali üks ülesande harudest, sest `main` sisaldab algprojekti.

```bash
git clone https://github.com/FrederikRuutel/mm24blog-front.git
cd mm24blog-front
git switch primevue
npm ci
npm run dev
```

Buniga saab käivitada käsuga `bun run dev`. Teise lahenduse proovimiseks peata server, vaheta haru (`git switch element-plus` või `git switch naive-ui`), käivita `npm ci` ja seejärel uuesti arendusserver. Ava `http://localhost:3000`.

Kasside lehed ja menüü töötavad ilma backendita. Avalehe postituste jaoks on vaja API-t `http://localhost:8000/api/posts`.

## Raamistike kommentaarid

- **PrimeVue:** Nuxti moodul ja Aura teema annavad valmis menüü; Nuxt UI-ga kattuva `useToast` automaatimpordi lülitasin välja. Menubar sobib siia hästi, sest toetab NuxtLinke ja mobiilis avatavat menüüd.
- **Element Plus:** Paigaldus kasutab Nuxti pluginat ja eraldi CSS-i importi; kitsal ekraanil menüü mähkimise jaoks lisasin stiilid. ElMenu sobib lihtsale menüüle ning toetab Vue Routerit ja aktiivse lingi kuvamist.
- **Naive UI:** Serveripoolsete stiilide jaoks on lisatud `nuxtjs-naive-ui`; linkide sildid tuleb koostada renderdusfunktsioonidega. NMenu sobib kompaktseks menüüks ja aktiivset valikut saab juhtida marsruudi järgi.

## Kontroll

Kõik kolm haru läbisid `npm ci` ja `npm run build` kontrolli Node.js 24.22.3-ga. Iga haru serveripoolse renderduse kontroll kinnitas avalehe, `/cats`, `/kittens`, `/kittens/nuustik`, `/kittens/miisu` ning täiendava dünaamilise nime `/kittens/testkiisu` vastuse 200 ja vajalike menüülinkide olemasolu.


Aluseks on [tunni mm24blog-front](https://github.com/Kasparsu/mm24blog-front/tree/8ec7561) projekti `main`. Võrreldes algkoodiga muutus harus `main` ainult see README. Menüüd on ülal lingitud harudes.
