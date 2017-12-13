```bash
cd ./node_modules/library
npm install
npm run build

cd ../../app
npm install
npm run build
```

`./app/dist/app.js` now contains multiple jquery modules.
That is probably the same behavior as `node ./app/src/index.js` because there are two jquery modules (`./app/node_modules/jquery` and `./node_modules/library/node_modules/jquery`).

But since `./node_modules/library/webpack.config.js` has `externals: ["jquery"]` I do not except `./node_modules/library/node_modules/jquery` to be resolved by webpack.