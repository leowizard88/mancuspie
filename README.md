# MANCUSPIE · Netlify + Decap CMS

Questa versione non è WordPress: è un sito statico veloce con pannello editoriale gratuito tramite Decap CMS su Netlify.

## Cosa contiene

- Eleventy come generatore statico.
- Netlify come hosting gratuito.
- Decap CMS come pannello `/admin`.
- Collezioni modificabili:
  - Testi
  - Note
  - Altri progetti
  - Call
  - Impostazioni homepage
- Immagini moodboard integrate nello sfondo.
- Sidebar minimale con solo indice e logo-colonna vertebrale.

## Deploy su Netlify

### Metodo rapido

1. Crea un account GitHub.
2. Crea un nuovo repository, per esempio `mancuspie`.
3. Carica tutti i file di questa cartella nel repository.
4. Vai su Netlify.
5. New site from Git.
6. Scegli il repository.
7. Netlify dovrebbe leggere `netlify.toml` automaticamente.

Impostazioni corrette:

- Build command: `npm run build`
- Publish directory: `_site`

## Attivare il pannello admin

1. Su Netlify vai nel sito.
2. Vai in **Identity** e abilitalo.
3. Vai in **Identity → Services → Git Gateway** e abilitalo.
4. Vai in **Identity → Invite users** e invita la tua email.
5. Accetta l’invito via email.
6. Apri `https://tuosito.netlify.app/admin`.

Da lì modifichi contenuti e pubblichi. Ogni modifica crea un commit Git e Netlify rigenera il sito.

## Collegare mancuspie.com

Quando compri il dominio:

1. Netlify → Domain management.
2. Add custom domain.
3. Inserisci `mancuspie.com`.
4. Segui i DNS che Netlify ti dà.
5. Attendi propagazione.

## Lavorare in locale

Serve Node.js.

```bash
npm install
npm run start
```

Poi apri l’indirizzo locale indicato dal terminale.

Per testare il CMS in locale:

```bash
npx decap-server
npm run start
```

## Dove modificare il design

- CSS: `src/style.css`
- Layout base: `src/_includes/base.njk`
- Sidebar/logo: `src/_includes/sidebar.njk`
- Homepage: `src/index.njk`
- Immagini: `src/assets/`
- Contenuti: `src/content/`
