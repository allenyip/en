---

title: Meeting Node.js

layout: post

---
JavaScript(JS) is an amazing language, sometimes it's so simple that you won't treat it as a programing language, but sometimes it's really complecated with capacities to solve strange things from front-end to back-end.

JQuery, Dojo, YUI, Mootools... All these popular front-end JS frameworks are beautiful and useful, but they just don't attract me. Then I meet Node.js([Node][1]), JS Script running on Server, it roused my enthusiasm towards JS again.

##**GOAL**
JS plays a role as front-end(client) script no matter you write simple JS code to validate data or use JS framework to simplify interaction. However, back-end(server) JS scripts represented by Node are becoming more and more popular(It's really strange that JS can run on server without browser). Different from Java or PHP, Node takes aim at network programming or server request/response:

>Node's goal is to provide an easy way to build scalable network programs.

An easy way to build scalable network programs, what is the problem of Java or PHP? A LOT I would say, but Node is trying to solve the concurrence problem. Since Java or PHP simply spawns a new thread for every new connection, the maximum number of concurrent connections becomes a bottleneck of the network.

##**NODE**
So how to solve this problem? Node makes the most of JS event-driven feature, insteads of spawning new thread, it refects every connection into an event of Node engine. Acturally, Node is not just a JS library, it's a JS runtime (Google [V8 JS Engine][3]) wrote in C++.

Node's architecure is a module system, you can use NPM to install kinds of modules and type require to include them. Let's see what Node's Hello World looks like :

{% gist 7749475 node1.js %}

Functional Programming is amazing, it passes function as regular argument or even anonymous funtion. This Call-back Based on Event-driven is how Node really works. But the question is, how does Node handle requests without spawning new thread. 

Check out this [post][4], Node passes a function when it creates server, it invokes this function whenever a request comes. I will try to explain the design of event-driven in Node:

First let's see how block happens：

{% gist 7749475 node2.js %}

After the process execute the query statement, it will hang-up to wait the query finish. Apparently it will block when the query is crazily complecated or there are too many query processes running.

How event-driven solve this problem:

{% gist 7749475 node3.js %}

Instead of hanging up and waiting, the process keeps on running next statements after executing the query statement, and it will invoke the function automatically as soon as query is done.

##**DEMO**
There are so many tutorials about Node.js on Google, I roughly learned it according to this [book][5]. Besides, the sleep function in JS is really interesting:

{% gist 7749475 node4.js %}

I wrote some demos, implemented a efficient file upload function with very few codes. I have to say, Node is powerful but hard to understand. This is my beginning, I think I should read more books about functional programming if I want to become a good Node developer.

Keep on learning:)

[1]:http://nodejs.org/
[2]:http://en.wikipedia.org/wiki/Event-driven_programming
[3]:http://code.google.com/p/v8/
[4]:http://debuggable.com/posts/understanding-node-js:4bd98440-45e4-4a9a-8ef7-0f7ecbdd56cb
[5]:http://www.nodebeginner.org/index-zh-cn.html