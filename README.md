# arode-landing

Page d'attente temporaire pour `arodestudio.com`, en attendant le cutover V2.

Site statique : un `index.html`, aucune dépendance, aucun build.

## Déploiement

```bash
git init && git add -A && git commit -m "Landing page Arode"
gh repo create arode-landing --private --source=. --push
```

Puis sur Vercel : New Project → import `arode-landing` → Framework Preset **Other** → Deploy.
Ensuite Settings → Domains → ajouter `arodestudio.com` et `www.arodestudio.com`.

DNS chez le registrar :
- `A` `@` → `76.76.21.21`
- `CNAME` `www` → `cname.vercel-dns.com`

## Cutover vers la V2

1. Projet `arode-landing` → Settings → Domains → retirer `arodestudio.com` et `www`
2. Projet de la V2 → Settings → Domains → ajouter `arodestudio.com` et `www`

Aucun changement DNS nécessaire : les deux projets doivent être sur le même compte Vercel.
Vérifier que le déploiement V2 est vert **avant** de retirer le domaine ici.

## Assets

- `assets/wave.mp4` / `assets/wave.webm` — animation d'encre, filigrane Gemini retiré (filtre ffmpeg `delogo`)
- `assets/surfer.svg` — curseur au survol du logo
