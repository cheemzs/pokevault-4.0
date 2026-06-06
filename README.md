# PokeVault 4.0

Personal Pokémon card investment tracker — deployed on Vercel with Supabase.

## Setup

1. **Supabase**: Run `supabase_setup.sql` in your Supabase SQL editor.
2. **Env vars** (set in Vercel dashboard → Settings → Environment Variables):
   - `POKEPRICE_API_KEY` — your PokéPrice Pro API key
3. **Deploy**: Push to GitHub and connect to Vercel. No build step needed.

## Local dev

```bash
# Serve the public folder with any static server, e.g.:
npx serve public
```

## Fixes applied (v3.0.1)
- `public/js/app.js`: Removed accidental shell heredoc wrapper (`cat > ... << 'ENDOFFILE'`) that was breaking the entire JS file
- `vercel.json`: Removed conflicting `rewrites` block (Vercel does not allow both `rewrites` and `routes` simultaneously)
- `api/pokeprice.js`: Fixed env variable name mismatch (`POKEPRICE_KEY` → `POKEPRICE_API_KEY`)
- `.env.example`: Updated to reflect correct env var names
