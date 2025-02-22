# **PGP Tools & Commands for Linux**  

## **1. Install GnuPG**  
GPG is included in most Linux distributions. If missing, install it with:  

```sh
# Debian/Ubuntu
sudo apt install gnupg

# Arch Linux
sudo pacman -S gnupg

# Fedora
sudo dnf install gnupg

# OpenSUSE
sudo zypper install gpg2

# Gentoo
sudo emerge --ask app-crypt/gnupg
```

## **2. Generate a PGP Key**  
```sh
gpg --full-generate-key
```
**Follow the prompts:**  
- Select **RSA** (default).  
- Choose a **key size** (4096 recommended).  
- Set an **expiration date** or choose "no expiration."  
- Enter your **name**.  
- Choose a **strong passphrase**.  

## **3. List Existing Keys**  
```sh
# List public keys
gpg --list-keys

# List private (secret) keys
gpg --list-secret-keys
```

## **4. Find Your Key Fingerprint**  
```sh
gpg --fingerprint "Your Name"
```

## **5. Export & Import PGP Keys**  

### **Export a Public Key**  
```sh
gpg --armor --export "Your Name" > public_key.asc
```

### **Export a Private Key (Backup Only!)**  
```sh
gpg --armor --export-secret-keys "Your Name" > private_key.asc
```

### **Import a PGP Key**  
```sh
gpg --import public_key.asc
```

## **6. Encrypt & Decrypt Messages**  

### **Encrypt a Message (Command-Line Input, Ctrl+D to End)**  
```sh
gpg --armor --encrypt --recipient "Recipient Name"
```
_Type your message and press **Ctrl+D** to finish._  

### **Encrypt a File**  
```sh
gpg --armor --encrypt --recipient "Recipient Name" file.txt
```

### **Decrypt a Message (Paste Text, Ctrl+D to Process)**  
```sh
gpg --decrypt
```
_Paste the encrypted text, then press **Ctrl+D**._  

### **Decrypt a File**  
```sh
gpg --decrypt file.txt.asc
```

## **7. Sign & Verify Messages**  

### **Sign a Message (Ctrl+D to End Input)**  
```sh
gpg --clearsign
```
_Type your message and press **Ctrl+D**._  

### **Sign a File**  
```sh
gpg --clearsign file.txt
```

### **Verify a Signed File**  
```sh
gpg --verify file.txt.asc
```

## **8. Encrypt & Decrypt Large Files**  

### **Encrypt Large Files (AES-256 Encryption, No Recipient)**  
```sh
gpg --symmetric --cipher-algo AES256 file.tar.gz
```

### **Decrypt Large Files**  
```sh
gpg --output file.tar.gz --decrypt file.tar.gz.gpg
```

## **9. Revoking a Key**  

### **Generate a Revocation Certificate (For Key Compromise Cases)**  
```sh
gpg --output revoke.asc --gen-revoke "Your Name"
```

### **Import the Revocation Certificate**  
```sh
gpg --import revoke.asc
```

## **10. Remove or Delete Keys**  

### **Delete a Public Key**  
```sh
gpg --delete-key "Your Name"
```

### **Delete a Private Key**  
```sh
gpg --delete-secret-key "Your Name"
```

## **11. Backup & Restore PGP Keys**  

### **Export All Keys (For Backup)**  
```sh
gpg --export --armor > all-public-keys.asc
gpg --export-secret-keys --armor > all-private-keys.asc
```

### **Restore PGP Keys from Backup**  
```sh
gpg --import all-public-keys.asc
gpg --import all-private-keys.asc
```

---
