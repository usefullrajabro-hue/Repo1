import webbrowser
from pathlib import Path

html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Sister 💖</title>

<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
body{
margin:0;
overflow:hidden;
font-family:'Poppins',sans-serif;
background:linear-gradient(135deg,#ff9a9e,#fad0c4,#fbc2eb,#a6c1ee);
background-size:400% 400%;
animation:gradientBG 12s ease infinite;
display:flex;
justify-content:center;
align-items:center;
height:100vh;
}

@keyframes gradientBG{
0%{background-position:0% 50%}
50%{background-position:100% 50%}
100%{background-position:0% 50%}
}

.container{
text-align:center;
color:white;
}

h1{
font-family:'Pacifico',cursive;
font-size:50px;
animation:glow 2s infinite alternate;
}

@keyframes glow{
from{text-shadow:0 0 10px #fff;}
to{text-shadow:0 0 25px #ff4da6;}
}

.message{
font-size:20px;
margin-top:20px;
max-width:400px;
animation:fadeIn 2s ease forwards;
}

@keyframes fadeIn{
from{opacity:0; transform:translateY(20px);}
to{opacity:1; transform:translateY(0);}
}

button{
margin-top:30px;
padding:12px 30px;
border:none;
border-radius:30px;
background:#ff4da6;
color:white;
font-weight:bold;
cursor:pointer;
transition:0.3s;
}

button:hover{
transform:scale(1.1);
}

.emoji{
font-size:60px;
animation:bounce 2s infinite;
}

@keyframes bounce{
0%,100%{transform:translateY(0);}
50%{transform:translateY(-20px);}
}

/* Floating hearts */
.heart{
position:absolute;
font-size:25px;
animation:floatUp 5s linear infinite;
}

@keyframes floatUp{
0%{transform:translateY(100vh); opacity:1;}
100%{transform:translateY(-10vh); opacity:0;}
}

/* Balloon */
.balloon{
position:absolute;
font-size:50px;
animation:balloonUp 8s linear infinite;
}

@keyframes balloonUp{
0%{transform:translateY(100vh);}
100%{transform:translateY(-20vh);}
}
</style>
</head>

<body>

<div class="container">
<div class="emoji">🎂</div>
<h1>Happy Birthday Sis 💕</h1>
<div class="message">
You are not just my sister… you are my best friend, my protector, 
and my biggest blessing in life. 💖  
May your day be filled with happiness, laughter, success, and endless love!
</div>
<button onclick="celebrate()">Celebrate 🎉</button>
</div>

<script>
function createHearts(){
for(let i=0;i<20;i++){
let heart=document.createElement("div");
heart.className="heart";
heart.innerHTML="💖";
heart.style.left=Math.random()*100+"%";
heart.style.animationDuration=(3+Math.random()*5)+"s";
document.body.appendChild(heart);
}
}

function createBalloons(){
for(let i=0;i<10;i++){
let balloon=document.createElement("div");
balloon.className="balloon";
balloon.innerHTML="🎈";
balloon.style.left=Math.random()*100+"%";
balloon.style.animationDuration=(6+Math.random()*5)+"s";
document.body.appendChild(balloon);
}
}

function celebrate(){
createHearts();
createBalloons();
}
</script>

</body>
</html>
"""

file_path = Path("sister_birthday_surprise.html")
file_path.write_text(html_content, encoding="utf-8")
webbrowser.open(file_path.resolve().as_uri())