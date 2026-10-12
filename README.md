<!doctype html>
<html lang="pt-PT">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<meta name="theme-color" content="#100d1b">
<meta name="description" content="Memistarz — uma biblioteca digital gratuita, selecionada e organizada por pessoas para pessoas.">
<title>Memistarz — Biblioteca Digital Gratuita</title>
<style>
:root{color-scheme:dark;--bg:#100d1b;--panel:#191528;--panel2:#211c32;--line:#332b49;--text:#f6f2ff;--muted:#b6adc9;--purple:#b49aff;--pink:#f0abfc;--cyan:#8be9f5;--green:#a7f3d0}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{margin:0;background:radial-gradient(ellipse at 78% -12%,#382454 0,transparent 42%),var(--bg);color:var(--text);font:15px/1.55 Inter,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif}
a{color:inherit;text-decoration:none}
button,input{font:inherit}
.wrap{width:min(1120px,calc(100% - 32px));margin:auto}
.topbar{position:sticky;top:0;z-index:5;background:#100d1beF;backdrop-filter:blur(16px);border-bottom:1px solid #332b497a}
.nav{min-height:72px;display:flex;align-items:center;justify-content:space-between;gap:18px}
.brand{display:flex;align-items:center;gap:11px}
.logo{width:40px;height:40px;border-radius:13px;display:grid;place-items:center;background:linear-gradient(135deg,var(--purple),var(--pink));color:#1a1028;font-size:23px;font-weight:950;box-shadow:0 5px 25px #a78bfa35}
.brand strong{font-size:18px;letter-spacing:.8px}
.brand small{display:block;font-size:10px;color:var(--muted);letter-spacing:1.5px}
.navlinks{display:flex;gap:22px;color:var(--muted);font-size:13px}
.navlinks a:hover{color:white}
.support,.download{display:inline-flex;align-items:center;justify-content:center;gap:8px;padding:10px 14px;border-radius:12px;background:var(--purple);color:#1a1229;font-weight:800;border:0}
.support{font-size:12px}
.hero{padding:64px 0 38px;display:grid;grid-template-columns:1.25fr .75fr;gap:32px;align-items:center}
.eyebrow{font-size:11px;letter-spacing:2px;text-transform:uppercase;color:var(--cyan);font-weight:800}
.hero h1{font-size:clamp(34px,5vw,56px);line-height:1.05;letter-spacing:-1.8px;margin:13px 0 16px;max-width:650px}
.hero h1 span{background:linear-gradient(90deg,var(--purple),var(--pink),var(--cyan));-webkit-background-clip:text;background-clip:text;color:transparent}
.hero p{color:var(--muted);max-width:590px;font-size:16px}
.hero-actions{display:flex;gap:10px;flex-wrap:wrap;margin-top:23px}
.secondary{display:inline-flex;align-items:center;justify-content:center;padding:10px 14px;border-radius:12px;border:1px solid var(--line);color:var(--text);font-weight:700;font-size:13px}
.hero-art{min-height:250px;border:1px solid #554276;border-radius:26px;background:radial-gradient(circle at 50% 40%,#56357b 0,#28203d 38%,#171323 74%);display:grid;place-items:center;position:relative;overflow:hidden}
.orb{width:145px;height:145px;border:1px solid #e9ddff88;border-radius:50%;display:grid;place-items:center;box-shadow:0 0 0 22px #ffffff07,0 0 0 48px #ffffff05,0 0 65px #b49aff55;font-size:54px;color:#e9ddff}
.float{position:absolute;border:1px solid #ffffff2a;background:#171323c9;backdrop-filter:blur(10px);padding:10px 13px;border-radius:13px;font-size:12px;color:#e9ddff}
.f1{top:22px;left:18px}
.f2{right:16px;bottom:25px;color:var(--cyan)}
.section{padding:26px 0 50px}
.section-head{display:flex;align-items:end;justify-content:space-between;gap:18px;margin-bottom:18px}
.section-head h2{font-size:25px;letter-spacing:-.5px;margin:3px 0}
.section-head p{margin:0;color:var(--muted);font-size:13px}
.search{width:min(330px,100%);padding:12px 14px;border:1px solid var(--line);background:var(--panel);border-radius:12px;color:white;outline:none}
.search:focus{border-color:var(--purple)}
.filters{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:18px}
.filter{padding:8px 13px;border:1px solid var(--line);border-radius:999px;background:transparent;color:var(--muted);font-size:12px;cursor:pointer}
.filter.active,.filter:hover{background:#b49aff1b;border-color:#8066bd;color:#f1eaff}
.grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:16px}
.resource{border:1px solid var(--line);border-radius:18px;background:linear-gradient(145deg,#201a31,#171323);overflow:hidden;display:flex;flex-direction:column;min-width:0}
.cover{height:155px;display:grid;place-items:center;position:relative;overflow:hidden;background:radial-gradient(ellipse at 50% 45%,#6d4fc2 0,#35204f 42%,#171323 78%)}
.cover:before,.cover:after{content:"";position:absolute;border:1px solid #ffffff35;border-radius:50%;width:145px;height:145px}
.cover:after{width:190px;height:190px}
.cover.cyan{background:radial-gradient(ellipse at 50% 45%,#176779 0,#183a4d 42%,#171323 78%)}
.cover.pink{background:radial-gradient(ellipse at 50% 45%,#8a376e 0,#44213f 42%,#171323 78%)}
.cover .symbol{z-index:1;font-size:48px;color:#f5edff;text-shadow:0 0 25px #fff5}
.tag{position:absolute;z-index:2;top:12px;left:12px;background:#100d1bd9;border:1px solid #ffffff24;border-radius:7px;padding:4px 7px;font-size:10px;color:#e9ddff}
.resource-body{padding:16px;display:flex;flex-direction:column;flex:1}
.resource h3{font-size:16px;margin:0 0 7px}
.resource p{font-size:12px;color:var(--muted);margin:0 0 15px;flex:1}
.meta{font-size:11px;color:#9e93b5;margin-bottom:13px}
.download{font-size:12px;width:100%;cursor:pointer}
.download:hover,.support:hover{filter:brightness(1.08)}
.empty{display:none;padding:28px;text-align:center;border:1px dashed var(--line);border-radius:15px;color:var(--muted)}
.community{padding:24px;border:1px solid var(--line);border-radius:20px;background:linear-gradient(110deg,#241b39,#171323);display:flex;align-items:center;justify-content:space-between;gap:22px}
.community h2{margin:4px 0 6px;font-size:24px}
.community p{margin:0;color:var(--muted);font-size:13px;max-width:650px}
.footer{border-top:1px solid var(--line);padding:25px 0 35px;color:var(--muted);font-size:12px}
.footrow{display:flex;justify-content:space-between;gap:18px;align-items:center}
.footlinks{display:flex;gap:16px;flex-wrap:wrap}
.footlinks a:hover{color:white}
.hidden{display:none!important}
@media(max-width:800px){
.hero{grid-template-columns:1fr;padding-top:42px}
.hero-art{min-height:200px}
.grid{grid-template-columns:repeat(2,minmax(0,1fr))}
.navlinks{display:none}
.section-head{align-items:stretch;flex-direction:column}
.search{width:100%}
}
@media(max-width:520px){
.wrap{width:min(100% - 24px,1120px)}
.nav{min-height:64px}
.brand strong{font-size:15px}
.support{padding:9px 10px}
.hero{padding-top:34px}
.hero h1{font-size:37px}
.hero p{font-size:14px}
.hero-art{min-height:175px}
.orb{width:110px;height:110px;font-size:42px}
.grid{grid-template-columns:1fr}
.cover{height:170px}
.community{align-items:flex-start;flex-direction:column}
.community h2{font-size:21px}
.footrow{align-items:flex-start;flex-direction:column}
}
</style>
</head>
<body>
<header class="topbar">
<div class="wrap nav">
<a class="brand" href="#inicio" aria-label="Memistarz início">
<span class="logo">M</span>
<span><strong>MEMISTARZ</strong><small>BIBLIOTECA DIGITAL</small></span>
</a>
<nav class="navlinks" aria-label="Navegação principal">
<a href="#biblioteca">Biblioteca</a>
<a href="#comunidade">Comunidade</a>
<a href="#sobre">Sobre</a>
</nav>
<a class="support" href="https://patreon.com/bronzstarz" target="_blank" rel="noopener noreferrer">Apoiar o projeto ↗</a>
</div>
</header>
<main>
<section class="wrap hero" id="inicio">
<div>
<div class="eyebrow">Um espaço para descobrir e partilhar</div>
<h1>Boas ideias merecem ser <span>livres.</span></h1>
<p>Uma biblioteca digital gratuita, organizada por pessoas para pessoas. Descobre recursos, encontra inspiração e descarrega o que precisas — sem conta, sem complicações.</p>
<div class="hero-actions">
<a class="support" href="#biblioteca">Explorar a biblioteca ↓</a>
<a class="secondary" href="#sobre">Conhecer a Memistarz</a>
</div>
</div>
<div class="hero-art" aria-hidden="true">
<span class="float f1">✦ Recursos gratuitos</span>
<div class="orb">M</div>
<span class="float f2">↓ Descarregar sem conta</span>
</div>
</section>
<section class="wrap section" id="biblioteca">
<div class="section-head">
<div>
<div class="eyebrow">Escolhidos e organizados por nós</div>
<h2>A biblioteca</h2>
<p>Pesquisa ou escolhe uma categoria para encontrar o teu próximo recurso.</p>
</div>
<input id="search" class="search" type="search" placeholder="Pesquisar recursos…" aria-label="Pesquisar recursos">
</div>
<div class="filters" role="group" aria-label="Filtrar por categoria">
<button class="filter active" data-filter="todos">Tudo</button>
<button class="filter" data-filter="memes">Memes e reações</button>
<button class="filter" data-filter="design">Arte e design</button>
<button class="filter" data-filter="educacao">Educação</button>
<button class="filter" data-filter="ferramentas">Ferramentas</button>
</div>
<div class="grid" id="resources">
<article class="resource" data-category="memes" data-search="24 reações originais memes stickers imagens pack reação gamer">
<div class="cover"><span class="tag">MEMES E REAÇÕES</span><span class="symbol">✦</span></div>
<div class="resource-body">
<h3>Pack de 24 reações originais</h3>
<p>Um conjunto de reações digitais para usar em conversas, publicações e conteúdos criativos.</p>
<div class="meta">ZIP · Pack digital · Gratuito</div>
<a class="download" href="downloads/Memistarz_24_Reacoes_Originais_V7.zip" download>Descarregar gratuitamente ↓</a>
</div>
</article>
<article class="resource" data-category="design" data-search="arte design imagens recursos visuais">
<div class="cover cyan"><span class="tag">ARTE E DESIGN</span><span class="symbol">◈</span></div>
<div class="resource-body">
<h3>Recursos de arte e design</h3>
<p>Uma área para materiais visuais selecionados. Novos ficheiros serão adicionados à medida que forem preparados.</p>
<div class="meta">Novos recursos em preparação</div>
<span class="secondary" aria-label="Recursos em preparação">A preparar</span>
</div>
</article>
<article class="resource" data-category="educacao" data-search="educação guias aprendizagem documentos">
<div class="cover pink"><span class="tag">EDUCAÇÃO</span><span class="symbol">✧</span></div>
<div class="resource-body">
<h3>Guias e materiais educativos</h3>
<p>Documentos e materiais para aprender, explorar ideias e desenvolver projetos.</p>
<div class="meta">Novos recursos em preparação</div>
<span class="secondary" aria-label="Recursos em preparação">A preparar</span>
</div>
</article>
</div>
<div class="empty" id="empty">Não encontrámos recursos com esses termos. Experimenta outra pesquisa.</div>
</section>
<section class="wrap section" id="comunidade">
<div class="community">
<div>
<div class="eyebrow">Uma comunidade feita de descobertas</div>
<h2>Encontra algo útil. Partilha a ideia.</h2>
<p>A Memistarz cresce através dos recursos que selecionamos e das pessoas que os usam, recomendam e ajudam a divulgar. Os conteúdos são publicados pela equipa da Memistarz.</p>
</div>
<a class="secondary" href="https://patreon.com/bronzstarz" target="_blank" rel="noopener noreferrer">Apoiar voluntariamente ↗</a>
</div>
</section>
<section class="wrap section" id="sobre">
<div class="section-head">
<div>
<div class="eyebrow">A nossa missão</div>
<h2>Gratuita por princípio.</h2>
<p>O objetivo é facilitar o acesso a recursos digitais úteis e criativos. Não precisas de criar uma conta, fornecer e-mail ou pagar para descarregar os ficheiros identificados como gratuitos. O apoio financeiro é opcional e feito através do Patreon.</p>
</div>
</div>
</section>
</main>
<footer class="footer">
<div class="wrap footrow">
<span>© <span id="year"></span> Memistarz · Uma biblioteca digital aberta.</span>
<div class="footlinks">
<a href="#biblioteca">Biblioteca</a>
<a href="#sobre">Sobre</a>
<a href="https://patreon.com/bronzstarz" target="_blank" rel="noopener noreferrer">Patreon ↗</a>
</div>
</div>
</footer>
<script>
const search=document.getElementById('search'),
cards=[...document.querySelectorAll('.resource')],
filters=[...document.querySelectorAll('[data-filter]')];
let category='todos';
function update(){
const q=search.value.trim().toLocaleLowerCase('pt-PT');
let shown=0;
cards.forEach(card=>{
const okCat=category==='todos'||card.dataset.category===category;
const okText=(card.dataset.search+' '+card.innerText).toLocaleLowerCase('pt-PT').includes(q);
const visible=okCat&&okText;
card.classList.toggle('hidden',!visible);
if(visible)shown++;
});
document.getElementById('empty').style.display=shown?'none':'block';
}
search.addEventListener('input',update);
filters.forEach(btn=>btn.addEventListener('click',()=>{
category=btn.dataset.filter;
filters.forEach(b=>b.classList.toggle('active',b===btn));
update();
}));
document.getElementById('year').textContent=new Date().getFullYear();
</script>
</body>
</html>