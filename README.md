**[DRAFT]**

# Cybersec-101
A guide on how to safely use computers and the internet for the common man. Each section aims to explain one aspect of internet technology and how it can be used against you if used recklessly.

**Chapters:**
- HTML Cookies and CSRF Attacks
- HTTP vs HTTPS and Packet Sniffing Attacks
- SSL Certificates and Phishing Attacks
- The Password stuff

## HTML Cookies and Cross-Site Request Forgery (CSRF) Attacks

An HTML Cookie is a piece of information of locally stored information that allows a website to individually identify your computer from other computers in your network. Without cookies, you would have to log in to every website and rebuild every shopping cart for each browsing session. Life without cookies would be tedious, but arguably safer. If someone stole your laptop and went to Amazon.com, the thief would have access to your Amazon account because the cookies on your computer would have them automatically logged in to your account. To keep yourself safe, only accept cookies on a trusted device, preferably one that can't be easily accessed by an authorized user (phones are easier to steal than desktops). Of course, some websites don't even give you the option to accept or reject cookies. In these circumstances, it's best to use an incognito tab so that the cookies used are destroyed once the incognito tab is closed. 

What if you live in a nice suburban neighborhood with a 0% change of being mugged? Should you still be vigilant about cookies? Absolutely; a hacker could use a Cross-Site Request Forgery (CSRF) attack to access your accounts by using your cookies. Back in yee old days, a hacker could sneak JavaScript code into an email that would run once the victim ran the HTML file (A.K.A viewed the email). Thus that hacker could send a request from your computer to your bank account requesting that it transferred 5K dollars to some offshore bank and the website would comply because the request came from your computer using your cookies. Fortunately, these types of attacks are not as common since most email clients have taken measures to stop JavaScript from sneaking into emails. Additionally many websites with sensitive information (such as banks) don't allow cookies to be stored anyways.


## HTTP vs HTTPS
**See my friend there are two types of websites in this world; those with SSL/TLS encryption and those without, [you dig?](https://youtu.be/l1711jiiRtM)**

Adding an "S" to Hypertext Transfer Protocol (HTTP) gives us HTTPS; the "S" stands for "secured". Packets sent to a website using HTTPS are encrypted using Transport Layer Security (TLS) encryption. 

(NERD DETAILS: TLS is sometimes refered to as SSL or SSL/TLS. Secured Socket Layer (SSL) encryption was developed by Netscape back in 1995 and was the predecessor to TLS. After the company withered away, updates to SSL were developed by the Internet Engineering Task Force and the name was changed to TLS to reflect the change in ownership.)

Encryption is a topic that can be infinitely complex, but the thing you need to know is that HTTP lets other people see the packets being exchanged while HTTPS doesn't. Therefore if you transmitted data through wifi in public, someone with a packet sniffer could see and interpret the data being sent to an HTTP website. That is why [ever since 2019 Google Chrome has flagged all HTTP websites as unsecure](https://security.googleblog.com/2018/02/a-secure-web-is-here-to-stay.html)

![alt text](

HTTP is fine if you are simply viewing a website for information. However if you are ever prompted to enter names, addresses, credit card information, email, phone numbers, etc, just know your packets are naked. Only consider entering sensitive information to HTTPS websites, they will put a mantle of encryption to your data.

Also this is why you probably don't need a VPN subscription. That "military grade encryption" ofered by most VPN services is already provided by all HTTPS websites.

## SSL Certificates and Phishing Attacks

**You think a green padlock means you're safe? THINK AGAIN!**

Merely having HTTPS doesn't mean the website is safe. Even if your connection to a website is encrypted, it could be that the website is a fake and you are actually transmitting data to a scammer/ hacker mascerading as the real website. Fortunately, Certificate Authorities exist to help us verify that the website we are in is the authentic website.

Every HTTPS website has a SSL certificate (Nerd alert: because the certificate contains the public key for the website that is required for public-private key encrpytion, it is therefore required for HTTPS to be secured). Yet not every certficate should be trusted. Websites can derive their certificates from public CA, Private CA or even provide self-signed certificates. 

Popular Public Certificate Authorities include:
Sectigo
Comodo
DigiCert
Symatic
Thawte
GeoTrust
RapidSSL
GoDaddy

Popular Private Certificate Authorities:
Microsoft CA
Apple CA
AWS (Amazon) CA
WARNING AZURE MAKES SITES APPEAR TO BE FROM MICROSOFT

So what should you look out for? Certificates that are 

 ## All about passwords
 
 We all know what passwords are, but few know how to be responsible with our passwords. There are two concepts you should follow. 
 
 1 - Don't make your password predicable
 
 Password is a terrible password. So is Password1234. To keep hackers from bruteforcing their way into a login, avoid using dictionary words. Opt to use slang, made up words, or leet speak. (Th1s is 133t sp3ak, c00l r1ght?). Additionally never use the same password twice or establish a pattern with your password creation process. Explain data breaches and "hail hitler" ww2 decryption. Obviously use number and symbols when possible
 
 2 - Don't keep your password naked
 Don't have your passowrds in a stickynote on ur monitor, nor written in a text file on ur computer. 
 
 Use a password manager to keep things simple.

While it can be a little tedious, it greatly enhances personal security. Use your phone (SMS, email, or device [google]). Consider using U2F key or QR

AVOID BIOMETRICS!!!! (Explain legal reasons police can search ur phone using bios)



