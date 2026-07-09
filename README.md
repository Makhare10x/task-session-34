# Session 34 - Homework Task
## Build Tools & Package Management (npm)

**Estimated Time:** 6–8 hours

---

### Task Description

> ⚠️ **Read this first:** Do **NOT** commit `node_modules/` to your repository - a `.gitignore` is already included in the starter repo. You submit the recipe (`package.json` + `package-lock.json`), not the installed folder.

---

## Instructions

---

### Task 1 - Initialise a Project & Use a Dependency

1. Create a folder `mini-utils` and run `npm init -y`.
2. Install `lodash`, then in `index.js` use at least **three** lodash functions (e.g. `_.capitalize`, `_.chunk`, `_.uniq`) and `console.log` each result.
3. Add a `"start": "node index.js"` script and confirm `npm start` prints your output.

---

### Task 2 - dependencies vs devDependencies

1. In `mini-utils`, install `dayjs` as a normal dependency.
2. Install `eslint` and `jest` as **dev** dependencies (`npm i -D eslint jest`).
3. Confirm in `package.json` that `dayjs` sits under `dependencies` and `eslint` + `jest` sit under `devDependencies`.

---

### Task 3 - npm Scripts

Add these scripts to `package.json` and run every one - each must execute successfully:

```json
"scripts": {
  "start": "node index.js",
  "lint":  "eslint .",
  "hello": "echo Hello, npm!",
  "info":  "node -v && npm -v"
}
```

Run: `npm start`, `npm run hello`, `npm run info`, `npm run lint`.

---

### Task 4 - Semantic Versioning in Practice

1. Install a specific old version: `npm install dayjs@1.11.0`. Notice `package.json` now shows `^1.11.0`.
2. Run `npm ls dayjs` to see exactly which version is installed.
3. Change `^1.11.0` to `~1.11.0` in `package.json`, delete `node_modules` and `package-lock.json`, then run `npm install` and `npm ls dayjs` again to see which version resolves.
4. Run `npm outdated` to list packages with newer versions, then `npm update` to update within the allowed ranges.

---

### Task 5 - The Lockfile & npm ci

1. Make sure `package-lock.json` exists (it is created automatically when you install).
2. Delete the entire `node_modules` folder.
3. Run `npm ci` and confirm the project reinstalls cleanly from the lockfile.
4. Run `npm ls --depth=0` to list your top-level installed packages.

---

### Task 6 - ESLint in Action

1. Run `npx eslint --init` to generate a config.
2. Create `messy.js` with **three deliberate problems**: an unused variable, `==` instead of `===`, and a stray `debugger` statement.
3. Run `npx eslint messy.js` - it should flag all three.
4. Fix all three problems and re-run until ESLint reports **no problems**.

---

### Task 7 - Fix the Broken package.json

Create a folder `broken-project` and paste the file below as its `package.json`. It has **four** mistakes that make npm fail. Fix them so that `npm install` runs successfully and `npm start` works (add a tiny `index.js` that logs something).

```json
{
  "name": "broken app",
  "version": 1.0,
  "scripts": {
    "start": "node index.js",
    "test": "jest",
  }
  "dependencies": {
    "lodash": "^4.17.21"
  }
}
```

> ✅ **Done when:** running `npm install` succeeds (a `package-lock.json` is generated) and `npm start` runs without error.

---

## Acceptance Criteria

| Task | Criteria |
|------|----------|
| Task 1 | mini-utils initialises; three lodash functions used and logged; npm start works |
| Task 2 | dayjs in dependencies; eslint & jest in devDependencies |
| Task 3 | All four scripts run successfully |
| Task 4 | Range changed to `~` and reinstalled; `npm ls` and `npm update` run |
| Task 5 | node_modules deleted and rebuilt cleanly with `npm ci` |
| Task 6 | messy.js flagged for all 3 issues, then fixed and clean |
| Task 7 | Broken package.json fixed; `npm install` succeeds and `npm start` runs |

---

## Submission

1. Fork this repository to your own GitHub account:

```
https://github.com/Makhare10x/task-session-34.git
```

2. Clone **your fork** (use your own username in the URL):

```
git clone https://github.com/<your-username>/task-session-34.git
cd task-session-34
```

3. Work on the `main` branch of your forked project. Your folder structure should look like:

```
task-session-34/
├── mini-utils/       (tasks 1–6, WITHOUT node_modules)
│   ├── package.json
│   ├── package-lock.json
│   ├── index.js
│   └── messy.js
└── broken-project/   (task 7, WITHOUT node_modules)
    ├── package.json
    ├── package-lock.json
    └── index.js
```

4. Commit and push to your fork:

```
git add .
git commit -m "Session 34 homework complete"
git push origin main
```

5. Share the link to **your forked repository** for review **before the deadline** - and make sure `node_modules/` is **not** committed.
```
Share repos in this Google Sheet file: https://docs.google.com/spreadsheets/d/1Og4orLBGzyyJK8TPFZHfdtDCgfygs-87Y9W6ROG5ktU/edit?usp=sharing
```
