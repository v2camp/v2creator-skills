# Usage

## Command Syntax

```bash
./sc-run sc-compress-image main <input> [options]
```

## Options

| Option | Short | Description | Default |
|--------|-------|-------------|---------|
| `<input>` | | File or directory | Required |
| `--output` | `-o` | Output path | Same path, new ext |
| `--format` | `-f` | webp, png, jpeg | webp |
| `--quality` | `-q` | Quality 0-100 | 80 |
| `--keep` | `-k` | Keep original | false |
| `--recursive` | `-r` | Process subdirs | false |
| `--json` | | JSON output | false |

## Examples

```bash
# Single file → WebP (replaces original)
./sc-run sc-compress-image main image.png

# Keep PNG format
./sc-run sc-compress-image main image.png -f png --keep

# Directory recursive
./sc-run sc-compress-image main ./images/ -r -q 75

# JSON output
./sc-run sc-compress-image main image.png --json
```

## Preferences (EXTEND.md)

Check EXTEND.md existence (priority order):

1. `.v2creator/compress-image/EXTEND.md` (Project directory)
2. `$HOME/.v2creator/compress-image/EXTEND.md` (User home)
3. `${XDG_CONFIG_HOME:-$HOME/.config}/v2creator/compress-image/EXTEND.md`

**EXTEND.md Supports**:
- `default_format`: webp | png | jpeg
- `default_quality`: 0-100
- `keep_original`: true | false
