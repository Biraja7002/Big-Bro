# Big-Bro
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>For My Big Brother — 05.11.2026</title>

<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>

/* =====================================================
   VARIABLES
===================================================== */

:root{
  --black:#030303;
  --black2:#080708;
  --burgundy:#210b10;
  --burgundy2:#351018;

  --gold:#d7b36a;
  --gold2:#f0d99b;

  --cream:#eee4d0;
  --text:#c1b8aa;
  --muted:#766e64;

  --line:rgba(215,179,106,.22);
}


/* =====================================================
   RESET
===================================================== */

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

html{
  scroll-behavior:smooth;
}

body{
  background:var(--black);
  color:var(--cream);
  font-family:"DM Sans",sans-serif;
  overflow-x:hidden;
}

body.locked{
  overflow:hidden;
}

button{
  font-family:inherit;
}


/* =====================================================
   GLOBAL
===================================================== */

section{
  min-height:100vh;
  position:relative;

  display:flex;
  align-items:center;
  justify-content:center;

  padding:100px 7%;

  overflow:hidden;
}

.container{
  width:min(1100px,100%);
  margin:auto;
}

.eyebrow{
  color:var(--gold);

  font-size:10px;
  letter-spacing:5px;

  text-transform:uppercase;

  margin-bottom:20px;
}

h1,
h2,
h3{
  font-family:"Cormorant Garamond",serif;
  font-weight:500;
}

h2{
  font-size:clamp(45px,7vw,82px);
  line-height:.9;
}

p{
  color:var(--text);
  line-height:1.8;
}

.gold{
  color:var(--gold2);
}


/* =====================================================
   MUSIC PLAYER
   THIS IS ALWAYS UNLOCKED
===================================================== */

.music-player{

  position:relative;

  z-index:10001;

  width:min(720px,92%);

  margin:18px auto 0;

  padding:15px 18px;

  display:flex;
  align-items:center;
  justify-content:space-between;

  gap:20px;

  background:
    linear-gradient(
      120deg,
      rgba(255,255,255,.045),
      rgba(215,179,106,.025)
    );

  border:1px solid var(--line);

  backdrop-filter:blur(18px);

  box-shadow:
    0 15px 60px rgba(0,0,0,.5);
}

.music-info{
  display:flex;
  align-items:center;
  gap:13px;
}

.music-disc{

  width:40px;
  height:40px;

  flex-shrink:0;

  border-radius:50%;

  border:1px solid rgba(215,179,106,.6);

  display:flex;
  align-items:center;
  justify-content:center;

  animation:discSpin 5s linear infinite;

  animation-play-state:paused;
}

.music-disc::before{
  content:"";

  position:absolute;

  width:27px;
  height:27px;

  border:1px solid rgba(215,179,106,.25);

  border-radius:50%;
}

.music-disc span{

  width:8px;
  height:8px;

  border-radius:50%;

  background:var(--gold);

  box-shadow:
    0 0 18px rgba(215,179,106,.5);
}

.music-label{

  color:#777067;

  font-size:7px;

  letter-spacing:3px;
}

.music-title{

  margin-top:3px;

  font-family:"Cormorant Garamond",serif;

  font-size:20px;

  color:var(--gold2);
}

.music-player button{

  padding:10px 21px;

  border:1px solid var(--gold);

  background:transparent;

  color:var(--gold2);

  font-size:8px;

  letter-spacing:3px;

  cursor:pointer;

  transition:.35s ease;
}

.music-player button:hover{

  background:var(--gold);

  color:#050505;
}

@keyframes discSpin{

  to{
    transform:rotate(360deg);
  }
}


/* =====================================================
   LOCK SCREEN
===================================================== */

#lockScreen{

  position:fixed;

  inset:0;

  z-index:9999;

  overflow-y:auto;

  padding-top:15px;

  background:

    radial-gradient(
      circle at 50% 45%,
      rgba(85,24,35,.38),
      transparent 35%
    ),

    radial-gradient(
      circle at 50% 100%,
      rgba(215,179,106,.07),
      transparent 45%
    ),

    #030303;

  transition:

    opacity 1.5s ease,

    visibility 1.5s ease;
}

