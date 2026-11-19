# Proposal-<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Un-clickable NO ❤️</title>
<meta name="theme-color" content="#ffd6e7">
<style>
/* ===== THEME TOKENS ===== */
:root{
  --bg1:#ffe3ee; --bg2:#ffc2d9; --card:rgba(255,255,255,.86); --text:#4a2336; --muted:#8a5a70;
  --accent:#ff4d88; --accent2:#ff7aa8; --shadow:0 20px 50px rgba(255,77,136,.25); --line:#ffd0e2;
  --btn-no:#fff; --btn-no-text:#a0486a;
}
:root[data-theme="dark"]{
  --bg1:#2a1238; --bg2:#4a1d4f; --card:rgba(52,24,66,.82); --text:#ffe9f3; --muted:#d9a9c4;
  --accent:#ff6fa5; --accent2:#c067ff; --shadow:0 20px 50px rgba(0,0,0,.45); --line:#6b3a78;
  --btn-no:#3d1f4d; --btn-no-text:#ffc9df;
}
*{box-sizing:border-box;margin:0}
*{-webkit-user-select:none;user-select:none;-webkit-touch-callout:none}
img,svg{-webkit-user-drag:none;user-drag:none}
input,textarea{-webkit-user-select:text;user-select:text;-webkit-touch-callout:default}
html{scroll-behavior:smooth}
body{
  min-height:100vh;min-height:100dvh;color:var(--text);
  font-family:ui-rounded,"Hiragino Maru Gothic ProN","Nunito","Segoe UI",system-ui,sans-serif;
  background:linear-gradient(160deg,var(--bg1),var(--bg2));background-attachment:fixed;
  transition:background .5s,color .5s;overflow-x:hidden;
  padding:max(16px,env(safe-area-inset-top)) 16px max(16px,env(safe-area-inset-bottom));
  display:flex;flex-direction:column;align-items:center;
}
h1,h2{font-family:Georgia,"Times New Roman",serif;font-weight:700;line-height:1.2}
button{font:inherit;cursor:pointer;border:0;color:inherit;-webkit-tap-highlight-color:transparent}
button:focus-visible{outline:3px solid var(--accent);outline-offset:3px}

/* ===== TOP BAR ===== */
.bar{width:100%;max-width:520px;display:flex;justify-content:flex-end;gap:8px;margin-bottom:8px;z-index:5}
.chip{min-height:44px;min-width:44px;padding:0 14px;border-radius:22px;background:var(--card);
  box-shadow:0 4px 14px rgba(255,77,136,.18);backdrop-filter:blur(8px);-webkit-backdrop-filter:blur(8px);font-size:.9rem;transition:transform .2s}
.chip:hover:not(:disabled){transform:translateY(-2px)}
.chip:disabled{opacity:.55;cursor:not-allowed}

/* ===== CARD ===== */
.card{
  position:relative;width:100%;max-width:520px;background:var(--card);border-radius:32px;
  padding:20px 18px 18px;text-align:center;box-shadow:var(--shadow);
  backdrop-filter:blur(10px);-webkit-backdrop-filter:blur(10px);border:1px solid var(--line);
  transition:background .5s;z-index:2;
}
.hidden{display:none!important}
.screen{animation:fadeIn .6s ease both}
@keyframes fadeIn{from{opacity:0;transform:translateY(14px) scale(.98)}to{opacity:1;transform:none}}
.eyebrow{color:var(--text);font:700 1.2rem Georgia,serif;margin-bottom:2px}
.q{font-size:clamp(1.7rem,7vw,2.3rem);color:var(--accent);margin:2px 0 14px}
.sub{color:var(--muted);margin-bottom:12px;font-size:.98rem}
.catwrap{position:relative;z-index:1;width:150px;margin:0 auto 2px;touch-action:manipulation}
.cat{width:150px;height:auto;display:block;overflow:visible;pointer-events:none}
.hit{pointer-events:visiblePainted;cursor:pointer}
.cat *{-webkit-tap-highlight-color:transparent}
.pop{position:absolute;top:10%;font-size:1.4rem;pointer-events:none;animation:floatUp 1.3s ease-out forwards}
@keyframes floatUp{0%{transform:translateY(0) scale(.6);opacity:0}20%{opacity:1}100%{transform:translateY(-60px) scale(1.2);opacity:0}}

