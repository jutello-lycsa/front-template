# Configuración de Branch Protection

## Protección de rama `main`

Para configurar la protección de la rama principal, ir a **Settings → Branches → Add rule** para `main`:

### Reglas requeridas

1. **Require status checks to pass before merging**
   - ✅ Require branches to be up to date before merging
   - Seleccionar status check: `build` (del workflow CI)

2. **Require a pull request before merging**
   - ✅ Require approvals: 0 (para permitir auto-merge de Dependabot)
   - ✅ Dismiss stale pull request approvals when new commits are pushed

3. **Do not allow bypassing the above settings**
   - ✅ Include administrators (opcional pero recomendado)

4. **Allow auto-merge**
   - Activar en **Settings → General → Pull Requests**
   - ✅ Allow auto-merge

### Resultado

- ❌ Pushes directos a `main` bloqueados
- ✅ Solo PRs con CI verde pueden mergearse
- ✅ Dependabot puede crear PRs y auto-merge si CI pasa
- ✅ Auto-merge habilitado para todos los PRs
