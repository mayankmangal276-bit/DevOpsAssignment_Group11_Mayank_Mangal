# NPM Commands Notes

## What is NPM?

**NPM (Node Package Manager)** is the default package manager for Node.js.

It is used to:

- Install packages
- Manage dependencies
- Run scripts
- Run tests
- Build projects
- Check security vulnerabilities
- Manage package versions

---

# 1. npm init

### Command

```bash
npm init
```

### Use

Creates a `package.json` file interactively.

### Example

```bash
mkdir my-project
cd my-project
npm init
```

---

# 2. npm init -y

### Command

```bash
npm init -y
```

### Use

Creates a `package.json` file with default values.

### Difference

```text
npm init     → Asks questions
npm init -y  → Uses default values
```

---

# 3. npm install

### Command

```bash
npm install
```

Short form:

```bash
npm i
```

### Use

Installs all dependencies mentioned in `package.json`.

### Example

```bash
npm install
```

It creates/updates:

```text
node_modules/
package-lock.json
```

---

# 4. npm install <package>

### Command

```bash
npm install express
```

### Use

Installs a specific package.

### Example

```bash
npm install express
npm install mongoose
npm install cors
npm install dotenv
```

The package is added to `dependencies` in `package.json`.

---

# 5. npm install <package>@<version>

### Command

```bash
npm install express@5
```

### Use

Installs a specific version of a package.

### Example

```bash
npm install react@18
```

---

# 6. npm install -D <package>

### Command

```bash
npm install -D nodemon
```

Short form:

```bash
npm i -D nodemon
```

### Use

Installs a package as a **development dependency**.

### Example

```bash
npm install -D nodemon
npm install -D eslint
npm install -D prettier
```

These packages are added to:

```json
{
  "devDependencies": {}
}
```

---

# 7. npm install -g <package>

### Command

```bash
npm install -g <package>
```

### Use

Installs a package globally on the system.

### Example

```bash
npm install -g nodemon
```

### Note

Global installation is useful for tools intended to be used system-wide. Project dependencies are normally installed locally.

---

# 8. npm uninstall

### Command

```bash
npm uninstall express
```

Short form:

```bash
npm un express
```

### Use

Removes a package from the project.

It updates:

```text
node_modules/
package.json
package-lock.json
```

---

# 9. npm update

### Command

```bash
npm update
```

### Use

Updates installed packages according to the version ranges specified in `package.json`.

### Specific Package

```bash
npm update express
```

---

# 10. npm outdated

### Command

```bash
npm outdated
```

### Use

Shows packages for which newer versions are available.

Typical information:

```text
Package | Current | Wanted | Latest
```

---

# 11. npm run

### Command

```bash
npm run
```

### Use

Shows the scripts available in `package.json`.

Example:

```json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "test": "jest",
    "lint": "eslint ."
  }
}
```

---

# 12. npm run <script>

### Command

```bash
npm run <script-name>
```

### Example

```bash
npm run dev
npm run build
npm run test
npm run lint
```

### Use

Runs a custom script defined inside `package.json`.

---

# 13. npm run dev

### Command

```bash
npm run dev
```

### Use

Runs the project in development mode.

### Example

For a Vite frontend:

```json
{
  "scripts": {
    "dev": "vite"
  }
}
```

Then:

```bash
npm run dev
```

---

# 14. npm start

### Command

```bash
npm start
```

### Use

Runs the `start` script from `package.json`.

### Example

```json
{
  "scripts": {
    "start": "node server.js"
  }
}
```

Running:

```bash
npm start
```

executes:

```bash
node server.js
```

---

# 15. npm test

### Command

```bash
npm test
```

### Use

Runs the project's test script.

### Example

```json
{
  "scripts": {
    "test": "jest"
  }
}
```

Then:

```bash
npm test
```

---

# 16. npm run build

### Command

```bash
npm run build
```

### Use

Creates a production-ready build of the application.

### Example

```json
{
  "scripts": {
    "build": "vite build"
  }
}
```

Run:

```bash
npm run build
```

Typical output:

```text
dist/
```

### Build Flow

```text
Source Code
     ↓
npm run build
     ↓
Build Tool
     ↓
Production Files
     ↓
Deployment
```

---

# 17. npm ci

### Command

```bash
npm ci
```

### Use

Performs a clean and reproducible installation using `package-lock.json`.

### Common Use

- CI/CD pipelines
- Automated builds
- Testing environments
- Production deployments

