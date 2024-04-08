# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default {
  // other rules...
  parserOptions: {
    ecmaVersion: "latest",
    sourceType: "module",
    project: ["./tsconfig.json", "./tsconfig.node.json"],
    tsconfigRootDir: __dirname,
  },
};
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list

## ESlint + Prettier + huskey

- ESlint
  - 構文ルールを決めるために使用されるライブラリ
  - 静的テストの一部
  - コンパイルする前にコードの記述が正しいか、プロジェクトのルールに沿っているのかチェックすることができる
- 本番環境で使用することはないので、開発環境の -D でインストールします。

```shell
% npm i -D eslint

up to date, audited 335 packages in 565ms

101 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```

```shell
% npx eslint --init
You can also run this command directly using 'npm init @eslint/config'.
? How would you like to use ESLint? …
  To check syntax only
❯ To check syntax and find problems
  To check syntax, find problems, and enforce code style

% npx eslint --init
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · problems
? What type of modules does your project use? …
❯ JavaScript modules (import/export)
  CommonJS (require/exports)
  None of these

% npx eslint --init
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · problems
✔ What type of modules does your project use? · esm
? Which framework does your project use? …
❯ React
  Vue.js
  None of these

% npx eslint --init
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · problems
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · react
? Does your project use TypeScript? …
  No
❯ Yes

% npx eslint --init
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · problems
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · react
✔ Does your project use TypeScript? · typescript
? Where does your code run? …  (Press <space> to select, <a> to toggle all, <i> to invert selection)
✔ Browser
  Node

% npx eslint --init
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · problems
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · react
✔ Does your project use TypeScript? · typescript
✔ Where does your code run? · browser
The config that you've selected requires the following dependencies:

eslint, globals, @eslint/js, typescript-eslint, eslint-plugin-react
? Would you like to install them now? › No / Yes

% npx eslint --init
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · problems
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · react
✔ Does your project use TypeScript? · typescript
✔ Where does your code run? · browser
The config that you've selected requires the following dependencies:

eslint, globals, @eslint/js, typescript-eslint, eslint-plugin-react
✔ Would you like to install them now? · No / Yes
? Which package manager do you want to use? …
❯ npm
  yarn
  pnpm
  bun

% npx eslint --init
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · problems
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · react
✔ Does your project use TypeScript? · typescript
✔ Where does your code run? · browser
The config that you've selected requires the following dependencies:

eslint, globals, @eslint/js, typescript-eslint, eslint-plugin-react
✔ Would you like to install them now? · No / Yes
✔ Which package manager do you want to use? · npm
☕️Installing...

added 61 packages, changed 10 packages, and audited 396 packages in 5s

141 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
Successfully created /Users/oikawa.masaki/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test/eslint.config.js file.
```

## Prettier

- コード整形

```shell
% npm i -D prettier

added 1 package, and audited 397 packages in 543ms

142 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```

- package.json の修正

```json
"scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "lint": "eslint src",
    "lint:fix": "eslint --fix src",
    "preview": "vite preview",
    "test": "vitest",
    "format": "prettier --write src"
  },
```

## husky

```shell
% npm i -D husky

added 1 package, and audited 398 packages in 1s

143 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

% npx husky init
.git can't be found%
```

```shell
% git init
Initialized empty Git repository in /Users/oikawa.masaki/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test/.git/

% git remote -v

% git remote add origin git@github.com:oikawa-masaki/huskey-env-setup.git

% git remote -v
origin	git@github.com:oikawa-masaki/huskey-env-setup.git (fetch)
origin	git@github.com:oikawa-masaki/huskey-env-setup.git (push)

% git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.eslintrc.cjs
	.gitignore
	.husky/
	README.md
	eslint.config.js
	index.html
	package-lock.json
	package.json
	prettier.config.js
	public/
	src/
	tsconfig.json
	tsconfig.node.json
	vite.config.ts
	vitest-setup.ts

nothing added to commit but untracked files present (use "git add" to track)

% git add .

% git branch -M main

% git commit -m "Add husky"
[main (root-commit) f1ae501] Add husky
 23 files changed, 6498 insertions(+)
 create mode 100644 .eslintrc.cjs
 create mode 100644 .gitignore
 create mode 100644 .husky/pre-commit
 create mode 100644 README.md
 create mode 100644 eslint.config.js
 create mode 100644 index.html
 create mode 100644 package-lock.json
 create mode 100644 package.json
 create mode 100644 prettier.config.js
 create mode 100644 public/vite.svg
 create mode 100644 src/App.css
 create mode 100644 src/App.tsx
 create mode 100644 src/assets/react.svg
 create mode 100644 src/components/Book/Book.tsx
 create mode 100644 src/components/Input/TextInput.test.tsx
 create mode 100644 src/components/Input/TextInput.tsx
 create mode 100644 src/index.css
 create mode 100644 src/main.tsx
 create mode 100644 src/vite-env.d.ts
 create mode 100644 tsconfig.json
 create mode 100644 tsconfig.node.json
 create mode 100644 vite.config.ts
 create mode 100644 vitest-setup.ts

% git push
fatal: The current branch main has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin main

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


% git push --set-upstream origin main
Enumerating objects: 32, done.
Counting objects: 100% (32/32), done.
Delta compression using up to 8 threads
Compressing objects: 100% (25/25), done.
Writing objects: 100% (32/32), 58.29 KiB | 5.83 MiB/s, done.
Total 32 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:oikawa-masaki/huskey-env-setup.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

## lint-staged をインストール

```shell
% npm i -D lint-staged

