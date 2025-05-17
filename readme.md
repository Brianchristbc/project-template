List of templated items:

1. .gitignore
2. package.json  
   run scripts using npm run script_name
   npm run build = npx webpack
   npm run dev = npx webpack serve
   npm run deploy = git subtree push --prefix dist origin gh-pages
3. webpack.common.js
4. webpack.dev.js
5. webpack.prod.js

Steps:

If starting with template

1.  copy following files into project
    .gitignore, package.json, webpack.common.js, webpack.dev.js webpack.prod.js
2.  install dependencies by running npm install in terminal, package-lock.json, and node_modules will automatically be created
3.  create source files including src/index.js src/template.html src/style.css src/favicon.ico as entry point for webpack
    template.html does not need any head links to script or style
    include import "./style.css"; in index.js
    include import { function_name } from "./page.js" in index.js
    in other js pages if importing path img, include import setImgName from "./img/img_name.png"
4.  run in development using npm run dev and open preview in http://localhost:8080
5.  run in production by using npm run build to create dist folder
6.  deploy project to github pages
    git branch gh-pages
    git status
    git checkout gh-pages && git merge main --no-edit
    npx webpack
    git add dist -f && git commit -m "Deployment commit"
    git subtree push --prefix dist origin gh-pages
    git checkout main
    ensure source branch on github pages is set to gh-pages branch

If starting without this template

1. download all dependencies manually
   download core: run npm install --save-dev webpack webpack-cli
   download dev server: npm install --save-dev webpack-dev-server
   download html plugin: npm install --save-dev html-webpack-plugin html-loader
   download css handler: npm install --save-dev style-loader css-loader
   download environment variables: npm install --save-dev dotenv-webpack
   run npm install
   download css minimizer: npm install css-minimizer-webpack-plugin --save-dev
   download date-fns npm install date-fns --save-dev