#lockScreen::before{

  content:"";

  position:absolute;

  inset:0;

  opacity:.06;

  background-image:

    linear-gradient(
      rgba(255,255,255,.2) 1px,
      transparent 1px
    ),

    linear-gradient(
      90deg,
      rgba(255,255,255,.2) 1px,
      transparent 1px
    );

  background-size:60px 60px;

  mask-image:
    radial-gradient(
      circle,
      black,
      transparent 75%
    );
}

#lockScreen::after{

  content:"";

  position:absolute;

  left:50%;
  top:50%;

  width:20px;
  height:20px;

  transform:translate(-50%,-50%);

  border-radius:50%;

  background:var(--gold2);

  box-shadow:

    0 0 70px 30px rgba(215,179,106,.1),

    0 0 180px 70px rgba(215,179,106,.04);

  opacity:.25;

  animation:pulseLight 4s ease-in-out infinite;
}

.lock-content{

  position:relative;

  z-index:2;

  width:min(900px,92%);

  margin:0 auto;

  padding-bottom:50px;

  text-align:center;
}

.lock-label{

  margin-top:28px;

  color:var(--gold);

  font-size:9px;

  letter-spacing:6px;

  text-transform:uppercase;
}


/* LOCK ICON */

.lock-icon{

  width:72px;
  height:72px;

  margin:30px auto 35px;

  position:relative;
}

.lock-body{

  position:absolute;

  left:13px;
  bottom:3px;

  width:46px;
  height:39px;

  border:1px solid var(--gold);

  background:rgba(215,179,106,.04);
}

.lock-body::after{

  content:"";

  position:absolute;

  left:20px;
  top:13px;

  width:5px;
  height:12px;

  background:var(--gold);
}

.lock-shackle{

  position:absolute;

  left:24px;
  top:0;

  width:25px;
  height:34px;

  border:2px solid var(--gold);

  border-bottom:0;

  border-radius:15px 15px 0 0;
}


/* LOCK TITLE */

.lock-title{

  font-family:"Cormorant Garamond",serif;

  font-size:clamp(52px,9vw,105px);

  line-height:.8;

  letter-spacing:-2px;
}

.lock-subtitle{

  margin-top:25px;

  color:#9b9286;

  font-size:10px;

  letter-spacing:4px;

  text-transform:uppercase;
}


/* COUNTDOWN */

.countdown{

  display:flex;

  justify-content:center;

  gap:12px;

  margin:55px auto 35px;
}

.time-box{

  width:115px;

  padding:22px 10px;

  border:1px solid var(--line);

  background:rgba(255,255,255,.015);

  backdrop-filter:blur(10px);
}

.time-number{

  display:block;

  color:var(--gold2);

  font-family:"Cormorant Garamond",serif;

  font-size:48px;

  line-height:1;
}

.time-name{

  display:block;

  margin-top:9px;

  color:#81786c;

  font-size:8px;

  letter-spacing:3px;

  text-transform:uppercase;
}

.unlock-date{

  color:#70695f;

  font-size:9px;

  letter-spacing:4px;

  text-transform:uppercase;
}

.locked-message{

  margin-top:28px;

  color:#756d63;

  font-size:10px;

  letter-spacing:2px;
}


/* LOCK DISAPPEARS */

#lockScreen.unlocked{

  opacity:0;

  visibility:hidden;

  pointer-events:none;
}


/* =====================================================
   BIRTHDAY CONTENT
===================================================== */

#birthdayContent{

  opacity:.08;

  filter:blur(12px);

  pointer-events:none;

  transition:

    opacity 2s ease,

    filter 2s ease;
}

body.unlocked #birthdayContent{

  opacity:1;

  filter:none;

  pointer-events:auto;
}


/* =====================================================
   HERO
===================================================== */

.hero{

  background:

    radial-gradient(
      circle at 50% 50%,
      rgba(74,18,28,.36),
      transparent 45%
    ),

    linear-gradient(
      180deg,
      #060506,
      #100609 55%,
      #050505
    );
}

.hero::before{

  content:"";

  position:absolute;

  width:500px;
  height:500px;

  border-radius:50%;

  background:rgba(215,179,106,.045);

  filter:blur(110px);
}

.hero-content{

  position:relative;

  z-index:2;

  text-align:center;
}

.hero-small{

  color:var(--gold);

  font-size:10px;

  letter-spacing:7px;
}

.hero h1{

  margin:25px 0;

  font-size:clamp(65px,12vw,150px);

  line-height:.78;
}

