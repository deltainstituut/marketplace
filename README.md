# Delta Instituut Marketplace

Plugin marketplace voor het Delta Instituut team.

## Marketplace toevoegen

In Claude Code: **Settings > Plugins > Add marketplace** en voer in:

```
deltainstituut/marketplace
```

## Plugin updaten (voor maintainers)

Na een push naar de plugin repo moet je de `sha` in `.claude-plugin/marketplace.json` updaten, anders krijgen gebruikers de nieuwe versie niet.

1. Haal de laatste commit hash op:
   ```bash
   gh api repos/deltainstituut/delta-instituut-plugin/commits/main --jq '.sha'
   ```

2. Update de `sha` in `.claude-plugin/marketplace.json`:
   ```json
   "source": {
     "source": "url",
     "url": "https://github.com/deltainstituut/delta-instituut-plugin.git",
     "sha": "<nieuwe-commit-hash>"
   }
   ```

3. Commit en push naar deze marketplace repo.

Gebruikers krijgen de update bij hun volgende sync.
