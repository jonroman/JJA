var getTime = () => {
  var date = new Date();
  var node = document.createElement("DIV");
  var timenode = document.createTextNode(date);
  node.appendChild(timenode);
  document.getElementById("time_1").appendChild(node);
  document.getElementById("time_1").style.display = "block";
}

var clearTime = () => {
  var node = document.getElementById("time_1");
  while (node.hasChildNodes()) {   
    node.removeChild(node.firstChild);
  }
}

var toggleTime = () => {
  var toggle = "block";
  if (document.getElementById("time_1").style.display == "block") {
    toggle = "none";
  }
  document.getElementById("time_1").style.display = toggle;
}

var showCode = () => {
  window.open('get_time.js');
}

// ***** JQUERY  ****
$("#get_time").on("click", () => {
  var date = new Date();
  $("#time_2").append("<div class='card-title'>TIME:</div><div class='card-body'>"+date+"</div>").css("display","block");
});

$("#clear_time").on("click", () => {
  $("#time_2").empty();
});

$("#toggle_time").on("click", () => {
  $("#time_2").toggle();
});

$("#show_code").on("click", () => {
  window.open('get_time.js');
});

// Angularjs
var app = angular.module('jonny-app', []);
app.controller('iron-man-controller', function($scope) {
    $scope.title = "Angularjs (1.6)";
    $scope.subtitle = "...featuring bootstrap 4";
    $scope.current_time = new Date();
    $scope.times = [];
    $scope.hide_show = false;
    

    $scope.getTime = () => {
      var date = new Date();
      $scope.times.push(date);
    };

    $scope.clearTime = () => {
      $scope.times = [];
    };

    $scope.toggleTime = () => {
      if(!$scope.hide_show) {
       $scope.hide_show = true;
      } else {
        $scope.hide_show = false;
      }
    };

    $scope.showCode = () => {
      window.open('get_time.js');
    };
});