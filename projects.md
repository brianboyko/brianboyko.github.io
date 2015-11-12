---
layout: default
title: Projects
omit_title_suffix: true
cssid: projects
---

{% capture digiquiz_head %}    
[Digiquiz](http://dgqwz.herokuapp.com)
{% endcapture %}

{% capture digiquiz_desc %}    
Keep students engaged in class through interactive educational gameplay
{% endcapture %}

{% capture digiquiz_source %}
[Source](https://github.com/squarepegs/MKS21-thesis)
{% endcapture %}

{% capture digiquiz_image %}
<img src="images/digiquiz.png" width="100%" />
{% endcapture %}

{% capture digiquiz_video %}
[Video](https://www.youtube.com/watch?v=djVlG4gGOp4)
{% endcapture %}

{% capture digiquiz_main %}

**The problem: Student Engagement**

Teachers today have an impossible problem: keeping students engaged while preparing them adequately for common core standardized testing. Traditional "edutainment" games (Reader Rabbit, Carmen Sandiego, et. al.) are usually solo endeavors and teach only what the software has programmed.

We wanted a system that: A) Allowed the whole class to get involved, B) Allowed the teacher to specify or amend curriculum.

DigiQuiz is a mobile-enabled, real-time question-and-answer platform that keeps students engage in class through interactive educational gameplay. (In other words, it plays Jeopardy).

Teachers control the game from a device or laptop, while students can buzz in.  Teachers can then see who buzzed in first. Students can also leave live feedback on how difficult they found the question, giving them real-time data into what subjects the class needs the most review on.

**Tech Stack:**

* MongoDB
* Express.js
* Socket.IO
* React.js 
* Node.js
* Materialize.css

{% endcapture %}

{% capture digiquiz_team %}
**"Square Pegs"**

* Brian Boyko (Product Owner)
* Juan Sierra (Project Manager)
* Peter Do (Full-Stack Developer)
{% endcapture %}






{% capture speak_head %}    
[Speak](http://spkr.herokuapp.com)
{% endcapture %}

{% capture speak_desc %}    
Feedback for Public Speakers
{% endcapture %}

{% capture speak_source %}
[Source](https://github.com/stacks-on-stacks/spkr)
{% endcapture %}

{% capture speak_image %}
<img src="images/spkr.png" width="100%" />
{% endcapture %}

{% capture speak_main %}

**The problem: Legacy Project**

This was a legacy project - we were given a half-developed greenfield project from another team, and we were asked to add features. 

Originally, the project was able to gather data and display it, but we felt that there were some significant limitations. Specifically, the original app had nine categories hard-coded into the system, we added the ability to add and remove categories both stored on the database and displayed via the data visualization library, D3.

We allowed for evaluators to leave custom feedback for the form, and we made the site design responsive using Bootstrap.css. 

**Tech Stack:**

* MongoDB
* Express.js
* Angular.js
* Node.js
* D3.js
* Bootstrap.css

{% endcapture %}

{% capture speak_team %}
**Stacks-on-Stacks**

* Brian Boyko (Project Manager) 
* Vaishnavi Reddi (Product Owner) 
* Peter Do (Front-End Developer) 
* Dan Moser (Full-Stack Developer) 
* Josh Stevens (Full-Stack Developer)

{% endcapture %}






{% capture wwtbam_head %}    
[WWTBAM](https://wwtbam.herokuapp.com/)
{% endcapture %}

{% capture wwtbam_desc %}    
Play "Who Wants To Be A Millionaire" in real time.
(36 Hour Coding Challenge)
{% endcapture %}

{% capture wwtbam_source %}
[Source](https://github.com/brianboyko/MKS-solo)
{% endcapture %}

{% capture wwtbam_image %}
<img src="images/wwtbam.png" width="100%" />
{% endcapture %}

{% capture wwtbam_main %}

**The problem: Real-Time Interaction and Asynchronous events**

This 36 hour solo coding challenge was the culmination of the first half of the MakerSquare advanced software engineering immersive. 

Multiple users can go to the website, one of them gives a command to start the game, and the users then answer questions, and chat and play with each other. Correct answers give ten points; the first correct answer the server recieves gets a bonus five points. 

More of a proof of concept than an actual app, it nevertheless was well recieved.  

**Tech Stack:**

* Node.js
* FS.js
* Socket.IO
* jQuery

{% endcapture %}

{% capture wwtbam_team %}
Solo project.

{% endcapture %}








{% capture thisguy_head %}    
[thisguy](http://sendthisguytocodecamp.com)
{% endcapture %}

{% capture thisguy_desc %}    
Crowdfund Coding Bootcamp
(pre-MakerSquare)
{% endcapture %}

{% capture thisguy_source %}
[Back-End Source](https://github.com/brianboyko/thisguy-checkout)
[Front-End Source](https://github.com/brianboyko/frontend-thisguy)
{% endcapture %}

{% capture thisguy_image %}
<img src="images/thisguy.png" width="100%" />
{% endcapture %}

{% capture thisguy_main %}

**The problem: Paying for code camp through Crowdfunding**

In order to improve my skills as a developer (and to prove that I had the capacity to *become* a software engineer, I created a crowdfunding website based on what I had learned from previous projects - specifically, the Mayday.US site. 

My plan was to raise money to pay for at least the deposit to go to MakerSquare (or similar camp), after which I would pay forward the amount I raised to a scholarship fund.  The site raised $2500, enough to put the deposit down on MakerSquare's tuition. Towards that effort, I intend to pay $2600 towards the recipient of the [Science Ambassador Scholarship](http://www.scienceambassadorscholarship.org/) in order to pay for books and or a laptop. 

**Tech Stack:**

* PostgreSQL
* Jekyll
* Stripe

{% endcapture %}

{% capture thisguy_team %}
Solo project. 
{% endcapture %}






{% capture consoley_head %}    
[Consoley](http://brianboyko.github.io/consoley/)
{% endcapture %}

{% capture consoley_desc %}    
Debian command-line installer script generator.
(pre-MakerSquare)
{% endcapture %}

{% capture consoley_source %}
[Source](https://github.com/brianboyko/consoley)
{% endcapture %}

{% capture consoley_image %}
<img src="images/consoley.png" width="100%" />
{% endcapture %}

{% capture consoley_main %}

**The problem: Automate apt-get commands after fresh install on debian-based Linux**

My first real work with javascript for web development, Consoley was another "prove to myself I can do this" project with javascript.  It is very simple: Choose a distribution, then choose the programs you want to install from a generated list - as checkmarks are checked and unchecked, the install script changes, and when you're satisfied, you just copy and paste into the console.  

This project would have been a lot easier had I known what jQuery was at the time I was developing it.  As such, the site is pure vanilla, client-side Javascript.  

**Tech Stack:**

* Vanilla client-side Javascript

{% endcapture %}

{% capture consoley_team %}
Solo project. 
{% endcapture %}


{% include projects.html %}