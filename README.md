This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

- Installing latest version of Nextjs ie v13 with typescript

```
    npx create-next-app@latest --experimental-app --ts
```

- Project Setup
  -- we will move inside our app root directory

```
    cd datastructure
```

| we will be using `yarn` as a package manager, but you are open to use `npm` as well

```
    yarn install
    yarn dev
```

After running above command we will be having our application live on http://localhost:3000.

- Now to check our repo for production let's build our application

```yarn build

```

-- Note: It is recommended to close the server while running the build, but it is not manadatory.

- After running the build we will get good description about the application build.

```
    yarn run v1.22.17
    $ next build
    warn  - You have enabled experimental feature (appDir) in next.config.js.
    warn  - Experimental features are not covered by semver, and may cause unexpected or broken application behavior. Use at your own risk.
    info  - Thank you for testing `appDir` please leave your feedback at https://nextjs.link/app-feedback

    info  - Creating an optimized production build
    info  - Compiled successfully
    info  - Linting and checking validity of types ..info  - VS Code settings.json has been created for Next.js' automatic app types, this file can be added to .gitignore if desired
    info  - Linting and checking validity of types
    info  - Collecting page data
    info  - Generating static pages (3/3)
    info  - Finalizing page optimization

    Route (app)                                Size     First Load JS
    ─ ○ /                                      0 B                0 B
    + First Load JS shared by all              65.3 kB
    ├ chunks/17-8005a504a3fcc407.js          63 kB
    ├ chunks/main-app-c5031435e4d1ed94.js    200 B
    └ chunks/webpack-9e765e27c32b1a64.js     2.07 kB

    Route (pages)                              Size     First Load JS
    ┌ ○ /404                                   179 B          80.3 kB
    └ λ /api/hello                             0 B            80.2 kB
    + First Load JS shared by all              80.2 kB
    ├ chunks/main-22dc530da03ba9f1.js        77.9 kB
    ├ chunks/pages/_app-9f5490aa3d56632f.js  192 B
    └ chunks/webpack-9e765e27c32b1a64.js     2.07 kB

    λ  (Server)  server-side renders at runtime (uses getInitialProps or getServerSideProps)
    ○  (Static)  automatically rendered as static HTML (uses no initial props)

    Done in 56.45s.
```

## ## Engine Locking

- As we are working with node.js, so it's very important to settle on a single run time engine & package manager for every developer working on this application.
- In order to lock an engine we will be creating two files
  1. .nvmrc - this file informs the other developers about the node version being used
  2. .npmrc - this file informs other developers about the package manager being used

Note that the use of engine-strict didn't specifically say anything about yarn, we do that in package.json as given below:

```
{
    "name": "datastructure",
    "version": "0.1.0",
    "private": true,
    "scripts": {
        "dev": "next dev",
        "build": "next build",
        "start": "next start",
        "lint": "next lint"
    },
    "engines": {
        "node": ">=16.0.0",
        "yarn": ">=1.22.0",
        "npm": "please-use-yarn"
    },
    "dependencies": {
        "@types/node": "18.11.9",
        "@types/react": "18.0.25",
        "@types/react-dom": "18.0.8",
        "next": "13.0.2",
        "react": "18.2.0",
        "react-dom": "18.2.0",
        "typescript": "4.8.4"
    }
}

```

|In above the engines field is where we specify the specific versions of the tools[node engine, package manager] we are using

#### Version Control System

- As our intention is to create a scalable application, so it's very important to maintain our codebase and manage it's various versions and modules by different developers. So for maintaining & managing our codebase we will be using GIT as a VCS software and github as a cloud platform to host our codebase.
- Let's add our code to get tracked by the git

```
>git add .
> git status
On branch next-ts-13-boilerplate
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   .gitignore
        new file:   .npmrc
        new file:   .nvmrc
        new file:   .vscode/settings.json
        new file:   README.md
        new file:   app/globals.css
        new file:   app/head.tsx
        new file:   app/layout.tsx
        new file:   app/page.module.css
        new file:   app/page.tsx
        new file:   next.config.js
        new file:   package-lock.json
        new file:   package.json
        new file:   pages/api/hello.ts
        new file:   public/favicon.ico
        new file:   public/vercel.svg
        new file:   tsconfig.json
```

- Now it's the best time to write our first commit

