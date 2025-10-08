# Using-tools-like-John-the-Ripper-for-password-cracking
## AIM:
To crack password hashes using John the Ripper in Kali Linux.
## REQUIREMENTS:
- **Operating System:** Kali Linux / Ubuntu / Windows (with JtR binaries)
- **Tools:**
    - John the Ripper (Community/Pro version)
    - Hash generating tools (e.g., openssl, unshadow)
- **Test Data:**
    - /etc/shadow file (Linux hashed passwords)
    - Custom password-protected file (ZIP, RAR, etc.)
## ARCHITECTURE DIAGRAM:
```mermaid
flowchart TD
    A[Password Protected File / Hash] --> B[John the Ripper]
    B --> C[Select Attack Mode: Dictionary or Brute Force]
    C --> D[Load Wordlist / Charset Rules]
    D --> E[Password Cracking Process]
    E --> F[Recovered Passwords]
```
## DESIGN STEPS:
### Step 1: Install John the Ripper
```bash
sudo apt update
sudo apt install john -y
```

### Step 2: Prepare Hash File
- Extract hashes (Linux example):
```
unshadow /etc/passwd /etc/shadow > myhashes.txt
```
- For a ZIP file:
```
zip2john secret.zip > ziphash.txt
```
### Step 3: Run John the Ripper
- Dictionary Attack:
```
john --wordlist=/usr/share/wordlists/rockyou.txt myhashes.txt
```
- Brute Force (Incremental Mode):
```
john --incremental myhashes.txt
```
### Step 4: Show Cracked Passwords
```
john --show myhashes.txt
```
## PROGRAM:
1. **Hash Extraction** – Obtain password hashes from system files or encrypted archives.
2. **Attack Mode Selection** – Choose between dictionary, brute force, or hybrid.
3. **Cracking Phase** – John the Ripper runs through candidate passwords.
4. **Password Recovery** – Successfully cracked passwords are displayed.

## OUTPUT:
<img width="955" height="925" alt="VirtualBox_kali_08_10_2025_08_37_55" src="https://github.com/user-attachments/assets/26db1407-3759-4b08-b042-753df0b1bd81" />

<img width="955" height="925" alt="VirtualBox_kali_08_10_2025_08_39_15" src="https://github.com/user-attachments/assets/3838cc63-0750-479d-b831-9ee11950f129" />

<img width="955" height="925" alt="VirtualBox_kali_08_10_2025_08_41_04" src="https://github.com/user-attachments/assets/1f6c4ee5-dd03-45fb-8b47-890fb2bc42c9" />


<img width="955" height="925" alt="VirtualBox_kali_08_10_2025_08_41_44" src="https://github.com/user-attachments/assets/7df9524f-ccf8-4290-9615-cc1d4fa6c1d1" />

<img width="955" height="925" alt="VirtualBox_kali_08_10_2025_08_42_26" src="https://github.com/user-attachments/assets/98a98d95-1758-4cb3-901f-40bc984526cd" />

<img width="955" height="925" alt="VirtualBox_kali_08_10_2025_08_43_32" src="https://github.com/user-attachments/assets/9fceca7c-8728-4fb9-8ec7-bfd4930caf4e" />

<img width="955" height="925" alt="VirtualBox_kali_08_10_2025_08_48_45" src="https://github.com/user-attachments/assets/faade71c-22f5-4b62-a270-369c938c6306" />

<img width="955" height="925" alt="VirtualBox_kali_08_10_2025_08_51_10" src="https://github.com/user-attachments/assets/977c3733-347e-4568-a883-a8483179067a" />


Cracked Passwords from Hash File

## RESULT:
The password hashes were successfully cracked using John the Ripper.