.hero h1 span{

  display:block;

  color:var(--gold2);
}

.hero-description{

  max-width:600px;

  margin:auto;

  font-size:14px;
}

.scroll-line{

  margin-top:70px;

  color:#777067;

  font-size:9px;

  letter-spacing:5px;
}

.scroll-line::after{

  content:"";

  display:block;

  width:1px;
  height:55px;

  margin:14px auto 0;

  background:
    linear-gradient(
      var(--gold),
      transparent
    );
}


/* =====================================================
   TIMELINE
===================================================== */

.timeline-section{
  background:#070607;
}

.timeline{

  position:relative;

  margin-top:65px;
}

.timeline::before{

  content:"";

  position:absolute;

  left:50%;
  top:0;
  bottom:0;

  width:1px;

  background:
    linear-gradient(
      transparent,
      var(--line),
      var(--line),
      transparent
    );
}

.timeline-item{

  width:50%;

  padding:25px 55px;

  position:relative;
}

.timeline-item:nth-child(even){

  margin-left:50%;
}

.timeline-dot{

  position:absolute;

  width:9px;
  height:9px;

  border:1px solid var(--gold);

  border-radius:50%;

  top:39px;

  background:var(--black);
}

.timeline-item:nth-child(odd)
.timeline-dot{

  right:-5px;
}

.timeline-item:nth-child(even)
.timeline-dot{

  left:-5px;
}

.timeline-year{

  color:var(--gold);

  font-size:9px;

  letter-spacing:4px;
}

.timeline-item h3{

  margin:10px 0;

  font-size:35px;
}


/* =====================================================
   BROTHER CODE
===================================================== */

.code-section{

  background:
    linear-gradient(
      120deg,
      #070607,
      #18080c,
      #070607
    );
}

.code-grid{

  display:grid;

  grid-template-columns:
    repeat(4,1fr);

  gap:15px;

  margin-top:60px;
}

.code-card{

  min-height:250px;

  padding:30px 22px;

  border:1px solid var(--line);

  background:rgba(255,255,255,.015);

  cursor:pointer;

  transition:.5s ease;
}

.code-card:hover{

  transform:translateY(-8px);

  border-color:
    rgba(215,179,106,.55);

  background:
    rgba(215,179,106,.035);
}

.code-number{

  color:var(--gold);

  font-size:9px;

  letter-spacing:3px;
}

.code-card h3{

  margin:45px 0 15px;

  font-size:32px;
}

.code-card p{

  font-size:12px;
}


/* =====================================================
   LETTER
===================================================== */

.letter-section{
  background:#090708;
}

.letter-box{

  max-width:750px;

  margin:60px auto 0;

  padding:60px;

  border:1px solid var(--line);

  background:
    linear-gradient(
      145deg,
      rgba(255,255,255,.025),
      rgba(255,255,255,.005)
    );

  position:relative;
}

.letter-box::before{

  content:"";

  position:absolute;

  inset:10px;

  border:
    1px solid
    rgba(215,179,106,.07);

  pointer-events:none;
}

.letter-top{

  display:flex;

  justify-content:space-between;

  margin-bottom:45px;

  color:#776f65;

  font-size:8px;

  letter-spacing:3px;
}

.letter-box h3{

  margin-bottom:30px;

  font-size:42px;
}

.letter-box p{

  color:#d3c8b7;

  font-family:"Cormorant Garamond",serif;

  font-size:22px;

  line-height:1.7;
}


/* =====================================================
   CHALLENGE
===================================================== */

.challenge-section{

  background:

    radial-gradient(
      circle at 50% 50%,
      rgba(61,15,24,.35),
      transparent 45%
    ),

    #060506;
}

.challenge{

  max-width:650px;

  margin:60px auto 0;

  text-align:center;
}

.challenge-question{

  margin-bottom:35px;

  font-family:"Cormorant Garamond",serif;

  font-size:38px;
}

.challenge-buttons{

  display:flex;

  justify-content:center;

  gap:12px;

  flex-wrap:wrap;
}

.challenge-btn{

  padding:14px 28px;

  border:1px solid var(--line);

  background:transparent;

  color:#cfc5b5;

  cursor:pointer;

  font-size:9px;

  letter-spacing:2px;

  text-transform:uppercase;

  transition:.4s;
}

.challenge-btn:hover,
.challenge-btn.active{

  background:var(--gold);

  color:#090707;
}

