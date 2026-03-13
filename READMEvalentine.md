<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine Proposal</title>

<style>

body{
margin:0;
font-family:Poppins, sans-serif;
height:100vh;
overflow:hidden;
background:linear-gradient(135deg,#ff9ecf,#ffd6ec);
}

/* pages */

.page{
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
text-align:center;
}

/* floating hearts */

.heart{
position:absolute;
font-size:20px;
color:#ff2e8b;
animation:float 6s linear infinite;
}

@keyframes float{
0%{transform:translateY(100vh);opacity:0}
50%{opacity:1}
100%{transform:translateY(-10vh);opacity:0}
}

/* title */

h1{
font-size:45px;
color:#d6006c;
animation:fade 2s infinite alternate;
}

@keyframes fade{
from{transform:scale(1)}
to{transform:scale(1.08)}
}

/* buttons */

button{
padding:14px 28px;
font-size:18px;
border:none;
border-radius:30px;
cursor:pointer;
margin:10px;
}

#yes{
background:#ff2e8b;
color:white;
}

#no{
background:white;
color:#ff2e8b;
position:relative;
}

/* second page */

#page2{
display:none;
background:linear-gradient(135deg,#ff5fa2,#ff85c9);
color:white;
}

#page2 h2{
font-size:45px;
animation:pulse 1.5s infinite alternate;
}

@keyframes pulse{
from{transform:scale(1)}
to{transform:scale(1.1)}
}

</style>
</head>

<body>

<!-- FIRST PAGE -->

<div id="page1" class="page">

<h1>Will you be my Valentine dear? 💖</h1>

<div>
<button id="yes">Yes 💕</button>
<button id="no">No 😢</button>
</div>

</div>

<!-- SECOND PAGE -->

<div id="page2" class="page">

<h2>Yay! 💖</h2>

<p style="font-size:24px;">
I also love you very much 💕 <br>
Thank you for accepting my proposal 🌹
</p>

</div>

<script>

/* YES BUTTON */

document.getElementById("yes").onclick=function(){

document.getElementById("page1").style.display="none";
document.getElementById("page2").style.display="flex";

}

/* NO BUTTON RUN AWAY */

let noBtn=document.getElementById("no");

noBtn.addEventListener("mouseover",function(){

let x=Math.random()*(window.innerWidth-100);
let y=Math.random()*(window.innerHeight-50);

noBtn.style.position="absolute";
noBtn.style.left=x+"px";
noBtn.style.top=y+"px";

});

/* floating hearts */

setInterval(()=>{

let heart=document.createElement("div");

heart.className="heart";
heart.innerHTML="💖";

heart.style.left=Math.random()*100+"vw";
heart.style.fontSize=(20+Math.random()*25)+"px";

document.body.appendChild(heart);

setTimeout(()=>heart.remove(),6000);

},300);

</script>

</body>
</html>
