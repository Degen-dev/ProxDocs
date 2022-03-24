# Basic Setup
Often times, a proxy site that is open source will include basic setup instructions for their site. These instructions normally include how to clone the repository, and how to run or "start" the backend web proxy, as well as serve the static files of the site.

## Cloning
Cloning a proxy is as simple as running `git clone`, and then the link to the repository. See an example below:
```sh
$ git clone https://github.com/Degen-dev/Degeneracy
```

Be sure to replace `Degen-dev/Degeneracy` with the repo to the proxy you are trying to clone, assuming you are not trying to clone Degeneracy.

## Installing Dependencies
Web proxies and proxy sites will have dependencies in order to get them up and running. In general, a proxy site will use a Node.js framework to serve static files and [NPM](https://www.npmjs.com) to install dependencies. To install dependencies, simply run the following command:
```sh
$ npm install
```

## Starting the Site
Sometimes the creator of a site will include a start script in npm that makes it as simple as possible to start the proxy. See the command below:
```sh
$ npm start
```

Assuming the site does not include a start script, you will have to find the index file manually. In general, the file name will be something along the lines of `main.js`, `index.js` or `start.js`. To run the file, simply run the following command:
```sh
$ node {filename}.js
```

Be sure to exclude the curly brackets and change `filename` to the actual name of the file you are trying to run.

## Authors
- [Degen-dev (Degenerate)](https://github.com/Degen-dev)