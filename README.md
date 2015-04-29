<!DOCTYPE HTML>
<html>
<head>
	<meta http-equiv="content-type" content="text/html" />
	<meta name="author" content="lolkittens" />

	<title>Untitled 2</title>
    <script src="http://code.jquery.com/jquery-1.11.2.min.js"></script> 
    
 <style type="text/css">
 
 #mask {
  position: absolute;
  left: 0;
  top: 0;
  z-index: 9000;
  background-color: #000;
  display: none;
}

#boxes .window {
  position: absolute;
  left: 0;
  top: 0;
  width: 440px;
  height: 200px;
  display: none;
  z-index: 9999;
  padding: 20px;
  border-radius: 15px;
  text-align: center;
}

#boxes #dialog {
  width: 750px;
  height: 300px;
  padding: 10px;
  background-color: #ffffff;
  font-family: 'Segoe UI Light', sans-serif;
  font-size: 15pt;
}

#popupfoot {
  font-size: 16pt;
  position: absolute;
  bottom: 0px;
  width: 250px;
  left: 250px;
}
 
 </style>   
 
 <script type="text/javascript">
$(document).ready(function() {	

var id = '#dialog';
	
//Get the screen height and width
var maskHeight = $(document).height();
var maskWidth = $(window).width();
	
//Set heigth and width to mask to fill up the whole screen
$('#mask').css({'width':maskWidth,'height':maskHeight});

//transition effect
$('#mask').fadeIn(500);	
$('#mask').fadeTo("slow",0.9);	
	
//Get the window height and width
var winH = $(window).height();
var winW = $(window).width();
              
//Set the popup window to center
$(id).css('top',  winH/2-$(id).height()/2);
$(id).css('left', winW/2-$(id).width()/2);
	
//transition effect
$(id).fadeIn(2000); 	
	
//if close button is clicked
$('.window .close').click(function (e) {
//Cancel the link behavior
e.preventDefault();

$('#mask').hide();
$('.window').hide();
});

//if mask is clicked
$('#mask').click(function () {
$(this).hide();
$('.window').hide();
});
	
}); 
</script>
 
    
</head>

<body>

<div id="boxes">
  <div id="dialog" class="window">
    Your Content Goes Here
    <div id="popupfoot"> <a href="#" class="close agree">I agree</a> | <a class="agree"style="color:red;" href="#">I do not agree</a> </div>
  </div>
  <div id="mask"></div>
</div>

</body>
</html>
