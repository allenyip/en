---

title: Modernizr n HTML5

layout: post

---
Today I checked [HTML5 Boilerplate](http://html5boilerplate.com/) and relight the passion about HTML5, imagine all the browsers in computer/pad/phone can support HTML5 perfectly. 

However, reality is so crue, from the [Baidu Stats](http://tongji.baidu.com/data/browser) browser market share, one in ten of Chinese netizens is still using IE-7.

![Borwser Share](https://dl.dropboxusercontent.com/u/36470533/Photos/browser_201311.jpg)

Is it means that every front-end developers should realize two version, and decide which one to response in every request? Of corse not, we can use [Modernizr](http://modernizr.com/) to solve this problem.

##**MODERNIZR**

Modernizr is an open-source JavaScript library that helps you build the next generation of HTML5 and CSS3-powered websites. We don't need to write codes to check what browser the user use and what HTML5 properties user supports, just focus on functional implementation.

###**DOWNLOAD**

Same to most JS libraries, Modernizr apply two versions, Development and Production. Development version is for rookie like me, it contains full packages. Download it and put it into js folder in my project, open index page and add this codes between `<head>` element:

{% gist 8144258 modernizr1.htm %}

Then add a 'no-js' class in `<html>` element：

{% gist 8144258 modernizr2.htm %}

If Modernizr works regularly, it'll removes 'no-js' and add a 'js' class. Otherwise, the 'no-js' remains. How it works? the answer is not that hard.

###**MECHANISM**

After finish loading Modernizr.js, it automatically generates a Modernizr object including all properties the browser supports. What's more, it adds a new class to `<html>` element. Here is the code of Chrome 31 for Windows:

{% gist 8144258 modernizr3.htm %}

###**DEMO**

For example, an input interface like this:

{% gist 8144258 modernizr4.css %}

If browser support box-shadow, the class in `<html>` contains xshadow, otherwise it contains no-boxshadow, then we can customize the output in CSS file. We don't have to write any JS code in this process.

###**LOADING SCRIPTS**

For these incompatible browsers, Modernizr loads [shim/polyfills](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills) scripts by calling Modernizr.load(). Here is how it works: 

{% gist 8144258 modernizr5.js %}

* test: property you test
* yep: script to load if browser supports
* nope:script to load if browser not supports
* complete: function to run after loading

The advantage of Modernizr.load() is that the scripts loading is depending on the browser, also Modernizr can load external scripts asynchronously. To get more scripts you can visit [yepnope](http://yepnopejs.com/).

###**CONCLUSION**

Modernizr is definitely a great tool for front-end developers, it cuts down codes and works in an really easy way. But as a client JS library, we should try our best to make it smaller and faster, so think twice before you use it. For example, if the user is using IE-6, should we still load scripts for him?