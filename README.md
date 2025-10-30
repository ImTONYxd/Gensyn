# 🚀 GENSYN NODE SETUP — One-Click Complete Guide

Follow these steps to install and run your Gensyn node seamlessly.  
At the end, you can **📋 copy all commands at once** to save time.

---

## 🧩 Step 1: Run Gensyn Setup Script
This script automatically installs system dependencies and prepares your environment.
```bash
curl https://raw.githubusercontent.com/imysryasir/Gsnyn-1-Click-Solutions/refs/heads/main/gensyn_setup.sh |
```

## 🧹 Step 2: Remove Any Old Installations
```bash
Clean up any previous versions of the rl-swarm folder to avoid conflicts.
```
sudo rm -rf ~/rl-swarm

## 🧠 Step 3: Clone the Gensyn RL-Swarm Repository

Get the latest version of the Gensyn node code directly from GitHub.
```bash
git clone https://github.com/gensyn-ai/rl-swarm
```
## 💻 Step 4: Start a Dedicated Screen Session

Create a detachable terminal session so your node keeps running even if you disconnect.
```bash
screen -S gensyn
```
## 📂 Step 5: Enter the RL-Swarm Directory

Move into the cloned project folder.
```bash
cd rl-swarm
```
## 🧰 Step 6: Create a Python Virtual Environment

This isolates your dependencies and keeps the system Python clean.
```bash
python3 -m venv .venv
```
## 🟢 Step 7: Activate the Virtual Environment

Activate your new environment so Python uses it for all installs and runs.
```bash
source .venv/bin/activate
```
## 📦 Step 8: Install Required Python Packages

Force reinstall the required libraries to ensure full compatibility.
```bash
pip install --force-reinstall transformers==4.51.3 trl==0.19.1
```
## 🧾 Step 9: Verify Installed Packages

Check that everything installed correctly.
```bash
pip freeze
```
## ⚙️ Step 10: Start the RL-Swarm Node

Launch the main node script.
```bash
./run_rl_swarm.sh
```
## 🌐 Step 11: Expose Node Dashboard (Optional)

Use Cloudflare Tunnel to make your local node dashboard accessible online securely.
```bash
cloudflared tunnel --url http://localhost:3000
```
