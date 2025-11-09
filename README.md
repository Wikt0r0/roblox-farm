# roblox-farm

A farming game project for Roblox.

## 🛠️ Requirements

- [Git](https://git-scm.com/)
- [Rust](https://rustup.rs/) (for Foreman)
- [Roblox Studio](https://www.roblox.com/create)
- [Visual Studio Code](https://code.visualstudio.com/) (recommended)

## 🚀 Initial Project Setup

### 1. Install Foreman

```bash
cargo install foreman
```

### 2. Install Development Tools

```bash
foreman install
```

This will install:
- **Rojo** - code synchronization with Roblox Studio
- **Selene** - Luau linter
- **StyLua** - code formatter

**Note:** Wally (package manager) is commented out in `foreman.toml` due to compilation issues on newer systems. If you need it, install from releases:
```bash
# Download from: https://github.com/UpliftGames/wally/releases
# Or use aftman instead: https://github.com/LPGhatguy/aftman
```

**Add to PATH (optional):** To use tools directly without `foreman run`, add to your shell config:
```bash
export PATH="$HOME/.foreman/bin:$PATH"
```

### 3. Start Rojo

```bash
rojo serve
```

Then in Roblox Studio:
- Open the Rojo plugin
- Connect to localhost:34872

### 4. Install Dependencies (Optional, if using Wally)

If you've installed Wally and have dependencies in `wally.toml`:
```bash
wally install
```

## 💻 Working with the Project

### Format Code

```bash
stylua src/
# or with full path:
~/.foreman/bin/stylua src/
```

### Lint Code

```bash
selene src/
# or with full path:
~/.foreman/bin/selene src/
```

### Build Project

```bash
rojo build -o build.rbxl
# or with full path:
~/.foreman/bin/rojo build -o build.rbxl
```

## 📁 Project Structure

```
src/
├── client/         # Client-side code
├── server/         # Server-side code
└── shared/         # Shared code
```

## 🔧 VS Code

When you open the project in VS Code, recommended extensions will be automatically suggested:
- Luau LSP (JohnnyMorganz.luau-lsp)
- StyLua (JohnnyMorganz.stylua)
- Selene (Kampfkarren.selene-vscode)
- Rojo (evaera.vscode-rojo)

Code will be automatically formatted on save.

## 👥 Team Workflow

1. Always pull before starting work: `git pull`
2. Format code before committing: `stylua src/`
3. Check for errors: `selene src/`
4. Commit with clear messages
5. Push regularly so the team can see progress

## 📝 Path Aliases

You can use aliases in the project:
- `@client` → `src/client`
- `@server` → `src/server`
- `@shared` → `src/shared`

## 🐛 Troubleshooting

### Rojo won't connect to Studio
- Check if `rojo serve` is running
- Restart Roblox Studio
- Verify the Rojo plugin is installed

### StyLua doesn't work
- Make sure you installed the tools: `foreman install`
- Check if the StyLua extension is installed in VS Code

### Selene reports errors
- Ensure `selene.toml` is in the project root folder
- Verify you're using the correct Roblox standard
