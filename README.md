**[DRAFT]**

# Cybersec-101
A guide on how to safely use computers and the internet for the common man. Each section aims to explain one aspect of internet technology and how it can be used against you if used recklessly.

**Chapters:**
- HTML Cookies and CSRF Attacks
- SSL Certificate Authorities and Phishing Attacks
- HTTP vs HTTPS and Man-in-the-Middle Attacks
-The Password Commandments
  - DOnt use a predictable password (1337 and slang > dictionary words; never use same password twice; don't use "hail hitler" encryption; etc)
  - Avoid seeing your passwords naked. (Written in post it note on monitor, ideally don't know your password use password manager)
  - FUCK biometrics (POLICE OFFICERS CAN JUST USE YOUR PHONE WITHOUT UR PERMISSION!!!!)
  
## HTML Cookies and Cross-Site Request Forgery (CSRF) Attacks

A HTML Cookies is a piece of information of localy stored information that allows a website to individually identify your computer from other computers in your network. Without cookies, you would have to log in to every website and rebuild every shopping cart for each browsing session. Life without cookies would be tedious, but arguably safer. If someone stole your laptop and went to Amazon.com, the theif would have access to your Amazon account because the cookies on your computer would have them automatically logedin to your account. To keep yourself safe, only accept cookies on a trusted device, and preferably one that can't be easily accessed by an authorized user (phones are easier to steal than desktops). Ofcourse, some websites don't even give you the option to accept or reject cookies. In these circumstances, its best to use an incognito tab so that the cookies used are destroyed once the incognito tab is closed. 

What if you live in a nice sub-urban neighborhood? No one is going to mug you, should you still be vigilant about cookies? Absolutely; a hacker could use a Cross-Site Request Forgery (CSRF) attack to access your accounts by using your cookies. Fortunately this isn't much of a widespread problem anymore. Back in the yee old days, a hacker could sneak in JavaScript code into an email that would run once the victim ran the html file (A.K.A viewed the email). Thus that hacker could send a request from your computer to a your bank account requesting that it transfered 5K dollars to some offshore bank and the website would comply because the request came from your computer using your cookies. Fortunately these types of attacks are not as common since most email clients have taken measure to stop JavaScript from sneaking into emails and many websites with sensitive information (such as banks) don't allow cookies to be stored anyways. Cookies are dangerous, consume them with milk.

## SSL Certifcation Authorities and Phishing Attacks

Do you know how to tell the difference between a real Rolex and a fake Rolex? Me neither. Similarly, I bet both of us wouldn't be able to tell the difference between a fake YouTube page and a real one, especially since its extremely easy to copy and paste the html and css layout of a website. Fortunately, Certificate Authorities exist to help us verify that the website we are in is the real website. 

This is how it looks like

Unfortunately, not many people know about SSL certificates and thus phishing attacks are quite effective. Congrats you win a free virus. Or have your email spammed or phone. 


## HTTP vs HTTPS

The S stands for secured, meaning your information is encrypted. Packets sent to a HTTP website can be intercepted and viewed raw (such as by WireShark)

## All about passwords

While it can be a little tedious, it greatly enhances personal security. Use your phone (SMS, email, or device [google]). Consider using U2F key or QR

