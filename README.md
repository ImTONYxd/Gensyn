<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🛑 Gensyn Node Setup</title>
<style>
body { font-family: monospace; background: #0d1117; color: #c9d1d9; padding: 2rem; }
pre { background: #161b22; padding: 1rem; border-radius: 10px; position: relative; }
button.copy-btn {
  position: absolute; top: 8px; right: 8px; background: #238636; border: none;
  color: white; padding: 4px 8px; border-radius: 6px; cursor: pointer;
}
button.copy-btn:hover { background: #2ea043; }
h1,h2 { color: #58a6ff; }
</style>
</head>
<body>

<h1>🛑 GENSYN NODE SETUP — One Click Install 🛑</h1>

<p>Click “Copy” to copy all setup commands at once 👇</p>

<pre><code id="setup">
curl https://raw.githubusercontent.com/imysryasir/Gsnyn-1-Click-Solutions/refs/heads/main/gensyn_setup.sh | bash
sudo rm -rf ~/rl-swarm
git clone https://github.com/gensyn-ai/rl-swarm
screen -S gensyn
cd rl-swarm
python3 -m venv .venv
source .venv/bin/activate
pip install --force-reinstall transformers==4.51.3 trl==0.19.1
pip freeze
./run_rl_swarm.sh
cloudflared tunnel --url http://localhost:3000
</code><button class="copy-btn" onclick="copyText()">📋 Copy</button></pre>

<script>
function copyText() {
  const text = document.getElementById("setup").innerText;
  navigator.clipboard.writeText(text);
  alert("✅ Commands copied to clipboard!");
}
</script>

</body>
</html>

