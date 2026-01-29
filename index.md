<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Flower Garden</title>

<style>
body {
  margin:0;
  padding:20px;
  background:#fff0f6;
  text-align:center;
  font-family:Arial;
}

h1 { color:#c2185b; }

button {
  padding:10px 18px;
  margin:5px;
  font-size:16px;
  background:#ff69b4;
  color:white;
  border:none;
  border-radius:8px;
  cursor:pointer;
}

#garden {
  position:relative;
  height:80vh;
  width:100%;
  overflow:hidden;
  cursor:crosshair;
}

.flower {
  position:absolute;
  animation: pop .3s ease-out;
}

@keyframes pop {
  from {transform:scale(0);}
  to {transform:scale(1);}
}
</style>
</head>

<body>

<h1>🌸 Flower Garden for You 🌸</h1>
<p>Click anywhere to plant flowers</p>

<button onclick="clearGarden()">Clear Garden</button>
<button onclick="toggleAuto()">Auto Bloom</button>

<div id="garden"></div>

<script>
const garden = document.getElementById("garden");
let auto = null;

function plantFlower(x,y){
  const f = document.createElement("div");
  const flowers = ["🌸","🌷","🌹","🌺","🌼","🌻"];
  f.className = "flower";
  f.innerText = flowers[Math.floor(Math.random()*flowers.length)];
  f.style.left = x+"px";
  f.style.top = y+"px";
  f.style.fontSize = (30+Math.random()*40)+"px";
  garden.appendChild(f);
}

garden.onclick = (e)=>{
  plantFlower(e.offsetX, e.offsetY);
}

function clearGarden(){
  garden.innerHTML="";
}

function toggleAuto(){
  if(auto){
    clearInterval(auto);
    auto=null;
  } else {
    auto = setInterval(()=>{
      plantFlower(
        Math.random()*garden.clientWidth,
        Math.random()*garden.clientHeight
      );
    },200);
  }
}
</script>

</body>
</html>
