[README.txt](https://github.com/user-attachments/files/32837578/README.txt)
VIBE TROPICAL — prototype
Open index.html in a modern browser. It is a self-contained mobile-friendly prototype.
Features: Home/Trending, Discover, Search, Library, Now Playing demo, Like counter, navigation.
The songs are demo entries; no copyrighted audio is included.
NOW WANT TO AHEAD WITH THE APP
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Vibe Tropical</title>
<style>
:root{--bg:#061116;--card:#0d1b21;--card2:#12252c;--text:#f4fbfa;--muted:#9ab0b3;--accent:#19e6bf;--accent2:#8cebd9;--line:#20343a}
*{box-sizing:border-box}body{margin:0;background:#02090d;color:var(--text);font-family:Inter,system-ui,-apple-system,Segoe UI,sans-serif}
button,input{font:inherit}button{cursor:pointer}
.app{max-width:480px;margin:auto;min-height:100vh;background:linear-gradient(180deg,#061116,#07141a 60%,#061015);padding-bottom:78px}
header{padding:22px 18px 10px;display:flex;align-items:center;gap:12px}.logo{font-size:24px;font-weight:800;letter-spacing:-1px}.logo span{color:var(--accent);font-style:italic;font-weight:700}.avatar{margin-left:auto;width:38px;height:38px;border-radius:50%;background:linear-gradient(135deg,#e88d42,#18d9b8);display:grid;place-items:center;font-weight:800}
.search{margin:8px 18px 18px;background:#122229;border:1px solid var(--line);border-radius:28px;padding:12px 15px;display:flex;gap:9px}.search input{width:100%;background:none;border:0;outline:0;color:var(--text)}.search input::placeholder{color:#71888c}
.page{padding:0 18px}.hero{border-radius:22px;min-height:205px;padding:20px;background:linear-gradient(135deg,rgba(3,29,35,.7),rgba(0,80,67,.45)),radial-gradient(circle at 80% 20%,#f09b49,#123d3d 42%,#071217 80%);display:flex;flex-direction:column;justify-content:flex-end;overflow:hidden;position:relative}.hero:after{content:"☼";position:absolute;right:18px;top:12px;font-size:74px;opacity:.15}.eyebrow{color:var(--accent);font-size:12px;font-weight:800;text-transform:uppercase;letter-spacing:1px}.hero h1{font-size:29px;margin:5px 0}.hero p{color:#d5e1e1;margin:0 0 15px}.primary{border:0;background:var(--accent);color:#03231e;border-radius:24px;padding:12px 20px;font-weight:800;width:max-content}
.section{margin-top:24px}.section-title{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}.section-title h2{font-size:19px;margin:0}.link{color:var(--accent);font-size:13px;background:none;border:0}
.cards{display:flex;gap:10px;overflow:auto;padding-bottom:3px}.mini{min-width:112px;background:var(--card);border:1px solid var(--line);border-radius:15px;overflow:hidden}.cover{height:92px;background:linear-gradient(135deg,#ef9d55,#0d6b68);display:grid;place-items:center;font-size:30px}.mini:nth-child(2) .cover{background:linear-gradient(135deg,#e45d4d,#293b4c)}.mini:nth-child(3) .cover{background:linear-gradient(135deg,#dfc17a,#3b6b66)}.mini strong{display:block;font-size:13px;padding:9px 9px 1px}.mini small{display:block;color:var(--muted);padding:0 9px 10px}
.song{display:flex;align-items:center;gap:11px;padding:9px 0;border-bottom:1px solid var(--line)}.thumb{width:50px;height:50px;border-radius:11px;background:linear-gradient(135deg,#d77a46,#155b5a);display:grid;place-items:center;flex:none}.song .meta{min-width:0;flex:1}.song strong,.song small{display:block;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}.song small{color:var(--muted);margin-top:3px}.play{width:38px;height:38px;border-radius:50%;border:0;background:var(--accent);color:#05241f;font-weight:900}.heart{background:none;border:0;color:#8aa0a4;font-size:20px}.bottom{position:fixed;bottom:0;left:50%;transform:translateX(-50%);width:min(480px,100%);height:72px;background:rgba(5,15,19,.96);border-top:1px solid var(--line);display:flex;justify-content:space-around;align-items:center;z-index:5}.nav{background:none;border:0;color:#81979b;font-size:11px;display:flex;flex-direction:column;gap:4px;align-items:center}.nav b{font-size:20px}.nav.active{color:var(--accent)}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}.genre{background:var(--card);border:1px solid var(--line);border-radius:15px;padding:16px;font-weight:800}.genre span{display:block;font-size:24px;margin-bottom:9px}
.view{display:none}.view.active{display:block}.back{border:0;background:none;color:var(--text);font-size:24px}.topline{display:flex;align-items:center;gap:12px;padding:18px}.topline h1{margin:0;font-size:21px}.player{text-align:center;padding:10px 18px}.bigcover{aspect-ratio:1;background:linear-gradient(145deg,#e66d3d,#0b5e5b 58%,#06151a);border-radius:22px;display:grid;place-items:center;font-size:76px;box-shadow:0 18px 50px #0008}.player h1{font-size:24px;margin:20px 0 3px}.player p{color:var(--muted);margin:0}.bar{height:5px;background:#274047;border-radius:5px;margin:24px 0 7px}.bar i{display:block;width:42%;height:100%;background:var(--accent);border-radius:5px}.times{display:flex;justify-content:space-between;color:var(--muted);font-size:12px}.controls{display:flex;justify-content:center;align-items:center;gap:25px;margin:22px 0}.control{border:0;background:none;color:var(--text);font-size:23px}.pause{width:62px;height:62px;border:0;border-radius:50%;background:var(--accent);color:#04251f;font-size:24px}.empty{padding:40px 10px;text-align:center;color:var(--muted)}
</style>
</head>
<body>
<div class="app">
  <div id="home" class="view active">
    <header><div class="logo">Vibe<span>Tropical</span></div><div class="avatar">VT</div></header>
    <div class="search"><span>⌕</span><input id="homeSearch" placeholder="Search for songs, artists, albums..." oninput="searchFromHome(this.value)"></div>
    <main class="page">
      <div class="hero"><div class="eyebrow">Trending now</div><h1>Island Vibes</h1><p>Fresh sounds for your tropical mood.</p><button class="primary" onclick="play('Sunset Lover')">▶ Play</button></div>
      <section class="section"><div class="section-title"><h2>Trending Now</h2><button class="link" onclick="show('discover')">See all →</button></div><div id="songs"></div></section>
      <section class="section"><div class="section-title"><h2>New Releases</h2></div><div class="cards">
        <div class="mini"><div class="cover">🌅</div><strong>Island Morning</strong><small>Nova Tide</small></div>
        <div class="mini"><div class="cover">🌴</div><strong>Ocean Air</strong><small>Coastline</small></div>
        <div class="mini"><div class="cover">☀️</div><strong>Golden Hour</strong><small>Sol Wave</small></div>
      </div></section>
    </main>
  </div>

  <div id="discover" class="view">
    <div class="topline"><button class="back" onclick="show('home')">‹</button><h1>Discover</h1></div>
    <main class="page">
      <h2>Explore by Genre</h2><div class="grid">
        <div class="genre"><span>🌿</span>Afrobeat</div><div class="genre"><span>🌴</span>Reggae</div>
        <div class="genre"><span>🎵</span>Pop</div><div class="genre"><span>👑</span>Hip-Hop</div>
        <div class="genre"><span>🌊</span>Chill</div><div class="genre"><span>🎸</span>Rock</div>
      </div>
      <section class="section"><div class="section-title"><h2>Curated For You</h2></div>
        <div class="song" onclick="play('Island Vibes')"><div class="thumb">🌴</div><div class="meta"><strong>Island Vibes</strong><small>Relax & unwind</small></div><button class="play">▶</button></div>
        <div class="song" onclick="play('Sunset Drive')"><div class="thumb">🌅</div><div class="meta"><strong>Sunset Drive</strong><small>Warm evening beats</small></div><button class="play">▶</button></div>
        <div class="song" onclick="play('Ocean Air')"><div class="thumb">🌊</div><div class="meta"><strong>Ocean Air</strong><small>Easygoing tropical pop</small></div><button class="play">▶</button></div>
      </section>
    </main>
  </div>

  <div id="library" class="view">
    <div class="topline"><h1>Your Library</h1></div><main class="page">
      <div class="song"><div class="thumb">♥</div><div class="meta"><strong>Liked Songs</strong><small id="likedCount">0 songs</small></div><button class="link">›</button></div>
      <div class="song"><div class="thumb">♫</div><div class="meta"><strong>Playlists</strong><small>3 playlists</small></div><button class="link">›</button></div>
      <div class="song"><div class="thumb">◉</div><div class="meta"><strong>Albums</strong><small>12 albums</small></div><button class="link">›</button></div>
    </main>
  </div>

  <div id="player" class="view">
    <div class="topline"><button class="back" onclick="show('home')">‹</button><h1>Now Playing</h1></div>
    <main class="player"><div class="bigcover">🌴</div><h1 id="nowTitle">Sunset Lover</h1><p id="nowArtist">Coastline</p>
      <div class="bar"><i id="progress"></i></div><div class="times"><span>1:12</span><span>3:20</span></div>
      <div class="controls"><button class="control">⤨</button><button class="control">◀</button><button class="pause" id="pause" onclick="togglePlay()">Ⅱ</button><button class="control">▶</button><button class="control">↻</button></div>
      <button class="primary" onclick="likeCurrent()">♥ Like</button>
    </main>
  </div>

  <div id="search" class="view">
    <div class="topline"><button class="back" onclick="show('home')">‹</button><h1>Search</h1></div>
    <main class="page"><div class="search" style="margin:0"><span>⌕</span><input id="searchInput" placeholder="Try a song or artist..." oninput="renderSearch(this.value)"></div><div id="searchResults" class="section"></div></main>
  </div>
</div>

<nav class="bottom">
  <button class="nav active" data-v="home" onclick="show('home')"><b>⌂</b>Home</button>
  <button class="nav" data-v="discover" onclick="show('discover')"><b>◉</b>Discover</button>
  <button class="nav" data-v="player" onclick="show('player')"><b>♫</b>Player</button>
  <button class="nav" data-v="library" onclick="show('library')"><b>▢</b>Library</button>
</nav>

<script>
const songs=[
 {title:'Sunset Lover',artist:'Coastline',icon:'🌅'},
 {title:'Island Morning',artist:'Nova Tide',icon:'🌴'},
 {title:'Ocean Air',artist:'Sol Wave',icon:'🌊'},
 {title:'Palm Tree Dreams',artist:'Luna Coast',icon:'☀️'},
 {title:'Golden Hour',artist:'Tropic Soul',icon:'✨'}
];
let current=songs[0], liked=0, playing=true;
function songHTML(s,i){return `<div class="song"><div class="thumb">${s.icon}</div><div class="meta"><strong>${i?i+'. ':''}${s.title}</strong><small>${s.artist}</small></div><button class="heart" onclick="event.stopPropagation();likeCurrent()">♡</button><button class="play" onclick="play('${s.title}')">▶</button></div>`}
function renderSongs(list=songs){document.getElementById('songs').innerHTML=list.map((s,i)=>songHTML(s,i+1)).join('')}
function show(id){document.querySelectorAll('.view').forEach(v=>v.classList.remove('active'));document.getElementById(id).classList.add('active');document.querySelectorAll('.nav').forEach(n=>n.classList.toggle('active',n.dataset.v===id));if(id==='player')document.getElementById('pause').textContent=playing?'Ⅱ':'▶'}
function play(title){current=songs.find(s=>s.title===title)||{title,artist:'Vibe Tropical',icon:'🌴'};document.getElementById('nowTitle').textContent=current.title;document.getElementById('nowArtist').textContent=current.artist;playing=true;show('player')}
function togglePlay(){playing=!playing;document.getElementById('pause').textContent=playing?'Ⅱ':'▶'}
function likeCurrent(){liked++;document.getElementById('likedCount').textContent=liked+' song'+(liked===1?'':'s')}
function searchFromHome(q){if(q.trim()){show('search');document.getElementById('searchInput').value=q;renderSearch(q)}}
function renderSearch(q){let r=songs.filter(s=>(s.title+' '+s.artist).toLowerCase().includes(q.toLowerCase()));document.getElementById('searchResults').innerHTML=r.length?r.map((s,i)=>songHTML(s,i+1)).join(''):'<div class="empty">No songs found yet.</div>'}
renderSongs();
</script>
</body>
</html>[index.html](https://github.com/user-attachments/files/32837598/index.html)
