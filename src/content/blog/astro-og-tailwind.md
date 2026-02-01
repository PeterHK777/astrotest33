---
title: "Kom godt i gang med Astro og Tailwind"
description: "En guide til at opsætte et Astro-projekt med Tailwind CSS fra bunden."
date: 2026-01-30
author: "Peter"
---

At kombinere Astro med Tailwind CSS giver en effektiv udviklingsoplevelse. Her er et overblik over hvordan det fungerer.

## Opsætning

Først opretter du et nyt Astro-projekt:

```bash
npm create astro@latest
```

Derefter tilføjer du Tailwind:

```bash
npx astro add tailwind
```

Det var det! Astro konfigurerer automatisk Tailwind for dig.

## Content Collections

Astro v5 bruger **Content Collections** til at organisere dit indhold. Du definerer et schema i `src/content.config.ts` og lægger dine Markdown-filer i `src/content/`-mappen.

### Eksempel på schema

```typescript
const blog = defineCollection({
  schema: z.object({
    title: z.string(),
    description: z.string(),
    date: z.coerce.date(),
  }),
});
```

## Tailwind Typography

For at style Markdown-indhold bruger vi `@tailwindcss/typography`-pluginet. Det giver en `prose`-klasse der automatisk styler HTML genereret fra Markdown.

Det gør det nemt at få flot typografi uden at skrive brugerdefineret CSS for hvert enkelt element.
