<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="theme-color" content="#0a0a0b">
<title>COLE</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500;600;700&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
--bg:#0a0a0b;--card:#111114;--card2:#16161a;--card3:#1c1c21;
--accent:#d4a843;--accent-l:#e8c97a;--accent-dim:rgba(212,168,67,.08);
--text:#f0ead8;--text2:#9b9388;--muted:#55504a;--muted2:#1e1c19;
--green:#4ecb7f;--green-dim:rgba(78,203,127,.08);
--red:#e0716b;--red-dim:rgba(224,113,107,.08);
--blue:#6fa8d8;--blue-dim:rgba(111,168,216,.08);
--purple:#a78bfa;--border:#1a1a1e;--border2:#252428;
}
body.theme-light{--bg:#f7f4ef;--card:#fff;--card2:#f1ece3;--card3:#e9e2d6;--accent:#a8762e;--accent-l:#c4934a;--accent-dim:rgba(168,118,46,.08);--text:#1c1a17;--text2:#5c564c;--muted:#9a9186;--muted2:#e4ddd1;--green:#2e8052;--green-dim:rgba(46,128,82,.08);--red:#b5453f;--red-dim:rgba(181,69,63,.08);--blue:#2f5f8f;--blue-dim:rgba(47,95,143,.08);--border:#e6e0d4;--border2:#d8d0c2}
body.theme-dark{--bg:#000;--card:#0c0c0c;--card2:#131313;--card3:#1a1a1a;--accent:#d8d8d8;--accent-l:#fff;--accent-dim:rgba(216,216,216,.06);--text:#fff;--text2:#999;--muted:#4a4a4a;--muted2:#161616;--green:#5ee08a;--green-dim:rgba(94,224,138,.08);--red:#ea7a73;--red-dim:rgba(234,122,115,.08);--blue:#7eb3e8;--blue-dim:rgba(126,179,232,.08);--border:#1c1c1c;--border2:#262626}
body.theme-chatgpt{--bg:#0c0d11;--card:#151b28;--card2:#1a2030;--card3:#222a3d;--accent:#8b7cf6;--accent-l:#a596ff;--accent-dim:rgba(139,124,246,.1);--text:#e9e8f2;--text2:#94909e;--muted:#4d4a5c;--muted2:#191c28;--green:#5bd687;--green-dim:rgba(91,214,135,.08);--red:#f08178;--red-dim:rgba(240,129,120,.08);--blue:#69aaf5;--blue-dim:rgba(105,170,245,.08);--border:#1f2433;--border2:#272e42}
body.theme-pastel{--bg:#fdf6f8;--card:#ffffff;--card2:#fbeef2;--card3:#f6e2e8;--accent:#e8a0b4;--accent-l:#f2b8c8;--accent-dim:rgba(232,160,180,.12);--text:#3a3238;--text2:#7a6d74;--muted:#b8a8ae;--muted2:#f0dde3;--green:#7fb89a;--green-dim:rgba(127,184,154,.1);--red:#e0919a;--red-dim:rgba(224,145,154,.1);--blue:#9db4c9;--blue-dim:rgba(157,180,201,.1);--border:#f2dde3;--border2:#e8cdd6}
html,body,#root{height:100%;overflow:hidden;font-family:'DM Sans',sans-serif;background:var(--bg);color:var(--text);-webkit-font-smoothing:antialiased}
*{font-size:inherit}
html{font-size:15px}
::-webkit-scrollbar{width:3px;height:3px}::-webkit-scrollbar-thumb{background:var(--border2);border-radius:3px}
input,textarea,select{background:var(--card2);border:1px solid var(--border2);border-radius:10px;color:var(--text);font-family:'DM Sans',sans-serif;font-size:.93em;padding:.66em .86em;outline:none;width:100%;transition:border-color .15s;-webkit-appearance:none}
input:focus,textarea:focus,select:focus{border-color:var(--accent)}
::placeholder{color:var(--muted)}
select option{background:var(--card2);color:var(--text)}
button{cursor:pointer;font-family:'DM Sans',sans-serif;font-size:1em}
textarea{resize:vertical}
.fd{font-family:'Bebas Neue',sans-serif}
.fm{font-family:'DM Mono',monospace}
.sc{overflow-y:auto;-webkit-overflow-scrolling:touch}
.card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:1.2em}
body.theme-pastel .card{box-shadow:0 4px 24px rgba(232,160,180,.12)}
.sl{font-family:'DM Mono',monospace;font-size:.66em;font-weight:500;letter-spacing:1.5px;text-transform:uppercase;color:var(--muted)}
.btn-p{width:100%;background:var(--accent);border:none;border-radius:12px;color:#0a0a0b;font-weight:600;font-size:.93em;padding:.86em;letter-spacing:.2px;transition:opacity .15s}
body.theme-pastel .btn-p{color:#fff}
.btn-p:hover{opacity:.9}.btn-p:active{opacity:.78}.btn-p:disabled{opacity:.35;cursor:not-allowed}
.btn-g{background:none;border:1px solid var(--border2);border-radius:11px;color:var(--text2);font-size:.86em;padding:.53em .93em;transition:border-color .15s,color .15s}
.btn-g:hover{border-color:var(--accent);color:var(--accent)}
.chip{padding:.4em .93em;border-radius:20px;border:1px solid var(--border2);background:var(--card2);color:var(--muted);font-size:.73em;white-space:nowrap;cursor:pointer;font-weight:500;letter-spacing:.2px;transition:all .15s;flex-shrink:0}
.chip.on{background:var(--text);color:var(--bg);border-color:var(--text)}
body.theme-pastel .chip.on{background:var(--accent);color:#fff;border-color:var(--accent)}
.prog-t{background:var(--border2);height:4px;border-radius:4px;overflow:hidden}
.prog-f{height:100%;border-radius:4px;transition:width .5s cubic-bezier(.4,0,.2,1)}
.modal-ov{position:fixed;inset:0;background:rgba(0,0,0,.7);z-index:900;display:flex;align-items:flex-end;animation:fadeIn .18s ease}
.modal-sh{background:var(--card);border-radius:22px 22px 0 0;padding:1.46em 1.2em 2.93em;width:100%;max-height:92vh;overflow-y:auto;animation:sheetUp .24s cubic-bezier(.4,0,.2,1)}
@keyframes sheetUp{from{transform:translateY(100%)}to{transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
@keyframes fadeUp{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
@keyframes notifIn{from{transform:translateX(110%);opacity:0}to{transform:translateX(0);opacity:1}}
.notif-e{animation:notifIn .25s ease}
.afu{animation:fadeUp .22s ease}
.tog-t{width:2.8em;height:1.6em;background:var(--muted2);border-radius:12px;position:relative;cursor:pointer;transition:background .18s;flex-shrink:0}
.tog-t.on{background:var(--accent)}
.tog-th{position:absolute;width:1.2em;height:1.2em;background:#fff;border-radius:50%;top:.2em;left:.2em;transition:left .18s}
.tog-t.on .tog-th{left:1.4em}
#splash{position:fixed;inset:0;background:#0a0a0b;z-index:9999;display:flex;align-items:center;justify-content:center;transition:opacity .5s ease}
#splash.hide{opacity:0;pointer-events:none}
.splash-c{font-family:'Bebas Neue',sans-serif;font-size:110px;color:#d4a843;letter-spacing:6px;line-height:1;animation:splashPop 1.2s cubic-bezier(.4,0,.2,1) forwards}
@keyframes splashPop{0%{opacity:0;transform:scale(.45)}55%{opacity:1;transform:scale(1.08)}100%{opacity:1;transform:scale(1)}}
.txn-row{display:flex;align-items:flex-start;justify-content:space-between;gap:.86em;padding:1em 0;border-bottom:1px solid var(--border)}
.txn-row:last-child{border-bottom:none}
</style>
</head>
<body>
<div id="splash"><div class="splash-c">C</div></div>
<div id="root"></div>
<script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<script type="text/babel">
setTimeout(()=>{const s=document.getElementById('splash');if(s){s.classList.add('hide');setTimeout(()=>{try{s.remove()}catch(e){}},600)}},1500);

const {useState,useEffect,useCallback,useMemo,createContext,useContext}=React;

const STORE_KEY='cole_os_v7';
const DAYS=['Monday','Tuesday','Wednesday','Thursday','Friday','Saturday','Sunday'];
const BUSINESSES=['COCO Nails','C.Closette','LADI Nailbar','Personal','General'];
const TXN_TYPES=[{v:'income',l:'Income',color:'var(--green)'},{v:'expense',l:'Expense',color:'var(--red)'},{v:'credit',l:'Credit',color:'var(--blue)'},{v:'debit',l:'Debit',color:'var(--accent)'}];

const uid=()=>Date.now()+'-'+Math.floor(Math.random()*99999);
const parseAmt=function(s){if(!s&&s!==0)return 0;const n=parseFloat(String(s).replace(/[₦,\s]/g,''));return isNaN(n)?0:n};
const fmt=function(n){if(n===null||n===undefined||isNaN(n))return'₦0';const abs=Math.abs(n),sign=n<0?'-':'';if(abs>=1000000)return sign+'₦'+(abs/1000000).toFixed(2)+'M';if(abs>=1000)return sign+'₦'+abs.toLocaleString();return sign+'₦'+abs};
const todayStr=function(){return new Date().toISOString().split('T')[0]};
const fmtDate=function(s){if(!s)return'';const d=new Date(s);if(isNaN(d))return s;const M=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];return d.getDate()+' '+M[d.getMonth()]+' '+d.getFullYear()};
const getDaysUntil=function(s){if(!s)return null;const t=new Date(s);t.setHours(0,0,0,0);const today=new Date();today.setHours(0,0,0,0);return Math.round((t-today)/86400000)};
const getFullDateLabel=function(){const d=new Date();const days=['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday'];const months=['January','February','March','April','May','June','July','August','September','October','November','December'];return days[d.getDay()]+', '+d.getDate()+' '+months[d.getMonth()]+' '+d.getFullYear()};
const getGreeting=function(name){const h=new Date().getHours();if(h>=5&&h<12)return'Good morning, '+name;if(h>=12&&h<17)return'Good afternoon, '+name;return'Good evening, '+name};

function applyTheme(t){
  document.body.classList.remove('theme-light','theme-dark','theme-chatgpt','theme-pastel');
  if(t==='light')document.body.classList.add('theme-light');
  else if(t==='dark')document.body.classList.add('theme-dark');
  else if(t==='chatgpt')document.body.classList.add('theme-chatgpt');
  else if(t==='pastel')document.body.classList.add('theme-pastel');
}
function applyFontSize(f){
  const sizes={sm:'12.5px',md:'15px',lg:'18px',xl:'22px'};
  document.documentElement.style.fontSize=sizes[f]||'15px';
}

const MOTIVATION_QUOTES=[
  {text:"Discipline is choosing between what you want now and what you want most.",author:"Daily Focus"},
  {text:"Small consistent actions compound into results no one can ignore.",author:"Daily Focus"},
  {text:"You don't need more hours in the day, you need clearer priorities.",author:"Daily Focus"},
  {text:"Every task you finish today is one less thing standing between you and your goal.",author:"Daily Focus"},
  {text:"Progress doesn't announce itself. It shows up quietly, one completed task at a time.",author:"Daily Focus"},
  {text:"Momentum is built, not found. Start with the smallest task on your list.",author:"Daily Focus"},
  {text:"The business that grows is the one that gets worked on daily, not just thought about.",author:"Daily Focus"},
  {text:"Clarity comes from action, not thinking. Move on the next task.",author:"Daily Focus"},
  {text:"What you track, you improve. What you ignore, you lose.",author:"Daily Focus"},
  {text:"Today's effort is tomorrow's balance sheet.",author:"Daily Focus"},
  {text:"Consistency beats intensity. Show up again today.",author:"Daily Focus"},
  {text:"Your future business is built from today's follow-through.",author:"Daily Focus"},
  {text:"Done is better than perfect, ship the task, refine later.",author:"Daily Focus"},
  {text:"Every client you follow up with today is revenue you're not leaving on the table.",author:"Daily Focus"},
  {text:"Growth feels slow in the moment and obvious in hindsight. Keep going.",author:"Daily Focus"},
  {text:"You are one completed task away from momentum.",author:"Daily Focus"},
  {text:"A goal without a deadline is just a wish. Check your Target page today.",author:"Daily Focus"},
  {text:"The version of you that hits target didn't wait for motivation, she scheduled the work.",author:"Daily Focus"},
  {text:"Protect your mornings. What you do first sets the tone for everything after.",author:"Daily Focus"},
  {text:"Money follows attention. Give your business the attention it needs today.",author:"Daily Focus"},
  {text:"Every business you run is a reflection of your discipline, not your luck.",author:"Daily Focus"},
  {text:"Finish the task in front of you before starting the one calling from the corner.",author:"Daily Focus"},
  {text:"You built this from nothing. Today is just one more brick.",author:"Daily Focus"},
  {text:"Slow progress is still progress. Log it, track it, keep moving.",author:"Daily Focus"},
  {text:"The tasks you avoid are usually the ones worth the most.",author:"Daily Focus"},
  {text:"Systems don't get tired. Trust the process you built for yourself.",author:"Daily Focus"},
  {text:"Today's income starts with today's first task.",author:"Daily Focus"},
  {text:"You don't have to feel ready. You just have to start.",author:"Daily Focus"},
  {text:"Every deadline you meet builds the reputation that gets you the next client.",author:"Daily Focus"},
  {text:"Balance the books, balance the mind. Check Finance today.",author:"Daily Focus"}
];
function getDailyQuote(){
  const start=new Date(2026,0,1);
  const now=new Date();
  const dayIndex=Math.floor((now-start)/86400000);
  const idx=((dayIndex%MOTIVATION_QUOTES.length)+MOTIVATION_QUOTES.length)%MOTIVATION_QUOTES.length;
  return MOTIVATION_QUOTES[idx];
}

const BRANDS=[
  {v:'COCO Nails',voice:'nail brand and training academy'},
  {v:'C.Closette',voice:'bespoke unisex tailoring brand'},
  {v:'LADI Nailbar',voice:'nail bar'},
  {v:'Personal',voice:'personal brand'}
];
const PLATFORMS=['Instagram caption','Threads post','Facebook post','TikTok caption','Marketing campaign','Product launch','Promotional copy','Sales copy','WhatsApp promotional message','Customer appreciation post','Holiday campaign','Flash sale campaign','Educational content','Client engagement idea','Business growth idea'];

const OPENERS=['Okay so','Listen,','New drop:','PSA:','Quick one —','Real talk,','Guess what,','Not me finally posting this but','Update:','Big news,'];
const CTA_BOOK=['Slide into DMs to book.','Link in bio to book your slot.','DM to secure your spot, filling up fast.','Tap the bio link, let\'s get you booked.','Comment BOOK and we\'ll sort you out.','WhatsApp us to lock in your appointment.'];
const CTA_SALES=['Offer runs for a limited time, don\'t sleep on it.','Spaces are limited, lock yours in now.','First come first served, book today.','Available while slots last.','Ends soon, don\'t miss this one.'];
const HASHTAGS={
  'COCO Nails':['#CocoNailsHQ','#LagosNails','#NailTechLagos','#NailTraining','#LekkiNails','#LagosMainland'],
  'C.Closette':['#CCosette','#BespokeTailoring','#LagosFashion','#MadeToMeasure','#LagosTailor'],
  'LADI Nailbar':['#LADINailbar','#LagosNailbar','#NailsOnFleek','#IslandNails','#LekkiBeauty'],
  'Personal':['#LagosEntrepreneur','#BuildInPublic','#LagosHustle']
};

function generateContentTemplate(brand,platform,topic){
  const b=BRANDS.find(function(x){return x.v===brand}) || BRANDS[0];
  const locationLine=brand==='Personal'?'':(Math.random()>0.5?' — serving clients across Lagos Mainland and our Lekki location.':' Based in Lagos Mainland, with our Lekki (Island) location open too.');
  const opener=OPENERS[Math.floor(Math.random()*OPENERS.length)];
  const p=platform.toLowerCase();
  const cta=(p.indexOf('sale')>-1||p.indexOf('promo')>-1||p.indexOf('launch')>-1||p.indexOf('holiday')>-1||p.indexOf('flash')>-1)
    ? CTA_SALES[Math.floor(Math.random()*CTA_SALES.length)]
    : CTA_BOOK[Math.floor(Math.random()*CTA_BOOK.length)];
  const tags=(HASHTAGS[brand]||[]).slice(0,4).join(' ');

  let body='';
  if(p.indexOf('marketing campaign')>-1){
    body=opener+' '+b.v+' is rolling something out and you need to hear about it.'+locationLine+'\n\n'+topic+'\n\nThis is for the people who\'ve been waiting — '+b.voice+' energy, done right. '+cta+'\n\n'+tags;
  }else if(p.indexOf('product launch')>-1){
    body='Introducing: '+topic+'\n\n'+b.v+' is bringing this to you because you deserve better options.'+locationLine+' Book in, come see for yourself.\n\n'+cta+'\n\n'+tags;
  }else if(p.indexOf('tiktok')>-1){
    body=opener+' '+topic+' at '+b.v+'. '+cta+' '+tags.split(' ').slice(0,3).join(' ');
  }else if(p.indexOf('threads')>-1){
    body=opener+' '+topic+'. That\'s it, that\'s the post. '+b.v+' knows what\'s up.';
  }else if(p.indexOf('facebook')>-1){
    body=b.v+' here\n\n'+topic+locationLine+'\n\nWe\'ve been working on this and it\'s finally ready to share. '+cta+'\n\nQuestions? Drop a comment or send a message, we\'re happy to help.';
  }else if(p.indexOf('whatsapp')>-1){
    body='Hi! '+b.v+' here\n\n'+topic+'\n\n'+cta+'\n\nReply to this message and we\'ll sort you out.';
  }else if(p.indexOf('appreciation')>-1){
    body='To everyone who\'s trusted '+b.v+' this month, thank you. '+topic+'\n\nWe don\'t take it for granted. More coming your way soon.\n\n'+tags;
  }else if(p.indexOf('holiday')>-1){
    body=opener+' the season calls for something special.\n\n'+topic+'\n\n'+b.v+locationLine+' '+cta+'\n\n'+tags;
  }else if(p.indexOf('flash sale')>-1){
    body='FLASH: '+topic+'\n\n'+b.v+' — '+cta+'\n\n'+tags;
  }else if(p.indexOf('educational')>-1){
    body='Something worth knowing:\n\n'+topic+'\n\nFrom the team at '+b.v+'. Save this for later.\n\n'+tags;
  }else if(p.indexOf('engagement')>-1){
    body='Question for you: '+topic+'\n\nDrop your answer below — '+b.v+' wants to hear from you.';
  }else if(p.indexOf('growth idea')>-1){
    body='Growth idea for '+b.v+': '+topic+'\n\nWorth testing this month and tracking the results in Finance.';
  }else if(p.indexOf('sales')>-1||p.indexOf('promotional')>-1){
    body=opener+' '+topic+'\n\n'+b.v+locationLine+' '+cta+'\n\n'+tags;
  }else{
    body=opener+' '+topic+'\n\n'+b.v+' bringing the '+b.voice+' energy as always.'+locationLine+' '+cta+'\n\n'+tags;
  }
  return body;
}

const MEAL_BANK={
  low:{
    breakfast:[{name:'Akara and pap',ingredients:['Beans','Pepper','Onion','Pap/Ogi'],calories:320,protein:14,carbs:38,fat:11},{name:'Bread and egg sauce',ingredients:['Bread','Eggs','Tomato','Onion','Pepper'],calories:380,protein:16,carbs:40,fat:15},{name:'Yam and egg',ingredients:['Yam','Eggs','Tomato','Onion'],calories:410,protein:15,carbs:52,fat:12}],
    lunch:[{name:'Beans and plantain',ingredients:['Beans','Plantain','Palm oil','Pepper'],calories:520,protein:18,carbs:78,fat:14},{name:'Rice and stew',ingredients:['Rice','Tomato','Pepper','Onion','Chicken (small)'],calories:560,protein:22,carbs:70,fat:16},{name:'Jollof rice (small portion)',ingredients:['Rice','Tomato','Pepper','Onion','Seasoning'],calories:480,protein:10,carbs:75,fat:12}],
    dinner:[{name:'Indomie and egg',ingredients:['Indomie noodles','Eggs','Onion'],calories:430,protein:14,carbs:52,fat:16},{name:'Yam porridge',ingredients:['Yam','Palm oil','Pepper','Onion','Crayfish'],calories:490,protein:12,carbs:65,fat:18},{name:'Spaghetti and stew',ingredients:['Spaghetti','Tomato','Pepper','Onion'],calories:470,protein:13,carbs:68,fat:14}]
  },
  mid:{
    breakfast:[{name:'Moi moi and pap',ingredients:['Beans','Pepper','Eggs','Pap'],calories:390,protein:20,carbs:36,fat:16},{name:'Bread, egg and tea',ingredients:['Bread','Eggs','Tea','Milk','Sugar'],calories:420,protein:18,carbs:45,fat:15},{name:'Yam and fried egg',ingredients:['Yam','Eggs','Tomato','Pepper'],calories:440,protein:17,carbs:55,fat:14}],
    lunch:[{name:'Jollof rice and chicken',ingredients:['Rice','Chicken','Tomato','Pepper','Onion'],calories:650,protein:34,carbs:72,fat:20},{name:'Efo riro and swallow',ingredients:['Spinach/Ugu','Palm oil','Assorted meat','Pepper'],calories:600,protein:28,carbs:58,fat:24},{name:'Fried rice and fish',ingredients:['Rice','Fish','Mixed veg','Seasoning'],calories:610,protein:30,carbs:70,fat:16}],
    dinner:[{name:'Amala and ewedu',ingredients:['Yam flour','Ewedu leaves','Assorted meat','Pepper'],calories:560,protein:24,carbs:65,fat:18},{name:'Pepper soup and rice',ingredients:['Goat meat','Pepper soup spice','Rice'],calories:590,protein:32,carbs:60,fat:19},{name:'Rice and beans',ingredients:['Rice','Beans','Palm oil','Pepper'],calories:540,protein:20,carbs:74,fat:14}]
  },
  high:{
    breakfast:[{name:'Full breakfast plate',ingredients:['Eggs','Sausage','Bread','Beans','Tea'],calories:560,protein:28,carbs:48,fat:26},{name:'Shawarma breakfast wrap',ingredients:['Bread wrap','Chicken/Beef','Veg','Sauce'],calories:520,protein:30,carbs:45,fat:22},{name:'Yam, egg and plantain',ingredients:['Yam','Eggs','Plantain','Tomato'],calories:540,protein:20,carbs:68,fat:16}],
    lunch:[{name:'Grilled chicken and jollof',ingredients:['Rice','Grilled chicken','Tomato','Pepper','Plantain'],calories:720,protein:42,carbs:75,fat:22},{name:'Seafood okra and swallow',ingredients:['Okra','Prawns','Fish','Assorted meat'],calories:680,protein:44,carbs:52,fat:28},{name:'Suya platter and rice',ingredients:['Suya beef','Rice','Onion','Pepper mix'],calories:700,protein:40,carbs:70,fat:24}],
    dinner:[{name:'Peppered goat meat and fried rice',ingredients:['Goat meat','Rice','Mixed veg','Pepper'],calories:680,protein:38,carbs:68,fat:24},{name:'Grilled fish and plantain',ingredients:['Fish','Plantain','Pepper sauce'],calories:600,protein:36,carbs:58,fat:20},{name:'Ofada rice and sauce',ingredients:['Ofada rice','Ofada pepper sauce','Assorted meat'],calories:650,protein:30,carbs:72,fat:22}]
  }
};
const DAY_NAMES=['Monday','Tuesday','Wednesday','Thursday','Friday','Saturday','Sunday'];

function generateMealPlanTemplate(budget,numDays,seed){
  const bank=MEAL_BANK[budget]||MEAL_BANK.mid;
  const days=[];
  const s=seed||0;
  for(let i=0;i<numDays;i++){
    const breakfast=bank.breakfast[(i+s)%bank.breakfast.length];
    const lunch=bank.lunch[(i+1+s)%bank.lunch.length];
    const dinner=bank.dinner[(i+2+s)%bank.dinner.length];
    days.push({day:DAY_NAMES[i%7],breakfast:breakfast,lunch:lunch,dinner:dinner});
  }
  const shoppingSet=new Set();
  days.forEach(function(d){[d.breakfast,d.lunch,d.dinner].forEach(function(m){m.ingredients.forEach(function(ing){shoppingSet.add(ing)})})});
  const totalCalories=days.reduce(function(sum,d){return sum+d.breakfast.calories+d.lunch.calories+d.dinner.calories},0);
  const avgCalories=Math.round(totalCalories/days.length);
  const budgetLabel=budget==='low'?'budget-friendly':budget==='high'?'premium':'mid-range';
  const nutritionNotes='This '+budgetLabel+' plan balances carbohydrates, protein and vegetables across each day, using ingredients that are easy to find in Lagos mainland markets. Rotate proteins through the week for variety and better nutrition.';
  return{days:days,shoppingList:Array.from(shoppingSet),avgCalories:avgCalories,nutritionNotes:nutritionNotes};
}

function loadState(){try{const r=localStorage.getItem(STORE_KEY);if(r)return JSON.parse(r)}catch(e){}return null}
function saveState(s){try{localStorage.setItem(STORE_KEY,JSON.stringify(s))}catch(e){}}

const calc={
  balance:function(starting,txns){
    const inc=txns.filter(function(t){return t.type==='income'||t.type==='credit'}).reduce(function(s,t){return s+t.amount},0);
    const exp=txns.filter(function(t){return t.type==='expense'||t.type==='debit'}).reduce(function(s,t){return s+t.amount},0);
    return parseAmt(starting)+inc-exp;
  },
  totalByType:function(txns,type){return txns.filter(function(t){return t.type===type}).reduce(function(s,t){return s+t.amount},0)},
  progress:function(target,starting,txns){const t=parseAmt(target);if(!t)return 0;return Math.min(100,Math.round((calc.balance(starting,txns)/t)*100))},
  remaining:function(target,starting,txns){return Math.max(0,parseAmt(target)-calc.balance(starting,txns))},
  businessStats:function(txns,biz){
    const bt=txns.filter(function(t){return t.business===biz});
    const inc=bt.filter(function(t){return t.type==='income'||t.type==='credit'}).reduce(function(s,t){return s+t.amount},0);
    const exp=bt.filter(function(t){return t.type==='expense'||t.type==='debit'}).reduce(function(s,t){return s+t.amount},0);
    return{income:inc,expense:exp,net:inc-exp,count:bt.length};
  },
  monthlyPerformance:function(tasks,txns){
    const now=new Date();
    const m=now.getMonth(),y=now.getFullYear();
    const monthTasks=tasks.filter(function(t){const c=t.completedAt?new Date(t.completedAt):null;return c&&c.getMonth()===m&&c.getFullYear()===y});
    const monthTxns=txns.filter(function(t){const d=new Date(t.date);return d.getMonth()===m&&d.getFullYear()===y});
    const inc=monthTxns.filter(function(t){return t.type==='income'||t.type==='credit'}).reduce(function(s,t){return s+t.amount},0);
    const exp=monthTxns.filter(function(t){return t.type==='expense'||t.type==='debit'}).reduce(function(s,t){return s+t.amount},0);
    const totalTasksThisMonth=tasks.filter(function(t){const c=t.createdAt?new Date(t.createdAt):null;return c&&c.getMonth()===m&&c.getFullYear()===y}).length;
    const completionRate=totalTasksThisMonth>0?Math.round((monthTasks.length/totalTasksThisMonth)*100):0;
    const daysInMonth=new Date(y,m+1,0).getDate();
    const dayOfMonth=now.getDate();
    const weeklyBreakdown=[0,1,2,3].map(function(w){
      const weekStart=w*7+1,weekEnd=Math.min(weekStart+6,daysInMonth);
      const weekTasks=monthTasks.filter(function(t){const d=new Date(t.completedAt).getDate();return d>=weekStart&&d<=weekEnd});
      return{label:'Week '+(w+1),count:weekTasks.length};
    });
    return{
      monthLabel:now.toLocaleString('default',{month:'long',year:'numeric'}),
      tasksCompleted:monthTasks.length,
      completionRate:completionRate,
      income:inc,expense:exp,net:inc-exp,
      dayOfMonth:dayOfMonth,daysInMonth:daysInMonth,
      weeklyBreakdown:weeklyBreakdown
    };
  }
};

const StoreCtx=createContext(null);
const NotifCtx=createContext(null);
const NavCtx=createContext(null);

function StoreProvider(props){
  const saved=loadState();
  const [tasks,setTasks]=useState(saved&&saved.tasks?saved.tasks:[]);
  const [transactions,setTransactions]=useState(saved&&saved.transactions?saved.transactions:[]);
  const [deadlines,setDeadlines]=useState(saved&&saved.deadlines?saved.deadlines:[]);
  const [target,setTargetState]=useState(saved&&saved.target?saved.target:{total:0,startingBalance:0,label:''});
  const [settings,setSettings]=useState(saved&&saved.settings?saved.settings:{userName:'Gbemi',notifications:true,fontSize:'md',theme:'default'});
  const [savedAt,setSavedAt]=useState(saved&&saved._savedAt?saved._savedAt:null);

  useEffect(function(){
    const s={tasks:tasks,transactions:transactions,deadlines:deadlines,target:target,settings:settings,_savedAt:new Date().toISOString()};
    saveState(s);setSavedAt(s._savedAt);
  },[tasks,transactions,deadlines,target,settings]);

  useEffect(function(){applyFontSize(settings.fontSize||'md')},[settings.fontSize]);
  useEffect(function(){applyTheme(settings.theme||'default')},[settings.theme]);

  const postTransaction=function(d){
    const txn={
      id:uid(),title:d.title||'Untitled',type:d.type,business:d.business||'General',
      category:d.category||'other',amount:parseAmt(d.amount),date:d.date||todayStr(),
      reference:d.reference||'',source:d.source||'manual',taskId:d.taskId||null,
      createdAt:new Date().toISOString()
    };
    setTransactions(function(p){return p.concat([txn])});
    return txn.id;
  };
  const removeTransaction=function(id){setTransactions(function(p){return p.filter(function(t){return t.id!==id})})};
  const removeTransactionsByTaskId=function(taskId){setTransactions(function(p){return p.filter(function(t){return t.taskId!==taskId})})};

  const addTask=function(d){setTasks(function(p){return p.concat([{
    id:uid(),text:d.text||'',tag:d.tag||'personal',urgent:d.urgent||d.tag==='urgent'||false,
    day:d.day||'',time:d.time||'',note:d.note||'',done:false,completedAt:null,createdAt:new Date().toISOString(),
    moneyType:d.moneyType||'none',amount:d.amount||'',business:d.business||'General',category:d.category||'other'
  }])})};
  const updateTask=function(id,u){setTasks(function(p){return p.map(function(t){return t.id===id?Object.assign({},t,u):t})})};
  const deleteTask=function(id){setTasks(function(p){return p.filter(function(t){return t.id!==id})});removeTransactionsByTaskId(id)};

  const toggleTask=function(id){
    const task=tasks.find(function(t){return t.id===id});
    if(!task)return null;
    const done=!task.done;
    const now=new Date().toISOString();
    setTasks(function(p){return p.map(function(t){return t.id===id?Object.assign({},t,{done:done,completedAt:done?now:null}):t})});
    removeTransactionsByTaskId(id);
    if(done&&task.moneyType&&task.moneyType!=='none'&&parseAmt(task.amount)>0){
      postTransaction({
        title:task.text,type:task.moneyType,business:task.business||'General',
        category:task.category||'task',amount:task.amount,date:todayStr(),
        reference:task.note||'',source:'task',taskId:task.id
      });
    }
    return Object.assign({},task,{done:done});
  };

  const addDeadline=function(d){setDeadlines(function(p){return p.concat([{id:uid(),title:d.title,date:d.date,amount:d.amount?parseAmt(String(d.amount)):0,category:d.category||'general',done:false,urgent:d.urgent||false,note:d.note||'',createdAt:new Date().toISOString()}])})};
  const toggleDeadline=function(id){setDeadlines(function(p){return p.map(function(d){return d.id===id?Object.assign({},d,{done:!d.done}):d})})};
  const deleteDeadline=function(id){setDeadlines(function(p){return p.filter(function(d){return d.id!==id})})};

  const setTarget=function(total,sb,label){setTargetState({total:parseAmt(String(total)),startingBalance:parseAmt(String(sb)),label:label||''})};
  const updateSettings=function(u){setSettings(function(p){return Object.assign({},p,u)})};

  const resetAll=function(){
    try{localStorage.removeItem(STORE_KEY);Object.keys(localStorage).filter(function(k){return k.indexOf('cole')===0}).forEach(function(k){localStorage.removeItem(k)})}catch(e){}
    setTasks([]);setTransactions([]);setDeadlines([]);
    setTargetState({total:0,startingBalance:0,label:''});
    setSettings({userName:'Cole',notifications:true,fontSize:'md',theme:'default'});
  };

  const store={
    tasks:tasks,transactions:transactions,deadlines:deadlines,target:target,settings:settings,savedAt:savedAt,
    addTask:addTask,updateTask:updateTask,deleteTask:deleteTask,toggleTask:toggleTask,
    postTransaction:postTransaction,removeTransaction:removeTransaction,
    addDeadline:addDeadline,toggleDeadline:toggleDeadline,deleteDeadline:deleteDeadline,
    setTarget:setTarget,updateSettings:updateSettings,resetAll:resetAll,
    getBalance:function(){return calc.balance(target.startingBalance,transactions)},
    getIncome:function(){return calc.totalByType(transactions,'income')},
    getExpense:function(){return calc.totalByType(transactions,'expense')},
    getCredit:function(){return calc.totalByType(transactions,'credit')},
    getDebit:function(){return calc.totalByType(transactions,'debit')},
    getProgress:function(){return calc.progress(target.total,target.startingBalance,transactions)},
    getRemaining:function(){return calc.remaining(target.total,target.startingBalance,transactions)},
    getBusinessStats:function(biz){return calc.businessStats(transactions,biz)},
    getMonthlyPerformance:function(){return calc.monthlyPerformance(tasks,transactions)}
  };
  return React.createElement(StoreCtx.Provider,{value:store},props.children);
}
function useStore(){return useContext(StoreCtx)}

function NotifProvider(props){
  const [notifs,setNotifs]=useState([]);
  const push=useCallback(function(msg,type,dur){
    type=type||'info';dur=dur||3800;
    const id=Date.now()+Math.random();
    setNotifs(function(n){return n.concat([{id:id,msg:msg,type:type}])});
    setTimeout(function(){setNotifs(function(n){return n.filter(function(x){return x.id!==id})})},dur);
  },[]);
  const dismiss=useCallback(function(id){setNotifs(function(n){return n.filter(function(x){return x.id!==id})})},[]);
  return React.createElement(NotifCtx.Provider,{value:{notifs:notifs,push:push,dismiss:dismiss}},props.children);
}
function useNotif(){return useContext(NotifCtx)}

function NavProvider(props){
  const [page,setPage]=useState('home');
  const [sidebarOpen,setSidebarOpen]=useState(false);
  const navigate=useCallback(function(p){setPage(p);setSidebarOpen(false)},[]);
  return React.createElement(NavCtx.Provider,{value:{page:page,navigate:navigate,sidebarOpen:sidebarOpen,setSidebarOpen:setSidebarOpen}},props.children);
}
function useNav(){return useContext(NavCtx)}

const NC={info:'var(--accent)',success:'var(--green)',error:'var(--red)',warning:'var(--accent)'};
function NotifStack(){
  const ctx=useNotif();
  if(!ctx.notifs.length)return null;
  return React.createElement('div',{style:{position:'fixed',top:0,left:0,right:0,zIndex:9000,pointerEvents:'none',display:'flex',flexDirection:'column'}},
    ctx.notifs.map(function(n){
      return React.createElement('div',{key:n.id,className:'notif-e',style:{background:'var(--card)',borderBottom:'2px solid '+(NC[n.type]||NC.info),padding:'.73em 1em',display:'flex',alignItems:'center',gap:10,pointerEvents:'all'}},
        React.createElement('div',{style:{flex:1,fontSize:'.86em',fontWeight:500,color:'var(--text)',lineHeight:1.4}},n.msg),
        React.createElement('button',{onClick:function(){ctx.dismiss(n.id)},style:{background:'none',border:'none',color:'var(--muted)',pointerEvents:'all',fontSize:'1.13em',lineHeight:1}},'\u00D7')
      );
    })
  );
}

function Card(props){return React.createElement('div',{className:'card',style:Object.assign({cursor:props.onClick?'pointer':'default'},props.style||{}),onClick:props.onClick},props.children)}
function MiniStat(props){return React.createElement('div',{style:{background:'var(--card2)',borderRadius:12,padding:'.8em .93em'}},React.createElement('div',{className:'sl',style:{marginBottom:4,color:props.color}},props.label),React.createElement('div',{className:'fm',style:{fontSize:'1.06em',fontWeight:600,color:props.color||'var(--text)'}},props.value),props.sub&&React.createElement('div',{className:'fm',style:{fontSize:'.6em',color:'var(--muted)',marginTop:3}},props.sub))}
function StatCard(props){return React.createElement('div',{onClick:props.onClick,style:{background:'var(--card)',border:'1px solid var(--border)',borderRadius:14,padding:'.93em 1.06em',cursor:props.onClick?'pointer':'default'}},React.createElement('div',{className:'sl',style:{marginBottom:6}},props.label),React.createElement('div',{className:'fm',style:{fontSize:'1.33em',fontWeight:600,color:props.color||'var(--text)',lineHeight:1.1}},props.value),props.sub&&React.createElement('div',{className:'fm',style:{fontSize:'.66em',color:'var(--muted)',marginTop:4}},props.sub))}
function ProgBar(props){const p=props.max>0?Math.min(100,Math.round((props.value/props.max)*100)):0;return React.createElement('div',{className:'prog-t'},React.createElement('div',{className:'prog-f',style:{width:p+'%',background:props.color||'var(--accent)'}}))}
function Toggle(props){return React.createElement('div',{className:'tog-t'+(props.on?' on':''),onClick:props.onChange},React.createElement('div',{className:'tog-th'}))}
function Field(props){return React.createElement('div',{style:{marginBottom:14}},props.label&&React.createElement('div',{className:'sl',style:{marginBottom:6}},props.label),props.children)}
function R2(props){return React.createElement('div',{style:{display:'flex',gap:props.gap||10,alignItems:'flex-start'}},props.children)}
function EmptyState(props){return React.createElement('div',{className:'afu',style:{textAlign:'center',padding:'2.93em 1.6em'}},React.createElement('div',{style:{fontSize:'.93em',fontWeight:600,color:'var(--text2)',marginBottom:6}},props.title),props.sub&&React.createElement('div',{style:{fontSize:'.8em',color:'var(--muted)',lineHeight:1.6,marginBottom:18,maxWidth:260,margin:'0 auto 18px'}},props.sub),props.action&&props.onAction&&React.createElement('button',{className:'btn-g',onClick:props.onAction,style:{fontSize:'.8em'}},props.action))}
function ModalSheet(props){return React.createElement('div',{className:'modal-ov',onClick:function(e){if(e.target===e.currentTarget)props.onClose()}},React.createElement('div',{className:'modal-sh'},React.createElement('div',{style:{display:'flex',alignItems:'center',justifyContent:'space-between',marginBottom:20}},React.createElement('div',{className:'fd',style:{fontSize:'1.26em',letterSpacing:2,color:'var(--text)'}},props.title),React.createElement('button',{onClick:props.onClose,className:'btn-g',style:{fontSize:'.8em',padding:'.4em .8em'}},'Close')),props.children))}

const NAV_SVG={
  home:React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.6,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('path',{d:'M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z'}),React.createElement('polyline',{points:'9 22 9 12 15 12 15 22'})),
  tasks:React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.6,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('polyline',{points:'9 11 12 14 22 4'}),React.createElement('path',{d:'M21 12v7a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h11'})),
  finance:React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.6,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('rect',{x:2,y:5,width:20,height:14,rx:2}),React.createElement('line',{x1:2,y1:10,x2:22,y2:10})),
  target:React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.6,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('circle',{cx:12,cy:12,r:10}),React.createElement('circle',{cx:12,cy:12,r:6}),React.createElement('circle',{cx:12,cy:12,r:2})),
  businesses:React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.6,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('rect',{x:2,y:7,width:20,height:14,rx:2}),React.createElement('path',{d:'M16 7V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v2'})),
  deadlines:React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.6,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('rect',{x:3,y:4,width:18,height:18,rx:2}),React.createElement('line',{x1:16,y1:2,x2:16,y2:6}),React.createElement('line',{x1:8,y1:2,x2:8,y2:6}),React.createElement('line',{x1:3,y1:10,x2:21,y2:10})),
  mealplanner:React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.6,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('path',{d:'M3 2v7c0 1.1.9 2 2 2h2a2 2 0 0 0 2-2V2'}),React.createElement('path',{d:'M7 2v20'}),React.createElement('path',{d:'M21 15V2a5 5 0 0 0-5 5v6c0 1.1.9 2 2 2h3zm0 0v7'})),
  contentstudio:React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.6,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('path',{d:'M12 19l7-7 3 3-7 7-3-3z'}),React.createElement('path',{d:'M18 13l-1.5-7.5L2 2l3.5 14.5L13 18l5-5z'}),React.createElement('circle',{cx:11,cy:11,r:2})),
  settings:React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.6,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('circle',{cx:12,cy:12,r:3}),React.createElement('path',{d:'M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83-2.83l.06-.06A1.65 1.65 0 0 0 4.68 15a1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 2.83-2.83l.06.06A1.65 1.65 0 0 0 9 4.68a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 2.83l-.06.06A1.65 1.65 0 0 0 19.4 9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z'}))
};
const NAV_ITEMS=[{id:'home',label:'Home'},{id:'tasks',label:'Tasks'},{id:'finance',label:'Finance'},{id:'target',label:'Target'},{id:'businesses',label:'Businesses'},{id:'deadlines',label:'Deadlines'},{id:'mealplanner',label:'Meal Planner'},{id:'contentstudio',label:'Content Studio'},{id:'settings',label:'Settings'}];

function Sidebar(){
  const nav=useNav();
  return React.createElement(React.Fragment,null,
    nav.sidebarOpen&&React.createElement('div',{onClick:function(){nav.setSidebarOpen(false)},style:{position:'fixed',inset:0,background:'rgba(0,0,0,.65)',zIndex:400}}),
    React.createElement('div',{style:{position:'fixed',top:0,bottom:0,left:0,width:230,background:'var(--card)',borderRight:'1px solid var(--border)',zIndex:500,display:'flex',flexDirection:'column',transform:nav.sidebarOpen?'translateX(0)':'translateX(-100%)',transition:'transform .24s cubic-bezier(.4,0,.2,1)',overflowY:'auto'}},
      React.createElement('div',{style:{padding:'3.46em 1.33em 1.2em',borderBottom:'1px solid var(--border)',display:'flex',justifyContent:'space-between',alignItems:'flex-start'}},
        React.createElement('div',null,React.createElement('div',{className:'fd',style:{fontSize:'1.73em',letterSpacing:6,color:'var(--accent)',lineHeight:1}},'COLE'),React.createElement('div',{className:'sl',style:{marginTop:5}},'Operating System')),
        React.createElement('button',{onClick:function(){nav.setSidebarOpen(false)},style:{background:'none',border:'none',color:'var(--muted)',fontSize:'1.2em',lineHeight:1}},'\u00D7')
      ),
      React.createElement('div',{style:{flex:1,paddingTop:8}},
        NAV_ITEMS.map(function(item){
          const active=nav.page===item.id;
          return React.createElement('div',{key:item.id,onClick:function(){nav.navigate(item.id)},style:{display:'flex',alignItems:'center',gap:12,padding:'.8em 1.33em',cursor:'pointer',background:active?'var(--card2)':'transparent',transition:'background .15s',position:'relative'}},
            active&&React.createElement('div',{style:{position:'absolute',left:0,top:0,bottom:0,width:2,background:'var(--accent)'}}),
            React.createElement('div',{style:{width:28,height:28,borderRadius:8,flexShrink:0,display:'flex',alignItems:'center',justifyContent:'center',color:active?'var(--accent)':'var(--muted)'}},NAV_SVG[item.id]),
            React.createElement('span',{style:{fontSize:'.9em',fontWeight:active?600:400,color:active?'var(--text)':'var(--text2)'}},item.label)
          );
        })
      ),
      React.createElement('div',{style:{padding:'.93em 1.33em',borderTop:'1px solid var(--border)'}},React.createElement('div',{className:'sl'},'Version 2.0'))
    )
  );
}

const PT={home:'COLE OS',tasks:'TASKS',finance:'FINANCE',target:'TARGET',businesses:'BUSINESSES',deadlines:'DEADLINES',mealplanner:'MEAL PLANNER',contentstudio:'CONTENT STUDIO',settings:'SETTINGS'};
function TopBar(){
  const nav=useNav();
  const store=useStore();
  return React.createElement('div',{style:{display:'flex',alignItems:'center',gap:13,padding:'3.2em 1.2em .8em',borderBottom:'1px solid var(--border)',background:'var(--bg)',flexShrink:0}},
    React.createElement('button',{onClick:function(){nav.setSidebarOpen(true)},style:{width:36,height:36,background:'var(--card)',border:'1px solid var(--border)',borderRadius:10,display:'flex',alignItems:'center',justifyContent:'center',flexShrink:0,color:'var(--text)'}},
      React.createElement('svg',{width:16,height:16,viewBox:'0 0 24 24',fill:'none',stroke:'currentColor',strokeWidth:1.7,strokeLinecap:'round'},React.createElement('line',{x1:3,y1:6,x2:21,y2:6}),React.createElement('line',{x1:3,y1:12,x2:21,y2:12}),React.createElement('line',{x1:3,y1:18,x2:21,y2:18}))
    ),
    React.createElement('div',{style:{flex:1}},React.createElement('div',{className:'fd',style:{fontSize:'1.06em',letterSpacing:3,color:'var(--text)',lineHeight:1}},PT[nav.page]||nav.page.toUpperCase()),store.settings.userName&&React.createElement('div',{className:'sl',style:{marginTop:2}},store.settings.userName+"'s workspace")),
    React.createElement('div',{className:'fm',style:{fontSize:'.6em',fontWeight:500,letterSpacing:.5,color:store.savedAt?'var(--green)':'var(--muted)'}},store.savedAt?'Saved':'')
  );
}

const EMPTY_TASK={text:'',tag:'personal',urgent:false,day:'',time:'',note:'',moneyType:'none',amount:'',business:'General',category:'other'};
const MONEY_TYPES=[{v:'none',l:'No Money'},{v:'income',l:'Income'},{v:'expense',l:'Expense'},{v:'credit',l:'Credit'},{v:'debit',l:'Debit'}];
function TaskModal(props){
  const store=useStore();const notif=useNotif();
  const isEdit=!!props.task;
  const [form,setForm]=useState(isEdit?Object.assign({},EMPTY_TASK,props.task,{amount:props.task.amount||''}):Object.assign({},EMPTY_TASK));
  const set=function(k,v){setForm(function(f){const nf=Object.assign({},f);nf[k]=v;return nf})};
  const hasMoney=form.moneyType!=='none';
  const submit=function(){
    if(!form.text.trim())return notif.push('Task text required','error');
    if(hasMoney&&!form.amount)return notif.push('Enter an amount for this task','error');
    if(isEdit){store.updateTask(props.task.id,form);notif.push('Task updated','success')}
    else{store.addTask(form);notif.push('Task added','success')}
    props.onClose();
  };
  return React.createElement(ModalSheet,{title:isEdit?'Edit Task':'Add Task',onClose:props.onClose},
    React.createElement(Field,{label:'Task'},React.createElement('input',{value:form.text,onChange:function(e){set('text',e.target.value)},placeholder:'What needs to be done?',autoFocus:true})),
    React.createElement(Field,{label:'Money Type'},React.createElement('div',{style:{display:'flex',gap:7,flexWrap:'wrap'}},MONEY_TYPES.map(function(m){return React.createElement('button',{key:m.v,onClick:function(){set('moneyType',m.v)},style:{padding:'.46em .86em',borderRadius:10,border:'1px solid',borderColor:form.moneyType===m.v?'var(--accent)':'var(--border2)',background:form.moneyType===m.v?'var(--accent-dim)':'var(--card2)',color:form.moneyType===m.v?'var(--accent)':'var(--muted)',fontSize:'.8em',fontWeight:500,cursor:'pointer'}},m.l)}))),
    hasMoney&&React.createElement('div',{style:{background:'var(--card2)',borderRadius:12,padding:'.93em',marginBottom:14}},
      React.createElement(Field,{label:'Amount (\u20A6)'},React.createElement('input',{type:'number',value:form.amount,onChange:function(e){set('amount',e.target.value)},placeholder:'0'})),
      React.createElement(R2,null,
        React.createElement('div',{style:{flex:1}},React.createElement(Field,{label:'Business'},React.createElement('select',{value:form.business,onChange:function(e){set('business',e.target.value)}},BUSINESSES.map(function(b){return React.createElement('option',{key:b,value:b},b)})))),
        React.createElement('div',{style:{flex:1}},React.createElement(Field,{label:'Category'},React.createElement('input',{value:form.category,onChange:function(e){set('category',e.target.value)},placeholder:'e.g. sales, rent'})))
      )
    ),
    React.createElement(R2,null,
      React.createElement('div',{style:{flex:1}},React.createElement(Field,{label:'Tag'},React.createElement('select',{value:form.tag,onChange:function(e){set('tag',e.target.value)}},[{v:'personal',l:'Personal'},{v:'urgent',l:'Urgent'},{v:'client',l:'Client'},{v:'business',l:'Business'},{v:'content',l:'Content'},{v:'admin',l:'Admin'}].map(function(t){return React.createElement('option',{key:t.v,value:t.v},t.l)})))),
      React.createElement('div',{style:{flex:1}},React.createElement(Field,{label:'Day'},React.createElement('select',{value:form.day,onChange:function(e){set('day',e.target.value)}},React.createElement('option',{value:''},'No day'),DAYS.map(function(d){return React.createElement('option',{key:d,value:d},d)}))))
    ),
    React.createElement(R2,null,
      React.createElement('div',{style:{flex:1}},React.createElement(Field,{label:'Time'},React.createElement('input',{type:'time',value:form.time,onChange:function(e){set('time',e.target.value)}}))),
      React.createElement('div',{style:{flex:1,display:'flex',alignItems:'center',gap:8,paddingTop:22}},React.createElement('input',{type:'checkbox',id:'urg-cb',checked:form.urgent,onChange:function(e){set('urgent',e.target.checked)},style:{width:'auto',margin:0}}),React.createElement('label',{htmlFor:'urg-cb',style:{fontSize:'.86em',color:'var(--text)',cursor:'pointer'}},'Urgent'))
    ),
    React.createElement(Field,{label:'Note'},React.createElement('textarea',{value:form.note,onChange:function(e){set('note',e.target.value)},rows:2,placeholder:'Optional context, used as Finance reference'})),
    React.createElement('button',{className:'btn-p',onClick:submit,style:{marginTop:4}},isEdit?'Save Changes':'Add Task')
  );
}

function HomePage(){
  const store=useStore();const nav=useNav();
  const balance=store.getBalance(),income=store.getIncome(),expense=store.getExpense();
  const progress=store.getProgress(),remaining=store.getRemaining(),hasTarget=store.target.total>0;
  const pendingTasks=store.tasks.filter(function(t){return !t.done});
  const urgentTasks=store.tasks.filter(function(t){return t.urgent&&!t.done});
  const upcomingDl=store.deadlines.filter(function(d){return !d.done}).sort(function(a,b){return new Date(a.date)-new Date(b.date)}).slice(0,3);
  const recentTxns=store.transactions.slice().sort(function(a,b){return new Date(b.date)-new Date(a.date)}).slice(0,4);
  const isEmpty=store.tasks.length===0&&store.transactions.length===0;
  const quote=useMemo(function(){return getDailyQuote()},[]);
  const perf=store.getMonthlyPerformance();

  return React.createElement('div',{className:'sc',style:{flex:1,paddingBottom:60}},
    React.createElement('div',{style:{padding:'.53em 1.2em 1.06em'}},React.createElement('div',{className:'fd',style:{fontSize:'1.53em',letterSpacing:1.5,color:'var(--text)',lineHeight:1.1}},getGreeting(store.settings.userName)),React.createElement('div',{className:'sl',style:{marginTop:5}},getFullDateLabel())),

    React.createElement('div',{style:{margin:'0 1.2em 1.06em'}},
      React.createElement(Card,{style:{background:'linear-gradient(135deg,var(--card),var(--card2))'}},
        React.createElement('div',{className:'sl',style:{marginBottom:8}},'Daily Motivation'),
        React.createElement('div',{style:{fontSize:'.93em',color:'var(--text)',lineHeight:1.6,fontStyle:'italic',marginBottom:6}},'"'+quote.text+'"'),
        React.createElement('div',{style:{fontSize:'.73em',color:'var(--muted)'}},'\u2014 '+quote.author)
      )
    ),

    isEmpty&&React.createElement('div',{style:{margin:'0 1.2em 1.06em'}},React.createElement(Card,{style:{background:'var(--card2)',border:'none'}},React.createElement('div',{style:{fontSize:'.86em',fontWeight:600,color:'var(--text)',marginBottom:8}},'Welcome to Cole OS'),React.createElement('div',{style:{fontSize:'.8em',color:'var(--text2)',lineHeight:1.6,marginBottom:16}},'Set a target, add tasks, and log finance. Completed tasks with money attached post automatically.'),React.createElement('div',{style:{display:'flex',gap:8,flexWrap:'wrap'}},[['Set Target','target'],['Add Task','tasks'],['Finance','finance']].map(function(pair){return React.createElement('button',{key:pair[1],className:'btn-g',onClick:function(){nav.navigate(pair[1])},style:{fontSize:'.8em'}},pair[0])})))),

    hasTarget&&React.createElement('div',{style:{margin:'0 1.2em 1.06em'}},React.createElement('div',{onClick:function(){nav.navigate('target')},style:{background:'var(--card)',border:'1px solid var(--border)',borderRadius:18,padding:'1.33em 1.46em',cursor:'pointer'}},React.createElement('div',{className:'sl',style:{marginBottom:6}},store.target.label||'Target Progress'),React.createElement('div',{style:{display:'flex',justifyContent:'space-between',alignItems:'flex-end',marginBottom:14}},React.createElement('div',null,React.createElement('div',{className:'fm',style:{fontSize:'1.86em',fontWeight:600,color:'var(--text)',lineHeight:1}},fmt(balance)),React.createElement('div',{className:'fm',style:{fontSize:'.66em',color:'var(--muted)',marginTop:4}},'of '+fmt(store.target.total))),React.createElement('div',{style:{textAlign:'right'}},React.createElement('div',{className:'fm',style:{fontSize:'1.73em',fontWeight:600,color:'var(--accent)',lineHeight:1}},progress+'%'),React.createElement('div',{className:'fm',style:{fontSize:'.6em',color:'var(--muted)',marginTop:3}},fmt(remaining)+' left'))),React.createElement(ProgBar,{value:balance,max:store.target.total,color:'var(--accent)'}))),

    React.createElement('div',{style:{display:'grid',gridTemplateColumns:'1fr 1fr',gap:10,margin:'0 1.2em 1.06em'}},React.createElement(StatCard,{label:'Balance',value:fmt(balance),onClick:function(){nav.navigate('finance')}}),React.createElement(StatCard,{label:'Active Tasks',value:pendingTasks.length,sub:urgentTasks.length>0?(urgentTasks.length+' urgent'):'all clear',onClick:function(){nav.navigate('tasks')}})),
    React.createElement('div',{style:{display:'grid',gridTemplateColumns:'1fr 1fr',gap:10,margin:'0 1.2em 1.06em'}},React.createElement(MiniStat,{label:'Income',value:fmt(income),color:'var(--green)'}),React.createElement(MiniStat,{label:'Expense',value:fmt(expense),color:'var(--red)'})),

    React.createElement('div',{style:{margin:'0 1.2em 1.06em'}},
      React.createElement('div',{className:'sl',style:{marginBottom:10}},'Monthly Performance \u2014 '+perf.monthLabel),
      React.createElement(Card,null,
        React.createElement('div',{style:{display:'flex',justifyContent:'space-between',alignItems:'baseline',marginBottom:14}},
          React.createElement('div',null,React.createElement('div',{className:'fm',style:{fontSize:'1.6em',fontWeight:600,color:'var(--text)'}},perf.tasksCompleted),React.createElement('div',{className:'sl',style:{marginTop:2}},'Tasks Completed')),
          React.createElement('div',{style:{textAlign:'right'}},React.createElement('div',{className:'fm',style:{fontSize:'1.33em',fontWeight:600,color:'var(--accent)'}},perf.completionRate+'%'),React.createElement('div',{className:'sl',style:{marginTop:2}},'Completion Rate'))
        ),
        React.createElement('div',{style:{display:'grid',gridTemplateColumns:'1fr 1fr',gap:8,marginBottom:14}},
          React.createElement(MiniStat,{label:'Income',value:fmt(perf.income),color:'var(--green)'}),
          React.createElement(MiniStat,{label:'Expense',value:fmt(perf.expense),color:'var(--red)'})
        ),
        React.createElement('div',{className:'sl',style:{marginBottom:8}},'Weekly Breakdown'),
        React.createElement('div',{style:{display:'flex',gap:6,alignItems:'flex-end',height:60}},
          perf.weeklyBreakdown.map(function(w,i){
            const max=Math.max.apply(null,perf.weeklyBreakdown.map(function(x){return x.count}).concat([1]));
            const h=Math.max(6,Math.round((w.count/max)*54));
            return React.createElement('div',{key:i,style:{flex:1,display:'flex',flexDirection:'column',alignItems:'center',gap:5}},
              React.createElement('div',{style:{width:'100%',height:h,background:'var(--accent)',borderRadius:4,opacity:.85}}),
              React.createElement('div',{className:'sl',style:{fontSize:'.53em'}},w.label.replace('Week ','W'))
            );
          })
        )
      )
    ),

    recentTxns.length>0&&React.createElement('div',{style:{margin:'0 1.2em 1.06em'}},React.createElement('div',{style:{display:'flex',justifyContent:'space-between',alignItems:'baseline',marginBottom:10}},React.createElement('div',{className:'sl'},'Recent Transactions'),React.createElement('div',{onClick:function(){nav.navigate('finance')},style:{fontSize:'.73em',color:'var(--accent)',cursor:'pointer'}},'View all')),React.createElement(Card,null,recentTxns.map(function(t,i){const tc=TXN_TYPES.find(function(x){return x.v===t.type});const sign=(t.type==='income'||t.type==='credit')?'+':'\u2212';return React.createElement('div',{key:t.id,className:'txn-row',style:{borderBottom:i<recentTxns.length-1?'1px solid var(--border)':'none'}},React.createElement('div',{style:{flex:1}},React.createElement('div',{style:{fontSize:'.86em',fontWeight:500,color:'var(--text)'}},t.title)),React.createElement('div',{className:'fm',style:{fontSize:'.86em',fontWeight:600,color:tc.color}},sign+fmt(t.amount)))}))),

    urgentTasks.length>0&&React.createElement('div',{style:{margin:'0 1.2em 1.06em'}},React.createElement('div',{className:'sl',style:{marginBottom:10}},'Urgent'),React.createElement(Card,null,urgentTasks.slice(0,4).map(function(t,i){return React.createElement('div',{key:t.id,className:'txn-row',style:{borderBottom:i<Math.min(urgentTasks.length,4)-1?'1px solid var(--border)':'none'}},React.createElement('div',{style:{width:5,height:5,borderRadius:'50%',background:'var(--red)',flexShrink:0}}),React.createElement('div',{style:{flex:1,fontSize:'.86em',fontWeight:500,color:'var(--text)'}},t.text))}))),

    upcomingDl.length>0&&React.createElement('div',{style:{margin:'0 1.2em 1.06em'}},React.createElement('div',{className:'sl',style:{marginBottom:10}},'Upcoming Deadlines'),React.createElement(Card,null,upcomingDl.map(function(d,i){const dl=getDaysUntil(d.date);return React.createElement('div',{key:d.id,className:'txn-row',style:{borderBottom:i<upcomingDl.length-1?'1px solid var(--border)':'none'}},React.createElement('div',{style:{flex:1,fontSize:'.86em',color:'var(--text)'}},d.title),d.amount>0&&React.createElement('div',{className:'fm',style:{fontSize:'.73em',color:'var(--accent)'}},fmt(d.amount)),React.createElement('div',{className:'fm',style:{fontSize:'.6em',fontWeight:600,color:(dl!==null&&dl<0)?'var(--red)':dl===0?'var(--accent)':'var(--muted)'}},dl===null?'':dl<0?'Overdue':dl===0?'Today':(dl+'d')))})))
  );
}

function TaskRow(props){
  const store=useStore();
  const task=props.task;
  const tagColors={personal:'var(--blue)',urgent:'var(--red)',client:'var(--green)',business:'var(--accent)',admin:'var(--muted)',content:'var(--purple)'};
  const hasMoney=task.moneyType&&task.moneyType!=='none';
  const tc=TXN_TYPES.find(function(x){return x.v===task.moneyType});
  const handleToggle=function(){store.toggleTask(task.id)};
  return React.createElement('div',{style:{display:'flex',alignItems:'flex-start',gap:11,padding:'.93em 0',borderBottom:'1px solid var(--border)',opacity:task.done?.6:1}},
    React.createElement('button',{onClick:handleToggle,style:{background:task.done?'var(--accent)':'transparent',border:'1.5px solid',borderColor:task.done?'var(--accent)':(task.urgent?'var(--red)':'var(--border2)'),borderRadius:6,width:19,height:19,flexShrink:0,marginTop:1,padding:0,display:'flex',alignItems:'center',justifyContent:'center'}},task.done&&React.createElement('svg',{width:11,height:11,viewBox:'0 0 24 24',fill:'none',stroke:'#0a0a0b',strokeWidth:3,strokeLinecap:'round',strokeLinejoin:'round'},React.createElement('polyline',{points:'20 6 9 17 4 12'}))),
    React.createElement('div',{style:{flex:1,minWidth:0}},
      React.createElement('div',{style:{fontSize:'.93em',fontWeight:(task.urgent&&!task.done)?600:500,color:task.done?'var(--muted)':'var(--text)',textDecoration:task.done?'line-through':'none',lineHeight:1.35}},task.text),
      React.createElement('div',{style:{display:'flex',alignItems:'center',gap:6,marginTop:6,flexWrap:'wrap'}},
        React.createElement('span',{style:{fontSize:'.6em',padding:'.26em .6em',borderRadius:6,background:(tagColors[task.tag]||'var(--muted)')+'15',color:tagColors[task.tag]||'var(--muted)',fontWeight:500}},task.tag),
        hasMoney&&React.createElement('span',{style:{fontSize:'.6em',padding:'.26em .6em',borderRadius:6,background:tc.color+'15',color:tc.color,fontWeight:700,textTransform:'uppercase',letterSpacing:.3}},tc.l),
        (task.day||task.time)&&React.createElement('span',{className:'fm',style:{fontSize:'.66em',color:'var(--muted)'}},task.day+(task.day&&task.time?' \u00B7 ':'')+task.time)
      ),
      hasMoney&&React.createElement('div',{className:'fm',style:{fontSize:'1em',fontWeight:700,color:tc.color,marginTop:6}},fmt(parseAmt(task.amount)))
    ),
    React.createElement('div',{style:{display:'flex',gap:3,flexShrink:0}},React.createElement('button',{onClick:function(){props.onEdit(task)},style:{background:'none',border:'none',color:'var(--muted)',padding:5,fontSize:'.73em'}},'Edit'),React.createElement('button',{onClick:function(){if(confirm('Delete task?'))store.deleteTask(task.id)},style:{background:'none',border:'none',color:'var(--red)',opacity:.65,padding:5,fontSize:'.73em'}},'Delete'))
  );
}

function TasksPage(){
  const store=useStore();
  const [showAdd,setShowAdd]=useState(false);const [editTask,setEditTask]=useState(null);
  const [filter,setFilter]=useState('all');
  const total=store.tasks.length,done=store.tasks.filter(function(t){return t.done}).length;
  const filtered=store.tasks.filter(function(t){
    if(filter==='all')return true;
    if(filter==='pending')return !t.done;
    if(filter==='done')return t.done;
    if(filter==='money')return t.moneyType&&t.moneyType!=='none';
    return t.tag===filter;
  });
  const pending=filtered.filter(function(t){return !t.done}),completed=filtered.filter(function(t){return t.done});
  return React.createElement('div',{className:'sc',style:{flex:1}},
    React.createElement('div',{style:{padding:'.66em 1.2em .8em'}},React.createElement('div',{style:{display:'flex',justifyContent:'space-between',marginBottom:7}},React.createElement('div',{className:'sl'},done+'/'+total+' completed'),React.createElement('div',{className:'fm',style:{fontSize:'.73em',fontWeight:600,color:'var(--accent)'}},(total>0?Math.round((done/total)*100):0)+'%')),React.createElement(ProgBar,{value:done,max:total||1,color:'var(--accent)'})),
    React.createElement('div',{style:{padding:'0 1.2em .8em'}},React.createElement('button',{className:'btn-p',onClick:function(){setShowAdd(true)}},'Add Task')),
    React.createElement('div',{style:{display:'flex',gap:7,padding:'0 1.2em',marginBottom:14,overflowX:'auto'}},[{v:'all',l:'All'},{v:'pending',l:'Pending'},{v:'money',l:'Has Money'},{v:'done',l:'Done'},{v:'client',l:'Client'},{v:'content',l:'Content'}].map(function(f){return React.createElement('button',{key:f.v,className:'chip'+(filter===f.v?' on':''),onClick:function(){setFilter(f.v)}},f.l)})),
    React.createElement('div',{style:{padding:'0 1.2em 2.66em'}},
      filtered.length===0?React.createElement(EmptyState,{title:'No tasks',sub:'Add a task, attach money to it and completing it posts straight to Finance.',action:'Add Task',onAction:function(){setShowAdd(true)}}):
      React.createElement(React.Fragment,null,
        pending.length>0&&React.createElement(React.Fragment,null,React.createElement('div',{className:'sl',style:{marginBottom:4}},'Pending \u2014 '+pending.length),pending.map(function(t){return React.createElement(TaskRow,{key:t.id,task:t,onEdit:setEditTask})})),
        completed.length>0&&React.createElement(React.Fragment,null,React.createElement('div',{className:'sl',style:{margin:'16px 0 4px'}},'Completed \u2014 '+completed.length),completed.map(function(t){return React.createElement(TaskRow,{key:t.id,task:t,onEdit:setEditTask})}))
      )
    ),
    showAdd&&React.createElement(TaskModal,{onClose:function(){setShowAdd(false)}}),
    editTask&&React.createElement(TaskModal,{task:editTask,onClose:function(){setEditTask(null)}})
  );
}

function TxnModal(props){
  const store=useStore();const notif=useNotif();
  const [form,setForm]=useState({title:'',type:'income',business:'General',category:'other',amount:'',date:todayStr(),reference:''});
  const set=function(k,v){setForm(function(f){const nf=Object.assign({},f);nf[k]=v;return nf})};
  const submit=function(){
    if(!form.title.trim())return notif.push('Enter a title','error');
    if(!form.amount||parseAmt(form.amount)<=0)return notif.push('Enter a valid amount','error');
    store.postTransaction(Object.assign({},form,{source:'manual'}));
    notif.push(form.title+' logged','success');
    props.onClose();
  };
  return React.createElement(ModalSheet,{title:'Log Transaction',onClose:props.onClose},
    React.createElement(Field,{label:'Title'},React.createElement('input',{value:form.title,onChange:function(e){set('title',e.target.value)},placeholder:'e.g. Client payment, Fuel, Rent',autoFocus:true})),
    React.createElement(Field,{label:'Type'},React.createElement('div',{style:{display:'flex',gap:7,flexWrap:'wrap'}},TXN_TYPES.map(function(t){return React.createElement('button',{key:t.v,onClick:function(){set('type',t.v)},style:{flex:'1 1 70px',padding:9,borderRadius:10,border:'1px solid',borderColor:form.type===t.v?t.color:'var(--border2)',background:form.type===t.v?(t.color+'15'):'var(--card2)',color:form.type===t.v?t.color:'var(--muted)',fontWeight:600,fontSize:'.8em'}},t.l)}))),
    React.createElement(R2,null,React.createElement('div',{style:{flex:1}},React.createElement(Field,{label:'Amount (\u20A6)'},React.createElement('input',{type:'number',value:form.amount,onChange:function(e){set('amount',e.target.value)},placeholder:'0'}))),React.createElement('div',{style:{flex:1}},React.createElement(Field,{label:'Date'},React.createElement('input',{type:'date',value:form.date,onChange:function(e){set('date',e.target.value)}})))),
    React.createElement(Field,{label:'Business'},React.createElement('select',{value:form.business,onChange:function(e){set('business',e.target.value)}},BUSINESSES.map(function(b){return React.createElement('option',{key:b,value:b},b)}))),
    React.createElement(Field,{label:'Reference'},React.createElement('input',{value:form.reference,onChange:function(e){set('reference',e.target.value)},placeholder:'Optional note about this transaction'})),
    React.createElement('button',{className:'btn-p',onClick:submit},'Log Transaction')
  );
}

function TxnRow(props){
  const txn=props.txn;
  const tc=TXN_TYPES.find(function(x){return x.v===txn.type});
  const sign=(txn.type==='income'||txn.type==='credit')?'+':'\u2212';
  return React.createElement('div',{className:'txn-row'},
    React.createElement('div',{style:{flex:1,minWidth:0}},
      React.createElement('div',{style:{fontSize:'.93em',fontWeight:500,color:'var(--text)',lineHeight:1.3}},txn.title),
      React.createElement('div',{style:{display:'flex',gap:8,alignItems:'center',marginTop:4}},
        React.createElement('span',{style:{fontSize:'.6em',padding:'.2em .5em',borderRadius:6,background:tc.color+'15',color:tc.color,fontWeight:600,textTransform:'uppercase',letterSpacing:.3}},tc.l),
        React.createElement('span',{className:'fm',style:{fontSize:'.66em',color:'var(--muted)'}},fmtDate(txn.date))
      ),
      txn.reference&&React.createElement('div',{style:{marginTop:6}},React.createElement('div',{className:'sl',style:{marginBottom:2,fontSize:'.6em'}},'Reference'),React.createElement('div',{style:{fontSize:'.8em',color:'var(--text2)',lineHeight:1.5}},txn.reference))
    ),
    React.createElement('div',{style:{textAlign:'right',flexShrink:0}},
      React.createElement('div',{className:'fm',style:{fontSize:'.93em',fontWeight:600,color:tc.color}},sign+fmt(txn.amount)),
      txn.source!=='task'&&React.createElement('button',{onClick:function(){props.onDelete(txn.id)},style:{background:'none',border:'none',color:'var(--muted)',fontSize:'.66em',padding:'.2em 0',marginTop:4}},'Remove')
    )
  );
}

function FinancePage(){
  const store=useStore();const notif=useNotif();
  const [showAdd,setShowAdd]=useState(false);
  const [typeFilter,setTypeFilter]=useState('all');
  const [search,setSearch]=useState('');

  const balance=store.getBalance(),income=store.getIncome(),expense=store.getExpense(),credit=store.getCredit(),debit=store.getDebit();

  const filtered=useMemo(function(){
    let txns=store.transactions.slice().sort(function(a,b){return new Date(b.date)-new Date(a.date)});
    if(typeFilter!=='all')txns=txns.filter(function(t){return t.type===typeFilter});
    if(search.trim())txns=txns.filter(function(t){return t.title.toLowerCase().indexOf(search.toLowerCase())>-1});
    return txns;
  },[store.transactions,typeFilter,search]);

  const handleDelete=function(id){if(confirm('Remove this transaction?')){store.removeTransaction(id);notif.push('Transaction removed','info')}};

  return React.createElement('div',{className:'sc',style:{flex:1}},
    React.createElement('div',{style:{margin:'.66em 1.2em 1.06em'}},
      React.createElement('div',{style:{background:'var(--card)',border:'1px solid var(--border)',borderRadius:18,padding:'1.46em'}},
        React.createElement('div',{className:'sl',style:{marginBottom:8}},'Current Balance'),
        React.createElement('div',{className:'fm',style:{fontSize:'2.26em',fontWeight:600,color:'var(--text)',lineHeight:1}},fmt(balance))
      )
    ),
    React.createElement('div',{style:{display:'grid',gridTemplateColumns:'repeat(4,1fr)',gap:8,margin:'0 1.2em 1.06em'}},
      React.createElement(MiniStat,{label:'Income',value:fmt(income),color:'var(--green)'}),
      React.createElement(MiniStat,{label:'Expense',value:fmt(expense),color:'var(--red)'}),
      React.createElement(MiniStat,{label:'Credit',value:fmt(credit),color:'var(--blue)'}),
      React.createElement(MiniStat,{label:'Debit',value:fmt(debit),color:'var(--accent)'})
    ),
    React.createElement('div',{style:{padding:'0 1.2em .8em'}},React.createElement('button',{className:'btn-p',onClick:function(){setShowAdd(true)}},'Log Transaction')),
    React.createElement('div',{style:{padding:'0 1.2em .66em'}},React.createElement('input',{value:search,onChange:function(e){setSearch(e.target.value)},placeholder:'Search transactions...'})),
    React.createElement('div',{style:{display:'flex',gap:7,padding:'0 1.2em',marginBottom:16,overflowX:'auto'}},[{v:'all',l:'All'}].concat(TXN_TYPES.map(function(t){return{v:t.v,l:t.l}})).map(function(f){return React.createElement('button',{key:f.v,className:'chip'+(typeFilter===f.v?' on':''),onClick:function(){setTypeFilter(f.v)}},f.l)})),
    React.createElement('div',{style:{padding:'0 1.2em 2.66em'}},
      filtered.length===0?React.createElement(EmptyState,{title:'No transactions',sub:'Log income, expenses, credit or debit here, or complete a task with money attached.',action:'Log Transaction',onAction:function(){setShowAdd(true)}}):
      React.createElement(Card,{style:{padding:'.26em 1.06em'}},filtered.map(function(t){return React.createElement(TxnRow,{key:t.id,txn:t,onDelete:handleDelete})}))
    ),
    showAdd&&React.createElement(TxnModal,{onClose:function(){setShowAdd(false)}})
  );
}

function SetTargetModal(props){
  const store=useStore();const notif=useNotif();
  const [total,setTotal]=useState(store.target.total>0?String(store.target.total):'');
  const [startBal,setStartBal]=useState(store.target.startingBalance>0?String(store.target.startingBalance):'');
  const [label,setLabel]=useState(store.target.label||'');
  const submit=function(){const t=parseAmt(total);if(!t)return notif.push('Enter a target amount','error');store.setTarget(t,parseAmt(startBal),label);notif.push('Target set','success');props.onClose()};
  return React.createElement(ModalSheet,{title:'Set Target',onClose:props.onClose},
    React.createElement(Field,{label:'Target Amount (\u20A6)'},React.createElement('input',{type:'number',value:total,onChange:function(e){setTotal(e.target.value)},placeholder:'e.g. 500000',autoFocus:true})),
    React.createElement(Field,{label:'Starting Balance (\u20A6)'},React.createElement('input',{type:'number',value:startBal,onChange:function(e){setStartBal(e.target.value)},placeholder:'What you have now'})),
    React.createElement(Field,{label:'Label'},React.createElement('input',{value:label,onChange:function(e){setLabel(e.target.value)},placeholder:'e.g. Monthly Target'})),
    React.createElement('button',{className:'btn-p',onClick:submit},'Set Target')
  );
}

function TargetPage(){
  const store=useStore();const[showSet,setShowSet]=useState(false);
  const progress=store.getProgress(),balance=store.getBalance(),remaining=store.getRemaining();
  const income=store.getIncome(),hasTarget=store.target.total>0;
  return React.createElement('div',{className:'sc',style:{flex:1}},
    React.createElement('div',{style:{padding:'.66em 1.2em 2.66em'}},
      React.createElement('div',{style:{display:'flex',justifyContent:'flex-end',marginBottom:14}},React.createElement('button',{className:'btn-g',onClick:function(){setShowSet(true)}},hasTarget?'Edit Target':'Set Target')),
      !hasTarget?React.createElement(Card,null,React.createElement(EmptyState,{title:'No target set',sub:'Set a target and starting balance, progress updates automatically as transactions are logged.',action:'Set Target',onAction:function(){setShowSet(true)}})):
      React.createElement(Card,null,
        React.createElement('div',{className:'sl',style:{marginBottom:6}},store.target.label||'Target Progress'),
        React.createElement('div',{style:{display:'flex',justifyContent:'space-between',alignItems:'flex-end',marginBottom:16}},
          React.createElement('div',null,React.createElement('div',{className:'fm',style:{fontSize:'1.86em',fontWeight:600,color:'var(--text)',lineHeight:1}},fmt(balance)),React.createElement('div',{className:'fm',style:{fontSize:'.66em',color:'var(--muted)',marginTop:4}},'of '+fmt(store.target.total))),
          React.createElement('div',{style:{textAlign:'right'}},React.createElement('div',{className:'fm',style:{fontSize:'2.13em',fontWeight:600,color:progress>=100?'var(--green)':'var(--accent)',lineHeight:1}},progress+'%'),React.createElement('div',{className:'fm',style:{fontSize:'.6em',color:'var(--muted)',marginTop:3}},progress>=100?'Target reached':'in progress'))
        ),
        React.createElement(ProgBar,{value:balance,max:store.target.total,color:progress>=100?'var(--green)':'var(--accent)'}),
        React.createElement('div',{style:{display:'grid',gridTemplateColumns:'repeat(3,1fr)',gap:8,marginTop:16}},[{l:'Starting',v:fmt(store.target.startingBalance)},{l:'Income',v:fmt(income),c:'var(--green)'},{l:'Remaining',v:fmt(remaining),c:'var(--red)'}].map(function(s){return React.createElement('div',{key:s.l,style:{background:'var(--card2)',borderRadius:10,padding:'.66em',textAlign:'center'}},React.createElement('div',{className:'sl',style:{marginBottom:4,color:s.c}},s.l),React.createElement('div',{className:'fm',style:{fontSize:'.86em',fontWeight:600,color:s.c||'var(--text)'}},s.v))}))
      )
    ),
    showSet&&React.createElement(SetTargetModal,{onClose:function(){setShowSet(false)}})
  );
}

function BusinessesPage(){
  const store=useStore();
  const bizList=BUSINESSES.filter(function(b){return b!=='General'});
  return React.createElement('div',{className:'sc',style:{flex:1}},
    React.createElement('div',{style:{padding:'.66em 1.2em 2.66em'}},
      bizList.map(function(biz){
        const stats=store.getBusinessStats(biz);
        return React.createElement(Card,{key:biz,style:{marginBottom:14}},
          React.createElement('div',{style:{fontSize:'1em',fontWeight:600,color:'var(--text)',marginBottom:14}},biz),
          React.createElement('div',{style:{display:'grid',gridTemplateColumns:'repeat(3,1fr)',gap:8}},
            React.createElement(MiniStat,{label:'Income',value:fmt(stats.income),color:'var(--green)'}),
            React.createElement(MiniStat,{label:'Expense',value:fmt(stats.expense),color:'var(--red)'}),
            React.createElement(MiniStat,{label:'Net',value:fmt(stats.net),color:stats.net>=0?'var(--green)':'var(--red)'})
          )
        );
      })
    )
  );
}

function DeadlineModal(props){
  const store=useStore();const notif=useNotif();
  const [form,setForm]=useState({title:'',date:'',amount:'',category:'general',urgent:false,note:''});
  const set=function(k,v){setForm(function(f){const nf=Object.assign({},f);nf[k]=v;return nf})};
  const submit=function(){if(!form.title||!form.date)return notif.push('Title and date required','error');store.addDeadline(form);notif.push('Deadline added','success');props.onClose()};
  return React.createElement(ModalSheet,{title:'Add Deadline',onClose:props.onClose},
    React.createElement(Field,{label:'Title'},React.createElement('input',{value:form.title,onChange:function(e){set('title',e.target.value)},placeholder:'e.g. Pay rent',autoFocus:true})),
    React.createElement(R2,null,React.createElement('div',{style:{flex:1}},React.createElement(Field,{label:'Date'},React.createElement('input',{type:'date',value:form.date,onChange:function(e){set('date',e.target.value)}}))),React.createElement('div',{style:{flex:1}},React.createElement(Field,{label:'Amount (optional)'},React.createElement('input',{type:'number',value:form.amount,onChange:function(e){set('amount',e.target.value)},placeholder:'\u20A6'})))),
    React.createElement('div',{style:{display:'flex',alignItems:'center',gap:9,marginBottom:14}},React.createElement('input',{type:'checkbox',id:'dl-urg',checked:form.urgent,onChange:function(e){set('urgent',e.target.checked)},style:{width:'auto',margin:0}}),React.createElement('label',{htmlFor:'dl-urg',style:{fontSize:'.86em',color:'var(--text)'}},'Urgent')),
    React.createElement(Field,{label:'Note'},React.createElement('textarea',{value:form.note,onChange:function(e){set('note',e.target.value)},rows:2})),
    React.createElement('button',{className:'btn-p',onClick:submit},'Add Deadline')
  );
}

function DeadlinesPage(){
  const store=useStore();const notif=useNotif();
  const [showAdd,setShowAdd]=useState(false);
  const sorted=store.deadlines.slice().sort(function(a,b){if(a.done!==b.done)return a.done?1:-1;const da=getDaysUntil(a.date);const db=getDaysUntil(b.date);return(da===null?9999:da)-(db===null?9999:db)});
  return React.createElement('div',{className:'sc',style:{flex:1}},
    React.createElement('div',{style:{padding:'.66em 1.2em .8em'}},React.createElement('button',{className:'btn-p',onClick:function(){setShowAdd(true)}},'Add Deadline')),
    React.createElement('div',{style:{padding:'0 1.2em 2.66em'}},
      sorted.length===0?React.createElement(EmptyState,{title:'No deadlines',sub:'Track payment deadlines and important dates here.'}):
      React.createElement(Card,{style:{padding:'.26em 1.06em'}},sorted.map(function(d,i){
        const dl=getDaysUntil(d.date),isOverdue=!d.done&&dl!==null&&dl<0;
        return React.createElement('div',{key:d.id,className:'txn-row',style:{opacity:d.done?.5:1}},
          React.createElement('button',{onClick:function(){store.toggleDeadline(d.id);notif.push(d.done?'Reopened':'Done','success')},style:{background:d.done?'var(--accent)':'transparent',border:'1.5px solid',borderColor:d.done?'var(--accent)':isOverdue?'var(--red)':'var(--border2)',borderRadius:6,width:18,height:18,flexShrink:0}}),
          React.createElement('div',{style:{flex:1}},React.createElement('div',{style:{fontSize:'.86em',fontWeight:500,color:d.done?'var(--muted)':'var(--text)',textDecoration:d.done?'line-through':'none'}},d.title),React.createElement('div',{className:'fm',style:{fontSize:'.66em',color:isOverdue?'var(--red)':'var(--muted)',marginTop:2}},fmtDate(d.date))),
          d.amount>0&&React.createElement('div',{className:'fm',style:{fontSize:'.86em',fontWeight:600,color:'var(--accent)'}},fmt(d.amount)),
          React.createElement('button',{onClick:function(){if(confirm('Delete?')){store.deleteDeadline(d.id);notif.push('Deleted','info')}},style:{background:'none',border:'none',color:'var(--red)',opacity:.6,fontSize:'.73em',marginLeft:8}},'Delete')
        );
      }))
    ),
    showAdd&&React.createElement(DeadlineModal,{onClose:function(){setShowAdd(false)}})
  );
}

function MealPlannerPage(){
  const notif=useNotif();
  const [plan,setPlan]=useState(null);
  const [budget,setBudget]=useState('mid');
  const [days,setDays]=useState(7);
  const [seed,setSeed]=useState(0);

  const BUDGET_LABELS={low:'Budget-friendly',mid:'Mid-range',high:'Premium'};

  const generate=function(){
    const nextSeed=seed+1;
    setSeed(nextSeed);
    const result=generateMealPlanTemplate(budget,days,nextSeed);
    setPlan(result);
    notif.push(plan?'New meal plan generated':'Meal plan generated','success');
  };

  return React.createElement('div',{className:'sc',style:{flex:1}},
    React.createElement('div',{style:{padding:'.66em 1.2em 2.66em'}},
      React.createElement(Card,{style:{marginBottom:16}},
        React.createElement('div',{className:'sl',style:{marginBottom:12}},'Generate Plan'),
        React.createElement(Field,{label:'Days'},React.createElement('div',{style:{display:'flex',gap:7}},[3,5,7].map(function(d){return React.createElement('button',{key:d,onClick:function(){setDays(d)},style:{flex:1,padding:9,borderRadius:10,border:'1px solid',borderColor:days===d?'var(--accent)':'var(--border2)',background:days===d?'var(--accent-dim)':'var(--card2)',color:days===d?'var(--accent)':'var(--muted)',fontWeight:600}},d+' days')}))),
        React.createElement(Field,{label:'Budget'},React.createElement('div',{style:{display:'flex',gap:7}},Object.keys(BUDGET_LABELS).map(function(k){return React.createElement('button',{key:k,onClick:function(){setBudget(k)},style:{flex:1,padding:10,borderRadius:10,border:'1px solid',borderColor:budget===k?'var(--accent)':'var(--border2)',background:budget===k?'var(--accent-dim)':'var(--card2)',color:budget===k?'var(--accent)':'var(--text2)',fontSize:'.8em',fontWeight:600}},BUDGET_LABELS[k])}))),
        React.createElement('button',{className:'btn-p',onClick:generate},plan?'Regenerate Meal Plan':'Generate Meal Plan')
      ),
      plan&&React.createElement(React.Fragment,null,
        React.createElement(Card,{style:{marginBottom:14}},React.createElement('div',{className:'sl',style:{marginBottom:6}},'Average Daily Calories'),React.createElement('div',{className:'fm',style:{fontSize:'1.6em',fontWeight:600,color:'var(--accent)'}},plan.avgCalories+' kcal'),plan.nutritionNotes&&React.createElement('div',{style:{fontSize:'.8em',color:'var(--text2)',marginTop:10,lineHeight:1.6}},plan.nutritionNotes)),
        plan.days.map(function(d,i){
          return React.createElement(Card,{key:i,style:{marginBottom:12}},
            React.createElement('div',{style:{fontSize:'.93em',fontWeight:600,color:'var(--text)',marginBottom:10}},d.day),
            ['breakfast','lunch','dinner'].map(function(meal){
              const m=d[meal];
              if(!m)return null;
              return React.createElement('div',{key:meal,style:{marginBottom:10,paddingBottom:10,borderBottom:meal!=='dinner'?'1px solid var(--border)':'none'}},
                React.createElement('div',{style:{display:'flex',justifyContent:'space-between',marginBottom:4}},React.createElement('span',{className:'sl'},meal),React.createElement('span',{className:'fm',style:{fontSize:'.8em',color:'var(--accent)',fontWeight:600}},m.calories+' kcal')),
                React.createElement('div',{style:{fontSize:'.86em',fontWeight:500,color:'var(--text)',marginBottom:4}},m.name),
                React.createElement('div',{style:{fontSize:'.73em',color:'var(--muted)',marginBottom:4}},m.ingredients.join(', ')),
                React.createElement('div',{style:{display:'flex',gap:10}},
                  React.createElement('span',{className:'fm',style:{fontSize:'.66em',color:'var(--green)'}},'P '+m.protein+'g'),
                  React.createElement('span',{className:'fm',style:{fontSize:'.66em',color:'var(--blue)'}},'C '+m.carbs+'g'),
                  React.createElement('span',{className:'fm',style:{fontSize:'.66em',color:'var(--red)'}},'F '+m.fat+'g')
                )
              );
            })
          );
        }),
        plan.shoppingList&&React.createElement(Card,null,React.createElement('div',{className:'sl',style:{marginBottom:10}},'Shopping List'),plan.shoppingList.map(function(item,i){return React.createElement('div',{key:i,style:{fontSize:'.86em',color:'var(--text2)',padding:'.33em 0',borderBottom:i<plan.shoppingList.length-1?'1px solid var(--border)':'none'}},item)}))
      )
    )
  );
}

function ContentStudioPage(){
  const notif=useNotif();
  const [brand,setBrand]=useState(BRANDS[0].v);
  const [platform,setPlatform]=useState(PLATFORMS[0]);
  const [topic,setTopic]=useState('');
  const [result,setResult]=useState('');

  const generate=function(){
    if(!topic.trim())return notif.push('Describe what this content is about','error');
    const text=generateContentTemplate(brand,platform,topic);
    setResult(text);
    notif.push('Content generated','success');
  };

  const copyResult=function(){
    if(navigator.clipboard)navigator.clipboard.writeText(result);
    notif.push('Copied to clipboard','success',2000);
  };

  return React.createElement('div',{className:'sc',style:{flex:1}},
    React.createElement('div',{style:{padding:'.66em 1.2em 2.66em'}},
      React.createElement(Card,{style:{marginBottom:16}},
        React.createElement(Field,{label:'Brand'},React.createElement('div',{style:{display:'flex',flexDirection:'column',gap:7}},BRANDS.map(function(b){return React.createElement('button',{key:b.v,onClick:function(){setBrand(b.v)},style:{padding:'.66em .8em',borderRadius:10,border:'1px solid',borderColor:brand===b.v?'var(--accent)':'var(--border2)',background:brand===b.v?'var(--accent-dim)':'var(--card2)',textAlign:'left',fontSize:'.86em',fontWeight:600,color:brand===b.v?'var(--accent)':'var(--text)'}},b.v)}))),
        React.createElement(Field,{label:'Content Type'},React.createElement('select',{value:platform,onChange:function(e){setPlatform(e.target.value)}},PLATFORMS.map(function(p){return React.createElement('option',{key:p,value:p},p)}))),
        React.createElement(Field,{label:'What is this about?'},React.createElement('textarea',{value:topic,onChange:function(e){setTopic(e.target.value)},rows:3,placeholder:'e.g. New nail training cohort opening at our Lekki location'})),
        React.createElement('button',{className:'btn-p',onClick:generate},'Generate Content')
      ),
      result&&React.createElement(Card,null,
        React.createElement('div',{style:{display:'flex',justifyContent:'space-between',alignItems:'baseline',marginBottom:10}},React.createElement('div',{className:'sl'},platform+' \u00B7 '+brand),React.createElement('button',{onClick:copyResult,className:'btn-g',style:{fontSize:'.73em'}},'Copy')),
        React.createElement('div',{style:{fontSize:'.93em',color:'var(--text)',lineHeight:1.7,whiteSpace:'pre-wrap'}},result)
      )
    )
  );
}

function SettingsPage(){
  const store=useStore();const notif=useNotif();const nav=useNav();
  const [confirmReset,setConfirmReset]=useState(false);const [resetText,setResetText]=useState('');
  const FONT_SIZES=[{v:'sm',l:'Small'},{v:'md',l:'Medium'},{v:'lg',l:'Large'},{v:'xl',l:'X-Large'}];
  const THEMES_LIST=[
    {v:'default',l:'Default',swatch:'linear-gradient(135deg,#0a0a0b 50%,#d4a843 100%)'},
    {v:'light',l:'Light',swatch:'linear-gradient(135deg,#f7f4ef 50%,#a8762e 100%)'},
    {v:'dark',l:'Dark',swatch:'linear-gradient(135deg,#000 50%,#d8d8d8 100%)'},
    {v:'chatgpt',l:'ChatGPT',swatch:'linear-gradient(135deg,#0c0d11 50%,#8b7cf6 100%)'},
    {v:'pastel',l:'Pastel Pink & Silver',swatch:'linear-gradient(135deg,#fdf6f8 40%,#e8a0b4 70%,#c0c4c9 100%)'}
  ];
  const totalEntries=store.tasks.length+store.transactions.length+store.deadlines.length;
  const curTheme=store.settings.theme||'default',curFs=store.settings.fontSize||'md';

  const handleReset=function(){
    if(resetText!=='RESET')return notif.push('Type RESET to confirm','error');
    store.resetAll();notif.push('All data cleared','info',4000);
    setConfirmReset(false);setResetText('');nav.navigate('home');
  };
  const handleExport=function(){
    const data={tasks:store.tasks,transactions:store.transactions,deadlines:store.deadlines,target:store.target,settings:store.settings,exportedAt:new Date().toISOString()};
    const blob=new Blob([JSON.stringify(data,null,2)],{type:'application/json'});
    const url=URL.createObjectURL(blob);const a=document.createElement('a');
    a.href=url;a.download='cole-os-backup-'+todayStr()+'.json';a.click();URL.revokeObjectURL(url);
    notif.push('Exported','success');
  };

  return React.createElement('div',{className:'sc',style:{flex:1}},
    React.createElement('div',{style:{padding:'.66em 1.2em 2.66em'}},
      React.createElement('div',{style:{marginBottom:18}},React.createElement('div',{className:'sl',style:{marginBottom:8}},'Profile'),React.createElement(Card,null,React.createElement(Field,{label:'Your Name'},React.createElement('input',{value:store.settings.userName||'',onChange:function(e){store.updateSettings({userName:e.target.value})}})))),
      React.createElement('div',{style:{marginBottom:18}},React.createElement('div',{className:'sl',style:{marginBottom:8}},'Appearance'),React.createElement(Card,null,React.createElement('div',{style:{display:'grid',gridTemplateColumns:'1fr 1fr',gap:9}},THEMES_LIST.map(function(t){return React.createElement('button',{key:t.v,onClick:function(){store.updateSettings({theme:t.v});applyTheme(t.v);notif.push('Theme: '+t.l,'success',1200)},style:{border:'1px solid',borderColor:curTheme===t.v?'var(--accent)':'var(--border2)',background:curTheme===t.v?'var(--accent-dim)':'var(--card2)',borderRadius:12,padding:10,textAlign:'left'}},React.createElement('div',{style:{width:'100%',height:28,borderRadius:7,background:t.swatch,marginBottom:8}}),React.createElement('div',{style:{fontSize:'.8em',fontWeight:600,color:curTheme===t.v?'var(--accent)':'var(--text)'}},t.l))})))),
      React.createElement('div',{style:{marginBottom:18}},React.createElement('div',{className:'sl',style:{marginBottom:8}},'Text Size'),React.createElement(Card,null,React.createElement('div',{style:{display:'grid',gridTemplateColumns:'repeat(4,1fr)',gap:8}},FONT_SIZES.map(function(f){return React.createElement('button',{key:f.v,onClick:function(){store.updateSettings({fontSize:f.v});applyFontSize(f.v);notif.push('Text size: '+f.l,'success',1200)},style:{border:'1px solid',borderColor:curFs===f.v?'var(--accent)':'var(--border2)',background:curFs===f.v?'var(--accent-dim)':'var(--card2)',borderRadius:10,padding:'.66em .26em',display:'flex',flexDirection:'column',alignItems:'center',gap:5}},React.createElement('span',{style:{fontSize:f.v==='sm'?12:f.v==='md'?15:f.v==='lg'?18:22,fontWeight:700,color:curFs===f.v?'var(--accent)':'var(--text2)'}},'Aa'),React.createElement('span',{style:{fontSize:9,color:curFs===f.v?'var(--accent)':'var(--muted)'}},f.l))})))),
      React.createElement('div',{style:{marginBottom:18}},React.createElement('div',{className:'sl',style:{marginBottom:8}},'Notifications'),React.createElement(Card,null,React.createElement('div',{style:{display:'flex',justifyContent:'space-between',alignItems:'center'}},React.createElement('div',{style:{fontSize:'.93em',color:'var(--text)'}},'In-app Alerts'),React.createElement(Toggle,{on:store.settings.notifications!==false,onChange:function(){store.updateSettings({notifications:!store.settings.notifications})}})))),
      React.createElement('div',{style:{marginBottom:18}},React.createElement('div',{className:'sl',style:{marginBottom:8}},'Data'),React.createElement(Card,null,React.createElement('div',{style:{fontSize:'.8em',color:'var(--text2)',marginBottom:12}},totalEntries+' total entries'),React.createElement('button',{className:'btn-p',onClick:handleExport},'Export Data (JSON)'))),
      React.createElement('div',null,React.createElement('div',{className:'sl',style:{marginBottom:8,color:'var(--red)'}},'Danger Zone'),React.createElement(Card,{style:{borderColor:'var(--red)'}},
        !confirmReset?React.createElement('button',{onClick:function(){setConfirmReset(true)},style:{width:'100%',background:'none',border:'1px solid var(--red)',color:'var(--red)',borderRadius:11,padding:12,fontWeight:600}},'Reset All App Data'):
        React.createElement('div',null,React.createElement('div',{style:{fontSize:'.8em',color:'var(--text2)',marginBottom:10}},'Type RESET to confirm:'),React.createElement('input',{value:resetText,onChange:function(e){setResetText(e.target.value)},placeholder:'RESET',style:{marginBottom:10,borderColor:'var(--red)'}}),React.createElement('div',{style:{display:'flex',gap:8}},React.createElement('button',{onClick:handleReset,disabled:resetText!=='RESET',style:{flex:1,background:resetText==='RESET'?'var(--red)':'var(--card2)',border:'none',borderRadius:11,color:resetText==='RESET'?'#fff':'var(--muted)',padding:12,fontWeight:600}},'Confirm'),React.createElement('button',{onClick:function(){setConfirmReset(false);setResetText('')},className:'btn-g',style:{flex:1}},'Cancel')))
      ))
    )
  );
}

const PAGES={home:HomePage,tasks:TasksPage,finance:FinancePage,target:TargetPage,businesses:BusinessesPage,deadlines:DeadlinesPage,mealplanner:MealPlannerPage,contentstudio:ContentStudioPage,settings:SettingsPage};
function PageRouter(){const nav=useNav();const C=PAGES[nav.page]||HomePage;return React.createElement(C,null)}

function App(){
  return React.createElement(StoreProvider,null,
    React.createElement(NotifProvider,null,
      React.createElement(NavProvider,null,
        React.createElement('div',{style:{display:'flex',flexDirection:'column',height:'100%',background:'var(--bg)',overflow:'hidden',position:'relative'}},
          React.createElement(NotifStack,null),
          React.createElement(Sidebar,null),
          React.createElement('div',{style:{display:'flex',flexDirection:'column',height:'100%',overflow:'hidden'}},
            React.createElement(TopBar,null),
            React.createElement('div',{style:{flex:1,overflow:'hidden',display:'flex',flexDirection:'column'}},React.createElement(PageRouter,null))
          )
        )
      )
    )
  );
}

ReactDOM.createRoot(document.getElementById('root')).render(React.createElement(App,null));
</script>
</body>
</html>