.challenge-result{

  min-height:35px;

  margin-top:35px;

  color:var(--gold2);

  font-family:"Cormorant Garamond",serif;

  font-size:25px;
}


/* =====================================================
   APPRECIATION
===================================================== */

.appreciation{
  background:#080708;
}

.appreciation-grid{

  display:grid;

  grid-template-columns:
    repeat(3,1fr);

  gap:20px;

  margin-top:60px;
}

.app-card{

  min-height:220px;

  padding:38px 30px;

  border-top:1px solid var(--line);

  background:
    linear-gradient(
      180deg,
      rgba(215,179,106,.025),
      transparent
    );
}

.app-card span{

  color:var(--gold);

  font-family:"Cormorant Garamond",serif;

  font-size:48px;
}

.app-card h3{

  margin:18px 0 12px;

  font-size:27px;
}


/* =====================================================
   SECRET VAULT
===================================================== */

.vault-section{

  background:
    linear-gradient(
      180deg,
      #080708,
      #14070b,
      #080708
    );
}

.vault{

  width:min(650px,100%);

  text-align:center;
}

.vault-lock{

  width:90px;
  height:90px;

  margin:0 auto 35px;

  border:1px solid var(--line);

  display:flex;

  align-items:center;

  justify-content:center;

  position:relative;
}

.vault-lock::before{

  content:"";

  width:35px;
  height:30px;

  border:1px solid var(--gold);
}

.vault-lock::after{

  content:"";

  position:absolute;

  width:18px;
  height:24px;

  top:20px;

  border:1px solid var(--gold);

  border-bottom:0;

  border-radius:
    12px 12px 0 0;
}

.vault button{

  margin-top:35px;

  padding:15px 35px;

  border:1px solid var(--gold);

  background:transparent;

  color:var(--gold2);

  font-size:9px;

  letter-spacing:3px;

  cursor:pointer;

  transition:.4s;
}

.vault button:hover{

  background:var(--gold);

  color:#050505;
}

.vault-message{

  min-height:45px;

  margin-top:35px;

  color:var(--gold2);

  font-family:"Cormorant Garamond",serif;

  font-size:28px;
}


/* =====================================================
   FINAL
===================================================== */

.final{

  min-height:100vh;

  background:

    radial-gradient(
      circle at 50% 40%,
      rgba(73,21,30,.4),
      transparent 40%
    ),

    #030303;

  text-align:center;
}

.stars{

  position:absolute;

  inset:0;

  overflow:hidden;
}

.star{

  position:absolute;

  width:2px;
  height:2px;

  background:#e8d5a6;

  border-radius:50%;

  opacity:.45;

  animation:
    twinkle
    3s
    infinite
    alternate;
}

.final-content{

  position:relative;

  z-index:2;
}

.final-small{

  color:var(--gold);

  font-size:9px;

  letter-spacing:6px;
}

.final h2{

  margin:25px 0;

  font-size:
    clamp(65px,11vw,135px);
}

.final h2 span{

  color:var(--gold2);
}

.final p{

  max-width:580px;

  margin:auto;

  font-family:"Cormorant Garamond",serif;

  font-size:25px;
}

.signature{

  margin-top:55px;

  color:#766d62;

  font-size:8px;

  letter-spacing:4px;

  text-transform:uppercase;
}


/* =====================================================
   PARTICLES
===================================================== */

.particle{

  position:fixed;

  width:2px;
  height:2px;

  background:var(--gold);

  border-radius:50%;

  opacity:.25;

  pointer-events:none;

  z-index:100;

  animation:
    floatUp
    linear
    infinite;
}


/* =====================================================
   ANIMATIONS
===================================================== */

@keyframes pulseLight{

  0%,100%{
    transform:translate(-50%,-50%) scale(.7);
    opacity:.15;
  }

  50%{
    transform:translate(-50%,-50%) scale(1.2);
    opacity:.4;
  }
}

@keyframes twinkle{

  from{
    opacity:.15;
    transform:scale(.7);
  }

  to{
    opacity:.8;
    transform:scale(1.4);
  }
}

@keyframes floatUp{

  from{
    transform:translateY(100vh);
    opacity:0;
  }

  15%{
    opacity:.3;
  }

  85%{
    opacity:.3;
  }

  to{
    transform:translateY(-10vh);
    opacity:0;
  }
}


