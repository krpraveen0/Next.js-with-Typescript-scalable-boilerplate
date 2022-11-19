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
| we will be using ```yarn``` as a package manager, but you are open to use ```npm``` as well
```
    yarn install
    yarn dev
```
After running above command we will be having our application live on http://localhost:3000.

- Now to check our repo for production let's build our application
``` yarn build
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
In order to enforce common coding standard & rules for all the conftributor in order to maintain the best practices, style[formatting] & coding standard consistency. In order to achieve this we will be using two tools:
    1. eslint : For maintaining the best practices coding standards
    2. prettier. For automatic code formatting of the code.

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

