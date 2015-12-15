# Bootstrapping An Application With Angular

## Objectives

1. Know the ropes of starting an Angular app

## Importing Angular Libraries

Since Angular is a single page application, everything starts off with
a single HTML page. The `index.html` file serves this purpose well since
it is the normally the first page that is loaded when a visitor views
our site.

```html
<!DOCTYPE html>
<html>
    <head></head>
    <body></body>
</html>
```

Our page is very bare and doesn't load Angular yet. We'll need to do this
by including Angular's libraries from Google. To do so, you'll need to add
the following code inside your `<body></body>` tags.

```html
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.15/angular.min.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.15/angular-route.min.js"></script>
```

## Initializing an Angular App

Now that you loaded Angular into your page, we need to 
initialize your own application. In Angular, we call these 
[modules](https://docs.angularjs.org/guide/module). 
It is essentially a container for your code to live in! After 
including Angular's libraries, we will want to create this
container to start writing code into.

```javascript
<script>
    window.MyApp = angular.module('MyApp', ['ngRoute'])
</script>
```

* We put the module into the `window` because this will allow us
  to access our container and its functions globally in any other
  Javascript function
* `MyApp` is just an example naming, you can change this to what
  you prefer
* `ngRoute` is Angular's routing feature which helps us interpret
  URLs and display content based on URL patterns

Our Angular app then needs to know where it can use the DOM
or our HTML page. In our case, we just want Angular to use
the entire page and we'll just attach it to the `<body>`

```html
<body ng-app="MyApp">
  <div ng-view></div>
</body>
```

* `ng-app` tells Angular which application to use
* `ng-view` is the space where Angular can write its
  view from templates
