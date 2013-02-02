---

title: A Little BUG

layout: post

---
![BUG Email][1]

Blogging with Jekyll is really cool. After reading "[Blogging Like A Hacker][4]", an article wrote by [Github][2] co-founder [Tom Preston-Werner][3], I built this blog and bought a domain immediately. However, blogging with Jekyll is also very SABIXI, and it really makes me frustrated when Github send me a BUG email after I push my post.

This BUG is really little and easy, but took me some time to deal with it, because:

* I didn't post for a very long time. - and it sucks
* Jekyll Server of Github is updated. - and I didn't know
* I want to add Google Analytics(GA) service in my website. — even nobody comes here

So I added the GA code and committed a new post, then I received the first BUG email from Github, and of course, I thought it was because of the GA service, but it made no differences after I modifying the codes, changing the config, removing the GA service... I did lots of things in vain. Eventually, I typed jekyll --safe to debug locally and found this error:

>Liquid Exception: undefined method 'xmlschema' for nil:NilClass in default

I googled it and solved the error, it was because the filename of the website about file didn't match CCYY-MM-DD-title mode, so I deleted the date of that file and commited sucessfully.

I was killing this little bug till mid-night, and now I'm writing this post to tell myself:

* Do not take things for granted or consider yourself always right.
* Do not be lazy, write MORE articles.
* Do not stay up so late, go to sleep NOW!

[1]:http://i.imgur.com/dlD2Ox3.png
[2]:http://github.com
[3]:http://tom.preston-werner.com/
[4]:http://tom.preston-werner.com/2008/11/17/blogging-like-a-hacker.html