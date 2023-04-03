
# Cybersecurity 101 for the commonman (or woman, or child, or kitten)
A guide on how to safely use computers and the internet for the average person. Each section aims to explain one aspect of internet technology and how it can be used against you if used recklessly.

**Chapters:**
- [HTML Cookies and CSRF Attacks](https://github.com/Cham0i/Cybersec-101#html-cookies-and-cross-site-request-forgery-csrf-attacks)
- [HTTP vs HTTPS and Packet Sniffing Attacks](https://github.com/Cham0i/Cybersec-101#html-cookies-and-cross-site-request-forgery-csrf-attacks)
- [SSL Certificates and Phishing Attacks](https://github.com/Cham0i/Cybersec-101#ssl-certificates-and-phishing-attacks)
- [The Password stuff](https://github.com/Cham0i/Cybersec-101#all-about-passwords)
  - Don't make your password predictable
  - Don't store your passwords raw
  - 2-Factor Authentication
  - Biometric passwords

## HTML Cookies and Cross-Site Request Forgery (CSRF) Attacks

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/1.jpg)

An HTML Cookie is a piece of information of locally stored information that allows a website to individually identify your computer from other computers in your network. Without cookies, you would have to log in to every website and rebuild every shopping cart for each browsing session. Life without cookies would be tedious, but arguably safer. If someone stole your laptop and went to Amazon.com, the thief would have access to your Amazon account because the cookies on your computer would have them automatically logged in to your account. To keep yourself safe, only accept cookies on a trusted device, preferably one that can't be easily accessed by an authorized user (phones are easier to steal than desktops). Of course, some websites don't even give you the option to accept or reject cookies. In these circumstances, it's best to use an incognito tab so that the cookies used are destroyed once the incognito tab is closed. 

What if you live in a nice suburban neighborhood with a 0% change of being mugged? Should you still be vigilant about cookies? Absolutely; a hacker could use a Cross-Site Request Forgery (CSRF) attack to access your accounts by using your cookies. Back in yee old days, a hacker could sneak JavaScript code into an email that would run once the victim ran the HTML file (A.K.A viewed the email). Thus that hacker could send a request from your computer to your bank account requesting that it transferred 5K dollars to some offshore bank and the website would comply because the request came from your computer using your cookies. Fortunately, these types of attacks are not as common since most email clients have taken measures to stop JavaScript from sneaking into emails. Additionally many websites with sensitive information (such as banks) don't allow cookies to be stored anyways.

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/2.jpg)

## HTTP vs HTTPS

**See my friend there are two types of websites in this world; those with SSL/TLS encryption and those without**

Adding an "S" to Hypertext Transfer Protocol (HTTP) gives us HTTPS; the "S" stands for "secured". Packets sent to a website using HTTPS are encrypted using Transport Layer Security (TLS) encryption. (TLS is sometimes refered to as SSL or SSL/TLS. Secured Socket Layer (SSL) encryption was developed by Netscape back in 1995 and was the predecessor to TLS. After the company withered away, updates to SSL were developed by the Internet Engineering Task Force and the name was changed to TLS to reflect the change in ownership.)

Encryption is a topic that can be infinitely complex, but the thing you need to know is that HTTP lets other people see the packets being exchanged while HTTPS doesn't. Therefore if you transmitted data through wifi in public, someone with a packet sniffer could see and interpret the data being sent to an HTTP website. That is why [ever since 2019 Google Chrome has flagged all HTTP websites as unsecure](https://security.googleblog.com/2018/02/a-secure-web-is-here-to-stay.html)

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/3.png)

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/5.png)

HTTP is fine if you are simply viewing a website for information. However if you are ever prompted to enter names, addresses, credit card information, email, phone numbers, etc, just know your packets are naked. Only consider entering sensitive information to HTTPS websites, they will put a mantle of encryption to your data.

Also, this is why you probably don't need a VPN subscription. That "military-grade encryption" offered by most VPN services is already provided by all HTTPS websites.

## SSL Certificates and Phishing Attacks

**You think a green padlock means you're safe? THINK AGAIN!**

Merely having HTTPS doesn't mean the website is safe. Even if your connection to a website is encrypted, it could be that the website is a fake and you are actually transmitting data to a scammer/ hacker masquerading as the real website (known as a phishing website). 

In order for a HTTPS website to be encrypted the website must have a SSL certificate (because the certificate contains the public key for the website that is required for public-private key encrpytion). These SSL Certificates can come from many places, but the ones we trust should derive their SSL certifcates from a Certificate Authority (CA) who ties personal or company information to a domain.

Popular Certificate Authorities include:
- Sectigo
- Comodo
- DigiCert
- Symatic
- Thawte
- GeoTrust
- RapidSSL
- GoDaddy

Within these CAs there are three different types of certificates with varying levels of trust.

- Domain (DV)

DV certificate's only requirement is that the buyer demonstrate control of the domain or URL. It is typically easy to obtained and used by blogs and other obscure parts of the internet. You should be very skeptical of inputing personal information on theses websites.


- Organizational (OV)

