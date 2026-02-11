<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Will You Be My Valentine? 💝</title>
<style>
body{margin:0;font-family:Poppins,sans-serif;height:100vh;background:linear-gradient(135deg,#ffafbd,#ffc3a0);display:flex;justify-content:center;align-items:center;overflow:hidden}
.container{background:rgba(255,255,255,.95);padding:25px;border-radius:20px;width:92%;max-width:420px;text-align:center;box-shadow:0 20px 40px rgba(0,0,0,.2)}
h1,h2,h3{color:#ff4757}
button{background:#ff6b6b;border:none;color:white;padding:10px 18px;margin:6px;border-radius:25px;cursor:pointer;font-size:1rem}
button:hover{background:#ff8787}
.hidden{display:none}
.meter{font-size:2rem;color:#ff4757}
.yellow{color:#f1c40f}.green{color:#2ecc71}.red{color:#e74c3c}
.answer-box{background:#ffe6ec;padding:10px;border-radius:10px;margin-top:10px;font-size:.9rem;text-align:left}
.fade{animation:fadeIn 1s ease-in-out}
@keyframes fadeIn{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}/* Floating Hearts */
    .heart {
        position: fixed;
        bottom: -10px;
        font-size: 20px;
        animation: floatUp 6s linear infinite;
        opacity: 0.7;
    }
    @keyframes floatUp {
        0% { transform: translateY(0) scale(1); opacity:0.7; }
        100% { transform: translateY(-100vh) scale(1.5); opacity:0; }
    }

    /* Animated Score */
    .scoreReveal {
        font-size: 26px;
        font-weight: bold;
        animation: pop 0.6s ease forwards;
    }
    @keyframes pop {
        0% { transform: scale(0); }
        100% { transform: scale(1); }
    }

    /* Dark Romantic Theme */
    body {
        background: linear-gradient(135deg,#1a001f,#330033);
        color: #ffccff;
    }
    button {
        background:#ff4da6;
        color:white;
        border:none;
        padding:10px 18px;
        border-radius:20px;
        cursor:pointer;
        transition:0.3s;
    }
    button:hover { transform:scale(1.1); }

    /* Confetti */
    .confetti {
        position: fixed;
        width: 10px;
        height: 10px;
        background: pink;
        top: 0;
        animation: fall 4s linear infinite;
    }
    @keyframes fall {
        to { transform: translateY(100vh) rotate(360deg); }
    }

    /* Heart Explosion */
    .boom {
        position: fixed;
        font-size: 30px;
        animation: explode 1s ease-out forwards;
    }
    @keyframes explode {
        0% { transform: scale(0); opacity:1; }
        100% { transform: scale(3); opacity:0; }
    }

    /* Typing Effect */
    .typing {
        overflow: hidden;
        white-space: nowrap;
        border-right: 2px solid pink;
        width: 0;
        animation: typing 3s steps(40,end) forwards;
    }
    @keyframes typing {
        to { width:100%; }
    }
</style>

</head>
<body><!-- Background Music -->
<audio id="bgMusic" loop>
    <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_115b9b7f42.mp3" type="audio/mpeg">
</audio>

<div class="container"><h1 id="mainQ">Do you like me?</h1>
<div id="likeBtns">
<button onclick="likeYes()">Yes</button>
<button onclick="alert('Wrong answer 😌')">No</button>
</div><p id="likeMsg" class="hidden fade">I don't like you, I love you! ❤️</p><div id="loveSection" class="hidden">
<p>How much do you love me?</p>
<div class="meter" id="meter">100%</div>
<p id="loveText"></p>
<button onclick="addLove(200)">This much!</button>
<button onclick="addLove(1000)">More 😏</button>
<button onclick="goForever()">Next ❤️</button>
</div><div id="foreverSection" class="hidden">
<h2>Will you be my forever wala person?</h2>
<button onclick="promiseGate()">Yes</button>
<button onclick="noForever()">No</button>
</div><div id="promiseSection" class="hidden fade">
<p><i>"Before you read this, promise me something…"</i></p>
<button onclick="showNote()">Go ahead</button>
</div><div id="noteSection" class="hidden fade">
<p>
thank you for being with me always and thank you for choosing me<br><br>
thank you for listening to all my childish acts and ofc not leaving me alone and holding me tight when i am not okay.....<br><br>
i will always be yours. see a thing or the person that is yours will always be yours right...!!!
</p>
<button onclick="secretIntro()">You know a secret? 👀</button>
</div><div id="quiz"></div>
<div id="result" class="hidden"></div>
<button id="showAnsBtn" class="hidden" onclick="showAnswers()">📋 Show Answers</button></div><script>
let love=100,noCount=0,answers=[],score=0,qi=0;

function likeYes(){
likeMsg.classList.remove('hidden');
setTimeout(()=>{likeBtns.classList.add('hidden');loveSection.classList.remove('hidden')},1200)
}

function addLove(v){
love+=v;meter.innerText=love+'%';
if(love>10000)loveText.innerText='WOOOOW You love me that much?? 🥰🚀💝';
else if(love>1000)loveText.innerText='To infinity and beyond! 🚀💝';
else if(love>100)loveText.innerText='And beyond! 🥰';
}

function goForever(){loveSection.classList.add('hidden');foreverSection.classList.remove('hidden')}

function noForever(){
noCount++;
if(noCount==2)alert("you don't love me?? :(");
if(noCount>=3)alert('you are not allowed to');
}

function promiseGate(){
foreverSection.classList.add('hidden');
promiseSection.classList.remove('hidden');
}

function showNote(){
promiseSection.classList.add('hidden');
noteSection.classList.remove('hidden');
}

function secretIntro(){
noteSection.classList.add('hidden');
quiz.classList.remove('hidden');
renderQ();
}

const questions=[
{q:'When is my birthday?',o:['29 October','29 August','29 November'],c:0,lv:'yellow'},
{q:'If I talk about breakup what will I do?',o:['Cry','Mute myself','Ignore & move on'],c:0,lv:'yellow'},
{q:'What am I to you?',o:['Girlfriend','Best friend','None'],c:0,lv:'yellow'},
{q:'Which is my favourite English song?',o:['Love Me Like You Do','Love Story','Driver’s License'],c:1,lv:'green'},
{q:'Favourite singer?',o:['Arijit Singh','Shreya Ghoshal','Taylor Swift'],c:0,lv:'green'},
{q:'If I could have a superpower?',o:['Teleportation','Fly','Time travel'],c:0,lv:'green'},
{q:'Would you rather always win or never argue?',o:['Win','Apologize','Never argue'],c:1,lv:'red'},
{q:'What outfit do I look the cutest in?',o:['Dress','Casual','Traditional'],c:2,lv:'red'},
{q:'Which kiss do I like most?',o:['French','Rainbow','Neck'],c:0,lv:'red'},
{q:'Would you be jealous if you saw me with other guys?',o:['Yes','No','Ofc no but yes'],c:2,lv:'red'}
];

function renderQ(){
quiz.innerHTML=`<h3 class="${questions[qi].lv}">${questions[qi].q}</h3>`+
questions[qi].o.map((x,i)=>`<button onclick="pick(${i})">${x}</button>`).join('');
}

function pick(i){
answers.push({question:questions[qi].q,answer:questions[qi].o[i]});
if(i===questions[qi].c)score++;
qi++;
if(qi<questions.length)renderQ();
else finish();
}

function finish(){
quiz.classList.add('hidden');
result.classList.remove('hidden');
let msg=score===10?'LOVE YOU BABY!!':score<=4?'😡😡':'DON\'T YOU LOVE ME?!';
result.innerHTML=`<h2>Congratulations! Score: ${score}/10</h2><p>${msg}</p><p>I love you more than you know and be sure about it, I will never ever leave you… I love you and that’s never gonna be replaced ❤️</p>`;
localStorage.setItem('valentineAnswers',JSON.stringify(answers));
localStorage.setItem('valentineScore',score);
showAnsBtn.classList.remove('hidden');
}

function showAnswers(){
const data=JSON.parse(localStorage.getItem('valentineAnswers'))||[];
result.innerHTML+=`<div class="answer-box"><b>Your Answers:</b><br>`+data.map(x=>`• ${x.question} → ${x.answer}`).join('<br>')+`</div>`;
}

        // Play music on first click anywhere
        document.addEventListener("click", function() {
            const music = document.getElementById("bgMusic");
            if (music && music.paused) {
                music.play().catch(()=>{});
            }
        }, { once: true });

        // Floating hearts generator
        setInterval(() => {
            const heart = document.createElement("div");
            heart.className = "heart";
            heart.style.left = Math.random() * 100 + "vw";
            heart.innerHTML = "💖";
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 6000);
        }, 800);

        // Runaway No button
        function moveNo(btn) {
            btn.style.position = "absolute";
            btn.style.top = Math.random() * 80 + "vh";
            btn.style.left = Math.random() * 80 + "vw";
        }

    
        // Suspense score counting
        function dramaticScore(finalScore){
            let count = 0;
            const display = document.getElementById("scoreText");
            const interval = setInterval(()=>{
                display.innerHTML = "Calculating... " + count;
                count++;
                if(count>finalScore){
                    clearInterval(interval);
                    display.innerHTML = "Final Score: " + finalScore + " / 10";
                    if(finalScore==10){
                        heartExplosion();
                        confettiRain();
                    }
                }
            },300);
        }

        // Confetti rain
        function confettiRain(){
            for(let i=0;i<50;i++){
                const c=document.createElement("div");
                c.className="confetti";
                c.style.left=Math.random()*100+"vw";
                c.style.background=`hsl(${Math.random()*360},100%,70%)`;
                c.style.animationDuration=(Math.random()*3+2)+"s";
                document.body.appendChild(c);
                setTimeout(()=>c.remove(),4000);
            }
        }

        // Heart Explosion
        function heartExplosion(){
            for(let i=0;i<20;i++){
                const h=document.createElement("div");
                h.className="boom";
                h.style.left=Math.random()*100+"vw";
                h.style.top=Math.random()*100+"vh";
                h.innerHTML="💖";
                document.body.appendChild(h);
                setTimeout(()=>h.remove(),1000);
            }
        }

        // Password lock for Show Answers
        function showAnswers(){
            const pass = prompt("Enter password to see answers:");
            if(pass==="forever29"){
                document.getElementById("answersSection").style.display="block";
            } else {
                alert("Wrong password 😏");
            }
        }

    </script></body>
</html>