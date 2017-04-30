Install babel babel-cli for dev env to execute/compile es6 to es5 which the browser understands.
running babel src/index.jsx w/o babelrc i.e w/o specifying presets for babel compiler it will gives error. After including presets in .babelrc run babel src/index.jsx it will compile the code in .jsx to actual React code.

Browser doesn't understand es6 
We shouldn't load many modeules/libraries in browser one by one, generally it takes more time to start the app hence it's better to convert all the es6 code to es5 and have everything compiled into one .js file for browser to easily/quickly start showing page data.

Even though the app is simple it actually made up of hundreds of underlying files which make up React and ReactDOM libraries.
- It will be really inefficient to load these libraries one by one. So instead we want to put all our code including the libraries into a single .js file which can be understood and executed by the browser.
- To do this we need a module bundler. The most popular choice of module bundler is `webpack`.
- Webpack is capable of taking all our application code and bundle it into a single .js file but it isn't able to convert it from es6 and jsx syntax to es5.
- To do this we use another tool known as transpiler which in this case `babel` which is again very popular in React community
- Babel exits independently of webpack and is designed to convert/transpile es6 javascript into es5 to enable browsers to use new es6 features before it is implemented in the browsers themselves.
- npm install --global babel babel-cli
- babel --help
- babel src/index.jsx => error
  This gives error because babel doesn't underatand any additional syntax out of the box so we need to babel our code is in es6 javascriptand uses React(.jsx) syntax 
- This is required to build and run on our project but not to run on browser so we can save these as development only dependencies in package.json 
- npm install --save-dev babel-preset-es2015 babel-preset-react
- We actually need to tell babel to use the presets we installed which is done by creating a file called .babelrc in project root which is a json file specifying the presets we will use
- Now run the babel command again =>
  babel src/index.jsx 
  And it will output the transpiled code into the terminal.

- Now we need to bundle all the code into one .js file 

Setting up Webpack




