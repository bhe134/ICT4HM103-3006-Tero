# 2.3 ONE-WAY FUNCTIONS
  * One-way function is the basis of the building blocks of the cryptography protocols and thus is central to public cryptography.
  * The one-way function is easy to compute but extremely difficult to reverse compute. This is to say give value x, its easy to compute function f(x). However, given function f(x), it is extremely difficult to reverse calculate value x.
  * A good example of the one-way function is breaking a plate into multiple tiny pieces, it is difficult or impossible to put back those pieces back together to have the original plate.
  * One-way functions cannot be used for encryption because a message encrypted with the one-way hash function is impossible to decrypt. A good example would be to write an important message on a plate, then break that plate into numerous tiny pieces, and request someone to rebuild the plate and read the message. Its just impossible.
  * A trapdoor one-way function is a special one-way function with a secret trapdoor. This is to say, given x, we can calculate function f(x). Having a secret key y, we can take the function f(x) and secret key y and compute the value x. An example is taking apart the watch into its numerous miniscule pieces, its extremely difficult to put back the watch, however, with the watch’s assembly instruction that is the secret, the assembly is easier.

# 2.4 ONE-WAY HASH FUNCTIONS
  * Numerous names for the one-way hash functions: compression function, contraction function, message digest, fingerprint, cryptographic checksum, message integrity check (MIC), manipulation detection code (MDC).
  * One-way hash functions are central to modern cryptography and a major building block for multiple protocols.
  * A one-way hash function is a mathematical function or otherwise and takes a variable string of input called the pre-image and converts it to a fixed length output called a hash value. 
  * The goal is to fingerprint the pre-image and to produce a value such that it would be possible to ascertain whether a candidate pre-image is the same as the real pre-image.
  * Thus, a one-way hash function works in a single direction that is it is easy to compute the has value from the pre-image but extremely difficult to compute the pre-image from the hash value.
  * A good one-way hash value is also collision free. This means that its difficult to calculate two pre-image strings from the same hash value.
  * The has function is public and is not a secret, its security is centred on its onewayness.
  * Given a hash value, it is computationally impossible to find a pre-image that hashes to the specific hash value. 
  * An example of this is when a person claims to have a similar file as you have, and you don’t want to request them to send the file. So instead, you request hash value of the file. If the sent hash value is correct, then its almost certain they have the same file.
  * This is useful in financial transactions, for example, a withdrawal of $100 should not turn as a withdrawal of $1000 in another part of the network. Then the use of a one-way hash function without a key is applicable. If the intention is for the recipient to verify the hash, then a key is used.
  * The message authentication code (MAC) or data authentication code (DAC) is a one-way hash function with an addition of a secret key. Thus, the hash value is a result of the function of the pre-image and the key. This is similar to the hash function except that someone with the key can verify the hash value.
  * Generally systems do not store passwords in plaintext but in the form of hash. An example of a hash can be e24589b322ffd5324ed90a6ac4e1108d.
  * The hash is a single way function and cannot be changed into the password.
  * Hashcat is a linux tool that can be used to identify the hash and crack the hash. hashcat has been installed and tested in task c). 
  ## Reference
  Bruce Schneier. March 2015. Applied Cryptography: Protocols, Algorithms and Source Code in C, 20th Anniversary Edition. Wiley. E-book. Accessed: 9 November 2024.
  
  https://terokarvinen.com/2022/cracking-passwords-with-hashcat/

## a). Billion dollar busywork
Print a hash from string hello: 

