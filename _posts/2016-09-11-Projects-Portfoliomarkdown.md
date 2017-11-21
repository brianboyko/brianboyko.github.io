---
title: "Projects/Portfolio"
layout: post
date: 2016-09-11 16:37:51
---
* [Instagram Data Miner](#instagramdataminer)
* [Can You Hear Us.IS](#canyouhearus)
* [MathPanel for Mathcraft](#mathpanel)
* [Reduxify](#reduxify)
* [Fancy Fizzbuzz](#fancyfizzbuzz)
* [Whichlang](#whichlang)
* [Digiquiz](#digiquiz)
* [Speaker](#speaker)
* [WWTBAM](#wwtbam)
* [Send This Guy To Code Camp](#sendthisguytocodecamp)
* [Mayday.us](#mayday)


---

<a name="instagramdataminer"></a>
## Instagram Data Miner

2016 Q4 - Code Challenge 

**A code-challenge assignment to search Instagram's API by tag name and date range -- when Instagram does not provide that functionality in their API.**

![Pixlee Code Challenge](http://i.imgur.com/4KSjuUq.jpg)

As Instagram doesn't provide the ability to search by date, this code challenge focused on how to provide that ability to clients. 

It should be noted that this turned out to be an "impossible task" - in the sense that you can only search for the latest images by tag and paginate through, 20 images at a time. 

However, that's exactly what I did - given an email address, tag, and date range, the site will gather all the matching pictures in that time frame by literally starting at the latest tags and making subsequent requests until such time as the API is complete. 

This is not by any means a workable solution -- for one, Instagram limits tokens to 500 (hobbyist) and 5000 (business) requests per hour, limiting the maximum number of photos you could take to 10,000 per hour.  

This was assigned to be "two to three days of work" but the assignment was clearly over-scoped - still, anything worth doing is worth doing well. 

[SOURCE](https://github.com/brianboyko/pixlee-code-challenge)
[DEPLOYMENT](https://pixleecodechallenge.herokuapp.com/)

#### Tech Stack:

* React
* Redux
* React-Redux-Router
* Instagram API
* Postgres
* Webpack
* Mocha/Chai
* Nodemailer
* Knex.js
* Node
* Express.js
* Material-UI
* Heroku

---

<a name="canyouhearus"></a>
## Can You Hear us?

2016 Q4 - Iceland Constitutional Society

**Site to raise funds and advocate for the establishment of the new Icelandic constitution.**

<img src="http://i.imgur.com/f1vz6TJ.jpg" width="600px"/>

Another project I worked on with @lessig, CanYouHearUs.is is a bilingual (English and Icelandic) site which uses React/Redux to quickly and instantly switch languages without having to reload the page. 

One neat feature - though it defaults to Icelandic, the site will detect if the visitor is from an English-predominant country and automatically switch the language to English if that's the case. 

It also integrates with Stripe's Checkout API in order to collect donations (in USD), and MailChimp's API for managing mailing lists. Finally, it keeps track of donations and subscriptions in a Mongo-based database.  

The big challenge with this site was timing - by the time I had received the assignment, the election in Iceland was imminent, this required a lot of "shooting from the hip" but still managed to create a site that handled well, through a Heroku deployment.  

[SOURCE](https://github.com/brianboyko/canyouhearusis)

[DEPLOYMENT](https://www.canyouhearus.is/)

#### Tech Stack:

* React
* Redux
* MongoDB w/ Native Driver
* Node
* Express.js
* Webpack
* Stripe API
* Material-UI
* Heroku
* SSL
* Cloudflare

---

<a name="mathpanel"></a>
##MathPanel for Mathcraft
2016 Q2 - Cycorp

**Application interface for AI-based edutainment game**

<iframe width="560" height="315" src="https://www.youtube.com/embed/7Dk1ZZq09mk" frameborder="0" allowfullscreen></iframe>

Mathcraft is one of Cycorp's experimental projects, and I was put in charge of improving the UI and adding features to the interface that deals with how users solve math problems.  One problem that we had was that (due to the nature of AI) the back-end was stateful and it was impossible to recreate the user experience based on reproduction notes from testers, leading to bugs taking orders of magnitude longer to find and fix. 

To solve this problem, I redesigned the site to use Redux, a functional state manager designed to work with the React stack.  Redux, being built with functional programming in mind, will always produce the exact same output given the exact same input. What I did was ensure that every change to the application's state was registered as a "redux action".  By keeping a log of those actions in memory, I could easily recreate the user experience up to and including the behavior that resulted in the bug.  

Furthermore, since these actions were simple Javascript objects, I was able to use Express, Node, and Mongo DB to create a system where, with one button click, a tester creates a report of all the actions that have occurred during his/her session, then sends that information both to the Mongo database and (using JIRA's API) automatically creates a JIRA issue.  A little cross-referencing magic allowed me to create an interface where developers could recreate any play session by simply entering the name of the JIRA issue in a form on the site.  

#### Tech Stack:

* React
* Redux
* MongoDB w/ Native Driver
* Node
* Express.js
* Amazon Web Services
* JIRA API
* Material-UI

---

<a name="reduxify"></a>
##Reduxify [NPM Module]
2016 Q2

```text
npm install --save reduxify
```

**Reduxify is a small NPM module utility designed to quickly connect your react components to redux stores.**

Mostly for use in development operations, with the Reduxify library, one line of code maps all your actions and all reducers to the props of your component.

For those using react-redux, this saves a great deal of time writing boilerplate during development, as one does not need to remember which actions and reducers go with each component.  

To move from development to production, simply specify which redux keys you wish to have connected to each component (this prevents unnecessary re-rendering of React components when unrelated props change.) 

* You can access actions via "this.props.actions.NAME\_OF\_ACTION"
* You can access keys to the redux store via "this.props.NAME\_OF\_KEY"
* You can access the dispatch via "this.props.dispatch," (perfect for if you need to pass in dispatch as a callback parameter)
* You can access any other methods you provide in the 4th parameter via "this.props.NAME\_OF\_METHOD"

[SOURCE](https://github.com/brianboyko/reduxify)

[NPM entry](https://www.npmjs.com/package/reduxify)

#### Tech Stack:
* ES5
* React
* Redux
* Published as NPM Module

####Co-Contributor: 
* Johnathan Sun

---

<a name="fancyfizzbuzz"></a>
##Fancy Fizzbuzz
2016 Q1

![Fancy Fizzbuzz](http://i.imgur.com/DxL4ovZ.png?1)

**Coding challenge: Take the simple "Fizzbuzz" application and over-engineer the heck out of it.**

There really wasn't a challenge, per se, in creating Fancy Fizzbuzz - being able to do a Fizzbuzz on a whiteboard is pretty much a prerequisite for all engineering jobs. 

So when I was asked to do one as a coding challenge, I took it as an opportunity to show off my professional, rather than algorithmic, skills. 

Fancy Fizzbuzz: 

* Takes command line parameters
* Takes custom modulos (instead of 3 and 5)
* Takes custom outputs (instead of "Fizz" and "Buzz")
* Can read from, or output, to a file using Node's built in FS functionality.
* Handles integers larger/smaller than &#177; (2<sup>53</sup> - 1) through the use of the bigInteger library



[SOURCE](https://github.com/brianboyko/fancyFizzbuzz)

---

<a name="whichlang"></a>
##Whichlang
2015 Q4

**Mobile App Development Coding Challenge**

![Whichlang App](http://brianboyko.github.io/images/ionic.png)

This was a coding challenge for a “MEAN Stack developer position” at a Austin-based custom app development firm. Because the company specializes in software for mobile app development, I was asked to use Ionic Framework (which itself is built on top of Angular).

The assignment was to create a buzzfeed-like personality test (I chose “Which programming language should you study”), which stored user’s login information to a MongoDB, was deployable on Heroku (including DB), and could be packaged, via Cordova, to an Android *.apk file. Users should get an e-mail sent to their address with their results.

Even though I had never worked with Ionic or Cordova before, I considered it a point of pride that I was able to understand them quickly and apply what I learned.

[SOURCE](https://github.com/brianboyko/whichlanguage)

#### Tech Stack:

* MongoDB w/ native driver
* Express.js
* Angular.js
* Node.js
* Ionic Framework
* Cordova
* NodeMailer (for email capabilities)

---

<a name="digiquiz"></a>
##Digiquiz
2015 Q4
![Digiquiz](http://i.imgur.com/p4elQNA.png?1)
**Keep students engaged in class through interactive real-time educational gameplay**

Teachers today have an impossible problem: keeping students engaged while preparing them adequately for common core standardized testing. Traditional “edutainment” games (Reader Rabbit, Carmen Sandiego, et. al.) are usually solo endeavors and teach only what the software has programmed.

We wanted a system that: A) Allowed the whole class to get involved, B) Allowed the teacher to specify or amend curriculum.

DigiQuiz is a mobile-enabled, real-time question-and-answer platform that keeps students engage in class through interactive educational gameplay. (In other words, it plays Jeopardy).

Teachers control the game from a device or laptop, while students can buzz in. Teachers can then see who buzzed in first. Students can also leave live feedback on how difficult they found the question, giving them real-time data into what subjects the class needs the most review on.

#### Team: Square Pegs
* Brian Boyko (Product Owner)
* Juan Sierra (Project Manager)
* Peter Do (Full-Stack Developer)

[SOURCE](https://github.com/squarepegs/MKS21-thesis)

####Tech Stack:

* MongoDB w/ Mongoose
* Express.js
* Socket.IO
* React.js
* Node.js
* Materialize.css

---

<a name="speaker"></a>
##Speaker
2015 Q3 - *Legacy Project* 
![Speaker](http://i.imgur.com/WSUndHv.png)
**Feedback for public speakers**

This was a legacy project - we were given a half-developed greenfield project from another team, and we were asked to add features.

Originally, the project was able to gather data and display it, but we felt that there were some significant limitations. Specifically, the original app had nine categories hard-coded into the system, we added the ability to add and remove categories both stored on the database and displayed via the data visualization library, D3.

We allowed for audience members to leave custom feedback for the form, and we made the site design responsive using Bootstrap.css.

Tech Stack:

#### Team: Stacks-On-Stacks
* Brian Boyko (Project Manager)
* Vaishnavi Reddi (Product Owner)
* Peter Do (Front-End Developer)
* Dan Moser (Full-Stack Developer)
* Josh Stevens (Full-Stack Developer)

[SOURCE](https://github.com/stacks-on-stacks/spkr)

#### Tech Stack: 
* MongoDB
* Express.js
* Angular.js
* Node.js
* D3.js
* Bootstrap.css

---

<a name="wwtbam"></a>

## WWTBAM 
2015, Q3 - *36 Hour Solo Coding Challenge*

![WWTBAM](http://i.imgur.com/3RVOhvD.png)

**Trivia game featuring real-time multiplayer interaction using Websockets.**

This 36 hour solo coding challenge was the culmination of the first half of the MakerSquare advanced software engineering immersive.

Multiple users can go to the website, one of them gives a command to start the game, and the users then answer questions, and chat and play with each other. Correct answers give ten points; the first correct answer the server recieves gets a bonus five points.

More of a proof of concept than an actual app, it nevertheless was well received.

[SOURCE](https://github.com/brianboyko/MKS-solo)

#### Tech Stack:

* Node.js
* FS.js
* Socket.IO
* jQuery

---

<a name="sendthisguytocodecamp"></a>
## SendThisGuyToCodeCamp
2015, Q3

![SendThisGuyToCodeCamp](http://brianboyko.github.io/images/thisguy.png)

**A crowdfunding site without the 5% overhead of GoFundMe to pay for my deposit to MakerSquare**

In order to improve my skills as a developer (and to prove that I had the capacity to become a software engineer, I created a crowdfunding website based on what I had learned from previous projects - specifically, the Mayday.US site.

My plan was to raise money to pay for at least the deposit to go to MakerSquare (or similar camp), after which I would pay forward the amount I raised to a scholarship fund. The site raised $2500, enough to put the deposit down on MakerSquare’s tuition. Towards that effort, I intend to pay $2600 towards the recipient of the Science Ambassador Scholarship in order to pay for books and or a laptop.

* [FRONTEND SOURCE](https://github.com/brianboyko/frontend-thisguy)
* [BACKEND SOURCE](https://github.com/brianboyko/thisguy-checkout)

####Tech Stack: 

* PostgreSQL
* Heroku
* CSS Animations
* Client-Side JS
* Jekyll
* Sinatra.rb
* Stripe API

---

<a name="consoley></a>
## Consoley
2015, Q3 - Debian command line installer script generator

![Consoley](http://brianboyko.github.io/images/consoley.png)

**Automate apt-get commands after fresh install on debian-based Linux**

My first real work with javascript for web development, Consoley was another “prove to myself I can do this” project with javascript. It is very simple: Choose a distribution, then choose the programs you want to install from a generated list - as checkmarks are checked and unchecked, the install script changes, and when you’re satisfied, you just copy and paste into the console.

This project would have been a lot easier had I known what jQuery was at the time I was developing it. As such, the site is pure vanilla, client-side Javascript.

* [SOURCE](https://github.com/brianboyko/consoley)
####Tech Stack: 

* Vanilla client-side Javascript

---

<a name="mayday"></a>
## Mayday.US
2014, Q2 - Crowdfunding site for the Mayday PAC

<iframe src="https://player.vimeo.com/video/93299391" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

**Build crowdfunding infrastructure which can take conditional payments and comply with FEC regulations for 501(c)4 PACs**

Stuck in a pinch, Harvard Law Professor and activist, Laurence Lessig asked me to take a shot at building a web application for his Mayday PAC - an attempt to fight money in politics by crowdfunding a moneybomb big enough to shift the tides of elections in favor of reformers. 

The site would need to conditionally process payments and gather information to comply with 501(c)4 reporting requirements. 

Before this, the most complex code I ever written was HTML/CSS. *"Out of my depth" doesn't begin to cover it.* However, over the two weeks before the deadline, I was able to learn just enough to build and implement a solution that worked. The initial site - a solo endeavor - raised $250K within the first 24 hours. 

Then it crashed. Because I had routed everything through one MySQL database, and it couldn't handle the demand. 

However, this early success lead others to volunteer their technical experience to get the site up and running. In 30 days, we hit our first goal of $1M, in 60 days, we hit our final goal of $6M (with a little help from a well-timed tweet from George Takei).  

This was the project that had me consider software development as a career - as many of the people I worked with told me that I picked things up quickly and had a talent for the work. 

Also, through Mayday PAC, I got to work (admittedly not directly) with Joseph Gordon-Levitt, Steve Wozniak, and Jason Alexander. 

[SOURCE](https://github.com/brianboyko/Mayday_Late_Version)

#### Team: The First Responders
* Aaron Lifshin - CTO
* Brian Boyko - Deputy CTO
* J.T. Olds - First Responder Engineer
* David Harrison - First Responder Engineer
* Hunter Freyer - First Responder Engineer
* Adam Pickering - First Responder Engineer

####Tech Stack:

* WordPress
* PHP
* Stripe API
* CSS
* Jekyll