---

title: SAE Kidding

layout: post

---
It has been years since cloud computing becoming popular, many companies released their cloud platform, such as GAE/Azure/EC2/Heroku/Appfog/OpenShift, and SAE/BAE/ACE/TAE, etc. Each company has their own features on languages, services and price. It's hard for developers or buyers to choose a right cloud platform.

To be honest, without the GFW and fast internet speed, all these domestic XAES will not survive for so long, not just because their late for developing, lack of technologies and expensive seveices, the developers is so pissed off by their ugly home pages (GAE is ugly, but it's simple and tidy).   

Alright, this post is about to tell the SAE, I'm putting a PHP project to SAE these days, I've heard many news about Platform Rules Thing, I think most of the rules are not for cloud, it exists because the platform itself can't suport different architectures effectively.

I zipped the codes and uploaded to SAE, errors appear with no surprise.  
First is MySQL, I turned on the MySQL Service and built the database manually, changed the database configuration to this:

{% gist 7749402 sae1.php %}

Then, Memcache, since SAE doesn't support writing files directly, it doesn't support Smarty, too. The template cache should be put into Memcache, so I turned on the Memcache Service and changed the Smarty configuration to this:

{% gist 7749402 sae2.php %}

Now the Storage, SAE say files should be writen into its Storage, so I turned on the Storage Service and set up a domain, changed the file-writing-related codes to this:

{% gist 7749402 sae3.php %}

I'll update other SAE Services later on...