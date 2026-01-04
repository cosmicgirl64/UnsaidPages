<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Unsaid Pages — Author Portfolio</title>

  <!-- Literary fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Libre+Baskerville&display=swap" rel="stylesheet">

  <style>
    :root{
      --paper:#ffffff;
      --ink:#1f1f1f;
      --muted:#6f6f6f;
      --gold:#b7a46a;
    }

    *{box-sizing:border-box;}

    body{
      margin:0;
      font-family:'Libre Baskerville', serif;
      background:#f3f2ee;
      color:var(--ink);
      line-height:1.9;
    }

    /* ---------- NAV ---------- */
    nav{
      position:fixed;
      top:0; left:0; right:0;
      background:rgba(255,255,255,0.9);
      border-bottom:1px solid #e5e5e5;
      padding:14px 10%;
      display:flex;
      justify-content:space-between;
      align-items:center;
      z-index:100;
    }

    nav span{
      font-family:'Playfair Display', serif;
      letter-spacing:1px;
    }

    nav a{
      text-decoration:none;
      color:var(--ink);
      margin-left:25px;
      font-size:0.9rem;
    }

    /* ---------- HOME PAGE ---------- */
    .home{
      min-height:100vh;
      display:flex;
      flex-direction:column;
      justify-content:center;
      align-items:center;
      text-align:center;
      background:var(--paper);
      padding:100px 15% 60px;
    }

    .symbol{
      font-size:2.5rem;
      color:var(--gold);
      margin-bottom:20px;
    }

    .home h1{
      font-family:'Playfair Display', serif;
      font-size:3.8rem;
      letter-spacing:2px;
      margin-bottom:10px;
    }

    .home p{
      max-width:520px;
      color:var(--muted);
      margin-bottom:40px;
    }

    .btn{
      padding:14px 36px;
      border:1px solid var(--gold);
      color:var(--gold);
      text-decoration:none;
      border-radius:30px;
      transition:0.3s;
    }

    .btn:hover{
      background:var(--gold);
      color:#fff;
    }

    /* ---------- INDEX / BOOK ---------- */
    .index{
      padding:120px 12% 80px;
    }

    h2{
      font-family:'Playfair Display', serif;
      font-size:2.4rem;
      text-align:center;
      margin-bottom:50px;
    }

    .toc{
      max-width:400px;
      margin:0 auto;
      display:flex;
      flex-direction:column;
      gap:18px;
    }

    .chapter-card{
      background:var(--paper);
      padding:32px;
      border:1px solid #e3e3e3;
      cursor:pointer;
      transition:0.3s;
      position:relative;
    }

    .chapter-card::after{
      content:'›';
      position:absolute;
      right:25px;
      opacity:0.4;
      color:var(--muted);
    }

    .chapter-card:hover{
      transform:translateY(-6px);
    }

    .chapter-card:hover::after{
      opacity:1;
    }

    /* ---------- PAGE TURN ---------- */
    .page{
      max-width:850px;
      margin:80px auto;
      background:var(--paper);
      padding:70px;
      box-shadow:0 18px 45px rgba(0,0,0,0.06);
      animation:pageTurn 0.6s ease;
    }

    @keyframes pageTurn{
      from{transform:rotateY(14deg);opacity:0;}
      to{transform:rotateY(0);opacity:1;}
    }

    .page h3{
      font-family:'Playfair Display', serif;
      font-size:2rem;
      margin-bottom:25px;
    }

    .like{
      margin-top:40px;
      border:1px solid var(--gold);
      background:none;
      color:var(--gold);
      padding:10px 24px;
      cursor:pointer;
    }

    .like:hover{background:var(--gold);color:#fff;}

    /* ---------- ADMIN ---------- */
    #adminLogin,#adminPanel{display:none;padding:120px 20%;}

    input{width:100%;padding:14px;margin-bottom:15px;font-family:inherit;}

    .stat{background:#fff;border:1px solid #e3e3e3;padding:20px;margin-bottom:15px;}

    footer{
      text-align:center;
      padding:60px;
      color:var(--muted);
      font-size:0.9rem;
    }

    @media(max-width:768px){
      nav{padding:14px 6%;}
      .home h1{font-size:2.8rem;}
      .index{padding:100px 6%;}
      .page{padding:40px;}
    }
  </style>
</head>
<body>

<nav>
  <span>Unsaid Pages</span>
  <div>
    <a href="#home">Home</a>
    <a href="#index">Read</a>
  </div>
</nav>

<!-- HOME PAGE -->
<section id="home" class="home">
  
  <h1>UNSAID PAGES</h1>
  <p>A personal literary project exploring unspoken emotions, silent responsibilities, and the strength found between the lines.</p>
  <a class="btn" href="#index">Open the Book</a>
</section>

<!-- INDEX PAGE -->
<section id="index" class="index">
  <h2>Chapters</h2>
  <div class="toc">
    <div class="chapter-card" onclick="openChapter(1)">Chapter I</div>
    <div class="chapter-card" onclick="openChapter(2)">Chapter II</div>
    <div class="chapter-card" onclick="openChapter(3)">Chapter III</div>
    <div class="chapter-card" onclick="openChapter(4)">Chapter IV</div>
    <div class="chapter-card" onclick="openChapter(5)">Chapter V</div>
    <div class="chapter-card" onclick="openChapter(6)">Chapter VI</div>
    <div class="chapter-card" onclick="openChapter(7)">Chapter VII</div>
    <div class="chapter-card" onclick="openChapter(8)">Chapter VIII</div>
    <div class="chapter-card" onclick="openChapter(9)">Chapter IX</div>
    <div class="chapter-card" onclick="openChapter(10)">Chapter X</div>
  </div>
</section>

<div id="reader"></div>

<!-- ADMIN -->
<section id="adminLogin">
  <h2>Author Login</h2>
  <input id="pass" type="password" placeholder="Password" />
  <button class="btn" onclick="login()">Login</button>
</section>

<section id="adminPanel">
  <h2>Reader Statistics</h2>
  <div id="stats"></div>
</section>

<footer>
  © 2026 • Unsaid Pages • Author Portfolio — Sanvi Shah
</footer>

<script>
  const reader=document.getElementById('reader');
  const stats=document.getElementById('stats');

  function openChapter(n){
    let v=Number(localStorage.getItem('v'+n)||0)+1;
    localStorage.setItem('v'+n,v);

    reader.innerHTML=`
      <div class='page'>
        <h3>Chapter ${n}</h3>
        <p>Paste chapter ${n} text here...</p>
        <button class='like' onclick='like(${n})'>♥ Like (<span id='l${n}'>${localStorage.getItem('l'+n)||0}</span>)</button>
      </div>`;
  }

  function like(n){
    let l=Number(localStorage.getItem('l'+n)||0)+1;
    localStorage.setItem('l'+n,l);
    document.getElementById('l'+n).innerText=l;
  }

  document.addEventListener('keydown',e=>{
    if(e.key==='A') document.getElementById('adminLogin').style.display='block';
  });

  function login(){
    if(document.getElementById('pass').value==='admin123'){
      document.getElementById('adminLogin').style.display='none';
      document.getElementById('adminPanel').style.display='block';
      loadStats();
    }
  }

  function loadStats(){
    stats.innerHTML='';
    for(let i=1;i<=10;i++){
      stats.innerHTML+=`<div class='stat'>Chapter ${i} — Views: ${localStorage.getItem('v'+i)||0}, Likes: ${localStorage.getItem('l'+i)||0}</div>`;
    }
  }
</script>

</body>
</html>
