# Web Page for Paint Application

## AIM:

To design a static website for Paint Application using HTML5 canvas.

## DESIGN STEPS:

### Step 1:

Requirement collection.

### Step 2:

Creating the layout using HTML,CSS and canvas.

### Step 3:

Write javascript to capture move events.

### Step 4:

Perform the drawing operation based on the user input.

### Step 5:

Validate the layout in various browsers.

### Step 6:

Validate the HTML code.

### Step 6:

Publish the website in the given URL.

## PROGRAM :
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Paint Application</title>
  <style>
  * {
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }
    body {
      background-color:rgb(83, 83, 88);
    }
    .container {
      width: 1400px;
      margin-left: auto;
      margin-right: auto;
      
    }
    .content {
      display: block;
      width: 100%;
      background-color: #e9ebe3;
      height: 800px;
      margin-top: 150px;
    }
    h1{
      text-align: center;
      padding-top: 50px;
      color: rgb(36, 23, 23);
      font-style: bold;
    }
    .formelement{
      text-align: center;
      font-size:xx-large;
      margin-top: 5px;
      margin-bottom: 5px;
    }
    .auth{
      text-align: center;
      color:black;
      font-family: Georgia, 'Times New Roman', Times, serif;
      font-size:xx-large;
    }
    canvas{
      margin-left: 40px;
      margin-right: 40px;
    }
    .toolbar{
      text-align: center;
      display:block;
      width: 100%;
      background-color: #d4ec8b;
      height: 80px;
      margin-top: 50px;
    }
    
  </style>
  <script type="text/javascript">
    var drawing = false;
    var ctx;

    window.onload=function(){
      document.getElementById('btnClear').addEventListener('click',function(){
        ctx.clearRect(0,0,ctx.canvas.width,ctx.canvas.height);
      },false);
      document.getElementById('lineWidth').addEventListener('change', function(){
            ctx.lineWidth = document.getElementById('lineWidth').value;
        }, false);
    document.getElementById('colorChange').addEventListener('change', function(){
            ctx.strokeStyle = document.getElementById('colorChange').value;
        }, false);

        ctx.strokeStyle="#000";
        ctx.lineJoin="round";
        ctx.lineWidth=5;

      }

    
    function myClickEvent(e) {
      //alert("clicked")
      var message;
      //message = "X=" +e.offsetX +",Y=" + e.offsetY;
      ctx.beginPath();
      if (shape == 0){
          ctx.arc(e.offsetX, e.offsetY, 50, 0, 2 * Math.PI);
             
      }else if (shape==1){
          ctx.rect(e.offsetX, e.offsetY, 100, 100);
          
      }else if (shape == 2){
          ctx.strokeRect(e.offsetX,e.offsetY,150,100);
      
      }else if (shape == 3){
        ctx.moveTo(e.offsetX, e.offsetY);
            ctx.lineTo(e.offsetX-(100/2),e.offsetY-(100*0.86602));
            ctx.lineTo(e.offsetX+(100/2),e.offsetY-(100*0.86602));
            ctx.lineTo(e.offsetX,e.offsetY)
      }
      //else if (shape == 3){
        //ctx.moveTo(e.offsetX,e.offsetY);
        //ctx.lineTo(e.offsetX-(e.offsetX/2),e.offsetY-(e.offsetY*0.86602));
        //ctx.lineTo(e.offsetX+(e.offsetX/2),e.offsetY-(e.offsetY*0.86602));
        //ctx.lineTo(e.offsetX,e.offsetY)}
      else if (shape == 4){
        ctx.moveTo(e.offsetX, e.offsetY);
        //ctx.lineTo(e.offsetX-(100/2),e.offsetY-(100*0.86602));
        ctx.lineTo(e.offsetX+(100/2),e.offsetY+(100*0.86602));
        
        
      }

    ctx.stroke();
    }
  
  
  
  function circleclicked() {
      shape=0;
  }
  function squareclicked() {
      shape=1;
  }
  function rectangleclicked() {
      shape=2;
  }
  function triangleclicked() {
      shape=3;
  }
  function lineclicked() {
      shape=4;
  }

  </script>

</head>
<body>
    <div class="container">
      <div class="content">
        <h1>Drawing Application</h1>
        <canvas 
        id="myCanvas"
        width="1315"
        height="600"
        style="border:1px solid #000000"
        ></canvas>
        <div class="toolbar">
              <input type="button" id="circle"  value="Circle"/>
              <input type="button" id="square"  value="Square"/>
              <input type="button" id="rectangle" value="Rectangle"/>
              <input type="button" id="triangle"  value="Triangle"/>
              <input type="button" id="line"  value="line"/><br>
              <lable for ="colorChange">Color: </lable><input type="color" id="colorChange"/>
              <lable for ="lineWidht">Size:</lable><input type="range" id="lineWidth" min="1" max="10" stpe="1"/>
              <button id="btnClear">Clear</button><br>
              Designed by: JEEVA ABISHAKE A 21500568
              
            


    </div>    
    </div>
    </div>
<script>
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");
shape=0;

c.addEventListener("click",myClickEvent);
document
.getElementById("circle")
.addEventListener("click",circleclicked);
document
.getElementById("square")
.addEventListener("click",squareclicked);
document
.getElementById("rectangle")
.addEventListener("click",rectangleclicked);
document
.getElementById("triangle")
.addEventListener("click",triangleclicked);
document
.getElementById("line")
.addEventListener("click",lineclicked);

    //alert("HI,canvas drawing")
</script>
</body>
</html>
```

## OUTPUT:

![output](blankpage.png)
![output](sample.png)
![output](editingbox.png)

## Result:

Thus a website is designed and validated for paint application using HTML5 canvas.
