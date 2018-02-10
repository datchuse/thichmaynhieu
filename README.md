<html>
<head>
<title>Thích Mày Nhiều</title>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<style> 
*{
    margin: 0px;
    padding: 0px;
}
body{
    background: url('http://file.vforum.vn/hinh/2014/12/cap-doi-tinh-yeu-12.jpg') center center fixed no-repeat transparent;
}
#texttyping{
    width: 500px;
    margin: 20px 10px 20px 100px;
    font-weight: bold;
    position: absolute;
    top: 150px;
    left: 30px;
    float: left;
}
#marquee{
    height: 400px;
    width: 400px;
    position: absolute;
    top: 50px;
    left: 650px;
    z-index: 10;
    float: left;
}
</style>
<script type="text/javascript" src="js/html5_audio_visualizer.js"></script>
<script language="javascript"> 
mensaje= 
 
'<font size="4" face="Courier New" color="#FF0099">Hiếu Xinh Đẹp . . .  Tao thích mày ^^<br></font>'+' <br>'+ 
 
'<font color="#009933" size="4">Mới đó mà đã 1 năm ruỡi trôi qua rồi nhỉ , nhanh thật đấy , hì hì. Nhớ lại những kỉ niệm giữa 2 đứa mình mà vui thật đấy , thời gian mình ở bên nhau không nhiều nhưng lại có khá nhìu kỉ niệm đẹp mà anh không bao giờ quên ^^</font>                <br>           '+
 
'<br>           '+
 
'<font size="4"  color="#FF6633">Mỗi khi nhìn say nắng m về nhà tao nhìn lại tao thì.....</font><br>'+
 
'                    <br>'+
 
'<font size="4" color="#ff3333">Một ngày gặp mày tao đã làm tao thấy nhớ...Nhiều lúc muốn nói ra hết tất cả mà lại không có đủ can đảm^^  Cái chuyện lần trước mà nói tao bồ mày thực sự không phải tao nói(chỉ vì tao mà làm phiền đến mày nhiều tao xin lỗi)^^ Xin lỗi nhiều </font>  <br> <br>           '+
 
'  <font size="7" color="#F5A9F2">  Tớ thích cậu mãi mãi^^ </font>'+
'                    <br>'+
'<br><font color="#669933">( </font><font color="#ff3333">Because</font> <font color="#333399">I</font> <font color="#ff00ff">L♥ve</font> <font color="#333333">You</font> <font color="#669933">... )</font><br>'+
'<br><p align="left"> <font face="Courier New" color="#E0F8F7" size="8">Mãi Mãi Yêu Em</font></p>'
 
line=0
 
cursor='_'
 
function teclear(){
 
if(line==mensaje.length) cursor=''
 
texttyping.innerHTML=mensaje.substring(0,line)+cursor
 
if(line++<mensaje.length) setTimeout("teclear()",60) 
 
}
</script>
<script type="text/javascript"> 
// Set the number of snowflakes (more than 30 - 40 not recommended)
var snowmax=12
 
// Set the colors for the snow. Add as many colors as you like
var snowcolor=new Array("#aaaacc","#ddddFF","#ccccDD","#ffffff","#ffc0cb")
 
// Set the fonts, that create the snowflakes. Add as many fonts as you like
var snowtype=new Array("Arial Black","Arial Narrow","Times","Comic Sans MS")
 
// **** CHANGE YOUR IMAGE HERE ****
 
// Set the letter that creates your snowflake (recommended: * )
var snowletter=" ĐẠT ♥ Hiếu "
 
// Set the speed of sinking (recommended values range from 0.3 to 2)
var sinkspeed=0.6
 
// Set the maximal-size of your snowflaxes
var snowmaxsize=40
 
// Set the minimal-size of your snowflaxes
var snowminsize=20
 
// Set the snowing-zone
// Set 1 for all-over-snowing, set 2 for left-side-snowing
// Set 3 for center-snowing, set 4 for right-side-snowing
var snowingzone=1
 
