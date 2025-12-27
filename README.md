# DICTIONARY
<!DOCTYPE html>
<html lang="fil">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tagalog Dictionary & Games</title>
<link href="https://fonts.googleapis.com/css2?family=Merriweather:wght@300;400;700&display=swap" rel="stylesheet">
<style>
/* ===== Base Styles ===== */
body {
  margin: 0;
  font-family: "Merriweather", serif;
  background: #fdfcf9;
  color: #222;
}

header {
  background: #1a2b4c;
  color: white;
  padding: 25px;
  border-bottom: 4px solid #c7a14a;
  text-align: center;
}

header h1 {
  margin: 0;
  letter-spacing: 1px;
  font-size: 28px;
}

header p {
  font-size: 14px;
  opacity: 0.9;
  margin-top: 5px;
}

nav {
  background: white;
  border-bottom: 1px solid #ddd;
  padding: 12px;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
}

nav a {
  cursor: pointer;
  text-decoration: none;
  font-weight: bold;
  color: #1a2b4c;
}

nav a:hover {
  text-decoration: underline;
}

.container {
  max-width: 900px;
  width: 95%;
  margin: auto;
  padding: 25px 10px;
}

h2 {
  color: #1a2b4c;
  border-bottom: 2px solid #e2e2e2;
  padding-bottom: 6px;
  margin-top: 25px;
}

.search-box {
  width: 100%;
  padding: 14px;
  font-size: 16px;
  border: 2px solid #c7a14a;
  border-radius: 8px;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
  margin-bottom: 20px;
}

.entry-card {
  background: #fff8e7;
  border-left: 6px solid #c7a14a;
  padding: 20px 25px;
  margin-bottom: 20px;
  border-radius: 14px;
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.12);
  transition: transform 0.25s, box-shadow 0.25s;
  width: 100%;
  box-sizing: border-box;
}

.entry-card:hover {
  transform: scale(1.03);
  box-shadow: 0 12px 28px rgba(0, 0, 0, 0.18);
}

.entry-word {
  font-size: 20px;
  font-weight: bold;
  color: #1a2b4c;
  cursor: pointer;
  transition: transform 0.2s;
}

.entry-word:hover {
  transform: scale(1.02);
}

.entry-pron {
  font-style: italic;
  color: #555;
}

.entry-meaning {
  margin-top: 6px;
  opacity: 1;
  color: #333;
}

.topic-badge {
  display: inline-block;
  padding: 5px 12px;
  border-radius: 20px;
  color: white;
  font-weight: bold;
  font-size: 13px;
  margin-top: 6px;
  margin-right: 6px;
}

