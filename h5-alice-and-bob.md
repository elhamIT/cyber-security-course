# h5 Alice and bob

This assignment is about the usage of public key encryption in every day.

## [Schneier 2015: Applied Cryptography](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/)

### [Chapter 1 – Foundations, Section 1.1 Terminology: Sender/Receiver, Messages & Encryption, Algorithms & Keys, Symmetric, Public-Key](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/08_chap01.html#chap01-sec001)

* Defines the basic model: Sender sends a message to Receiver, with the goal of confidentiality and/or integrity.
* Distinguishes plaintext (cleartext) vs ciphertext (encrypted form), and defines encryption and decryption operations.
* Introduces algorithm (the publicly known method) vs key (the secret value that controls encryption/decryption). It emphasizes that security must rest on key secrecy.
* Describes symmetric algorithms: same key for encryption and decryption. It is efficient but requires secure key distribution.
* Describes public-key (asymmetric) algorithms: pair of keys (public for encrypting, private for decrypting), which solves key-distribution problem and enables things like secure communication, digital signatures.

### [Chapter 2 – Protocol Building Blocks, Section 2.5 Communications Using Public-Key Cryptography](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec005)

* Focuses on how public-key cryptography is used in communication protocols: sender uses receiver’s public key to encrypt a message, receiver uses private key to decrypt.
* Explains that because public-key encryption is computationally heavy, in practice it is often used to securely exchange a symmetric key, then that symmetric key is used for bulk communication.
* Highlights the role of authenticity / trust: public-key schemes require correct mapping of keys to identities (i.e., key verification, certificates).
* Points out limitations and considerations: possible attackers (eavesdropper Eve, active attacker Mallory), need to consider what happens when keys are compromised or mis-used, and how protocols must handle these threats.

## [Karvinen 2023: PGP – Send Encrypted and Signed Message](https://terokarvinen.com/2023/pgp-encrypt-sign-verify/)
* PGP uses public-key cryptography for secure email/files
* Encrypt with receiver’s public key
* Decrypt with receiver’s private key
* Sign with sender’s private key
* Verify with sender’s public key
* gpg implements PGP on Linux using command-line tools (gpg `--encrypt`, `--sign`, `--verify`, etc.)

## Pubkey Today
How I use Public-Key Crypto commonly outside the homework, is for SSH Login. When I SSH into GitHub/servers, my laptop uses a private key and the server has my public key an authentication happens without passwords.
Another common example is Messaging Apps like Whatsapp, in which each device has a keypair and messages are encrypted using recipients’ public keys and only their private key decrypts.

## Encrypt a Message (PGP/GPG)
How the keys are used at each stage of encryption:

Let’s assume I (Sender) want to send an encrypted message to Alice (Receiver).

First, encryption (Sender side) command: `gpg --encrypt --recipient Alice message.txt`. Here, Alice’s public key is used by me (the sender) and it encrypts the message so only Alice’s private key can decrypt it.
Public key is meant to be shared. Anyone can encrypt, however only the private key owner can decrypt.

Second, Decryption (Receiver side) command: `gpg --decrypt message.txt.gpg`. Alice’s private key (secret) is used to decrypt. GPG automatically asks for Alice’s private key passphrase.
Only the private key can reverse the encryption.

### Security Evaluation of GPG (PGP)

* Uses hybrid encryption:
  - A random AES symmetric session key encrypts the message.
  - The session key is encrypted with the receiver’s RSA public key.
* Strong cryptographic defaults (`AES`, `RSA`, `SHA-256`, etc.)
* Trust model includes fingerprint verification.
* Attack resistance:
  - Eavesdroppers cannot read (confidentiality).
  - Attackers cannot forge signatures (integrity/authenticity).

* Weak points (if misused):
  - Weak passphrase on private key.
  - Not verifying fingerprints → risk of man-in-the-middle.
  - Poor key storage (e.g., unencrypted private key).

But overall, GPG is considered highly secure for encrypted communication.

## Eve and Mallory: How PGP defends against them

### EVE = Passive attacker (eavesdropping)

Here problem is: Eve only listens but does not modify traffic. The protection is using the **Encryption**:

* Sender encrypts with receiver’s public key: `gpg --encrypt --recipient Alice message.txt`
* Only the receiver’s private key can decrypt.
  
Therefore, Eve learns nothing, even if she copies the ciphertext.

### MALLORY = Active attacker (modifies messages)

Here, the problemis: Mallory changes messages or injects fake ones.The protection is using the **Digital signatures**.

* Sender signs with sender’s private key: `gpg --sign message.txt` or combines it with encryption: `gpg --encrypt --sign --recipient Alice message.txt`
* Receiver verifies: `gpg --verify message.txt.gpg`

This is how this stops Mallory:
* Signature proves message **integrity**:
  - any modification breaks it.
* Signature proves **authenticity**:
  - only sender’s private key can create a valid signature.
* Receiver checks using sender’s public key

Therefore, Mallory cannot forge, alter, or replace the message without detection.

**Flags related to protection in Eve and Mallory**: 
* Eve uses `--encrypt` for **Confidentiality**, which the mechanism is Receiver’s public key.
* Mallory uses `--sign` for **Integrity**, which the mechanism is Sender’s private key.
* Mallory uses `--verify` for **Authenticity**, which the mechanism is Sender’s public key.
* `--encrypt --sign` can be used for combined protection and the mechanism is both encryption and sign.

## Password Management
For this subtask, I used **KeePassXC** to create Vault and set a master password to that and add entries for example for my github account. However when I tried to take screenshot for this, it does not let to take screenshot.
Here is the explanation why the password managers are needed.
These are the attacks that succeed when people don’t use password managers:
* Credential stuffing
  - Attackers reuse leaked passwords across multiple sites.
  - Users who reuse passwords are easily compromised.
* Brute force attacks
  - Humans choose weak passwords, so to say easy to guess.
  - Managers generate strong random ones (e.g., 32 characters).
* Phishing attacks
  - Manager won’t autofill on a fake site.
  - Prevents entering credentials on the wrong domain.
* Keylogging exposure
  - Only one master password typed.
  - Other passwords are never typed manually.
* Password reuse after data breaches
  - When one site is hacked, reused passwords cause chain compromises.

Therefore, password management creates long random passwords, avoids password reuse, auto-fills only on correct domains, secure local encrypted storage, and protects against many human-error based attacks.

## References
* https://terokarvinen.com/cyber-security/
* https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/
* https://terokarvinen.com/2023/pgp-encrypt-sign-verify/
* https://keepassxc.org/
