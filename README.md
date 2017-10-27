# helloworld
<!DOCTYPE html>
<!--Garrett Morgan, Joshua Lampenfield, Chris Gamble, Robbie Eberhardt
Professor Mullins
CpSc 215
13 October 2017-->
<html>
<head>
<title>Image Animation</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<script>
var selectImg=[]; <!-- Array of selected images -->
var i=-1;
var j=-1;
var q=0;
var animTimer=setInterval(startAnim, 1000);
clearInterval(animTimer); <!-- Stops timer -->
function addImg(imgId){ <!-- Adds image to array of selected images -->
    i++;
    j++;
    selectImg.push(imgId);
    document.getElementById('under').innerHTML+="<img src='" + selectImg[i].src + "' id=img"+j+"a width='160' height='122'/> ";
}
function deleteLast(){ <!-- Removes last image from page and array -->
  var divUnder = document.getElementById('under');
  var currentImg = document.getElementById('img'+j+'a');
  divUnder.removeChild(currentImg);
  selectImg.pop();
  i--;
  j--;
}
function startAnim(){
    document.getElementById('over').innerHTML="<img src='" + selectImg[q].src + "' id=img"+j+"a width='208' height='159'/> ";
  q++;
  if (q>i){
      q=0;
    }
}
function stopAnim(){
    clearInterval(animTimer);
}
</script>
<style>
    img {
       max-width: 100%;
       height: auto;
    }
</style>
</head>
<body>
<div id='over'>
<img src="attentionLeft.jpg" width="208" height="159" onclick="addImg(this);">
<img src="attentionRight.jpg" width="208" height="159" onclick="addImg(this);">
<img src="bBall.jpg" width="208" height="159" onclick="addImg(this);">
<img src="bend1.jpg" width="208" height="159" onclick="addImg(this);">
<img src="bendBall.jpg" width="208" height="159" onclick="addImg(this);">
<img src="cowForward.jpg" width="208" height="159" onclick="addImg(this);">
<img src="cowLeft.jpg" width="208" height="159" onclick="addImg(this);">
<img src="escape.jpg" width="208" height="159" onclick="addImg(this);">
<img src="handsOut.jpg" width="208" height="159" onclick="addImg(this);">
<img src="handsUp.jpg" width="208" height="159" onclick="addImg(this);">
<img src="holdBall.jpg" width="208" height="159" onclick="addImg(this);">
<img src="holdRabbit.jpg" width="208" height="159" onclick="addImg(this);">
<img src="lunchLady.jpg" width="208" height="159" onclick="addImg(this);">
<img src="rabbit.jpg" width="208" height="159" onclick="addImg(this);">
<img src="safe.jpg" width="208" height="159" onclick="addImg(this);">
<img src="standBall.jpg" width="208" height="159" onclick="addImgr(this);">
<img src="startBall.jpg" width="208" height="159" onclick="addImgr(this);">
<img src="startEmpty.jpg" width="208" height="159" onclick="addImg(this);">
<img src="walkLFF.jpg" width="208" height="159" onclick="addImg(this);">
<img src="walkRFF.jpg" width="208" height="159" onclick="addImg(this);">
</div>
<button type ="button" onclick="deleteLast();">delete last</button>
<button type ="button" onclick="startAnim();animTimer=setInterval(startAnim, 1000);">start</button>
<button type ="button" onclick="stopAnim();">stop</button>
<p>Add frames by clicking the image</p>
<div id="under">
</div>
</body>
</html>

