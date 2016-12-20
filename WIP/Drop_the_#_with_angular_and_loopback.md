# Pretty Url in AngularJS and Loopback. Drop the '#'

[AngularJS](https://angularjs.org/) routing system is great to create RESTfull single page applications, but it comes at the cost of accepting this annoying # in all your urls.

However, this tiny character can be easily dropped to get old school, pretty urls.

There are two things that need to be done:

1. Configuring AngularJS to enable HTML5 mode
2. Configuring your backend framework to redirect all non REST and non static asset http request to the frontend index.html

Here I will be using [Loopback](https://loopback.io/) as an example of REST api framework, but it can be easily adapted to other frameworks like Spring or Symfony.

## Configuring AngularJS to enable HTML5 mode

This step will depend on which version of Angular you're using.

### Angular 1 with angular-route or angular-ui-router

When you set your angular application configuration, you simply have to use the `$locationProvider` module and set `html5Mode` to true.

```javascript
  angular.module('app')
    .config(config)

  config.$inject = ['$locationProvider'];
  function config($locationProvider) {
    $locationProvider.html5Mode(true);
  }
```

To tell Angular what is the base path of your application, provide a base tag to your index.html

```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">

    <base href="/">
</head>
```

### Angular 2

The equivalent of HTML5 mode in Angular 2 is to use the `PathLocationStrategy` as the router strategy.

```javascript
import {ROUTER_PROVIDERS, APP_BASE_HREF} from 'angular2/router';

bootstrap(yourApp, [
  ROUTER_PROVIDERS, // includes binding to PathLocationStrategy
  provide(APP_BASE_HREF, {useValue: '/'})
]);
```

You can edit the `APP_BASE_HREF` to define your application base path

```javascript
provide(APP_BASE_HREF, {useValue: '/my/app/path'})
```

## Configuring your backend

The above configuration will work on its own if you always start your navigation from your angular home page and if you do not ask your browser to refresh. When you will try to directly access an angular route, your web server won't know he has to redirect this url to your angular application.

You have to configure your backend framework to redirect all your angular route urls to your index.html.

This can be simply made by adding a filter to the server.js file.

```javascript
var path = require('path');

app.all('/*', function(req, res, next) {
  //Redirecting to index only the requests that do not point to the scripts, stylesheets, templates or the loopback rest api
  if(!req.url.startsWith('/vendor') && !req.url.startsWith('/css') && !req.url.startsWith('/js') && !req.url.startsWith('/views') && !req.url.startsWith('/api'))
    res.sendFile('index.html', { root: path.resolve(__dirname, '..', 'client') });
  else
    next();
});
```

Now, all your requests that do not match the specified patterns (/vendor, /css, /js, /views, /api) are considered as request that should be taken care of by the angular routing system and not the loopback one.

You have now to be extra careful when adding new assets or rest endpoints, and be sure that their urls do not conflict with angular routes.

For example, you cannot hope to create an angular state at /home and put a static asset at /home/style.css. If you add /home to your filter, you wont be able to access your angular route, and is you do not add it, your /home/style.css will serve the index.html instead of your stylesheet.

## Conclusion

Congratulations ! You have now a fully functional angular application without any trace of hashtags in url ! Keep in mind that this trick can be reproduce with any backend framework that supports request filtering and you could easily adapt this example to any language.