### Difference

```text
npm install
     ↓
Install dependencies
     ↓
May update package-lock.json


npm ci
     ↓
Clean installation
     ↓
Uses package-lock.json
```

---

# 18. npm list

### Command

```bash
npm list
```

### Use

Shows installed packages.

### Top-level packages only

```bash
npm list --depth=0
```

Example:

```text
project
├── express
├── mongoose
└── cors
```

---

# 19. npm view

### Command

```bash
npm view express
```

### Use

Shows information about a package from the NPM registry.

### Latest Version

```bash
npm view express version
```

### All Versions

```bash
npm view express versions
```

---

# 20. npm info

### Command

```bash
npm info express
```

### Use

Displays information about an NPM package.

---

# 21. npm search

### Command

```bash
npm search express
```

### Use

Searches for packages in the NPM registry.

---

# 22. npm audit

### Command

```bash
npm audit
```

### Use

Checks project dependencies for known security vulnerabilities.

### Example

```text
Project Dependencies
        ↓
    npm audit
        ↓
Security Vulnerability Check
```

---

# 23. npm audit fix

### Command

```bash
npm audit fix
```

### Use

Attempts to automatically fix compatible dependency vulnerabilities.

### Note

Review the changes after running this command because some updates may affect the project.

---

# 24. npm cache verify

### Command

```bash
npm cache verify
```

### Use

Verifies the NPM cache.

---

# 25. npm cache clean

### Command

```bash
npm cache clean --force
```

### Use

Clears the NPM cache.

### Note

Usually used only for troubleshooting cache-related problems.

---

# 26. npm version

### Command

```bash
npm version
```

### Use

Displays package version information.

---

# 27. npm version patch

### Command

```bash
npm version patch
```

### Example

```text
1.0.0 → 1.0.1
```

### Use

Used for patch/bug-fix releases.

---

# 28. npm version minor

### Command

```bash
npm version minor
```

### Example

```text
1.0.0 → 1.1.0
```

### Use

Used for backward-compatible feature releases.

---

# 29. npm version major

### Command

```bash
npm version major
```

### Example

```text
1.0.0 → 2.0.0
```

### Use

Used when making breaking changes.

---

# 30. npx

### Command

```bash
npx <command>
```

### Use

Executes a package command.

### Example

```bash
npx create-vite@latest
```

Another example:

```bash
npx eslint .
```

### NPM vs NPX

```text
NPM
 ↓
Install and manage packages

NPX
 ↓
Execute package commands
```

---

# 31. npm config list

### Command

```bash
npm config list
```

### Use

Displays NPM configuration.

---

# 32. npm config get

### Command

```bash
npm config get registry
```

### Use

Gets a specific NPM configuration value.

---

# 33. npm config set

### Command

```bash
npm config set key value
```

### Use

Sets an NPM configuration value.

---

# 34. npm config delete

### Command

```bash
npm config delete key
```

### Use

Deletes an NPM configuration value.

---

# 35. npm doctor

### Command

```bash
npm doctor
```

### Use

Checks the NPM environment and reports common problems.

---

# 36. npm help

### Command

```bash
npm help
```

### Use

Displays general NPM help.

### Help for a specific command

```bash
npm help install
```

---

# 37. npm --help

### Command

```bash
npm --help
```

### Use

Displays NPM command information.

---

# 38. npm <command> --help

### Command

```bash
npm install --help
```

### Use

Displays help for a specific command.

---

# 39. npm login

### Command

```bash
npm login
```

### Use

Logs in to an NPM registry.

Mainly useful when publishing packages.

---

# 40. npm whoami

### Command

```bash
npm whoami
```

### Use

Shows the currently authenticated NPM user.

---

# 41. npm publish

### Command

```bash
npm publish
```

### Use

Publishes a package to the NPM registry.

> Mainly used when creating and distributing your own NPM package.

---

# 42. npm version for Release

A common release process is:

```bash
npm version patch
npm publish
```

For a minor release:

```bash
npm version minor
npm publish
```

For a major release:

```bash
npm version major
npm publish
```

---

# FSD Project Example

A Full Stack Development project can have:

```text
FSD-Project/
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── package-lock.json
│
├── backend/
│   ├── src/
│   ├── server.js
│   ├── package.json
│   └── package-lock.json
│
└── README.md
```

---

# Frontend Commands

Move into frontend:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Run development server:

```bash
npm run dev
```

