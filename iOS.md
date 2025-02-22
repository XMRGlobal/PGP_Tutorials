# **PGP Tools & Commands for iOS**  

## **1. Install a PGP App**  
Since iOS does not support native GPG in the terminal, you need a third-party app:

### **1.1 Recommended Apps:**  
- **iPGMail** – Paid app for managing PGP keys and encryption/decryption.  
- **PGPro** – Free, allows signing and encryption.  
- **OpenKeychain (via iSH Terminal)** – Works if using a Linux shell on iOS.  

## **2. Generate a PGP Key (Using iPGMail or PGPro)**  
Inside the app:  
1. Go to **Key Management**.  
2. Click **Create New Key**.  
3. Set a **name**, **key size** (4096-bit RSA recommended), and **passphrase**.  
4. Save the key and back it up.  

## **3. Import a PGP Key**  
Download or copy the **public key** to your iPhone.  

**Using iPGMail:**  
1. Go to **Key Management** → **Import Key**.  
2. Select the key file (`.asc`) and import it.  

## **4. Export a PGP Key**  
To export a public key:  
1. Go to **Key Management** in iPGMail.  
2. Select your key → Click **Export**.  
3. Send or save the exported `.asc` file.  

## **5. Encrypt a Message**  
To encrypt a message:  
1. Open **iPGMail** or **PGPro**.  
2. Go to **Encrypt** → Enter the message.  
3. Select the **recipient’s public key**.  
4. Encrypt and copy the output.  

## **6. Decrypt a Message**  
To decrypt a message:  
1. Paste the encrypted text in the **decrypt** section.  
2. Select your **private key**.  
3. Enter your **passphrase**.  
4. Decrypt and view the message.  

## **7. Sign a Message**  
To sign a message:  
1. Open **PGPro** or **iPGMail**.  
2. Go to **Sign Message** and enter your text.  
3. Use your **private key** to sign the message.  

## **8. Verify a Signed Message**  
To verify a signed message:  
1. Paste the signed message into the **Verify** section.  
2. Use the sender’s **public key** to check the signature.  

## **9. Encrypt & Decrypt Files**  
### **Encrypt a File:**  
1. Open **iPGMail**.  
2. Go to **Encrypt File**.  
3. Select the **recipient’s key**.  
4. Save or share the encrypted file.  

### **Decrypt a File:**  
1. Open the encrypted file in **iPGMail**.  
2. Select your **private key**.  
3. Enter your **passphrase**.  
4. View or export the decrypted file.  

## **10. Backup & Restore PGP Keys**  
### **Backup Keys:**  
1. Go to **Key Management** in iPGMail.  
2. Export and save your **public** and **private** keys.  
3. Transfer them securely to a backup device.  

### **Restore Keys:**  
1. Import your **.asc** key file back into **iPGMail**.  
