# Bot-Tutorial
How to start making your own discord bot in discord.js  
  
  
  # So, you want to learn how to make a discord bot, great!
  I remember when I first started off and it was stressful. Hopefully this guide will help you get pointed in the right direction to becoming the greatest bot developer of all time! 
     
  #  What is needed before I start?
You will need a few programs if you want to use this tutorial correctly.
  
  1. [Nodejs](http://nodejs.org) - Nodejs is a powerful tool that basically takes your javascript code and converts it into a runable aplication on your computer.
  2. [npm](http://npmjs.com) - npm is a packaging software that will (in this case) download the nodes you need to connect to the discord API. (This comes with Nodejs)
 3. Some sort of text editor, just don't use notepad! use a program made to code in like [Atom](http://atom.io) or [Sublime](http://sublimetext.com)
  
  # Creating your application
    
   So lets jump right in! First you need to go to [the discord developers website](https://discordapp.com/developers/applications/me) and create a new application. Now, name your application and give it a wonderful description to help you know what it will do. Finally hit that create app button! Thats not it though, that was too easy.scroll down til you find the button called create a bot user. accept all of it asks of you it wants.  
    
  # The start of your code
  now its finally time to code the discord bot. All we will be doing to start off will be nothing fancy, just how to make your bot say pong when you say !ping. so first, make a folder on your desktop called whatever you want your bot to be called. next open up cmd or powershell in that positon (shift right click, open cmd/powershell here) and type "npm init --save" (without quotes). Hit enter through it all (endless you want to change any of it). This will download the package.json file that you need to run. next, keep your terminal open and type "npm install discord.js --save" to install the discord.js package. this will do 2 things. 1,  it makes a node_modules folder where all the packages you install go. And it might make a package-lock.json (you can leave this alone). Now, make 2 files. 1 called "index.js" and one called "config.json". open up the config.json with your editor and copy this code to it
```
{
	"token": "",
	"prefix": ""
}
```
Now, in the empty "" on the token line, add your bot token. You can find your bot token by going back to the discord developer page, find the token feild, click the click to reveal spot, and copy that whole token and paste it in the "" of the config.json file. this means that every time you refer to config.token (config as the json file name and token as that field within the file) it will display your token. so your token line should look like this: 
```
"token": "6qi1NzExYLIJuTYUzhDQy.DUgCFg",
``` 
(im not putting a real token in). now in then prefix side of things, in the quotes put whatever prefix you want it to be (Ex. !). Now you can close that and get to editing the index file (where the actual code will be).
	
   # The Index.js file
	
Now that your configuration settings are complete we will attempt to make a command that will say pong when you say !ping (or whatever prefix you set it as). Open your editor for index.js and at the top add
```
const Discord = require("discord.js");
const client = new Discord.Client();
```
This will define and allow you to use discord.js and connect to there API. Now, we want to be able to let the bot log in. to do that we will add a line of code at the very bottem of all of our code (this is how most people do it). paste this line into your code and make sure it stays at the bottom.
```
client.login(config.json)
```
There is 1 probem, right now the json file cannot be read because we diden't define it. Add this line of code so the bot knows where to look:
```
const config = require('./config.json')
```
There. now the bot will be able to find the bot token and it will log in sucseccfully. Your code should look just about like this:
```
const Discord = require("discord.js");
const client = new Discord.Client();
consg config = require("./config.json")

client.login(config.json)
```
# First command
Now that we set up our index file to login correctly, let's make our first command! we do this by using the client.on function. to make a command, add this bit of code in between the defining section and the client.login:
```
client.on("message", (message) => {
  if (message.content.startsWith(`${config.prefix}ping)) {
    message.channel.send("pong!");
  }
});
```
what this is basicly saying is that if anyone says prefix + pong (!pong) it will send a message saying ping!
	
# Inviting the bot
so now that we coded the discord bot we need to invite it to a server! to do that go to [Discords permission calculator](https://discordapi.com/permissions.html#0) and at the bottom, post your bots id (shown on discord developers page) in the client id field. Then click the link field and it should bring you to your invite page. From there, you can select what server you want your bot in. select one and click the big blue button and accept the captcha.
	
# Turning bot on
Now the bot dosent run itself, you need to be able to keep your console window open. If you have a server and know what to do already, then go ahead and skip this part, but for the rest of us we need to run it on our own computer. To do that open up the command prompt in the same place as we have had it through this whole turtorial, and type "node ." If that dosen't work then try "node index.js" If this is still coming out as errors then something is wrong with your code and you will have to debug to try and find whats wrong. Post the error your getting in the issues tab and I will do ym best to fix the problem. Now if no errors poped up, then your bot was turned on correctly. go to the server you invited your bot into and look at it run! try out the command you added by doing !ping and it should say pong! 
	
# The end!
Thats it for this turtorial! I hope you enjoyed and this help you learn a thing or 2 about discord.js, or node in general. This is my first turtorial so if i messed up anything let me know!
