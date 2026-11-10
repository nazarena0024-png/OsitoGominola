
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pink Doll Dress Up ♡</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@500;700&family=Pacifico&display=swap');

* { box-sizing: border-box; }

body {
  margin: 0;
  font-family: Quicksand, sans-serif;
  color: #975b83;
  background: #f7d6e7;
  background-image: radial-gradient(#fff 1.5px, transparent 1.5px);
  background-size: 22px 22px;
}

.game {
  max-width: 950px;
  margin: 25px auto;
  padding: 18px;
  background: #fff7fb;
  border: 5px solid white;
  border-radius: 22px;
  box-shadow: 0 6px 0 #dca8c8;
}

header {
  text-align: center;
  background: #f5c4dd;
  border: 3px solid white;
  border-radius: 15px;
  padding: 12px;
}

h1 {
  font-family: Pacifico, cursive;
  font-size: 32px;
  margin: 0;
  color: #bd6597;
  text-shadow: 2px 2px white;
}

header p { margin: 4px; }

.content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 18px;
  margin-top: 18px;
}

.panel {
  background: #fce8f2;
  border: 3px solid white;
  border-radius: 17px;
  padding: 14px;
  text-align: center;
}

h2 {
  font-family: Pacifico, cursive;
  color: #bd6597;
  margin: 5px;
}

.dressing-room {
  height: 390px;
  border: 3px solid white;
  border-radius: 15px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  overflow: hidden;
  background: #f7d9e9;
  transition: background .3s;
}

.dressing-room svg {
  width: 245px;
  height: 365px;
  position: relative;
  z-index: 2;
}

.decor {
  position: absolute;
  font-size: 25px;
  color: white;
}

.d1 { top: 20px; left: 20px; }
.d2 { top: 70px; right: 20px; }
.d3 { bottom: 35px; left: 25px; }
.d4 { bottom: 80px; right: 20px; }

.message {
  font-family: Pacifico, cursive;
  color: #c27ba5;
  margin: 12px 0;
}

button {
  font-family: Quicksand, sans-serif;
  font-weight: bold;
  cursor: pointer;
  border: 2px solid white;
  border-radius: 10px;
  padding: 9px 12px;
  background: #f3b9d5;
  color: #854d70;
  box-shadow: 0 3px 0 #d99bbd;
  transition: .15s;
}

button:hover {
  background: #e99dc4;
  transform: translateY(-2px);
}

button:active {
  transform: translateY(2px);
  box-shadow: none;
}

.tabs {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 7px;
  margin: 15px 0;
}

.tabs button.active {
  background: #bd77a4;
  color: white;
}

.items {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 9px;
  margin-top: 12px;
}

.item {
  min-height: 88px;
  background: white;
  border: 2px solid #efc4dc;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 5px;
  box-shadow: none;
  padding: 5px;
}

.item span { font-size: 28px; }
.item small { font-size: 10px; }

.actions {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 9px;
  margin-top: 17px;
}

.backgrounds {
  display: flex;
  justify-content: center;
  gap: 9px;
  margin-top: 12px;
}

.backgrounds button {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  padding: 0;
  border: 3px solid white;
}

footer {
  text-align: center;
  font-size: 12px;
  margin-top: 20px;
  color: #c27ba5;
}

@media(max-width:650px) {
  .game { margin: 8px; padding: 10px; }
  .content { grid-template-columns: 1fr; }
  .dressing-room { height: 370px; }
}
</style>
</head>

<body>

<div class="game">

<header>
  <h1>Pink Doll Dress Up ♡</h1>
  <p>✧ Make your own fashion style! ✧</p>
</header>

<div class="content">

