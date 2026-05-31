<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>AI Lottery FIXED</title>

<style>
body{
    font-family: Arial;
    background:#0f172a;
    color:white;
    text-align:center;
    padding:50px;
}

button{
    padding:15px 30px;
    font-size:18px;
    background:#22c55e;
    border:none;
    border-radius:10px;
    cursor:pointer;
}

.box{
    margin-top:30px;
    font-size:22px;
}
</style>
</head>

<body>

<h1>🔥 AI LOTTERY SYSTEM (FIXED)</h1>

<button onclick="runAI()">RUN AI</button>

<div class="box" id="result"></div>

<script>

let history = [77,58,31,63,50,26,91,6,20,87,43,77,31,16,47,50,51];

// =========================
// 📊 3 DIGIT MODEL
// =========================
function getBest3(){
    let freq = {};

    history.forEach(x=>{
        freq[x] = (freq[x]||0)+1;
    });

    return Object.keys(freq).reduce((a,b)=>
        freq[a]>freq[b]?a:b
    );
}

// =========================
// 🎯 2 DIGIT MODEL
// =========================
function getBest2(){
    let freq = {};

    history.forEach(x=>{
        let last2 = x % 100;
        freq[last2] = (freq[last2]||0)+1;
    });

    return Object.keys(freq).reduce((a,b)=>
        freq[a]>freq[b]?a:b
    );
}

// =========================
// 🚀 RUN AI
// =========================
function runAI(){

    let best3 = getBest3();
    let best2 = getBest2();

    document.getElementById("result").innerHTML =
    "👑 3 ตัวบน: " + best3.padStart(3,'0') + "<br><br>" +
    "🎯 2 ตัวล่าง: " + best2.padStart(2,'0') + "<br><br>" +
    "📊 Status: READY ✔";
}

</script>

</body>
</html>
