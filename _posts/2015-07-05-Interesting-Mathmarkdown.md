---
title: "Interesting Math"
layout: post
date: 2015-07-05 19:22:25
---


Because I want to get working on anticorruption issues as soon as possible, I'm applying for the next cohort of MakerSquare, which starts on July 20th.  I have to pass a technical interview (this July 8th) in order to be acepted, but if I am I have to pay up-front for the education (unlike other schools, which give you until the last day of the course to get the money together.)<!-- break -->

So, obviously, it would be awesome if I could meet the goal: $17,000, in the next two weeks. ($16,920 for tuition, $80 for bus fare to downtown). I haven't really begun my social media push, because I didn't want to compete for attention with the work of the NHRebellion this July 4th, so it's possible that will work.  

However, if we get *close*, I do have options available which will allow me to attend, and I'll keep the crowdfunding campaign open until the cohort concludes on October 20th.  

The reason why I want to get started so quickly is because, quite frankly, the sooner I learn to code some realy cool apps, the sooner that information can be used to fight corruption. 

For example, take phi. 

![From Wikipedia](https://upload.wikimedia.org/math/3/1/1/3111468a5927b94bc1fa66a2ff2646f9.png)

That's phi, and it's written in code like this:

{% highlight javascript %}
	function phi(table) {
	  return (table[3] * table[0] - table[2] * table[1]) /
	    Math.sqrt((table[2] + table[3]) *
	              (table[0] + table[1]) *
	              (table[1] + table[3]) *
	              (table[0] + table[2]));
	}
{% endhighlight %}

Why is that important in fighting corruption?  

Well, we've got all sorts of data from various transparency laws - projects like OpenSecrets, organizations like the Sunlight Foundation - they will tell you who gave what to whom and how much.  

One of the arguments of Citizens United v. FEC's majority opinion is that money doesn't corrupt politics.  **With science, you could use phi to calculate the correlation between a group giving money to a candidate and that candidate's support of the law.**  It doesn't prove causation, naturally, but if you could demonstrate beyond a reasonable doubt that money influences politics - and show people *exactly*, and *quantitatively* how much it does - then you strengthen the argument for reform.  

That's the kind of thing I'd like to work on.  If I knew how - which is the whole point of me going to code camp.  

In the meantime, there's something else you can do - if you have a website, you can embed my new widget.  It looks like this: 

<iframe width="420px" height="310px" src="http://sendthisguytocodecamp.com/embed.html"></iframe>

You can get your own by embedding this code:

{% highlight html %}
<iframe width="420px" height="310px" src="http://sendthisguytocodecamp.com/embed.html"></iframe>
{% endhighlight %}

Thank you once again for all your help!  

-- Brian Boyko, a.k.a. "this guy."

P.S.: Feel free to send me any ideas you have for web application projects! I'll see what I can do to code them!  