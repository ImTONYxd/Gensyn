# 🛑 GENSYN NODE SETUP — FULL ONE-LINE GUIDE 🛑
# Follow this sequence to deploy your Gensyn Node quickly.

# ⚡️ STEP 1 — Install / Deploy Gensyn
curl https://raw.githubusercontent.com/imysryasir/Gsnyn-1-Click-Solutions/refs/heads/main/gensyn_setup.sh | bash

# ⚡️ STEP 2 — Delete Old Gensyn (if exists)
sudo rm -rf ~/rl-swarm

# ⚡️ STEP 3 — Install New Gensyn Repo
git clone https://github.com/gensyn-ai/rl-swarm

# ⚡️ STEP 4 — (Optional) Transfer your old swarm file
# Copy it manually if you have one from a previous install.

# ⚡️ STEP 5 — Create a new screen session
screen -S gensyn

# ⚡️ STEP 6 — Start Gensyn Node
cd rl-swarm
python3 -m venv .venv
source .venv/bin/activate
pip install --force-reinstall transformers==4.51.3 trl==0.19.1
pip freeze
./run_rl_swarm.sh

# ⚡️ STEP 7 — Login using localhost tunnel
cloudflared tunnel --url http://localhost:3000

# ⚡️ STEP 8 — When asked:
# Hugging Face: N  (choose No)

# ⚡️ FINAL STEP — When asked:
# "Name of the model you want to use in hugging face repo/format"
# Just press ENTER to skip.

# ✅ DONE! Your node is running and syncing 🚀
# You can detach from screen with:
# Ctrl + A + D
# And reattach with:
# screen -r gensyn

# 🧩 Useful Commands
# Check logs:
tail -f ~/rl-swarm/logs/latest.log

# Stop node:
pkill -f run_rl_swarm.sh
