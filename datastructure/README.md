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
    git add .
```
- Now it's the best time to write our first commit 
```

```

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

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
