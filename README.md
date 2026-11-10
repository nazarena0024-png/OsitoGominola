from pathlib import Path

html = r'''<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Muñeca Y2K Dress Up — Tiger & Orchid</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Quicksand:wght@600;700&display=swap');
:root{--pink:#f6c5dc;--pink2:#eaa7c8;--orchid:#c9a9df;--ink:#382534;--panel:#ffeaf4;--line:#a66d91}
*{box-sizing:border-box}
body{margin:0;background:#f5d9e8;color:var(--ink);font-family:Quicksand,Arial,sans-serif}
button{font:700 13px Quicksand,Arial;cursor:pointer;color:var(--ink);border:2px solid #8d5c7b;border-radius:7px;background:linear-gradient(#fff7fb,#efbfd8);box-shadow:inset 0 1px #fff,0 2px 0 #bd8ba9;padding:7px 10px}
button:hover{filter:brightness(1.06);transform:translateY(-1px)}
button:active{transform:translateY(1px);box-shadow:none}
.shell{max-width:1500px;margin:8px auto;padding:7px;background:linear-gradient(135deg,#f9e4ef,#e9c6df);border:4px ridge #d38db4;border-radius:14px;box-shadow:0 5px 18px #9b628755}
.topbar{display:flex;align-items:center;gap:8px;justify-content:space-between;padding:6px 10px;background:linear-gradient(#fbe4ef,#eebbd4);border:3px ridge #d59ab9;border-radius:8px}
.logo{font:700 clamp(17px,2.5vw,32px) Fredoka,sans-serif;letter-spacing:.5px;text-shadow:2px 2px #fff,-1px -1px #fff;white-space:nowrap}
.logo span{color:#a65d91}
.topbuttons{display:flex;gap:6px;flex-wrap:wrap;justify-content:center}
.toolbar{display:flex;justify-content:center;gap:8px;flex-wrap:wrap;padding:7px;margin:5px 0;background:#f6d7e7;border:2px ridge #c98eae;border-radius:7px}
.layout{display:grid;grid-template-columns:minmax(210px, .95fr) minmax(340px,2.5fr) minmax(210px,.95fr);gap:7px;min-height:720px}
.side,.stage{border:3px ridge #c58bac;border-radius:8px;background:linear-gradient(135deg,#ffeaf4,#f5d4e6);overflow:hidden}
.side h2{margin:0;padding:9px 7px;text-align:center;font:700 27px Fredoka;background:linear-gradient(#f8d8e8,#e9b4d0);border-bottom:3px ridge #c58bac;text-shadow:2px 2px white}
.side-scroll{height:calc(100% - 48px);max-height:680px;overflow:auto;padding:7px}
.group{margin-bottom:12px;padding-bottom:9px;border-bottom:2px dotted #c48cac}
.group h3{text-align:center;margin:2px 0 7px;font:700 17px Fredoka;text-shadow:1px 1px white}
.items{display:grid;grid-template-columns:repeat(3,1fr);gap:6px}
.item{min-height:86px;padding:5px;background:linear-gradient(#fff9fc,#f8dce9);border:2px solid #b77f9e;border-radius:5px;box-shadow:inset 0 0 0 2px #fff}
.item .emoji{display:block;font-size:31px;line-height:1.25}
.item small{font-size:10px;display:block}
.item.selected{outline:3px solid #b66ca0;background:#f5c6df}
.stage{position:relative;min-height:720px;background:
radial-gradient(ellipse at 50% 43%,#fff7fa 0,#fbe5f0 43%,transparent 70%),
repeating-radial-gradient(ellipse at 50% 50%,#ffffff33 0 2px,transparent 3px 20px),
linear-gradient(135deg,#f8d8e8,#e8c7e7)}
.stage:before,.stage:after{content:"✿ ❀ ✧ ♡ ✧ ❀ ✿";position:absolute;left:0;right:0;text-align:center;color:#c28bb0;letter-spacing:12px;font-size:24px;opacity:.8}
.stage:before{top:8px}.stage:after{bottom:8px}
.stage-title{text-align:center;position:relative;z-index:2;padding:9px;font:700 17px Fredoka;letter-spacing:2px;color:#8d547b;text-shadow:1px 1px white}
.doll-wrap{height:600px;display:flex;justify-content:center;align-items:center;position:relative;z-index:1}
.doll{height:min(590px,82%);width:min(390px,90%);overflow:visible;filter:drop-shadow(0 5px 4px #9c6d8c33)}
.spark{position:absolute;color:#fff;font-size:27px;text-shadow:0 0 5px #d58ab8;animation:twinkle 2s infinite alternate}
.s1{top:17%;left:10%}.s2{top:24%;right:10%}.s3{bottom:18%;left:13%}.s4{bottom:22%;right:12%}
@keyframes twinkle{to{opacity:.35;transform:scale(.8)}}
.stage-caption{text-align:center;position:relative;z-index:2;font:700 14px Fredoka;color:#9b6386}
.score{margin:6px;padding:8px;background:linear-gradient(#f8d8e8,#e9b4d0);border:2px ridge #c58bac;border-radius:6px;text-align:center;font:700 17px Fredoka}
.progress{height:12px;background:#fff;border:1px solid #9d6687;border-radius:20px;overflow:hidden;margin-top:5px}
.progress span{display:block;width:68%;height:100%;background:linear-gradient(90deg,#e88dbb,#c99adf)}
.footer{display:flex;justify-content:space-between;gap:8px;align-items:center;flex-wrap:wrap;padding:8px 12px;margin-top:6px;background:linear-gradient(#fbe4ef,#eebbd4);border:3px ridge #d59ab9;border-radius:8px;font-size:13px;font-weight:700}
.colorpick{width:100px;height:27px;border:2px solid #9b6685;border-radius:5px;background:white}
#toast{position:fixed;bottom:18px;left:50%;transform:translateX(-50%);background:#fff2f8;border:2px solid #b77f9e;border-radius:20px;padding:10px 18px;box-shadow:0 3px 12px #75405c44;display:none;z-index:10;font-weight:700}
@media(max-width:900px){.layout{grid-template-columns:1fr 1.5fr;}.right{grid-column:1/-1}.right .side-scroll{max-height:none}.right .items{grid-template-columns:repeat(6,1fr)}}
@media(max-width:620px){.topbar{display:block;text-align:center}.logo{white-space:normal;margin-bottom:7px}.layout{grid-template-columns:1fr}.stage{grid-row:1;min-height:590px}.doll-wrap{height:470px}.doll{height:440px}.side-scroll{max-height:none}.right{grid-column:auto}.right .items{grid-template-columns:repeat(3,1fr)}}
</style>
</head>
<body>
<div class="shell">
  <header class="topbar">
    <div class="logo"><span>☆</span> MUÑECA Y2K DRESS UP — SWEET TIGER & ORCHID FASHION v1.03 <span>☆</span></div>
    <div class="topbuttons"><button onclick="saveGame()">⭐</button><button onclick="help()">☠</button></div>
  </header>
  <nav class="toolbar">
    <button onclick="saveGame()">↑ GUARDAR</button>
    <button onclick="resetGame()">🦋 REINICIAR</button>
    <button onclick="randomize()">☆ ALEATORIO</button>
    <button onclick="window.print()">🖨 IMPRIMIR</button>
    <button onclick="help()">☆ AYUDA?</button>
    <button onclick="document.body.classList.toggle('night')">☾</button>
  </nav>

  <main class="layout">
    <aside class="side">
      <h2>🌸 ROPA ♡</h2>
      <div class="side-scroll" id="clothes"></div>
    </aside>

    <section class="stage" id="stage">
      <div class="stage-title">✧ SWEET TIGER & ORCHID ✧</div>
      <span class="spark s1">✧</span><span class="spark s2">♡</span><span class="spark s3">✿</span><span class="spark s4">✧</span>
      <div class="doll-wrap">
        <svg class="doll" viewBox="0 0 360 590" aria-label="Muñeca para vestir">
          <defs>
            <linearGradient id="hair" x2="1" y2="1"><stop stop-color="#392044"/><stop offset=".55" stop-color="#68406e"/><stop offset="1" stop-color="#281b35"/></linearGradient>
            <linearGradient id="skin" x2="0" y2="1"><stop stop-color="#ffe0cb"/><stop offset="1" stop-color="#eeb69f"/></linearGradient>
            <linearGradient id="dress" x2="0" y2="1"><stop stop-color="#ffd7e7"/><stop offset="1" stop-color="#e79abf"/></linearGradient>
          </defs>
          <!-- pelo largo detrás -->
          <path id="hairBack" d="M91 150 Q60 30 180 25 Q300 30 270 160 L292 420 Q270 500 235 440 L125 450 Q80 500 65 420Z" fill="url(#hair)" stroke="#38233f" stroke-width="5"/>
          <!-- piernas -->
          <path d="M137 410 Q125 475 132 530 L160 530 Q168 470 174 420Z" fill="url(#skin)" stroke="#9c6a65" stroke-width="2"/>
          <path d="M190 415 Q194 475 205 530 L232 530 Q224 470 220 405Z" fill="url(#skin)" stroke="#9c6a65" stroke-width="2"/>
          <!-- calcetas y zapatos -->
          <path d="M130 490 L161 490 L162 526 L130 526Z M199 490 L229 490 L235 526 L204 526Z" fill="#f9d8e8" stroke="#a76e91" stroke-width="3"/>
          <path d="M126 523 Q145 510 166 528 L169 550 L120 550 Q115 536 126 523Z M201 524 Q220 512 238 529 L247 550 L199 550Z" fill="#d98bb6" stroke="#71435f" stroke-width="4"/>
          <path d="M125 536 L163 536 M207 536 L241 536" stroke="#fff2f8" stroke-width="5"/>
          <!-- brazos -->
          <path d="M117 210 Q84 265 77 350 Q78 369 94 366 Q111 330 139 275Z" fill="url(#skin)" stroke="#a36c68" stroke-width="3"/>
          <path d="M242 210 Q278 270 286 345 Q285 367 268 365 Q248 328 220 275Z" fill="url(#skin)" stroke="#a36c68" stroke-width="3"/>
          <!-- cuello -->
          <path d="M158 160 L202 160 L205 207 L155 207Z" fill="url(#skin)"/>
          <!-- cara -->
          <ellipse cx="180" cy="122" rx="65" ry="82" fill="url(#skin)" stroke="#a36c68" stroke-width="2"/>
          <!-- flequillo -->
          <path id="hairFront" d="M115 115 Q95 35 177 40 Q258 34 247 118 Q226 90 211 91 L204 127 L190 91 L178 128 L163 91 L149 127 L139 91Z" fill="#4d3158" stroke="#38233f" stroke-width="4"/>
          <!-- ojos cerrados estilo ilustración -->
          <path d="M139 133 Q153 143 166 133 M194 133 Q207 143 221 133" fill="none" stroke="#432d3b" stroke-width="5" stroke-linecap="round"/>
          <path d="M145 132 l-5 -6 M157 136 l-1 -7 M201 136 l1 -7 M214 132 l5 -6" stroke="#432d3b" stroke-width="2"/>
          <ellipse cx="132" cy="153" rx="13" ry="6" fill="#e98ea9" opacity=".55"/><ellipse cx="228" cy="153" rx="13" ry="6" fill="#e98ea9" opacity=".55"/>
          <path d="M174 160 Q180 166 187 160" fill="none" stroke="#b95e78" stroke-width="3" stroke-linecap="round"/>
          <!-- torso base -->
          <path d="M143 197 Q180 215 217 197 L239 292 L121 292Z" fill="url(#dress)" stroke="#9c6684" stroke-width="3"/>
          <!-- vestido/cuerpo intercambiable -->
          <path id="outfitTop" d="M145 205 Q180 225 215 205 L229 286 L131 286Z" fill="#eeb2cf" stroke="#80506e" stroke-width="3"/>
          <path id="outfitSkirt" d="M132 280 Q180 300 228 280 L280 432 Q180 470 80 432 L132 280Z" fill="#f3c4d9" stroke="#80506e" stroke-width="4"/>
          <path d="M131 286 Q180 310 229 286 M100 420 Q180 450 260 420" fill="none" stroke="#fff0f7" stroke-width="7"/>
          <!-- patrón tigre opcional -->
          <g id="tigerPattern" opacity=".9" fill="none" stroke="#8e573f" stroke-width="6" stroke-linecap="round">
            <path d="M143 315 l-15 18 M175 323 l-13 20 M211 315 l14 20 M115 370 l20 10 M243 365 l-20 12 M155 395 l-10 19 M205 395 l12 18"/>
          </g>
          <!-- mangas -->
          <path d="M142 207 Q113 207 108 245 L130 260 L151 222Z M218 207 Q247 207 252 245 L230 260 L209 222Z" fill="#f8dce9" stroke="#9c6684" stroke-width="3"/>
          <!-- collar -->
          <path d="M153 204 Q180 230 207 204" fill="none" stroke="#fff4f8" stroke-width="8"/>
          <g id="necklace"><path d="M148 207 Q180 246 212 207" fill="none" stroke="#f5e6c6" stroke-width="5"/><circle cx="180" cy="239" r="7" fill="#e99cbd" stroke="#fff" stroke-width="2"/></g>
          <!-- hair clips -->
          <g id="hairAccessory"><path d="M112 88 l12 -12 12 12 -12 12Z" fill="#f5a8ca" stroke="#fff" stroke-width="3"/><path d="M230 88 l12 -12 12 12 -12 12Z" fill="#c6a5e5" stroke="#fff" stroke-width="3"/></g>
          <!-- alas -->
          <g id="wings" opacity="0"><path d="M118 240 Q30 180 55 270 Q78 300 120 272 Q35 320 88 350 Q120 330 137 270Z M242 240 Q330 180 305 270 Q282 300 240 272 Q325 320 272 350 Q240 330 223 270Z" fill="#f6d9f0" stroke="#b987c3" stroke-width="3"/></g>
          <!-- objeto en mano -->
          <g id="held"><text x="63" y="350" font-size="42">🐯</text></g>
          <!-- sparkle hair -->
          <text x="240" y="63" font-size="25">✦</text>
        </svg>
      </div>
      <div class="stage-caption">♡ ARRÁSTRA Y COLOCA LOS ACCESORIOS SOBRE LA MUÑECA ♡</div>
    </section>

    <aside class="side right">
      <h2>🌸 ACCESORIOS ⭐</h2>
      <div class="side-scroll" id="accessories"></div>
      <div class="score">PUNTOS DE ESTILO: <span id="score">1280</span> ⭐<div class="progress"><span></span></div></div>
    </aside>
  </main>

  <footer class="footer">
    <span>»» ¡CREÁ TU LOOK FAVORITO! ««</span>
    <span>Tema: TIGER & ORCHID Y2K SWEET</span>
    <span id="savedStatus">Guardado automático ✓ ♡</span>
    <label>COLOR: <input class="colorpick" type="color" value="#f5c5dc" onchange="changeColor(this.value)"></label>
  </footer>
</div>
<div id="toast"></div>
<script>
const clothing=[
 ['VESTIDOS','dresses',[['🐯','Vestido tiger','#e9a15d'],['🌸','Vestido orchid','#e99dbd'],['🌼','Vestido floral','#f2c9a4']]],
 ['PELO','hair',[['💜','Largo violeta','#68406e'],['🌸','Rosa con flores','#e99abd'],['🖤','Coleta oscura','#33283c']]],
 ['TOPS','tops',[['🎀','Top corset','#e99cbd'],['🐻','Suéter bear','#f1d99d'],['🐯','Chaqueta tiger','#d99556']]],
 ['FALDAS','skirts',[['🌷','Falda rosa','#edb4d0'],['💜','Falda lila','#bba0d9'],['🦋','Falda celeste','#a8cce5']]]
];
const accessory=[
 ['ALAS','wings',[['🦋','Alas mariposa','butterfly'],['🪽','Alas lilas','lilac'],['🦋','Alas rosas','pink']]],
 ['ACCESORIOS CABEZA','head',[['🎀','Moño','bow'],['⭐','Estrellas','stars'],['🌺','Corona floral','flower']]],
 ['JOYERÍA','jewelry',[['📿','Collar perlas','pearls'],['💗','Collar corazón','heart'],['🌸','Gargantilla flor','flower']]],
 ['OBJETO','object',[['🪄','Varita','wand'],['🐯','Tigre plush','tiger'],['💐','Ramo flores','bouquet']]],
 ['FONDO','background',[['🌸','Orquídeas','orchid'],['🌷','Jardín rosa','garden'],['☁️','Cielo azul','sky']]]
];
let points=1280;
function makeGroups(data,target){
 const root=document.getElementById(target);
 data.forEach(([title,category,items])=>{
  const group=document.createElement('div');group.className='group';
  group.innerHTML=`<h3>${title}</h3><div class="items"></div>`;
  const grid=group.querySelector('.items');
  items.forEach(([emoji,name,value])=>{
   const b=document.createElement('button');b.className='item';b.innerHTML=`<span class="emoji">${emoji}</span><small>${name}</small>`;
   b.onclick=()=>apply(category,value,b);
   grid.appendChild(b);
  });
  root.appendChild(group);
 });
}
function toast(msg){const t=document.getElementById('toast');t.textContent=msg;t.style.display='block';clearTimeout(window.toastTimer);window.toastTimer=setTimeout(()=>t.style.display='none',1900)}
function apply(category,value,button){
 if(button){button.parentElement.querySelectorAll('.item').forEach(x=>x.classList.remove('selected'));button.classList.add('selected')}
 if(category==='dresses'){document.getElementById('outfitTop').setAttribute('fill',value);document.getElementById('outfitSkirt').setAttribute('fill',value);document.getElementById('tigerPattern').style.display=value==='#e9a15d'?'block':'none'}
 if(category==='tops'){document.getElementById('outfitTop').setAttribute('fill',value)}
 if(category==='skirts'){document.getElementById('outfitSkirt').setAttribute('fill',value)}
 if(category==='hair'){document.getElementById('hairBack').style.fill=value;document.getElementById('hairFront').style.fill=value}
 if(category==='wings'){document.getElementById('wings').style.opacity=1;document.getElementById('wings').querySelectorAll('path').forEach(p=>p.setAttribute('fill',value==='pink'?'#f8d5e8':value==='lilac'?'#d9c7f2':'#e8e2fa'))}
 if(category==='head'){document.getElementById('hairAccessory').style.display='block';document.getElementById('hairAccessory').style.opacity=1}
 if(category==='jewelry'){document.getElementById('necklace').style.display='block'}
 if(category==='object'){document.getElementById('held').querySelector('text').textContent=value==='wand'?'🪄':value==='bouquet'?'💐':'🐯'}
 if(category==='background'){const colors={orchid:'linear-gradient(135deg,#f7d5e9,#e9c6ed)',garden:'linear-gradient(135deg,#f6d3df,#d9ead5)',sky:'linear-gradient(135deg,#b9d9f5,#f5e8f5)'};document.getElementById('stage').style.background=colors[value]}
 points+=20;document.getElementById('score').textContent=points;
 document.getElementById('savedStatus').textContent='Look actualizado ✓';
}
function saveGame(){const data={top:document.getElementById('outfitTop').getAttribute('fill'),skirt:document.getElementById('outfitSkirt').getAttribute('fill'),hair:document.getElementById('hairFront').style.fill,points};localStorage.setItem('y2kDollSave',JSON.stringify(data));toast('¡Tu look fue guardado! ♡');document.getElementById('savedStatus').textContent='Guardado ✓'}
function resetGame(){location.reload()}
function randomize(){const colors=['#e9a15d','#e99dbd','#f2c9a4','#bba0d9','#a8cce5','#f1d99d'];const c=()=>colors[Math.floor(Math.random()*colors.length)];document.getElementById('outfitTop').setAttribute('fill',c());document.getElementById('outfitSkirt').setAttribute('fill',c());document.getElementById('hairBack').style.fill=c();document.getElementById('hairFront').style.fill=document.getElementById('hairBack').style.fill;document.getElementById('wings').style.opacity=Math.random()>.5?1:0;points+=50;document.getElementById('score').textContent=points;toast('¡Look aleatorio creado! ✨')}
function help(){toast('Elegí prendas y accesorios en los paneles laterales. ¡Combiná todo!')}
function changeColor(color){document.documentElement.style.setProperty('--pink',color);document.querySelector('.shell').style.background=`linear-gradient(135deg,${color},#f8e5ef)`;toast('¡Color actualizado!')}
makeGroups(clothing,'clothes');makeGroups(accessory,'accessories');
</script>
</body>
</html>'''
path = Path("/mnt/data/pink_doll_y2k.html")
path.write_text(html, encoding="utf-8")
print(f"Creado: {path} ({path.stat().st_size} bytes)")
