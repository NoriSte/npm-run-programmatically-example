# npm-run-programmatically-example

![npm run programmatically](assets/demo.gif)
_You can watch the video on [asciinema](https://asciinema.org/a/274563) too_.

Demo project to show how to launch `npm run` programmatically (through `npm.run()`, not `child_process.exec())` etc.).

All you have to do in your proejct is:

- install npm as a local dependency `$ npm i -D npm`
- require it from your JavaScript file `const npm = require("npm");`
- load the NPM project and, then, launching `npm.run("SCRIPT_NAME")`

Please note that every package.json _preSCRIPT_NAME_ and _postSCRIPT_NAME_ are respected and launched too.

Take a look at the [_index.js_ file](index.js). If you launch it (through `node index.js` or `npm run run-example`) the output will be

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

Read a dedicated article on [Medium](https://medium.com/@NoriSte/launching-npm-run-programmatically-with-npm-run-f2a1b8a569a6) or on [dev.to](https://dev.to/noriste/launching-npm-run-programmatically-with-npm-run-3mmc).
