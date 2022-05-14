# gh-pages Hello World example

This example shows the most basic idea behind Next. We have 2 pages: `pages/index.js` and `pages/about.js`. The former responds to `/` requests and the latter to `/about`. Using `next/link` you can add hyperlinks between them with universal routing capabilities.

## How to use

Execute [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) with [npm](https://docs.npmjs.com/cli/init) or [Yarn](https://yarnpkg.com/lang/en/docs/cli/create/) to bootstrap the example:

```bash
npx create-next-app --example gh-pages gh-pages-app
# or
yarn create next-app --example gh-pages gh-pages-app
# or
pnpm create next-app -- --example gh-pages gh-pages-app
```

### Deploy it to github

Edit `env-config.js` and replace `'Next-gh-page-example'` by your project name.

Edit `next.config.js` and replace `'Next-gh-page-example'` by your project name.

1.  Create repository.
2.  Link it to your github account.
3.  Publish your default branch, e.g. `main`.

```bash
npm run deploy
```

Test it:

Replace `<github-user-name>` and `<github-project-name>`

```bash
https://<github-user-name>.github.io/<github-project-name>/
```

Example:

```bash
https://github.com/thierryc/Next-gh-page-example/

https://thierryc.github.io/Next-gh-page-example/
```









# nextjs sample project 개발 세팅 시작

    1. 프로젝트 생성 : npx create-next-app --example gh-pages gh-pages-app typescript


        C:\job\front-end\nextjs>npx create-next-app --example gh-pages gh-pages-app typescript
        Creating a new Next.js app in C:\job\front-end\nextjs\gh-pages-app.

        Downloading files for example gh-pages. This might take a moment.

        Installing packages. This might take a couple of minutes.

        yarn install v1.22.18
        info No lockfile found.
        [1/4] Resolving packages...
        [2/4] Fetching packages...
        [3/4] Linking dependencies...
        [4/4] Building fresh packages...

        success Saved lockfile.
        Done in 32.62s.

        Initialized a git repository.

        Success! Created gh-pages-app at C:\job\front-end\nextjs\gh-pages-app
        Inside that directory, you can run several commands:

        yarn dev
            Starts the development server.

        yarn build
            Builds the app for production.

        yarn start
            Runs the built app in production mode.

        We suggest that you begin by typing:

        cd gh-pages-app
        yarn dev

    2. 프로젝트 이동 및 vscode 실행

        C:\job\front-end\nextjs>  cd gh-pages-app

        C:\job\front-end\nextjs\gh-pages-app>code .


    3. package.json 내용
        C:\job\front-end\nextjs\gh-pages-app\package.json

        {
            "private": true,
            "scripts": {
                "dev": "next",
                "build": "next build",
                "start": "next start",
                "export": "next export",
                "deploy": "rm -rf node_modules/.cache && next build && next export && touch out/.nojekyll && git add out/ && git commit -m \"Deploy Next.js to gh-pages\" && git subtree push --prefix out origin gh-pages"
            },
            "dependencies": {
                "next": "latest",
                "react": "^17.0.2",
                "react-dom": "^17.0.2"
            },
            "devDependencies": {
                "babel-plugin-transform-define": "^1.3.0"
            }
        }


    
    4. 로컬에서 실행 : yarn dev
        C:\job\front-end\nextjs\gh-pages-app>yarn dev
        yarn run v1.22.18
        $ next
        ready - started server on 0.0.0.0:3000, url: http://localhost:3000
        info  - Disabled SWC as replacement for Babel because of custom Babel configuration ".babelrc.js" https://nextjs.org/docs/messages/swc-disabled
        info  - Using external babel configuration from C:\job\front-end\nextjs\gh-pages-app\.babelrc.js
        wait  - compiling...
        event - compiled client and server successfully in 3.8s (140 modules)


    5. 크롬 확인
        http://localhost:3000/

    6. 프로젝트 빌드 : yarn build

        C:\job\front-end\nextjs\gh-pages-app>yarn build
        yarn run v1.22.18
        $ next build
        info  - Checking validity of types
        warn  - No ESLint configuration detected. Run next lint to begin setup
        info  - Disabled SWC as replacement for Babel because of custom Babel configuration ".babelrc.js" https://nextjs.org/docs/messages/swc-disabled
        info  - Using external babel configuration from C:\job\front-end\nextjs\gh-pages-app\.babelrc.js
        info  - Creating an optimized production build  
        info  - Compiled successfully
        info  - Collecting page data  
        info  - Generating static pages (4/4)
        info  - Finalizing page optimization

        Page                                       Size     First Load JS
        ┌ ○ /                                      2.2 kB         72.7 kB
        ├ ○ /404                                   2.99 kB        73.5 kB
        └ ○ /about                                 2.21 kB        72.7 kB
        + First Load JS shared by all              70.5 kB
        ├ chunks/framework-e70c6273bfe3f237.js   42 kB
        ├ chunks/main-1a59f16f14cc63cc.js        26 kB
        ├ chunks/pages/_app-036f199acba0ea9f.js  977 B
        └ chunks/webpack-38a82e476e2590a4.js     1.43 kB

        ○  (Static)  automatically rendered as static HTML (uses no initial props)

        Done in 12.77s.

        C:\job\front-end\nextjs\gh-pages-app>



    7. 리포지토리 생성 하기
        echo "# gh-pages-app" >> README.md
        git init
        git add README.md
        git commit -m "first commit"
        git branch -M main
        git remote add origin https://github.com/king-garlic/gh-pages-app.git
        git push -u origin main    


    8. 리포지토리 생성 터미널 로그



        C:\job\front-end\nextjs\gh-pages-app>echo "# gh-pages-app" >> README.md

        C:\job\front-end\nextjs\gh-pages-app>git init
        Reinitialized existing Git repository in C:/job/front-end/nextjs/gh-pages-app/.git/

        C:\job\front-end\nextjs\gh-pages-app>git add README.md
        warning: LF will be replaced by CRLF in README.md.
        The file will have its original line endings in your working directory

        C:\job\front-end\nextjs\gh-pages-app>git commit -m "first commit"
        [main e6baef6] first commit
        1 file changed, 4 insertions(+), 2 deletions(-)

        C:\job\front-end\nextjs\gh-pages-app>git branch -M main

        C:\job\front-end\nextjs\gh-pages-app>git remote add origin https://github.com/king-garlic/gh-pages-app.git

        C:\job\front-end\nextjs\gh-pages-app>git push -u origin main
        Enumerating objects: 20, done.
        Counting objects: 100% (20/20), done.
        Delta compression using up to 8 threads
        Compressing objects: 100% (20/20), done.
        Writing objects: 100% (20/20), 8.58 KiB | 2.86 MiB/s, done.
        Total 20 (delta 4), reused 0 (delta 0), pack-reused 0
        remote: Resolving deltas: 100% (4/4), done.
        To https://github.com/king-garlic/gh-pages-app.git
        * [new branch]      main -> main
        Branch 'main' set up to track remote branch 'main' from 'origin'.

        C:\job\front-end\nextjs\gh-pages-app>



    9. 리포지토리 : 새로고침
        https://github.com/king-garlic/gh-pages-app    


    10. 소스 수정 : env-config.js
        C:\job\front-end\nextjs\gh-pages-app\env-config.js
            "process.env.BACKEND_URL": prod ? "/gh-pages-app" : "",
    
    11. 소스 수정 : env-config.js
        C:\job\front-end\nextjs\gh-pages-app\next.config.js
            assetPrefix: !debug ? "/gh-pages-app/" : "",


    12. cmd 에서 bash 로 변경 하고 배포 명령 실행 : npm run deploy


    13. 배포 명령 실행 TERMINAL 로그

        213100@DESKTOP-EE56G2V MINGW64 /c/job/front-end/nextjs/gh-pages-app (main)
        $ npm run deploy

        > deploy
        > rm -rf node_modules/.cache && next build && next export && touch out/.nojekyll && git add out/ && git commit -m "Deploy Next.js to gh-pages" && git subtree push --prefix out origin g

        info  - Checking validity of types
        warn  - No ESLint configuration detected. Run next lint to begin setup
        info  - Disabled SWC as replacement for Babel because of custom Babel configuration ".babelrc.js" https://nextjs.org/docs/messages/swc-disabled
        info  - Creating an optimized production build
        info  - Compiled successfully
        info  - Collecting page data
        info  - Generating static pages (4/4)
        info  - Finalizing page optimization

        Page                                       Size     First Load JS
        ┌ ○ /                                      2.2 kB         72.7 kB
        ├ ○ /404                                   2.99 kB        73.5 kB
        └ ○ /about                                 2.21 kB        72.7 kB
        + First Load JS shared by all              70.5 kB
        ├ chunks/framework-e70c6273bfe3f237.js   42 kB
        ├ chunks/main-1a59f16f14cc63cc.js        26 kB
        ├ chunks/pages/_app-036f199acba0ea9f.js  977 B
        └ chunks/webpack-38a82e476e2590a4.js     1.43 kB

        ○  (Static)  automatically rendered as static HTML (uses no initial props)

        info  - using build directory: C:\job\front-end\nextjs\gh-pages-app\.next
        info  - Copying "static build" directory
        info  - No "exportPathMap" found in "C:\job\front-end\nextjs\gh-pages-app\next.config.js". Generating map from "./pages"
        info  - Launching 7 workers
        info  - Exporting (3/3)
        Export successful. Files written to C:\job\front-end\nextjs\gh-pages-app\out
        warning: LF will be replaced by CRLF in out/404.html.
        The file will have its original line endings in your working directory
        warning: LF will be replaced by CRLF in out/_next/static/chunks/polyfills-5cd94c89d3acac5f.js.
        The file will have its original line endings in your working directory
        [main 19ead76] Deploy Next.js to gh-pages
        16 files changed, 25 insertions(+)
        create mode 100644 out/.nojekyll
        create mode 100644 out/404.html
        create mode 100644 out/_next/static/CT3KEC2OafX7SSMNKOJn2/_buildManifest.js
        create mode 100644 out/_next/static/CT3KEC2OafX7SSMNKOJn2/_middlewareManifest.js
        create mode 100644 out/_next/static/CT3KEC2OafX7SSMNKOJn2/_ssgManifest.js
        create mode 100644 out/_next/static/chunks/894.884bc9854a9cfe85.js
        create mode 100644 out/_next/static/chunks/framework-e70c6273bfe3f237.js
        create mode 100644 out/_next/static/chunks/main-1a59f16f14cc63cc.js
        create mode 100644 out/_next/static/chunks/pages/_app-036f199acba0ea9f.js
        create mode 100644 out/_next/static/chunks/pages/_error-98e801c646abf33c.js
        create mode 100644 out/_next/static/chunks/pages/about-3ada7c2c9e76ff10.js
        create mode 100644 out/_next/static/chunks/pages/index-06b9b971e804acd5.js
        create mode 100644 out/_next/static/chunks/polyfills-5cd94c89d3acac5f.js
        create mode 100644 out/_next/static/chunks/webpack-38a82e476e2590a4.js
        create mode 100644 out/about.html
        create mode 100644 out/index.html
        git push using:  origin gh-pages
        Enumerating objects: 23, done.
        Counting objects: 100% (23/23), done.
        Delta compression using up to 8 threads
        Compressing objects: 100% (21/21), done.
        Writing objects: 100% (23/23), 108.26 KiB | 5.70 MiB/s, done.
        Total 23 (delta 3), reused 0 (delta 0), pack-reused 0
        remote: Resolving deltas: 100% (3/3), done.
        remote:
        remote: Create a pull request for 'gh-pages' on GitHub by visiting:
        remote:      https://github.com/king-garlic/gh-pages-app/pull/new/gh-pages
        remote:
        To https://github.com/king-garlic/gh-pages-app.git
        * [new branch]      187f40f096c47984968af41b24d0e06da974a6df -> gh-pages

        213100@DESKTOP-EE56G2V MINGW64 /c/job/front-end/nextjs/gh-pages-app (main)
        $


    14. SET Your GitHub Pages site is currently being built from the gh-pages branch.
        https://github.com/king-garlic/gh-pages-app/settings/pages

        SET 설명 페이지 
        https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

    15. 배포된 프로젝트 홈페이지 확인 
        https://king-garlic.github.io/gh-pages-app

        
    16. 
    17. 
    18. 
    19. 
    20. 
    "# gh-pages-app" 
