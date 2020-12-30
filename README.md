### Extending WebSight Foundation Modules with new module:
- add new dependency with version in `package.json` file `dependencies` section
- add dependency name in `snowpack.config.js` file `webDependencies` section
- deploy to local WebSight at port 8080 `mvn clean install -P autoInstallBundle`
- the module exported as ES6 module is available at 
`http://localhost:8080/apps/websight-atlaskit-esm/web-resources/<dependency name>.js`
for example `react` dependency: `http://localhost:8080/apps/websight-atlaskit-esm/web-resources/react.js`

#### Example:
##### package.json
```
...
"dependencies": {
    "react": "npm:@pika/react@16.13.1",
    "react-dom": "npm:@pika/react-dom@16.13.1"
  },
...
```

##### snowpack.config.js
```
...
module.exports = {
  webDependencies: [
    "react",
    "react-dom"
  ],
...
```

### Usage:

Build
```
mvn clean install
```

Build with local deployment
```
mvn clean install -P autoInstallBundle
```
