<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🎁 Idris Ultimate Gift Reveal</title>
<style>
/* ===== RESET ===== */
*{margin:0;padding:0;box-sizing:border-box;font-family:'Poppins',sans-serif;}
body{overflow:hidden;display:flex;flex-direction:column;justify-content:space-between;align-items:center;height:100vh;background:linear-gradient(135deg, red, orange, yellow, green, cyan, blue, violet);background-size:400% 400%;animation:rainbowBG 15s ease infinite;cursor:pointer;}

/* ===== BACKGROUND ANIMATION ===== */
@keyframes rainbowBG{0%{background-position:0% 50%}50%{background-position:100% 50%}100%{background-position:0% 50%;}}

/* ===== HEADER ===== */
header{color:white;font-size:3em;text-shadow:0 0 25px rgba(255,255,255,0.7);animation:headerPulse 2s infinite alternate;text-align:center;margin-top:20px;}
@keyframes headerPulse{0%{text-shadow:0 0 25px rgba(255,255,255,0.7)}100%{text-shadow:0 0 80px rgba(255,255,255,1);}}

/* ===== FOOTER ===== */
footer{color:white;font-size:1.5em;margin-bottom:25px;text-shadow:0 0 15px rgba(255,255,255,0.5);transition:transform 0.3s ease;text-align:center;}
footer:hover{transform:scale(1.6);text-shadow:0 0 60px #fff;}

/* ===== CHECKBOX HACK FOR CLICK ===== */
#toggle{display:none;}
/* increased gift-container so photo can be bigger */
.gift-container{position:relative;width:400px;height:400px;margin:20px auto;cursor:pointer;z-index:10;}
.gift-box{width:100%;height:100%;background:url('https://cdn-icons-png.flaticon.com/512/869/869636.png') center/contain no-repeat;transition:transform 0.5s ease, box-shadow 0.3s ease;}
.gift-box:hover{transform:scale(1.1) rotate(-5deg);box-shadow:0 0 70px white;}

/* ===== PHOTO REVEAL ===== */
.photo{position:absolute;top:50%;left:50%;width:98%;height:98%;border-radius:15px;background:url('https://i.ibb.co/YsZp8sP/Whats-App-Image-2025-11-05-at-14-31-22-4b19b395.jpg') center/cover no-repeat;opacity:0;transform:translate(-50%,-50%) scale(0.7);transition:all 1.2s ease;z-index:1;}
#toggle:checked + .gift-container .photo{opacity:1;transform:translate(-50%,-50%) scale(1.05);box-shadow:0 0 130px white;border:6px solid rgba(255,255,255,0.7);animation:photoPulse 1.5s infinite alternate;}
@keyframes photoPulse{0%{box-shadow:0 0 70px rgba(255,255,255,0.6)}100%{box-shadow:0 0 200px rgba(255,255,255,1);}}

/* ===== SPARKLES ===== */
@keyframes sparkleAnim{0%{transform:scale(0);opacity:1}50%{transform:scale(1.5);opacity:0.8}100%{transform:scale(0);opacity:0}}
.gift-container::before,.gift-container::after{content:"";position:absolute;width:12px;height:12px;background:white;border-radius:50%;top:50%;left:50%;animation:sparkleAnim 1.2s infinite ease-in-out;}
.gift-container::after{animation-delay:0.6s;}

/* ===== FLOATING EMOJIS ===== */
@keyframes floatEmoji{0%{transform:translateY(0) rotate(0deg);opacity:0.8}100%{transform:translateY(-500px) rotate(360deg);opacity:0;}}
.emoji{position:absolute;font-size:32px;top:200px;animation:floatEmoji 6s linear infinite;}
.emoji:nth-child(1){left:10%;animation-delay:0s;}
.emoji:nth-child(2){left:30%;animation-delay:1s;}
.emoji:nth-child(3){left:50%;animation-delay:2s;}
.emoji:nth-child(4){left:70%;animation-delay:3s;}
.emoji:nth-child(5){left:90%;animation-delay:4s;}
.emoji:nth-child(6){left:15%;animation-delay:2.5s;}
.emoji:nth-child(7){left:35%;animation-delay:3.2s;}
.emoji:nth-child(8){left:55%;animation-delay:1.8s;}
.emoji:nth-child(9){left:75%;animation-delay:0.5s;}
.emoji:nth-child(10){left:85%;animation-delay:1.1s;}

/* ===== BUBBLES ===== */
@keyframes bubbleMove{0%{transform:translateY(0) scale(0.5)}100%{transform:translateY(-900px) scale(1.5)}}
.bubble{position:absolute;width:15px;height:15px;border-radius:50%;background:rgba(255,255,255,0.3);animation:bubbleMove 10s linear infinite;}
.bubble:nth-child(1){left:5%;bottom:0;animation-delay:0s;}
.bubble:nth-child(2){left:15%;bottom:0;animation-delay:1s;}
.bubble:nth-child(3){left:25%;bottom:0;animation-delay:2s;}
.bubble:nth-child(4){left:35%;bottom:0;animation-delay:3s;}
.bubble:nth-child(5){left:45%;bottom:0;animation-delay:4s;}
.bubble:nth-child(6){left:55%;bottom:0;animation-delay:5s;}
.bubble:nth-child(7){left:65%;bottom:0;animation-delay:6s;}
.bubble:nth-child(8){left:75%;bottom:0;animation-delay:7s;}
.bubble:nth-child(9){left:85%;bottom:0;animation-delay:8s;}
.bubble:nth-child(10){left:95%;bottom:0;animation-delay:9s;}

/* ===== CONFETTI ===== */
@keyframes confettiFall{0%{transform:translateY(0) rotate(0deg)}100%{transform:translateY(900px) rotate(720deg);opacity:0;}}
.confetti{position:absolute;width:12px;height:12px;background:hsl(200,100%,50%);opacity:0.9;border-radius:2px;animation:confettiFall 3s linear infinite;}
.confetti:nth-child(1){left:10%;animation-delay:0s;}
.confetti:nth-child(2){left:20%;animation-delay:0.3s;}
.confetti:nth-child(3){left:30%;animation-delay:0.6s;}
.confetti:nth-child(4){left:40%;animation-delay:0.9s;}
.confetti:nth-child(5){left:50%;animation-delay:1.2s;}
.confetti:nth-child(6){left:60%;animation-delay:1.5s;}
.confetti:nth-child(7){left:70%;animation-delay:1.8s;}
.confetti:nth-child(8){left:80%;animation-delay:2.1s;}
.confetti:nth-child(9){left:90%;animation-delay:2.4s;}
.confetti:nth-child(10){left:95%;animation-delay:2.7s;}
</style>
</head>
<body>

<header>✨ Open Your Ultimate Surprise ✨</header>

<input type="checkbox" id="toggle">
<label class="gift-container" for="toggle">
  <div class="gift-box"></div>
  <div class="photo"></div>
</label>

<!-- Floating emojis -->
<div class="emoji">🎉</div>
<div class="emoji">🎁</div>
<div class="emoji">🔥</div>
<div class="emoji">💥</div>
<div class="emoji">✨</div>
<div class="emoji">🎶</div>
<div class="emoji">💫</div>
<div class="emoji">🎊</div>
<div class="emoji">🎇</div>
<div class="emoji">💖</div>

<!-- Bubbles -->
<div class="bubble"></div>
<div class="bubble"></div>
<div class="bubble"></div>
<div class="bubble"></div>
<div class="bubble"></div>
<div class="bubble"></div>
<div class="bubble"></div>
<div class="bubble"></div>
<div class="bubble"></div>
<div class="bubble"></div>

<!-- Confetti -->
<div class="confetti"></div>
<div class="confetti"></div>
<div class="confetti"></div>
<div class="confetti"></div>
<div class="confetti"></div>
<div class="confetti"></div>
<div class="confetti"></div>
<div class="confetti"></div>
<div class="confetti"></div>
<div class="confetti"></div>

<footer>Made with 💥 by <b>Idris</b></footer>

</body>
</html>
