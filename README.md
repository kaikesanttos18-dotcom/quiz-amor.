# quiz-amor.[quiz.love.html](https://github.com/user-attachments/files/25829033/quiz.love.html)
```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>Quiz do Amor 💖</title>

<style>

body{
font-family:Arial;
background:linear-gradient(135deg,#ff758c,#ff7eb3);
text-align:center;
margin:0;
overflow:hidden;
}

.quiz{
background:white;
padding:30px;
border-radius:20px;
max-width:600px;
margin:120px auto;
box-shadow:0 10px 30px rgba(0,0,0,0.3);
}

h1{
color:#ff2f65;
}

.pergunta{
font-size:22px;
margin:20px;
}

button{
display:block;
width:100%;
margin:10px 0;
padding:12px;
border:none;
border-radius:10px;
background:#ff2f65;
color:white;
font-size:16px;
cursor:pointer;
transition:0.3s;
}

button:hover{
background:#ff004c;
}

.heart{
position:fixed;
top:-10px;
font-size:20px;
animation:cair 3s linear;
}

@keyframes cair{
0%{transform:translateY(0);opacity:1}
100%{transform:translateY(100vh);opacity:0}
}

.explosion{
position:fixed;
font-size:25px;
animation:boom 1s ease-out;
}

@keyframes boom{
0%{transform:scale(0.5);opacity:1}
100%{transform:scale(3);opacity:0}
}

#final{
font-size:50px;
color:white;
margin-top:40px;
display:none;
}

</style>

</head>

<body>

<div class="quiz">

<h1>Quiz do Amor 💕</h1>

<div id="pergunta" class="pergunta"></div>

<div id="respostas"></div>

<div id="final">EU TE AMOOOOOOO ❤️</div>

</div>

<script>

let quiz=[

{
p:"1️⃣ O quanto você me ama?",
r:[
"A) infinito igual ao Buzz Lightyear 🚀",
"B) MUITO MUITO MUITO MUITO",
"C) IMENSAMENTE ❤️",
"D) Todas as alternativas"
]
},

{
p:"2️⃣ Quem é o amor da sua vida?",
r:[
"A) Você",
"B) Meu namorado lindo",
"C) Meu tudo",
"D) Todas as alternativas"
]
},

{
p:"3️⃣ Nosso amor é:",
r:[
"A) Forte",
"B) Especial",
"C) Infinito",
"D) O melhor do universo"
]
},

{
p:"4️⃣ Quando pensa em mim você:",
r:[
"A) Sorri",
"B) Fica feliz",
"C) Sente saudade",
"D) Tudo isso"
]
},

{
p:"5️⃣ Qual é a resposta certa?",
r:[
"A) Amar",
"B) Amar muito",
"C) Amar infinitamente",
"D) TODAS"
]
}

]

let atual=0

function chuva(qtd){

for(let i=0;i<qtd;i++){

let h=document.createElement("div")

h.className="heart"

h.innerHTML="❤️"

h.style.left=Math.random()*100+"vw"

h.style.fontSize=(Math.random()*20+15)+"px"

document.body.appendChild(h)

setTimeout(()=>h.remove(),3000)

}

}

function explosao(){

for(let i=0;i<40;i++){

let h=document.createElement("div")

h.className="explosion"

h.innerHTML="💖"

h.style.left=Math.random()*100+"vw"
h.style.top=Math.random()*100+"vh"

document.body.appendChild(h)

setTimeout(()=>h.remove(),1000)

}

}

function mostrar(){

if(atual>=quiz.length){

document.getElementById("pergunta").innerHTML=""
document.getElementById("respostas").innerHTML=""

document.getElementById("final").style.display="block"

explosao()

return
}

let p=quiz[atual]

document.getElementById("pergunta").innerHTML="<h2>"+p.p+"</h2>"

let html=""

p.r.forEach((r,i)=>{

html+=`<button onclick="clicou(${i})">${r}</button>`

})

document.getElementById("respostas").innerHTML=html

}

function clicou(i){

if(i==3){
explosao()
}else{
chuva(25)
}

atual++

mostrar()

}

mostrar()

</script>

</body>
</html>