OV certificates must verify the domain owner as well as several details related to the affiliated business including name, type, status, and physical address. If you are ordering food from your local mom-and-pop shop and their website has a OV certificate, its safe to say you are giving your credit card information to the right people.

- Extended (EV)

Nine additional steps are required to obtain a EV certificate. These include verifying a businesses’ public phone number, length of time in business, registration number and jurisdiction, as well as a domain fraud check, contact blacklist check and a telephone call to authenticate the employment status of the requestor. Below is Apple's SSL certificate. Because this is a EV SSL certificate verified by DigiCert we can be certain that this website is an authentic Apple website.

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/6.png)

**BEWARE** There has been instances where EV certificate were used for phishing attacks. For example the following websites had a valid Microsoft EV SSL certificate despite it being a phishing website.

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/phishing-site.jpg)

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/4.jpg)

So why does this fake website have a real Microsoft certificate? Because their website is hosted in Microsoft Azure, and therefore they have a valid Microsoft SSL certificate. The only thing you can do here is be skeptical. If the URL looks funny, such as the ones shown above, consider accessing the website throught a different source (like going to your google account to go to your Google Docs or YouTube account) to double check that the website is legitimate.

## All about passwords
 
 We all know what passwords are, but few know how to be responsible with our passwords. There are two concepts you should follow. 
 
### 1 - Don't make your password predicable

Password is a terrible password; so is Password1234. To keep hackers from brute-forcing their way into a login, avoid using dictionary words, opt to use slang, made-up words, or leet speak (th1s is 133t sp3ak, c00l r1ght), and remember to use numbers and symbols when possible.

Additionally, never use the same password twice or establish a pattern with your password creation process because websites have their data breached all the time. In fact, there is a whole website dedicated to tracking all these breaches. https://haveibeenpwned.com/

For demonstration purposes, lets see if I have had my password leaked.

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/7.png)

I was a dumb middle schooler when I signed up for these websites and they were dumb for having their data breached. Fortunately, D20 only compromised my password hash, meaning my password in its encrypted form. If D20 stored my password raw, hackers would have known that I use "ILove1D1recti0n" for D20 and could have tried to use that password for my google account. This is why you NEVER use the same password twice or make them predictable (which is why "ILove1D1recti0n1234" for my google account password is bad too. Also ignore that Wattpad data breach, I think someone else used my email for that...).

### 2 - Don't store your passwords raw

If you have your passwords on a sticky note on your monitor or written in a text file on your computer, stop it. If you are going to store your passwords naked, at the very least store them somewhere private. Writting your passwords down in your diary or on an external flashdrive is better than storing them out in the open. Yet, storing your passwords as a hash, like how most websites do, is a far better alternative than storing them raw.

I know this is extremely tedious and I don't expect the commonman to single-handedly encrypt all of their passwords. Which is why I recommend everyone use a password manager. It may not be as secure as storing your passwords yourself, but the increased convinience offered by most password managers makes them a reasonable option for managing passwords. Just avoid LastPass because they recently got their [data breached](https://blog.lastpass.com/2023/03/security-incident-update-recommended-actions/) (told you these were common). I use BitWarden; which requires a master password for accessing my other passwords and also allows me to copy passwords to my clipboard, which keeps them hidden as black dots when pasted.

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/bit.png)

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/warden.png)

### 2-Factor Authentication

When you are walking down a sketchy alleyway its best to walk with someone else so that both of you may protect each other in case of an attack. 2 Factor authentication essentially is that second password. 2-factor authentication is usually required when there is a log in from an unknown device. Althought some applications have the option to require 2 factor authentication for transactions, sessions, account changes, etc. If you ever been sent and email or SMS with a code to log in, congratulations, you already have 2 factor authentication for that service; that's really all you need. But if you want to be hardcore with your security you can use QR authentication or a U2F key to greatly reduce your chances of getting laid.

### A warning to the people using biometric passwords

If you use your fingerprints or face to unlock your phone, you should consider switching back to a pattern or pin password. Police officers and jealous partners can easily unlock your phone without your permission. As a person who is wanted by the state of Oklahoma and who is currently cheating on his girlfriend of 7 years, I can't tell you how many times having a simple memorized password has saved me from trouble.

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/noob.jpg)

Speaking more on the legal issue (because I'm a law nerd too), the 5th Amendment allows us to remain silent in face of police interrogation. However courts have already established that forcing defendants to disclose names, home addresses, and even fingerprints are not considered interrogation as per the Routine Booking Exception, see United States v. Cruz-Mercedes, 945 F.3d 569 (1st Cir. 2019). Thus a police officer is legally allowed to use a defendant's fingerprints to unlock their phone without their consent. In fact, this rationale has already been adopted in United States v. Barrera, 415 F. Supp. 3d 832 (N.D. Ill. 2019), and will continue to be implemented in other jurisdictions until it inevitably has to be resolved by the SCOTUS. In no case that I am aware of, has a justice ever held that person must be required to disclose their phone's password to the government. To require anyone to say anything against their will is a clear violation of the 5th Amendment and thus I urge everyone to use memorized passwords instead of biometric passwords to ensure they are protected under the 5th Amendment.
