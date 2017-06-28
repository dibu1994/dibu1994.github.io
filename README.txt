To run application open index.html in your browser

Optimzations required

 FIle : index.html
 - add async attribute to analytics and perfmatters script
 - replace images with compressed images. COmpressed version of images is located at compressed/images
 - optimize css delievery for screen , print and fonts styles
 - add async tags in images for asynchronous loading of images


 File:  views/js/main.js

-Changed changedPizzaSizes function :- Pipeline is not broken now and Expensive determinDx method not called now

function changePizzaSizes(size) {

var newWidth=0;
    switch(size)
    {
      case "1":
      newWidth=25;
      break;
      case "2":
      newWidth=33.33;
      break;
      case "3":
      newWidth=50;
      break;
      default:
      console.log("Bug");
    }
    var randomPizzas=document.querySelectorAll(".randomPizzaContainer");

    for (var i = 0; i < document.querySelectorAll(".randomPizzaContainer").length; i++) {
      randomPizzas[i].style.width = newWidth+"%";
    }
  }

  -in updatePositions functions take out  line :var top=document.body.scrollTop/1250 ouside for loop so that pipeline is not broken
  - query Selector replaced by getElementById in function changeSliderLabel
  - At Line 550 number of pizzas reduced to 24 insted of 200
  - This declaration is made outside for loop :  var movingPizzas = document.getElementById('movingPizzas1');


  File : views/css/style.css

  Added   transform: translateZ(0); to mover class