```
     git commit -m "Datastructure Project Initialized"
[next-ts-13-boilerplate 098a405] Datastructure Project Initialized
 17 files changed, 1247 insertions(+)
 create mode 100644 datastructure/.gitignore
 create mode 100644 datastructure/.npmrc
 create mode 100644 datastructure/.nvmrc
 create mode 100644 datastructure/.vscode/settings.json
 create mode 100644 datastructure/app/globals.css
 create mode 100644 datastructure/app/head.tsx
 create mode 100644 datastructure/app/layout.tsx
 create mode 100644 datastructure/app/page.module.css
 create mode 100644 datastructure/app/page.tsx
 create mode 100644 datastructure/next.config.js
 create mode 100644 datastructure/package-lock.json
 create mode 100644 datastructure/public/favicon.ico
> git status
On branch next-ts-13-boilerplate
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)

no changes added to commit (use "git add" and/or "git commit -a")
> git add .\README.md
> git commit -m
error: switch `m' requires a value
> git commit -m "change: added new takeup"
[next-ts-13-boilerplate 8923639] change: added new takeup
 1 file changed, 25 insertions(+), 1 deletion(-)
```

- While writting the commit messages we will be following commit convention to write human redable commit message[https://www.conventionalcommits.org/en/v1.0.0/#summary]

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

##Configuring Code Formatting
In order to enforce common coding standard & rules for all the conftributor in order to maintain the best practices, style[formatting] & coding standard consistency. In order to achieve this we will be using two tools: 1. eslint : For maintaining the best practices coding standards 2. prettier. For automatic code formatting of the code.

    #1. eslint
        - eslint, automatically comes installed and pre-cofigured with nextjs projects, we will be making use of that with bit stricter rules. To do so we will configure everything in `.eslintrc.json` ie
        ```
            {
                "extends": ["next","next/core-web-vitals","eslint:recommended"],
                "globals":{
                    "React": "readonly"
                },
                "rules":{
                    "no-unused-vars": [1,{"args":"after-used","argsIgnorePattern":"^_"}]
                }
            }

        ```
        - In above eslintrc file we have added some configuration,
            - One of them is that we have said React will be always be defined even if we don't specifically import it.
            - Also I have added one custom rule to prefix unused variable with _ . So if we want to declare any variable for future use then we can prefix them with _.
        - Now let's install eslint package for nextjs ie eslint-config-next ie
            ``` yarn add -D eslint-config-next ```

        Now to test our lint rules hit the below command in command prompt/terminal
            ``` yarn lint ```
        The above command will show the below output ie..
        ```
            yarn lint
            yarn run v1.22.17
            $ next lint
            warn  - You have enabled experimental feature (appDir) in next.config.js.
            warn  - Experimental features are not covered by semver, and may cause unexpected or broken application behavior. Use at your own risk.
            info  - Thank you for testing `appDir` please leave your feedback at https://nextjs.link/app-feedback

            ✔ No ESLint warnings or errors
            Done in 3.26s.
        ```
    #2. Configuring Prettier
    We are adding Prettier as it will take care of automatically fomatting our files
    to add prettier to our repo run the below command
    ```
         yarn add -D prettier
    ```
    Also I highly recommend installing prettier VS code extension so that VS Code can handle the formatting of the files for us & we don't need to hit command every time to style our code. So let's create a file to keep all prettier related configuration inside it so that VS Code can use those settings for formatting the code.
    At root let's create a file `.prettierrc` add the below written code inside it
    ```
        {
            "trailingComma": "es5",
            "tabWidth": 2,
            "semi": true,
            "singleQuote": true
        }
    ```
    Now let's create another file at root ie .prettierignore which will contain all the files which we don't want prettier to ignore. Add the below files inside .prettierignore file
    ```
        .yarn
        .next
        dist
        node_modules
    ```
    Now let's add a new script in package.json file to run prettier
    - package.json
    ```
        "scripts": {
            "dev": "next dev",
            "build": "next build",
            "start": "next start",
            "lint": "next lint",
            "prettier": "prettier --write ."
        },
    ```
    Now let's check if prettier has been configured properly by running the below command
    ``` yarn prettier ```
    If everything works fine prettier will format all the files. We can see those changes by git status command

## Configuring Git Hooks
    We will be configuring *husky* which is a tool or git hook used for running scripts at different stages of the git process. 
    Example: while git add, commit, push etc
    We will try to set certain conditions, and only allow things like commit & push by the contributor only if code written meets those conditions, presuming that it indicates our project is of acceptable quality.
    Let's install husky by using the below command: 
        ``` yarn add -D husky ```
    Then, to create .husky directory where exactly our hooks will live. 
        ``` npx husky install ```
    Make sure *.husky* directory is included in our code repo as it's intended for other developers as well not just for me/you.

    Then we need to add script command for husky inside pakage.json file as given below
        "scripts": {
            "dev": "next dev",
            "build": "next build",
            "start": "next start",
            "lint": "next lint",
            "prettier": "prettier --write .",
            *"prepare": "husky install"*
        },
        ```"prepare": "husky install" ensures husky get's installed automatically when other developers run this project
        ```
    Now in order to create a run hook hit the below given command ie 
    ``` 
        npx husky add .husky/pre-commit "yarn lint"
    ```
    Above command says that in order for our commit to succed, the `yarn lint` script must first run and succed in this context means no errors. We can also configure warnings on failure of the hooks
    Note: ESLint config a setting of 1 is a warning and 2 is a n error. 

    Let's add one more hook ie
    ```
        npx husky add .husky/pre-push "yarn build"
    ```
    The above hook ensures that we are not allowed to push to the remote repository unless our code can successfully build.

## Commit Convention
    - Let's add one more tool which will encourage all the contributors of the repo to write standard commit messages. So let's add commitlint for this repo

    ``` yarn add -D @commitlint/config-conventional @commitlint/cli
    ```
    To configure commitlint we will be using set of standard defaults, but let's list explicitly in a ``` commitlint.config.js ``` file for all contributers working on this repo.
    ```
        // build: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
        // ci: Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs)
        // docs: Documentation only changes
        // feat: A new feature
        // fix: A bug fix
        // perf: A code change that improves performance
        // refactor: A code change that neither fixes a bug nor adds a feature
        // style: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
        // test: Adding missing tests or correcting existing tests

        module.exports = {
            extends: ['@commitlint/config-conventional'],
            rules: {
            'body-leading-blank': [1, 'always'],
            'body-max-line-length': [2, 'always', 100],
            'footer-leading-blank': [1, 'always'],
            'footer-max-line-length': [2, 'always', 100],
            'header-max-length': [2, 'always', 100],
            'scope-case': [2, 'always', 'lower-case'],
            'subject-case': [
                2,
                'never',
                ['sentence-case', 'start-case', 'pascal-case', 'upper-case'],
            ],
            'subject-empty': [2, 'never'],
            'subject-full-stop': [2, 'never', '.'],
            'type-case': [2, 'always', 'lower-case'],
            'type-empty': [2, 'never'],
            'type-enum': [
                2,
                'always',
                [
                'build',
                'chore',
                'ci',
                'docs',
                'feat',
                'fix',
                'perf',
                'refactor',
                'revert',
                'style',
                'test',
                'translation',
                'security',
                'changeset',
                ],
            ],
            },
        };
    ```
    After that let's enable commitlint with husky by below command
    ``` 
        npx husky add .husky/commit-msg 'npx --no --commitlint --edit "$1"'
    ```
## VS Code Configuration
    - Create a directory `.vscode` in the root of the project
    - Inside .vscode folder create a file ie ` settings.json `, which we will be using to list out values that overrides the default settings of installed VS code of the contributor.
    - We can use this settings.json to set specific settings that only apply to this project, and share them with the rest of the our team by including .vscode in the code repository.

    Add the below lines of code inside ./vscode/settings.json file
    ```
        {
            "typescript.tsdk": "./node_modules/typescript/lib",
            "typescript.enablePromptUseWorkspaceTsdk": true,
            "editor.defaultFormatter": "esbenp.prettier-vscode",
            "editor.formatOnSave": true,
            "editor.codeActionsOnSave": {
                "source.fixAll": true,
                "source.organizeImports": true
            }
        }
    ``` 
    The above lines of code 
        - tells VS Code to use prettier extension as the default formatter( if someone want to use any other formatter, they are free to do so.)
        - formats & organizes the imports of the file on saving the file.
    
    
## Debugging
Now we will setup a convenient environment for debugging our application/project in case we run into any issues during the development phase.
So create `launch.json` file inside `.vscode/` folder
    - launch.json
        ```
            {
                "version": "0.1.0",
                "configurations": [
                    {
                    "name": "Next.js: debug server-side",
                    "type": "node-terminal",
                    "request": "launch",
                    "command": "npm run dev"
                    },
                    {
                    "name": "Next.js: debug client-side",
                    "type": "pwa-chrome",
                    "request": "launch",
                    "url": "http://localhost:3000"
                    },
                    {
                    "name": "Next.js: debug full stack",
                    "type": "node-terminal",
                    "request": "launch",
                    "command": "npm run dev",
                    "console": "integratedTerminal",
                    "serverReadyAction": {
                        "pattern": "started server on .+, url: (https?://.+)",
                        "uriFormat": "%s",
                        "action": "debugWithChrome"
                    }
                    }
                ]
            }
        ```
    Now in order to log server data in the browser while working in dev mode, we will install a package ie *cross-env*  by using the below command 
    ``` yarn add -D cross-env ```
    Then let's add respective script option inside package.json file
        ```
            "scripts": {
                "dev": "cross-env NODE_OPTIONS='--inspect' next dev",
                "build": "next build",
                "start": "next start",
                "lint": "next lint",
                "prettier": "prettier --write .",
                "prepare": "husky install"
            }, 
        ```
    Now we can debug our code easily   




[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
