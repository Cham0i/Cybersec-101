**[DRAFT]**

# Cybersec-101
A guide on how to safely use computers and the internet for the common man. Each section aims to explain one aspect of internet technology and how it can be used against you if used recklessly.

**Chapters:**
- HTML Cookies and CSRF Attacks
- SSL Certificate Authorities and Phishing Attacks
- HTTP vs HTTPS and Man-in-the-Middle Attacks
-The Password stuff

## HTML Cookies and Cross-Site Request Forgery (CSRF) Attacks

A HTML Cookies is a piece of information of localy stored information that allows a website to individually identify your computer from other computers in your network. Without cookies, you would have to log in to every website and rebuild every shopping cart for each browsing session. Life without cookies would be tedious, but arguably safer. If someone stole your laptop and went to Amazon.com, the theif would have access to your Amazon account because the cookies on your computer would have them automatically logedin to your account. To keep yourself safe, only accept cookies on a trusted device, and preferably one that can't be easily accessed by an authorized user (phones are easier to steal than desktops). Ofcourse, some websites don't even give you the option to accept or reject cookies. In these circumstances, its best to use an incognito tab so that the cookies used are destroyed once the incognito tab is closed. 

What if you live in a nice sub-urban neighborhood? No one is going to mug you, should you still be vigilant about cookies? Absolutely; a hacker could use a Cross-Site Request Forgery (CSRF) attack to access your accounts by using your cookies. Fortunately this isn't much of a widespread problem anymore. Back in the yee old days, a hacker could sneak in JavaScript code into an email that would run once the victim ran the html file (A.K.A viewed the email). Thus that hacker could send a request from your computer to a your bank account requesting that it transfered 5K dollars to some offshore bank and the website would comply because the request came from your computer using your cookies. Fortunately these types of attacks are not as common since most email clients have taken measure to stop JavaScript from sneaking into emails and many websites with sensitive information (such as banks) don't allow cookies to be stored anyways. Cookies are dangerous, consume them with milk.

## Certifcation Authorities and Phishing Attacks

Do you know how to tell the difference between a real Rolex and a fake Rolex? Me neither. Similarly, I bet both of us wouldn't be able to tell the difference between a fake YouTube page and a real one, especially since its extremely easy to copy and paste the html and css layout of a website. Fortunately, Certificate Authorities exist to help us verify that the website we are in is the real website. 



## HTTP vs HTTPS
Adding an "S" to Hypertext Transfer Protocol (HTTP) gives us HTTPS; the S stands for secured. Packets sent to a website using HTTPS are encrypted using Transport Layer Security (TLS) encryption. 

(NERD DETAILS: TLS is sometimes refered to as SSL or SSL/TLS. Secured Socket Layer (SSL) encryption was developed by Netscape back in 1995 and was the predecessor to TLS. After the company withered away, updates to SSL were developed by the Internet Engineering Task Force and the name was changed to TLS to reflect the change in ownership.)

Encryption is a topic that can be infinately complex, but the thing you need to know is that HTTP lets other people plainly see the packets being exchanged while HTTPS doesn't. Therefore if you transmitted data through wifi in public, someone with a packet sniffer could see and interpret the data being sent to a HTTP website.

 ## All about passwords
 
 We all know what passwords are, but few know how to be responsible with our passwords. There are two concepts you should follow. 
 
 1 - Don't make your password predicable
 
 Password is a terrible password. So is Password1234. To keep hackers from bruteforcing their way into a login, avoid using dictionary words. Opt to use slang, made up words, or leet speak. (Th1s is 133t sp3ak, c00l r1ght?). Additionally never use the same password twice or establish a pattern with your password creation process. Explain data breaches and "hail hitler" ww2 decryption. Obviously use number and symbols when possible
 
 2 - Don't keep your password naked
 Don't have your passowrds in a stickynote on ur monitor, nor written in a text file on ur computer. 
 
 Use a password manager to keep things simple.

While it can be a little tedious, it greatly enhances personal security. Use your phone (SMS, email, or device [google]). Consider using U2F key or QR

AVOID BIOMETRICS!!!! (Explain legal reasons police can search ur phone using bios)