/* ----- living cat: transform-only animations (cheap on phones) ----- */
.breathe{transform-origin:100px 232px;animation:breathe 3.4s ease-in-out infinite}
@keyframes breathe{50%{transform:scale(1.02,1.035)}}
.headBob{animation:hbob 3.4s ease-in-out infinite}
@keyframes hbob{50%{transform:translateY(-1.6px)}}
.tailIdle{transform-origin:148px 212px;animation:swing 2.8s ease-in-out infinite}
@keyframes swing{0%,100%{transform:rotate(-7deg)}50%{transform:rotate(9deg)}}
.tail{transform-origin:148px 212px}
.tailTip{transform-origin:186px 168px;animation:tip 2.8s ease-in-out -.45s infinite}
@keyframes tip{0%,100%{transform:rotate(7deg)}50%{transform:rotate(-11deg)}}
.tail.zoom{animation:wag .42s ease-in-out 3}
.tail.wag{animation:wag .9s ease-in-out}
@keyframes wag{0%,100%{transform:rotate(0)}15%{transform:rotate(-24deg)}35%{transform:rotate(22deg)}55%{transform:rotate(-20deg)}75%{transform:rotate(16deg)}}
.tail.fluff{animation:fluff .8s ease-out}
@keyframes fluff{30%{transform:scale(1.3) rotate(-10deg)}100%{transform:none}}
.tail.curl{animation:curl 1s ease-in-out}
@keyframes curl{40%{transform:rotate(-38deg) scale(.92)}70%{transform:rotate(-30deg) scale(.92)}}
.ear{transition:none}
.earL{transform-origin:66px 55px}.earR{transform-origin:134px 55px}
.earL.twitch{animation:twL .4s}.earR.twitch{animation:twR .4s}
@keyframes twL{30%{transform:rotate(-14deg)}60%{transform:rotate(6deg)}}
@keyframes twR{30%{transform:rotate(14deg)}60%{transform:rotate(-6deg)}}
#headT{transform-origin:100px 150px;transition:transform .5s ease}
#headT.tilt-l{transform:rotate(-6deg)}#headT.tilt-r{transform:rotate(6deg)}
#headT.purr{animation:purr .9s ease-in-out}
@keyframes purr{0%,100%{transform:none}15%{transform:rotate(-3deg) translateY(2px)}30%{transform:rotate(3deg)}45%{transform:rotate(-3deg) translateY(2px)}60%{transform:rotate(3deg)}80%{transform:rotate(-2deg)}}
#all{transform-origin:100px 190px}
#all.jump{animation:jump .7s ease-out}
@keyframes jump{30%{transform:translateY(-24px) scale(.96,1.05)}60%{transform:translateY(0) scale(1.06,.92)}80%{transform:scale(.99,1.02)}}
#all.wiggle{animation:wiggle .7s ease-in-out}
@keyframes wiggle{20%{transform:rotate(-8deg)}40%{transform:rotate(8deg)}60%{transform:rotate(-6deg)}80%{transform:rotate(5deg)}}
#all.squish{animation:squish .6s ease-out}
@keyframes squish{30%{transform:scale(1.1,.86)}60%{transform:scale(.94,1.07)}}
#all.spin{animation:spin .8s ease-in-out}
@keyframes spin{50%{transform:rotate(180deg) scale(.8)}to{transform:rotate(360deg)}}
#all.hop{animation:hop .8s ease-out}
@keyframes hop{25%{transform:translateY(-16px)}45%{transform:translateY(0) scale(1.04,.96)}65%{transform:translateY(-10px)}85%{transform:translateY(0) scale(1.02,.98)}}
#all.stretch{animation:stretch 1.5s ease-in-out}
@keyframes stretch{35%{transform:scale(.96,1.08) translateY(-3px)}70%{transform:scale(1.05,.95)}}
#headT.nuzzle{animation:nuzzle .8s ease-in-out}
@keyframes nuzzle{30%{transform:rotate(-8deg) translate(-4px,3px)}60%{transform:rotate(8deg) translate(4px,3px)}}
#headT.nod{animation:nod 1.1s ease-in-out}
@keyframes nod{30%{transform:rotate(4deg) translateY(4px)}60%{transform:rotate(-3deg) translateY(1px)}}
.whisk{transform-origin:100px 118px}
.whisk.wiggle{animation:whisk .6s ease-in-out}
@keyframes whisk{20%{transform:rotate(3deg)}50%{transform:rotate(-2.5deg)}80%{transform:rotate(1deg)}}
.nose{transform-origin:100px 112px}
.nose.sniff{animation:sniff .5s ease-in-out}
@keyframes sniff{30%{transform:scale(1.2,.88)}60%{transform:scale(.94,1.06)}}
.eyes{transform-box:fill-box;transform-origin:center;transition:transform .07s}
.cat.blink .eyes{transform:scaleY(.08)}
.pup{transition:transform .25s ease-out;transform:translate(calc(var(--lx,0)*1px + var(--px,0)*1px),calc(var(--py,0)*1px))}

