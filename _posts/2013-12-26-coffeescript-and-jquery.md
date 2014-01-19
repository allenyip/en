---

title: CoffeeScript n jQuery

layout: post

---
The idea of learning [CoffeeScript](http://coffeescript.org/) keeps erminding me after I met [NodeJS](http://allenyip.com/2013/01/30/meeting-nodejs.html), I think it's because all coders praise it so much. Today in my break, I finally got it.

##**CoffeeScript**

CoffeeScript is created by a famous JavaScript developer [Jeremy Ashkenas](http://ashkenas.com/), the Backbone and Underscore libraries he made is also really shining.

>CoffeeScript is a little language that compiles into JavaScript.   
>It's just JavaScript

These two sentences define CoffeeScript simply and precisely, the only goal of CoffeeScript is to make JS easier. It's true that JS has many misunderstanding things. It also mixes kinds of language pattern. I was told that the creator of JS, Brendan Eich, spent just 10 days inventing it. Instead of saying that CoffeeScript is invented to simplify JS, mayeb it's more like to please all these injured developers.

###**INSTALLATION**

CoffeeScript is installed through Node package, so we need to download and install Node and npm first. Nowdays, Node is so easy to install, it also support one click installation is Windows platform.

After install Node and npm, just type this code in shell:

>sudo npm install -g coffee-script

###**COMMAND**

You can use coffee command to compile coffee scripts now, here are some useful params:

* -c, --compile: compile .coffee script to .js
* -o, --output [DIR]: write all js script into a specific dir
* -w, --watch: check if the script is updated
* -j, --join [FILE]: write many scripts into one
* null:just input coffee it opens REPL, type Ctrl-D to end, and Ctrl-V to select lines.

###**GRAMMAR**

CoffeeScript codes is beautiful, things happen in compiling is beautiful too. Check the grammar of functions, it's similar to a simple assignment statement.

{% gist 8485182 cup0.coffee %}

Assignment may also like this:

{% gist 8485182 cup1.coffee %}

Array iterator is very strong:

{% gist 8485182 cup2.coffee %}

All the grammar is written in the [CoffeeScript](http://coffeescript.org/) homepage, it also provide online compile, rookie like me can learn fast in their homepage.

##**jQuery**

Years ago, when young [John Resig](http://ejohn.org/) wrote jQuery at night, he would never expect it becoming so popular today. Almost every developers know jQuery, as one of the most popular library in JS libraries, it helps many front-end developers in a very good way.

Don't want to say things about jQuery, here I just want to show you how to combine these two beautiful things together.

###**DomReady** 

The ready function in CoffeeScript looks like this:

{% gist 8485182 cup3.coffee %}

###**Form** 

Getting input values just by noe sentence(awesome!):

{% gist 8485182 cup4.coffee %}

###**Callback** 

An simple callback example:

{% gist 8485182 cup5.coffee %}

...

##**CONCLUSION**

Front-end Development is really a beautiful thing, but I still can't make my mind to walk this path. Now there are too many things I want to learn but I don't have enough time. The worst thing is, I'm still digging different holes. Just like now, I want to dig about Ruby again, before I finish learning CoffeeScript. It's bad, I know, but I just can't stop it :(