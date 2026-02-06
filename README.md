<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>𝐌𝐀𝐀𝐌𝐎𝐔𝐍 | Digital Identity</title>

<!-- Google Font -->
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@1,600&display=swap" rel="stylesheet">

<!-- Icons -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
:root{
  --main:#00ff99;
  --soft:#c9ffe9;
}

*{margin:0;padding:0;box-sizing:border-box}

body{
  background:black;
  color:var(--main);
  font-family:"Courier New", monospace;
  overflow-x:hidden;
}

/* ===== Matrix ===== */
canvas{
  position:fixed;
  inset:0;
  z-index:-1;
}

/* ===== Frame ===== */
.site-frame{
  max-width:960px;
  margin:50px auto;
  padding:12px;
  border-radius:26px;
  background:linear-gradient(
    160deg,
    rgba(0,255,153,.35),
    rgba(0,255,153,.05),
    rgba(0,0,0,.9)
  );
  box-shadow:0 0 60px rgba(0,255,153,.2);
}

.wrapper{
  border-radius:22px;
  padding:70px 22px;
  background:rgba(0,0,0,.92);
}

/* ===== Header ===== */
header{
  text-align:center;
}

/* ===== Name ===== */
.name{
  font-family:'Playfair Display', serif;
  font-style:italic;
  font-size:clamp(36px,9vw,62px);
  letter-spacing:6px;
  text-shadow:
    0 0 10px rgba(0,255,153,.6),
    0 0 25px rgba(0,255,153,.4);
}

/* ===== Avatar ===== */
.avatar{
  width:170px;
  height:170px;
  margin:30px auto 18px;
  border-radius:50%;
  overflow:hidden;
  border:2px solid rgba(0,255,153,.8);
  box-shadow:
    0 0 25px rgba(0,255,153,.5),
    inset 0 0 20px rgba(0,255,153,.25);
  animation:fadeIn 1.2s ease forwards;
}

.avatar img{
  width:100%;
  height:100%;
  object-fit:cover;
  filter:contrast(120%) brightness(.9);
}

@keyframes fadeIn{
  from{opacity:0;transform:scale(.85)}
  to{opacity:1;transform:scale(1)}
}

/* ===== Social Buttons ===== */
.social{
  margin-top:22px;
  display:flex;
  flex-direction:column;      /* عمودي */
  align-items:center;
  gap:12px;
}

.social a{
  width:220px;
  justify-content:center;
  padding:8px 20px;
  border-radius:999px;
  border:1px solid rgba(0,255,153,.6);
  background:rgba(0,255,153,.06);
  color:var(--main);
  font-size:13px;
  text-decoration:none;
  display:flex;
  align-items:center;
  gap:8px;
  transition:.3s ease;
}

.social a:hover{
  background:var(--main);
  color:black;
  transform:translateY(-2px);
  box-shadow:0 10px 22px rgba(0,255,153,.4);
}

/* ===== About ===== */
.about{
  margin-top:55px;
}

.about h2{
  font-size:20px;
  margin-bottom:12px;
  border-left:4px solid var(--main);
  padding-left:12px;
}

.about p{
  font-size:15px;
  line-height:2;
  color:var(--soft);
  max-width:720px;
}

/* ===== Footer ===== */
footer{
  margin-top:70px;
  text-align:center;
  font-size:13px;
  opacity:.6;
}

/* ===== Mobile ===== */
@media (max-width:480px){
  .site-frame{
    margin:22px 10px;
    border-radius:20px;
  }
  .wrapper{
    padding:55px 16px;
  }
}
</style>
</head>

<body>

<canvas id="matrix"></canvas>

<div class="site-frame">
<div class="wrapper">

<header>
  <h1 class="name">𝐌𝐀𝐀𝐌𝐎𝐔𝐍</h1>

  <!-- الصورة تعمل داخل Learn HTML -->
  <div class="avatar">
   <img src="avatar.jpg" alt="Avatar">
  </div>

  <!-- الأزرار بالترتيب المطلوب -->
  <div class="social">
    <a href="https://t.me/XZITG " target="_blank">
      <i class="fa-brands fa-telegram"></i> Telegram
    </a>

    <a href="https://instagram.com/4.f3y" target="_blank">
      <i class="fa-brands fa-instagram"></i> Instagram
    </a>

    <a href="https://www.facebook.com/profile.php?id=61556407491599" target="_blank">
      <i class="fa-brands fa-facebook-f"></i> Facebook
    </a>
  </div>
</header>

<section class="about">
  <h2>About Me</h2>
  <p>
    I’m MAAMOUN — This is my website for contacting me via Telegram, Instagram, and Facebook.
    My age: 2007/06/07 
    My residence: Miliana 
  </p>
</section>

<footer>
  © 2026 MAAMOUN — Crafted with discipline.
</footer>

</div>
</div>

<script>
/* ===== Matrix Effect ===== */
const c=document.getElementById("matrix"),
ctx=c.getContext("2d");

function resize(){
  c.width=innerWidth;
  c.height=innerHeight;
}
resize();
addEventListener("resize",resize);

const chars="01MAAMOUN";
const size=14;
let drops=Array(Math.floor(c.width/size)).fill(1);

setInterval(()=>{
  ctx.fillStyle="rgba(0,0,0,.06)";
  ctx.fillRect(0,0,c.width,c.height);
  ctx.fillStyle="#00ff99";
  ctx.font=size+"px monospace";

  drops.forEach((y,i)=>{
    const t=chars[Math.random()*chars.length|0];
    ctx.fillText(t,i*size,y*size);
    if(y*size>c.height && Math.random()>.975) drops[i]=0;
    drops[i]++;
  });
},33);
</script>

</body>
</html>
