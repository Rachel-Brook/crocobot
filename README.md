# crocobot :crocodile::robot:

**snappy automated testing**

Initial Puppeteer setup forked from [@xfumihiro](https://github.com/xfumihiro/jest-puppeteer-example)
This is an example of using the global setup/teardown apis with the async test-environment apis to integrate jest and puppeteer.

## This framework uses Cucumber
Using [Jest Cucumber](https://github.com/bencompton/jest-cucumber), tests are first written as .feature files using Gherkin plain language in a format that's very similar to a user story. The 'behind the scenes' coding for this to work is put in a step definition JS file.

## Writing tests
Tests are stored in `website/__tests__`
Browser events are coded via the [Puppeteer API](https://github.com/GoogleChrome/puppeteer/blob/master/docs/api.md)
Asserts are via `expect` giving access to [Jest matchers](http://facebook.github.io/jest/docs/en/using-matchers.html#content)

### Features and step definitions
First write the `.feature` file for the test.
Test steps are then defined in the corresponding `.steps.js` file.

#### Steps shell
A new `.steps.js` file should contain this:
```
import { defineFeature, loadFeature } from 'jest-cucumber';
const feature = loadFeature('./__tests__/features/foo.feature');

defineFeature(feature, test => {
});
```
When the test is first run it will fail, but will then provide the bones of a test based on the corresponding `.feature` file.

