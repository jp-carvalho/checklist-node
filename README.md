# Create Node.js Project with Test configuration using Mocha

### Creating Folder
- [ ] ```mkdir FOLDER_NAME FOLDER_NAME/src && cd FOLDER_NAME```

- [ ] ```npm init -y```

### Installing Dependencies
- Express
- [ ] ```npm i express@4.17.1 -E```
- Nodemon
- [ ] ```npm i nodemon@2.0.15 -D -E```
- Mocha
- [ ] ```npm install mocha@8.4.0 chai@4.3.4 -D -E```
- ChaiHttp
- [ ] ```npm install chai-http@4.3.0 -D -E```
- Sinon
- [ ] ```npm install sinon@11.1.1 -D -E```
      
```
OBS:
-D is the same as --save-dev
-E is the same as --save-exact
```

### Installing and configure linter e git (trybe course use)
- [ ] ```npm i eslint@6.8.0 eslint-config-trybe-backend@1.0.1 -D -E```

- [ ] ```touch .eslintignore .eslintrc.json```

- [ ] ADD ON: .eslintignor
 ```
node_modules
```

- [ ] ADD ON: .eslintrc.json
```
  {
    "env": {
      "es2020": true
    },
    "extends": "trybe-backend",
    "rules": {
      "sonarjs/no-duplicate-string": ["error", 5]
    }
  }
```

- [ ] ```git init && touch .gitignore```

- [ ] ADD ON: .gitignore
  ```
  node_modules
  ```

### CREATING SERVER
- [ ] ADD ON: src/app.js
  ```
  const express = require('express');

  const app = express();
  app.use(express.json());

  module.exports = app;
  ```

- [ ] ADD ON: src/server.js
  ```
  const app = require('./app');

  app.listen(3001, () => console.log('server running on port 3001'));
  ```

- [ ] ADD ON: package.json
  ```
  "scripts": {
  "start": "node src/server.js",
  "dev": "nodemon src/server.js",
  "lint": "eslint --no-inline-config --no-error-on-unmatched-pattern -c .eslintrc.json .",
  "test": "mocha tests/**/*.test.js --exit"
  }
  ```

#### SERVER TEST
- [ ] ```npm run dev```


# Test configuration using Mocha
- [ ] ADD ON: tests/TEST_FILE.test.js
```
const chai = require('chai');
const chaiHttp = require('chai-http');
const sinon = require('sinon');
const fs = require('fs');
const app = require('./FOLDER_NAME/app.js');

chai.use(chaiHttp);
const { expect } = chai;



// const MOCK_NAME = JSON.stringify({ 
  example: [
    {
      id: 1,
      ... //

describe('Testing 1, 2, 3', function () {
  beforeEach(function () {
    sinon.stub(fs.promises, 'readFile')
      .resolves(mockFile);
  });

  afterEach(function () {
    sinon.restore();
  });


```