![image](https://github.com/user-attachments/assets/a1b52a22-7cf3-43cc-9944-e4556798d164)

Add some string to the hello string and run the above command again:

![image](https://github.com/user-attachments/assets/7efba1b9-7457-4c48-bdaa-69924bcc6751)

Adding zeros to the hash:
Adding a single leading zero was achieved through multiple/numerous trial and error attempts.Evidently, my assumption is that the difficulty raises exponentially for possible the character strings that will lead or results in an increase in the prceeding zeros on the hash value.

![image](https://github.com/user-attachments/assets/6c810611-525b-42e8-9439-e68e49ea3bf6)

## b). Compare Hash
An empty file named compare-hash.txt was created and the hash of the file computed. Next, another empty file named compare-hash2.txt was created. The has was computed. Next, the compare-hash.txt file was moved to compare-hash2.txt file and the hash computed for the file compare-hash2.txt. In all cases, the following can be observed:

  1-	The hash value computed from all the files are the same.

  2-	The hash value is of fixed length i.e. 64 hexadecimal characters.

![image](https://github.com/user-attachments/assets/13fe8877-927f-405b-abee-0e9227470910)

## c). Hashcat
The following screenshot show the installation of hashcat. A tool to identify the hash type and to crack the hash.

![image](https://github.com/user-attachments/assets/b9801238-d4ce-46b3-a224-f1a1690931be)

![image](https://github.com/user-attachments/assets/724f13b7-9682-4598-a580-28af54cf5b5f)

Creation of a working directory:

![image](https://github.com/user-attachments/assets/8bd0442c-f278-4047-87e4-51dae3e3163f)

Next, the download of a big dictionary. This consists of one word after another. The Rockyou dictionary is downloaded as is probably the most common.

![image](https://github.com/user-attachments/assets/1e10caf2-d813-45b7-b4e0-0d5fa9b4d84f)

![image](https://github.com/user-attachments/assets/aade70c4-04a5-4926-99a7-870242f30dbe)

### Reference
https://terokarvinen.com/2022/cracking-passwords-with-hashcat/


## d). Dictionary Attack
Attempts to crack the hash:  21232f297a57a5a743894a0e4a801fc3 with hashcat.
Identity Hash Type:

![image](https://github.com/user-attachments/assets/17d7b235-7c63-4bc4-9509-523945b9cea1)

Crack the Hash with MD5

![image](https://github.com/user-attachments/assets/6552c50d-b84c-4f16-b9bd-79dac0ddcd7d)

![image](https://github.com/user-attachments/assets/28d433a9-d633-4409-a9a7-65f074388334)

Increase of virtual machine base memory to 3MB and running hashcat crack again.

![image](https://github.com/user-attachments/assets/d348c3ba-ce66-4dde-88fd-e3117886f6df)

![image](https://github.com/user-attachments/assets/058ef72b-1479-406d-a0b6-57c0f1b30883)

![image](https://github.com/user-attachments/assets/f1ed43c6-065b-4f26-8028-4ddf3cb46b92)
### Reference
https://terokarvinen.com/2022/cracking-passwords-with-hashcat/

## e) How can you make a password that's protected against a dictionary attack?
Weak passwords are susceptible to dictionary attacks. As I have discovered with the hashcat tool and disctionary, the dictionary attach relies on this automated software to guess the passwords until the corrected one is discovered.

These methods are used to protect against dictionary attacks:
* The use of strong and complex passwords. For example, 12 characters long, a mixture of upper case, lower case, numbers and special characters.
* The use of password managers. For example, in class 2 we worked with pass as one of the options for password management.
* The use of multi factor authentication. For example, login to an email or account also requires an extra step of a login code sent to the mobile device as text or even a second software generated code from the mobile devices as an extra login code.
* Regular change of password. This cannot be emphasised enough. Strong password policies that includes expiration of passwords and ultimately change.
* Monitoring of suspicious login attempts. For example, some email features notify the machine and location of login that was attempted.
* Slow down the repeat of login attampts. For example, lock accounts for several minutes incase of login failures. This slows the attackers speed of dictionary attack attempts.
* Use of CAPTCHA. This is an extra step to verify if indeed the login attempt is from a human or some automated source.

## Reference: 
https://www.sapphire.net/blogs-press-releases/dictionary-attacks/

## f) Voluntary: Two minute job.

Identifying Hash Type and then Crack the Hash

Hash Type: Unknown Hash.
This is not a hash value. It appears to be just a string of typed out characters.

![image](https://github.com/user-attachments/assets/dcc86234-568f-4be1-9f2b-9491c5fb9244)

![image](https://github.com/user-attachments/assets/594f1f03-1f66-401a-9411-b807b7114144)

### Reference
https://terokarvinen.com/2022/cracking-passwords-with-hashcat/

## g) Voluntary bonus: Crack this Windows NTLM hash: f2477a144dff4f216ab81f2ac3e3207d
It was not possible to crack this hash. The compute resources of my virtual machine were insufficient or not enough and the displayed cracking status was “Exhausted”.

![image](https://github.com/user-attachments/assets/62264f4a-6bd5-4015-ae77-8247688f5d71)

![image](https://github.com/user-attachments/assets/a1140170-8ab6-48b1-b91a-93a4f6068c56)

![image](https://github.com/user-attachments/assets/8d637e88-6069-4fa4-88f4-b54440c0e668)

![image](https://github.com/user-attachments/assets/630ee087-e725-4351-a9c9-38f379650f0f)

### Reference
https://terokarvinen.com/2022/cracking-passwords-with-hashcat/

## h) Voluntary bonus: Make hashcat work with your display adapter (GPU). Compare hash rate with and without GPU enabled.

I am running this on a virtual machine. In a bid to use the hosts GPU card I performed a search on the internet and apparently I did not find a method for the guest to directly utilise the hosts GPU card. 
I enabled the settings "Enable 3D acceleration" and run the crack on the Windows NTLM hash with similar results.

![image](https://github.com/user-attachments/assets/d4c60f0c-14da-4c31-8c88-87e07efc8e7f)

![image](https://github.com/user-attachments/assets/8745a8db-b985-4bd1-8c81-61d0fb1345c7)

![image](https://github.com/user-attachments/assets/dd4c510c-44a8-4b8e-9fe9-a3e2db0ffd8f)

![image](https://github.com/user-attachments/assets/cf59509b-850a-46e2-a803-dcc168fd4b4b)

![image](https://github.com/user-attachments/assets/1852b51a-7cc2-43c5-9d28-1c5678525da2)

### Reference
https://terokarvinen.com/2022/cracking-passwords-with-hashcat/

## i)	Voluntary bonus: My hash. create some hashes of your own, then crack them with hashcat.
Create hash for string $2y$18$axMtQ4N8j:

![image](https://github.com/user-attachments/assets/066fd4d6-87a9-4fa4-80fc-234d5cc80e6b)

Check Hash Type:

![image](https://github.com/user-attachments/assets/b5334205-c20e-40e9-95b3-154b3929b128)

Crack Hash:

![image](https://github.com/user-attachments/assets/179cacf7-9cda-4484-9e47-5668301f6499)

![image](https://github.com/user-attachments/assets/f36c575a-dff0-4a97-aa66-c3ac148132af)

Results: Status “Exhausted” that is not possible to crack the hash value with the computational resources available on the virtual machine.

### Reference
https://terokarvinen.com/2022/cracking-passwords-with-hashcat/

## j)  Install Jumbo John. Compile it from source code as needed

Install the tools and the libraries required for John.
NOTE: The package zlib-gst was not found. 

![image](https://github.com/user-attachments/assets/4efd65e6-2e00-4c04-a919-2c69e20c616a)

![image](https://github.com/user-attachments/assets/44ca2773-426f-4027-b8a8-9e0d062d6df2)

![image](https://github.com/user-attachments/assets/c6965596-3a41-439e-ac00-345662e9ca7a)

Download & Compile John the Ripper, Jumbo version

![image](https://github.com/user-attachments/assets/40412dbf-099f-4c66-802c-4177a8732f6d)

![image](https://github.com/user-attachments/assets/fa2c3701-2677-4e44-a9d7-00560db9ee69)

![image](https://github.com/user-attachments/assets/8b338c87-e87a-4836-8f47-712fd3606b0a)

![image](https://github.com/user-attachments/assets/5dd721e8-34fe-4288-846e-dfc1c8aa7431)

![image](https://github.com/user-attachments/assets/44126687-99a4-49ef-bb62-00b873ab1590)

New executables and scripts in run/.

![image](https://github.com/user-attachments/assets/66b5764a-f1ff-4b9b-883b-b882ec3bbdb4)

![image](https://github.com/user-attachments/assets/2925beb5-271b-4a37-8d72-ed40e8797efc)

![image](https://github.com/user-attachments/assets/e780bfe2-a757-4e90-8bef-f3ab753334e4)
## Reference: 
https://terokarvinen.com/2023/crack-file-password-with-john/

## k) Crack file password with John
The following crack attempt is on a password protected .zip file.

Download a password protected .zip file.

![image](https://github.com/user-attachments/assets/f9b3f2fb-bf0e-44a0-9558-28e6ca2c4b11)

Attempt to open the password protected .zip file with incorrect password.

![image](https://github.com/user-attachments/assets/4d2aeffb-1938-4d47-a164-9fd51164b2b8)

* Crack the password: Step 1, extract the hash into a new file

![image](https://github.com/user-attachments/assets/319f0fe4-e5cd-4b71-9330-b53fecb91224)
![image](https://github.com/user-attachments/assets/30c6dc5a-5d2d-471a-bb61-90783a8f696b)

* Crack the password: Step 2, perform a dictionary attack against the hash

![image](https://github.com/user-attachments/assets/e2ce286c-dc98-43a4-bf95-fff548de7c8d)
![image](https://github.com/user-attachments/assets/b0172eae-4720-4852-bca1-70845c331383)

## l) Voluntary bonus: Custom dictionary. What's Elmeri's password?
![image](https://github.com/user-attachments/assets/46fd2286-2df6-4104-8630-e348fc7ebec8)

![image](https://github.com/user-attachments/assets/38b25cac-0199-4730-be03-f877e3b2d0b9)

Updated the contents of shadow file with the hash password.
![image](https://github.com/user-attachments/assets/06ec86e8-37d7-442c-9d44-2bf575dd2513)

Combined both passwd and shadow files into a single file and crack the hash. Is the Elmeris password his own username i.e. elmik9? If so a poor choice of a password!

![image](https://github.com/user-attachments/assets/1ff16e78-52fc-4836-99e6-71fb4b9c84dd)

## Reference
https://www.freecodecamp.org/news/crack-passwords-using-john-the-ripper-pentesting-tutorial/

https://terokarvinen.com/2023/crack-file-password-with-john/

https://linuxize.com/post/etc-shadow-file/
