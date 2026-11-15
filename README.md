
<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Emprego Moz</title>
<style>
body{margin:0;font-family:Arial;background:#f2f5f8;color:#193047}
header{background:#087443;color:white;text-align:center;padding:28px 15px}
header h1{margin:0;font-size:30px}
main{max-width:700px;margin:25px auto;padding:15px}
input,select{width:100%;padding:14px;margin:8px 0;border:1px solid #ccc;border-radius:8px;font-size:16px;box-sizing:border-box}
.vaga{background:white;padding:18px;margin:14px 0;border-radius:10px;border-left:5px solid #087443}
button{background:#087443;color:white;padding:12px;border:0;border-radius:7px}
footer{text-align:center;padding:20px}
</style>
</head>
<body>
<header>
<h1>🇲🇿 EMPREGO MOZ</h1>
<p>O teu futuro começa aqui!</p>
</header>
<main>
<h2>Encontra oportunidades de emprego</h2>
<input id="pesquisa" placeholder="Pesquisar emprego...">
<select id="provincia">
<option value="">Todas as províncias</option>
<option>Cabo Delgado</option>
<option>Nampula</option>
<option>Maputo</option>
<option>Sofala</option>
<option>Zambézia</option>
<option>Tete</option>
<option>Niassa</option>
<option>Manica</option>
<option>Gaza</option>
<option>Inhambane</option>
</select>
<h2>Oportunidades recentes</h2>
<div id="vagas"></div>
</main>
<footer>Emprego Moz © 2026</footer>
<script>
const oportunidades=[
{nome:"Técnico de Farmácia",provincia:"Cabo Delgado"},
{nome:"Assistente Administrativo",provincia:"Nampula"},
{nome:"Enfermeiro",provincia:"Maputo"}
];
function mostrar(){
let p=document.getElementById("pesquisa").value.toLowerCase();
let local=document.getElementById("provincia").value;
let lista=oportunidades.filter(v=>
v.nome.toLowerCase().includes(p)&&(!local||v.provincia===local));
document.getElementById("vagas").innerHTML=lista.map(v=>
`<div class="vaga"><h3>${v.nome}</h3><p>${v.provincia}</p></div>`
).join("")||"Nenhuma oportunidade encontrada.";
}
document.getElementById("pesquisa").addEventListener("input",mostrar);
document.getElementById("provincia").addEventListener("change",mostrar);
mostrar();
</script>
</body>
</html>

