**[DRAFT]**

# Cybersec-101
A guide on how to safely use computers and the internet for the common man. Each section aims to explain one aspect of internet technology and how it can be used against you if used recklessly.

**Chapters:**
- HTML Cookies and CSRF Attacks
- HTTP vs HTTPS and Packet Sniffing Attacks
- SSL Certificates and Phishing Attacks
- The Password stuff

## HTML Cookies and Cross-Site Request Forgery (CSRF) Attacks

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/1.jpg)

An HTML Cookie is a piece of information of locally stored information that allows a website to individually identify your computer from other computers in your network. Without cookies, you would have to log in to every website and rebuild every shopping cart for each browsing session. Life without cookies would be tedious, but arguably safer. If someone stole your laptop and went to Amazon.com, the thief would have access to your Amazon account because the cookies on your computer would have them automatically logged in to your account. To keep yourself safe, only accept cookies on a trusted device, preferably one that can't be easily accessed by an authorized user (phones are easier to steal than desktops). Of course, some websites don't even give you the option to accept or reject cookies. In these circumstances, it's best to use an incognito tab so that the cookies used are destroyed once the incognito tab is closed. 

What if you live in a nice suburban neighborhood with a 0% change of being mugged? Should you still be vigilant about cookies? Absolutely; a hacker could use a Cross-Site Request Forgery (CSRF) attack to access your accounts by using your cookies. Back in yee old days, a hacker could sneak JavaScript code into an email that would run once the victim ran the HTML file (A.K.A viewed the email). Thus that hacker could send a request from your computer to your bank account requesting that it transferred 5K dollars to some offshore bank and the website would comply because the request came from your computer using your cookies. Fortunately, these types of attacks are not as common since most email clients have taken measures to stop JavaScript from sneaking into emails. Additionally many websites with sensitive information (such as banks) don't allow cookies to be stored anyways.

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/2.jpg)

## HTTP vs HTTPS

See my friend there are two types of websites in this world; those with SSL/TLS encryption and those without

Adding an "S" to Hypertext Transfer Protocol (HTTP) gives us HTTPS; the "S" stands for "secured". Packets sent to a website using HTTPS are encrypted using Transport Layer Security (TLS) encryption. (NERD DETAILS: TLS is sometimes refered to as SSL or SSL/TLS. Secured Socket Layer (SSL) encryption was developed by Netscape back in 1995 and was the predecessor to TLS. After the company withered away, updates to SSL were developed by the Internet Engineering Task Force and the name was changed to TLS to reflect the change in ownership.)

Encryption is a topic that can be infinitely complex, but the thing you need to know is that HTTP lets other people see the packets being exchanged while HTTPS doesn't. Therefore if you transmitted data through wifi in public, someone with a packet sniffer could see and interpret the data being sent to an HTTP website. That is why [ever since 2019 Google Chrome has flagged all HTTP websites as unsecure](https://security.googleblog.com/2018/02/a-secure-web-is-here-to-stay.html)

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/3.png)

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/5.png)

HTTP is fine if you are simply viewing a website for information. However if you are ever prompted to enter names, addresses, credit card information, email, phone numbers, etc, just know your packets are naked. Only consider entering sensitive information to HTTPS websites, they will put a mantle of encryption to your data.

Also this is why you probably don't need a VPN subscription. That "military grade encryption" ofered by most VPN services is already provided by all HTTPS websites.

## SSL Certificates and Phishing Attacks

**You think a green padlock means you're safe? THINK AGAIN!**

Merely having HTTPS doesn't mean the website is safe. Even if your connection to a website is encrypted, it could be that the website is a fake and you are actually transmitting data to a scammer/ hacker mascerading as the real website. Fortunately, Certificate Authorities exist to help us verify that the website we are in is the authentic website.

Every HTTPS website has a SSL certificate (Nerd alert: because the certificate contains the public key for the website that is required for public-private key encrpytion, it is therefore required for HTTPS to be secured). Yet not every certficate should be trusted. Websites can derive their certificates from a certificate authority who ties personal or company information to a domain.

Popular Certificate Authorities include:
- Sectigo
- Comodo
- DigiCert
- Symatic
- Thawte
- GeoTrust
- RapidSSL
- GoDaddy

These certificate authorities have three different types of certificates

- Domain (DV)

The buyer only needs to demonstrate control of the domain or URL. While convenient, this one-check form of validation is the lowest standard on the Internet—and should be trusted accordingly.


- Organizational (OV)

OV certificates CAs must verify the domain owner as well as several details related to the affiliated business including name, type, status, and physical address.

- Extended (EV)