.topic-health { background: linear-gradient(135deg, #ff6b6b, #ff8787); }
.topic-work { background: linear-gradient(135deg, #6b9fff, #87b3ff); }
.topic-social { background: linear-gradient(135deg, #6bffb3, #87ffd4); }
.topic-personality { background: linear-gradient(135deg, #ffd36b, #ffe087); }
.topic-news { background: linear-gradient(135deg, #b36bff, #d087ff); }
.topic-lifestyle { background: linear-gradient(135deg, #6bfff6, #87fff8); }

button {
  padding: 12px;
  border: none;
  cursor: pointer;
  font-family: inherit;
  width: 100%;
  margin-bottom: 10px;
  border-radius: 8px;
  transition: 0.2s;
  font-weight: bold;
}

button:hover {
  opacity: 0.85;
  transform: scale(1.02);
}

#gameScore, #gameRec {
  font-weight: bold;
  margin-top: 10px;
  padding: 8px;
  border-radius: 8px;
}

#gameScore { background: #fff3e0; color: #c77f00; }
#gameRec { background: #f0f9ff; color: #1a73e8; }

.hidden { display: none; }

/* ===== Home Daily Word ===== */
#home { position: relative; }
#home::before {
  content: "";
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: radial-gradient(circle at top right, #fff3e0, #fdfcf9);
  z-index: 0;
}
#home .daily-card {
  position: relative;
  background: #fff8e7;
  border-left: 8px solid #c7a14a;
  padding: 25px 30px;
  border-radius: 16px;
  box-shadow: 0 6px 25px rgba(0, 0, 0, 0.12);
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  margin-bottom: 30px;
  z-index: 1;
  overflow: hidden;
  width: 100%;
  box-sizing: border-box;
}
#home .daily-card:hover { transform: scale(1.03) rotate(-0.5deg); }
#dailyTitle { font-size: 24px; font-weight: bold; margin-bottom: 8px; color: #1a2b4c; }
#dailyWord { font-size: 36px; font-weight: 800; color: #1a2b4c; margin-bottom: 10px; }
#dailyPron { font-size: 16px; font-style: italic; color: #555; margin-bottom: 14px; }
#dailyMeaning { font-size: 19px; color: #333; margin-bottom: 16px; position: relative; padding-left: 20px; }
#dailyMeaning::before { content: "“"; font-size: 36px; position: absolute; left: 0; top: -10px; color: #c7a14a; }
#dailyTopic { display: inline-block; background: linear-gradient(135deg, #1a2b4c, #3a4b7c); color: #fff; font-size: 13px; padding: 6px 14px; border-radius: 25px; font-weight: bold; opacity: 1; transform: translateX(0); }

/* ===== Media Queries for Mobile ===== */
@media (max-width: 600px) {
  header h1 { font-size: 22px; }
  header p { font-size: 12px; }

  nav { flex-direction: column; gap: 12px; padding: 10px; }
  nav a { font-size: 16px; }

  h2 { font-size: 18px; }

  .entry-word { font-size: 18px; }
  .entry-pron, .entry-meaning { font-size: 14px; }

  .search-box { font-size: 14px; padding: 10px; }

  #dailyWord { font-size: 28px; }
  #dailyMeaning { font-size: 16px; }
  #dailyTitle { font-size: 20px; }

  #gameWord { font-size: 22px; }
  button { font-size: 14px; padding: 10px; }

  .entry-card, .daily-card { padding: 15px 15px; }
}
</style>
</head>
<body>

<header>
  <h1>shesh</h1>
  <p>basta</p>
</header>

<nav>
  <a onclick="showPage('home')">Home</a>
  <a onclick="showPage('dictionary')">Dictionaries</a>
  <a onclick="showPage('games')">Games</a>
</nav>

<!-- HOME PAGE -->
<div class="container" id="home">
  <div class="daily-card">
    <div id="dailyTitle">Salita Ngayon</div>
    <div class="entry-word" id="dailyWord"></div>
    <div class="entry-pron" id="dailyPron"></div>
    <div class="entry-meaning" id="dailyMeaning"></div>
    <div class="entry-topic" id="dailyTopic"></div>
  </div>
</div>

<!-- DICTIONARY PAGE -->
<div class="container hidden" id="dictionary">
  <h2>Search Words</h2>
  <input type="text" id="search" class="search-box" placeholder="Type a letter or word…" onkeyup="searchWord()">
  
  <h2>Topics</h2>
  <div id="topics"></div>

  <h2>All Words</h2>
  <div id="allWords"></div>
</div>

<!-- WORD DETAIL PAGE -->
<div class="container hidden" id="wordPage">
  <button onclick="backToDictionary()">← Back to Dictionary</button>
  <h2 id="wordTitle"></h2>
  <div class="entry-pron" id="wordPron"></div>
  <div class="entry-pos" id="wordPOS"></div>
  <div class="entry-meaning" id="wordMeaning"></div>
  <div class="topic-badge" id="wordTopic"></div>
</div>

<!-- GAMES PAGE -->
<div class="container hidden" id="games">
  <h2>Hulaan ang Kahulugan</h2>
  <div class="entry-card" id="gameCard">
    <p id="gameProgress" style="margin-bottom:10px;font-weight:bold;">Question 1 / 10</p>
    <div style="background:#eee;border-radius:12px;overflow:hidden;height:16px;margin-bottom:15px;">
      <div id="progressBar" style="height:16px;width:0%;background:linear-gradient(135deg,#1a73e8,#6b9fff);transition:width 0.3s;"></div>
    </div>
    <p id="gameWord" style="font-size:24px;font-weight:bold;color:#1a2b4c;margin-bottom:15px;"></p>
    <div id="gameOptions"></div>
    <p id="gameFeedback" style="margin-top:10px;"></p>
    <p id="gameScore"></p>
    <p id="gameRec"></p>
    <button id="retryButton" class="hidden" onclick="retryGame()">Retry</button>
  </div>
</div>

<footer>© 2025 Diksyonaryo - Group 6 - Pagbasa</footer>

<script>
// ===== DATA =====
const dictionary = [
  {word:"agaw-buhay", pron:"a-gaw-buhay", pos:"n.", meaning:"Naghihingalo; malapit sa kamatayan.", topic:"Health"},
  {word:"ahas-bahay", pron:"a-has-ba-hay", pos:"n.", meaning:"Masamang kasambahay.", topic:"Lifestyle"},
  {word:"alilang-kanin", pron:"a-lil-ang-ka-nin", pos:"n.", meaning:"Utusang walang sweldo, pagkain lang.", topic:"Work"},
  {word:"alimuom", pron:"a-li-mu-om", pos:"n.", meaning:"Tsismis.", topic:"Social"},
  {word:"anak-dalita", pron:"a-nak-da-li-ta", pos:"n.", meaning:"Mahirap.", topic:"Social"},
  {word:"anak-pawis", pron:"a-nak-pa-wis", pos:"n.", meaning:"Magsasaka.", topic:"Work"},
  {word:"bahag ang buntot", pron:"ba-hag ang bun-tot", pos:"adj.", meaning:"Duwag.", topic:"Personality"},
  {word:"balat sibuyas", pron:"ba-lat si-bu-yas", pos:"adj.", meaning:"Iyakin, sensitibo.", topic:"Personality"},
  {word:"balat-kalabaw", pron:"ba-lat-ka-la-baw", pos:"adj.", meaning:"Makapal, di agad tinatablan ng hiya.", topic:"Personality"}
];

// ===== HOME DAILY WORD =====
const dailyIndex = Math.floor(Math.random() * dictionary.length);
document.getElementById('dailyWord').innerText = dictionary[dailyIndex].word;
document.getElementById('dailyPron').innerText = dictionary[dailyIndex].pron;
document.getElementById('dailyMeaning').innerText = dictionary[dailyIndex].meaning;
document.getElementById('dailyTopic').innerText = dictionary[dailyIndex].topic;

// ===== NAVIGATION =====
function showPage(id){
  const pages = ['home','dictionary','wordPage','games'];
  pages.forEach(p=>document.getElementById(p).classList.add('hidden'));
  document.getElementById(id).classList.remove('hidden');
}

function backToDictionary(){
  showPage('dictionary');
}

// ===== DICTIONARY =====
const allWordsDiv = document.getElementById('allWords');
const topicsDiv = document.getElementById('topics');

function displayWords(words){
  allWordsDiv.innerHTML = '';
  words.forEach(w=>{
    const card = document.createElement('div');
    card.className = 'entry-card';
    card.innerHTML = `
      <div class="entry-word" onclick="showWord('${w.word}')">${w.word}</div>
      <div class="entry-pron">${w.pron}</div>
      <div class="entry-meaning">${w.meaning}</div>
      <div class="topic-badge">${w.topic}</div>
    `;
    allWordsDiv.appendChild(card);
  });
}

function displayTopics(){
  const topics = [...new Set(dictionary.map(d=>d.topic))];
  topicsDiv.innerHTML = '';
  topics.forEach(t=>{
    const btn = document.createElement('button');
    btn.innerText = t;
    btn.onclick = ()=>displayWords(dictionary.filter(d=>d.topic===t));
    topicsDiv.appendChild(btn);
  });
}

function showWord(word){
  const w = dictionary.find(d=>d.word===word);
  document.getElementById('wordTitle').innerText = w.word;
  document.getElementById('wordPron').innerText = w.pron;
  document.getElementById('wordPOS').innerText = w.pos;
  document.getElementById('wordMeaning').innerText = w.meaning;
  document.getElementById('wordTopic').innerText = w.topic;
  showPage('wordPage');
}

function searchWord(){
  const query = document.getElementById('search').value.toLowerCase();
  displayWords(dictionary.filter(d=>d.word.toLowerCase().includes(query)));
}

displayWords(dictionary);
displayTopics();

// ===== SIMPLE GAME =====
const gameWords = dictionary.slice(0,10);
let gameIndex = 0, score = 0;

function nextGame(){
  if(gameIndex >= gameWords.length){
    document.getElementById('gameOptions').innerHTML='';
    document.getElementById('gameWord').innerText='Tapos na!';
    document.getElementById('gameScore').innerText='Score: '+score+'/'+gameWords.length;
    document.getElementById('retryButton').classList.remove('hidden');
    return;
  }
  const w = gameWords[gameIndex];
  document.getElementById('gameWord').innerText=w.word;
  const options = [w.meaning];
  while(options.length<4){
    const rand = dictionary[Math.floor(Math.random()*dictionary.length)].meaning;
    if(!options.includes(rand)) options.push(rand);
  }
  options.sort(()=>Math.random()-0.5);
  const optsDiv = document.getElementById('gameOptions');
  optsDiv.innerHTML='';
  options.forEach(o=>{
    const b = document.createElement('button');
    b.innerText=o;
    b.onclick=()=>checkAnswer(o,w.meaning);
    optsDiv.appendChild(b);
  });
  document.getElementById('gameProgress').innerText=`Question ${gameIndex+1} / ${gameWords.length}`;
  document.getElementById('progressBar').style.width=((gameIndex)/gameWords.length*100)+'%';
  document.getElementById('gameFeedback').innerText='';
}

function checkAnswer(selected,correct){
  if(selected===correct){ score++; document.getElementById('gameFeedback').innerText='Tama!'; }
  else{ document.getElementById('gameFeedback').innerText='Mali!'; }
  gameIndex++;
  setTimeout(nextGame,500);
  document.getElementById('progressBar').style.width=(gameIndex/gameWords.length*100)+'%';
}

function retryGame(){ gameIndex=0; score=0; document.getElementById('retryButton').classList.add('hidden'); nextGame(); }

nextGame();
</script>

</body>
</html>
