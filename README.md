<!DOCTYPE html>
<html lang="my">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>💖 Love</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:sans-serif;
}

body{
    height:100vh;
    overflow:hidden;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ffd6e7,#ffc0cb);
}

.card{
    background:white;
    padding:30px;
    border-radius:20px;
    text-align:center;
    box-shadow:0 10px 30px rgba(0,0,0,.2);
    z-index:10;
    position:relative;
}

h1{
    color:#ff3b7d;
    margin-bottom:25px;
}

.buttons{
    display:flex;
    justify-content:center;
    gap:20px;
}

button{
    padding:12px 28px;
    border:none;
    border-radius:30px;
    font-size:18px;
    cursor:pointer;
    transition:.2s;
}

#yes{
    background:#ff3b7d;
    color:white;
}

#yes:hover{
    transform:scale(1.08);
}

#no{
    background:white;
    color:#ff3b7d;
    border:2px solid #ff3b7d;
}

.heart{
    position:fixed;
    top:-30px;
    font-size:25px;
    animation:fall linear infinite;
}

@keyframes fall{
    from{
        transform:translateY(-30px);
    }
    to{
        transform:translateY(110vh);
    }
}
</style>
</head>

<body>

<div class="card">
<h1>💖 ကျွန်တော့်ကိုချစ်လား? 🥺</h1>

<div class="buttons">
<button id="yes">💖 ချစ်တယ်</button>
<button id="no">💔 မချစ်ဘူး</button>
</div>

</div>

<script>

const no=document.getElementById("no");

function moveButton(){

    no.style.position="fixed";

    let x=Math.random()*(window.innerWidth-140);
    let y=Math.random()*(window.innerHeight-70);

    no.style.left=x+"px";
    no.style.top=y+"px";
}

no.addEventListener("mouseover",moveButton);
no.addEventListener("touchstart",function(e){
    e.preventDefault();
    moveButton();
});

document.getElementById("yes").onclick=function(){

document.body.innerHTML=`
<div style="
height:100vh;
display:flex;
justify-content:center;
align-items:center;
background:linear-gradient(135deg,#ffd6e7,#ffc0cb);
font-size:35px;
text-align:center;
padding:20px;
color:#ff3b7d;
font-weight:bold;
">
💖<br><br>
ကျွန်တော့်ကို ချစ်ပေးလို့<br>
ကျေးဇူးပါနော် 💕🥹
</div>
`;

for(let i=0;i<50;i++){
heart();
}

}

function heart(){

let h=document.createElement("div");

h.className="heart";
h.innerHTML=["💖","💕","💗","💘"][Math.floor(Math.random()*4)];

h.style.left=Math.random()*100+"%";
h.style.animationDuration=(3+Math.random()*4)+"s";
h.style.fontSize=(20+Math.random()*20)+"px";

document.body.appendChild(h);

setTimeout(()=>{
h.remove();
},7000);

}

setInterval(heart,300);

</script>

</body>
</html>
