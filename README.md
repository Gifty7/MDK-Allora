# 📦 Train and Package Your Model Using Allora MDK

This repository helps you set up, train, and package your machine learning model using the **Allora Model Development Kit (MDK)**. Includes setup for Go, Conda, and integration with Tiingo API for financial data.

---

## 🔧 Prerequisites

- Ubuntu 20.04 or later
- Python 3.11
- Go 1.22+
- Tiingo API Key

---

## 🚀 Quick Start

```bash
git clone https://github.com/Gifty7/MDK-Allora.git
cd MDK-Allora
⚙️ System Update
bash
Copy
Edit
sudo apt update
sudo apt upgrade -y
🛠️ Install Go
bash
Copy
Edit
curl -OL https://go.dev/dl/go1.22.4.linux-amd64.tar.gz
tar -C /usr/local -xvf go1.22.4.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin
go version
🧰 Setup Allora Model Maker
bash
Copy
Edit
git clone https://github.com/allora-network/allora-model-maker.git
cd allora-model-maker
🔐 Add Tiingo API Key
Create an account at Tiingo

Copy your API key

Create a .env file:

bash
Copy
Edit
nano .env
Paste this:

env
Copy
Edit
TIINGO_API_KEY=your_api_key_here
Save and close (Ctrl + X, then Y, then Enter)

🧬 Setup Conda & Install Dependencies
bash
Copy
Edit
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
export PATH="/root/miniconda3/bin:$PATH"
Create and activate the environment:

bash
Copy
Edit
conda create --name modelmaker python=3.11 -y
source activate base
conda activate modelmaker
Check Python version:

bash
Copy
Edit
python --version
🧪 Install Python Packages
bash
Copy
Edit
pip install setuptools==72.1.0 Cython==3.0.11 numpy==1.24.3 pystan
nano requirements.txt
Remove this line:

text
Copy
Edit
pystan==2.19.1.1
Then:

bash
Copy
Edit
pip install -r requirements.txt
🧠 Train Your Model
Place your model.py inside the model/ directory.

Modify it according to your dataset and training logic.

Run training:

bash
Copy
Edit
make train
Evaluate your model:

bash
Copy
Edit
make eval
When prompted, choose:

Copy
Edit
1
If results are not good, adjust the model and retrain.

📦 Package Your Model
bash
Copy
Edit
make package-<model-name>
Replace <model-name> with your folder name, e.g., make package-btc-predictor

✅ You're Done!
Your model is now trained and packaged, ready to plug into the Allora Network's decentralized intelligence layer.
