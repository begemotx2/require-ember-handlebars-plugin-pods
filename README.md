# Require.js Ember Handlebars Plugin.
Modification for migration to pods stucture.

Automatic requires of template calls to helpers, views, controllers and
partials.

## Usage
Write an Ember Handlebars template like so:

`pods/email/template.hbs`
```handlebars
<section>Welcome to my awesome app!</section>

```

Then require the template with your route:

```js
require(["podhbs!pods/email"], function() {
  // pods/email/template.hbs now exists in Ember.TEMPLATES.email  
});
```

## Config
You can configure the paths for the plugin to look up resources, like so:
```js
require.config({
  podshbs: {
    paths: {
      templates: "foo/bar/templates",
      views: "foo/bar/views",
      controllers: "foo/bar/controllers",
      helpers: "foo/bar/helpers"
    }
  }
})
```

You can also configure the type of casing used on your files, like so:
```js
require.config({
  podshbs: {
    casing: "camel"
  }
})
```

Valid options are:

* `camel` - `require("ehbs!coolTemplate")` will load `templates/coolTemplate.hbs`
* `class` - `require("ehbs!coolTemplate")` will load `templates/CoolTemplate.hbs`
* `underscore` or `snake` - `require("ehbs!coolTemplate")` will load `templates/cool_template.hbs`

## Tests
Open up `tests/index.html` in your browser.

## Todo
* Builds
* i18n
* More robust and deeper testing
* Pull out ES5 functions for IE6-8 support.


## License
MIT
