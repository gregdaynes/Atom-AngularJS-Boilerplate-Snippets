# Atom AngularJS Boilerplate Snippets

Adds AngularJS boilerplate snippets from best practices in Atom.

Based on John Papa's guides, and Jason Miazga's Atom snippets.

## Key Features

- AngularJS template snippets from best practices
- Utilizes SOLID principles for Rule of 1, and readability.
- HTML index boilerplate snippet
- JS boilerplate snippets for app module, controller, constant, directive, directive with controller, factory, custom module, service

## Install

**Console**
```
apm install angularjs-boilerplate-snippets
```
**Atom Editor**  
Go to Atom > Preferences... then search for "AngularJS Boilerplate Snippets" in the Packages tab.

## Snippets

Type a prefix and press `tab`, and the snippet will replace it.

#### HTML

- `angindex` - Index Boilerplate

### Javascript

- `angapp` - Primary App Module
- `angcon` - Controller
- `angconst` - Constant
- `angdir` - Directive
- `angdir` - Directive w/ Controller
- `angfact` - Factory
- `angmod` - Custom Module
- `angser` - Service


## Examples

### angindex
```html
<!DOCTYPE html>
<!--[if lt IE 7]>      <html lang="en" ng-app="app" class="no-js lt-ie9 lt-ie8 lt-ie7"> <![endif]-->
<!--[if IE 7]>         <html lang="en" ng-app="app" class="no-js lt-ie9 lt-ie8"> <![endif]-->
<!--[if IE 8]>         <html lang="en" ng-app="app" class="no-js lt-ie9"> <![endif]-->
<!--[if gt IE 8]><!--> <html lang="en" ng-app="app" class="no-js"> <!--<![endif]-->
<head>
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge">

  <title>${1:Title}</title>
  <meta name="description" content="${2: Description}" />
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <script src="//ajax.googleapis.com/ajax/libs/angularjs/${1:1.3.14}/angular.js"></script>

</head>
<body>
  <!--[if lt IE 7]>
      <p class="browsehappy">You are using an <strong>outdated</strong> browser. Please <a href="http://browsehappy.com/">upgrade your browser</a> to improve your experience.</p>
  <![endif]-->
  <div class="container" ng-view=""></div>
</body>
</html>
```

### angapp
```js
(function() {
  'use strict';

  angular.module('${1:app}', [
    // Angular modules
    $1
    // Reusable cross app code modules
    $2
    // 3rd Party modules
    $3
  ]);

})();
```

### angcon
```js
(function() {
  'use strict';

  angular
    .module('${1:app}')
    .controller('${2:Controller}',${2: Controller});

    ${2:MyController}.$inject = [${3:'$scope'}];

  function ${2:MyController}(${3:$scope}){

    /*jshint validthis: true */
    var vm = this;

    activate();

    function activate(){

    }

  }

})();
```

### angconst
```js
(function() {
  'use strict';

    angular
        .module('${1:app}')
        .constant('${2:myConstant}', ${3:'value'})$4;

})();
```

### angdir
```js
(function() {
  'use strict';

  angular
    .module('${1:app}')
    .directive('${2:directive}', ${2:directive});

  ${2:directive}.$inject = [${3:'dataService'}];

  function ${2:directive}(${3:dataService}){
    // Usage: ...
    var directive = {
      restrict: '${4:ACE}',
      templateUrl: '${4:templateUrl}',
      scope: {
      },
      link: link
    };
    return directive;

    function link(scope, element, attrs){

    }

  }

})();
```

### angdirc
```js
(function() {
  'use strict';

  angular
    .module('${1:app}')
    .directive('${2:directive}', ${2:directive});

  function ${2:directive}(){
    // Usage: ...
    var directive = {
      restrict: '${3:ACE}',
      templateUrl: '${4:templateUrl}',
      scope: {
      },
      link: link,
      controller: '${5:Controller}',
      controllerAs: 'vm',
      bindToController: true
    };
    return directive;

    function link(scope, element, attrs, ctrl){

    }

  }

  ${5:Controller}.$inject = ['${6:dataService}'];

  function ${5:Controller}(${6:dataService}) {
      var vm = this;

      activate();

      function activate() {

      }
  }

})();
```

### angfact
```js
(function() {
  'use strict';

  angular
    .module('${1:app}')
    .factory('${2:factory}', ${2:factory});

  ${2:factory}.$inject = [${3:'$http'}];

  function ${2:DataService}(${3:$http}){

    var service = {
      ${4:getIndex}: ${4:getIndex}
    };

    return service;

    function ${4:getIndex}(){
      $5
    }

  }

})();
```

### angmod
```js
(function() {
  'use strict';

  angular.module('${1:module}', [$2]);

})();
```

### angserv
```js
(function() {
  'use strict';

  angular
    .module('${1:app}')
    .service('${2:dataService}', ${2:dataService});

  ${2:DataService}.$inject = [${3:'$http'}];

  //////////////////

  function ${2:dataService}(${3:$http}){

    this.${4:getIndex} = function(){
      $5
    }

  }

})();
```

## Contributing

1. Fork it!
1. Create your feature branch: git checkout -b my-new-feature
1. Commit your changes: git commit -m 'Add some feature'
1. Push to the branch: git push origin my-new-feature
1. Submit a pull request

## History

Check [Release][releases] list.

## License

MIT License © Justin Blough

[releases]: https://github.com/justinblough/Atom-AngularJS-Template-Snippets/releases
