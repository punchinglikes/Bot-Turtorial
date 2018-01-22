# Bot-Turtorial
How to start making your own discord bot in discord.js  
  
  
  # So, you want to learn how to make a discord bot, great!
  I remember when i first started off and it was stressful. Hopefully this guide will help you get pointed in the right direction to becoming the greatest bot developer of all time! 
     
  #  What is needed before I start?
You will need a few programs if you want to use this turtorial correctly.
  
  1. [Nodejs](http://link.url/) - Nodejs is a powerful tool that basicly takes your javascript code and converts it into a runable aplication on your computer.
  2. [npm](http://link.url/) - npm is a packaging software that will (in this case) download the nodes you need to connect to the discord API. (This comes with Nodejs)
 3. Some sort of text editor, just don't use notepad! use a program made to code in like [Atom](http://link.url/) or [Sublime](http://link.url/)
  
  # Creating your application
    
   So lets jump right in! First you need to go to [the discord developers website](https://discordapp.com/developers/applications/me) and create a new application. Now, name your application and give it a wonderful description to help you know what it will do. Finally hit that create app button! Thats not it though, that was too easy.scroll down til you find the button called create a bot user. accept all of it asks of you it wants.  
    
  # The start of your code
  now its finally time to code the discord bot. All we will be doing to start off will be nothing fancy, just how to make your bot say pong when you say !ping. so first, make a folder on your desktop called whatever you want your bot to be called. next open up cmd or powershell in that positon (shift right click, open cmd/powershell here) and type "npm init --save" (without quotes). Hit enter through it all (endless you want to change any of it). This will download the package.json file that you need to run. next, keep your terminal open and type "npm install discord.js --save" to install the discord.js package. this will do 2 things. 1,  it makes a node_modules folder where all the packages you install go. And it might make a package-lock.json (you can leave this alone). Now, make 2 files. 1 called "index.js" and one called "config.json". open up the config.json with your editor and copy this code to it - 
```{
	"token": "",
	"prefix": ""
}```
