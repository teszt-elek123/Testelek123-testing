# Testelek123-testing

require_once("../common/php/environment.php");
$db = new Database("test");
$result = $db ->execute("SELECT * FROM car");
Util::setResponse($result);

<body ng-app="app" ng-controller="appController">
<ul ng-repeat="cars in car">
    <li>{{cars.id}} - {{cars.name}}</li>
</ul>


  <script src="../components/angular-js/1.8.2/js/angular.min.js"></script>
  <script src="../common/js/common-angular.js"></script>
  <script>
    angular.module('app', ["app.common"])
    .controller('appController', [
      "$scope",
      "http",
      ($scope,http) => {
        http.request('getData.php').then((request) =>{
        $scope.car = request;
        $scope.$applyAsync();
        }).catch((error)=>{
            console.log(error);
        })
      }
    ]);
