# Bootstrapping An Application With Angular

## Objectives

1. Know the ropes of starting an Angular app

## Importing Angular Libraries

In our `index.html` file, we need to include the appropriate scripts
that will import Angular onto our page.

```
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.15/angular.min.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.15/angular-route.min.js"></script>
```

## Starting an Angular App

Now that Angular's libraries are included into the page, we need
to initialize Angular for our own application.

```
window.MyApp = angular.module('MyApp', ['ngRoute'])
```

* You can change "MyApp" to anything you like
* ngRoute is Angular's routing feature which helps us interpret
  URLs and display content based on URL patterns. We'll get into
  how to use this in later lessons.

Our Angular app then needs to know where it can use the DOM
or our HTML page. In our case, we just want Angular to use
the entire page and we'll just attach it to the `<body>`

```
<body ng-app="MyApp">
  <div ng-view></div>
</body>
```

* `ng-app` tells Angular which application to use
* `ng-view` is the space where Angular can write its
  view from templates
