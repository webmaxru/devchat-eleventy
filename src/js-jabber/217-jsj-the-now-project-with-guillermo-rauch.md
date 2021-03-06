---
layout: layouts/post.njk
title: >
  217 JSJ The Now Project with Guillermo Rauch
date: 2016-06-22 07:00:27
episode_number: 217
duration: 51:49
audio_url: https://media.devchat.tv/js-jabber/JSJ217Now.mp3
podcast: js-jabber
tags:
  - js_jabber
  - podcast
---

## Check out [Newbie Remote Conf](https://allremoteconfs.com/newbie-2016) and get your tickets!

&nbsp;02:24 - Guillermo Rauch Introduction

- [Twitter](https://twitter.com/rauchg)
- [GitHub](https://github.com/guille)
- [Blog](https://zeit.co/blog)
- [ZEIT](https://zeit.co/)
  - [@zeithq](https://twitter.com/zeithq) &nbsp;
- [Cloudup](https://cloudup.com/)
- [Mongoose.js](https://mongoosejs.com/)
- [Socket.IO](https://socket.io/)
  03:07 - [Now: Realtime Node.js Deployments](https://zeit.co/now)04:28 - Key Concepts
- [now-serve](https://github.com/zeit/now-serve)
- [Heroku](https://www.heroku.com/)
  10:22 - Deployment Process14:55 - Getting Started Experience
- [About](https://zeit.co/about)
  17:22 - Technology vs Design20:36 - Running Now vs [npm-install](https://docs.npmjs.com/cli/install)27:17 - Simplicity; SSH and Metrics35:33 - Debugging and Performance37:34 - Security41:44 - What’s Next?&nbsp;Picks
- [Overwatch](https://playoverwatch.com/) (Joe)
- [To Kill A Mockingbird by Harper Lee](https://en.wikipedia.org/wiki/To_Kill_a_Mockingbird) (Jamison)
- [React Rally](https://www.reactrally.com/) (Jamison)
- [Grokking Algorithms: An illustrated guide for programmers and other curious people by Aditya Y. Bhargava](https://www.manning.com/books/grokking-algorithms) (Aimee)
- [Birgitta Böckeler: Born for it](https://martinfowler.com/articles/born-for-it.html) (Aimee)
- [TSA Pre✓](https://www.tsa.gov/tsa-precheck) (Chuck)
- [RIF6 Cube 2-inch Mobile Projector](https://www.amazon.com/RIF6-Projector-120-inch-Portable-Rechargeable/dp/B00QXS8L6I?ie=UTF8&psc=1&redirect=true&ref_=oh_aui_detailpage_o00_s00) (Chuck)
- [Eat That Frog!: 21 Great Ways to Stop Procrastinating and Get More Done in Less Time by Brian Tracy](https://www.amazon.com/Eat-That-Frog-Great-Procrastinating/dp/1576754227) (Guillermo)

### Transcript

**_[This episode is sponsored by Frontend Masters. They have a terrific lineup of live courses you can attend either online or in person. They also have a terrific backlog of courses you can watch including JavaScript the Good Parts, Build Web Applications with Node.js, AngularJS In-Depth, and Advanced JavaScript. You can go check them out at FrontEndMasters.com.]_**

**_[This episode is sponsored by Hired.com. Every week on Hired, they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on JavaScript developers, providing them with salary and equity upfront. The average JavaScript developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with the company or deny them without any continuing obligations. It’s totally free for users. And when you’re hired, they also give you a $1,000 bonus as a thank you for using them. But if you use the JavaScript Jabber link, you’ll get a $2,000 bonus instead. Finally, if you’re not looking for a job and know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept a job. Go sign up at Hired.com/JavaScriptJabber.]_**

**_[Let's face it. Bookkeeping is hard and it's not really what you're good at anyway. Bench.co is the online bookkeeping service that pairs you with a team of dedicated bookkeepers who use simple, elegant software to do your bookkeeping for you. Check it out and get your free trial today at Bench.co/JavaScriptJabber for 20% off today. They focus on what matters most and that's why they're there. Once again that's Bench.co/JavaScriptJabber.]_**

**_[This episode is sponsored by Rangle.io. Rangle's been working with Angular 2 for a long time and they are now putting together an eight-hour, 2-day course designed to help Angular developers learn how to write apps in Angular 2. If you're looking to level up your JavaScript and Angular 2 skills then go to Rangle.io/training and click on the link for Angular 2 training. If you're looking for other training in React or JavaScript, they also have that available at Rangle.io/training.]_**

**CHUCK:&nbsp;** Hey everybody, and welcome to episode 217 of the JavaScript Jabber Show. This week on our panel we have Aimee Knight.

**AIMEE:&nbsp;** Hello.

**CHUCK:&nbsp;** Jamison Dance.

**JAMISON:&nbsp;** Hello.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. Quick shout-out for Newbies Remote Conf coming up in July. We also have a special guest this week and that's Guillermo Rauch.

**GUILLERMO:&nbsp;** Thank you for having me.

**CHUCK:&nbsp;** I hope I said your name right. Do you want to introduce yourself?

**GUILLERMO:&nbsp;** Yeah. So, I'm the founder and CEO of a company called ZEIT. You can all access it through Zeit.co. Before starting this company for hosting JavaScript applications in the cloud I started another company called Cloudup which was acquired by WordPress.com. And before that I was known for different open source projects such as Mongoose.js and Socket.IO and just contributing to a lot of different Node.js projects since we've been using it for many, many years now.

**CHUCK:&nbsp;** Very cool. I think we got you on to talk about Now which is a part of ZEIT's offering. Can you kind of…

**GUILLERMO:** &nbsp; So, Now [inaudible]…

**CHUCK:&nbsp;** Give us the premise there? What it's about, what it does.

**GUILLERMO:&nbsp;** Yeah. Now allows you with just one command, appropriately named 'now' to deploy any JavaScript application to the cloud instantly. So, it doesn't even require for you to set up a repository. It doesn't require for you to set up any instances in the cloud, processes, configuration. You just run 'npm install now' and then 'now' on any directory that you want to instantly serve to the cloud.

**CHUCK:&nbsp;** This project name reminds me a little bit about the problems I have with Google's Go language. [Chuckles] I'm trying to…

**GUILLERMO:&nbsp;** [Chuckles] I'm sure.

**CHUCK:** Put something up for Go right Now.

**GUILLERMO: &nbsp;** I'm sure. Yeah, for some people, so they might remember that there was another npm project called now many years ago. So, we actually, they actually gave us the name in what I think is a very nice handover. Because npm has become somewhat of a DNS system where it's not so easy [inaudible] good names. And in other cases, as we saw with the whole left-pad incident, packages just become outdated. And maybe sometimes the owners decide to remove themselves. We're happy to have had a great name to start this product with.

**CHUCK:&nbsp;** So, I've talked to several people about how they deployed their JavaScript applications and for the most part most folks that I talked to are doing something like basically doing a Git push to set up a Git repository on the server they want to deploy to. They push to that and then it does some kind of rsync or other copy to the running directory. Does Now do something similar to that or is it a completely different setup?

**GUILLERMO:&nbsp;** Yeah, so a few key concepts that I consider very much new, especially new from the [inaudible] of there are new challenges that we have to solve to make this work. One of them is there's no idea of deploying and overriding and existing deployment. Every time you run Now we provision an altogether new server, which means that if you're working on a simple website for example, running Now every time you make a change will give you a bunch of different URLs that you can share with your coworkers to share the state of how things are changing. Or for example if you're talking to someone on Slack and you make a change to your project, you can exchange URLs back and forth of how things are evolving. And later on if that conversation wants to be revisited, all those links would work.

So, I think the very and most important concept is things like rsync, things like 'git push origin', they usually are associated with this idea that you give your project a name and then you constantly redeploy to it. We have a complete different view of this for several reasons. One is like I mentioned, it enhances collaboration when you're able to maintain this immutable ledger of deployments. But also, how you upgrade things to production, how you do the zero downtime deploys is solved by this same system. So, the idea is that when you deploy with Now you get a new URL that has some random characters in it to make it unique and unguessable. And then when you decide, “Okay, it looks good. It's time for this project to go live,” you say, “Okay, I want something-else.now.sh which is a URL that we give you or you want a certain-domain.com to point to this deployment.” So, it almost becomes an inherent way to stage deployments before they become public. So, you can see how it blurs the lines between development and staging and production in a way where everything is production-ready. And when it comes to you want to upgrade something to production, you want to make it live, all you do is you change the pointer at the naming layer for where deployments have to go.

**CHUCK:&nbsp;** So, Now isn't something I'm going to use to deploy to my own server. It's something I'm going to use to deploy to now.sh?

**GUILLERMO:&nbsp;** Right. So, one of our core ideas is that we're trying to blur the lines of the underlying technologies. So, at no point are you choosing to run a Linux or run Windows or you choose an instance type or you say you want to be in a particular region. So, at the same time we're not introducing any new concepts from the perspective of how your application is set up. What we say is if 'npm start' works, then it works with Now. So really, the only convention that we're following is that a package.json has to be in place and that it needs a script to start a project and listen on some HTTP port. And then we can come back to this idea of these are all HTTP services and how we also scale and improve the performance of those.

But the core idea is that even if Now doesn't enter the picture as a service, you still can run all these projects on your computers. You can if you wanted to run it on your own servers. But from the perspective of the cloud deployment, we can now host your container, your application, in the best possible location. So, you run 'now' and we give you a URL back that for your customers is served from the most appropriate location in the world. So, you cannot see how this becomes like a CDN. But CDNs are normally for static files. And in this case for us it's for dynamic code, a subset of which is static files. So, we recently launched a little plugin called now-serve. So, if you just want to serve a static website you can run 'now serve' enter and it also gives you a URL on Now that hosts your static website. So, the best way to think of Now is kind of like if you combined S3 and CloudFront but also you made them run dynamic code. And all of this is so easy to use that it really takes one command.

**CHUCK:&nbsp;** It reminds me a little bit of Heroku.

**GUILLERMO:&nbsp;** Yeah. Heroku I think was a really big inspiration because they started doing a great job for Ruby applications back in the day. Their core thing was we're going to make it easier to host Rails applications. Now, when they had to make the transition to hosting JavaScript applications they actually had to change their entire underlying model because Node applications are known to be long-running processes. So, our whole thing is we're looking at the cloud landscape. We're personally a team of people that have been using Node.js for a very long time.

But now with the advent of the microservice architecture we don't really see a world where for writing a quick Slackbot or writing a small microservice endpoint that shuffles different data around coming from different web services or cloud services, we see that the language that actually makes the most sense, the one that's most commonplace and the language that has the largest community and the largest number of modules. So for us, it's a good way to revisit this whole idea of the cloud, how it works, how easy we can make it with the assumption and opinion, right? It's a strong opinion that JavaScript is the technology that makes this the easiest to write this type of application that people are concerned with writing nowadays.

**CHUCK:&nbsp;** So, the other question I have is if there are deployment steps, so for example I see some systems where people use continuous integration or they just run the build on their own machine. And then they push that up. But then I see other people who are using module loaders and build processes and stuff. And that's all part of their deployment process. So, they write it in TypeScript or ES6 or even in ES5. And then they have some other build process that builds and minifies and does all the other work, runs the tests, and then pushes it out. So, does Now expect you to do all of that stuff on your own? Or can you build other steps into that deployment process?

**GUILLERMO:&nbsp;** That's a great question. Because I just mentioned that if you look at the cloud landscape you can see that we've been creating all this complexity. In fact, deployment processes involved all these different services and connections and steps. So earlier, when I mentioned that as long as you run something on 'npm start' it works for us, there is an important distinction to be made which is a lot of projects run build steps before 'npm start' actually works. So, there are hooks for example like pre-publish, pre-install, post-install, post-publish. There's the 'npm test' command. So, the main idea here is we're not avoiding any of those. So, we actually encourage you to use this this as basically a very broad tool that can run JavaScript projects. So, some JavaScript projects are actually perhaps only running tests.

So, the experience that we set up is when you type in 'now' and then press enter we give you a URL within milliseconds. Usually it takes us 200 milliseconds to give you a URL. So, when you go there what you're going to see is a full-screen Unix terminal that shows you the progress of the tasks and tests and deployment itself. Until 'npm starts' is run and an HTTP server is basically spawned. And then the URL refreshes itself and you see your website or your service. Or maybe not. Maybe it gets stuck there. So, the basic idea is it's a very general platform for running JavaScript code that might have an HTTP server running later on.

And this is very useful because we've seen that a lot of complexity starts to creep up in this build process. One of the ways that we see that is just the most obvious way for every JavaScript developer which is slowness. You run 'npm install' and then you run builds and you might have to wait 10 minutes. I joked recently we're slowly but surely going away from the immediate interpreted world into a world where we have compiler tool chains like GCC and G++ and it takes a long time. And we have caches and we have to invalidate them and we have to rebuild parts of it. And then it's not reproducible on every computer. So, we're trying to make all that extremely quick and reproducible. [Inaudible] is that every time you run 'now' you will see those dependencies being fetched. You'll see those builds happening. And then even if something goes wrong you have that URL and you have that output that you can share also with your coworkers. Like “Look, left-pad is missing. Look at this failed deployment,” and you send them the URL. So, that's very important to us is to acknowledge that there are all these steps before the app actually runs. And we handle them all.

Now, if you already have a continuous integration system, et cetera, it's also very easy for you to use our API that we announced recently and say, “I want to orchestrate a deployment dynamically,” perhaps. So, it's a very versatile tool. You don't have to do it in a particular way. The way that I think it works really well is if you make it so that when you run 'now' everything happens from scratch because that's going to give you the most reproducibility. It makes no assumptions about the state that your computer is in. There are other services where when you push it relies too much on what's on the computer at that particular point. And maybe someone else tries it later and it actually doesn't work at all. And that ties into how we scale this out because we need to make sure that in order to scale it out your code is safe when it run it many, many, many times. So, it's all a very general framework for reproducibility, immutability, and also scalability. We ensure all of those things with this very simple model.

**JAMISON:&nbsp;** So, I think we kind of skipped over to me the coolest things about Now which are just the experience of getting started. I feel like I've heard this about a lot of different things. I go, “It's so easy to get started.”

[Chuckles]

**JAMISON:&nbsp;** But I literally have never seen an easier onboarding process than Now. You install a module, and then you click a link that gets sent to your email, and then you have a server. And it feels like magic.

**GUILLERMO:&nbsp;** Thank you.

**JAMISON:&nbsp;** It's pretty amazing.

**GUILLERMO:&nbsp;** So, we're actually announcing an improvement on this, that will be open source and I think will really help the community at large to make this sort of experiences really, really easy. I can't say too much about it now. But it's something that we looked at in the beginning when I mentioned the experience of running something in the cloud. If you go to our about page the mission of the company is to make cloud computing as easy as mobile computing. Mobile computing I think compared to desktop computing, what it did was something pretty dramatic which is installing and running applications, something that should have been so easy, is now a few taps. But that didn't use to be the case even with the Mac. And we've always associated Apple with great user experience but you had to download these weird packages, double-click them, mount them. They show up as a volume. You drag and drop the application. You go to Applications and then you double-click it. Then came mobile computing and it's just about finding it on the App Store, tapping install and then tapping the icon.

And for us, we're trying to do the same thing but for more ambitious things. Running a JavaScript application is not something that perhaps every single person does today. But if you look at the growth of perhaps coding schools and bootcamps and people that just want to automate things in their daily lives and want to know how the APIs of their favorite services work, now I think we can do a lot to put these technologies in their hands just by making this whole process a lot easier. And that involves making a lot of decisions on behalf of the user, right? Because when you type 'now' you sign up and then you deploy, we've already made a ton of decisions for you like you never decide on an instance type. You never even found out about how things are being scaled on your behalf and things like this. So, [inaudible]

**JAMISON:&nbsp;** Yeah, I didn't have to pick like a plan or a username.

**GUILLERMO:&nbsp;** that really great user experience.

**JAMISON:&nbsp;** Yeah.

**GUILLERMO:&nbsp;** Exactly.

**JAMISON:&nbsp;** It feels like a ton of work has gone into streamlining that.

**GUILLERMO:&nbsp;** Absolutely.

**JAMISON:&nbsp;** That's like an immediate thing that you notice right away. And then your docs are beautiful. They have a pretty unique aesthetic. How much of what you're doing do you feel like is in the technology powering it and the immutability stuff that you were talking about earlier? And how much of it is in the design side where, I don't mean just the UI design but designing the experience of using it? Does that make sense?

**GUILLERMO:&nbsp;** Yeah, that's a great question. Even going back to the mobile computing example. You know, a lot of the technologies that went into the iPhone weren't necessarily new. And a lot of it was a re-purposing the technology that they'd already created in a way that was a lot more user-friendly and meaningful. And for us it's similar because we've created things like Now every time we've set up a new startup to work with Node. We sort of reinvented Now on very slightly different ways. Every time we wanted immediate deployments. We knew that Node is so fast for launching an HTTP server. I see this when you write test cases where every test can spawn a new HTTP server, kill it, and do it 200 times. And the tests take 200 milliseconds. So, a big question that comes up is why isn't deployment as fast when the underlying technology is really fast and really lightweight? So, I think that's the main thing that we set out to do, is we need to make sure that the underlying technologies are properly used so that we have that great experience.

So obviously, we never set out to write a new interpreter for Node.js. We set out to like, what is the best way to deploy with Node so that we can make that happen? The challenges from the technology perspective come in the scalability side of things. So, we have a system that monitors network traffic and resources of your application so that it knows when to scale them or perhaps even when to shut them down completely. Because as I was saying earlier, we want to create this idea that you never worry about launching a new one. You can launch even by mistake, you could launch 200 apps. If you were thinking about the traditional cloud, launching 200 instances would cost you a lot of money. And you would quickly adjust it and worry about it. With us you don't have to, because if the process is inactive from a user interaction perspective then we smartly allocated resources in such a way that your deployments that are actually receiving traffic get more resources to them.

So, there are very new and quite challenging technological requirements associated with this type of user experience. And I think that's why we started with Node.js. Because it satisfied those immediate boot up requirements that we had. It satisfies this great user experience. It's a language that frankly is very friendly to people that are just getting started but also to people that are… Uber uses Node.js. So, we're trying to tackle those new challenges in a way that we narrow the size of the problem to some very well-understood use cases. And then we can provide that user-friendliness that you were just mentioning with this underlying technology that makes it extremely powerful.

**AIMEE:&nbsp;** So, I did have one question. I have a couple but this one was really interesting to me. So, you're probably familiar with this Hacker News thread that a bunch of people are asking questions in. But one question in there was kind of interesting to me. Unless this was misinterpreted, you said that in most cases, that running 'now' was faster than running 'npm install' on your local machine. And I'm just curious if you can talk about how that is.

**GUILLERMO:&nbsp;** Yeah. That's actually one of the things that we've spent a lot of engineering hours in and we continue to do so. Because we're obsessed with this idea that running 'now' should be as fast as, if not faster than localhost. So, it comes down to first of all one of the ideas that I mentioned earlier which is reproducibility. The beautiful thing about Node, if we go back to its creation and npm and the module system is Ryan made the decision to make module installations local to your project's directory.

Now, this right now sounds obvious. There's no other way that you would design a module system. But back in the day there were people that had conflicting versions of globally installed gems and all these other package systems. Or at some point some modules would even be distributed through Apt, Debian's and Ubuntu's package manager. So, you would have a global installation of Perl dependencies or just a really huge mess. So, when Node had the opportunity to revisit the problem they decided to make module installations local. And this solved a really big reproducibility problem because now you could just clone the repository from GitHub, run 'npm install' and it works for everyone. I think later on with the advent of the SemVer symbols and Git URLs and dynamic downloads some of that was a little bit lost. And it made the system a lot harder to optimize for because caching something that's a moving target is not as easily done as caching something that has strict versions of or strict checksums like SHA values. So, the idea is nowadays if you clone a project fresh and you run the, and you install the module that it requires, the caching is very difficult to do. The amount of stuff that it can actually cache on your computer is also a challenge.

Then the number of nested dependencies increases a lot over time which I think personally, I think it's a really great thing. I think a lot of people when the left-pad incident came out saying “Oh, we should inline more of this code.” And I think honestly, that's what a package manager does. It's like a smart copy and paste. Node modules directories are a bunch of files after all. So, it's like doing it on your behalf. So, I don't think tons of nested dependencies are a problem. But I do think that we've made it so that the current state of things is installing takes a lot of time. And again in a very reproducible way. Because if you already have a local Node modules directory and you're adding only one project to it, then that's going to be fast. And to those that have a lot of experience with Node modules actually, they will know when hearing this that it actually doesn't guarantee that the state of that incremental addition that you did, it doesn't guarantee that…

**JAMISON:&nbsp;** Yeah. [Laughs]

**GUILLERMO:&nbsp;** When you run it from scratch it's going to be the same. So, I think Now provides a very good solution to this really big problem in my opinion. Because we've implemented a distributed cache. We implemented a cache that understands SemVer. And on top of all this we cannot get into this habit of starting from scratch. That will rid you of the side-effects that are inherent to this installation system. So, it's all about making it fast but making it also correct. So, of course it's not going to be always faster than localhost if you already have a populated directory of dependencies. But it's always going to be faster in the correct way. And that's the goal that we're pursuing. We're pursuing a world where it's very easy to reason about your deployments and the state that they're in.

And also from the perspective of security audits, right? Because what we're doing is let's say you update a module and you run 'now' again. With how quickly the ecosystem moves, by the time you deploy maybe three dependencies changed. And they introduced security problems. So, by not overwriting your deployment directly and giving you a new URL for it with a new, fresh deployment and download of the dependencies it's a new opportunity for you to review everything again from the perspective of security. So, you can see the logs. You can see what modules ended up where. We have this thing where you can add a 'slash underscore S-R-C', source to any deployment and you see the source code.

So, that for us is going to be where we add all of this other user experience around your code. Your code when run with Now which understands Node.js really well will have all this, it's this idea of the code that will be alive in some sense. And it will be introspectable by you. And it will be auditable by you in a way that I think makes a lot of sense because the underlying package system is very dynamic. But when it comes to upgrading something to production you can't always have such a dynamic system. You need something with stronger guarantees. So, we've found a really great balance between these two worlds of “I want to move really fast but also I want the opportunity to review the code that I'm putting out there.”

**AIMEE:&nbsp;** So, I think some of the confusion there too was I think I was talking about it was always doing a fresh install. But it's not truly a fresh install, right?

**GUILLERMO:&nbsp;** It is from the perspective of the developer. It's always a true fresh install. So, the fact that we do it really fast is I think the really nice piece of this. So basically, the state that it's going to be at, at the end is what you expect it to be. Now, the time that it takes is a lot, lot, lot less. And we can do this again because we understand the underlying structure of package.json and the associated dependencies very well. To the point where again if you compare a fresh npm install on your directory and a fresh Now deployment, now is actually going to win. And over time, it's going to win to the point where it'll… a vast majority of modules that don't need to do anything with binary installations, it's likely that it's going to be completely instant. So, that's precisely what we're very focused on right now.

**JAMISON:&nbsp;** So, it seems like part of the core of Now is simplicity. And so, there are a bunch of things that either maybe I'm just not aware and you do support them but can you SSH into a box or can you run multiple processes? Or is it just you have some JavaScript that runs in one process and that's it?

**GUILLERMO:&nbsp;** So, that's a great question. Because simplicity with a lot of magic I don't think works really well. So, I think simplicity with the ability to over time make sense of the entire system works really well. So, I think that the question is great. As far as SSH I think when people SSH, what they really want is information about the internal state. SSH is sort of a way of getting there that's actually not that great because unless you're very, very, very experienced with the Unix tool chain it's hard to make sense of something like the evolution of memory consumption from the top utility or looking at the proc file system to understand the different underlying networking conditions. So I think what you really want when you SSH is you want information. We're already addressing this with 'underscore source' where you can see the current state of the file system in a way that's actually a lot more user-friendly. Because if you try it out you can highlight a piece of code and link to a coworker and say “Oh look, this is what broke the deployment.” It also answers the question of what is the code that's really right now behind this. It's a question that I have…

**JAMISON:&nbsp;** Yeah, that's…

**GUILLERMO:&nbsp;** I've had myself [on other projects].

**JAMISON:** That's [how] plenty of bugs where I'm not sure what is actually…

**GUILLERMO:&nbsp;** Yeah. Because GitHub, your Git repository keeps evolving right? Or regressing or whatever. But production is working and you want to see exactly what's behind this right now. And the source hyperlink does this for you. So, that's one of the things you do when you SSH, right? You look at the file system and you 'sa', you 'ls', you 'cat', you 'grep'. You find stuff. So, that whole part of it I think is covered and also improved from the user experience and collaboration perspective. Kind of like with GitHub. You link to a line. With Now you can link to even a character within your active deployment.

And then the other metrics are very important as well like understanding logs, understanding memory usage, CPU usage. And these are things that we're working on adding in a very similar manner to how we added the source code support. So for example, the idea of being able to understand what parts of the code are being more used. Because something that's very interesting about Node is Node is a long-running process. Sometimes it's very hard to make sense of what's going [on] inside the process. When the process is this event loop that's alternating every stack between different requests, different database access, different file system reads. So, we want to give you an idea of really what's happening inside. And not just like when you SSH you can look at the outside information. We can also go ahead and link that information all the way to its source code. So, we can tell you like “This is the hot area of your code.” And you can only do this when you control the entire experience of hosting the code and being able to [package] it, right?

So, that's why I mentioned earlier we have such a focus on JavaScript because with JavaScript come very unique requirements and very unique introspection and debugging needs that are very much unique to this stack. They're not very easy to generalize. For example PHP you know that a request comes in, the file is interpreted, and then the response comes out. Whereas in Node you have this long-running process that is simultaneously service tons of different connections. So, this is why we look to answering that SSH problem with tools that actually make sense even more for JavaScript and Node.js.

**JAMISON:&nbsp;** Sounds pretty rad, the performance visualization at the code level. I guess another portion of my question was it feels like this refrain of start out we'll make this experience really simple, I hear this about Heroku specifically and then other platforms too where you start off on its platform and it's worth… because it makes it so easy to get started it's worth taking some time to build your stuff on the platform. But eventually you want to do things that are more custom or weirder or that it doesn't support or that is harder. And either the platform built it in and grows more complex or you more towards something you have more control over like AWS or something. Do you see Now as falling in that spectrum where it's really easy to get started for simple things or things where you don't need a ton of control? Perfect. And then you might move to AWS or some other platform later? Or do you see it as you're going to try and solve those problems that move people to other platforms on Now itself.

**GUILLERMO:&nbsp;** That's a wonderful question. Because we've seen this time and time again where the platforms that give you a quick start advantage don't give you a longer term advantage.

**JAMISON:&nbsp;** Yeah, there's that whole, was it the load balancing or routing thing that Heroku had a few years ago where some of the underlying abstractions of the platform turned out to be limiting to you. And I know [inaudible]

**GUILLERMO:&nbsp;** Absolutely. And that's why I mentioned that simplicity when you don't really understand what's going on underneath is actually a very clear disadvantage. So, our answer to this has different angles. One of them is we don't want to be necessarily the solution that answers every single problem in the world. Because what we see about the cloud space right now is there are tons of really great services that you can mix and match. And this is actually where Now comes in, because Now in JavaScript makes it so easy to write a quick microservice that is invoking all these sophisticated cloud APIs. You can have… maybe the Now deployment is serving requests to a webhook from SendGrid that's reading an email that gets to Now and ends up transformed or translated by a Google Translate API and then out put it back to a cloud database.

And so, what we see about the cloud today is that before it required you to move to AWS and set it up yourself is kind of not a thing anymore. Because you're very, very, very likely to find a cloud service that already answers that. So, that idea that it's an all or nothing play I think is no longer true. You can even see this when you see open source projects that come out. And from the very moment they become open source they also have a hosted version of them. Because the authors know that all of these things are painful to set up. So, no one wants to download the latest, let's say a graph database and set it up themselves on a cloud provider anymore. They are expecting that someone will give them an HTTP API for it.

**JAMISON:&nbsp;** Sure.

**GUILLERMO:&nbsp;** So, that's where I see it now making a lot of sense, because if we're not able to fully satisfy a particular need we're going to do the best that we can to do so of course while maintaining our simplicity. But we'll make it so that it's the best place still to make those requests to all those other services. And in fact, it's going to be very hard to migrate away when for example we're giving you complete coverage in every data center in the world. It's going to be very hard for you to make the decision to migrate to one instance or a couple of instances in one region or one availability zone somewhere else.

So, we're taking that slice of the problem which is in this case HTTP 2 services. And then their connection with the greater cloud. And you know, if you find that something is limiting in the HTTP side of things or how we allow, how we scale and manage deployments then it really is our fault. Because we want to excel at that. Now, if you find that a very particular service that you want to add on is missing, instead of adding a huge stack of services we're probably going to tell you, “This is a great partner or this is a great API resource for you to look into.”

**JAMISON:&nbsp;** Sure. That makes sense.

**AIMEE:&nbsp;** So, I just have one other question, because this is just like always notoriously a pain when you're in production and you try to debug stuff. Do you want to talk about how Now makes that easier?

**GUILLERMO:&nbsp;** Yeah. So, we started with the source URL because we wanted to show people that this is how our extensibility model works. We have these additional resources that are obviously if you're in the premium plan are exclusive to you where you can get information about your deployment. Right now it's only static information. The idea is that since we're in control of your deployment we can launch more than one of your deployments. We do this obviously for different reasons. One is reliability and fault tolerance. Another one is geographical distribution which we'll talk more about in the coming months. And the other one is the ability for us to extract a lot of information in a way that doesn't hurt performance. So, we can understand your code because we can essentially extract information in a limited basis from it. And then expose it to you through the additional underscore resources that we offer.

So, it's not something that we're going to be able to give you perhaps all of the information of everything that's happening all the time because it might actually have a performance problem in doing so. Observation itself is not free. But the idea is that over time we can give you insights. So, that's why one of our first additions to the source interface is going to be this idea of temperature of your code and to understand what paths are more active than others. Because when a lot of the discussions come up about performance and V8 and running microbenchmarks, a lot of it always come down to are you really benchmarking the things that are important? Maybe you're optimizing a for loop somewhere where it really doesn't matter. So, the first step for us as far as code debugging is telling you, “Look, these are the parts of the application that are worth optimizing.”

**JOE:&nbsp;** Yeah, so I'm kind of curious about what you're doing, what the security profile is like for this, what you're doing to keep the code that is deployed. Obviously not any code that's going to go out to the client. But the Node code. I might have keys or something in that code. So, where does security fall on your priority list and what you guys have been doing?

**GUILLERMO:&nbsp;** Security is extremely important to us. So, we'll actually announce very soon our first security challenge where we're going to set up a very interesting type of Now deployment for people to break into and out of. So basically, we provide very strict isolation guarantees in that what we launch for you is a new machine. It's a new server. Then as far as the code is concerned, open source projects obviously their code is public. So, the associated underscore resources that we provide are going to be public for open source projects. But that also means that every open source deployment that you launch on ZEIT no matter how much traffic it generates in terms of for example simultaneous connections, we'll host. But the code is public.

Now, from the perspective of the premium customer basically all the insight is private. All the tokens are private. We're also coming out with the secret storage feature that I think is going to be a way of incorporating really great best practices into deployment where people no longer ever need to store their secret API tokens in their GitHub repositories. They never have to put them directly in their source code. They don't have to put them in package.json. Basically a very easy and smart way of exposing environmental variables through secrets. And that's also going to work for both plans, open source and premium. But security is something we're continuously revisiting from all different sides, one of them being abuse and denial of service, another one being the isolation guarantees that we provide. Another one being the build step itself. Because we have this idea of a very quick way of sharing the modules between deployments but there is a challenge associated with that which is you don't want to be able to break out and poison that cache, essentially introduce bad code into something that's globally shared.

And at the same time moving forward we'll also have, I think there are interesting problems and challenges associated with pulling code from a registry itself. So, I think there are several ways that we can do the security of npm downloads themselves. Some of them being for example integrating with security APIs that tell us about the safety of different modules so that we can warn you about running modules that are known to be unsafe. Another aspect of security in that regard is technically the keys of a certain developer that is the developer of a very popular module could be compromised. So, this is a problem we worry about a lot. And we're trying to think what solutions we can provide for the great JavaScript community, not just Now users where if you rely on npm downloading packages all the time and you don't review them every time, then you're trusting that no developer of all of these possible developers that you're downloading code from have been compromised. So, for very large-scale deployments this could be a very, very big concern. So, security for us has all these different angles to it. And we're trying to attack all of them.

**JOE:&nbsp;** I love the idea of these coding contests, the hacking contests. I think that's a great way to find these security holes as well rather than just waiting around passively for somebody to point something out.

**GUILLERMO:&nbsp;** Absolutely. And I think we can make it really fun specifically because you can use our own tool to try to I guess break out of it without doing damage to others. So, I think it's going to be a great opportunity for people to, especially people that are very, they're all about finding these little hacks and glitches. And maybe they're not JavaScript developers but they will be drawn by the contest itself.

**JAMISON:&nbsp;** So, what's coming next for Now? You've mentioned a few things around instrumentation and debugging and getting insight into what your code is doing. Are there any other big things that you're ready to talk about?

**GUILLERMO:&nbsp;** Yeah. We're actually announcing this week probably our biggest feature yet that has to do with what I mentioned earlier regarding instantly upgrading your deployment. And we have some really juicy features associated with that. So, the basic idea is custom domains. But we have some really great surprises associated with that. Then very immediate on a road map is this idea of we want to make sure that you trust us because of our latency characteristics. You don't need to trust us because we claim that we're the best. So, we want to add a great level of introspection into our own cloud to show you what it means to deploy with us in terms of numbers and how it compares to everything else that's out there.

For example, I think a question that I routinely have is I have a great experience when I deploy something in San Francisco and I consume it from San Francisco. It's great. I have a really fast internet connection and everything goes smoothly. But as someone that also travels a lot and goes to a lot of conferences, I know that my own stuff is painful to visit when you're overseas. So, the bulk of our work for 2016 is to be very transparent with how we address this problem. We want to on a mission level, I think it's all about democratizing the access to the cloud technology that perhaps works really well on a certain region or it works exclusively well for that region. On the other hand, it's all about also making claims that we can back with data. And communicating that data to people I think is really important. So, a lot of our work coming up is in showing our, the performance of our cloud in real-time.

And of course like you were mentioning, everything related to improving the experience of JavaScript debugging and deployment. It's not a milestone in the road map but it's something that we're constantly revisiting. So, installation performance and the ability for us to get more and more data out of the deployment and logs. So, these are things that we're constantly revisiting. We don't see an end in sight to those particular improvements. So, it's something you can expect to get all the time. If you follow us on Twitter at ZeitHQ, Z-E-I-T-H-Q, you probably will see that we're posting updates to our infrastructure, our Now client from npm, on a weekly basis.

**CHUCK:&nbsp;** Alright. Let's go ahead and do some picks. Joe, what are your picks?

**JOE:&nbsp;** Alright. So, I want to pick the game Overwatch. Just launched yesterday in the evening. I've played it a bit. I played it in Beta as well. Super fun game. They picked a really reasonable price point at 40 bucks. Blizzard did. I think they could have charged more so I feel like they picked a very reasonable price point. It doesn't run a single-player game so maybe that was their justification or maybe they thought they couldn't justify a higher price. But it's a really fun game. So many different characters you can play. It's a first-person shooter but there are so many different roles you can choose and they're all extremely different. There's like 20 of them. Very fun game, very fast-paced. Games on average last less than 10 minutes. So, it's easy to jump into just for a little bit at lunch when you're off the clock and then be done and get right back to work. So, I'm going to pick Overwatch as my pick.

**CHUCK:&nbsp;** Alright. Jamison, what are your picks?

**JAMISON:&nbsp;** I have two picks. My first pick is I read 'To Kill a Mockingbird' for the first time last week. I don't know how I just missed that as a kid.

**JOE:&nbsp;** Wow Jamison, did you never go to English class in ninth grade? [Chuckles]

**JAMISON:&nbsp;** I never went to ninth grade I guess.

**JOE:&nbsp;** [Laughs]

**JAMISON:&nbsp;** No, but it lives up to its reputation. I'm kind of glad I didn't read it earlier because I was programmed to not like all the books we read in school. And maybe I wouldn't have enjoyed it as much if I had read it earlier. But it was solid. If you hadn't read 'To Kill a Mockingbird' it's a great work of American literature. I loved it.

And my other pick is just React Rally. It's the React conference that I am running. It's in Salt Lake City in August. And tickets are on sale now. We actually posted the schedule and the speakers. So, you can finally see who's going to be there. And if you go to ReactRally.com you can see all that and also buy tickets. I'd love to see you there. Those are my picks.

**JOE:&nbsp;** Jamison, I picked that last week. You're such a follower.

**JAMISON:&nbsp;** [Chuckles]

**JOE:&nbsp;** [Laughs]

**JAMISON:&nbsp;** I just do what you do, Joe.

**CHUCK:&nbsp;** Aimee, what are your picks?

**AIMEE:&nbsp;** I have two. The first one is this book that I'm obsessed with because I think it is probably one of the best things I've ever read so far. It's called 'Grokking Algorithms'. There are two, three chapters but I just ordered the book and started it. And it is so friendly for people who are trying to get started with this. I've just never read anything that explains things this well. So, that is my first pick. I just highly recommend anybody who's interested in it to go read this book.

And the second one is a blog post on Martin Fowler's blog. But it's not by him. It's by another woman and I'm going to butcher her name so I'm probably just not even going to say it. You'll have to check the link to see her name. But it's called 'Born for it: How the image of software developers came about'. It's not a very long read. But I thought it was pretty good. So, that is it for me this week.

**CHUCK:&nbsp;** Alright. I'm going to put out a couple of picks. The first one is I just barely booked my travel to go to Podcast Movement. And that's in July. It's the week of the fourth, actually. Fourth is on a Monday. I fly out on Tuesday. It's Wednesday, Thursday, Friday. And then I'm actually doing a meetup in Chicago on Saturday and then coming home. But the thing that I really like is that I was traveling enough to where I actually go the TSA pre-check thing. And that is so nice to be able to just walk through security. You just go through the metal detector so you don't have to take your shoes off or anything. I don't have to pull my laptop out of the bag or any of that other stuff and the line is usually much shorter. And so, I'm going to pick the TSA pre-check because it is nice.

Another pick that I'm going to make is something that I saw at ng-conf and decided I wanted bad enough to buy it for myself. And that is the cube. It's a projector. So basically, it's about an inch and a half or two inches cube, more or less. I don't think it's exactly cubic. But it's close enough. And it's a projector that you can actually set up on a desk, has a little tripod that comes with it. You can hook it up via HDMI to your computer. And it works pretty darn good. I was doing a training for some Cub Scout leaders last week on Thursday. And just walking through how the Cub Scout program works. And I set it up and projected onto the wall and it worked pretty darn good.

One thing I will say about it is that it wasn't super-duper bright. So, you do have to turn the lights off if you want to be able to see it. Some projectors are bright enough to where you can more or less make things out. But the way that the church lights were set up that I was in, it just didn't work until I turned the lights off. But then it worked great. And I was surprised at what comes in such a little package that works really well. It also will work with your iPad or iPhone or Android phone or other tablet. So, you have to get an adapter that will adapt to HDMI but it works real well. So, I've been pretty, pretty darn happy with that.

And those are my picks. Guillermo, what are your picks?

**GUILLERMO:&nbsp;** I was just thinking about them. I like this concept a lot, by the way, finishing with the picks. So, I'll share one that I read yesterday which is a productivity tip. It's called 'Eat that Frog'. I was just googling. It seems like it originated with a Mark Twain quote which I don't know if we can trust that a quote has been actually said by Mark Twain at this point.

**JAMISON:&nbsp;** [Laughs] That's true.

**GUILLERMO:&nbsp;** But the idea is that you eat the frog in the morning, which is you eat the thing that you don't really want to do. You do it, you get it out of the way, and then the rest of the day is going to be great. And I like it because it's so short and concise. And you know for my own productivity, my role now has evolved into doing so many different things as a startup CEO that there are a lot of frogs to be eaten first thing in the morning. So, that's my only thing to share.

**CHUCK:&nbsp;** I keep hearing about a…

**AIMEE:&nbsp;** I really like that.

**CHUCK:&nbsp;** I keep hearing about a book by that name, by Brian Tracy. So, I've heard it's good. But, yeah.

**GUILLERMO:&nbsp;** Oh, might be worth looking into.

**CHUCK:&nbsp;** Yeah.

**AIMEE:&nbsp;** Maybe that's why I go running first thing in the morning. [Chuckles] Just kidding.

[Laughter]

**GUILLERMO:&nbsp;** Yeah.

**AIMEE:&nbsp;** I really love it.

**CHUCK:&nbsp;** Eat that frog, right?

**AIMEE:&nbsp;** [Laughs]

**GUILLERMO:&nbsp;** It's difficult, yeah. Good for you.

**CHUCK:&nbsp;** Yeah, I'll put a link to the Brian Tracy book in the show notes as well. I haven't read it yet. So, it's not exactly a pick. But I've heard it's good from people I trust. But yeah, I like the idea.

Alright, well if people want to follow up with you, find out what you're up to Guillermo, what do they do?

**GUILLERMO:&nbsp;** RauchG on Twitter or ZeitHQ on Twitter. Hopefully soon we can get rid of the HQ somehow. [Chuckles] But yeah, we tweet there a lot. Zeit.co/blog. We blog a lot as well. And that's the best way to stay tuned for now.

**CHUCK:&nbsp;** Alright. Well, we'll go ahead and wrap this up. Go check out Now. It sounds really cool. And we'll catch you all next week.

**_[Bandwidth for this segment is provided by CacheFly, the world’s fastest CDN. Deliver your content fast with CacheFly. Visit CacheFly.com to learn more.]_**

**_[Do you wish you could be part of the discussion on JavaScript Jabber? Do you have a burning question for one of our guests? Now you can join the action at our membership forum. You can sign up at JavaScriptJabber.com/Jabber and there you can join discussions with the regular panelists and our guests.]_**
