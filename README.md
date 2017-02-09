# A demo of using ES6/ Webpack/ React in a way that's friendly to doing it inside of another non-Webpack/ ES6/ React application

This was inspired by/ forked from Cory House's [Build a JS Dev Environment in 1 Hour](https://www.codemash.org/session/build-a-javascript-dev-environment-in-1-hour/), Matthew LaForest's, [Integrating React into a legacy web app](https://www.codemash.org/session/integrating-react-into-a-legacy-web-app/), and my own interest in using React in various places.

##The big idea

- You've got an app that's not using React or Webpack and you want to start using it in just one part of the app without disturbing other stuff.
- Everything in the enclave is coded in ES6/ JSX.
- Everything in the enclave is bundled (JS and CSS).
- There's not a ton of other strange new stuff going on other than React and ES6.
- At the end of the day, the bundled stuff is copied to a folder where it can be dealt with easily by another build process.
- JSX is automatically getting transpiled in the background as you change it so you can just refresh your browser to test new code.
- BUT, it's not hot-reloading as you change stuff, in case your app already being served by another web server. The hot-reloading stuff uses its own web server, generally. I've read that using another web server is possible, but let's keep things easy for now. If the enclave is just one part of my app, serving it on its own for the sake of hot reloading may not even make much sense.

##What I changed from the original demo
- No more hot reloading
- Added CSS bundling
- Added copying index.html to the build folder
- Added React/ JSX
- Added onto the import/ export example so I could prove I was doing it right since I'm new to ES6

##How to use 

After cloning, run
```
npm install
npm install webpack -g
```

Then, to build to the build folder, run:
```
webpack
```

To build and keep building to the build folder, run `webpack --watch`. Obviously, make sure you're serving the build folder somehow.

To run unit tests, run `npm run test`.

##TODO

- There's a ton of dependencies that aren't needed but are still there
- It should minify the CSS.
- I think I took out the linting.
- I'd like to write up how to run all the commands at once, so you can run one command and get JIT transpiling, linting, unit tests running and live updating, etc. all at once.

##Interesting bits
- Most tutorials assume you want to hot reload so it wasn't obvious initially how to just keep the build folder up-to-date so something else could serve it. It'd be nice to do this with something other than the webpack --watch command, so then you wouldn't need that separate global install.

## More Info and Inspiration
- [Codemash Talk Slides](https://www.dropbox.com/s/utvgg07ib25dq4x/Build%20a%20JS%20Dev%20Env%20in%201%20Hr%20-%20Codemash.pptx?dl=0)
- [Building a JavaScript Development Environment on Pluralsight](https://app.pluralsight.com/library/courses/javascript-development-environment/table-of-contents) 
- [React Slingshot](https://github.com/coryhouse/react-slingshot) - My starter Kit
- [Andrew Farmer's list of React Starter Kits](http://andrewhfarmer.com/starter-project/)