/* =====================================================
   MOBILE
===================================================== */

@media(max-width:800px){

  section{
    padding:85px 6%;
  }

  .countdown{
    gap:6px;
  }

  .time-box{

    width:72px;

    padding:15px 5px;
  }

  .time-number{
    font-size:32px;
  }

  .time-name{

    font-size:7px;

    letter-spacing:2px;
  }

  .lock-title{
    font-size:58px;
  }

  .lock-subtitle{

    font-size:8px;

    letter-spacing:2.5px;
  }

  .timeline::before{
    left:8px;
  }

  .timeline-item,
  .timeline-item:nth-child(even){

    width:100%;

    margin-left:0;

    padding:
      25px
      10px
      25px
      40px;
  }

  .timeline-item:nth-child(odd)
  .timeline-dot,
  .timeline-item:nth-child(even)
  .timeline-dot{

    left:4px;

    right:auto;
  }

  .code-grid{

    grid-template-columns:
      1fr 1fr;
  }

  .appreciation-grid{

    grid-template-columns:1fr;
  }

  .letter-box{

    padding:35px 25px;
  }

  .letter-box p{
    font-size:19px;
  }
}

@media(max-width:500px){

  .music-player{

    margin-top:10px;

    padding:11px 12px;
  }

  .music-disc{

    width:35px;
    height:35px;
  }

  .music-title{
    font-size:17px;
  }

  .music-player button{

    padding:9px 13px;

    font-size:7px;
  }

  .code-grid{
    grid-template-columns:1fr;
  }

  .lock-title{
    font-size:48px;
  }

  .time-box{
    width:67px;
  }

  .time-number{
    font-size:28px;
  }

  .hero h1{
    font-size:72px;
  }
}

</style>
</head>


<body class="locked">


<!-- =====================================================
     ALWAYS-UNLOCKED MUSIC
===================================================== -->

<div class="music-player">

  <div class="music-info">

    <div class="music-disc">
      <span></span>
    </div>

    <div>

      <div class="music-label">
        NOW PLAYING
      </div>

      <div class="music-title">
        Tera Naam Doon
      </div>

    </div>

  </div>


  <button
    id="musicButton"
    onclick="toggleMusic()">

    PLAY

  </button>


  <audio
    id="birthdaySong"
    preload="auto">

    <source
      src="tera naam doon.mp3"
      type="audio/mpeg">

  </audio>

</div>



<!-- =====================================================
     LOCKED COUNTDOWN
===================================================== -->

<div id="lockScreen">

  <div class="lock-content">

    <div class="lock-label">
      PRIVATE BIRTHDAY ROOM
    </div>


    <div class="lock-icon">

      <div class="lock-shackle"></div>

      <div class="lock-body"></div>

    </div>


    <div class="lock-title">
      BIG BROTHER
    </div>


    <div class="lock-subtitle">
      The birthday room is currently locked
    </div>


    <div class="countdown">

      <div class="time-box">

        <span
          class="time-number"
          id="days">
          00
        </span>

        <span class="time-name">
          Days
        </span>

      </div>


      <div class="time-box">

        <span
          class="time-number"
          id="hours">
          00
        </span>

        <span class="time-name">
          Hours
        </span>

      </div>


      <div class="time-box">

        <span
          class="time-number"
          id="minutes">
          00
        </span>

        <span class="time-name">
          Minutes
        </span>

      </div>


      <div class="time-box">

        <span
          class="time-number"
          id="seconds">
          00
        </span>

        <span class="time-name">
          Seconds
        </span>

      </div>

    </div>


    <div class="unlock-date">

      Unlocks —
      05 November 2026 · 00:00 IST

    </div>


    <div class="locked-message">

      SOME THINGS ARE WORTH WAITING FOR.

    </div>

  </div>

</div>



<!-- =====================================================
     BIRTHDAY CONTENT
===================================================== -->

<main id="birthdayContent">


<!-- =====================================================
     HERO
===================================================== -->

<section class="hero">

  <div class="hero-content">

    <div class="hero-small">
      05 · 11 · 2026
    </div>


    <h1>

      FOR MY

      <span>
        BIG BROTHER
      </span>

    </h1>


    <p class="hero-description">

      Not just my brother.

      A built-in protector,
      occasional headache,
      permanent teammate,
      and one of the people
      who will always have a place
      in my story.

    </p>


    <div class="scroll-line">
      ENTER THE STORY
    </div>

  </div>

