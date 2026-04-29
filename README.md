<!DOCTYPE html>
<html lang="ro">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Clinică Stomatologică Premium</title>

<style>
body{
margin:0;
font-family:system-ui;
background:#0b1220;
color:white;
}

/* HERO */
.hero{
height:90vh;
background:url('https://images.unsplash.com/photo-1606811841689-23dfddce3a1b?auto=format&fit=crop&w=1600&q=80') center/cover;
display:flex;
align-items:center;
justify-content:center;
text-align:center;
position:relative;
}

.overlay{
position:absolute;
inset:0;
background:linear-gradient(to bottom, rgba(0,0,0,0.6), #0b1220);
}

.content{
position:relative;
max-width:800px;
}

h1{font-size:52px;}
p{color:#cbd5e1;}

/* BUTTON */
.btn{
padding:12px 20px;
margin:6px;
border:none;
border-radius:10px;
cursor:pointer;
background:#0ea5e9;
color:white;
transition:0.3s;
}
.btn:hover{
transform:scale(1.05);
box-shadow:0 0 20px rgba(14,165,233,0.5);
}

/* SECTION */
.section{
padding:70px 20px;
text-align:center;
}

/* GRID */
.grid{
display:flex;
flex-wrap:wrap;
justify-content:center;
gap:20px;
}

.card{
background:#111a2e;
padding:20px;
width:240px;
border-radius:14px;
cursor:pointer;
transition:0.3s;
}
.card:hover{
transform:translateY(-5px) scale(1.03);
}

/* IMG */
.img{
width:100%;
border-radius:10px;
margin-bottom:10px;
}

/* TESTIMONIAL */
.testimonial{
background:#111a2e;
padding:20px;
border-radius:12px;
max-width:500px;
margin:10px auto;
}

/* BEFORE AFTER */
.compare{
display:flex;
flex-wrap:wrap;
justify-content:center;
gap:20px;
}
.compare img{
width:200px;
border-radius:10px;
}

/* CONTACT */
.contact{
background:#0f172a;
padding:60px 20px;
text-align:center;
}

/* MAP */
iframe{
border:none;
border-radius:12px;
margin-top:20px;
}

/* POPUP */
.popup{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:rgba(0,0,0,0.85);
display:none;
align-items:center;
justify-content:center;
}

.popup-content{
background:#111a2e;
padding:25px;
border-radius:12px;
max-width:420px;
width:90%;
}

.close{
float:right;
cursor:pointer;
}

/* INPUT */
input{
width:100%;
padding:10px;
margin:8px 0;
border-radius:8px;
border:none;
}
</style>

</head>

<body>

<!-- HERO -->
<div class="hero">
<div class="overlay"></div>

<div class="content">
<h1>Zâmbet Perfect, Tehnologie Modernă</h1>
<p>Implanturi • Estetică • Tratamente premium</p>

<button class="btn" onclick="scrollToSection()">Programează-te</button>
</div>
</div>

<!-- SERVICII -->
<div class="section">
<h2>Servicii</h2>

<div class="grid">

<div class="card" onclick="openPopup('Implant dentar')">
<img class="img" src="https://images.unsplash.com/photo-1588776814546-1ffcf47267a5">
Implant dentar
</div>

<div class="card" onclick="openPopup('Albire dentară')">
<img class="img" src="https://images.unsplash.com/photo-1588776814546-1ffcf47267a5">
Albire dentară
</div>

<div class="card" onclick="openPopup('Fațete dentare')">
<img class="img" src="https://images.unsplash.com/photo-1588776814546-1ffcf47267a5">
Fațete dentare
</div>

</div>
</div>

<!-- REZULTATE -->
<div class="section">
<h2>Rezultate</h2>

<div class="compare">
<img src="https://images.unsplash.com/photo-1606811841689-23dfddce3a1b">
<img src="https://images.unsplash.com/photo-1606811841689-23dfddce3a1b">
</div>
</div>

<!-- TESTIMONIALE -->
<div class="section">
<h2>Părerea pacienților</h2>

<div class="testimonial">“Servicii excelente și rapide.”</div>
<div class="testimonial">“Recomand cu încredere.”</div>

</div>

<!-- CONTACT -->
<div class="contact">
<h2>Contact & Locație</h2>

<p>📍 Str. Exemplu nr. 10, Cluj-Napoca</p>
<p>📞 Recepție: 07xx xxx xxx</p>
<p>📧 contact@clinica-exemplu.ro</p>

<iframe
src="https://www.google.com/maps?q=Cluj-Napoca&output=embed"
width="90%" height="300">
</iframe>
</div>

<!-- POPUP -->
<div id="popup" class="popup">
<div class="popup-content">

<span class="close" onclick="closePopup()">✖</span>

<h2 id="serviceTitle"></h2>

<p>Durată: urmează personalizat</p>
<p>Preț: urmează personalizat</p>

<input type="date" id="date">
<input type="time" id="time">
<input type="text" id="name" placeholder="Nume">
<input type="text" id="phone" placeholder="Telefon">

<button class="btn" onclick="send()">Trimite programare</button>

</div>
</div>

<script>
let service="";

function openPopup(s){
service=s;
document.getElementById("popup").style.display="flex";
document.getElementById("serviceTitle").innerText=s;
}

function closePopup(){
document.getElementById("popup").style.display="none";
}

function scrollToSection(){
window.scrollTo({top:600, behavior:'smooth'});
}

function send(){
let n=document.getElementById("name").value;
let p=document.getElementById("phone").value;
let d=document.getElementById("date").value;
let t=document.getElementById("time").value;

let url="https://wa.me/40700000000?text=" +
"Programare:%0A" +
"Serviciu: "+service+"%0A" +
"Nume: "+n+"%0A" +
"Telefon: "+p+"%0A" +
"Data: "+d+"%0A" +
"Ora: "+t;

window.open(url);
}
</script>

</body>
</html>