# 🧠 Train and Package Your Model Using Allora MDK

This guide walks you through setting up the [Allora Model Development Kit (MDK)](https://github.com/allora-network/allora-model-maker), training your custom model, and packaging it for use within the Allora Network.

---

## 🔧 Prerequisites

- Ubuntu 20.04 or later
- Python 3.11
- Go 1.22+
- Tiingo API Key (Get it [here](https://www.tiingo.com/account/api/token))

---

## ⚙️ System Setup


# Train and Package your Model using Allora MDK

```
sudo apt update
sudo apt upgrade -y
```

### Install Go

```
curl -OL https://go.dev/dl/go1.22.4.linux-amd64.tar.gz
```
```
tar -C /usr/local -xvf go1.22.4.linux-amd64.tar.gz
```
```
export PATH=$PATH:/usr/local/go/bin
```
```
go version
```

### setup model maker

```
git clone https://github.com/allora-network/allora-model-maker.git
cd allora-model-maker
```
Create account at https://www.tiingo.com/account/api/token and paste the key to .env file
```
nano .env
```
```
TIINGO_API_KEY=your_api_key_here
```

### Setting up Conda and install dependencies

```
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
```
```
export PATH="/root/miniconda3/bin:$PATH"
```
```
conda create --name modelmaker python=3.11
```
```
source activate base
conda activate modelmaker
```
python version should be 3.11.
```
python --version
```
```
pip install setuptools==72.1.0 Cython==3.0.11 numpy==1.24.3 pystan
```
```
nano requirements.txt
```
remove entry for pystan==2.19.1.1. Save file ctrl+x then y
```
pip install -r requirements.txt
```

# Train model

model.py placed inside model directory for each type of models. modify your model.py as per requirement on which your model will be trained


```
make train
```


```
make eval
```
select: 1
If your result is not good you can train a different model
```
make package-<model-name>
```
