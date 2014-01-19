---

title: Binding User in Wechat

layout: post

---
It's really hard to be a rookie, lately I met a problem when developing Wechat service account: How to bind Wechat user to my system. After googling and googling, I finally find a reliable way - openid.

##**OPENID**

First thing I should know is service accounts can not get user's real Wechat ID, instead, there is a openid between service account and his users, and this openid is unique.

It means that even a user unsubscribe a specific service account hundreds times, his(or their) openid stays the same. So what we need to do is bind this openid into his system account.

###**BINDING**

Refer to an example of CMBC, the binding process is very simple:

1. User sends a request in Wechat app.
2. Server gets his openid and search user table.
3. If nothing found Server return a url with openid to user.
4. User click the url, enter account info to bind.
5, User return to Wechat, finish binding.

###**Security**

Although it's easy to realize, but there is a critical problem should be notice, security problem. Openid is as important as uername and password, here are measures we can do:

* Put openid into session
* encrypt openid
* add a expiration time in url
* add a secret key in url
* pack all the ctgs in url and create a signature

###**CODE**

{% gist 8134128 %}