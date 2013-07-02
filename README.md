# Require.js Ember Handlebars Plugin
Automatic requires of template calls to helpers, views, controllers and
partials.

## Usage
Write an Ember Handlebars template like so:

`templates/index.hbs`
```html
<section>Welcome to my awesome app!</section>
<div>{{partial login}}</div>
```

`templates/login.hbs`
```html
<form>
  {{view Ember.TextField valueBinding="username"}}
  {{view Ember.TextField valueBinding="password" type="password"}}
  <button {{action submitForm on="submit"}}>Submit</button>
</form>
```

Then require the template with your route:

```js
require(["ehbs!index"], function() {
  // templates/index.hbs now exists in Ember.TEMPLATES.index
  // and
  // templates/login.hbs now exists in Ember.TEMPLATES.login
});
```

## Config
You can configure the paths for the plugin to look up resources, like so:
```js
require.config({
  ehbs: {
    paths: {
      templates: "foo/bar/templates",
      views: "foo/bar/views",
      controllers: "foo/bar/controllers",
      helpers: "foo/bar/helpers"
    }
  }
})
```

## Tests
Open up `tests/index.html` in your browser.

## Todo
* Builds
* i18n
* More robust and deeper testing
* Pull out ES5 functions for IE6-8 support.


## License
MIT