Run tests:

```bash
npm test
```

Run linting:

```bash
npm run lint
```

Create production build:

```bash
npm run build
```

---

# Backend Commands

Move into backend:

```bash
cd backend
```

Initialize project:

```bash
npm init -y
```

Install Express:

```bash
npm install express
```

Install Nodemon:

```bash
npm install -D nodemon
```

Run development server:

```bash
npm run dev
```

Run tests:

```bash
npm test
```

Start production server:

```bash
npm start
```

---

# Example Backend package.json

```json
{
  "name": "backend",
  "version": "1.0.0",
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js",
    "test": "jest",
    "lint": "eslint ."
  },
  "dependencies": {
    "express": "^5.0.0"
  },
  "devDependencies": {
    "nodemon": "^3.0.0",
    "jest": "^30.0.0",
    "eslint": "^9.0.0"
  }
}
```

---

# DevOps Build Workflow

```text
Developer Code
      ↓
npm ci
      ↓
Install Dependencies
      ↓
npm test
      ↓
Run Tests
      ↓
npm run lint
      ↓
Code Quality Check
      ↓
npm run build
      ↓
Production Build
      ↓
Deploy
```

---

# Important NPM Build Tools

| Tool | Purpose |
|---|---|
| Vite | Development server and production build |
| Webpack | Module bundling |
| Babel | JavaScript transpilation |
| TypeScript | TypeScript compilation |
| ESLint | Code quality checking |
| Prettier | Code formatting |
| Jest | Automated testing |

---

# Quick Revision Cheat Sheet

| Command | Use |
|---|---|
| `npm init` | Initialize project |
| `npm init -y` | Initialize with defaults |
| `npm install` | Install dependencies |
| `npm install <package>` | Install package |
| `npm install -D <package>` | Install development dependency |
| `npm install -g <package>` | Install globally |
| `npm uninstall <package>` | Remove package |
| `npm update` | Update packages |
| `npm outdated` | Find outdated packages |
| `npm run` | Show project scripts |
| `npm run dev` | Run development server |
| `npm start` | Start application |
| `npm test` | Run tests |
| `npm run lint` | Check code quality |
| `npm run build` | Create production build |
| `npm ci` | Clean CI/CD installation |
| `npm list` | List installed packages |
| `npm view <package>` | View package information |
| `npm search <keyword>` | Search packages |
| `npm audit` | Check security vulnerabilities |
| `npm audit fix` | Fix compatible vulnerabilities |
| `npm cache verify` | Verify NPM cache |
| `npm version patch` | Patch release |
| `npm version minor` | Minor release |
| `npm version major` | Major release |
| `npx <command>` | Execute package command |
| `npm doctor` | Diagnose NPM environment |
| `npm login` | Login to registry |
| `npm whoami` | Show logged-in user |
| `npm publish` | Publish package |
| `npm -v` | Show NPM version |
| `npm --help` | Show help |

---

# Most Important Commands for DevOps

```bash
npm ci
```

**Install dependencies in a clean and reproducible way.**

```bash
npm test
```

**Run automated tests.**

```bash
npm run lint
```

**Check code quality.**

```bash
npm run build
```

**Create production-ready build.**

```bash
npm start
```

**Start the application.**

---

# Easy Memory Trick

```text
npm init -y
      ↓
Project Setup

npm install
      ↓
Install Dependencies

npm run dev
      ↓
Development

npm test
      ↓
Testing

npm run lint
      ↓
Code Quality

npm run build
      ↓
Production Build

npm start
      ↓
Run Application

npm ci
      ↓
CI/CD Installation

npm audit
      ↓
Security Check
```

---

# Viva Questions

## What is NPM?

> NPM stands for Node Package Manager. It is used to manage Node.js packages, dependencies, and project scripts.

## What is npm install?

> `npm install` installs the dependencies specified in `package.json`.

## What is npm ci?

> `npm ci` performs a clean and reproducible installation using the lockfile and is commonly used in CI/CD.

## What is npm run build?

> `npm run build` executes the build script defined in `package.json` and normally generates production-ready files.

## What is npm test?

> `npm test` executes the project's test script.

## What is npm run?

> `npm run` is used to execute scripts defined in `package.json`.

## What is NPX?

> NPX is used to execute package binaries and commands.

## Why is NPM useful in DevOps?

> NPM helps automate dependency installation, testing, linting, building, and other project tasks in CI/CD pipelines.
