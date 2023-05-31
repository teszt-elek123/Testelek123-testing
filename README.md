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

      
      
      
       Console.WriteLine($"7.feladat: \n\tA legkisebb alapterületű ingatlan {min} m2 területű, {minRooms} szobás.\n\tEladó adatai: {minName}, {minPhone}");
            Dictionary<string, int> statistics = new Dictionary<string, int>();
            foreach (var item in estates)
            {
                if (!statistics.ContainsKey(item.categoryName))
                {
                    statistics.Add(item.categoryName, 1);
                }
                else
                {
                    statistics[item.categoryName]++;
                }
            }
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
            Console.WriteLine("8.feladat: Statisztika");
            foreach (var item in statistics)
            {
                Console.WriteLine($"\t{item.Key} - {item.Value} ");
            }
            StreamWriter sw = new StreamWriter("FreeOfCharge.txt");
            sw.WriteLine("Id;Rooms;Floors;Area;CreateAt;SellerName;SellerPhone;CategoryName");
            foreach (var item in estates)
            {
                if (item.freeOfCharge == 0)
                {
                    sw.WriteLine($"{item.id};{item.rooms};{item.floors};{item.area};{item.createAt:yyy.MM.d};{item.sellerName};{item.sellerPhone};{item.categoryName}");

                }
            }
            sw.Flush();
            sw.Close();