</section>



<!-- =====================================================
     TIMELINE
===================================================== -->

<section class="timeline-section">

  <div class="container">

    <div class="eyebrow">
      THE STORY
    </div>


    <h2>

      Years of

      <br>

      <span class="gold">
        Brotherhood.
      </span>

    </h2>


    <div class="timeline">


      <div class="timeline-item">

        <div class="timeline-dot"></div>

        <div class="timeline-year">
          CHAPTER 01
        </div>

        <h3>
          The Beginning
        </h3>

        <p>
          Before either of us understood
          what brotherhood really meant,
          the story had already started.
        </p>

      </div>


      <div class="timeline-item">

        <div class="timeline-dot"></div>

        <div class="timeline-year">
          CHAPTER 02
        </div>

        <h3>
          The Lessons
        </h3>

        <p>
          The advice, arguments, jokes
          and moments that slowly became
          part of growing up together.
        </p>

      </div>


      <div class="timeline-item">

        <div class="timeline-dot"></div>

        <div class="timeline-year">
          CHAPTER 03
        </div>

        <h3>
          The Chaos
        </h3>

        <p>
          Because no proper brotherhood
          is complete without a little
          competition and absolute chaos.
        </p>

      </div>


      <div class="timeline-item">

        <div class="timeline-dot"></div>

        <div class="timeline-year">
          CHAPTER 04
        </div>

        <h3>
          Still Here
        </h3>

        <p>
          Different ages.
          Different lives.
          Same brotherhood.
        </p>

      </div>


    </div>

  </div>

</section>



<!-- =====================================================
     BROTHER CODE
===================================================== -->

<section class="code-section">

  <div class="container">

    <div class="eyebrow">
      THE BROTHER CODE
    </div>


    <h2>

      Things that

      <br>

      <span class="gold">
        never change.
      </span>

    </h2>


    <div class="code-grid">


      <div class="code-card">

        <div class="code-number">
          01
        </div>

        <h3>
          BACKUP
        </h3>

        <p>
          Even when the world gets
          complicated, brothers are
          supposed to have each
          other's back.
        </p>

      </div>


      <div class="code-card">

        <div class="code-number">
          02
        </div>

        <h3>
          ROAST
        </h3>

        <p>
          Respectfully annoying
          each other is,
          unfortunately,
          part of the contract.
        </p>

      </div>


      <div class="code-card">

        <div class="code-number">
          03
        </div>

        <h3>
          ADVICE
        </h3>

        <p>
          Sometimes asked for.
          Sometimes absolutely
          not asked for.
          Still somehow delivered.
        </p>

      </div>


      <div class="code-card">

        <div class="code-number">
          04
        </div>

        <h3>
          LOYALTY
        </h3>

        <p>
          Years can change almost
          everything.
          Brotherhood isn't one
          of them.
        </p>

      </div>


    </div>

  </div>

</section>



<!-- =====================================================
     LETTER
===================================================== -->

<section class="letter-section">

  <div class="container">

    <div class="eyebrow">
      A LETTER
    </div>


    <h2>

      From your

      <br>

      <span class="gold">
        younger brother.
      </span>

    </h2>


    <div class="letter-box">


      <div class="letter-top">

        <span>
          PRIVATE NOTE
        </span>

        <span>
          05.11.2026
        </span>

      </div>


      <h3>
        Dear Big Brother,
      </h3>


      <p>

        Happy Birthday.

        <br><br>

        We may not always say everything
        out loud, but I hope you know that
        having you as my big brother is
        something I genuinely value.

        <br><br>

        We've shared arguments, jokes,
        random moments, advice, and
        probably more chaos than necessary.

        But somewhere inside all of that
        is something simple —

        you're my brother,
        and that will never change.

        <br><br>

        I hope this year brings you
        bigger opportunities,
        good health, peace of mind,
        and plenty of reasons to be
        proud of yourself.

        <br><br>

        Happy Birthday, Bhai.

        <br><br>

        Keep moving forward.

        I'll always be somewhere
        in your corner.

      </p>

    </div>

  </div>

</section>



<!-- =====================================================
     BROTHER CHALLENGE
===================================================== -->

