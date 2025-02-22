# **PGP Tools & Commands for Tails, Whonix, and Qubes OS**  

## **1. Tails OS**  
### **1.1 Verify GnuPG Installation**  
GnuPG is **pre-installed** in Tails OS. You can verify it with:  
```sh
gpg --version
```

### **1.2 Open the PGP Keyring**  
1. Click **Applications** → **Accessories** → **Passwords and Keys**.  
2. Use this tool to **manage keys** and **encrypt/decrypt messages**.  

### **1.3 Encrypt & Decrypt Messages**  
```sh
# Encrypt a file
gpg --armor --encrypt --recipient "Recipient Name" file.txt

# Decrypt a file
gpg --decrypt file.txt.asc
```

---

## **2. Whonix OS**  
### **2.1 Verify GnuPG Installation**  
GnuPG is **pre-installed** in Whonix. You can verify it with:  
```sh
gpg --version
```

### **2.2 Encrypt & Decrypt Messages**  
```sh
# Encrypt a file
gpg --armor --encrypt --recipient "Recipient Name" file.txt

# Decrypt a file
gpg --decrypt file.txt.asc
```

### **2.3 Using PGP in Qubes-Whonix**  
In **Qubes OS with Whonix**, you can use **split GPG** for security:  
```sh
qvm-run --pass-io vault "echo 'Your Message' | gpg --armor --encrypt --recipient 'Recipient Name'"
```

---

## **3. Qubes OS**  
### **3.1 Verify GnuPG Installation**  
GnuPG is pre-installed in Qubes. Verify it with:  
```sh
gpg --version
```

### **3.2 Split GPG for Maximum Security**  
In Qubes OS, you can separate GPG operations from the main system using the **vault qube**.

### **3.3 Encrypt & Decrypt in a Secure Qube**  
Run these commands inside your **vault qube**:  
```sh
# Encrypt a file
echo "Your secret message" | gpg --armor --encrypt --recipient "Recipient Name"

# Decrypt a file
gpg --decrypt file.txt.asc
```

### **3.4 Sign & Verify Messages**  
```sh
# Sign a message
echo "Verified message" | gpg --clearsign

# Verify a signed file
gpg --verify file.txt.asc
```

---

## **4. Backup & Restore PGP Keys (All OS)**  
### **4.1 Export Keys**  
```sh
# Export Public Key
gpg --export --armor > public_key.asc

# Export Private Key
gpg --export-secret-keys --armor > private_key.asc
```

### **4.2 Import Keys**  
```sh
gpg --import public_key.asc
gpg --import private_key.asc
```