<!-- MUÑECA -->
<section class="panel">
  <h2>My Doll ✿</h2>

  <div class="dressing-room" id="room">

    <span class="decor d1">✧</span>
    <span class="decor d2">♡</span>
    <span class="decor d3">✧</span>
    <span class="decor d4">♡</span>

    <svg viewBox="0 0 200 350">

      <!-- Pelo trasero -->
      <path id="hairBack"
      d="M48 65 Q25 0 100 7 Q175 0 152 65
      L154 190 Q100 220 46 190 Z"
      fill="#754333"/>

      <!-- Piernas -->
      <path d="M76 215 L73 293 L92 293 L100 225Z"
      fill="#f2c4a9"/>
      <path d="M108 215 L109 293 L128 293 L123 215Z"
      fill="#f2c4a9"/>

      <!-- Zapatos -->
      <path id="shoe1"
      d="M70 290 Q80 282 96 291 L99 307 L66 307Z"
      fill="#ed91bd"/>
      <path id="shoe2"
      d="M107 291 Q125 282 133 291 L138 307 L105 307Z"
      fill="#ed91bd"/>

      <!-- Brazos -->
      <path d="M67 108 Q48 119 53 180"
      fill="none" stroke="#f2c4a9" stroke-width="13"
      stroke-linecap="round"/>

      <path d="M133 108 Q152 119 147 180"
      fill="none" stroke="#f2c4a9" stroke-width="13"
      stroke-linecap="round"/>

      <!-- Cuello -->
      <rect x="89" y="83" width="22" height="28"
      rx="8" fill="#f2c4a9"/>

      <!-- Cara -->
      <ellipse cx="100" cy="59" rx="37" ry="45"
      fill="#f2c4a9"/>

      <!-- Pelo frontal -->
      <path id="hairFront"
      d="M63 53 Q53 7 101 12 Q147 5 138 58
      Q121 35 108 40 Q84 53 63 53Z"
      fill="#754333"/>

      <!-- Ojos -->
      <ellipse cx="86" cy="62" rx="3.5" ry="5"
      fill="#54372e"/>
      <ellipse cx="114" cy="62" rx="3.5" ry="5"
      fill="#54372e"/>

      <!-- Mejillas -->
      <ellipse cx="76" cy="75" rx="7" ry="4"
      fill="#ed9eb2"/>
      <ellipse cx="124" cy="75" rx="7" ry="4"
      fill="#ed9eb2"/>

      <!-- Boca -->
      <path d="M94 81 Q100 87 106 81"
      fill="none" stroke="#b86c75" stroke-width="2"
      stroke-linecap="round"/>

      <!-- Parte superior -->
      <path id="top"
      d="M77 105 L100 111 L123 105 L137 178
      L119 183 L116 151 L116 210 L84 210
      L84 151 L81 183 L63 178Z"
      fill="#f4a8ce"/>

      <!-- Falda -->
      <path id="skirt"
      d="M83 175 L117 175 L143 245 L57 245Z"
      fill="#9bbde9"/>

      <!-- Moño -->
      <g id="bow">
        <path d="M130 24 L148 12 L145 39Z"
        fill="#f3a6ce"/>
        <path d="M130 24 L113 12 L116 39Z"
        fill="#f3a6ce"/>
        <circle cx="130" cy="25" r="6" fill="#fff0f6"/>
      </g>

      <!-- Collar -->
      <g id="necklace">
        <path d="M84 108 Q100 129 116 108"
        fill="none" stroke="#f5d17e" stroke-width="3"/>
        <circle cx="100" cy="124" r="5" fill="#f5d17e"/>
      </g>

    </svg>

    <span id="extra" style="
      position:absolute; top:105px; left:50%;
      transform:translateX(-50%);
      z-index:3; font-size:25px; display:none;">
    </span>

  </div>

  <p class="message" id="message">Looking cute! ♡</p>

  <h2>Choose a background</h2>

  <div class="backgrounds">
    <button style="background:#f7d9e9"
    onclick="changeBG('#f7d9e9')"></button>

    <button style="background:#d9eafa"
    onclick="changeBG('#d9eafa')"></button>

    <button style="background:#e8dcf8"
    onclick="changeBG('#e8dcf8')"></button>

    <button style="background:#f9e9b9"
    onclick="changeBG('#f9e9b9')"></button>

    <button style="background:#dcebd9"
    onclick="changeBG('#dcebd9')"></button>
  </div>
