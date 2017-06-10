# Back Story
Recentcly there're soooooo many programmers tryings to stop the bot 
to invade our apps. We can just easily implement CSRF, Password 
Hashing, even implementing Google Captcha to get rid of those 
bots.Those technique are surely can be solved asily by bots (uhh, i 
mean, those who use CSRF and Password Hashing things, not the 
Google Captcha one). We can easily reverse the algorithm, then 
strip those security chalanges to get juicy things from it. So, I'm 
getting woried of it.

Currently i'm able to strip a SSO login by reversing the ticket 
info then passing it to the ticket reciever on the client. 
[Here's a project of it](https://github.com/chez14/cas-min-min-php). 
The project are currently being developed but it now can be used to 
do some simple task. I don't know if it's ok to do it or not, but 
in my opinion, let's get a new method to stop the bot to steal our 
juicy stuff.

## How it's work
I'm trying to do some stuff that requires much executing stuff without making any ruckus thing. So i decided to use the JavaScript chalanges to do the trick.

The objective are relatively simple, we just need to pass a 
obfuscated minified modified Js file to it's form then make the 
browser execute it then get the respose from it and then make it as 
a field of the form. The field are required and sohuld be filled.
The Js script are taking string from Cookies, given Payload, and set 
a Cookie to it as a secondary responses.

Easy, right?