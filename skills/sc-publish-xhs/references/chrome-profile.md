# Chrome Profile

All CDP skills share a single profile directory. Do NOT create per-skill profiles.

Override: `SC_CHROME_PROFILE_DIR` env var (takes priority over all defaults). Set in `~/.v2creator/.env` for user-level override.

| Platform | Default Path |
|----------|-------------|
| macOS | `~/Library/Application Support/v2creator/chrome-profile` |
| Linux | `$XDG_DATA_HOME/v2creator/chrome-profile` (fallback `~/.local/share/`) |
| Windows | `%APPDATA%/v2creator/chrome-profile` |
| WSL | Windows home `/.local/share/v2creator/chrome-profile` |

New skills: use `SC_CHROME_PROFILE_DIR` only (not per-skill env vars like `X_BROWSER_PROFILE_DIR`).

## Self-Healing CDP

To improve reliability, CDP-based scripts should implement automatic port cleanup:

```typescript
import { killChromeUsingPort } from '../../scripts/vendor/sc-chrome-cdp';

// Before launching Chrome
await killChromeUsingPort(9222); 
```

This removes the need for Agent manual intervention (e.g., `pkill Chrome`) when port conflicts occur.