<section class="challenge-section">

  <div class="container">

    <div class="eyebrow">
      BROTHER TEST
    </div>


    <h2>

      One question.

      <br>

      <span class="gold">
        Choose carefully.
      </span>

    </h2>


    <div class="challenge">


      <div class="challenge-question">

        Who has the final authority
        in the brotherhood?

      </div>


      <div class="challenge-buttons">


        <button
          class="challenge-btn"
          onclick="
          answer(
            this,
            'Obviously the big brother.'
          )">

          Big Brother

        </button>


        <button
          class="challenge-btn"
          onclick="
          answer(
            this,
            'Nice try. That answer is suspicious.'
          )">

          Me

        </button>


        <button
          class="challenge-btn"
          onclick="
          answer(
            this,
            'Diplomatic answer. Respect.'
          )">

          Both

        </button>


      </div>


      <div
        class="challenge-result"
        id="challengeResult">
      </div>


    </div>

  </div>

</section>



<!-- =====================================================
     APPRECIATION
===================================================== -->

<section class="appreciation">

  <div class="container">

    <div class="eyebrow">
      RESPECT
    </div>


    <h2>

      Things I

      <br>

      <span class="gold">
        appreciate.
      </span>

    </h2>


    <div class="appreciation-grid">


      <div class="app-card">

        <span>
          01
        </span>

        <h3>
          Your Guidance
        </h3>

        <p>
          For the moments when a little
          advice was exactly what was needed.
        </p>

      </div>


      <div class="app-card">

        <span>
          02
        </span>

        <h3>
          Your Strength
        </h3>

        <p>
          For showing what it means to
          keep moving forward when things
          aren't easy.
        </p>

      </div>


      <div class="app-card">

        <span>
          03
        </span>

        <h3>
          Your Presence
        </h3>

        <p>
          Sometimes the biggest support
          is simply knowing someone is there.
        </p>

      </div>


    </div>

  </div>

</section>



<!-- =====================================================
     SECRET VAULT
===================================================== -->

<section class="vault-section">

  <div class="container">

    <div class="vault">


      <div class="eyebrow">
        CLASSIFIED
      </div>


      <div class="vault-lock"></div>


      <h2>

        Brother's

        <br>

        <span class="gold">
          Vault.
        </span>

      </h2>


      <p>
        One final message is hidden inside.
      </p>


      <button
        onclick="openVault()">

        OPEN THE VAULT

      </button>


      <div
        class="vault-message"
        id="vaultMessage">
      </div>


    </div>

  </div>

</section>



<!-- =====================================================
     FINAL
===================================================== -->

<section class="final">

  <div
    class="stars"
    id="stars">
  </div>


  <div class="final-content">


    <div class="final-small">

      05 · NOVEMBER · 2026

    </div>


    <h2>

      HAPPY

      <br>

      <span>
        BIRTHDAY.
      </span>

    </h2>


    <p>

      No matter how much we grow,
      how much life changes,
      or how many years pass —

      you'll always be my big brother.

    </p>


    <div class="signature">

      Made especially for my big brother

    </div>


  </div>

</section>


</main>



<script>

/* =====================================================
   MUSIC
===================================================== */

const birthdaySong =
  document.getElementById("birthdaySong");

const musicButton =
  document.getElementById("musicButton");

const musicDisc =
  document.querySelector(".music-disc");


function toggleMusic(){

  if(birthdaySong.paused){

    birthdaySong
      .play()
      .then(()=>{

        musicButton.textContent =
          "PAUSE";

        musicDisc.style.animationPlayState =
          "running";

      })
      .catch(()=>{

        musicButton.textContent =
          "PLAY";

      });

  }

  else{

    birthdaySong.pause();

    musicButton.textContent =
      "PLAY";

    musicDisc.style.animationPlayState =
      "paused";

  }

}


birthdaySong.addEventListener(
  "ended",
  ()=>{

    musicButton.textContent =
      "PLAY";

    musicDisc.style.animationPlayState =
      "paused";

  }
);


/* =====================================================
   COUNTDOWN
===================================================== */

/*
   IMPORTANT:

   5 November 2026
   12:00 AM
   India Standard Time

   TEST_UNLOCK = true
   lets you preview the unlocked website.
*/

const TARGET_DATE =
  new Date(
    "2026-11-05T00:00:00+05:30"
  ).getTime();


const TEST_UNLOCK =
