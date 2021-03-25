## Description

Atlaskit ESM is a module responsible to build ESM modules from existing libraries like 
Atlaskit or React using Snowpack. 


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

## Copyrights

Dynamic Solutions WebSight (Atlaskit ESM) - Atlaskit ESM
Copyright (C) 2013-2021 Dynamic Solutions

This module is part of WebSight Admin, which is released under license
GNU AFFERO GENERAL PUBLIC LICENSE Version 3.

WebSight Admin is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.

WebSight Admin is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with WebSight Admin.  If not, see <http://www.gnu.org/licenses/>.