With EV, nine additional steps are required including verifying a businesses’ public phone number, length of time in business, registration number and jurisdiction, as well as a domain fraud check, contact blacklist check and a telephone call to authenticate the employment status of the requestor. Below is Apple's SSL certificate. Because this is a EV SSL certificate verified by DigiCert we can be certain that the website we got the certificate from is an authentic Apple website.

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/6.png)

EVEN with EV certificates take caution of vulnerabiliites. For example the following websites has a valid Microsoft EV SSL certificate despite it being a phishing website (fake website used to fish for credentials).

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/phishing-site.jpg)

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/4.jpg)

Why does this fake website have a real Microsoft certificate? Because their website is hosted in Microsoft Azure, and therefore they have a valid Microsoft SSL certificate. The only thing you can do here is be skeptical. If the URL looks funny, such as the ones shown above, consider accessing the website throught a different source (like going to your google account to go to your Google Docs or YouTube account) to double check that the website is legitimate.

## All about passwords
 
 We all know what passwords are, but few know how to be responsible with our passwords. There are two concepts you should follow. 
 
### 1 - Don't make your password predicable
 
 Password is a terrible password. So is Password1234. To keep hackers from bruteforcing their way into a login, avoid using dictionary words. Opt to use slang, made up words, or leet speak. (Th1s is 133t sp3ak, c00l r1ght?). Use number and symbols when possible 
 
Additionally never use the same password twice or establish a pattern with your password creation process. This is because websites have their data breached all the time. As a matter of fact there is a whole website dedicated to tracking all theses breaches. https://haveibeenpwned.com/

Let's use my email for example

![alt text](https://github.com/Cham0i/Cybersec-101/blob/main/Cybersec101/7.png)

I was a dumb middleschooler when I signed up for these websites. So had a hacker used my email address and password from theses breaches to log in to my google account they probably would have succeeded. This is why you don't use the same passwords twice, and why you should change your passwords every year. 

(Fortunately D20 only compromised my password hash, meaning my password in its encrypted form. Had they stored my password naked I would be in very big trouble. Also we are not gonna talk about why I had a wattpad account in middleschool.)

### 2 - Don't keep your passwords naked and afraid

If you have your passowrds in a stickynote on your monitor or written in a text file on ur computer, stop it. If you are going to store your passwords naked, at the very least store them somewhere private. Writting your passwords down in your diary or on a external flashdrive are better than storing them out in the open. Yet, storing your passwords as a hash, like how most websites do, is a far better alternative than storing them naked. 

When you are walking down a sketchy alleyway its best to walk with someone else so that both of you may protect each other in case of an attack. 2 Factor authentication essentially is that second password. 2-factor authentication is usually required when there is a log in from an unknown device. althought some applications have the option to require 2 factor authentication for transactions, sessions, account changes, etc. If you ever been sent and email or SMS with a code to log in, congratulations, you already have 2 factor authentication for that service. That's really all you need, but if you want to be hardcore with your security you can use QR authentication or a U2F key to greatly reduce your chances of getting laid.

I know this is extremely tedious and I don't expect the common man to single handedly encrypt all of their passwords. This is why I recommend everyone use a password manager. Your ideal password manager should store all of your passwords as hashes and converts them back to its naked form so that you can copy and paste them into websites. It should also not be LastPass because they recently got their [data breached](https://blog.lastpass.com/2023/03/security-incident-update-recommended-actions/) (told you these were common).

### Disclaimer on the people using biometric passwords

If you use your fingerprints or face to unlock your phone, you should consider switching back to a pattern or pin password. Police officers and jelous partners can easily unlock your phone without your permission. As a person who is wanted by the state of Oklahoma and who is currently cheating on his girlfriend of 7 years, I can't tell you how many times having a simple memorized password has saved me from trouble.

Speaking more on the legal issue (because im a law nerd too), the 5th ammendment allows us to remain silent in face of police interregation. However courts have already established that forcing defendants to disclose names, home addresses, and even fingerprints are not considered interregation as per the Routine Booking Exception, see United States v. Cruz-Mercedes, 945 F.3d 569 (1st Cir. 2019). Thus a police officer is legally allowed to use a defendant's fingerprints to unlock their phone without their concent. In fact this rationale has already been adopted in United States v. Barrera, 415 F. Supp. 3d 832 (N.D. Ill. 2019), and will continue to be implemented in other jurisdictions until it inevitably has to be resolved by the SCOTUS. In no case that I am aware of, has a justice ever held that person must be required to disclose their phone's password to the government. To require anyone to say anything against their will is a clear violation of the 5th ammendment and thus I urge everyone to use memorized passwords instead of biometric passwords to ensure they are protected under the 5th ammendment.

