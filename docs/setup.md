# Structure

```shell
.obsidian
├── core-plugins.json  # ✅
├── community-plugins.json  # ✅
├── plugins  # ✅
│   ├── obsidian-excalidraw-plugin
│   └── obsidian-linter
├── themes  # ✅
│   └── Catppuccin
├── app.json  # 🤔
├── appearance.json
└── workspace.json  # 🙅
```

# Setup

## Option 1: Symlink entire `.obsidian/`

Simple. One symlink, zero maintenance. Caveat: `workspace.json` is shared — all vaults share the same window layout.

```shell
# Mac / Linux shell
ln -s /path/to/obsidian-setup/.obsidian /path/to/vault/.obsidian

# Windows PowerShell
New-Item -ItemType SymbolicLink -Path "C:\path\to\vault\.obsidian" -Target "C:\path\to\obsidian-setup\.obsidian"
# Windows CMD (junction, no admin needed)
mklink /J "C:\path\to\vault\.obsidian" "C:\path\to\obsidian-setup\.obsidian"
```

## Option 2: Exclude `workspace.json` (script)

Per-vault `.obsidian/` directory, symlink individual files/dirs. Each vault keeps its own layout.

```shell
# Mac / Linux shell
bash scripts/link-vault.sh /path/to/vault

# Windows PowerShell
powershell -ExecutionPolicy Bypass -File scripts/link-vault.ps1 -Vault "C:\path\to\vault"
# Windows CMD
powershell -ExecutionPolicy Bypass -File scripts\link-vault.ps1 -Vault "C:\path\to\vault"
```