///////////////////////////////////////////////////////////////////////////
// CONFIGURATION ENDS HERE
///////////////////////////////////////////////////////////////////////////
 
 
// Do not edit below this line
var snow=new Array()
var marginbottom
var marginright
var timer
var i_snow=0
var x_mv=new Array();
var crds=new Array();
var lftrght=new Array();
var browserinfos=navigator.userAgent
var ie5=document.all&&document.getElementById&&!browserinfos.match(/Opera/)
var ns6=document.getElementById&&!document.all
var opera=browserinfos.match(/Opera/)
var browserok=ie5||ns6||opera
 
function randommaker(range) {
	rand=Math.floor(range*Math.random())
    return rand
}
 
function initsnow() {
    teclear();
	if (ie5 || opera) {
      marginbottom = document.body.clientHeight
      marginright = document.body.clientWidth
   }
   else if (ns6) {
      marginbottom = window.innerHeight
      marginright = window.innerWidth
   }
	var snowsizerange=snowmaxsize-snowminsize
	for (i=0;i<=snowmax;i++) {
		crds[i] = 0;
    	lftrght[i] = Math.random()*15;
    	x_mv[i] = 0.03 + Math.random()/10;
		snow[i]=document.getElementById("s"+i)
		snow[i].style.fontFamily=snowtype[randommaker(snowtype.length)]
		snow[i].size=randommaker(snowsizerange)+snowminsize
		snow[i].style.fontSize=snow[i].size
		snow[i].style.color=snowcolor[randommaker(snowcolor.length)]
		snow[i].sink=sinkspeed*snow[i].size/5
		if (snowingzone==1) {snow[i].posx=randommaker(marginright-snow[i].size)}
		if (snowingzone==2) {snow[i].posx=randommaker(marginright/2-snow[i].size)}
		if (snowingzone==3) {snow[i].posx=randommaker(marginright/2-snow[i].size)+marginright/4}
		if (snowingzone==4) {snow[i].posx=randommaker(marginright/2-snow[i].size)+marginright/2}
		snow[i].posy=randommaker(2*marginbottom-marginbottom-2*snow[i].size)
		snow[i].style.left=snow[i].posx
		snow[i].style.top=snow[i].posy
	}
	movesnow()
}
 
function movesnow() {
	for (i=0;i<=snowmax;i++) {
		crds[i] += x_mv[i];
		snow[i].posy+=snow[i].sink
		snow[i].style.left=snow[i].posx+lftrght[i]*Math.sin(crds[i]);
		snow[i].style.top=snow[i].posy
 
		if (snow[i].posy>=marginbottom-2*snow[i].size || parseInt(snow[i].style.left)>(marginright-3*lftrght[i])){
			if (snowingzone==1) {snow[i].posx=randommaker(marginright-snow[i].size)}
			if (snowingzone==2) {snow[i].posx=randommaker(marginright/2-snow[i].size)}
			if (snowingzone==3) {snow[i].posx=randommaker(marginright/2-snow[i].size)+marginright/4}
			if (snowingzone==4) {snow[i].posx=randommaker(marginright/2-snow[i].size)+marginright/2}
			snow[i].posy=0
		}
	}
	var timer=setTimeout("movesnow()",60)
}
 
for (i=0;i<=snowmax;i++) {
	document.write("<span id='s"+i+"' style='position:absolute;top:-"+snowmaxsize+"'>"+snowletter+"</span>")
}
if (browserok) {
	window.onload=initsnow;
 
}
</script>
</head>
<body >
 
<iframe src="https://www.nhaccuatui.com/mh/auto/HkfqBZJHA0yo" width="1" height="1" frameborder="0" allowfullscreen></iframe>
<div id="marquee">
<marquee onmouseover="this.stop()" onmouseout="this.start()" scrollAmount="1" scrollDelay="60" direction="up">
<font color="#FF0099" size="2" face="tahoma"><b>
╔♫═╗╔╗ ♥ <b></br>
╚╗╔╝║║♫═╦╦╦╔╗<b> </br>
╔╝╚╗♫╚╣║║║║╔╣ <b></br>
╚═♫╝╚═╩═╩♫╩═╝ <b></br>
ஜ۩۞۩ஜ YOU ஜ۩۞۩ஜ<b></br>
<br />
<p align="center">Design By Hữu Đạt</p>
</b>
</marquee>
</div>
<div id="texttyping">
</div>
</body>
</html>
