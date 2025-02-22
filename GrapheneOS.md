# **PGP Tools & Commands for GrapheneOS**  

## **1. Install PGP on GrapheneOS**  
GrapheneOS does not include GPG by default, so you need to install a PGP app:

### **1.1 Recommended Apps:**  
- **Termux** (For command-line PGP operations)  
- **OpenKeychain** (Graphical PGP management)  
- **PGPainless** (For XMPP-based encrypted messages)  

### **1.2 Install GnuPG in Termux**  
If you prefer the command-line, install GnuPG via Termux:  
```sh
pkg update && pkg upgrade
pkg install gnupg
```

## **2. Generate a PGP Key (Termux)**  
```sh
gpg --full-generate-key
```
**Follow the prompts:**  
- Select **RSA** (default).  
- Choose a **key size** (4096 recommended).  
- Set an **expiration date** or choose "no expiration".  
- Enter your **name**.  
- Choose a **strong passphrase**.  

## **3. Generate a PGP Key (OpenKeychain)**  
If using **OpenKeychain**:  
1. Open **OpenKeychain** and go to **Manage Keys**.  
2. Click **+ Create Key**.  
3. Enter your **name** and **email**.  
4. Set **key strength** (4096-bit RSA recommended).  
5. Save and back up your keys.  

## **4. List Existing Keys**  

### **Using Termux:**  
```sh
gpg --list-keys
```

### **Using OpenKeychain:**  
- Go to **Manage Keys** to see all stored keys.  

## **5. Export PGP Keys**  

### **Export Public Key (Termux):**  
```sh
gpg --armor --export "Your Name" > public_key.asc
```

### **Export Private Key (Backup Only!):**  
```sh
gpg --armor --export-secret-keys "Your Name" > private_key.asc
```

### **Export Public Key (OpenKeychain):**  
1. Go to **Manage Keys** → Select Key → Click **Share**.  
2. Export the **.asc file** and transfer securely.  

## **6. Import a PGP Key**  

### **Using Termux:**  
```sh
gpg --import public_key.asc
```

### **Using OpenKeychain:**  
1. Go to **Manage Keys** → Click **Import Key**.  
2. Select the key file and import it.  

## **7. Encrypt a Message**  

### **Using Termux:**  
```sh
echo "Your secret message" | gpg --armor --encrypt --recipient "Recipient Name"
```

### **Using OpenKeychain:**  
1. Go to **Encrypt Message**.  
2. Select **recipient’s public key**.  
3. Type your message and encrypt.  

## **8. Decrypt a Message**  

### **Using Termux:**  
```sh
gpg --decrypt file.txt.asc
```

### **Using OpenKeychain:**  
1. Open **OpenKeychain** and go to **Decrypt Message**.  
2. Select the encrypted text or file.  
3. Enter your **private key passphrase**.  

## **9. Sign & Verify Messages**  

### **Sign a Message (Termux):**  
```sh
echo "Verified message" | gpg --clearsign
```

### **Verify a Signed Message:**  
```sh
gpg --verify file.txt.asc
```

## **10. Encrypt & Decrypt Files**  

### **Encrypt Large Files (AES-256 in Termux):**  
```sh
gpg --symmetric --cipher-algo AES256 file.tar.gz
```

### **Decrypt Large Files:**  
```sh
gpg --output file.tar.gz --decrypt file.tar.gz.gpg
```

## **11. Backup & Restore PGP Keys**  

### **Export Keys for Backup:**  
```sh
gpg --export --armor > all-public-keys.asc
gpg --export-secret-keys --armor > all-private-keys.asc
```

### **Import Keys from Backup:**  
```sh
gpg --import all-public-keys.asc
gpg --import all-private-keys.asc
```

## **12. Secure Messaging with PGP on GrapheneOS**  
For encrypted messaging with PGP:  
- **Use Conversations + OpenKeychain** for XMPP with PGP encryption.  
- **Use FairEmail** for PGP-secured emails.  
- **Use Delta Chat** for encrypted email-based chat.  
