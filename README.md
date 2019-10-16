# npm-run-programmatically-example

![npm run programmatically](assets/demo.gif)
*You can watch the video on [asciinema](https://asciinema.org/a/274563) too*.

Demo project to show how to launch `npm run` programmatically (through `npm.run()`, not `child_process.exec())` etc.).

All you have to do in your proejct is:
- install npm as a local dependency `$ npm i -D npm`
- require it from your JavaScript file `const npm = require("npm");`
- load the NPM project and, then, launching `npm.run("SCRIPT_NAME")`

Please note that every package.json *preSCRIPT_NAME* and *postSCRIPT_NAME* are respected and launched too.

Take a look at the [*index.js* file](index.js). If you launch it (through `node index.js` or `npm run run-example`) the output will be
```yaml
> npm-run-programmatically-example@ pretest /Users/noriste/Sites/test/npm-run-programmatically-example
> echo "Pre test"

Pre test

> npm-run-programmatically-example@ test /Users/noriste/Sites/test/npm-run-programmatically-example
> echo "Error: no test specified"

Error: no test specified

> npm-run-programmatically-example@ posttest /Users/noriste/Sites/test/npm-run-programmatically-example
> echo "Post test"

Post test
```

I leveraged this feature while developing [nprr](https://github.com/NoriSte/nprr), an "npm run + autocomplete" package.
