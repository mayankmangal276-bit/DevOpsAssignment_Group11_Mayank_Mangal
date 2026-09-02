# 🛠️ NPM Build Tools — Cheat Sheet

## 📦 NPM

**NPM = Node Package Manager**

Used for:
- Dependency Management
- Build Automation
- Testing
- Script Execution
- Package Management

---

## 🔑 Important Commands

| Command | Use |
|---|---|
| `npm init` | Creates `package.json` |
| `npm install` | Installs all dependencies |
| `npm install <package>` | Installs a package |
| `npm install -D <package>` | Installs development dependency |
| `npm uninstall <package>` | Removes a package |
| `npm update` | Updates dependencies |
| `npm run <script>` | Runs a script |
| `npm run build` | Creates production build |
| `npm test` | Runs tests |
| `npm start` | Starts application |
| `npm ci` | Clean & reproducible dependency installation |

---

## 🏗️ Build Tools

| Tool | Main Purpose |
|---|---|
| **Webpack** | Bundles project files |
| **Vite** | Fast development + production build |
| **Babel** | Converts modern JavaScript |
| **TypeScript** | Compiles TypeScript → JavaScript |
| **ESLint** | Finds code errors/style issues |
| **Prettier** | Formats code |

---

## 📄 package.json

Contains:

```text
Project Information
       ↓
Dependencies
       ↓
Dev Dependencies
       ↓
NPM Scripts