</section>

<!-- ARMARIO -->
<section class="panel">
  <h2>My Wardrobe ♡</h2>
  <p>Choose your favorite clothes!</p>

  <div class="tabs">
    <button class="active" onclick="showCategory('tops',this)">Tops</button>
    <button onclick="showCategory('skirts',this)">Skirts</button>
    <button onclick="showCategory('shoes',this)">Shoes</button>
    <button onclick="showCategory('hair',this)">Hair</button>
    <button onclick="showCategory('extras',this)">Extras</button>
  </div>

  <div class="items" id="items"></div>

  <div class="actions">
    <button onclick="randomLook()">🎀 Random look</button>
    <button onclick="resetLook()">↺ Reset</button>
    <button onclick="saveLook()">💗 Save look</button>
    <button onclick="loadLook()">📂 Load look</button>
  </div>
</section>

</div>

<footer>
  ✧ Made with love ♡ Pink Doll Fashion Studio ✧
</footer>

</div>

<script>

const wardrobe = {

tops: [
  {name:"Pink top",icon:"🎀",color:"#f4a8ce"},
  {name:"White blouse",icon:"🤍",color:"#fffafa"},
  {name:"Blue sweater",icon:"🩵",color:"#9dc9ec"},
  {name:"Purple top",icon:"💜",color:"#c9a5e8"},
  {name:"Yellow shirt",icon:"🌼",color:"#f4d77e"},
  {name:"Red top",icon:"❤️",color:"#e98c9c"}
],

skirts: [
  {name:"Blue skirt",icon:"🩵",color:"#9bbde9"},
  {name:"Pink skirt",icon:"🌸",color:"#f4a8ce"},
  {name:"Purple skirt",icon:"💜",color:"#c6a3df"},
  {name:"Black skirt",icon:"🖤",color:"#55505e"},
  {name:"Cream skirt",icon:"🤍",color:"#f2dfbb"},
  {name:"Green skirt",icon:"🍀",color:"#a9cba1"}
],

shoes: [
  {name:"Pink shoes",icon:"👠",color:"#ed91bd"},
  {name:"White shoes",icon:"🤍",color:"#fffafa"},
  {name:"Blue shoes",icon:"🩵",color:"#9dc9ec"},
  {name:"Black shoes",icon:"🖤",color:"#55505e"}
],

hair: [
  {name:"Brown hair",icon:"🤎",color:"#754333"},
  {name:"Blonde hair",icon:"💛",color:"#e8bd68"},
  {name:"Black hair",icon:"🖤",color:"#332b36"},
  {name:"Pink hair",icon:"🩷",color:"#e99ac3"},
  {name:"Red hair",icon:"❤️",color:"#b95c4b"},
  {name:"Purple hair",icon:"💜",color:"#9472bd"}
],

extras: [
  {name:"Pink bow",icon:"🎀",type:"bow",value:"#f3a6ce"},
  {name:"Purple bow",icon:"💜",type:"bow",value:"#b99ad9"},
  {name:"Yellow bow",icon:"🌼",type:"bow",value:"#f2d47c"},
  {name:"Necklace",icon:"📿",type:"necklace"},
  {name:"Star",icon:"⭐",type:"star"},
  {name:"Heart",icon:"💗",type:"heart"}
]

};

const defaults = {
  tops:"#f4a8ce",
  skirts:"#9bbde9",
  shoes:"#ed91bd",
  hair:"#754333",
  bow:"#f3a6ce",
  necklace:true,
  extra:""
};

let current = {...defaults};

function showCategory(category, button) {

  const container = document.getElementById("items");
  container.innerHTML = "";

  document.querySelectorAll(".tabs button")
    .forEach(b => b.classList.remove("active"));

  if(button) button.classList.add("active");

  wardrobe[category].forEach(item => {

    const btn = document.createElement("button");
    btn.className = "item";

    btn.innerHTML = `
      <span>${item.icon}</span>
      <small>${item.name}</small>
    `;

    btn.onclick = () => selectItem(category,item);

    container.appendChild(btn);

  });

}

