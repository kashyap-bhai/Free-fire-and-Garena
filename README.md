<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<title>Free Fire Sensitivity Calculator</title>
<style>
body {
  background:#0f0f0f;
  color:#fff;
  font-family: Arial, sans-serif;
  padding:20px;
}
.box {
  background:#1c1c1c;
  padding:20px;
  border-radius:10px;
  max-width:400px;
  margin:auto;
}
h1 { color:#ffcc00; text-align:center; }
input {
  width:100%;
  padding:10px;
  margin:10px 0;
  font-size:16px;
}
button {
  width:100%;
  padding:12px;
  background:#ffcc00;
  border:none;
  font-size:18px;
  cursor:pointer;
}
.result {
  margin-top:15px;
  background:#222;
  padding:10px;
  border-radius:8px;
}
small { opacity:0.6; }
</style>
</head>

<body>

<div class="box">
<h1>🎯 Sensitivity Calculator</h1>

<label>आपका Phone RAM (GB):</label>
<input type="number" id="ram" placeholder="जैसे 4">

<label>आपका Internet Ping (ms):</label>
<input type="number" id="ping" placeholder="जैसे 40">

<button onclick="calculate()">Calculate</button>

<div class="result" id="result"></div>

<small>*यह Garena से जुड़ा नहीं है। Fan-made tool.</small>
</div>

<script>
function calculate() {
  let ram = document.getElementById("ram").value;
  let ping = document.getElementById("ping").value;

  if(ram === "" || ping === "") {
    document.getElementById("result").innerHTML = "सही जानकारी डालो।";
    return;
  }

  let general = 90 - ping/5 + ram*2;
  let redDot = 85 - ping/6 + ram*2;
  let scope2x = 75 - ping/7 + ram;
  let scope4x = 65 - ping/8 + ram;
  let awm = 55 - ping/10 + ram;

  document.getElementById("result").innerHTML = `
  <b>Recommended Settings:</b><br>
  General: ${Math.round(general)}<br>
  Red Dot: ${Math.round(redDot)}<br>
  2x Scope: ${Math.round(scope2x)}<br>
  4x Scope: ${Math.round(scope4x)}<br>
  AWM Scope: ${Math.round(awm)}
  `;
}
</script>

</body>
</html>