added 36 packages, and audited 434 packages in 3s

161 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```

```json
"lint-staged": {
    "*.{js,jsx,ts,tsx}": [
      "eslint --fix",
      "prettier --write"
    ]
  },
```

```json
"scripts": {
    "lint": "eslint src",
    "preview": "vite preview",
    "test": "vitest --run",
  },
```

.husky/pre-commit

```
npx lint-staged

```

% touch .husky/pre-push
.husky/pre-push

```
npm run test
```

■以下、husly を動作させるためのコマンド一覧（git コマンド以下から）

```shell
oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test
% git init
Initialized empty Git repository in /Users/oikawa.masaki/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test/.git/

oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test [main]
% git branch -M main

oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test [main]
% git remote add origin git@github.com:oikawa-masaki/husky-test-2.git

oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test [main]
% git remote -v
origin  git@github.com:oikawa-masaki/husky-test-2.git (fetch)
origin  git@github.com:oikawa-masaki/husky-test-2.git (push)

oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test [main]
% npx husky init

oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test [main]
% touch .husky/pre-push

oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test [main]
% git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .eslintrc.cjs
        .gitignore
        .husky/
        README.md
        eslint.config.js
        index.html
        package-lock.json
        package.json
        prettier.config.js
        public/
        src/
        tsconfig.json
        tsconfig.node.json
        vite.config.ts
        vitest-setup.ts

nothing added to commit but untracked files present (use "git add" to track)

oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test [main]
% git add .

oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test ![main]
% git commit -m "husky-test-1"
⚠ Skipping backup because there’s no initial commit yet.

✔ Preparing lint-staged...
✔ Running tasks for staged files...
✔ Applying modifications from tasks...
[main (root-commit) a28e1d9] husky-test-1
 24 files changed, 7096 insertions(+)
 create mode 100644 .eslintrc.cjs
 create mode 100644 .gitignore
 create mode 100644 .husky/pre-commit
 create mode 100644 .husky/pre-push
 create mode 100644 README.md
 create mode 100644 eslint.config.js
 create mode 100644 index.html
 create mode 100644 package-lock.json
 create mode 100644 package.json
 create mode 100644 prettier.config.js
 create mode 100644 public/vite.svg
 create mode 100644 src/App.css
 create mode 100644 src/App.tsx
 create mode 100644 src/assets/react.svg
 create mode 100644 src/components/Book/Book.tsx
 create mode 100644 src/components/Input/TextInput.test.tsx
 create mode 100644 src/components/Input/TextInput.tsx
 create mode 100644 src/index.css
 create mode 100644 src/main.tsx
 create mode 100644 src/vite-env.d.ts
 create mode 100644 tsconfig.json
 create mode 100644 tsconfig.node.json
 create mode 100644 vite.config.ts
 create mode 100644 vitest-setup.ts

oikawa.masaki:~/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test [main]
% git push -u origin main

> vitest-setup-test@0.0.0 test
> vitest --run


 RUN  v1.4.0 /Users/oikawa.masaki/dev/udemy/Introduction-to-React-Testing-with-Vitest/vitest-setup-test

 ✓ src/components/Input/TextInput.test.tsx (2)
   ✓ TextInput Component test
   ✓ TextInput Event Test 2

 Test Files  1 passed (1)
      Tests  2 passed (2)
   Start at  22:20:46
   Duration  545ms (transform 144ms, setup 107ms, collect 169ms, tests 46ms, environment 81ms, prepare 48ms)

Enumerating objects: 33, done.
Counting objects: 100% (33/33), done.
Delta compression using up to 8 threads
Compressing objects: 100% (26/26), done.
Writing objects: 100% (33/33), 63.01 KiB | 15.75 MiB/s, done.
Total 33 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:oikawa-masaki/husky-test-2.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```
