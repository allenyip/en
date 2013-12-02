---

title: Wechat Official Accounts

layout: post

---
These days I am busy doing meaningless things in my lab, besides I am also writing an awful PHP project.   
The only thing interest me is developing a Wechat Official Account, now I'm writing this post to record the details.

The Wechat 5.0 version separated the official accounts into service accounts and subscription accounts, single developer can just apply the subscription account. After uploaded a stupid ID card picture I successfully registered an account. Wechat Official Accounts offer two kinds of modes for developers, edit mode and develop mode. As a sad coder I chose the develop mode decisively.  

Ew... It said that I should become developer first, since this project is developed on SAE, I constructed a new application on SAE and uploaded a php file which is provided by Wechat like this:  

{% gist 7749268 %}

I typed in the URL and Token, verification succeed. But the subscription account have no permission to custom menus, luckily, Wechat offers testing accounts to developers. After submiting my phone number I got a testing account.

I'm not familiar with PHP, so I copied some demos on [Github](http://github.com/), thanks to open source, here is the test result: 

![wechatrobot](https://dl.dropboxusercontent.com/u/36470533/Photos/wechatrobot.jpg)

Wechat has little interfaces now, but with link the Wechat app can open HTML5 pages directly. It's easy for us develop official accounts, but in these thousands of accounts there is no killer account. 

Full of gossip is saying that wechat team has many problems, as a concerned stranger, this is really not my business. God bless Wechat.