function selectItem(category,item) {

  if(category === "tops") {
    current.tops = item.color;
    document.getElementById("top").setAttribute("fill",item.color);
  }

  if(category === "skirts") {
    current.skirts = item.color;
    document.getElementById("skirt").setAttribute("fill",item.color);
  }

  if(category === "shoes") {
    current.shoes = item.color;
    document.getElementById("shoe1").setAttribute("fill",item.color);
    document.getElementById("shoe2").setAttribute("fill",item.color);
  }

  if(category === "hair") {
    current.hair = item.color;
    document.getElementById("hairBack").setAttribute("fill",item.color);
    document.getElementById("hairFront").setAttribute("fill",item.color);
  }

  if(category === "extras") {

    if(item.type === "bow") {
      current.bow = item.value;
      document.querySelectorAll("#bow path")
        .forEach(p => p.setAttribute("fill",item.value));
      current.extra = "";
    }

    if(item.type === "necklace") {
      current.necklace = true;
      document.getElementById("necklace").style.display = "block";
      current.extra = "";
    }

    if(item.type === "star" || item.type === "heart") {
      current.extra = item.icon;
      document.getElementById("extra").textContent = item.icon;
      document.getElementById("extra").style.display = "block";
    }

  }

  document.getElementById("message").textContent =
    "A new style! So pretty! ♡";

}

function changeBG(color) {
  document.getElementById("room").style.background = color;
}

function resetLook() {

  current = {...defaults};

  document.getElementById("top").setAttribute("fill",defaults.tops);
  document.getElementById("skirt").setAttribute("fill",defaults.skirts);

  document.getElementById("shoe1").setAttribute("fill",defaults.shoes);
  document.getElementById("shoe2").setAttribute("fill",defaults.shoes);

  document.getElementById("hairBack").setAttribute("fill",defaults.hair);
  document.getElementById("hairFront").setAttribute("fill",defaults.hair);

  document.querySelectorAll("#bow path")
    .forEach(p => p.setAttribute("fill",defaults.bow));

  document.getElementById("necklace").style.display = "block";
  document.getElementById("extra").style.display = "none";

  changeBG("#f7d9e9");

  document.getElementById("message").textContent =
    "Fresh new look! ♡";

}

function randomLook() {

  for(const category of ["tops","skirts","shoes","hair","extras"]) {

    const options = wardrobe[category];
    const item = options[Math.floor(Math.random()*options.length)];

    selectItem(category,item);
  }

  document.getElementById("message").textContent =
    "Your random outfit is ready! ✨";

}

function saveLook() {

  localStorage.setItem("pinkDollLook",JSON.stringify(current));

  document.getElementById("message").textContent =
    "Your outfit has been saved! 💗";

}

function loadLook() {

  const saved = localStorage.getItem("pinkDollLook");

  if(!saved) {
    document.getElementById("message").textContent =
      "You haven't saved an outfit yet! ♡";
    return;
  }

  const look = JSON.parse(saved);

  current = {...look};

  document.getElementById("top").setAttribute("fill",look.tops);
  document.getElementById("skirt").setAttribute("fill",look.skirts);

  document.getElementById("shoe1").setAttribute("fill",look.shoes);
  document.getElementById("shoe2").setAttribute("fill",look.shoes);

  document.getElementById("hairBack").setAttribute("fill",look.hair);
  document.getElementById("hairFront").setAttribute("fill",look.hair);

  document.querySelectorAll("#bow path")
    .forEach(p => p.setAttribute("fill",look.bow));

  document.getElementById("necklace").style.display =
    look.necklace ? "block" : "none";

  document.getElementById("extra").textContent = look.extra || "";
  document.getElementById("extra").style.display =
    look.extra ? "block" : "none";

  document.getElementById("message").textContent =
    "Your saved outfit is back! ♡";

}

showCategory("tops");

</script>

</body>
</html>