/* ===== BUTTONS ===== */
.btns{position:relative;z-index:3;display:flex;gap:12px;justify-content:center;align-items:center;flex-wrap:wrap;min-height:56px}
.say{position:relative;z-index:3;min-height:1.3em;margin-top:8px;font-weight:600;color:var(--accent);transition:opacity .3s}
.btn{min-height:52px;padding:0 28px;border-radius:30px;font-size:1.1rem;font-weight:700;transition:transform .2s,box-shadow .2s}
.yes{background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff;
  box-shadow:0 10px 24px rgba(255,77,136,.45);animation:pulse 1.8s ease-in-out infinite}
.yes:hover{transform:scale(1.08)}
@keyframes pulse{50%{box-shadow:0 10px 34px rgba(255,77,136,.7);transform:scale(1.04)}}
.no{background:#6b4f8a;color:#fff;border:2px solid #8a6fb0;
  transition:left .35s cubic-bezier(.3,1.6,.5,1),top .35s cubic-bezier(.3,1.6,.5,1);z-index:50;touch-action:manipulation}
.no.moved{position:absolute}
:root[data-theme="dark"] .no{background:#8a5fb0;color:#fff;border-color:#a77fd0}
.soft{background:var(--accent);color:#fff;box-shadow:0 8px 20px rgba(255,77,136,.35)}
.soft:hover{transform:translateY(-2px)}

/* ===== CELEBRATION ===== */
.big{font-size:clamp(1.9rem,8vw,2.8rem);color:var(--accent);margin-bottom:4px}
.sec{margin-top:18px;padding-top:16px;border-top:2px dashed var(--line)}
.sec h2{font-size:1.3rem;margin-bottom:10px}

/* Gift */
.gift{width:120px;height:120px;margin:0 auto;background:none;display:block;transition:transform .2s}
.gift:hover{transform:scale(1.07) rotate(-3deg)}
.gift .lid{transform-origin:20px 40px;transition:transform .6s cubic-bezier(.3,1.5,.5,1)}
.gift.open .lid{transform:translate(8px,-34px) rotate(-22deg)}
.gift.open{animation:giftwiggle .6s}
@keyframes giftwiggle{25%{transform:rotate(-6deg)}75%{transform:rotate(6deg)}}
.surprise{margin-top:8px;font-weight:600;font-size:.95rem}

/* Envelope */
.env{position:relative;width:220px;height:148px;margin:4px auto 0;background:none;display:block;perspective:600px}
.env .back{position:absolute;inset:0;background:#ffb6cf;border-radius:10px;box-shadow:0 6px 16px rgba(255,77,136,.3)}
.env .flap{position:absolute;left:0;top:0;width:100%;height:74px;background:#ff8fb7;
  clip-path:polygon(0 0,100% 0,50% 100%);transform-origin:top;transition:transform .7s;z-index:3;border-radius:10px 10px 0 0}
.env .front{position:absolute;inset:0;background:linear-gradient(135deg,#ffc7dc 50%,#ffa9c8 50%);
  clip-path:polygon(0 0,50% 55%,100% 0,100% 100%,0 100%);z-index:2;border-radius:10px}
.env .seal{position:absolute;left:50%;top:58px;transform:translateX(-50%);font-size:1.5rem;z-index:4;transition:opacity .3s}
.env.open .flap{transform:rotateX(180deg);z-index:1}
.env.open .seal{opacity:0}
.letter{margin:14px auto 0;max-width:420px;padding:18px 16px;border-radius:16px;background:#fffaf3;color:#5a3a2e;
  text-align:left;font-family:Georgia,serif;font-size:1rem;line-height:1.6;white-space:pre-line;
  box-shadow:0 8px 22px rgba(0,0,0,.12);animation:fadeIn .7s both}
:root[data-theme="dark"] .letter{background:#f6e9dd}

/* Form (link maker) */
.field{display:block;text-align:left;margin-bottom:12px;font-weight:600;font-size:.92rem}
.field small{font-weight:400;color:var(--muted)}
.field input,.field textarea{width:100%;margin-top:5px;padding:12px 14px;border-radius:16px;border:2px solid var(--line);
  background:var(--btn-no);color:var(--text);font:inherit;font-size:1rem;resize:none;transition:border-color .2s}
.field input:focus,.field textarea:focus{outline:none;border-color:var(--accent)}
.err{min-height:1.2em;margin-bottom:6px;color:var(--accent);font-weight:600;font-size:.9rem}
.result{margin-top:18px;animation:fadeIn .5s both}
.result input{width:100%;padding:10px 12px;border-radius:14px;border:2px dashed var(--line);background:var(--btn-no);color:var(--text);font:inherit;font-size:.85rem;margin-bottom:10px}
a.btn{display:inline-flex;align-items:center;text-decoration:none}
.msgbox{margin:0 auto 14px;max-width:380px;padding:10px 14px;border-radius:16px;background:var(--btn-no);
  color:var(--text);font-style:italic;line-height:1.45;font-size:.95rem}
.eyebrow,.q,.msgbox{overflow-wrap:anywhere}
/* Share */
.row{display:flex;gap:8px;justify-content:center;flex-wrap:wrap}

footer{margin-top:12px;color:var(--muted);font-size:.85rem;z-index:2}

/* ===== TOAST ===== */
.toast{position:fixed;left:50%;bottom:max(20px,env(safe-area-inset-bottom));transform:translate(-50%,30px);
  background:var(--accent);color:#fff;padding:10px 18px;border-radius:24px;font-weight:600;opacity:0;
  transition:.35s;pointer-events:none;z-index:200;max-width:90vw;text-align:center;font-size:.9rem}
.toast.show{opacity:1;transform:translate(-50%,0)}

/* ===== FLOATING HEARTS + CONFETTI ===== */
#bg{position:fixed;inset:0;pointer-events:none;overflow:hidden;z-index:1}
.fh{position:absolute;bottom:-40px;opacity:0;color:var(--accent2);animation:rise linear infinite;will-change:transform}
@keyframes rise{0%{transform:translateY(0) rotate(0);opacity:0}10%{opacity:.55}100%{transform:translateY(-115vh) rotate(25deg);opacity:0}}
.conf{position:fixed;pointer-events:none;z-index:150;animation:pop 1.6s ease-out forwards;will-change:transform}
@keyframes pop{0%{transform:translate(0,0) scale(.4);opacity:1}100%{transform:translate(var(--dx),var(--dy)) scale(1.2) rotate(var(--r));opacity:0}}

/* ===== CAT MOODS ===== */
.m{display:none}
svg[data-mood="normal"] .m-normal,
svg[data-mood="surprised"] .m-surprised,
svg[data-mood="yawn"] .m-yawn,
svg[data-mood="sad"] .m-sad,
svg[data-mood="happy"] .m-happy,
svg[data-mood="celebrate"] .m-happy,
svg[data-mood="celebrate"] .m-hat{display:inline}
.tear{animation:tear 1s ease-in infinite}
@keyframes tear{from{transform:translateY(0);opacity:1}to{transform:translateY(16px);opacity:0}}

/* ===== REDUCED MOTION ===== */
@media (prefers-reduced-motion:reduce){
  *,*::before,*::after{animation:none!important;transition-duration:.01ms!important;scroll-behavior:auto!important}
  #bg{display:none}
}

/* ===== SOUND TOGGLE ===== */
#soundBtn{font-size:1.05rem}
</style>
</head>
<body>

<div id="bg" aria-hidden="true"></div>

<div class="bar">
  <button class="chip" id="soundBtn" type="button" aria-label="Sound off">🔇</button>
  <button class="chip" id="themeBtn" type="button" aria-label="Switch between light and dark mode">🌙</button>
</div>

<main class="card" id="card">

  <!-- Cat (shared by both screens). Tap head / body / tail to play. -->
  <div class="catwrap" id="catwrap">
  <svg class="cat" id="cat" viewBox="0 0 200 236" role="img" aria-label="A cute orange cat. Tap its head, body or tail to play with it." data-mood="normal">
   <g id="all">
    <!-- tail -->
    <g class="hit tail" id="tail" data-part="tail"><g class="tailIdle">
      <path d="M146 214C186 222 206 184 188 152" stroke="rgba(0,0,0,.004)" stroke-width="40" fill="none" stroke-linecap="round"/>
      <path d="M146 214C186 222 206 184 188 152" stroke="#f59a3c" stroke-width="17" fill="none" stroke-linecap="round"/>
      <path d="M176 200l9-7M190 184l9-5" stroke="#d9791c" stroke-width="4" stroke-linecap="round"/>
      <g class="tailTip"><circle cx="188" cy="151" r="9" fill="#ffe3c2"/></g>
    </g></g>
    <!-- body -->
    <g class="hit" data-part="body"><g class="breathe">
      <ellipse cx="100" cy="194" rx="56" ry="36" fill="#f59a3c"/>
      <ellipse cx="100" cy="202" rx="30" ry="24" fill="#ffe3c2"/>
      <path d="M50 186q9 3 12 13M150 186q-9 3-12 13" stroke="#d9791c" stroke-width="4" fill="none" stroke-linecap="round"/>
      <ellipse cx="72" cy="224" rx="17" ry="9" fill="#ffe3c2"/><ellipse cx="128" cy="224" rx="17" ry="9" fill="#ffe3c2"/>
    </g></g>
    <!-- head -->
    <g id="headT"><g class="headBob"><g class="hit" data-part="head">
      <g class="ear earL"><polygon points="38,62 46,10 90,40" fill="#f59a3c"/><polygon points="48,52 52,24 76,42" fill="#ffb3c6"/></g>
      <g class="ear earR"><polygon points="162,62 154,10 110,40" fill="#f59a3c"/><polygon points="152,52 148,24 124,42" fill="#ffb3c6"/></g>
      <ellipse cx="100" cy="104" rx="72" ry="60" fill="#f59a3c"/>
      <path d="M100 46v16M84 50l4 13M116 50l-4 13" stroke="#d9791c" stroke-width="5" stroke-linecap="round"/>
      <ellipse cx="100" cy="124" rx="34" ry="24" fill="#ffe3c2"/>
      <circle cx="58" cy="118" r="10" fill="#ff9fb8" opacity=".6"/><circle cx="142" cy="118" r="10" fill="#ff9fb8" opacity=".6"/>
      <path class="nose" d="M94 108h12l-6 8z" fill="#e0517a"/>
      <g class="whisk"><path d="M62 112l-26-4M62 120l-26 4M138 112l26-4M138 120l26 4" stroke="#8a4a1c" stroke-width="2" stroke-linecap="round"/></g>
      <!-- normal -->
      <g class="m m-normal"><g class="eyes"><g class="pup"><circle cx="74" cy="94" r="7" fill="#3a2230"/><circle cx="126" cy="94" r="7" fill="#3a2230"/>
        <circle cx="76" cy="91" r="2.2" fill="#fff"/><circle cx="128" cy="91" r="2.2" fill="#fff"/></g></g>
        <path d="M86 122q14 12 28 0" stroke="#3a2230" stroke-width="3.5" fill="none" stroke-linecap="round"/></g>
      <!-- surprised -->
      <g class="m m-surprised"><g class="eyes"><circle cx="74" cy="92" r="13" fill="#fff"/><circle cx="126" cy="92" r="13" fill="#fff"/>
        <g class="pup"><circle cx="74" cy="92" r="6" fill="#3a2230"/><circle cx="126" cy="92" r="6" fill="#3a2230"/></g></g>
        <ellipse cx="100" cy="128" rx="7" ry="9" fill="#3a2230"/>
        <path d="M60 70q14-10 28 0M112 70q14-10 28 0" stroke="#d9791c" stroke-width="4" fill="none" stroke-linecap="round"/></g>
      <!-- sad -->
      <g class="m m-sad"><g class="eyes"><circle cx="74" cy="96" r="8" fill="#3a2230"/><circle cx="126" cy="96" r="8" fill="#3a2230"/>
        <circle cx="77" cy="93" r="3" fill="#fff"/><circle cx="129" cy="93" r="3" fill="#fff"/></g>
        <path d="M88 132q12-12 24 0" stroke="#3a2230" stroke-width="3.5" fill="none" stroke-linecap="round"/>
        <path d="M60 82l22 6M140 82l-22 6" stroke="#d9791c" stroke-width="4" stroke-linecap="round"/>
        <path class="tear" d="M70 106q-5 9 0 12q5-3 0-12z" fill="#6ec6ff"/>
        <path class="tear" d="M130 106q-5 9 0 12q5-3 0-12z" fill="#6ec6ff" style="animation-delay:.4s"/></g>
      <!-- happy / celebrate -->
      <g class="m m-happy"><path d="M62 98q12-18 24 0M114 98q12-18 24 0" stroke="#3a2230" stroke-width="4.5" fill="none" stroke-linecap="round"/>
        <path d="M84 118q16 30 32 0z" fill="#e0517a" stroke="#3a2230" stroke-width="3" stroke-linejoin="round"/></g>
      <!-- yawn (sleepy) -->
      <g class="m m-yawn"><path d="M62 98q12-10 24 0M114 98q12-10 24 0" stroke="#3a2230" stroke-width="4.5" fill="none" stroke-linecap="round"/>
        <ellipse cx="100" cy="130" rx="10" ry="12" fill="#e0517a" stroke="#3a2230" stroke-width="3"/></g>
      <g class="m m-hat"><polygon points="100,-2 78,40 122,40" fill="#a66bff" transform="translate(0 4)"/>
        <circle cx="100" cy="4" r="6" fill="#ffd23f"/><circle cx="92" cy="26" r="3" fill="#fff"/><circle cx="108" cy="22" r="3" fill="#ffd23f"/></g>
    </g></g></g>
   </g>
  </svg>
  </div>

  <!-- ===== LINK MAKER (shown when the URL has no valid names) ===== -->
  <section id="maker" class="screen hidden">
    <h1 class="q" style="margin-bottom:4px">Make a proposal link</h1>
    <p class="sub">Fill this in, then send the link to your crush.</p>
    <form id="makerForm" novalidate>
      <label class="field">Your Name<input id="fromIn" maxlength="30" autocomplete="off" placeholder="Rahim"></label>
      <label class="field">Crush's Name<input id="toIn" maxlength="30" autocomplete="off" placeholder="Anika"></label>
      <label class="field">Personal Message <small>(optional)</small><textarea id="msgIn" rows="2" maxlength="200" placeholder="Hello..."></textarea></label>
      <p class="err" id="formErr" role="alert"></p>
      <button class="btn yes" type="submit" style="animation:none">Generate My Link</button>
    </form>
    <div class="result hidden" id="result">
      <p class="sub">Your link is ready! 🎉</p>
      <input id="linkOut" readonly aria-label="Your personalised link">
      <div class="row">
        <a class="btn soft" id="waBtn" target="_blank" rel="noopener noreferrer">Share on WhatsApp</a>
        <button class="btn soft" id="copyBtn" type="button">Copy Link 🔗</button>
      </div>
    </div>
  </section>

  <!-- ===== PROPOSAL SCREEN ===== -->
  <section id="proposal" class="screen hidden">
    <p class="eyebrow" id="greet"></p>
    <p class="sub" id="ask">I have something to ask you… ❤️</p>
    <p class="msgbox hidden" id="msgBox"></p>
    <h1 class="q" id="question">Will you be mine?</h1>
    <div class="btns" id="btns">
      <button class="btn yes" id="yesBtn" type="button">YES! ❤️</button>
      <span id="noSlot"><button class="btn no" id="noBtn" type="button" aria-label="No button (it likes to run away)">NO 🙈</button></span>
    
