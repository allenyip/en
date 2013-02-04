---

title: Prolog, Logic Programming and Programming Paradigm

layout: post

---
Recently I did a research about Prolog language in my Artificial Intelligence class. I finally got a chance to see what logic programming reallys is. (No pressure, no power, what a lazy pig...) At the very start I just want to write something about Prolog, but it seems like I have so many things to talk about, so this post ends up with the title of Prolog, Logic Programming and Programming Paradigm.   

---

##**Programming Paradigm**

Class-based and Prototype-based, declarative programming and imperative programming, Object-oriented and procedure-oriented... all these programming paradigms are so disordered and complicated, but the Wikipedia has a brief definition of Programming Paradigm:  

>A programming paradigm is a fundamental style of computer programming.

Bazinga, I'm really not into these methodology things, so I found this [Principal Programming Paradigms][1] chart made by Peter Van Roy：

![Principal Programming Paradigms][2]

From this chart we know that it's usual that a single language supports kinds of programming paradigms, which is not so cool for simplists. Obviously this chart doesn't specify every paradigm, I quoted it because this kind of colorful charting looks really smart and the sentence under the title says: 

>More is not better (or worse) than less, just different.

I can't agree it any more, at the same time I can't help to add something behind this short sentence: 

>but less is beautiful.

Anyway, I googled it and picked up four main programming paradigms from the [Wikipedia List][3]: 

* Imperative Programming
* Functional Programming
* Object-oriented Programming
* Logic Programming

note: about [computational model][4]，functional programming is besed on  lambda calculus, logic programming is based on first order logic, and object-oriented and imperative programming are based on Turing machine.

##**Imperative Programming**

>First DO THIS and next DO THAT

Follow the ideas of [Von Neumann][5], strict like training discipline, representative languages are Fortran, Pascal and C.

##**Functional Programming**

>Evaluate an expression and use the resulting value for something

Based on mathematics and theory of functions, simpler and more clean than the imperative one. lan The reason is that the paradigm originates from a purely mathematical discipline: the theory of functions, representative languages are Lisp, Erlang and Haskell. (Seems like functional programming is becoming popular...[WHY][6]）

##**Object-oriented Programming**

>Send messages between objects to simulate the temporal evolution of a set of real world phenomena

Most polular paradigm in recent decade, bases on Object concepts, supports encapsulation, inheritance and polymorhism, representative languages are Smalltalk, C++ and Java.

##**Logic Programming**

>Answer a question via search for a solution

Dramatically different from the other three main programming paradigms, based on first order logic, most applied in Artificial Intelligence, representative languages are Prolog, Mercury and Logtalk.

Logic Programming sloves problem by setting rules rather than setting steps, the results are generating by matching lots of facts and rules. Actually, the implementation of logic programming is so simple that many other languages can do, but they should spend more execution efficiency and computing cost than Logic Programming Language. As an example, next I will show you how Prolog works.

##**PROLOG**

Prolog(Programming in Logic) was first conceived by a group around Alain Colmerauer in Marseille, France, in the early 1970s and the first Prolog system was developed in 1972 by Colmerauer with Philippe Roussel. Still, it widely used in many Aritificial Intelligence like Nature Language Processing, Expert System, etc. I really don't like rebuild wheels, so you guys can click [here][7] to check the Prolog tutorial "Learn Prolog Now!" wrote by Patrick Blackburn and his partners, the development tool I strongly recommend [SWI-Prolog][8], an little fast opensource Prolog tool.

Prolog is simple but effcient, it takes just two lines to solve the hanoi problem:

<pre><code class="prolog">
move(1,X,Y,\_):-write('Move top disk from '),write(X),write(' to '), write(Y), nl.   
move(N,X,Y,Z):-N>1,M is N-1,move(M,X,Z,Y),move(1,X,Y,\_),move(M,Z,Y,X). 
</code></pre>

I will make an simple example to show the three statements that Prolog has: fact, rule and result.

Assume we have a family tree like this:

![Family Diagram][9]

Define the facts and rules in family.pl like this:

<pre><code class="prolog">
/* facts */
male(baba).
male(yeye).
female(nainai).
female(mama).
male(wo).
father(yeye,baba).
father(baba,wo).
mother(nainai,baba).
mother(mama,wo).

/* rules */
grandfather(X,Y):-father(X,Z),father(Z,Y).
grandmother(X,Y):-mother(X,Z),father(Z,Y).
daughter(X,Y):-parent(X,Y),female(Y).
son(X,Y):-parent(Y,X),male(X).
parent(X,Y):-father(X,Y);mother(X,Y).
ancestor(X,Y):-parent(X,Y).
ancestor(X,Y):-parent(X,Z),ancestor(Z,Y).
</code></pre>

The results  begin with " ?- ", query like this :

![Prolog Query][10]

What's more, we can also use prolog to solve NLP or Expert System stuff, the basic mechanism is nearly the same. Here is my presentation:

<iframe src="http://www.slideshare.net/slideshow/embed_code/16338774" width="597" height="486" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC;border-width:1px 1px 0;margin-bottom:5px" allowfullscreen webkitallowfullscreen mozallowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="http://www.slideshare.net/allenyip/prolog-16338774" title="Prolog" target="_blank">Prolog</a> </strong> from <strong><a href="http://www.slideshare.net/allenyip" target="_blank">allenyip</a></strong> </div>

[1]:http://www.info.ucl.ac.be/~pvr/paradigmsDIAGRAMeng108.pdf
[2]:http://i.imgur.com/oACpKEi.png
[3]:http://en.wikipedia.org/wiki/Category:Programming_paradigms
[4]:http://en.wikipedia.org/wiki/Computational_model
[5]:http://en.wikipedia.org/wiki/John_von_Neumann
[6]:http://www.cse.chalmers.se/~rjmh/Papers/whyfp.html
[7]:http://www.learnprolognow.org/
[8]:http://www.swi-prolog.org
[9]:http://i.imgur.com/ekXPwFP.png
[10]:http://i.imgur.com/PX5NBlR.png