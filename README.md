"# mongoMigrations"  

```javascript
const migrator = require('./migrator.js');

const migrationOptions = {
  setDbVersion: function setDbVersion(v, cb) {
    doSomeThing(v);
    cb(newVersion);
  },
  getDbVersion: function getDbVersion(cb) {
    let v = doSomeThing(v);
    cb(v);
  },
  migrations: [
    require('./scripts/v001.js'),
    require('./scripts/v002.js')
  ],
  done: cb
};

migrator(migrationOptions);
```


"./scripts/v001.js"

```javascript
module.exports = {
  version: 1,
  message: 'Add new data',
  script: function (next) {
    doSomeThing();
    next();
  }
};
```