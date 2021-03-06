---
title: 'Compiling translations'
template: main.jade
---

# Compiling translations

Converting translated `.po` files into angular-compatible JavaScript files can be done automatically using the [`grunt-angular-gettext`](https://github.com/rubenv/grunt-angular-gettext) module. You will already have this module added to your project if you followed the instructions on the [extracting strings](/dev-guide/extract/) page. If this is not the case, please refer to that page first.

The `nggettext_compile` task converts a set of translated `.po` files into a JavaScript file that can be included in your project.

In your project's Gruntfile, add a section named `nggettext_compile` to the data object passed into `grunt.initConfig()`.

```javascript
grunt.initConfig({
  nggettext_compile: {
    all: {
      files: {
        'src/js/translations.js': ['po/*.po']
      }
    },
  },
})
```

Be sure to add this file (in this case `src/js/translations.js`) to your project.

Optionally, you can specify a `module` parameter, which defines the Angular.JS module for which the translations JavaScript is generated:

```javascript
grunt.initConfig({
  nggettext_compile: {
    all: {
      options: {
        module: 'myApp'
      },
      files: {
        'src/js/translations.js': ['po/*.po']
      }
    },
  },
})
```

<a href="/dev-guide/configure/" class="btn btn-primary">Next: Configuring angular-gettext</a>
