# Implementation of methods for protecting information during transmission over unsecured channels: IDS + Encryption

This project demonstrates a basic security system with Intrusion Detection System (IDS) and TLS-based encryption combined. It is divided into two .zip files. 

# Layer 1: AI-based Intrusion Detection System (IDS) Layer

Step 1: Unzip the AI Folder

      -unzip ai.zip
      -cd ai

Step 2: Install Requirements
Install necessary Python libraries:

    -pip install -r requirements.txt

Make sure you have scikit-learn, pandas, and numpy listed in requirements.txt.

Step 3: Load the Dataset
The IDS uses a pre-collected dataset stored locally in AI IDS layer.zip file. Make sure the dataset is extracted and accessible

Step 4: Run the IDS
Use Jupyter Notebook or other python environments to train and start monitoring

# Layer 2: Encryption Layer

Step 1: Unzip the Encryption Folder
unzip encryption.zip
cd encryption
Step 2: Install OpenSSL (if not already installed)

    -sudo apt update
    -sudo apt install openssl
Step 3: Generate Certificates
Option A – Manual Setup

Run each command one by one inside the encryption/ directory:

    -mkdir -p tls_config

### Generate CA key and certificate
    -openssl genrsa -out tls_config/ca.key 4096
    -openssl req -x509 -new -nodes \
    -key tls_config/ca.key \
    -sha256 -days 365 \
    -subj "/C=US/ST=State/L=City/O=Organization/CN=VPN-CA" \
    -out tls_config/ca.crt

### Server key and CSR
    -openssl genrsa -out tls_config/server.key 4096
    -openssl req -new \
    -key tls_config/server.key \
    -subj "/C=US/ST=State/L=City/O=Organization/CN=localhost" \
    -out tls_config/server.csr

### Sign server certificate
    -openssl x509 -req \
    -in tls_config/server.csr \
    -CA tls_config/ca.crt \
    -CAkey tls_config/ca.key \
    -CAcreateserial \
    -out tls_config/server.crt \
    -days 365 \
    -sha256

### Secure key files
    -chmod 600 tls_config/*.key
Option B – Use the Python Script

     -cd scripts
     -python3 generate_certs.py
This script will automatically generate all necessary certificates and place them in the tls_config/ folder.
