---
title: "How's it been?"
layout: post
date: 2016-02-10 06:00:00
---


Been a long time since the last update, partially because, well, I've been employed.  Currently, I'm at Cycorp, working on the UI/UX for the mathmatics portion of the [Mathcraft](http://www.cyc.com/mathcraft/) game we're developing. I can't talk about it much, except to say that it's using react. 

But I did want to talk about some of my sideprojects.  Despite what I said before, I really think I should go back and take another look at Digiquiz.  I think there are a number of things that can be done to improve it - while trying out new technologies to see how they work. 

So, here's what I'm thinking Digiquiz 2 will have:

* Updated Syntax to ES6/7

I especially like the Async/Await functionality in ES7, which makes asynchronous code look like, well, synchronous code.  I believe it was a convention borrowed from C#, and while it requires babel transpiling with polyfills, it is amazing to actually use. 

* Redux

Despite using React as the view, we really did build out an application with a traditional MVC framework; instead of Flux.  Now that I've been working with Flux-like structures a bit more at Cycorp, I'd like to take a look at implimenting Redux, a Flux framework that has features such as hot reloading, state control/undo, etc.  

* Switching from MongoDB to PostgreSQL.  

We only had four weeks to work on Digiquiz. We lost about half our time, and about 40% of our team, due to circumstances beyond our control, so when it came right down to it, some decisions were made because of speed rather than because it fit better.  MongoDB is great. I love it. It is incredibly easy to develop for, and doing things the Mongo way allowed us to rapidly iterate and create new features on the fly - we wouldn't have been able to do that with SQL. 

That said, the data in our database is entirely relational. Since there isn't any time pressure for this rebuild, there isn't any reason not to go with SQL. (Alternatively, if we build this right, we could support both.) 

* Adding additional game modes. 

While being able to play Jeopardy orally is cool, we wanted to include more game modes, such as a multiple choice option, a text-entry option, an "Agree or Disagree" option, etc.  We just didn't have time to build that out. 

* Charts and graphs of student performance.

Another thing we really wanted to add was data visualization of charts and performance.  Sadly, the framework we used, Charts.js, while simpler than D3.js, just wasn't fully featured enough.  Now, there might be more options out there, and it's worth investigating. 

So that's what I've got on the side-project backburner for now. 

Oh, one other thing, I'm helping mentor my friend Chris through FreeCodeCamp. I can't recommend MakerSquare enough, but you need to know some basics going in, and I'm going to help him with the basics of HTML/CSS/JS, at least to the point he understands higher order functions. (I also like to go to the FreeCodeCamp Austin's Sunday meetups at BuzzMill coffee and help people with projects.)