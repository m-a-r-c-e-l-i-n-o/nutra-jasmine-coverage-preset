# nutra-jasmine-coverage-preset
The "nutra-jasmine-coverage-preset" module makes available the [jasmine](http://jasmine.github.io/) behavior-driven testing framework, the [Istanbul](https://github.com/gotwarlost/istanbul) code coverage tool and the [commonjs](https://nodejs.org/docs/latest/api/modules.html) module loader to the [N.U.T.R.A.](https://github.com/m-a-r-c-e-l-i-n-o/nutra) unit test runner.

## Install Preset:
```bash
npm install nutra nutra-jasmine-coverage-preset
```

## Add Preset Configuration:
Create a "nutra.config.js" config file in the root of your project and populate it with the following:
```js
// nutra.config.js
module.exports = function( config ) {
  config.set({
    frameworks: ['nutra-jasmine'],
    files: ['test/specs/**/*.js', 'src/**/*.js'], // Modify to include your own app & spec files
    preprocessors: {
      'src/**/*.js': ['nutra-coverage'] // Modify to include only your app files. (No specs!)
    },
    reporters: ['nutra-coverage'],
    coverageOptions: {
      reporters: [
        { type: 'html', subdir: '.' }
      ]
      // For more coverage options, see:
      // https://github.com/m-a-r-c-e-l-i-n-o/nutra-coverage
    }
  })
  // For more configuration options, see:
  // https://github.com/m-a-r-c-e-l-i-n-o/nutra#configuration-anatomy
}
```
