https://www.youtube.com/watch?v=1hnyCQW-B4A



Claude Code + Browserbase: Build an AI Agent that Controls the Web
Code With Antonio
Code With Antonio
419k subscribers

Join


1.5k


Share

Ask

Download

46,544 views  14 Jul 2026
💻 Source Code: https://cwa.run/relay

📚 Resources:
Try Railway: https://cwa.run/railway
Try Clerk: https://cwa.run/clerk
Try Neon: https://cwa.run/neon
Try Trigger: https://cwa.run/trigger
Try Liveblocks: https://cwa.run/liveblocks
Try Browserbase: https://cwa.run/browserbase
Try Sentry: https://cwa.run/sentry

Timestamps

00:00 Intro
05:02 Project Setup
16:37 Agentic Coding Setup
27:25 Auth Setup
41:09 Organizations Setup
01:02:43 Dashboard Layout
01:47:31 Database Setup
02:22:18 Workflow Page
02:35:24 Trigger.dev Setup
03:03:37 Canvas Setup
03:16:35 Custom Nodes
03:28:54 Liveblocks Setup
03:40:38 Liveblocks Auth
04:00:12 Names & Avatars
04:06:00 Workflow Toolbar
04:38:22 Workflow Execution
05:00:07 Browserbase Setup
05:17:19 Data Passthrough
05:38:09 Live Run Status
05:53:34 Remaining Nodes
06:05:20 Email Node
06:11:03 Console Panel
06:36:30 Session Replay
06:52:37 Billing
07:02:24 Sentry Setup
07:15:33 Polish
07:19:56 Deployment
07:23:30 The End
Ask
Get answers, explore topics and more

Ask questions


--------------------------------------------------------------------------------------------

In this video


Chapters

Transcript
Search transcript
Search transcript

Chapter 1: Intro
0:000 secondsWhat if he could automate any website?
0:022 secondsWatch this. I'm going to give my agent one goal. Configure a Porsche 911 for me and then email me the link. Watch how
0:1111 secondsthe agent opens the site. Chooses the paint, the wheels, the exhaust, all on its own. I never told it where to click.
0:1919 secondsI just told it what I wanted. Seconds later, the finished build lands in my inbox. This is Relay, a platform where
0:2828 secondsyou and your team use AI agents to automate the web and actually get work done. And in this tutorial, you're going
0:3737 secondsto learn how to build this entire platform yourself. The heart of Relay is the canvas built with React Flow. You
0:4545 secondsstart with a trigger and then chain together action nodes into a workflow.
0:5151 secondsSome are simple like opening a URL or sending an email through resend. Others
0:5858 secondsare more powerful. The act node clicks and types for you. Observe finds elements on the page and extract pulls
1:071 minute, 7 secondsout exactly the data you need. And then there's the star of the show, the agent node. You give it a goal in plain
1:151 minute, 15 secondsEnglish, and it takes over the browser completely, deciding what to do, clicking, scrolling, and figuring out
1:221 minute, 22 secondseach step on its own until the job is done. Every node has a configuration panel, and you pass data from one step
1:301 minute, 30 secondsto the next using simple template tokens. Now, here's where it gets satisfying. While your workflow runs,
1:381 minute, 38 secondsevery node shows its status in real time. you see exactly which step is working, when it completes, and if
1:451 minute, 45 secondsanything fails. The agent lights up and goes to work. And down in the logs panel, you can watch each step finish
1:531 minute, 53 secondswith its exact duration and output. And all of this runs as a durable background job. So even if you close your tab, your
2:012 minutes, 1 secondworkflow keeps running reliably until it's done. But how is this even possible? Let's break it down. When you
2:082 minutes, 8 secondshit run, the agent spins up a real Chrome browser in the cloud powered by browser base and stage hand. That's how
2:172 minutes, 17 secondsit can handle any website. It's driving an actual browser, not just calling an API. The entire run executes in the
2:262 minutes, 26 secondsbackground using trigger.dev, dev which streams every step back to the canvas in real time while your workflows and the
2:362 minutes, 36 secondsresults are saved to a Postgres database with Drizzle and Neon. And because it's a real browser session, the whole thing
2:452 minutes, 45 secondsis recorded. So once it finishes, you can replay and watch exactly what the agent saw and did step by step. Nothing
2:542 minutes, 54 secondsis a black box and the entire canvas is multiplayer. Those cursors you've been seeing this whole time, that's your
3:013 minutes, 1 secondteam. Powered by Live Blocks, you can build and edit these workflows together in real time, just like a Figma file,
3:113 minutes, 11 secondseveryone on the same canvas at once. And building a Porsche is just one example.
3:173 minutes, 17 secondsYou can point an agent at almost anything. Have it play a full game of chess, make it solve today's wordle,
3:253 minutes, 25 secondsplan a road trip across the country, or put together a morning news briefing and email it to you. If a human can do it in
3:323 minutes, 32 secondsa browser, you can automate it with Relay. And of course, this is a real product. Authentication, organizations,
3:413 minutes, 41 secondsand billing are all built in with Clerk, so users can sign up, create a team, and upgrade to a paid plan. Everything you
3:503 minutes, 50 secondsneed to charge for this product from day one. And once it's ready, we deploy the whole thing to production on railway.
3:583 minutes, 58 secondsAnd this is more than just a coding tutorial. We're going to build our app the way software is actually written in
4:044 minutes, 4 seconds2026 using agentic coding. We are going to use coding agents like claude code and MCP tools as we build. So along the
4:134 minutes, 13 secondsway you won't just learn how to build this app. You'll learn how modern software engineering really gets done today and to keep all of this running
4:224 minutes, 22 secondssmoothly in production. We'll wire in Sentry. Most people know Sentry for error tracking, but it's grown into a
4:304 minutes, 30 secondsfull observability platform, logs, performance tracing, and even AI agent monitoring. And since our app is
4:374 minutes, 37 secondsconstantly running AI agents in the background, that's exactly what we need.
4:424 minutes, 42 secondsWe can trace any workflow run from start to finish, see precisely what happened at every step, and catch problems long
4:504 minutes, 50 secondsbefore a user ever runs into them. My name is Antonio, and I will be your instructor for this course. I couldn't
4:584 minutes, 58 secondsbe more excited to build all of this together. Let's get started.
Chapter 2: Project Setup
5:085 minutes, 8 secondsLet's get started by making sure we have the system requirements and tools needed to develop this project. The runtime in which we are going to develop our
5:175 minutes, 17 secondsapplication is NodeJS which makes this an absolute requirement to have it installed on your machine. You can
5:255 minutes, 25 secondsverify your installation by running the command node-v in your terminal which should output the
5:325 minutes, 32 secondsversion of node which you currently have. If you're wondering which node version you're supposed to have to be able to develop this project, the best
5:425 minutes, 42 secondsway to check is to go to next.js documentation inside of installation and find the system requirements. And in
5:505 minutes, 50 secondshere you will find the minimum NodeJS version. As you can see, it says 20.9,
5:575 minutes, 57 secondswhich means as long as you have this Node version or higher, you're good to go. So, you don't need to have the same version as me, and you don't need to
6:066 minutes, 6 secondshave the latest long-term support version. It's only important that you don't have a version lower than 20.9.
6:156 minutes, 15 secondsThe second requirement is some kind of version control. The one you are probably familiar with which is also the most commonly used one is git. You can
6:246 minutes, 24 secondsverify whether you have that by running git-v. This will be very important for us to have so we can maintain proper version control so we don't lose the progress of our project's development.
6:346 minutes, 34 secondsNext step is to cascade a brand new nex.js project. Now usually what I would do is I would direct you to the
6:426 minutes, 42 secondsdocumentation of nex.js JS tell you to find the installation and guide you through the quick start installation script. But recently I found myself
6:506 minutes, 50 secondsdoing something else. As some of you might know, every time I set up Nex.js, the second thing that I do is
6:596 minutes, 59 secondsimmediately add Chatsen UI design system. And I've recently found out that
7:067 minutes, 6 secondswe can actually save us a step by initializing a brand new project using chatsen installation script instead. So
7:147 minutes, 14 secondsinstead of running npx create next app, you can actually run npx chatsen latest
7:217 minutes, 21 secondsin it. But instead of using latest, I would highly recommend that you use the same version that I'm currently on 4.12.0,
7:307 minutes, 30 secondswhich is the current latest version. The reason I recommend doing this is because depending on when you're watching this
7:377 minutes, 37 secondstutorial, a new breaking change can be introduced in the uh later versions which I have no control over. So to make
7:457 minutes, 45 secondsthis tutorial easier for you to follow, I would recommend being on the exact same version as me. So we have the exact
7:527 minutes, 52 secondssame codebase. Let's go ahead and initiate this command. Let's select a template next.js. Let's select no for
8:018 minutes, 1 secondthe monor repo option. Select Radix for the component library, Nova for the preset, and let's go ahead and call our project browser automation.
8:118 minutes, 11 secondsAnd now let's go ahead and let it install. Once the installation is complete, go ahead and open that project in your IDE. You might be greeted with a
8:208 minutes, 20 secondsbanner like this one. Restricted mode is intended for safe code browsing. Trust this folder to enable all features. So
8:288 minutes, 28 secondsjust go ahead and find the restricted mode button. And in here you can verify that you trust this folder. There we go.
8:368 minutes, 36 secondsAnd that will enable you to uh manage this project and its codebase completely. Once you open your project in your IDE, it's also important that
8:468 minutes, 46 secondsyou enter this project in your command line interface. If you're using the CLI which is built in into your IDE, chances
8:548 minutes, 54 secondsare you are automatically going to be in that folder. But for those of you who are using a CLI outside of this project,
9:039 minutes, 3 secondsmake sure to do change directory and then enter the correct project. This way, if we do a command like npm run,
9:129 minutes, 12 secondsyou're not going to be greeted with script not found, but instead it's going to read from this project's package.
9:199 minutes, 19 secondsJSON, and it's going to find that exact script. So just make sure that in whatever command line interface you are
9:279 minutes, 27 secondsusing, you have entered the correct project. And once you've established that you are inside of your project, go ahead and run npm rundev. What this is
9:369 minutes, 36 secondsgoing to do is it's going to start this project on localhost 3000. And if you visit that in your browser, it's going
9:459 minutes, 45 secondsto look something like this. A message project ready. You may now add components and start building. We've
9:529 minutes, 52 secondsalready added the button component for you. Clicking the button does nothing, but clicking the letter D on your
10:0010 minuteskeyboard will toggle between dark and light mode, which is pretty cool.
10:0510 minutes, 5 secondsThey've built in that for us. So, if you take a look at the app folder, page.tsx
10:1310 minutes, 13 secondsis exactly where you're going to find the code from that homepage. So project ready and then the two paragraphs
10:2110 minutes, 21 secondsdescribing that we can now add components. At this point I would recommend creating a new repository so that we can commit this project and
10:2910 minutes, 29 secondsstart keeping track of every single change that we do. So let's go ahead and give this repository name something like browser automation app. I'm going to
10:3810 minutes, 38 secondskeep it private and I'm going to click create repository.
10:4310 minutes, 43 secondsOnce you've created a repository, go ahead and copy the second option. Push an existing repository from the command
10:5010 minutes, 50 secondsline. Then let's go ahead inside of here. Make sure that you have no uncommitted changes. If by any chance
10:5910 minutes, 59 secondsyou do, you are going to have to do get add and then you're going to have to do get commit with a message inside. But if
11:0711 minutes, 7 secondsyou have done all the steps like I did, you're not going to have any uncommitted changes and you will have just one commit which is the initial commit which
11:1611 minutes, 16 secondswas added once we run the command npx chaten in it. So the only thing you actually have to do is within this
11:2411 minutes, 24 secondsproject go ahead and paste those three commands. What this is going to do is it's going to push this entire project
11:3211 minutes, 32 secondsinto this GitHub repository. So from now on we can create branches, we can create commits, we can backtrack and most
11:4011 minutes, 40 secondsimportantly we ensure that we don't lose changes to this project. Now that we have a git repository set up, we can
11:4811 minutes, 48 secondssafely add all components from shatzen UI. So I would once again recommend using the exact version as me which is
11:5611 minutes, 56 secondsalso the same version we used to cascade this project. The reason we are adding all components at once is so that we don't waste time adding components
12:0512 minutes, 5 secondswhenever we need a new one and so we don't have to remember this version every single time. Once we finish the project, we can easily use AI and
12:1412 minutes, 14 secondsagentic coding to simply remove all components which we are not using. So let's go ahead and execute this command in our project. After the command
12:2312 minutes, 23 secondsfinishes, you might see a couple of messages like these which are basically instructions for components which need a little bit additional setup like adding
12:3212 minutes, 32 secondsthem to the root layout. We can forget about this for now and we can add this when we actually need this component.
12:3912 minutes, 39 secondsYou can also see one information here that it skipped a button file because the file is identical. So what does that
12:4712 minutes, 47 secondsmean? Well, if you remember inside of our app page.tsx DSX we already used the button component from components UI
12:5512 minutes, 55 secondsbutton. So that was one component which was already added for us. So now if you go inside of your UI folder inside of
13:0213 minutes, 2 secondscomponents you should see a bunch of new components available here and it's normal that some of them have some kind
13:1013 minutes, 10 secondsof lint errors. You don't really have to worry about this for now. We can easily resolve that later. So if you go ahead and just you know play around with them.
13:1813 minutes, 18 secondsUh there is a chance some of them have some type errors or things like that.
13:2313 minutes, 23 secondsYou don't have to worry about that. We are going to resolve if any of those are actually breaking our build. For now it's just important that you have added
13:3113 minutes, 31 secondsall of these components here. So as you can see I have 62 changes and I would suggest and I mean I would guess that
13:3813 minutes, 38 secondsyou have a similar amount if not exactly the same. You can even see that we have one hook added use mobile which is quite
13:4813 minutes, 48 secondsuseful even outside of these components which have been added. But as I said you can see that some of these files have
13:5513 minutes, 55 secondssome lint errors. We can ignore that for now. And what we are going to do is just commit these changes so that we are
14:0314 minutes, 3 secondsstarting to utilize this GitHub repository which we have just initialized. So I'm going to go ahead and do get add get commit and I will do feature add all chats UI components.
14:1714 minutes, 17 secondsAs simple as that. And let's do get push. So all of that is on our main branch. And if you go ahead and refresh
14:2514 minutes, 25 secondsyour GitHub repository, you will see that the latest commit is that we have added all Shatsen UI components.
14:3214 minutes, 32 secondsBrilliant. That brings us to the end of this first chapter. In the next chapter, we're going to learn how to set up agentic coding for this project. Now
14:4114 minutes, 41 secondsthat our GitHub repository is set up, it's the perfect time to connect it to Railway. So, every push we make from here on gets deployed automatically. One
14:5014 minutes, 50 secondsthing that really sets Railway apart is that they are running on their own infrastructure instead of simply reselling AWS. That gives them much
14:5914 minutes, 59 secondstighter control over performance, pricing, and scaling. So you can start with a single instance and grow all the way to a globally distributed deployment
15:0815 minutes, 8 secondswithout the usual cloud complexity or pricing. If you'd like to follow along, you can use the link on the screen to
15:1515 minutes, 15 secondsget $20 in Railway credits on a new account. Once you've created your Railway account, head into the dashboard and create a new project. You can use
15:2415 minutes, 24 secondsthe GitHub repository feature to find the new repository we just created and pushed our files into. Once you select
15:3115 minutes, 31 secondsit, it will automatically detect that this is a Nex.js application and start building it. Once your app has deployed, go inside of settings and scroll down
15:4015 minutes, 40 secondsuntil you find networking. In here, you can click on the button generate domain and go ahead and enter 8080 for the port and click generate domain.
15:5015 minutes, 50 secondsThat's going to create a public domain that anyone can now access. Visiting that domain will give you the exact state of the application we've had so
15:5815 minutes, 58 secondsfar along with a fully working light and dark mode toggle. From now on, every commit you push to this repository is
16:0616 minutes, 6 secondsgoing to be automatically rebuilt and redeployed. If for whatever reason your builds are not succeeding and have similar errors like this, rest assured
16:1516 minutes, 15 secondsthat we are going to fix all of that in periodical checks throughout this tutorial. What's important right now is that you have established a connection from your GitHub repository to Railway.
16:2716 minutes, 27 secondsSo regardless if your builds are succeeding or failing, rest assured we are going to have several chapters dedicated to resolving any build errors that our app might have.
Chapter 3: Agentic Coding Setup
16:4316 minutes, 43 secondsNow that our project and repository are set up, it's time to choose the tool which we're going to use to perform a gentic coding. The tool that I'm going
16:5116 minutes, 51 secondsto be using is Cloud Code with Oppus 4.8. That being said, you are not required to use the same tool and model
17:0017 minutesas me. If you prefer using Open Code and their models, feel free to do so. Or if you prefer using codecs and GPT models,
17:0917 minutes, 9 secondsyou can do that as well. Of course, it is preferable to use cloth code with OPUS 4.8 if available for you because
17:1817 minutes, 18 secondsthat will give you the closest output to what I will be getting throughout this tutorial. If you ever do find yourself in a position that your AI is producing
17:2717 minutes, 27 secondssignificantly different output from my AI, rest assured that this entire project is open source and every chapter
17:3517 minutes, 35 secondsthat we are going to do after this one will have a corresponding branch in GitHub. So no matter where you find
17:4317 minutes, 43 secondsyourself, you will always have a way to point your AI to how the code is supposed to look like. Or you can just
17:5017 minutes, 50 secondsskip that entirely and just use the branch as a checkpoint so you immediately get that code in your codebase and then continue from that
17:5817 minutes, 58 secondschapter onwards. So don't worry, I'm doing my best to mitigate or should I say improve the deterministic output of
18:0618 minutes, 6 secondsthis tutorial even though we are going to be using agentic coding. As you can see from these three examples, you can run a lot of these tools inside of
18:1518 minutes, 15 secondscommand line interfaces, but you are of course welcome to use any graphical user interfaces if you prefer them or desktop
18:2418 minutes, 24 secondstools equivalent of these apps. For example, I personally prefer using clot code for VS code which is a really cool
18:3218 minutes, 32 secondsextension which allows me to open cloud code as I said the tool which I will be using in a graphical user interface
18:4118 minutes, 41 secondswhich looks like this. It's easier to read and it will be easier for you to follow along. So if you're using cloud code and visual studio code make sure to
18:5018 minutes, 50 secondsinstall this extension. It's pretty neat and it will help you a lot. So let's perform our first agentic coding task.
18:5718 minutes, 57 secondsThere is one problem in our codebase. I have a file called agents.md.
19:0419 minutes, 4 secondsThis is a pretty standard file which a lot of coding tools use to get some necessary instructions on how to behave
19:1219 minutes, 12 secondsin this project. The problem is agents.md isn't always read by claude code. So,
19:2019 minutes, 20 secondswhat people usually do is they copy and paste this and then they rename it to claude.md.
19:2719 minutes, 27 secondsBut that can be pretty tedious to do, especially if we plan on adding changes to these files, which we actually do.
19:3419 minutes, 34 secondsSo, how about we create a symbolic link which basically references the agents.md inside a file named claude.md.
19:4419 minutes, 44 secondsThere is technically a way of just doing agents.md.
19:4819 minutes, 48 secondsI saw that. But why don't we just do a real symbolic link? So, I'm going to go
19:5619 minutes, 56 secondsahead and do the following. I'm going to open cloth code. I'm going to switch to auto mode so I don't have to allow
20:0420 minutes, 4 secondseverything. And I'm just going to tell it create a symbolic
20:1020 minutes, 10 secondscloud MD file that references agents.m
20:1620 minutes, 16 secondsMD. So this will be our first prompt. If you've never done a symbolic link before or don't know how to do that, you can
20:2420 minutes, 24 secondsjust ask AI to do that instead. There we go. So now claude code is a symbolic link which references agents.m MD. So if
20:3420 minutes, 34 secondsI click inside of claude.md, you can see the exact same output inside. To test if the symbolic link actually works, I
20:4120 minutes, 41 secondswould recommend going inside of agents.md and do something like test one two three and save this file. Then let's
20:5020 minutes, 50 secondsgo inside of claude.md. And if it is correctly set up, you should see that content immediately available here in
20:5820 minutes, 58 secondsclaude.md as well. And if you remove it from here, I think it should work vice versa. There we go. So you can see that
21:0521 minutes, 5 secondsuh whatever I type in one file is immediately available in the other file.
21:0921 minutes, 9 secondsSo with this very simple prompt, we have now created a symbolic link between these two instructions. So regardless if
21:1621 minutes, 16 secondsyou're using open code, codeex, cloud code or maybe switching between all three at the same time, you will rest assured that all of your prompts will get the exact same project instructions.
21:2721 minutes, 27 secondsAnd these ones are pretty important. for example. So what we have in our cloud MD and agents MD is the instruction which is now built in in every new Nex.js app.
21:3921 minutes, 39 secondsThis is not Nex.js. You know it's basically instructing the AI to tell it to ignore its training data and instead to use the node modules inside of here.
21:5221 minutes, 52 secondsSo it's telling the AI, hey, if you are ever wondering about how to do something with Nex.js, JS don't try to use your
21:5921 minutes, 59 secondstraining data but instead go inside of here and find nextJS and find the
22:0622 minutes, 6 secondsdocumentation wherever uh they have added it right and then it can read the upto-date data about this project that
22:1522 minutes, 15 secondswe are in so that's the kind of stuff that we are going to be adding here now let's do our first code change which
22:2222 minutes, 22 secondsactually alters the project so make sure you do npm rundev and make sure the project is running on localhost 3000 and
22:3122 minutes, 31 secondswhat I'm going to do now is the following. I'm going to start a new conversation and I'm going to tell it setup soner which is a component which
22:4022 minutes, 40 secondswe've added through shhatsen UI in layout because soner is basically a toast component which first needs to be
22:4822 minutes, 48 secondsadded to the layout file and alter the existing page.tsx tsx so that when we click on the button we use toast API.
23:0123 minutes, 1 secondI'm using auto mode so I don't have to approve anything manually. So you can just click here and then add that. As you can see it immediately recognized
23:0923 minutes, 9 secondswhat it has to do. So I'm just going to let it finish and then we're going to look through the code changes. This shouldn't be a big change. So that's why
23:1623 minutes, 16 secondsI'm doing it this way because we can just take a look at the git diff and then we are going to see if it did it correctly or not. There we go. So it's
23:2523 minutes, 25 secondsfinished. So I have a couple of files changed here. Layout.tsx is the first one. So what was done here
23:3223 minutes, 32 secondsis that we have a brand new import toaster from components UI sonner and it was rendered right beneath the theme
23:4023 minutes, 40 secondsprovider. So here's what I would actually do first. It's made a mistake and the mistake is that the toaster
23:4823 minutes, 48 secondsshould be inside of the team provider, right? Uh I think this will still work.
23:5323 minutes, 53 secondsLet's take a look at the page.tsx. So we have toast here. It changed this to use client. Perfect. And this button now has
24:0124 minutes, 1 seconduh an on click which basically calls the toast button clicked. So if I click this, there we go. Button clicked. And
24:0824 minutes, 8 secondslooks like even though it didn't wasn't added uh in the theme provider in the layout, it still works. That's
24:1824 minutes, 18 secondsinteresting. So, looks like the theme provider doesn't need to encapsulate the toaster. So, I'm just going to go ahead and ask AI whether this is required or
24:2724 minutes, 27 secondsnot. I see the toaster component wasn't added within the theme provider. Is that necessary?
24:3824 minutes, 38 secondsI can see that regardless of this, the theme switching still works on the toast
24:4824 minutes, 48 secondscomponent. Is it because we are using CSS class name for theme change? So,
24:5624 minutes, 56 secondslet's get an answer for this, right? Why is this working? This is what you can use AI for. Whenever you don't understand something, go ahead and ask
25:0525 minutes, 5 secondsit a question. and then we are going to see the answer. So this is how I intend to use AI in this tutorial. Not as a
25:1325 minutes, 13 secondsvibe coding but as a gentic coding to speed up what we would usually do by hand. So you will see that the curriculum for this project is very
25:2125 minutes, 21 secondssimilar to all other projects that I have. Meaning that we are not just going to randomly prompt uh finish the whole
25:2825 minutes, 28 secondsapp for me and do some weird loop and let it do its work autonomously. No, we are staying in control. You can see that
25:3625 minutes, 36 secondsI'm not satisfied with the way it rendered my toast component. So, I'm asking it is this the correct way to do so. So, let's see what it answered right
25:4525 minutes, 45 secondson both counts. The reason it works is because attribute class is what actually changes on the HTML tag. So, what is it
25:5325 minutes, 53 secondstalking about? We have this component called theme provider which was built in. And you can see that the attribute for next themes provider was set to
26:0326 minutes, 3 secondsclass. Meaning that whenever the theme changes, we don't programmatically change it using some API. We change the
26:1126 minutes, 11 secondswhole CSS attribute. I mean, we add a CSS attribute to the HTML tag. So that's why it worked. But I still think that it
26:2126 minutes, 21 secondsmakes sense to render the toaster inside of here. So yes, it's not necessary, but
26:2726 minutes, 27 secondsit is semantic. So the use theme value if ever used within Sonar gets the real value inside. And this is how it should look at the end. So let me close this.
26:3926 minutes, 39 secondsIn the layout.tsx, the toaster component should be rendered within the theme provider after the
26:4626 minutes, 46 secondschildren. And the page.tsx doesn't need any changes. Let's confirm one more time that this works. There we
26:5526 minutes, 55 secondsgo. So, nothing has changed because it uses the class attribute to change the theme. But now it is semantically
27:0327 minutes, 3 secondscorrect. And if we ever want to access the API within the toaster component, it will have the correct theme status.
27:1027 minutes, 10 secondsBrilliant. So, you just performed your very first agentic coding task. Let's go ahead and commit this changes. Get add,
27:1827 minutes, 18 secondsget commit, get push. Brilliant. Amazing job. and see you in the next chapter.
Chapter 4: Auth Setup
27:3127 minutes, 31 secondsNow that we have our project set up ready and we've prepared the environment for agentic coding, let's go ahead and add authentication. Building this
27:3927 minutes, 39 secondsyourself means creating login screens, registration screens, consent flows, client side logic, token validation, and
27:4727 minutes, 47 secondsuser management. Realistically, months of work before you even get to your actual product. Clerk reduces all of that to a few lines of code. Using the
27:5627 minutes, 56 secondslink on the screen, you'll land on Clerk's website. Once you're there, you can click the start building button, which will take you to the documentation
28:0428 minutes, 4 secondswhere you can grab the agentic prompt to paste straight into Claude Code. On their documentation page, you can find
28:1128 minutes, 11 secondsthe prompt needed to install Clerk in your project. You can of course also find the manual setup. If you've ever
28:1828 minutes, 18 secondsset up Clerk before, you are probably familiar with this. You install Clerk Nex.js package. You add the Clerk
28:2628 minutes, 26 secondsmiddleware to the proxy file. You then import the Clerk provider and you add the signin signup buttons and other
28:3428 minutes, 34 secondsClerk components. But recently I've been seeing more and more of this trend of software as a services adding a prompt
28:4228 minutes, 42 secondsto their documentation. So you can see that it is becoming increasingly relevant for us to learn agentic coding.
28:4928 minutes, 49 secondsSo let's do exactly that. I'm going to go ahead and copy this prompt and then I'm going to go into a new session in cloud code and I'm going to paste it
28:5728 minutes, 57 secondshere. And whenever you copy and paste prompts, make sure to at least scheme through the entire prompt to be aware of
29:0429 minutes, 4 secondswhat you are instructing your agent to do. Since this prompt came from a very reputable source, we can safely run it.
29:1229 minutes, 12 secondsBut it's always a good idea to simply go through the prompt to make sure that it is what you expect it to be. And in this
29:2029 minutes, 20 secondscase, it is exactly what we need, a prompt to set up clerk within our Nex.js JS app router project. So I am in auto
29:2829 minutes, 28 secondsmode and I'm just going to go ahead and let it do its thing. So before it did anything itself, it actually told me
29:3629 minutes, 36 secondswhat it's going to do. It's going to install or update the clerk CLI. It's going to set up clerk in this project or
29:4329 minutes, 43 secondsit's going to scaffold a new app if the directory is empty. Since we are not in an empty directory, it's just going to add clerk to this project. And then it's
29:5229 minutes, 52 secondsgoing to start the app with the clerk install. Great. So, this seems fine to me. And I also just want to tell you that I'm using [snorts] high effort in
30:0130 minutes, 1 secondcase that is relevant to you. So, I'm just going to go ahead and say proceed.
30:0530 minutes, 5 secondsLet's take a look what happened after I let it proceed. So, the first thing it did is it checked whether I have the
30:1230 minutes, 12 secondsclerk CLI installed. Since I didn't have it installed, the first thing it did is it globally installed the clerk CLI.
30:2130 minutes, 21 secondsAfter that, it attempted to run clerk out login. This is where some of you might have this entire setup interrupted
30:2930 minutes, 29 secondsbecause you needed to open a browser and actually log in. So if that happened to you, feel free to just say proceed once
30:3730 minutes, 37 secondsagain or just tell it I have now authenticated with clerk or maybe just open a brand new session and paste the entire prompt again now that you are
30:4630 minutes, 46 secondsauthenticated with clerk. So once the clerk CLI has authenticated you can see that it used clerk init framework next
30:5530 minutes, 55 secondsand it uses npm as the package manager because it recognized that that is what we are using. It successfully created a
31:0131 minutes, 1 secondproxy.ts TS file sign in and sign up pages and it wrapped the layout with clerk provider. Then it read through the
31:1031 minutes, 10 secondslayout and through the page and it also detected a chaten configuration which is very interesting and I'm going to show
31:1731 minutes, 17 secondsyou why. So here's a cool thing. It added clerk UI component and from clerk
31:2431 minutes, 24 secondsUI themes it imported chaten. So it added the appearance theme shhatzen to the clerk provider which basically means
31:3331 minutes, 33 secondsthat it has completely synchronized the theme to whatever our chaten theme is.
31:4031 minutes, 40 secondsIt also added the expected signin buttons and buttons here my apologies and other components here. It then run
31:4831 minutes, 48 secondsclerk doctor to verify the setup which is a very cool thing. Uh, I'm assuming it's some kind of CLI tool which just ensures that everything is as expected.
31:5831 minutes, 58 secondsAnd since it couldn't verify that the server was reachable, what it did is it modified the proxy.ts file such as that it added the homepage as a public route.
32:1132 minutes, 11 secondsI'm assuming you have something similar like this. The end result should be a successful clerk sign up. My apologies.
32:1932 minutes, 19 secondsSetup. So now let's go ahead and read through the actual diff instead. So [snorts] in the package JSON I have clerk nexjs and I have clerk UI added
32:2832 minutes, 28 secondshere. Let's go ahead and check the proxy.ds.
32:3332 minutes, 33 secondsSo clerk middleware create route matcher from clerk nextjs server. And we have a few public routes here. So we have the
32:4032 minutes, 40 secondssign in the sign up and it also added the default homepage as the public route which is I guess a smart idea so we can
32:4832 minutes, 48 secondstest whether it works or not. But we're going to see if we're going to remove this or not. Uh in here it's just a regular clerk middleware. Nothing special here and just a regular config.
32:5732 minutes, 57 secondsGreat. So that is the proxy.ts file which is located in the root of our application as you can see right here.
33:0533 minutes, 5 secondsNext. Next we have a layout.tsx update.
33:0833 minutes, 8 secondsSo in here we have a lot of changes. So it imported a bunch of components from next.js from clerk next.js. It imported
33:1533 minutes, 15 secondschassian from clerki themes. It even imported clerk UI themes shhatsen.css.
33:2133 minutes, 21 secondsIt also added a button here. It So I have some changes here which are unrelated which I'm guessing it's just my formatting. So you can ignore that.
33:3033 minutes, 30 secondsBut let's go ahead and actually focus on adding the clerk provider here. And then it just added the show component which
33:3733 minutes, 37 secondsonly shows when we are signed out and another show component which is only visible when signed in. And when it's
33:4533 minutes, 45 secondssigned in, it renders a user button. And when it's signed out, whoops. When it's signed out, it renders the sign in
33:5233 minutes, 52 secondsbutton or the sign up button. Very, very simple. If you want to see the full code because yours looks different, this is
34:0034 minutesmy entire body element. Let me even zoom in so you can see the entire HTML element. There we go. But also source code is available. And at the beginning
34:0834 minutes, 8 secondsof this chapter, you can actually see uh how this chapter will be named and the branch which you have to access to see
34:1534 minutes, 15 secondsthis exact code. So if yours looks drastically different or something is broken, you can simply copy the exact
34:2234 minutes, 22 secondsbranch which this chapter is on. or maybe more interesting for you to learn something uh point your agent to this
34:3134 minutes, 31 secondsproject's open-source branch for this chapter which I'm assuming would be 03 out setup. So try and do that instead
34:3934 minutes, 39 secondsand maybe ask your agent how can we get to this state and then it will tell you what are the differences and what it has
34:4734 minutes, 47 secondsto do to achieve this state. And the other things it did is it added two page files. Those two page files are inside
34:5534 minutes, 55 secondsof the app folder. Sign in and sign up both with their uh nested folders inside. There we go. page.tsx. If you've
35:0435 minutes, 4 secondsever set up clerk before, you are probably aware that this is just normal clerk setup, but we didn't have to do anything by hand. It did all of this for
35:1335 minutes, 13 secondsus. Now, it's time to check if this works or not. So, make sure you have your app running. So, the uh port is actually running. This might happen to
35:2135 minutes, 21 secondsyou as well. So what we can do here is just say kill port 3000 or if you know a
35:3035 minutes, 30 secondscommand you can uh do it yourself. There we go. Port 3000 cleared.
35:3635 minutes, 36 secondsLet's go ahead and do this again. There we go. Local host 3000. And there we go.
35:4235 minutes, 42 secondsSo you can see we now have a header which asks us to sign in or sign up. So if I go ahead and click sign in. There
35:5035 minutes, 50 secondswe go. I have to continue with Google to continue.
35:5435 minutes, 54 secondsAnd once I am signed in, I have a beautiful user button here. In one prompt, we added authentication to this
36:0236 minutes, 2 secondsproject. Amazing job. Now, let's go ahead and play just a little bit more with this and do something else. How
36:1136 minutes, 11 secondsabout we add a test route, which is supposed to be protected. So, right now, all of our routes are public. So I'm just going to do tell it to do the
36:1936 minutes, 19 secondsfollowing. Add a dummy page under test name which will be protected.
36:3136 minutes, 31 secondsDo not make it public in the proxy.
36:3536 minutes, 35 secondsDS. So add a dummy page under test name which will protected
36:4236 minutes, 42 secondsto test if redirect works. Do not run the server. I will be testing manually.
36:5036 minutes, 50 secondsSo I'm asking it to create a brand new uh Nex.js route on the client test page.
36:5636 minutes, 56 secondsAnd I just don't want it to be uh public. So as you can see right now, I have a brand new page.tsx
37:0537 minutes, 5 secondsunder the test folder inside of app. The content inside does not matter at all.
37:1137 minutes, 11 secondsSo don't worry if yours wasn't generated like this. So what do we want to test now? Well, we want to test whether we
37:1837 minutes, 18 secondscan go to test. There we go. This is what I expected would happen. I'm redirected to the login screen. So no
37:2537 minutes, 25 secondsmatter what I do, I cannot enter this test page unless I go into proxy.ts
37:3537 minutes, 35 secondsand add test here. If I do that,
37:4237 minutes, 42 secondsthen I am able to see the test page, but that's not what we want. Okay. So, I'm just testing whether everything truly works. There we go. And if I go ahead
37:5037 minutes, 50 secondsand log in again, there we go. Protected test page. And if I sign out from here, I'm redirected back to the root and I cannot access the test page. Brilliant.
38:0238 minutes, 2 secondsSo, we can now delete this test page because we don't actually need it. And we can leave the state of the authentication as is. So even though
38:1038 minutes, 10 secondswe're not really going to have this header, I think this is a pretty good stoppage point for us. So just like that, we've added whole authentication
38:1938 minutes, 19 secondsfrom one prompt. And since we are not vibe coding, we actually went through the git diff and we verified that this
38:2638 minutes, 26 secondsis what we want and that this actually works. So let's go ahead and add this changes and get push. One important
38:3438 minutes, 34 secondsthing I forgot to mention is that you should now have a environment or environment.local
38:4138 minutes, 41 secondsfile in your project which should now have clerk variables inside. So you should now have the next public clerk
38:4838 minutes, 48 secondspublishable key, the clerk secret key as well as the URLs for various routes like
38:5538 minutes, 55 secondssign in and sign up. What's important is that after you did git commit and git push is that that file isn't present
39:0439 minutes, 4 secondshere. So this file should always be in environment my apologies in ignore and
39:1139 minutes, 11 secondssince you did the exact same setup as me you will have this added. So it shouldn't be available in your git
39:2039 minutes, 20 secondsrepository right here. And if you go into clerk's dashboard, you should also see a brand new application here with
39:2739 minutes, 27 secondsthe name of your project. As you can see, browser automation is the exact name which it extracted from my package
39:3439 minutes, 34 secondsJSON. So that will be the name of your new project in clerk 2. And this will basically be your dashboard. So it's
39:4239 minutes, 42 secondsalso important that you verify that you have that as well. your users, your organizations, your billing, your logs
39:4939 minutes, 49 secondsand all other configuration is right here. Since we have connected the railway to our GitHub repository, every new push is going to cause a redeploy.
40:0040 minutesAnd in my scenario here, the redeployment actually fails. I'm not sure if this is going to happen to you
40:0740 minutes, 7 secondsor not, but I do want to share the fix with you anyway. By the description of the error that was given, it looks like package lock is in some kind of conflict
40:1640 minutes, 16 secondsor it's out of sync. So the only thing I did was run rmrf node modules and package lock.json.
40:2540 minutes, 25 secondsAfter that, I went ahead and run npm install and then I simply committed and
40:3240 minutes, 32 secondsthen get push. And you can see that once I did that, the deployment was successful. So that was the problem if
40:4140 minutes, 41 secondsyou are having the same error as me. One other thing you should add to railway to ensure that our deployment is working
40:4840 minutes, 48 secondsare environment variables which were automatically generated using the agentic prompt. So go inside of
40:5540 minutes, 55 secondsvariables tab, click on raw editor and simply paste the entire thing inside and click update variables and then click
41:0441 minutes, 4 secondsdeploy and then you can test clerk on your production instance.
Chapter 5: Organizations Setup
41:1541 minutes, 15 secondsNow that we've added authentication using clerk, let's also use their organizations feature to transform our
41:2141 minutes, 21 secondsproject from single tenant to a proper multi-tenant B2B application. The first thing I want to do is clean up some of
41:3041 minutes, 30 secondsthe things I don't like in our current authentication implementation. So because we needed to demonstrate that
41:3741 minutes, 37 secondsauthentication works, what we did is we enabled the home screen to be a public route. So that's the first thing I'm
41:4441 minutes, 44 secondsgoing to remove. I don't want the home screen to be a public route. Meaning that if I am signed out, the only route
41:5241 minutes, 52 secondsI want visible are the sign in and sign up routes. But as you can see, I have this weird header here and that is
41:5941 minutes, 59 secondsvisible on every single route because it was embedded in the layout file. So, that's the first thing that I'm going to
42:0642 minutes, 6 secondsremove. And depending on what code you have, it might not be in a header. It could just be rendered um in a normal
42:1542 minutes, 15 secondsdiv. So, here's what we can do. I'm going to go ahead and open cloud code.
42:1942 minutes, 19 secondsAnd since I'm already speaking whenever I type, I might just use text to speech, which you can also do using this icon
42:2742 minutes, 27 secondsright here, or any other app like Whisperflow, Super Whisper, or open- source tools like Handy. clean up my layout.tsx
42:3542 minutes, 35 secondsfile and make sure that there isn't any out logic inside besides the clerk provider. Meaning that I don't want any
42:4542 minutes, 45 secondsheader components which use clerk's show components or sign in and sign up buttons. All of that will be triggered from other pages not the root layout.
42:5742 minutes, 57 secondsAnd here is my prompt. So, exactly as I said, I don't want any out logic inside of my uh layout.tsx.
43:0743 minutes, 7 secondsSo, I'm just going to make sure that alph is properly spelled here. The only thing I don't want changed is the clerk provider. So, I just don't want to have
43:1543 minutes, 15 secondsany header components and I don't want to have any show components or sign in and sign up buttons. And let's go ahead
43:2243 minutes, 22 secondsand use auto mode with effort high on Oppus 4.8 to do this. There we go. It says done. The app layout now contains
43:3143 minutes, 31 secondsno AL UI. The header, the show, signin button, sign up button, user button, and
43:3843 minutes, 38 secondsunused button imports are all gone. Only the clerk provider, which wraps the theme provider, children, and toaster
43:4543 minutes, 45 secondsremains. So out actions can be triggered from individual pages. Perfect. So let's take a look at our current changes. In my layout.tsx,
43:5443 minutes, 54 secondsI have removed all imports from clerk next.js. JS. Besides the clerk provider, I have removed the unused button
44:0144 minutes, 1 secondcomponent. And now what I render is just a clerk provider which renders the theme provider and the children with the
44:0844 minutes, 8 secondstoaster inside. To show you the actual final code, this is what it looks like.
44:1344 minutes, 13 secondsSo very similar to what we had in the beginning. I just uh left the clerk UI themes shatzen css. I left the clerk UI
44:2144 minutes, 21 secondsthemes shhatzen and the clerk provider because all of that is important for clerk setup. But I don't want the actual clerk UI to be rendered here in my root
44:3044 minutes, 30 secondslayout file because that will make it visible everywhere. This is what I wanted. So when I log in, I will then be
44:3844 minutes, 38 secondsredirected to this page right here. But obviously we are now missing uh a log out button from here. So let's go ahead
44:4544 minutes, 45 secondsand add that as well. So just as we've cleaned this up, I'm now going to tell it the following. Now go ahead and clean up my page.tsx.
44:5444 minutes, 54 secondsThe only thing I want render rendered inside is the user button component from clerk.
45:0145 minutes, 1 secondLet's see if I did this correctly. So now go ahead and clean up my page.tsx.
45:0545 minutes, 5 secondsThe only thing I want rendered inside is the user button component from clerk. So I'm once again going to execute this in auto mode. This should be pretty simple.
45:1345 minutes, 13 secondsI uh don't want anything else rendered inside. And the reason we can safely render the user button inside app.page tsx. Let's take a look at this change
45:2145 minutes, 21 secondshere. So once again you can see I deleted everything in here and now it's much simpler actually my app page.tsx
45:3145 minutes, 31 secondsas you can see now only renders the user button. The reason we can now safely do this is because we have modified our proxy.ts.
45:3845 minutes, 38 secondsSo it no longer includes that homepage inside of the public route. If we accidentally left this then it would probably create some uh problems. But as
45:4745 minutes, 47 secondsyou can see now when user is logged in all they see is their user button. And if I sign out, I'm redirected to sign uh
45:5445 minutes, 54 secondsin or sign up pages. And if I try to manually go here, it redirects me back here. Perfect. So this is the uh setup
46:0346 minutes, 3 secondsthat I actually like that is easier for us to develop going forward rather than having to do it later. Before we add organizations, let's do one more thing.
46:1446 minutes, 14 secondsSo I don't like how my signin and signup folders are just here standalone in the app folder. I'd like to put them under
46:2246 minutes, 22 secondsone folder so that they are grouped together. But the problem is if we just create a brand new folder called out and then drag those two folders inside that
46:3146 minutes, 31 secondswould become the part of the URL. So I would have to use out sign in and that would require us to also change our
46:3946 minutes, 39 secondsenvironment variables here. So let's go ahead and use something called route groups. So I'm going to go ahead and open cloud code. I'm going to open a new
46:4746 minutes, 47 secondsconversation because this one is kind of unrelated. And I'm going to do the following. Go ahead and organize my signin and signup routes to all be under
46:5646 minutes, 56 secondsa singular Nex.js route group. Meaning you will have to use parenthesis in the folder name. And call that route group ALF.
47:0747 minutes, 7 secondsLooks like my pronunciation of ALF is not really good, but this is what I meant. Out. go ahead and organize my
47:1447 minutes, 14 secondssign in and sign up routes to all be under a singular Nex.js route group.
47:1847 minutes, 18 secondsMeaning you will have to use the parenthesis in the folder name and call that route group out. Let's go ahead and execute this and see the result. Let's
47:2747 minutes, 27 secondsgo ahead and look at its thought process because I think it's really interesting.
47:3147 minutes, 31 secondsSo it said I'll take a look at the current structure of the app directory and see the sign on sign in and sign up routes. And then what it did is the
47:3847 minutes, 38 secondsfollowing. Let me check the docs since Claude MD warns that this Nex.js version differs from what I know. And this is
47:4747 minutes, 47 secondsexactly why we added that symbolic link from agents MD to claude.m MD to instruct the whatever agent you're using
47:5647 minutes, 56 secondsthat this is not the next.js you know meaning not the next.js from their training data because that can be
48:0248 minutes, 2 secondsdrastically outdated. So what it did is it read from node modules next docs and
48:0948 minutes, 9 secondsin here it found routeg groupoups.md documentation and then it implemented exactly what I wanted an out folder in
48:1748 minutes, 17 secondsparenthesis that doesn't affect the URLs but lets us group files like this. So if you take a look at my uh file structure
48:2648 minutes, 26 secondsnow I now have an out folder and inside signin and signup route. So they were technically just moved here. But what's
48:3448 minutes, 34 secondsimportant is that they are in parenthesis. So nothing has really changed. Everything works exactly the way it worked before. If I go ahead and
48:4248 minutes, 42 secondstry to access localhost 3000, I'm once again redirected to sign in. And it works perfectly. And login also works of
48:5048 minutes, 50 secondscourse. Brilliant. So now we are ready to go ahead and focus on setting up organizations. One thing I would always
48:5848 minutes, 58 secondsrecommend whenever you do agentic coding is to create checkpoints so you don't lose your files because we just did a
49:0549 minutes, 5 secondssuccessful refactor of our homepage of our proxy of our layout and of our file
49:1249 minutes, 12 secondsstructure for the AL folder. So you can see that I have uh a combination of five staged and unstaged changes here. It's a
49:2149 minutes, 21 secondspretty good idea for me to commit this so that my upcoming prompts don't accidentally modify what I know works
49:2949 minutes, 29 secondsperfectly fine and so that I can always easily revert to this checkpoint if something goes wrong. So I'm going to go ahead and do git add small out refactor
49:3849 minutes, 38 secondsand get push. And now all of our changes are committed so we don't have to worry about them being overridden with some other prompt that we're going to do.
49:4649 minutes, 46 secondsWhenever you use Agentic coding to develop with a third-party tool, it's a good idea to make it aware of its
49:5449 minutes, 54 secondsdocumentation and how to use it properly. Because if it doesn't have that information, it's just going to rely on its training data or it's going
50:0350 minutes, 3 secondsto use some kind of web search which can waste a lot of tokens if it doesn't know what to look for. Thankfully, the clerk
50:1150 minutes, 11 secondsteam has prepared skills for us to add to our AI agent. And if you're wondering what is NPX skills, it is the facto
50:1950 minutes, 19 secondsstandard for distributing skills for AI agents. So you can find the exact same prompt by searching for clerk on
50:2650 minutes, 26 secondsskills.sh website. So whether you find the prompt from here or from here is the exact same thing. What's important is
50:3550 minutes, 35 secondsthat you are inside of your project and then go ahead and run this command. Now let's go ahead and choose which skills
50:4350 minutes, 43 secondswe're going to install. So I would recommend installing the entire core group because we are going to need all
50:5050 minutes, 50 secondsof these. Then let's go ahead and add all features as well. And under frameworks you can just select clerk
50:5750 minutes, 57 secondsnex.js patterns. You don't need to install the react patterns because the next.js patterns technically includes
51:0551 minutes, 5 secondsthat as well. The react patterns is more of a name if you're developing a single page application and are going to use
51:1251 minutes, 12 secondsspecific clerk react packages with vit for example. So you don't have to pick that even though we are using react and
51:2051 minutes, 20 secondsyou don't have to select anything else because we're not using anything on mobile and we're not using clerk with expo. So just make sure you've selected
51:2751 minutes, 27 secondsall the features. For me those are billing organizations and technically we don't need testing and web hooks. So you can actually remove those two. So just
51:3551 minutes, 35 secondsmake sure you have billing and organization selected. Now clerk setup custom UI CLI clerk backend API and clerk. I think all of these are useful
51:4351 minutes, 43 secondsto have even if we end up not using them but let's just leave them here and then go ahead and press enter. In here it's going to ask you for which agents you
51:5151 minutes, 51 secondswant to install this for. So just find your agent. I'm going to select cloud code here and down here you can find all other options. So if you are using
52:0052 minutessomething different go ahead and select that. So you can find uh open code here.
52:0452 minutes, 4 secondsYou can find codeex here. Basically whatever is the agent which you're using, go ahead and select it. You should see a green circle next to it.
52:1652 minutes, 16 secondsThen it's asking you where to install this. I would highly recommend picking project meaning install in the current directory. So these skills are committed
52:2452 minutes, 24 secondswith your project so that whoever picks up on this project can continue developing with it with the exact same agent instructions and skills. And for
52:3252 minutes, 32 secondsthe installation method, feel free to choose symbolic link which is a single source of truth with symbolic links to all other agents for which you want to
52:4152 minutes, 41 secondsinstall this for. And let's go ahead and proceed with the installation. You will now have a bunch of unsaved or should I say uncommitted changes in your project.
52:5152 minutes, 51 secondsSo don't worry all that is is updates in thecloud folder and agents folder with the exact skills which we have selected.
53:0053 minutesSo to make sure that these aren't interfering with the changes we are actually going to do what I would recommend is simply committing all of
53:0853 minutes, 8 secondsthem. So let's go ahead and do get commit feat add clerk skills as simple as that and then get push. This way you
53:1653 minutes, 16 secondsdon't have any uncommitted changes. So they are not interfering with the changes that we are actually going to do. Now let's go inside of cloud code,
53:2453 minutes, 24 secondsopen code, codeex, whatever you're using and verify that you actually have clerk skills available. So search for clerk like this and you should now see a bunch
53:3253 minutes, 32 secondsof commands which are basically clerk skills. If you're not seeing these commands, you can go ahead and use reload skills in cloud code which will
53:4053 minutes, 40 secondsadd new skills. And if that's still not working, you might have to close and reopen cloud code entirely or maybe your
53:4853 minutes, 48 secondsentire IDE if you're using an integration like I am. Let's go ahead and implement organizations. Now go
53:5653 minutes, 56 secondsahead and enable organizations in this clerk project. Go ahead and create a new
54:0254 minutes, 2 secondspage. Choose dash organization which is going to render the UI for choosing an organization using clerk components. Use clerk organization skill for this task.
54:1554 minutes, 15 secondsLet's take a look. So go ahead and enable organizations in this clerk project. Go ahead and create a new page.
54:2154 minutes, 21 secondsChoose dash organization. Let's call it organizations. Actually, no, it's organization, correct? Which is going to render the UI for choosing an organization using the clerk components.
54:3154 minutes, 31 secondsUse the clerk organization skill for this task. Let's go ahead and proceed with this prompt. Let's take a look at what it did. First, it decided it's
54:3954 minutes, 39 secondsgoing to use the clerk organization skill for this task exactly as we expected. Then, it explored the project structure to be aware of where it's
54:4854 minutes, 48 secondsworking. Then, it verified whether it can use the clerk CLI and whether we are authenticated with the clerk CLI. This
54:5654 minutes, 56 secondsis a very similar step as we did in our previous conversation uh where we set up clerk in the first place. So, at this
55:0355 minutes, 3 secondspoint, we already have the clerk CLI and we are authenticated with it. So then all it had to do is run clerk enable
55:1155 minutes, 11 secondsorganizations and that is essentially the same as us going onto the clerk dashboard and enabling organizations ourselves.
55:2055 minutes, 20 secondsThen it went ahead and created the choose organization page exactly as I've instructed it to do so. And it also
55:2855 minutes, 28 secondsregistered that new page choose organization in the clerk provider. And we can actually take a look at the
55:3455 minutes, 34 secondssummary down below. So first it enabled organizations in clerk via clerk enable organizations. The membership mode
55:4255 minutes, 42 secondsdefaults to membership required exactly as we expect. Society users without an organizations are routed through the
55:5055 minutes, 50 secondschoose organization session task. It created the page and it put it inside of the out route group. So it isn't terribly important if your agent didn't
55:5855 minutes, 58 secondsdo that. It's just for organization. If you want to, you can instruct it to move the choose organization page to the out
56:0656 minutes, 6 secondsroute group to be along sign in and sign up rendering clerk's task choose organization component which is the purpose-built UI for the choose
56:1456 minutes, 14 secondsorganization session task which redirects to the root on completion.
56:1956 minutes, 19 secondsPerfect. And then it wired that into clerk provider. Brilliant. This is exactly what we wanted. And there aren't that many changes actually. As you can
56:2756 minutes, 27 secondssee, we have a brand new choose-organization page, which now renders the task choose
56:3456 minutes, 34 secondsorganization within a div like this. And the other thing it did is it modified the layout.tsx
56:4256 minutes, 42 secondsso that the clerk provider now has task URLs. And when it when it comes to choose organization, so this is uh an enum. So if it misspells this, you will
56:5156 minutes, 51 secondshave an error, right? So it needs to be choose organization and it redirects to where? well to exactly the name which I
56:5856 minutes, 58 secondsspecified for the route since I knew that this is an enium in clerk that's why I chose this name so it matches so
57:0557 minutes, 5 secondsit makes sense right brilliant so let's go ahead and check it out now uh since I already have one account I'm actually
57:1357 minutes, 13 secondsnot sure how it's going to behave let's log in and see will it ask me to create an organization there we go so I'm redirected to tasks choose organization
57:2257 minutes, 22 secondsso I'm going to create Antonio's organization right here and then I'm redirected to this page. Brilliant. So now let's go ahead and add one more
57:3157 minutes, 31 secondsthing. So I'm going to tell you to do the following. Now go ahead and add organization switcher just beneath the user button in page.tsx.
57:4257 minutes, 42 secondsSo this way we can actually see which organization is currently active in our project. And there we go. So with just a
57:5057 minutes, 50 secondsvery simple uh simple prompt, it added an organization switcher which allows me to create another organization like
57:5957 minutes, 59 secondsthis. And I can now click create organization. I can also send invites
58:0758 minutes, 7 secondsand I can decide whether that's going to be a member or an admin.
58:1458 minutes, 14 secondsAnd from the organization switcher, I can always change between organizations.
58:1958 minutes, 19 secondsJust like that, we've implemented an entire B2B suite in our project. And if you go ahead and visit the organizations
58:2658 minutes, 26 secondsin your clerk dashboard, you will now see that you have those two organizations right here. You can also verify by going inside of configure
58:3458 minutes, 34 secondsorganization settings. Make sure that you have membership required set to the active option even though that is a
58:4258 minutes, 42 secondsstandard. In here you can also find some other settings for the organizations but for now I would recommend leaving it as is.
58:5258 minutes, 52 secondsAnd before we commit I just want to demonstrate how the sign up flow and organization creation or organization
58:5958 minutes, 59 secondsselection flow looks now in a completely new account. So I'm going to go ahead and click continue with Google and I'm
59:0759 minutes, 7 secondsgoing to enter with a brand new account here and let's see what happens. So the first thing here is the ability to join
59:1659 minutes, 16 secondsan organization that I'm actually invited to or I can create a new organization. So this is only visible to
59:2459 minutes, 24 secondsme because I invited myself to this organization. But if I go ahead and just create my organization, you will see that instead I have an invitation here.
59:3459 minutes, 34 secondsSo I have one as in one notification, meaning that this is something I am invited into. And now I'm part of the
59:4259 minutes, 42 secondssame organization as I am in this browser right here. And that is how we are going to implement multi-tenency and
59:5159 minutes, 51 secondslive collaboration in the canvas. So let's go together through our changes before we commit. So first things first,
59:5959 minutes, 59 secondsthe clerk provider now has task URLs which redirect the choose organization task to a specific route. Choose organization. No new imports have been
1:00:071 hour, 7 secondsadded, just a simple prop to the clerk provider. Next, we have the actual uh organization switcher added to under our
1:00:161 hour, 16 secondsuser button. The organization switcher is a component imported from the same place as the user button. So this is in our uh global page.tsx.
1:00:261 hour, 26 secondsAnd the last thing that's been added is inside of our out route group, we now have choose- organization which has a page which renders the task choose organization from clerk next.js.
1:00:381 hour, 38 secondsBrilliant. So let's go ahead and commit all of this. Get add and let's do get push. After I pushed these changes to my
1:00:451 hour, 45 secondsGitHub repository, Railway did an automatic deployment and something caused it to fail. And it wasn't until
1:00:521 hour, 52 secondscloser inspection that I found a very interesting error. If you take a look at this error message, which you may or may
1:01:001 hour, 1 minutenot have, perhaps they've changed this in the future, but my error message specifically mentions. Claude folder skills and then clerk nex.js patterns.
1:01:131 hour, 1 minute, 13 secondsNow, at first, I didn't understand how could this file or folder possibly cause
1:01:201 hour, 1 minute, 20 secondsthe deployment to fail. So, I went into my codebase and I found that exact
1:01:271 hour, 1 minute, 27 secondsfolder. So, inside of Cloud or inside of agents, if that's what you use, you should have clerk Next.js patterns. And
1:01:351 hour, 1 minute, 35 secondsthen I found this templates folder. And then it clicked for me. inside they have a very small replica of a nex.js application with its own package JSON.
1:01:481 hour, 1 minute, 48 secondsSo that is probably what confused railway or rail packs and causes the deployment to fail. Luckily for us the
1:01:571 hour, 1 minute, 57 secondsfix is very simple. All that we need to do is create a new file dot docker ignore and inside put claude and agents.
1:02:091 hour, 2 minutes, 9 secondsSo these two folders because agents also has the exact same templates inside. Then go ahead and commit those files.
1:02:181 hour, 2 minutes, 18 secondsAnd once you push this, it's going to trigger the redeployment once again. And that will result in a successful
1:02:251 hour, 2 minutes, 25 secondsdeployment. So adding docker ignore and adding those files or folders inside skips the attempt of rail packs to uh
1:02:351 hour, 2 minutes, 35 secondsinitialize that or build that as a standalone nex.js. GS application and successfully deploys our application instead.
Chapter 6: Dashboard Layout
1:02:491 hour, 2 minutes, 49 secondsIn this chapter, we're going to develop the dashboard layout. And for that we're going to need to do some architectural changes but also add some design
1:02:581 hour, 2 minutes, 58 secondsscreenshots so that we can tag them into cloud code, open code or codeex so that we can instruct our agents exactly how
1:03:061 hour, 3 minutes, 6 secondswe want our layout to look like. So let's go ahead and create a new folder called design. And inside of that folder
1:03:141 hour, 3 minutes, 14 secondsgo ahead and add all of these screenshots of the UI which I've prepared for you. Using the link on the
1:03:211 hour, 3 minutes, 21 secondsscreen, you can access this project's open-source repository. And once you are here, just make sure that you are either
1:03:281 hour, 3 minutes, 28 secondson the main branch or in chapter 05, which is the chapter that I'm recording
1:03:351 hour, 3 minutes, 35 secondsright now. So obviously I don't have it yet. And then once you're here, you will be able to find the designs folder,
1:03:441 hour, 3 minutes, 44 secondswhich we are going to commit now. And while you are in the repository, go ahead and do one more thing. This is
1:03:511 hour, 3 minutes, 51 secondsalso very important because it's going to dictate the look and feel of our application. Again, make sure that you are on the main branch or in chapter 05.
1:04:041 hour, 4 minutes, 4 secondsAnd once you're there, go inside of app, go inside of globals.css
1:04:101 hour, 4 minutes, 10 secondsand copy the entire file. and then go inside of app your globals.css
1:04:191 hour, 4 minutes, 19 secondsand replace it entirely. So some of the differences you're going to notice immediately
1:04:261 hour, 4 minutes, 26 secondsare things like these little snippets that enable the pointer cursor for the buttons when they are not disabled.
1:04:351 hour, 4 minutes, 35 secondsOther things that are different are specific colors in the dark mode and also some general variables like radius
1:04:441 hour, 4 minutes, 44 secondshave been changed. So just make sure that you update your globals.css according to my GitHub repositories
1:04:521 hour, 4 minutes, 52 secondsglobals.css file. Again just make sure you are on the main branch or in chapter05 and then go inside of app globals.css.
1:05:031 hour, 5 minutes, 3 secondscopy the entire thing and replace your global CSS. And now you should have around 17 changes. Don't take my word
1:05:121 hour, 5 minutes, 12 secondsfor it because maybe I will add more design images if I find that some are missing throughout this tutorial. What's
1:05:201 hour, 5 minutes, 20 secondsimportant is that right now the only uncommitted changes you have are globals. CSS and then just a bunch of
1:05:281 hour, 5 minutes, 28 secondsimages. Right? I'm not sure what is the exact number that I'm going to leave here. I might even remove some if you
1:05:351 hour, 5 minutes, 35 secondsend up not using them. But just make sure it looks something like this. And using the diff viewer, you can actually
1:05:431 hour, 5 minutes, 43 secondssee which differences you are supposed to have uh in your globals.css here. So looks like I also added clerk UI themes shhatzen.css.
1:05:531 hour, 5 minutes, 53 secondsI've replaced the radius and I've just replaced some of the colors uh in the dark mode. and added this right here.
1:06:011 hour, 6 minutes, 1 secondSo, not too much, but just enough to make our app look and feel a little bit better. So, I'm not really sure if we
1:06:091 hour, 6 minutes, 9 secondsactually need this clerk UI themes chaten.css because I think we already have it here,
1:06:161 hour, 6 minutes, 16 secondsbut I think it won't hurt being here as well. I don't know. I'm going to leave it as is. And if it causes any problems,
1:06:231 hour, 6 minutes, 23 secondsI'm going to remove it. So let's go ahead and actually do get add, get commit, and get push. So we can continue
1:06:311 hour, 6 minutes, 31 secondsdeveloping this chapter without having a bunch of uncommitted changes confusing us. So we don't know what is the code change and what is just some style
1:06:401 hour, 6 minutes, 40 secondschange. So go ahead and run your app and then visit it on localhost 3000. What you should look out for is that clerk
1:06:481 hour, 6 minutes, 48 secondsstyling looks fine. So you should have the user button working. You should have the organization switcher working and pressing the letter D on your keyboard
1:06:571 hour, 6 minutes, 57 secondsshould still switch to light mode and clerk design should follow. So I'm pretty certain at this point that we
1:07:051 hour, 7 minutes, 5 secondsactually no longer need this here because it's imported in globals.css.
1:07:111 hour, 7 minutes, 11 secondsSo if we actually remove this, I think everything will work just fine. But it's not causing any problems either. So I
1:07:201 hour, 7 minutes, 20 secondswill just leave it here and if I do notice any problems I'm going to remove it later or I will just clean up with AI
1:07:271 hour, 7 minutes, 27 secondslater. Great. So now let's go ahead and let's actually uh take a look at what we've added in the design here. So what
1:07:351 hour, 7 minutes, 35 secondsI've added here are mostly some atomic design screenshots about individual elements about sidebars uh full design
1:07:431 hour, 7 minutes, 43 secondslooks uh some empty states logs logs with different variants some other empty
1:07:491 hour, 7 minutes, 49 secondsstates specific uh node data looks editor states things like that which
1:07:571 hour, 7 minutes, 57 secondswill help us instruct our agent into how we want our app to look like. This isn't necessarily required. It's just so we
1:08:051 hour, 8 minutes, 5 secondshave some kind of reference. So you don't have to look through the web to find something that you like, but you have it all here. Usually you can do
1:08:131 hour, 8 minutes, 13 secondsthis through Figma as well. And the problem is if you want to use Figma MCP server and connect it to Cloud Code, for
1:08:211 hour, 8 minutes, 21 secondsexample, you unfortunately need a Figma paid plan. And I didn't want to do that as the default in this tutorial because
1:08:281 hour, 8 minutes, 28 secondsI understand not many of you want to update to Figma Premium just to follow a tutorial. So because of that, screenshots are the better choice here.
1:08:371 hour, 8 minutes, 37 secondsSo let's go ahead and actually try using this design right here. No workflow selected. So what I'm going to do is I'm
1:08:451 hour, 8 minutes, 45 secondsgoing to open cloud code and I'm going to tell it the following. Modify page.tsx and make sure you pick the one in the
1:08:531 hour, 8 minutes, 53 secondsapp folder. So the root page.tsx so that it uses empty components from
1:09:001 hour, 9 minutescomponents UI and it recreates the contents of no workflow selected PNG.
1:09:091 hour, 9 minutes, 9 secondsAnd once again I'm in auto mode with high effort. So let's see if it will be able to replicate that. It appears to
1:09:161 hour, 9 minutes, 16 secondshave completed its task. Let's see if it actually looks as I've expected. There we go. No workflow selected. Select a
1:09:241 hour, 9 minutes, 24 secondsworkflow from the sidebar or create a new one to get started. That is pretty close. Probably identical. Brilliant.
1:09:331 hour, 9 minutes, 33 secondsNow, let's go ahead and actually create a sidebar once again using Shatzen components. And let's prepare the
1:09:411 hour, 9 minutes, 41 secondsfollowing. Not the right sidebar. This is something else. So, make sure you choose the app sidebar. This is the one
1:09:491 hour, 9 minutes, 49 secondswhich we are going to recreate now. So, as you can see, we're going to have uh an organization switcher at the top.
1:09:551 hour, 9 minutes, 55 secondsThen, we're going to have uh workflows section with items inside, and we're going to have a user button at the
1:10:031 hour, 10 minutes, 3 secondsbottom. So, some questions we have to answer here are how do we display I mean, how do we keep the data for these workflows? Because we don't yet have any
1:10:111 hour, 10 minutes, 11 secondsdatabase. So, I'm going to instruct it to just keep a dummy array of things like this. And this button right here
1:10:191 hour, 10 minutes, 19 secondsshould collapse the sidebar to icon variant. So it will be interesting to see how we are going to uh develop this.
1:10:281 hour, 10 minutes, 28 secondsThe plus button can't do anything at the moment. Let's do one architectural change before we proceed and that is by
1:10:361 hour, 10 minutes, 36 secondscreating a new route group called dashboard and then simply drag and drop the root
1:10:431 hour, 10 minutes, 43 secondspage inside of that route group. This way the URL of our root hasn't changed
1:10:521 hour, 10 minutes, 52 secondsbut now we can maintain page within this folder right here. And also we can
1:11:001 hour, 11 minutescreate a layout file inside of that folder as well. This was a problem previously because we would override
1:11:071 hour, 11 minutes, 7 secondsthis layout but this layout is the root layout for the entire application. So we shouldn't actually add the sidebar here.
1:11:171 hour, 11 minutes, 17 secondsWhy not? Because in this root layout there are other pages which are rendered like choose organization, sign in and
1:11:251 hour, 11 minutes, 25 secondssign up. None of those should have a sidebar. So that's why we have to create a new route group. And when you drag and
1:11:341 hour, 11 minutes, 34 secondsdrop the page inside of dashboard, it can happen that you have this weird unsaved file coming from the next
1:11:411 hour, 11 minutes, 41 secondsfolder. This is regenerated every time you run the app. So you don't have to worry about this file at all. You can
1:11:481 hour, 11 minutes, 48 secondsjust close it and save it and forget about it. So it's this is a next folder.
1:11:531 hour, 11 minutes, 53 secondsMake sure you close it so it doesn't interfere with your work. So nothing changes now. Everything is exactly as it
1:12:011 hour, 12 minutes, 1 secondwas before. We didn't change absolutely anything. But now we can create a layout file inside of here and then instruct
1:12:091 hour, 12 minutes, 9 secondsthe agent to develop that with the sidebar. This is how our prompt is going to look like. Create a new layout file
1:12:181 hour, 12 minutes, 18 secondsin the dashboard route group which encapsulates the root page. DSX. We are first giving it instructions on where
1:12:261 hour, 12 minutes, 26 secondsthis is going to be developed. inside cascade a new sidebar from our components UI and everything it needs to
1:12:351 hour, 12 minutes, 35 secondsrender and function properly. So this will include things like sidebar provider and the entire semantic order
1:12:441 hour, 12 minutes, 44 secondsit needs to actually work. Develop the actual sidebar content inside a new component called
1:12:531 hour, 12 minutes, 53 secondsapp sidebar and put it in the components folder. So there is a difference between this sidebar and the app sidebar. The
1:13:021 hour, 13 minutes, 2 secondsapp sidebar will be a new component which will have the UI which we expect,
1:13:091 hour, 13 minutes, 9 secondsright? But what's going to be inside of the layout file in the dashboard is just going to be the sidebar chaten
1:13:161 hour, 13 minutes, 16 secondscomposition that will allow us to render this. And we're going to maintain this in the components folder. I'm then
1:13:251 hour, 13 minutes, 25 secondstelling it to utilize sidebar header to render clerk's organization switcher and utilize sidebar footer to render clerk's
1:13:331 hour, 13 minutes, 33 secondsuser button inside. In between, render a dummy list of workflows using sidebar items and buttons. And of course, I tell
1:13:421 hour, 13 minutes, 42 secondsit use the app sidebar PNG as design reference. Once again, Oppus 4.8 auto
1:13:501 hour, 13 minutes, 50 secondsmode effort high. Let's see what it comes up with. Let's take a look at the summary and then let's take a look at
1:13:571 hour, 13 minutes, 57 secondsthe actual result. So it says done. Two files created no type errors. First layout.tsx which now wraps the route
1:14:041 hour, 14 minutes, 4 secondsgroup in page.tsx. It adds a sidebar provider. It renders the app sidebar which is a new custom component and it uses a sidebar inset. Perfect.
1:14:151 hour, 14 minutes, 15 secondsAll of that is handled. So what it's saying here is basically describing how the sidebar component works. So we don't have to do anything here.
1:14:241 hour, 14 minutes, 24 secondsAnd then inside of the app sidebar, it did exactly what I wanted. So it used it used clerk organization switcher and it added it inside of sidebar header
1:14:321 hour, 14 minutes, 32 secondsalongside the sidebar trigger collapse button. So this is something that I didn't tell it to do. I actually forgot that. But it saw the design and in the
1:14:421 hour, 14 minutes, 42 secondsdesign there actually is a collapse button. The sidebar content are the workflows using sidebar group label and
1:14:491 hour, 14 minutes, 49 secondsa sidebar group action and then a dummy workflow list. So judging by this summary, this looks great. Let's take a
1:14:561 hour, 14 minutes, 56 secondslook at the code now. So what we have here is that we deleted the original page.tsx,
1:15:041 hour, 15 minutes, 4 secondsright? And we moved it here into the dashboard. And then inside of the layout here, we added sidebar inset and sidebar
1:15:111 hour, 15 minutes, 11 secondsprovider from components UI sidebar. So very simple dashboard layout file. So that's the new file which was created
1:15:181 hour, 15 minutes, 18 secondsand then it renders the app sidebar and this is the actual content. So use client great. So import from react
1:15:281 hour, 15 minutes, 28 secondsorganization switcher user button plus icon a bunch of imports from components UI sidebar a dummy list of our workflows
1:15:351 hour, 15 minutes, 35 secondsand then an export app sidebar. So in here we have uh active workflow and set active workflow. This isn't needed. Uh, and we're going to change this later.
1:15:451 hour, 15 minutes, 45 secondsSo, the reason it added this is because in the design here in the app sidebar,
1:15:521 hour, 15 minutes, 52 secondsyou can see that I have one workflow selected. So, it obviously wanted to replicate that as well. Obviously, we're
1:16:001 hour, 16 minutesgoing to maintain this using the URL, but I guess for now, it wants us to if your app didn't do this, perfectly fine.
1:16:101 hour, 16 minutes, 10 secondsNot needed. There will be no user state in our app sidebar. So don't worry.
1:16:151 hour, 16 minutes, 15 secondsOkay, let's take a look at the actual composition. So we have a sidebar.
1:16:181 hour, 16 minutes, 18 secondsGreat. Then we have sidebar header. In here we have a div which renders the organization switcher. It added the hide
1:16:271 hour, 16 minutes, 27 secondspersonal prop which is great because we don't support personal accounts. It added the appearance prop where it modified the elements like root box flex
1:16:341 hour, 16 minutes, 34 secondsone and organization switcher trigger with with full and justify between. We are going to see if this works for us or not. Next to it, we have the sidebar
1:16:431 hour, 16 minutes, 43 secondstrigger. So that's it for the sidebar header component. Then we have the sidebar content. In here, we have sidebar group, sidebar group label,
1:16:511 hour, 16 minutes, 51 secondsworkflows, and then a sidebar group action plus icon. Perfect. So if you're not following that is this right here.
1:16:591 hour, 16 minutes, 59 secondsSo this is a sidebar group label and this is a sidebar group action. A plus button.
1:17:051 hour, 17 minutes, 5 secondsUh let me keep this image open. So because I keep losing it.
1:17:121 hour, 17 minutes, 12 secondsAnd let's see what else do we have. So we now have sidebar group content, sidebar menu. And then using sidebar menu item and menu button, we basically
1:17:201 hour, 17 minutes, 20 secondshave the workflow text rendered and a little is active here which is maintained using that state which I told
1:17:261 hour, 17 minutes, 26 secondsyou isn't really needed. If your AI didn't implement that, no worries, you don't need it here. And that's it for the sidebar content. So all of these are
1:17:341 hour, 17 minutes, 34 secondsjust closing tags. And then we have sidebar footer which renders the user button once again uh with some appearance. Uh I'm not sure about the
1:17:431 hour, 17 minutes, 43 secondsshow name prop. I think we are not going to need that. So let's go ahead and take a look. Wow, this is incredible. This is
1:17:521 hour, 17 minutes, 52 secondsso close to our picture here. Take a look. So the only thing as I said I'm not sure of is the fact that we are displaying the name here. I kind of
1:18:001 hour, 18 minutesdon't think it looks good. And also we have this uh Nex.js GS indicator here.
1:18:061 hour, 18 minutes, 6 secondsSo what we can do for that is we can quickly go I mean you can just ask AI to do it for you but since it's pretty
1:18:131 hour, 18 minutes, 13 secondsquick just go inside of next config.ts dev indicators and set it to be false.
1:18:201 hour, 18 minutes, 20 secondsThere we go. And then it disappears.
1:18:241 hour, 18 minutes, 24 secondsPerfect. Wow. So this is pretty impressive. The only problem is there we go. We have a bug. the the sidebar collapse hides the entire sidebar.
1:18:351 hour, 18 minutes, 35 secondsThat's not what we want. We want it to collapse to icon mode, but we're going to have to do something about that.
1:18:411 hour, 18 minutes, 41 secondsGreat. So, I'm pretty satisfied with this.
1:18:471 hour, 18 minutes, 47 secondsYep, this looks fine. Perhaps we can add maybe a little bit of a gap between these elements. And I'm also going to remove this. So, let's go ahead and do
1:18:541 hour, 18 minutes, 54 secondsuh some of those tiny little changes by hand. So, we can remove show name. I think that's the first thing I can remove. And let me take a look at how
1:19:021 hour, 19 minutes, 2 secondsthat looks like. There we go. So, I'm not really sure if I really need these elements in that case, especially user
1:19:091 hour, 19 minutes, 9 secondsbutton trigger. I don't think I need that. Maybe the width full. So, it takes the whole space. But yeah, the other one is definitely not needed. Uh, brilliant.
1:19:201 hour, 19 minutes, 20 secondsLet's take a look at what else we have here. So, sidebar menu. Well, perhaps we can add a class name and do something like gap Y 0.5.
1:19:321 hour, 19 minutes, 32 secondsAnd then there's going to be like the tiniest space between these two elements. I think that looks uh very
1:19:401 hour, 19 minutes, 40 secondsvery good. Uh, brilliant. So now I'm going to continue here and I'm going to tell it the following.
1:19:461 hour, 19 minutes, 46 secondsThe sidebar collapse button should collapse to sidebars icon variant.
1:19:531 hour, 19 minutes, 53 secondsmeaning that it should still be visible and it shouldn't disappear completely when collapsed. There we go. So, this is my prompt and I'm just going to continue
1:20:001 hour, 20 minutesin the same conversation because it is relevant to what I want to change. Let's take a look at its changes. So, it imported the workflow icon because it
1:20:081 hour, 20 minutes, 8 secondsassumes we're going to need to render icons now when the sidebar is collapsed.
1:20:141 hour, 20 minutes, 14 secondsNext, it added the collapsible icon prop to our app sidebar.
1:20:201 hour, 20 minutes, 20 secondsThen it added a tool tip and a workflow icon to every single workflow rendered
1:20:281 hour, 20 minutes, 28 secondsin the workflow in the sidebar content because when collapsed and when you hover over it, it will show that tool
1:20:351 hour, 20 minutes, 35 secondstip. I'm going to show you that in a second. So it also told us one thing to be aware of in the header. The clerk organization switcher sits next to the
1:20:441 hour, 20 minutes, 44 secondstrigger and won't shrink gracefully into the rail. Its trigger will get clipped when collapsed. The sidebar trigger
1:20:521 hour, 20 minutes, 52 secondsitself stays visible and functional. So collapse expand works. If you want header to look clean while collapsed, the usual move is to swap the
1:21:011 hour, 21 minutes, 1 secondorganization switcher for just the organizational logo icon visibility classes. So let's take a look at what we currently have and then we're going to
1:21:081 hour, 21 minutes, 8 secondsdecide what to do with this. So let me refresh to see if this is something uh broken. Oh, there we go. Let's take a look at what happened here now.
1:21:181 hour, 21 minutes, 18 secondsSo app sidebar we have collapsible icon and then we have props. So I'm not really sure what is causing
1:21:261 hour, 21 minutes, 26 secondsuh this error right here. Let me maybe check this here. Uh I see this is one
1:21:341 hour, 21 minutes, 34 secondsthing we forgot to do when we added a tool tip. So chances are if you told your AI to do this as well and if inside
1:21:431 hour, 21 minutes, 43 secondsof app sidebar you have imported uh actually you didn't have to import
1:21:501 hour, 21 minutes, 50 secondsanything. The collapsible icon inside of sidebar uses tool tip and the only way tool tip can
1:21:591 hour, 21 minutes, 59 secondswork is if it's added to the layout file to the root layout. So, we are
1:22:061 hour, 22 minutes, 6 secondsencountering an error now. And honestly, this exact error isn't that useful. This
1:22:151 hour, 22 minutes, 15 secondsone is super weird. But the second error is very clear. Tool tip cannot be used outside uh of tool tip provider. So,
1:22:241 hour, 22 minutes, 24 secondslet's go ahead and actually add this right here. And I'm just going to go ahead and go back inside of clot code and let's do a quick fix. So
1:22:341 hour, 22 minutes, 34 secondsvariant actually collapsible icon makes the sidebar component use or
1:22:441 hour, 22 minutes, 44 secondsshould I say render the tool tip component. We never added the tool tip provider.
1:22:531 hour, 22 minutes, 53 secondsSo let's go ahead and tell it to fix that. Should be a pretty easy fix. It should just add the tool tip provider to our root layout the same way we have
1:23:021 hour, 23 minutes, 2 secondstheme provider. So we can already open this. Let's go ahead inside of our app folder layout.tsx.
1:23:111 hour, 23 minutes, 11 secondsSo the same way we have theme provider and toaster. Let's go ahead and see if it's going to add it here or maybe it will add it in this layout which
1:23:191 hour, 23 minutes, 19 secondstechnically works but I would prefer it actually does it somewhere else. So there we go. Sidebar provider now wraps its children in tool tip provider.
1:23:301 hour, 23 minutes, 30 secondsOkay, so that is not what we wanted to do. So watch happens once an AI does something incorrectly.
1:23:391 hour, 23 minutes, 39 secondsOkay, what you can do here whether you're using uh clo code or open codecs
1:23:461 hour, 23 minutes, 46 secondsmost of them have a reind functionality which you can either use by invoking a command like this if you are in the CLI
1:23:541 hour, 23 minutes, 54 secondsor you can click on the message like this. So, let me try using the reind here and let me go ahead and click this
1:24:021 hour, 24 minutes, 2 secondsone, which is basically the collapsible icon makes the sidebar component um makes the sidebar component uh use the
1:24:101 hour, 24 minutes, 10 secondstool tip. So, I'm just going to say continue. So, what happened now? Well, what happened now is that I reverted the
1:24:171 hour, 24 minutes, 17 secondscode that was generated in my last message. Okay, so I am technically back to where I was a moment ago. So, let me
1:24:271 hour, 24 minutes, 27 secondsgo ahead and add something else. Make sure to fix this in the root layout. And let's select the layout in the app and nowhere else.
1:24:391 hour, 24 minutes, 39 secondsThis time we are going to do it with more context and we're going to get a better result. So now we can confidently
1:24:461 hour, 24 minutes, 46 secondsopen the root layout file. So in here layout.tsx.
1:24:531 hour, 24 minutes, 53 secondsAnd there we go. You can see that now it has added the tool tip provider within the theme provider. So these things
1:25:001 hour, 25 minuteshappen, right? You technically didn't even have to rebind. You could just told it, hey, I wanted you to add this to the
1:25:071 hour, 25 minutes, 7 secondsroot layout and not modify uh the sidebar component. So just in case you are uh a bit overwhelmed now, still
1:25:161 hour, 25 minutes, 16 secondsnothing uh scary has happened. So these are our current changes. We disabled the dev indicators.
1:25:231 hour, 25 minutes, 23 secondsNow we added the tool tip provider to the root layout file right here.
1:25:311 hour, 25 minutes, 31 secondsWe moved the page inside of the dashboard. So this technically isn't a change, but we did fill it with a very nice empty component. We have a new
1:25:401 hour, 25 minutes, 40 secondslayout within app dashboard which renders the sidebar uh composition sidebar inset to render the children and
1:25:481 hour, 25 minutes, 48 secondsour custom component app sidebar. And instead of app sidebar, we added collapsible icon, which broke the app because it used the tool tip component.
1:25:571 hour, 25 minutes, 57 secondsSo now that we've added that tool tip component, we should be able to do this.
1:26:021 hour, 26 minutes, 2 secondsThere we go. So obviously not perfect, but we are getting to that point of making it look exactly how we want. So
1:26:101 hour, 26 minutes, 10 secondswhat sticks out the most at the moment is this broken organization switcher right here. I think it's easier for us
1:26:181 hour, 26 minutes, 18 secondsto simply hide the organization switcher. So the user will have to expand to full mode if they want to change organization. So let's go inside
1:26:251 hour, 26 minutes, 25 secondsof app sidebar here and let's change the root box to have the following class name. We are going to target if group data is collapsible icon and then we're
1:26:341 hour, 26 minutes, 34 secondsgoing to set it to be hidden with an exclamation point like this. And once you collapse now you can see that it is hidden. But I'm not sure if you notice
1:26:421 hour, 26 minutes, 42 secondsbut it's not perfectly aligned. there's like uh a little extra space here which it shouldn't be. You can see that this
1:26:501 hour, 26 minutes, 50 secondsisn't exactly centered as this is. So, let's go ahead and add a little class name here to fix that. What I'm going to do is I'm going to get rid of this div
1:26:591 hour, 26 minutes, 59 secondsand just have the sidebar header directly render both the organization switcher and the sidebar trigger. And
1:27:071 hour, 27 minutes, 7 secondsthen I'm going to give the give the sidebar header this class name right here. So I'm basically adding the exact
1:27:141 hour, 27 minutes, 14 secondssame class name it had before in a div and I'm also giving it if group data is
1:27:201 hour, 27 minutes, 20 secondscollapsible icon then use justify center and then once again if group data is collapsible icon set the gap to zero and
1:27:301 hour, 27 minutes, 30 secondsthen you will notice that this is now perfectly centered below this. There we go. So what now we have a very very
1:27:381 hour, 27 minutes, 38 secondssmooth collapse and uh expand functionality. Great. One thing I'm still seeing is missing is a variant here.
1:27:491 hour, 27 minutes, 49 secondsAnd let's set it to inset.
1:27:521 hour, 27 minutes, 52 secondsThere we go. I'm not sure if you noticed the difference, but now uh this has kind of like a encapsulating look. Take a look at how it looks without this.
1:28:051 hour, 28 minutes, 5 secondsYou can see it's just like a a very strict line here. But if you use variant
1:28:111 hour, 28 minutes, 11 secondsinset, then it looks much nicer. But it does add this overflow. So let's see how we can fix that. Let's go ahead and open
1:28:211 hour, 28 minutes, 21 secondsour dashboard layout.tsx and let's go inside of the sidebar provider and let's add a class name
1:28:291 hour, 28 minutes, 29 secondsheight h SVH like this.
1:28:361 hour, 28 minutes, 36 secondsAnd then on the sidebar inset, let's go ahead and add the following class name.
1:28:431 hour, 28 minutes, 43 secondsAnd this should completely eliminate the overflow. There we go. You can see how nice and encapsulated this sidebar insert looks. Now there is no overflow.
1:28:531 hour, 28 minutes, 53 secondsI cannot scroll up and down. uh as opposed to what we previously had. You can see it looks weird and you can
1:29:021 hour, 29 minutes, 2 secondsscroll and there's no visible border. So by adding these two classes, I mean class names, it looks much much better.
1:29:091 hour, 29 minutes, 9 secondsNow, let's also make sure that the user button correctly centers when collapsed because right now, once again, I'm not
1:29:171 hour, 29 minutes, 17 secondssure if you can see, but I can notice that there's too much space here. And I'm just a sucker for these details and
1:29:241 hour, 29 minutes, 24 secondsI have to fix them. So, let's go inside of the app sidebar here. Let's find the sidebar footer and let's go ahead and
1:29:311 hour, 29 minutes, 31 secondsgive it the following class name. And then let's modify two more elements in the user button appearance prop. So add
1:29:381 hour, 29 minutes, 38 secondsthis to user button trigger and this to user button outer identifier. So make sure you have these classes and then
1:29:471 hour, 29 minutes, 47 secondswhen collapsed you can see it's perfectly centered. Everything is aligned. Lovely. So what I don't like
1:29:561 hour, 29 minutes, 56 secondsright now is the fact that each of my workflow has an icon. Obviously this was
1:30:041 hour, 30 minutes, 4 secondsadded so that they can be displayed when in collapsed mode but there are better ways of doing this but to save the
1:30:131 hour, 30 minutes, 13 secondsprogress that we have let's go ahead and actually commit this. So get add get commit feet add dashboard
1:30:231 hour, 30 minutes, 23 secondslayout and app sidebar and get push. So, we have a checkpoint
1:30:301 hour, 30 minutes, 30 secondsfor what's currently working. We have a working sidebar. We have a nice inset uh
1:30:371 hour, 30 minutes, 37 secondscontent here. And we even have a nice empty state. So, we created a checkpoint. And now, we're going to create a new prompt, which is going to
1:30:461 hour, 30 minutes, 46 secondsmodify this so it looks a little bit nicer. Let's take a look at how we actually want the collapsed state to
1:30:541 hour, 30 minutes, 54 secondslook like. So what we saw already is the expanded app sidebar. Obviously we want
1:31:001 hour, 31 minutesto get rid of these icons. But when the sidebar is collapsed, we actually want
1:31:071 hour, 31 minutes, 7 secondsthis to happen. We want just one workflow icon which when clicked on opens a popover which renders a bunch of
1:31:161 hour, 31 minutes, 16 secondsworkflows inside as well as a button to create a new workflow. And when closed, it's just a normal icon beneath the
1:31:251 hour, 31 minutes, 25 secondssidebar collapse instead of being this, right? So, it's actually going to look exactly like this without all the other
1:31:331 hour, 31 minutes, 33 secondsoptions. And when we click on it, it will open a popover component like that.
1:31:381 hour, 31 minutes, 38 secondsSo, let's go ahead and prepare a prompt that's going to do that. The first thing I'd like to review is how our app sidebar looks at the moment. So, make
1:31:471 hour, 31 minutes, 47 secondssure that you are inside of this component. So right now app sidebar is a component which is responsible for
1:31:551 hour, 31 minutes, 55 secondsmaintaining the active workflow which we said we're going to remove anyway but still right now at least my version is
1:32:031 hour, 32 minutes, 3 secondsresponsible for this. So let's think. So I will now instruct it to maintain two different states. One when sidebar is
1:32:121 hour, 32 minutes, 12 secondsexpanded like this and then another when sidebar is collapsed like this. So, it's going to need to have some kind of if
1:32:201 hour, 32 minutes, 20 secondsclause to detect when the sidebar is in collapsed mode or it should use CSS for that, right? It's going to have to
1:32:281 hour, 32 minutes, 28 secondshandle something. So, here's what I'm thinking in my prompt. I actually want to include the following as well. I'm
1:32:361 hour, 32 minutes, 36 secondsthinking of entirely getting rid of what's inside of sidebar content. So,
1:32:431 hour, 32 minutes, 43 secondsthe entire sidebar group like this. and instead just rendering something like workflow navigation a new component and then developing that here.
1:32:561 hour, 32 minutes, 56 secondsSo a brand new function and then this component is going to be responsible
1:33:031 hour, 33 minutes, 3 secondsfor rendering the workflows and for maintaining which workflow is active.
1:33:101 hour, 33 minutes, 10 secondsRight? because I could just have if state is expanded here.
1:33:161 hour, 33 minutes, 16 secondsIn that case, let's return popover, right? This is just pseudo code, right?
1:33:221 hour, 33 minutes, 22 secondsBut I think you're getting the idea of what I want to do. So, let me just revert that state because none of this will be exactly like this. So, we are
1:33:311 hour, 33 minutes, 31 secondsback to uh where we were. Let me just do this. There we go. And now let's go ahead and create a brand new prompt for
1:33:401 hour, 33 minutes, 40 secondsthis. This is the prompt that we are going to execute. Refactor the workflow list in components app sidebar so it
1:33:471 hour, 33 minutes, 47 secondsadapts to whether the sidebar is expanded or collapsed. Pull the whole thing into a new component called workflow nav defined in the same file.
1:33:581 hour, 33 minutes, 58 secondsIt should own both states. Use the use sidebar hook from components UI sidebar
1:34:051 hour, 34 minutes, 5 secondsto know which state you are in. When you are in expanded, render the full list of workflows just like now. But remove the
1:34:141 hour, 34 minutes, 14 secondsicon from the workflow items because right now every item has one and I don't want any of them. When in collapsed mode, don't render the list at all.
1:34:241 hour, 34 minutes, 24 secondsInstead, render a single button with the workflow icon. This is the only icon in the whole thing.
1:34:311 hour, 34 minutes, 31 secondsClicking it opens a popover containing the list of workflows plus a button to create a new one. Don't track the
1:34:391 hour, 34 minutes, 39 secondspopover's open state yourself. Let the popover trigger handle that. And don't build custom components or write custom
1:34:471 hour, 34 minutes, 47 secondsCSS to match the design. Just use the default popover and sidebar components that already exist. And then we pass
1:34:551 hour, 34 minutes, 55 secondsalong the design reference which we uh previously showed. So, collapsed app sidebar and collapsed app sidebar
1:35:011 hour, 35 minutes, 1 secondworkflow list. And I added this because I wanted to understand that I really
1:35:081 hour, 35 minutes, 8 secondsdon't like that every workflow has the icon, but perhaps it will misunderstand this. So, I might remove this part actually. So, I think this is a pretty
1:35:171 hour, 35 minutes, 17 secondssolid plan for us to do. Let's go ahead and implement this in auto mode. Effort high oppus 4.8. Let's take a look at the
1:35:251 hour, 35 minutes, 25 secondssummary of the result. So the workflow list is now a contained workflow nav component which is defined within the
1:35:321 hour, 35 minutes, 32 secondsapp sidebar that reads the sidebar state via use sidebar and owns both layouts.
1:35:381 hour, 35 minutes, 38 secondsThe expanded where the full list well the full workflow list is exactly as before but with the per item workflow
1:35:451 hour, 35 minutes, 45 secondsicon removed. Then we have a collapsed no list just one sidebar menu button with the workflow icon that acts as a
1:35:531 hour, 35 minutes, 53 secondspopover trigger. The popover holds a new workflow button, a separator and the workflow list. So it extracted that from
1:36:001 hour, 36 minutesthe design which we gave it. Notes on the constraints you set. Popover open state is handled entirely by the trigger. No state tracked in the
1:36:091 hour, 36 minutes, 9 secondscomponent. Only existing popover and sidebar primitives are used and only a few class name tweaks to override
1:36:161 hour, 36 minutes, 16 secondsspacing. I am good with that. The active workflow state and workflow items are shared between both branches. So selection is consistent when whichever
1:36:251 hour, 36 minutes, 25 secondslayout renders. Type check passes with no errors for the file. Brilliant. Let's take a look at the actual change.
1:36:331 hour, 36 minutes, 33 secondsSo inside of the app sidebar, it seems like we've now imported the popover components. We added sidebar separator, sidebar trigger, and use sidebar here.
1:36:441 hour, 36 minutes, 44 secondsAnd we have a brand new component called workflow nav. And in here we are using a hook use sidebar. and the React use
1:36:531 hour, 36 minutes, 53 secondsstate which maintains the currently active workflow. And in here we render differently depending if the state is
1:37:011 hour, 37 minutes, 1 secondcollapsed in which we simply render a popover with a popover trigger with a sidebar menu button and then we render a
1:37:081 hour, 37 minutes, 8 secondslist of sidebar menu items within the popover content. Brilliant. Otherwise, if it's expanded, we do exactly what we
1:37:151 hour, 37 minutes, 15 secondsdid before. Looks like we have workflow items set in a variable. So it's only uh
1:37:221 hour, 37 minutes, 22 secondsdefined once and then we reuse it uh depending on state collapsed in the sidebar menu here within the popover
1:37:311 hour, 37 minutes, 31 secondscontent or inside of the sidebar menu right here. Brilliant. Very clean solution. And now we have actually freed
1:37:391 hour, 37 minutes, 39 secondsthe app sidebar uh from having to maintain all of that. And inside of the sidebar content we just render workflow
1:37:461 hour, 37 minutes, 46 secondsnav. Beautiful. Exactly what we imagined. So let's now go ahead and take a look at how the design looks like.
1:37:571 hour, 37 minutes, 57 secondsPerfect. This is exactly what I wanted.
1:37:591 hour, 37 minutes, 59 secondsSo tool tip is here. That's fine. We can work without it, but it might actually be useful. And when I click, we have a
1:38:061 hour, 38 minutes, 6 secondsnew workflow. We have a separator and we have a list of elements. One redundant thing is this tool tip right here.
1:38:141 hour, 38 minutes, 14 secondsThat's definitely not needed. Let's take a look at the expanded mode. Beautiful.
1:38:191 hour, 38 minutes, 19 secondsPerfect. So, such a clean implementation of this. Let's go ahead inside of the app sidebar now and let's just clean
1:38:271 hour, 38 minutes, 27 secondsthings up a little bit. So, I I can actually use uh the same session here.
1:38:341 hour, 38 minutes, 34 secondsAnd I can just tell it uh one thing.
1:38:381 hour, 38 minutes, 38 secondsRemove the tool tip for the popover content. I think that should be clean enough.
1:38:471 hour, 38 minutes, 47 secondsremove the tool tip for the popover content. Basically, I don't want uh let me go ahead and just expand a little
1:38:551 hour, 38 minutes, 55 secondsbit more. I don't want this to be having tool tips. So, let me go ahead and maybe
1:39:031 hour, 39 minutes, 3 secondstake a screenshot because I can't explain myself. Well, so now I didn't want you to remove uh
1:39:111 hour, 39 minutes, 11 secondsthe tool tip for the workflows button. I want you to remove the tool tip for workflows list which is rendered within the popover content.
1:39:211 hour, 39 minutes, 21 secondsAnd then I'm going to attach u a screenshot. So let me go ahead and just expand this.
1:39:301 hour, 39 minutes, 30 secondsThere we go.
1:39:341 hour, 39 minutes, 34 secondsSo now it will see the redundancy because it is redundant.
1:39:401 hour, 39 minutes, 40 secondsThere we go. So, I didn't want you to remove the tool tip for the workflows button because that's what it understood me it wants. Whether your agent did that
1:39:491 hour, 39 minutes, 49 secondsor not, it's not really important, right? But I'm just explaining that I didn't want that. I wanted you to remove the tool tip for the workflow list which is rendered within the popover cont uh
1:39:571 hour, 39 minutes, 57 secondscontent because it is redundant. So, you don't have to obsess over this as much as I am. Uh I just want to get rid of
1:40:041 hour, 40 minutes, 4 secondsthese tool tips and let's see if it'll be able to do that. Maybe we can detect it in real time.
1:40:121 hour, 40 minutes, 12 secondsUh, let's see. [snorts] Yes, the problem is that it has to keep it in the expanded list, but it actually I'm not
1:40:221 hour, 40 minutes, 22 secondssure it needs it anywhere. Let me take a look at the workflow nav here.
1:40:311 hour, 40 minutes, 31 secondsIt thinks it needs to have the tool tip here. So, it's over complicating. Now, this is the biggest problem when working
1:40:381 hour, 40 minutes, 38 secondsuh on high thinking with agentic coding because it tends to overthink.
1:40:441 hour, 40 minutes, 44 secondsSo, here's what I'm just going to tell it now. We don't need the tool tip in either state.
1:40:531 hour, 40 minutes, 53 secondsSo, I I it completely over complicated what is a very simple change. Uh and
1:41:001 hour, 41 minutesyes, these things happen with agentic coding and they can actually be reduced by noticing patterns like this and then
1:41:091 hour, 41 minutes, 9 secondsupdating uh your claude or agents.md file. So it can detect situations like this and just not give you so much opposition or such over complicating.
1:41:211 hour, 41 minutes, 21 secondsAnd obviously different models behave differently. Perhaps yours didn't do anything like this. Let's take a look
1:41:281 hour, 41 minutes, 28 secondsnow. There we go. This is something that I like. Brilliant. This is exactly how I
1:41:351 hour, 41 minutes, 35 secondswant this to look like. So now I'm going to go ahead and just do one more thing uh here. So instead of workflow items
1:41:431 hour, 41 minutes, 43 secondshere, I think in this sidebar menu I have this gap, but in this one I don't. So I'm just going to add it here. So I've added
1:41:511 hour, 41 minutes, 51 secondsthe class name for uh the popover content. So this one has the exact same tiny little gap between elements.
1:41:591 hour, 41 minutes, 59 secondsBrilliant. I'm very very happy with this solution right here. So now that we have this working, I actually want to
1:42:071 hour, 42 minutes, 7 secondscompletely separate this workflow nav component which we've developed here using aentic coding into its own file.
1:42:161 hour, 42 minutes, 16 secondsThe reason I want to do this is because workflow nav is a client component whereas app sidebar at least the plans
1:42:241 hour, 42 minutes, 24 secondsthat I have for it is going to be a server component meaning that we cannot develop both in the same file. Okay, it
1:42:311 hour, 42 minutes, 31 secondswas easier for us to use a gent coding to develop it here. But let's actually separate them now. So I'm going to tell
1:42:361 hour, 42 minutes, 36 secondsit to move the workflow nav component to a new location
1:42:441 hour, 42 minutes, 44 secondsand that location is going to be the following. So a brand new features
1:42:511 hour, 42 minutes, 51 secondsfolder and then workflows components and then workflow-nav.tsx
1:42:581 hour, 42 minutes, 58 secondsand then remove the use client from the app sidebar.
1:43:061 hour, 43 minutes, 6 secondsremember to add use client to the new separated workflow nav component.
1:43:151 hour, 43 minutes, 15 secondsSo that's what we are doing. We are now separating these two components. We are putting workflow nav in a brand new location in features uh workflows
1:43:231 hour, 43 minutes, 23 secondscomponents workflow nav and then we are removing the use client tag from components app sidebar. So the workflow
1:43:311 hour, 43 minutes, 31 secondsnav is the one which is going to have use client because that's going to be the reactive component. So let's go ahead and submit this as well. And there we go. Created workflows. My apologies.
1:43:411 hour, 43 minutes, 41 secondsFeatures workflows components workflow nav with use client exporting the workflow nav and the workflows data that it owns. So I didn't ask for that
1:43:491 hour, 43 minutes, 49 secondsbecause this is just dummy data. So it doesn't really matter. The components app sidebar no longer has use client.
1:43:551 hour, 43 minutes, 55 secondsIt's now a server component that imports workflow nav and only keeps the sidebar shell. Perfect. Let's take a look at this new output. So, first things first,
1:44:041 hour, 44 minutes, 4 secondslet's take a look at the changes within the app sidebar. It's much simpler now.
1:44:081 hour, 44 minutes, 8 secondsAs you can see, we just import workflow nav from its new location and all we do is render it in the sidebar content. We
1:44:151 hour, 44 minutes, 15 secondsno longer develop that component in here. So, we got rid of a bunch of unused imports from the popover and other things. And now we should also
1:44:231 hour, 44 minutes, 23 secondshave a brand new folder called features, workflows, components, workflow nav. And in here we now have use client. That's
1:44:311 hour, 44 minutes, 31 secondsimportant. And we now have the workflow nav component. Beautiful. So visually, design-wise, nothing is going to change.
1:44:411 hour, 44 minutes, 41 secondsBut now the app sidebar is no longer a client component, meaning that we can use it as a server component and directly access the database and load
1:44:491 hour, 44 minutes, 49 secondsthe workflows when we actually have a database to load from. So just verify that everything still works uh in your
1:44:571 hour, 44 minutes, 57 secondsproject. The last problem we have before we can uh close this chapter is the fact that the sidebar is still being somewhat
1:45:061 hour, 45 minutes, 6 secondsin mobile mode when fully collapsed. So it disappears entirely.
1:45:121 hour, 45 minutes, 12 secondsWorkflow apps are really not possible to be developed for mobile. Technically they are but they are never good. So in
1:45:211 hour, 45 minutes, 21 secondsour solution what we are just going to do is we're going to make sure that the sidebar never completely disappears. So users will be able to do this which is
1:45:291 hour, 45 minutes, 29 secondsenough to enable work on tablets but uh on mobile it's just not going to be as usable and it really makes no sense to completely hide the sidebar because that just makes the app completely unusable.
1:45:401 hour, 45 minutes, 40 secondsIn order to make the sidebar behave this way, let's go ahead directly inside of components UI and then go ahead and find
1:45:501 hour, 45 minutes, 50 secondsthe sidebar component. So thanks to chats and UI, we can actually take a look at the contents of our sidebar. In
1:45:561 hour, 45 minutes, 56 secondshere, find the function sidebar provider. And when it comes to the variable is mobile, simply set it to be false.
1:46:061 hour, 46 minutes, 6 secondsThen you can also remove this unused import right here. So just make sure that the sidebar provider has been set
1:46:131 hour, 46 minutes, 13 secondsto false. So this just by itself is not really enough. You can see that it still collapses. That is because we need to
1:46:211 hour, 46 minutes, 21 secondschange some CSS class names in the actual sidebar component. So go ahead and find sidebar. So scroll a bit down
1:46:311 hour, 46 minutes, 31 secondsand after this big block is mobile, you're going to see uh this div which by
1:46:391 hour, 46 minutes, 39 secondsdefault is hidden and only uh block on medium viewpoint. Now you can completely reverse that. So make it block by
1:46:481 hour, 46 minutes, 48 secondsdefault. And then if you scroll a bit down here, you will find the same thing in the sidebar container. So it's hidden
1:46:561 hour, 46 minutes, 56 secondsby default. And only on medium view port viewport does it become flex. So let's change that. And let's replace hidden
1:47:041 hour, 47 minutes, 4 secondswith flex. If it's easier for you, you can just go inside of my source code and copy the sidebar.tsx component. But this should basically do
1:47:131 hour, 47 minutes, 13 secondsit. Let me verify. There we go. No matter how small the device now, it is not going to collapse. So, let's go
1:47:221 hour, 47 minutes, 22 secondsahead and do get add, get commit, and let's do get push. Amazing job, and see you in the next chapter.
Chapter 7: Database Setup
1:47:371 hour, 47 minutes, 37 secondsNow, let's go ahead and set up a database and Drizzle RM in our project.
1:47:421 hour, 47 minutes, 42 secondsWe're going to set up a Postgress database using Neon using the link on the screen. You can get on their homepage. Once you're here, I would
1:47:501 hour, 47 minutes, 50 secondshighly recommend creating an account first and then once you have an account, go back here and go into the
1:47:581 hour, 47 minutes, 58 secondsdocumentation. The reason I'm telling you to create an account first is because once we run this one command
1:48:051 hour, 48 minutes, 5 secondssetup, it is going to ask you to authenticate. So, you need to have a Neon account ready. So, just go ahead
1:48:141 hour, 48 minutes, 14 secondsand sign up and then go back to documentation. Let's go ahead and use Neon's one command setup to add a
1:48:211 hour, 48 minutes, 21 secondsdatabase schema and even Drizzle ORM to our project. So, inside of our terminal, let's execute npx neon latest in it.
1:48:321 hour, 48 minutes, 32 secondsLet's select database for the option and then let's select install with defaults meaning MCP server and agent skills.
1:48:441 hour, 48 minutes, 44 secondsThis will also install a VS code extension if you are inside of VS Code.
1:48:491 hour, 48 minutes, 49 secondsAnd now you have to authorize the neon CLI. So that's why I told you to create an account first and then go back here.
1:48:571 hour, 48 minutes, 57 secondsIn here it will output which user you are currently logged in with. Once it finishes, it's going to look something
1:49:041 hour, 49 minutes, 4 secondslike this. It's going to tell you what it did, such as confirming whether Neon CDL CLI is up to date, that it added a
1:49:121 hour, 49 minutes, 12 secondsNeon MCP server for VS Code, and that it installed some agent skills. It will then give you the next steps. Copy the
1:49:211 hour, 49 minutes, 21 secondsfollowing into your agent chat. If you have Cloud Code opened at this moment, I would recommend restarting it. or if
1:49:301 hour, 49 minutes, 30 secondsyou're using a visual extension like me, go ahead and do reload window. So a
1:49:361 hour, 49 minutes, 36 secondsbrand new cloud code session opens and then let's go ahead and copy this and add it to our agent. So paste that
1:49:451 hour, 49 minutes, 45 secondsprompt into cloud code, open code, codeex, whatever you are using and let's see what's going to happen. If you're
1:49:521 hour, 49 minutes, 52 secondsusing cloud code, it can sometimes be a bit careful and it's not going to automatically do what we told it to do.
1:50:011 hour, 50 minutes, 1 secondAnd it will slightly explain that here.
1:50:041 hour, 50 minutes, 4 secondsSo it says the following. I see a neon onboarding prompt suggesting I run
1:50:101 hour, 50 minutes, 10 secondsneonctl init agent. Before I run anything, I want to check with you. That command kicks off Neon's cloud
1:50:181 hour, 50 minutes, 18 secondsonboarding creating linking a Neon Poscres project to your account which is an outward-facing action I shouldn't
1:50:261 hour, 50 minutes, 26 secondstake on my own. So, uh it's basically being careful and just making sure that we want to do this. So, what I'm going
1:50:341 hour, 50 minutes, 34 secondsto do is I'm going to select the first option run neonct in it. If your agent
1:50:421 hour, 50 minutes, 42 secondsdid a similar thing but didn't give you these options, you can just manually tell it run neon ctl in it or just proceed with the instructions as told.
1:50:521 hour, 50 minutes, 52 secondsRight? You don't need explanation. You don't need to skip anything. So just make sure to run neonctl in it. Let's
1:50:591 hour, 50 minutes, 59 secondstake a look at what it did. So the first thing it attempted to do is run neonctl in it. and that failed because neon CDL
1:51:091 hour, 51 minutes, 9 secondsisn't installed on our machine. So what it did then is it decided to simply run it using npx.
1:51:161 hour, 51 minutes, 16 secondsThen it reloaded my organizations. Since I have a brand new account, I only have one organization. There we go. Only one
1:51:241 hour, 51 minutes, 24 secondsorganization. So it will automatically use that organization. If you happen to have many organizations on Neon, it will
1:51:321 hour, 51 minutes, 32 secondsprobably ask you which one you want to use. Then it did the same with projects in this organization. Since I have no
1:51:401 hour, 51 minutes, 40 secondsexisting projects, it will simply create a new one called browser automation which matches this directory and my
1:51:471 hour, 51 minutes, 47 secondspackage JSON. If you would have a lot of projects, it would probably ask you if you want to use an existing one or if
1:51:541 hour, 51 minutes, 54 secondsyou wanted to create a new one. And then it created a brand new project for me as you can see here. and it updated the
1:52:021 hour, 52 minutes, 2 secondsneon context file with the information about the organization and the new database here. It also wrote the
1:52:101 hour, 52 minutes, 10 secondsenvironment variables to environment local and it also installed the neon uh serverless driver. Brilliant. Looks like
1:52:191 hour, 52 minutes, 19 secondsit also did a very simple select one against the database to verify that it worked. And once it verified the connection, it finalized the onboarding.
1:52:301 hour, 52 minutes, 30 secondsAnd here is that exact summary. So you should have something similar. And the next question it's asking me here is do I want to set up a schema or an ORM?
1:52:411 hour, 52 minutes, 41 secondsNext. Before we proceed with setting up a schema and OM, I want to bring something to your attention. So right
1:52:481 hour, 52 minutes, 48 secondsnow if I try to invoke any neon scale, it actually says I have no matching commands. That is because if you take a
1:52:561 hour, 52 minutes, 56 secondslook at the files which were added here, we do have some skills but they were
1:53:021 hour, 53 minutes, 2 secondsadded inside of agents folder. So these are skills which are available to all
1:53:101 hour, 53 minutes, 10 secondsother coding agents except claude. Don't ask me why we don't have one standardized pattern for this but it is
1:53:201 hour, 53 minutes, 20 secondsthe way it is. So that's why we actually can't see any of these two skills. So to fix that very easily, go back to neon, go into develop and find the AI section.
1:53:311 hour, 53 minutes, 31 secondsYou can click on AI for agents and down here in the table of contents, find agent skills. Then click on this right
1:53:401 hour, 53 minutes, 40 secondshere and that will tell you uh that will show you the NPX skills for Neon
1:53:471 hour, 53 minutes, 47 secondsdatabase. If you want to use uh this page here, you should also be able to find it through here. There we go. Neon database agent skills.
1:53:571 hour, 53 minutes, 57 secondsOkay. So, let's go ahead and simply run this npx skills. Let me close this. Let
1:54:041 hour, 54 minutes, 4 secondsme close that. npx skills. Add neon database agent skills. And now it's going to ask us which one we want to
1:54:101 hour, 54 minutes, 10 secondsinstall. So, select neon and select neon posgress. Why those two? Because those are the two which have been added in our
1:54:181 hour, 54 minutes, 18 secondsagents. Okay. So, now we want to do the same for cloud code. So that's why we want those two even though technically we no longer need the neon skill because
1:54:271 hour, 54 minutes, 27 secondswe just installed it. But still let's keep it inside just in case. But the neon posgress might be the more important one. And make sure that cloud
1:54:351 hour, 54 minutes, 35 secondscode is selected this time. And make sure you choose the project installation scope and symbolic link and proceed with
1:54:441 hour, 54 minutes, 44 secondsthe installation. And now you should see cloud skills for neon and neon
1:54:511 hour, 54 minutes, 51 secondspostgress. And now if you go here and if you do reload skills, ignore this. I've
1:54:591 hour, 54 minutes, 59 secondsbeen testing whether I have some skills or not. Uh you will see that uh for me it says no changes because in this exact
1:55:071 hour, 55 minutes, 7 secondssession I actually did add neon posress but I reverted it. But for you it might tell you that you now have one more skill. If you try, it will still not be
1:55:171 hour, 55 minutes, 17 secondsvisible until you do reload window or restart your Visual Studio Code. Try then and there we go. You will now have
1:55:251 hour, 55 minutes, 25 secondsNeon and Neon posgress. So if you're using the CLI, simply restart the CLI and you will have these two available.
1:55:331 hour, 55 minutes, 33 secondsSo now that we have Neon Skills installed, let's go ahead and use one of the prompts that they actually recommend. So this is really cool. At
1:55:421 hour, 55 minutes, 42 secondsthe bottom of this page that we are on, we actually have example prompts and one of them is set up drizzle ORM with neon.
1:55:491 hour, 55 minutes, 49 secondsPretty cool. Let's go ahead and try it out. So set up a drizzle OM with neon and it might be a good idea to tell it to use the neon postgress scale. Once
1:55:581 hour, 55 minutes, 58 secondsagain, I'm in auto mode effort high with oppus 4.8. Let's see what it's going to come up with. Let's take a look at the
1:56:061 hour, 56 minutes, 6 secondsoutput of this prompt. So it detected that we invoked the neon postgress scale. So the first thing it did was
1:56:141 hour, 56 minutes, 14 secondsloaded that skill. Then it inspected the current project state. And this is where I was getting a little bit worried
1:56:221 hour, 56 minutes, 22 secondsbecause I didn't know where is it going to get the knowledge about Drizzle OM
1:56:281 hour, 56 minutes, 28 secondsbecause we don't have any Drizzle skills, right? So I was worried that it might use some outdated training data.
1:56:371 hour, 56 minutes, 37 secondsBut look at this. Thankfully we invoked this skill. That is exactly why they were so confident with giving us this as
1:56:451 hour, 56 minutes, 45 secondsthe example prompt. So it basically analyzed our app. We have app router Nex.js16
1:56:521 hour, 56 minutes, 52 secondsno source folder and we use neon database serverless package which was installed in this uh chapter. We didn't
1:57:001 hour, 57 minutesdo it manually. We did it using uh npx uh neon in it. Okay. And it also
1:57:081 hour, 57 minutes, 8 secondsdetected no drizzle yet. And then it said, "Let me fetch the current official neon plus drizzle guide so I match their
1:57:151 hour, 57 minutes, 15 secondslatest convention." And would you look at that? Thanks to the neon postgress skill, they actually direct the agent to
1:57:231 hour, 57 minutes, 23 secondsuse this guide which teaches the agent how to set up Drizzle OM with Neon.
1:57:291 hour, 57 minutes, 29 secondsWonderful, wonderful guide here. So, it had the entire plan to implement this.
1:57:351 hour, 57 minutes, 35 secondsSo, it first decided that the code is going to live in the lib folder. It decided the driver it's going to use. It
1:57:431 hour, 57 minutes, 43 secondsdecided which files it's going to create. So we have lib database schema and lib database index which exports the database util a separate drizzle config
1:57:521 hour, 57 minutes, 52 secondsfile some environment variables like database URL and it even added scripts like generate migrate database push and
1:58:011 hour, 58 minutes, 1 seconddatabase studios. So the first thing it did is it installed all of the packages like drizzle o and it it installed a
1:58:081 hour, 58 minutes, 8 secondsdeveloper uh sorry development dependency drizzle kit and environment.
1:58:131 hour, 58 minutes, 13 secondsSo three packages in total. Then it wrote the drizzleconfig.ts wonderfully I assume and the database
1:58:211 hour, 58 minutes, 21 secondsindex.ts and then a very simple schema and then it created all of the scripts here. So overall a very very very smooth integration here better than I expected.
1:58:331 hour, 58 minutes, 33 secondsLet's take a look at the actual code here. So in here we have the drizzle config.ts
1:58:401 hour, 58 minutes, 40 secondswhich is just a usual define config. It targets our schema file in lib database schema, our out in lib database
1:58:491 hour, 58 minutes, 49 secondsmigrations, our dialect set to posgress and our database credentials set to be the migration URL which is essentially
1:58:561 hour, 58 minutes, 56 secondsreading from the environment file database URL unpulled or database URL.
1:59:021 hour, 59 minutes, 2 secondsSo yes, that was also added for us. If you do find your uh environment.local, you will find the database URL and
1:59:101 hour, 59 minutes, 10 secondsdatabase URL unpulled. So you don't have to worry about that either. So drizzle config definitely good. Then let's go
1:59:181 hour, 59 minutes, 18 secondsahead and take a look at the other file which is inside of the lib here. So we now have database folder and in here we
1:59:261 hour, 59 minutes, 26 secondshave a schema. So this is our schema. It doesn't matter if yours looks like this or not because obviously we are going to change this but it probably did create
1:59:351 hour, 59 minutes, 35 secondssome schema. And it also added an index.ts which is basically just the database util. So uh we can basically
1:59:441 hour, 59 minutes, 44 secondsimport it if we want to import it somewhere.
1:59:471 hour, 59 minutes, 47 secondsBrilliant. And if you take a look inside of your uh neon dashboard inside of your project here. So browser automation
1:59:561 hour, 59 minutes, 56 secondsthat's the project I'm in. Go inside of tables and in here you will see that it has successfully uh pushed the migration
2:00:052 hours, 5 secondsof that new schema. So we have ID, clerk ID, email name, created at basically exactly what's written here. ID, clerk
2:00:132 hours, 13 secondsID, email name, and created at updated at. Brilliant. So I'm very happy with this. One thing I'm not too happy about
2:00:202 hours, 20 secondsis that it automatically added migrations. Migrations are obviously the production way of doing things, but in development, they cause more problems
2:00:292 hours, 29 secondsthan solutions. So we are mostly just going to use database push instead of doing the whole migration. So what should you verify that you have?
2:00:392 hours, 39 secondsRemember you can always actually look at this chapters branch to verify things.
2:00:432 hours, 43 secondsBut in the lip folder you should have a database with index and with a schema.
2:00:492 hours, 49 secondsWe should also have a drizzle.config.ts ts file which basically exports define config and make sure that the schema and
2:00:582 hours, 58 secondsout uh match the lib folder which we verified a second ago. At this point we already have 14 uncommitted changes. So
2:01:072 hours, 1 minute, 7 secondsit would be a pretty good idea to create a checkpoint by adding a commit so that we can safely develop the schema to the
2:01:152 hours, 1 minute, 15 secondsway we like it. So let's simply go ahead and do git add get commit and let's go ahead and do git push. So we are not going to need the users schema at all.
2:01:252 hours, 1 minute, 25 secondsClerk can handle the users database.
2:01:272 hours, 1 minute, 27 secondsWhat we are going to be maintaining is the workflows table. So let me go ahead and remove everything here. And let's
2:01:362 hours, 1 minute, 36 secondsreplace it with this. So from Drizzle OM Postgress core, make sure you choose JSON B PG table timestamp and UYU ID. Go
2:01:462 hours, 1 minute, 46 secondsahead and create a new workflows table with an ID which is a primary key an organization ID meaning that each workflow will be scoped to its
2:01:552 hours, 1 minute, 55 secondsorganization so other organizations cannot see some other organizations workflows. The name is what each
2:02:032 hours, 2 minutes, 3 secondsworkflow is going to have. The graph is going to be stored inside of a JSON field because it can be very dynamic and
2:02:102 hours, 2 minutes, 10 secondsvery modular and can change very often and it's just easier to keep that data in a JSON field. and then some uh classic created at and updated at
2:02:192 hours, 2 minutes, 19 secondsfields. And then in here, let's go ahead and do uh an export type workflow which is type of workflows infer select. So
2:02:282 hours, 2 minutes, 28 secondsjust by adding this schema, we didn't exactly update our database because in our database we still have that users
2:02:362 hours, 2 minutes, 36 secondsmigration. So this is what I plan on doing right now. First off, go inside of the database folder and you can just remove the migrations folder entirely.
2:02:462 hours, 2 minutes, 46 secondsOr maybe a better idea is to just clean it. Okay.
2:02:502 hours, 2 minutes, 50 secondsThe reason I didn't remove the folder itself is for a very simple reason that we actually reference it in the drizzle
2:02:572 hours, 2 minutes, 57 secondsconfig and I'm not sure what happens if that folder is missing. So what we can do here is we can uh add a git keep file
2:03:072 hours, 3 minutes, 7 secondsinside of migrations. So even if it's empty, it's going to be committed. Okay?
2:03:132 hours, 3 minutes, 13 secondsBecause usually when you delete all files from a folder, git also removes the folder. If you add a little git keep file inside, then that folder is also going to be committed.
2:03:242 hours, 3 minutes, 24 secondsSo the reason we remove the migrations is so that we can safely uh override the uh database. Let's go ahead and attempt
2:03:332 hours, 3 minutes, 33 secondsto do this. So in package JSON, it says that we have database push. So let me go ahead and do two things first. So I'm
2:03:402 hours, 3 minutes, 40 secondsfirst going to try npm run database generate. There we go. So okay. So that creates the migration file. And let's
2:03:492 hours, 3 minutes, 49 secondsnow go ahead and do npm run database push.
2:03:552 hours, 3 minutes, 55 secondsAnd let's see if it's going to work. So it looks like it's asking us if workflows table is created or renamed
2:04:022 hours, 4 minutes, 2 secondsfrom another table. So it looks like it's still in this migration process. So let me just try something. Let me once
2:04:102 hours, 4 minutes, 10 secondsagain go inside of migrations and let me once again clear it entirely except git keep.
2:04:182 hours, 4 minutes, 18 secondsSo empty migrations and let me try just doing npm run database push nothing more.
2:04:282 hours, 4 minutes, 28 secondsAnd now let's go ahead and just say create table. And it's asking us what we are going to do here. So we are going to
2:04:362 hours, 4 minutes, 36 secondsdrop the users table and we're going to create the workflows table. And you can just pick yes, I want to execute all
2:04:432 hours, 4 minutes, 43 secondsstatements. There we go. And now if you go inside of your neon database, you will now have workflows here with ID,
2:04:532 hours, 4 minutes, 53 secondsorganization ID, name, graph, created at, and updated at. Great. And we don't
2:05:002 hours, 5 minuteshave the migrations here. I just think it's easier because if you keep track of migrations, which obviously you should do in production, but in development,
2:05:102 hours, 5 minutes, 10 secondsthey can just cause conflicts and then you have to resolve those conflicts, which you can now do with AI. But
2:05:172 hours, 5 minutes, 17 secondshonestly, I think it's just easier to just do database push every time we change our schema, even though we're not going to be changing it anymore. uh and
2:05:252 hours, 5 minutes, 25 secondslater in production when you do changes you should do migrations but for now it's just easier to do it this way. Now let's go ahead inside of our features
2:05:342 hours, 5 minutes, 34 secondsworkflows and in here let's create a new data.ts file.
2:05:402 hours, 5 minutes, 40 secondsIn here we can now import and descending and equals from drizzle package and we
2:05:472 hours, 5 minutes, 47 secondscan import our database package from lib database. So make sure that your database is actually created in the lib
2:05:552 hours, 5 minutes, 55 secondsfolder and that you have an index which exports the actual database here. Let's also make sure that we actually import
2:06:032 hours, 6 minutes, 3 secondsworkflows from lib database schema. Now let's go ahead and add a very simple list workflows which accepts an
2:06:102 hours, 6 minutes, 10 secondsorganization ID. The reason we are doing this by hand is so that we have a base a pattern to teach AI how to create other
2:06:202 hours, 6 minutes, 20 secondsfunctions for us. So that's always a good idea when you didn't exactly specify how you want something created.
2:06:282 hours, 6 minutes, 28 secondsFirst create it by hand and then use this as an example of how to create other functions using agentic coding.
2:06:362 hours, 6 minutes, 36 secondsNow let's go ahead and highlight this function and let's open our editor and let's make sure that we are in a new conversation. If you're using clot code
2:06:452 hours, 6 minutes, 45 secondsin Visual Studio Code, you can see that we have seven lines selected. If you don't have this functionality, you can always manually tag data.ts
2:06:542 hours, 6 minutes, 54 secondslike this. So I'm going to tell you to do the following. use the existing list
2:07:012 hours, 7 minutes, 1 secondworkflows as an example on how to build data functions. And then I'm going to
2:07:092 hours, 7 minutes, 9 secondstell it to create a create workflow data function that takes an organization ID and a required name and inserts a new
2:07:162 hours, 7 minutes, 16 secondsrow into the workflows table and returns it. So very simple uh method here of highlighting an existing function which
2:07:252 hours, 7 minutes, 25 secondswe wrote by hand and then teaching the agent how to produce other functions based on that pattern. Obviously this is
2:07:332 hours, 7 minutes, 33 secondsa super simplified way of doing it. But I think you get the gist. Uh as we move on and as our code becomes more and more
2:07:422 hours, 7 minutes, 42 secondscomplicated this will be a very valuable skill to have. And just like that we now have create workflow as well. Let's remove the end which is unused for now
2:07:512 hours, 7 minutes, 51 secondsand let's just add an empty space at the end here. Now if you remember from the demo or perhaps you remember in the
2:07:582 hours, 7 minutes, 58 secondspictures each of our workflows will have these uh automatically generated unique slugs and names. So let's go ahead and
2:08:072 hours, 8 minutes, 7 secondscreate a little helper for that. So inside of workflows I'm going to create a new folder called uh lib like this.
2:08:152 hours, 8 minutes, 15 secondsAnd then I'm once again going to open uh claude code. And this is what I'm going to tell it. We can open a new chat for this because it's not exactly connected.
2:08:242 hours, 8 minutes, 24 secondsCreate a generate slug util that uses unique names generator package to return a random hypeneted name made from an
2:08:332 hours, 8 minutes, 33 secondsadjective and an animal like brave otter. Develop this inside.
2:08:422 hours, 8 minutes, 42 secondsLet's just use features workflows and then lib folder
2:08:522 hours, 8 minutes, 52 secondsand that will generate a handy little helper for us which we can then use and you will see how we're going to use it in a second. So we should have that created any moment now. And there we go.
2:09:042 hours, 9 minutes, 4 secondsa function generate slug which simply returns unique names generator from the package which I told it to use uses
2:09:122 hours, 9 minutes, 12 secondsadjectives and animals uses the dash as a separator and keeps the length to two so that is exactly what's going to
2:09:192 hours, 9 minutes, 19 secondsgenerate these cool little names like dominant vasp right brilliant so just like we've added a data file inside of
2:09:272 hours, 9 minutes, 27 secondsour workflows feature let's also add actions ts file and in here let's go ahead and create a brand new action
2:09:362 hours, 9 minutes, 36 secondswhich is going to use this create workflow data function. So I'm going to go ahead and tell it to create a create
2:09:432 hours, 9 minutes, 43 secondsworkflow action server action that takes a name gets the active org ID from out and throws if there is none calls create
2:09:522 hours, 9 minutes, 52 secondsworkflow to create the row revalidates the layout and redirects to workflow ID develop this in actions.ts TS use the
2:10:022 hours, 10 minutes, 2 secondsfunctions from data.ts use out hooks uh actually out utils from
2:10:112 hours, 10 minutes, 11 secondsclerk packages. Let's proceed with this prompt. There we go. Exactly as we described. So it added a use server
2:10:182 hours, 10 minutes, 18 secondsdirective because this is a server action. It imported out from clerk next.js server and it also imported
2:10:252 hours, 10 minutes, 25 secondsrevalidate path and redirect. It imported the create workflow from our data package here. And it developed a
2:10:322 hours, 10 minutes, 32 secondsnew server action create workflow action which only accepts the name as the parameter because organization ID is
2:10:402 hours, 10 minutes, 40 secondsderived from the out tool right here. If the organization ID is missing, we throw an error, no active organization. And
2:10:482 hours, 10 minutes, 48 secondsthen we create a new workflow by passing along the organization ID and the name, which in return gives us back a
2:10:552 hours, 10 minutes, 55 secondsworkflow, which we can then use to redirect to. Brilliant. We need to call revalidate path here, even though it
2:11:032 hours, 11 minutes, 3 secondscurrently does nothing. The reason it currently does nothing is because we never used the list workflows function.
2:11:112 hours, 11 minutes, 11 secondsSo that's what we're going to do now. So let's remember where that is. So inside of dashboard layout, we use something
2:11:192 hours, 11 minutes, 19 secondscalled app sidebar. And remember that whole requirement which I made where I purposely wanted to
2:11:252 hours, 11 minutes, 25 secondsseparate the workflow nav from the app sidebar. So app sidebar can be a server component. Well, it's because of this.
2:11:332 hours, 11 minutes, 33 secondsIt's because I want app sidebar to be able to call this function list workflows. So make sure that you don't
2:11:402 hours, 11 minutes, 40 secondshave use client anywhere in here in dashboard layout there shouldn't be use client and inside of app sidebar there
2:11:492 hours, 11 minutes, 49 secondsshouldn't be use client either okay so you shouldn't have any use state or anything like that in the app sidebar that's why we removed all of that inside
2:11:572 hours, 11 minutes, 57 secondsof workflow nav which is a client component which is expected which is perfectly fine and this is the prompt that we are going to execute next to make app sidebar actually load the data.
2:12:092 hours, 12 minutes, 9 secondsSo use workflows data.ts list workflows function and add it in app sidebar.tsx
2:12:182 hours, 12 minutes, 18 secondsand pass maybe we should say pass the result along as a prop to workflow navigation
2:12:282 hours, 12 minutes, 28 secondscomponent replacing the dummy workflows with real data and I also gave it the following information. The list
2:12:362 hours, 12 minutes, 36 secondsworkflows function requires organization ID. So do a simple turnary using clerk's out function and fall back to an empty
2:12:432 hours, 12 minutes, 43 secondsarray if organization ID is not available. So if you take a look at the workflow navigation, you will see that it doesn't accept any
2:12:512 hours, 12 minutes, 51 secondsprops. Right? So that's what we are going to change. And we are going to replace this workflows array as well.
2:13:012 hours, 13 minutes, 1 secondAnd I'm also going to tell it to do the following. Remove the dummy active
2:13:082 hours, 13 minutes, 8 secondsworkflow set active workflow functionality from workflow nav as well.
2:13:162 hours, 13 minutes, 16 secondsWe will implement active item later.
2:13:212 hours, 13 minutes, 21 secondsOkay. So I don't want it to go into some rabbit hole of changing the code so that it works with real data. Now
2:13:282 hours, 13 minutes, 28 secondsuh great. So I'm very confident in this prompt. So the app sidebar will now call our data.ts list workflows which is
2:13:372 hours, 13 minutes, 37 secondsgoing to return uh basically a list of items. Let's go ahead in full screen and let's execute. Let's take a look at the
2:13:452 hours, 13 minutes, 45 secondssummary of the changes. Components app sidebar. It made it asynchronous.
2:13:502 hours, 13 minutes, 50 secondsBrilliant. It fetched org ID using clerk's out and it loaded real workflows with list workflows org ID falling back
2:13:582 hours, 13 minutes, 58 secondsto an empty array when there is no org ID and it then it passed the results to workflow navigation workflows prop. It
2:14:062 hours, 14 minutes, 6 secondsmodified the workflow nav to accept those same workflows uh and it used the type from database schema. Brilliant.
2:14:152 hours, 14 minutes, 15 secondsAnd it renders each workflow ID and workflow name. And it dropped the dummy list. And it also dropped the active
2:14:222 hours, 14 minutes, 22 secondsworkflow set active workflow state. And it removed the unused react import. So active item highlighting is left out for
2:14:292 hours, 14 minutes, 29 secondsnow as requested. So whether you had this part or not, I don't know. I just wanted to remove it because it's dummy.
2:14:362 hours, 14 minutes, 36 secondsAnd we are later going to use the URL to highlight an active item. But I think it's easier for us to actually take a
2:14:432 hours, 14 minutes, 43 secondslook at the code rather than read about it. So instead of components app sidebar here, let's see what happens. We now imported list workflows from features
2:14:522 hours, 14 minutes, 52 secondsworkflows data. We made the app sidebar asynchronous. That's why we can't have use client. We attempt to extract org ID
2:15:012 hours, 15 minutes, 1 secondfrom await out which we've imported from clerk.js server. And then we attempt to load the workflows by checking if we
2:15:092 hours, 15 minutes, 9 secondshave organization ID. Then await list workflows and pass in the org ID because that's what it accepts. Otherwise fall
2:15:162 hours, 15 minutes, 16 secondsback to an empty array. And once we got those workflows, we simply passed it as a prop to the workflow nav component.
2:15:232 hours, 15 minutes, 23 secondsThose are all the changes in app sidebar. You can also verify that using the diff. Now let's go ahead and take a
2:15:302 hours, 15 minutes, 30 secondslook at the component workflow nav. So in here we now have workflow nav props which uses workflow and then an array.
2:15:402 hours, 15 minutes, 40 secondsSo an array of workflows and it got this type from lib database schema which is an inferred type workflow. Now sometimes
2:15:482 hours, 15 minutes, 48 secondsagents don't do this. I'm very happy that our agent recognized that I actually have a workflow type inside of
2:15:562 hours, 15 minutes, 56 secondslib database schema. But sometimes they can actually do this. they can create their own uh workflow type and then give
2:16:052 hours, 16 minutes, 5 secondsit an ID, right? Which makes no sense and it's code smell. It's bad. So, here's what you can do. And what I'm
2:16:132 hours, 16 minutes, 13 secondsgoing to do anyway, even though this worked as expected, what I'm going to do is I'm going to go inside of my agents.md
2:16:222 hours, 16 minutes, 22 secondsand I'm going to add the following. You don't have to pause and copy this. You can simply use the link on the screen.
2:16:282 hours, 16 minutes, 28 secondsuh or if I forgot to add a link on the screen, just go to the GitHub repository, select this chapter or the main branch and then simply go ahead and
2:16:372 hours, 16 minutes, 37 secondsfind agents.md and copy whatever content you have inside. So this will basically instruct your agent to never handwrite custom or partial shapes for table rows.
2:16:502 hours, 16 minutes, 50 secondsSo it can always add and export and infer from the database, which is exactly what happened here. So if yours
2:16:572 hours, 16 minutes, 57 secondsdidn't do that, you can go ahead and literally give it this in your conversation. So tell it do not make
2:17:042 hours, 17 minutes, 4 secondscustom types and then tell it to do this instead. And then I guarantee you it will do the right thing. Brilliant. So
2:17:122 hours, 17 minutes, 12 secondsinside of workflow nav props, we also removed that dummy list and we also simplified. There is no longer that logic highlighting which item is
2:17:212 hours, 17 minutes, 21 secondsselected. So the only thing that this two now do is load items from our database and pass them here. And if you
2:17:282 hours, 17 minutes, 28 secondsnow go onto localhost 3000 and make sure that your app is running, you will notice that we have no workflows. So
2:17:352 hours, 17 minutes, 35 secondsit's time to finally enable this plus button. We can enable the creation using a prompt like this. modify the workflow
2:17:442 hours, 17 minutes, 44 secondsnavigation component to enable creation of new workflows by using the create workflow action from its location workflows actions.ts.
2:17:542 hours, 17 minutes, 54 secondsKeep in mind that this is a server action and workflow nav is a client component. It will most likely have to
2:18:012 hours, 18 minutes, 1 secondbe passed as a prop through components app sidebar which is a server component which means it's compatible with the
2:18:082 hours, 18 minutes, 8 secondsserver action. Also make use of generate slug lib from generate slug to create a
2:18:152 hours, 18 minutes, 15 secondsunique name before passing it to create workflow action. And let's go ahead and run this prompt. Let's take a look at
2:18:222 hours, 18 minutes, 22 secondsthe output. The wiring is complete. App sidebar imports create workflow action and passes it as on create workflow to
2:18:312 hours, 18 minutes, 31 secondsthe workflow nav. Workflow now now accepts that new action as a prop and handle create workflow which is a new function inside of workflow now
2:18:392 hours, 18 minutes, 39 secondsgenerates a unique name with generate slug before calling it inside a use transition. So is pending disables both
2:18:462 hours, 18 minutes, 46 secondsnew workflow triggers during the request. The action itself revalidates and redirects to the new workflow. Both the collapsed popover button and
2:18:552 hours, 18 minutes, 55 secondsexpanded sidebar group action now trigger creation. Let's briefly take a look at that code. So instead of app sidebar component, we import create
2:19:042 hours, 19 minutes, 4 secondsworkflow action from features workflows actions and then we pass it to the workflow nav under the name on create
2:19:112 hours, 19 minutes, 11 secondsworkflow. Inside of workflow nav, we now accept that brand new action and we also
2:19:182 hours, 19 minutes, 18 secondsadded use transition from react. The reason we've added this is so that we can call that function within start
2:19:272 hours, 19 minutes, 27 secondstransition because that will enable us to maintain the is pending state so that we can disable the button to create new workflows while one is already creating.
2:19:402 hours, 19 minutes, 40 secondsSo let's take a look at localhost now.
2:19:422 hours, 19 minutes, 42 secondsLet's refresh and let's go ahead and click the plus button. And what happens is we are redirected to a 404 page
2:19:492 hours, 19 minutes, 49 secondsbecause we never actually implemented the workflow ID. But if you delete this and go back to workflows and my apologies, if you go back to localhost
2:19:582 hours, 19 minutes, 58 seconds3000, you will now see a brand new workflow visible here. And inside of your neon database, you will now see a record has
2:20:082 hours, 20 minutes, 8 secondsbeen inserted into workflows. And what's important is that it's tied to its organization ID. So if you actually go
2:20:152 hours, 20 minutes, 15 secondsback here and switch to another organization, you will see that it's no longer available. So that is only
2:20:232 hours, 20 minutes, 23 secondsaccessible through a specific organization in which it was created.
2:20:282 hours, 20 minutes, 28 secondsThat brings us to the end of this chapter. We have successfully set up Neon. We got a Postgress database. We
2:20:352 hours, 20 minutes, 35 secondshave Drizzle ORM set up. And we even implemented data functions and server actions which we wired up into our app
2:20:442 hours, 20 minutes, 44 secondssidebar as a server component and in our workflow nav component which is a client component. Brilliant job. You can always
2:20:522 hours, 20 minutes, 52 secondscheck out this chapter uh this chapter's branch on GitHub. And don't worry if the code is slightly different than mine.
2:21:012 hours, 21 minutes, 1 secondThe goal of this project isn't to copy and paste what I do. It's to learn how to use agentic coding to your advantage.
2:21:072 hours, 21 minutes, 7 secondsIt's to learn to be in control and use AI to your advantage and not just let AI do what it wants to do. It doesn't have
2:21:162 hours, 21 minutes, 16 secondsto be exactly the same as it produced uh in my codebase, right? Subtle differences are completely okay as long
2:21:232 hours, 21 minutes, 23 secondsas the functionality works and you are satisfied and understand the code that was written. So, let's go ahead and do
2:21:302 hours, 21 minutes, 30 secondsget add, get commit, and get push. After you push your changes, your railway deployment will most likely fail. And
2:21:392 hours, 21 minutes, 39 secondsthat is because we have to update our environment variables. As you can see in this exact error, npm run build fail to
2:21:472 hours, 21 minutes, 47 secondscollect configuration. And then in here we have the error database URL is not set. So go into your environment or
2:21:552 hours, 21 minutes, 55 secondsenvironment.local and go ahead and copy the neon branch database URL and database URL unpulled. All of these were
2:22:032 hours, 22 minutes, 3 secondsadded automatically using Neon's quick start and agentic prompts. Then head into variables raw editor and simply add
2:22:122 hours, 22 minutes, 12 secondsthose new variables here. Click on update variables and then redeploy.
Chapter 8: Workflow Page
2:22:242 hours, 22 minutes, 24 secondsSo right now we have the ability to load workflows from our database and we also have the ability to create new
2:22:312 hours, 22 minutes, 31 secondsworkflows. The problem is every time we create a workflow or try to access an existing workflow we are greeted with a
2:22:392 hours, 22 minutes, 39 seconds404 page. That is because this URL right here workflows and then ID doesn't exist
2:22:472 hours, 22 minutes, 47 secondsin our file explorer. So we ought to create inside of the app folder dashboard route group that exact URL
2:22:562 hours, 22 minutes, 56 secondspath a workflows folder and then a dynamic URL folder which will accept any workflow ID. Let's create a prompt for
2:23:052 hours, 23 minutes, 5 secondsthat. Create an individual workflow route at dashboard route group workflows and then ID in square parenthesis
2:23:142 hours, 23 minutes, 14 secondsindicating that this is a dynamic part of the URL with four files. The first file is page. Page will be responsible
2:23:232 hours, 23 minutes, 23 secondsfor displaying the dynamic ID part from the URL. We are not going to implement any fetching logic and it's a good idea
2:23:312 hours, 23 minutes, 31 secondsto write that explicitly so it doesn't try to do that ahead of time. We're going to develop a loading file which
2:23:382 hours, 23 minutes, 38 secondswill simply use the spinner component from Shatsnui. And then we're going to use error and not found. And we are
2:23:462 hours, 23 minutes, 46 secondsgoing to utilize the empty tsx composition from chatnui. And we can even tell it reference existing page
2:23:562 hours, 23 minutes, 56 secondsfrom the dashboard to see how we did empty
2:24:032 hours, 24 minutes, 3 secondscomposition so far because this page right here is something that we are already uh familiar with. If you go back
2:24:122 hours, 24 minutes, 12 secondsto the root page here, there we go. This is that empty composition. So let's use that to create the error loading and not
2:24:212 hours, 24 minutes, 21 secondsfound elements as well. So I'm going to go ahead and execute this prompt. There we go. Four files created within
2:24:282 hours, 24 minutes, 28 secondsworkflows ID folder. A page file which is an asynchronous server component that awaits the params and renders the ID. No
2:24:382 hours, 24 minutes, 38 secondsfetching. Loading is just a centered spinner. error is a client component because that's required for error boundaries. That's a next.js rule. And
2:24:452 hours, 24 minutes, 45 secondsit uses the empty composition with a reset button wired. We also have a not found which also uses the empty
2:24:532 hours, 24 minutes, 53 secondscomposition with a link back to the workflows. Brilliant. Let's take a look at these changes. So I'm going to close
2:25:002 hours, 25 minutesthis first. We have a page file. It's located inside of app folder dashboard workflows ID. So all it does is it
2:25:082 hours, 25 minutes, 8 secondsextracts the ID from the params. Params need to be awaited. That is very important. That's why we have this right
2:25:162 hours, 25 minutes, 16 secondshere. So a lot of training data don't include the newest version of Nex.js in which you actually have to await the
2:25:242 hours, 25 minutes, 24 secondsparams. So what they usually do is they define params like this and then they just do this. This will technically
2:25:332 hours, 25 minutes, 33 secondswork, but it's also going to throw an error in the terminal. So make sure that your agent has created params as a promise and it's actually awaiting it.
2:25:422 hours, 25 minutes, 42 secondsSo that's all I want from the page. Make sure it's an asynchronous function so that it can await and that's it. I just want to see the ID that I have clicked
2:25:502 hours, 25 minutes, 50 secondson. In the not found uh what I'm expecting is something like this just a random empty composition workflow not
2:25:582 hours, 25 minutes, 58 secondsfound. And here we have some errors because this can be escaped. Sure. Yeah, we can do that. And for example, this is
2:26:062 hours, 26 minutes, 6 secondsan interesting thing that appears to be happening often. So I'm going to go ahead and I will tell you to do the
2:26:142 hours, 26 minutes, 14 secondsfollowing. This is a good exercise for us. So in not found.tsx, you've used apostrophes, however you
2:26:232 hours, 26 minutes, 23 secondspronounce that, which cause the following error. And then I'm going to paste the error. And then I'm going to tell it fix this. and also add a new
2:26:322 hours, 26 minutes, 32 secondsagents.m MD rule to avoid doing this in the future. So this is how you update the agents MD. When you see something
2:26:412 hours, 26 minutes, 41 secondsthat's kind of annoying and the agent appears to be doing it over and over again, you can add that to the agents.m
2:26:492 hours, 26 minutes, 49 secondsMD and then it's going to stop doing that. There we go. So I have this updated in my agents MD file. JSX text
2:26:572 hours, 26 minutes, 57 secondsescaping escape apostrophes and quotes in JSX text content and it's basically telling it how to avoid that error and
2:27:062 hours, 27 minutes, 6 secondsmy not found now has proper apostrophes set here. Perfect. And we also have a very simple loading which includes a
2:27:142 hours, 27 minutes, 14 secondsspinner and a not found. Great. So let's go ahead and try uh creating a new workflow now. And what should happen is
2:27:232 hours, 27 minutes, 23 secondsthis. This time we should we shouldn't be getting an error but instead we should be getting the exact ID that you
2:27:292 hours, 27 minutes, 29 secondssee in the URL. To test the error page, you can go inside of this new page.tsx and literally just go ahead and throw an
2:27:382 hours, 27 minutes, 38 secondserror test error like this. And then go ahead and reset this page. And there we go. This is how the error page is going
2:27:472 hours, 27 minutes, 47 secondsto look like. And if you want to see the not found, you can go ahead and uh import not found from next navigation
2:27:562 hours, 27 minutes, 56 secondsand save the file. And then go ahead and refresh again. There we go. Workflow not found. The workflow you're looking for doesn't exist or may have been deleted.
2:28:052 hours, 28 minutes, 5 secondsAnd clicking on go back leads back to uh localhost 3000. Perfect. So now let's go ahead and enable clicking on the items
2:28:132 hours, 28 minutes, 13 secondsin this list and keeping them active uh when you're actually in one of the workflows and make sure to remove the
2:28:212 hours, 28 minutes, 21 secondsnot found uh which we added here. So the component which we have to modify to enable the sidebar from being
2:28:282 hours, 28 minutes, 28 secondsinteractive and showing us which is the currently active workflow is workflow nav component. This is where we have to
2:28:352 hours, 28 minutes, 35 secondsadd that logic. We can achieve that with this prompt. So in the workflow nav component, make each workflow in the
2:28:432 hours, 28 minutes, 43 secondslist link to its own page and highlight the one that is currently open. Wrap each workflows sidebar menu button in a
2:28:522 hours, 28 minutes, 52 secondsnex.js link using as child prop so that link becomes the button component and make sure that it points to workflows
2:29:012 hours, 29 minutes, 1 secondand then workflow ID. Use the use pathname hook from next navigation to detect the active workflow and pass is
2:29:102 hours, 29 minutes, 10 secondsactive to that button so it shows as selected. Apply this both in the collapsed popover list and the expanded sidebar list since both render the same
2:29:192 hours, 29 minutes, 19 secondsworkflow items. Let's go ahead and execute this prompt. And that should produce results like this. The workflow
2:29:262 hours, 29 minutes, 26 secondsnav component should now have a link import use pathname import. It should use the use pathname hook to get the
2:29:332 hours, 29 minutes, 33 secondspath name value. And then instead of the workflow nav component here, each sidebar menu button should have an as child prop is active prop which is
2:29:422 hours, 29 minutes, 42 secondscalculated by comparing the path name to a generated URL which we expect with workflow ID injected and then a link
2:29:522 hours, 29 minutes, 52 secondswrapping the span which renders the workflow name with an href workflows uh workflow ID. And if we go ahead and test
2:30:002 hours, 30 minutesthat out, there we go. We can now navigate between our existing workflows.
2:30:052 hours, 30 minutes, 5 secondsThis seems like a pretty good place for a checkpoint. So, let's go ahead and commit our changes and then get push.
2:30:122 hours, 30 minutes, 12 secondsWhat we have to develop next is the workflow shell, which should look something like this. A very big center
2:30:202 hours, 30 minutes, 20 secondspanel where all of our nodes and the canvas in general is going to be.
2:30:262 hours, 30 minutes, 26 secondsBeneath it, we should have a logs panel where we are going to display each of the nodes status happening in real time.
2:30:342 hours, 30 minutes, 34 secondsAnd then we're going to have a right sidebar which will serve both as the toolbar to add new nodes and as the inspector for individual selected node.
2:30:442 hours, 30 minutes, 44 secondsAnd it's also going to have some functions like run or delete this workflow. The prompt to develop this is
2:30:522 hours, 30 minutes, 52 secondsgoing to be a little bit bigger than usual. So what I've prepared for you is the exact file which you can just download or copy or paste because I
2:31:002 hours, 31 minutesdon't expect you to pause the screen and copy the whole thing. So whenever we have these longer prompts which are mostly related to UI changes, I'm going
2:31:092 hours, 31 minutes, 9 secondsto add them in the specifications folder right here. So make sure you are in the main branch or simply select the branch
2:31:172 hours, 31 minutes, 17 secondsof this chapter. Go inside of specifications, find the workflow shell and then simply add it to your
2:31:252 hours, 31 minutes, 25 secondsspecifications right here. And these are the instructions which we are going to give. Create a workflow shell component
2:31:332 hours, 31 minutes, 33 secondsin features workflows components folder that takes a workflow ID and is the layout shell for the workflow editor.
2:31:422 hours, 31 minutes, 42 secondsThen render it from the workflow page.tsx tsx located inside of the dashboard route group inside of workflows ID page.tsx.
2:31:542 hours, 31 minutes, 54 secondsSo that is currently this right here which right now just renders the ID.
2:32:002 hours, 32 minutesThen we are going to say build all of this in one file using resizable components from chaten UI meaning
2:32:092 hours, 32 minutes, 9 secondscomponents UI resizable and use rem values for every size. That is because
2:32:162 hours, 32 minutes, 16 secondsits training data will probably tell it to use percentages but they don't look as good uh when you actually do it that
2:32:242 hours, 32 minutes, 24 secondsway especially when zooming in and zooming out. So using RAM values it's actually much better. And then what we do is we basically describe exactly how uh this canvas is supposed to look like.
2:32:362 hours, 32 minutes, 36 secondsThe layout is a horizontal resizable panel group that fills the space size full with two panels and a handle between them. So we have the left panel which is essentially this right here.
2:32:482 hours, 32 minutes, 48 secondsThat is the primary column with this specific min size. Inside is a vertical resizable panel group split into two
2:32:552 hours, 32 minutes, 55 secondspanels with a handle between them. The top panel has a minimum size of 18 rim for the canvas placeholder. The bottom
2:33:022 hours, 33 minutes, 2 secondspanel has a default size of 8 rim and minimum size 6 ram for the logs placeholder. So that is this panel right
2:33:102 hours, 33 minutes, 10 secondshere. And then we have the right panel which is the inspector with default size 16 RAM, minimum size 14 RAM and max size
2:33:172 hours, 33 minutes, 17 seconds36 RAM. So, Antonio, where do you get these values from? I just tweaked them until they looked good. That's why I'm
2:33:252 hours, 33 minutes, 25 secondsgiving you the prompt to implement this because it isn't really educational. Uh it's just tweaking the values until they
2:33:322 hours, 33 minutes, 32 secondslook and feel good. And I also instructed to put a simple label in each panel as placeholder content. So, we can
2:33:402 hours, 33 minutes, 40 secondsuh identify which one is the canvas, which one is the logs, and which one is the inspector. No subcomponents and no data fetching yet. So purely
2:33:492 hours, 33 minutes, 49 secondspresentational, we just want to get uh a skeleton of this layout. Let's go ahead and simply run implement specifications
2:33:562 hours, 33 minutes, 56 secondsworkflow shell MD. And the result should look something like this. A main canvas
2:34:032 hours, 34 minutes, 3 secondspanel beneath it a logs panel and on the right side the inspector panel. And these should be resizable to their
2:34:112 hours, 34 minutes, 11 secondsminimum and maximum values which we have defined. Beautiful. exactly as we imagined it from the picture. I
2:34:192 hours, 34 minutes, 19 secondspurposely didn't append this picture because then it would notice all of the cursors and it would notice all of these
2:34:262 hours, 34 minutes, 26 secondsicons and some agents can go crazy and just try to implement all of that. All I wanted was a simple shell, which is exactly what this prompt implemented.
2:34:362 hours, 34 minutes, 36 secondsLet's take a look at the changes together. So the page has been modified to no longer just render the ID but instead to render the workflow shell and
2:34:452 hours, 34 minutes, 45 secondsthe workflow ID prop. We implemented the workflow shell inside of features workflows components workflow shell as
2:34:532 hours, 34 minutes, 53 secondsinstructed. Right now we don't use the workflow ID prop for anything but we will later on. And in here we simply
2:35:012 hours, 35 minutes, 1 secondmake use of components UI resizable component. And this is the result. There we go. pretty clean implementation.
2:35:102 hours, 35 minutes, 10 secondsBrilliant. So that is exactly what we wanted to achieve and that is the perfect end for this chapter. So once again let's make sure we create a
2:35:192 hours, 35 minutes, 19 secondscheckpoint get commit and get push.
Chapter 9: Trigger.dev Setup
2:35:292 hours, 35 minutes, 29 secondsBefore we develop the UI which will allow us to add new nodes into the canvas, drag them around and connect
2:35:362 hours, 35 minutes, 36 secondsthem. It's important to understand how we are going to develop the execution logic of these workflows. This is an
2:35:432 hours, 35 minutes, 43 secondsexample workflow which we are going to be able to build once we implement the UI. So take a look at this process right
2:35:512 hours, 35 minutes, 51 secondshere. It starts with opening a URL. Then it goes to the agent node which is instructed to configure a Porsche 911.
2:36:002 hours, 36 minutesAfter that we connect it to extract node whose job is to extract the relevant information and that is connected to a
2:36:072 hours, 36 minutes, 7 secondssend email node whose job is to send an email. These types of workflows cannot function within your normal HTTP
2:36:162 hours, 36 minutes, 16 secondsrequest. Every classic request has some kind of timeout. Regardless of if you're deploying on railway versell or your
2:36:232 hours, 36 minutes, 23 secondscustom VPS, you will be hit with some kind of HTTP timeout error, which is not
2:36:312 hours, 36 minutes, 31 secondssomething we want when developing these longunning workflows. What we need is something built for AI workflows and
2:36:382 hours, 36 minutes, 38 secondslongunning tasks with cues, retries, and elastic scaling. And trigger.dev is the perfect solution for what we need. Even
2:36:472 hours, 36 minutes, 47 secondson their landing page, you can find a use case for browser automation using browserbase, which is exactly the way we
2:36:552 hours, 36 minutes, 55 secondsare going to implement our functionality. Besides that, trigger comes builtin with everything you see here on the screen. And if you're still
2:37:042 hours, 37 minutes, 4 secondsnot convinced or you are unsure about using a third-party library, rest assured because trigger.dev is
2:37:112 hours, 37 minutes, 11 secondsopensource and self-hostable. You can use the link on the screen to get on their page and create an account. Once you create your account, go ahead and
2:37:202 hours, 37 minutes, 20 secondscreate a new project. Once you set up a new project, you will see the installation wizard. This is a manual installation wizard, which is perfectly
2:37:292 hours, 37 minutes, 29 secondsfine to use. But since we're using Agentic Coding, they actually have a prompt that we can use. So, let's go
2:37:362 hours, 37 minutes, 36 secondsonto their landing page documentation and find the quick start. In here you will find setup with AI. Now triggers
2:37:442 hours, 37 minutes, 44 secondsquick start is intended to be used a little bit differently in comparison to clerks or neons which we had used before. So what I would recommend is
2:37:532 hours, 37 minutes, 53 secondshaving cloud code or whatever is your coding agent opened on one side and on the other side or just in a new window
2:38:012 hours, 38 minutes, 1 secondhave your regular terminal open. Let's go ahead and copy their prompt and paste it into cloud code. Depending on the agent you're using, you might get a
2:38:092 hours, 38 minutes, 9 secondslittle bit of a different response, but in general, it should be something like this. It should give you a very quick summary of your current codebase. And
2:38:172 hours, 38 minutes, 17 secondsthen it should tell you that you need to check whether you have a trigger.
2:38:222 hours, 38 minutes, 22 secondsSo, you have to manually tell it yes, I have a trigger. And this is what's going to happen next.
2:38:312 hours, 38 minutes, 31 secondsIt's going to try to run trigger.dev latest in it. But for example, uh my clot code immediately noticed that in it
2:38:402 hours, 38 minutes, 40 secondsis an interactive command, meaning that it's going to prompt the user for an organization and project selection or if
2:38:482 hours, 38 minutes, 48 secondsyou're not authenticated, it's going to log in via browser. So it knows that it won't be able to run this itself. That's
2:38:552 hours, 38 minutes, 55 secondswhy I told you to prepare a normal terminal on the side. What I would recommend answering now is the following. Yes, I have a trigger.dev dev
2:39:042 hours, 39 minutes, 4 secondsaccount. I will run the setup manually and tell you once it's done. So you can review the code changes and proceed with
2:39:112 hours, 39 minutes, 11 secondsthe trigger.dev setup. So there's no point in telling it can you go ahead and run this command. You can see that mine
2:39:202 hours, 39 minutes, 20 secondshas already detected that that would fail because it will. So let's go ahead and actually run this ourselves. The first thing that's going to happen is
2:39:282 hours, 39 minutes, 28 secondsthat we are going to have to authenticate our account. Next, it's going to list our projects. So, just go ahead and select whichever project you
2:39:372 hours, 39 minutes, 37 secondshave just created. Now, it's going to install the dependencies in our codebase. After trigger dependencies have been installed, it's going to ask
2:39:442 hours, 39 minutes, 44 secondsyou where you want to create the trigger directory. And the placeholder is source trigger. Since we are not using the
2:39:522 hours, 39 minutes, 52 secondssource folder, as you can see, we only have the root directly here. Let's go ahead and make sure that it doesn't
2:39:592 hours, 39 minutes, 59 secondscreate one unnecessarily and just put the name trigger inside instead. Now, it's asking you to choose an example to
2:40:072 hours, 40 minutes, 7 secondscreate in that directory. If you really want to play around and explore, you can choose the scheduled task, but I'm going to choose the simple option, which is
2:40:152 hours, 40 minutes, 15 secondsjust a hello world. Before we proceed forward, I want to focus on the files it has modified or created. So, first in
2:40:242 hours, 40 minutes, 24 secondsthe package JSON, we now have trigger.dev dev SDK. This is the version I am on. And we also have trigger.dev
2:40:312 hours, 40 minutes, 31 secondsbuild in the dev dependencies. We have a new file trigger.config.ts which is basically connected to the
2:40:392 hours, 40 minutes, 39 secondsproject we have selected as well as some max duration and retry options here and the directory from which it's going to
2:40:482 hours, 40 minutes, 48 secondsread uh longunning tasks or durable functions which we are going to define.
2:40:532 hours, 40 minutes, 53 secondsAnd then we have some updates to the tsconfig and we have an example file inside of the trigger folder right here.
2:41:022 hours, 41 minutes, 2 secondsNow here's one interesting thing. So the CLI which I used has generated this code
2:41:092 hours, 41 minutes, 9 secondsand I can see this import here trigger.dev SDK version 3. But if you actually take a look at their quick
2:41:182 hours, 41 minutes, 18 secondsstart and if you look at critical rules, you will see the rule always import from
2:41:242 hours, 41 minutes, 24 secondstrigger.dev SDK, never import from SDK version 3. So that is why it's useful to
2:41:342 hours, 41 minutes, 34 secondsuse this setup with AI even though we had to manually do a few things. So what I would recommend doing now is the
2:41:412 hours, 41 minutes, 41 secondsfollowing. Manual setup complete. Review the files and follow the critical rules
2:41:502 hours, 41 minutes, 50 secondsfrom the initial instructions. And let's see what it's going to do. Let's take a look at what happened. So, it reviewed
2:41:572 hours, 41 minutes, 57 secondsthe generated files. It detected that the init worked, but both files generated uh and violated the critical
2:42:072 hours, 42 minutes, 7 secondsrule. They import from version three. So it fixed that and it just uses the SDK
2:42:132 hours, 42 minutes, 13 secondsinstead. So both of my files, example.ts and trigger config now have the proper import. As you can see, there are no
2:42:222 hours, 42 minutes, 22 secondserrors, meaning that that truly does work. So if I take a look at trigger, there we go. No need for uh version
2:42:292 hours, 42 minutes, 29 secondsthree because it's redundant at this point. So let's go ahead and see what it recommends doing next. Now that we have
2:42:372 hours, 42 minutes, 37 secondsuh this trigger config set up, let's go ahead and actually run the dev server. So this is the command that it gave me.
2:42:452 hours, 42 minutes, 45 secondsAnd it also recommends running this in its own tab because it's a longunning task. So let's go ahead and do npxtrigger.dev
2:42:522 hours, 42 minutes, 52 secondslatest dev within our project right here. And that is going to build the local worker. And now if you actually go
2:43:012 hours, 43 minutes, 1 secondback here, you should no longer see the installation wizard. You should instead see the very file which we developed I
2:43:092 hours, 43 minutes, 9 secondsmean the command line interface developed here visible right here.
2:43:152 hours, 43 minutes, 15 secondsPretty cool. So I'm going to go ahead and respond with the following.
2:43:192 hours, 43 minutes, 19 secondsDevelopment server is running and the dashboard is no longer displaying the installation wizard. Instead it's showing the registered task. Now let's
2:43:272 hours, 43 minutes, 27 secondsfollow the step four which it has generated for me. Obviously, if yours tells you to do something different, you can follow that instructions, but you
2:43:352 hours, 43 minutes, 35 secondscan just follow what I do because it's it's the same thing, right? So, I'm going to copy this payload which it has prepared for me, which is a super simple
2:43:442 hours, 43 minutes, 44 secondsobject with key message and value of hello from the dashboard. But before I do that, I just want to manually review
2:43:532 hours, 43 minutes, 53 secondsthis code right here. So this is a hello world task which uses the task API from trigger. Its ID is hello world. Its max
2:44:022 hours, 44 minutes, 2 secondsduration is 300. And its run function does the following. It's an asynchronous function which accepts a payload. It
2:44:112 hours, 44 minutes, 11 secondscurrently has a type error here. We can just turn it off or just change this to unknown if it bothers you. And then
2:44:182 hours, 44 minutes, 18 secondsimmediately once the task is run, it's going to log hello world and it's going to display the payload and then it's
2:44:282 hours, 44 minutes, 28 secondsgoing to wait for 5 seconds once again using trigger API and at last it's going to return the output. So what I would
2:44:372 hours, 44 minutes, 37 secondsactually recommend is changing this to task finished so it doesn't confuse you with the log here and save this file.
2:44:442 hours, 44 minutes, 44 secondsAnd now let's go ahead and actually run the test here. So go ahead and find your workflow here and click on test. Now in
2:44:542 hours, 44 minutes, 54 secondsthe payload here, let's go ahead and do that message. Hello from the dashboard.
2:44:592 hours, 44 minutes, 59 secondsAnd down at the bottom you can find run test. So let's see what happens. First we have the payload visible here. Hello
2:45:072 hours, 45 minutes, 7 secondsfrom the dashboard. Then immediately we have a log hello world. And then no
2:45:142 hours, 45 minutes, 14 secondsoutput yet. It's not until 5 seconds pass and only then do we get the output
2:45:222 hours, 45 minutes, 22 secondstask finished. We have successfully developed our first longunning task which will be the base behind the entire
2:45:312 hours, 45 minutes, 31 secondsworkflow execution logic. This is of course a super simple example, but I think you can already see how useful
2:45:392 hours, 45 minutes, 39 secondsthis will be when we have actual longunning tasks and AI workflows with topologically sorted nodes which pass
2:45:472 hours, 45 minutes, 47 secondsdata through one another. And besides the dashboard, you will also see the output of the finished task in your terminal. Since the agent tells me that
2:45:552 hours, 45 minutes, 55 secondsthere are step five and step six we have to do. I'm just going to respond run completed successfully to see what is
2:46:032 hours, 46 minutes, 3 secondsthe next step I have to do. So the next step is to establish a trigger secret key in our environment. So what the
2:46:102 hours, 46 minutes, 10 secondsagent already did for me is it actually modified my environment.
2:46:162 hours, 46 minutes, 16 secondsYou probably don't have this and you don't need it yet. I'm maintaining this for this repository when it becomes a
2:46:242 hours, 46 minutes, 24 secondstutorial repository, right? So, whoever clones the repository has an environment example. But what you should be looking
2:46:312 hours, 46 minutes, 31 secondsat is the environment.local file. And inside, I'm just going to go ahead and prepare the following. So,
2:46:392 hours, 46 minutes, 39 secondsdon't be confused. Okay. So far, you should have the database neon clerk and these. Okay. You don't need to maintain
2:46:482 hours, 46 minutes, 48 secondsenvironment. example I am maintaining that so it's easier for me to develop this tutorial. So now let's go ahead and
2:46:542 hours, 46 minutes, 54 secondsfollow its instruction on how to obtain the trigger secret key. So in the dashboard make sure you are in the dev
2:47:022 hours, 47 minutes, 2 secondsenvironment. So let's ensure we are dev environment.
2:47:072 hours, 47 minutes, 7 secondsThen let's go inside of the API keys. So let's see how can we find that. There we go. API keys. And in here we have a
2:47:142 hours, 47 minutes, 14 secondssecret key. So I'm just going to go ahead and copy this. And then I'm going to paste it here. There we go. Just like that, we added our trigger secret key.
2:47:252 hours, 47 minutes, 25 secondsSo let's see what do we have to do next.
2:47:282 hours, 47 minutes, 28 secondsIt added the documented placeholder. So yours probably didn't do that if you don't have a environment.
2:47:342 hours, 47 minutes, 34 secondsAnd then we have step six, triggering from your Nex.js backend. Uh you are on Nex.js16. So you'll trigger the task from a server action or a route handler.
2:47:442 hours, 47 minutes, 44 secondsThe key rule is a type only import of the task. So it's code that never gets bundled into your app. So in here it's
2:47:532 hours, 47 minutes, 53 secondsrecommending something like a server action which imports the hello world task and then executes it with a payload hello from my app.
2:48:042 hours, 48 minutes, 4 secondsOkay. So here's what I'm going to tell it to do now.
2:48:092 hours, 48 minutes, 9 secondsUh before we do this, maybe yours already did that. you know, it's perfectly fine. But here's what I
2:48:162 hours, 48 minutes, 16 secondswant to do first. Is there any trigger AI
2:48:222 hours, 48 minutes, 22 secondstooling you can recommend for me to install? So before we proceed with
2:48:292 hours, 48 minutes, 29 secondsbuilding uh execution from our Nex.js app. So what it did is it fetched the documentation from trigger.dev.
2:48:372 hours, 48 minutes, 37 secondsSo in case yours didn't do that or it maybe used its training data, uh I want to show you that you can go inside of trigger documentation. You can scroll down and you can find building with AI.
2:48:492 hours, 48 minutes, 49 secondsSo my agent tells me that I already have an MCP server, which is okay. MCP server
2:48:582 hours, 48 minutes, 58 secondsbasically allows the connection between cloud code and trigger in a way that I can tell cloud code create a new project
2:49:072 hours, 49 minutes, 7 secondsin my workspace or create a new organization right things like that but skills will be more useful for us
2:49:142 hours, 49 minutes, 14 secondsbecause that will allow us to properly programmatically use trigger so because
2:49:212 hours, 49 minutes, 21 secondsof that I would recommend that we first focus on installing trigger scales So let's go ahead and go inside of our
2:49:302 hours, 49 minutes, 30 secondsterminal here. We can close the dev running task and let's run the following command. So the skills installer is
2:49:372 hours, 49 minutes, 37 secondsasking me which targets I want to support. So I'm going to select cloud code. If you're using something like
2:49:432 hours, 49 minutes, 43 secondsopen code or codex, you would select uh agents.md.
2:49:492 hours, 49 minutes, 49 secondsAgents.md is also going to cover like 99% of others. So let me go ahead and select these two. Now let's choose the
2:49:572 hours, 49 minutes, 57 secondsskills we want to install. So in here we have uh trigger authoring chat agent. Uh then we have trigger authoring tasks.
2:50:062 hours, 50 minutes, 6 secondsThen we have chat agent advanced costsaving getting started and real time and front end. So I'm going to select
2:50:142 hours, 50 minutes, 14 secondsall of them. And I'm going to press enter. And now it's going to install those. You're going to have to do the same selection for the other option,
2:50:232 hours, 50 minutes, 23 secondsagents MD. And yes, uh this is a bit weird. It seems broken. It actually
2:50:312 hours, 50 minutes, 31 secondshappens in almost every CLI tool that I use. Maybe it's ghosty, maybe it's my shell, but whenever I'm too zoomed in,
2:50:392 hours, 50 minutes, 39 secondseverything seems mushed. But yeah, I just basically select uh everything. If [snorts] for whatever reason you had
2:50:462 hours, 50 minutes, 46 secondstrouble running their executor, you can most certainly find on skills.sh
2:50:532 hours, 50 minutes, 53 secondstrigger right here, trigger.dev. Let's see. So, we have trigger setup, trigger uh real time. I would recommend having
2:51:022 hours, 51 minutes, 2 secondsuh the setup, the real time tasks con well all of these to be honest. Yeah, just make sure that they are coming from
2:51:092 hours, 51 minutes, 9 secondstrigger.dev. Okay. as long as that is the author, you can go ahead and install uh all of those and you will have pretty
2:51:172 hours, 51 minutes, 17 secondsmuch the same thing as me. So, okay, at this point I have a lot of skills here.
2:51:222 hours, 51 minutes, 22 secondsLet me do a quick review here. So, I'm going to look at my claude. Let's see. Skills. These are the ones that I have.
2:51:302 hours, 51 minutes, 30 secondsOkay. Trigger, authoring, chat agent, authoring tasks, chat agent, advanced, cost savings, getting started, real
2:51:372 hours, 51 minutes, 37 secondstime, and front end. So if you are adding yours individually here, I would recommend trying to find the real time
2:51:452 hours, 51 minutes, 45 secondsand front end. Let me see. Trigger real time. Looks like they have real time.
2:51:532 hours, 51 minutes, 53 secondsIs there maybe front end? Maybe they've bundled that into one. Uh anyway, just use uh npxtrigger.dev
2:52:012 hours, 52 minutes, 1 secondlatest skills and then you will be able to find these ones that I have selected.
2:52:052 hours, 52 minutes, 5 secondsUh if this is happening to you, like your shell looks weird, try zooming out, making the text smaller. Uh I think that
2:52:122 hours, 52 minutes, 12 secondscan fix it sometimes. But yeah, basically just use your arrow keys and press space to select all of them. Or
2:52:182 hours, 52 minutes, 18 secondsmaybe their skills agent skills CLI uh has the ability to like select all of
2:52:252 hours, 52 minutes, 25 secondsthem. Yeah, non-interactive install. You can just use this and then that's just going to install every skill without
2:52:332 hours, 52 minutes, 33 secondsprompting. Perfect. So yeah, here's the solution if you are having trouble.
2:52:382 hours, 52 minutes, 38 secondsBeautiful. So now that we have all of those skills, uh, let me just go a little bit back here to see if there's anything useful that I can have here.
2:52:482 hours, 52 minutes, 48 secondsSkills and MCP server. Apparently, we already have the MCP server, so we don't need that. Llms txt. This is when you don't use skills and just want to point
2:52:562 hours, 52 minutes, 56 secondsyour agent to a web search temporarily so it gets the context. Okay, I think I am satisfied with this.
2:53:032 hours, 53 minutes, 3 secondsAt this point, let me just do looks like there was a change in agents.m MD. So in here, it added trigger.dev agent skills
2:53:122 hours, 53 minutes, 12 secondsand it basically instructs uh it injects sorry. So agents.md is injected into
2:53:192 hours, 53 minutes, 19 secondsevery single prompt that we do agents MD or claude MD. And now it added this here
2:53:252 hours, 53 minutes, 25 secondswhich basically makes sure that whenever an agent needs to use a skill, it's going to use a skill. Okay, basically
2:53:342 hours, 53 minutes, 34 secondsinstructions on how to load the most relevant skills. Now, it's not the end of the world if yours looked different,
2:53:412 hours, 53 minutes, 41 secondsright? But this will just make it easier for agents to understand how to build task. And that's the whole point of agentic coding, right? Of providing a
2:53:502 hours, 53 minutes, 50 secondsfew examples yourself and then letting the AI do 50 other examples so you don't have to do it, right? or in this case the authors are providing us with
2:53:582 hours, 53 minutes, 58 secondsexamples. Since we already have uh sorry 20 uh uncommitted changes, I think this is a pretty good checkpoint. So I'm
2:54:062 hours, 54 minutes, 6 secondsgoing to do get commit and then get push. Now let's quickly create the UI for this run button so that we can test
2:54:142 hours, 54 minutes, 14 secondsour new trigger skills and see if we can make an agent connect a task with being executed by clicking on the run button.
2:54:242 hours, 54 minutes, 24 secondsSo let's go ahead and modify our workflow shell component. So workflow shell currently has all the panels which
2:54:322 hours, 54 minutes, 32 secondswe need and I want to put the run button inside of the inspector panel right here. So I'm going to highlight this part right here which will make the
2:54:402 hours, 54 minutes, 40 secondsthree lines selected. If you can't do that then just go ahead and tag the workflow shell in your editor like this.
2:54:482 hours, 54 minutes, 48 secondsMake sure you don't tag the specification, tag the component. So I'm going to tell you the following.
2:54:542 hours, 54 minutes, 54 secondsSeparate the selected lines. If you can't select lines, then tell it separate the inspector div. Right?
2:55:032 hours, 55 minutes, 3 secondsSeparate inspector div in its own component called right sidebar. DSX. And
2:55:102 hours, 55 minutes, 10 secondsinstead of a centered inspector paragraph, render a button component with a play icon. and run text.
2:55:242 hours, 55 minutes, 24 secondsGreat. So now my right sidebar in is its own component and I can click here and I have a button with a play icon inside.
2:55:342 hours, 55 minutes, 34 secondsSo if I go ahead and run my app and if I visit localhost 3000 here and select the workflow, I should see a big run button
2:55:432 hours, 55 minutes, 43 secondshere. So before we develop a prompt which is going to connect or wire up the right sidebar button to executing a
2:55:512 hours, 55 minutes, 51 secondstrigger.dev task, it's a good idea to check whether the skills are actually loaded in your agent. So try and search for something like trigger. And if it's
2:56:002 hours, 56 minutesnot here, go ahead and try doing reload skills. And if that doesn't work, go ahead and reload the entire window. So
2:56:092 hours, 56 minutes, 9 secondsthen if I go ahead and search for trigger, there we go. a bunch of skills available. And now we can execute a prompt like this. Use trigger.dev skills
2:56:182 hours, 56 minutes, 18 secondsto create a new server action in our workflows actions file. Call that server action run workflow action which will
2:56:272 hours, 56 minutes, 27 secondstrigger a example task which we got when we set up trigger. Then wire up that server action to the right sidebar button. Let's go ahead and execute this.
2:56:382 hours, 56 minutes, 38 secondsLet's take a look at the result. So first things first in our features workflow actions we now have the
2:56:452 hours, 56 minutes, 45 secondsfollowing. We now have tasks imported from trigger dev SDK and we have a type
2:56:522 hours, 56 minutes, 52 secondshello world task imported from trigger example. And then down here we have a new function run workflow action which
2:57:012 hours, 57 minutes, 1 secondonce again validates the organization ID. It doesn't have to do that yet because we are not really fetching anything with this org ID but why not?
2:57:102 hours, 57 minutes, 10 secondsAnd then what it does is it very simply uh executes the or should I say triggers
2:57:162 hours, 57 minutes, 16 secondsthe task called hello world. The only thing it didn't do is it didn't add any payload. So perhaps we can add some
2:57:242 hours, 57 minutes, 24 secondspayload. Let me close this here. So I'm going to go ahead and do something like message and I will do hello from right
2:57:342 hours, 57 minutes, 34 secondssidebar. So we know it's executed from there, right? Uh, and this run workflow action was I suppose connected through
2:57:432 hours, 57 minutes, 43 secondsthe right sidebar. There we go. Use client. And in here we have run workflow action imported. We have is pending
2:57:512 hours, 57 minutes, 51 secondsstart transition on run all added to the button. And let me look at the change in the workflow shell. So, okay, in here we just have the right sidebar rendered.
2:58:002 hours, 58 minutesNothing more, nothing less. So now let me go ahead inside of here and let me do
2:58:082 hours, 58 minutes, 8 secondsthe following. I want to prepare my tasks here or my runs. I think that might be a better idea here. First of
2:58:172 hours, 58 minutes, 17 secondsall, my local server is not connected to trigger.dev. So it's pretty good uh reminder that I need to both have
2:58:242 hours, 58 minutes, 24 secondstrigger.dev latest dev running and npm rundev. So make sure that you have both as well.
2:58:342 hours, 58 minutes, 34 secondsAnd that should make this connected. So let's just refresh. Perfect. And now let's go ahead and click run here. And
2:58:412 hours, 58 minutes, 41 secondslet's go ahead and refresh this. And there we go. We can now successfully execute longunning tasks and AI workflows from our Nex.js application.
2:58:512 hours, 58 minutes, 51 secondsAnd now just for fun, I'm going to do the following. I'm going to say use and then I can use the slash command and
2:58:592 hours, 58 minutes, 59 secondsfind trigger real time and front end scale to display the feedback of the task. I'm not really sure what to expect
2:59:082 hours, 59 minutes, 8 secondshere. I think every agent will develop something different. I just want to see if the skill actually works and if it can produce some useful results here.
2:59:172 hours, 59 minutes, 17 secondsSo, it looks like this is a pretty useful thing to run because it's going to install a package trigger dev react
2:59:242 hours, 59 minutes, 24 secondshooks. So, if you haven't, go ahead and just run a simple prompt with this skill. It will most likely do the same.
2:59:312 hours, 59 minutes, 31 secondsIf it doesn't, you can always instruct it to use this uh dependency specifically and then it's going to do
2:59:382 hours, 59 minutes, 38 secondsthat. And let's take a look at the changes it actually produced here. So, first I'm taking a look at the actions just to see if anything has changed
2:59:462 hours, 59 minutes, 46 secondshere. So nothing seems to be changed here. Now let's look at the package JSON. And this is where we see the first
2:59:522 hours, 59 minutes, 52 secondschange. Trigger.dev react hooks 4.5.1 has been added to my dependencies. And let me take a look at the right sidebar
3:00:013 hours, 1 secondhere. So what do we have here? There we go. So we have a new function called run status which uses the use realtime run
3:00:113 hours, 11 secondsand it uses the access token handle public access token. So, I'm assuming it read the skill and it knows how to uh
3:00:183 hours, 18 secondsset this up. Chances are yours has developed something different, right?
3:00:243 hours, 24 secondsBut as long as it's anything similar to this, if you can see hooks like use real time run and you can see the public
3:00:323 hours, 32 secondsaccess token being added here, it doesn't really matter how it implemented this because obviously we're going to modify this later. We're going to delete
3:00:403 hours, 40 secondsthe whole file. I just want to make sure that you know we can play around and you feel comfortable playing around with agentic coding right it doesn't need to
3:00:483 hours, 48 secondsbe the same as mine. So now in theory we should be able to click run and we should be getting some more useful
3:00:553 hours, 55 secondsinformation. Starting run dqed. Let's see if anything's going to update. So what does this mean? What just happened?
3:01:023 hours, 1 minute, 2 secondsI'm not even sure. Oh, it completed. Let me try again. Run dqed executing.
3:01:093 hours, 1 minute, 9 secondsAnd then we should get completed after. There we go. So we now have real time information here. Yours
3:01:183 hours, 1 minute, 18 secondscan have slightly different UI. That's perfectly fine. But I think you now get the idea that this real-time feedback is
3:01:243 hours, 1 minute, 24 secondsgoing to be important for us because if you take a look at our uh canvas design
3:01:313 hours, 1 minute, 31 secondshere, uh these nodes will need to be executed one by one, right? So we are eventually going to have something like
3:01:393 hours, 1 minute, 39 secondsa node in progress and that's going to look like this. So how do we make sure that uh whichever node is currently
3:01:483 hours, 1 minute, 48 secondsexecuting is the one that's currently highlighted? Well, exactly with a skill like trigger real time and front end. So
3:01:563 hours, 1 minute, 56 secondsthat's why I wanted you to run this prompt, not so you have the exact code as me, but so that you at least have the React Hooks package installed. Right?
3:02:073 hours, 2 minutes, 7 secondsRegardless of how your agent got to this solution, it really doesn't matter because we are later going to rework
3:02:143 hours, 2 minutes, 14 secondsthis and make it look like it's supposed to look like by first cleaning this entire component and then starting from scratch. So don't worry at all. As long
3:02:233 hours, 2 minutes, 23 secondsas you can actually see some real-time feedback, it should all be perfectly fine. Before we commit and push these
3:02:303 hours, 2 minutes, 30 secondschanges, remember that we added a new variable to environment.local.
3:02:353 hours, 2 minutes, 35 secondsSo go ahead and simply add a new variable here or just use the raw editor like this and then add it at the end. So
3:02:423 hours, 2 minutes, 42 secondstrigger secret key and click update variables like that. And if you want to, you can click deploy. And now let's go
3:02:493 hours, 2 minutes, 49 secondsahead and commit. That brings us to the end of this chapter. Amazing job and see you in the next one. If you get an error
3:02:563 hours, 2 minutes, 56 secondslike this on your railway redeployment, it appears to once again be some kind of conflict in the package lock file. The
3:03:033 hours, 3 minutes, 3 secondsfix is very easy. You just have to remove node modules and package lock, run an npm install, and then go ahead and commit that new package lock, which
3:03:123 hours, 3 minutes, 12 secondswill eventually cause the redeployment to work. But I'm going to go ahead and research in the meantime why this is happening. Perhaps this is only
3:03:193 hours, 3 minutes, 19 secondshappening to me. But I'm recording just in case any of you has this problem as well. So from now on, remember if you
3:03:263 hours, 3 minutes, 26 secondssee npmci and if you see mentions of package lock or something like this, remember that you just have to reinitialize the package lock file.
Chapter 10: Canvas Setup
3:03:433 hours, 3 minutes, 43 secondsNow that we have the basic execution logic in place, it's time to start developing the canvas component. And for
3:03:503 hours, 3 minutes, 50 secondsthat, we're going to be using React Flow, which is the fact standard for developing workflows. And it's a fully open- source library. Since React Flow
3:03:593 hours, 3 minutes, 59 secondsdoesn't have an official quick start using a gentic coding, nor does it maintain any official skills in the
3:04:063 hours, 4 minutes, 6 secondsskills sh registry. What we can use instead is their LLM's endpoint. So
3:04:133 hours, 4 minutes, 13 secondssimply append lms.txt on Reactflow domain and that's going to give you this markdown file which is
3:04:223 hours, 4 minutes, 22 secondsbasically an instruction file for agents on how to find relevant documentation for React Flow. So we can use this
3:04:303 hours, 4 minutes, 30 secondsinstead of skills or MCP servers. Let's go ahead and once again revisit our workflow shell component. And just like
3:04:383 hours, 4 minutes, 38 secondswe've separated the right sidebar in its own component, let's do the same for the canvas. So either use the line selection
3:04:473 hours, 4 minutes, 47 secondsfunctionality if you have that. You can see that I have three lines selected here. But if that's not working for you, then go ahead and tell it something like
3:04:553 hours, 4 minutes, 55 secondsthis. Separate the canvas div inside workflow shell.tsx
3:05:043 hours, 5 minutes, 4 secondsin its own component just like right sidebar.
3:05:103 hours, 5 minutes, 10 secondsDo not alter the actual content of the new component.
3:05:163 hours, 5 minutes, 16 secondsI just want to add one guard rail so it doesn't go off the rails and I don't know what it wants to implement. Let's go ahead and simply do that. After that,
3:05:243 hours, 5 minutes, 24 secondsyou should have a separate canvas component in place where this was written in line moments ago. The actual look of your app shouldn't change
3:05:333 hours, 5 minutes, 33 secondsbecause we explicitly told it that the new canvas component should preserve the content that was there before. But now we have a separate canvas component
3:05:413 hours, 5 minutes, 41 secondswhich we can target for uh upcoming prompts. So let's go ahead and do the following. Modify the canvas.tsx
3:05:493 hours, 5 minutes, 49 secondstsx component and set up a basic example of React flow using the documentation
3:05:583 hours, 5 minutes, 58 secondsand then in here go ahead and paste this llm's txt documentation. There we go. So
3:06:053 hours, 6 minutes, 5 secondshere's what the agent produced. It set up a basic React flow example in our new canvas.tsx component. It also installed
3:06:133 hours, 6 minutes, 13 secondsa new dependency xy flow react which is react flow 12. It also verified that there was an old package called React
3:06:203 hours, 6 minutes, 20 secondsFlow. So that is deprecated. And we can also verify that by very quickly visiting their documentation. And yes, we can see that this is the package it's
3:06:293 hours, 6 minutes, 29 secondssupposed to use. It replaced the placeholder content within our canvas component with a working flow. So we now have two connected nodes and some logic
3:06:383 hours, 6 minutes, 38 secondslike use nodes state, use edges state on connect and some components like background and controls. It also turned
3:06:453 hours, 6 minutes, 45 secondsthis into a client component because it's interactive and it uses hooks, so it's mandatory. Oh, sorry, no. And it
3:06:523 hours, 6 minutes, 52 secondsadded the mandatory style.css import. It also added the size full. So, it fills the resizable panel from
3:07:003 hours, 7 minutesworkflow shell. That [snorts] sounds pretty basic, exactly what we wanted.
3:07:053 hours, 7 minutes, 5 secondsSo, don't worry if yours looks somewhat different. This is, I'm pretty sure, exactly what's written here. I'm pretty
3:07:133 hours, 7 minutes, 13 secondssure that's it. Just maybe slightly modified so it matches our export function canvas and in here it's default
3:07:223 hours, 7 minutes, 22 secondsfunction app. So slight modification here. Uh great. So in here I can see one weird thing and that is that we are
3:07:293 hours, 7 minutes, 29 secondsskipping the second parameter. Oh yeah because we don't need set nodes. So if you added set nodes it will just be unused I guess. So that's why this is skipped and that's why it caught my eye.
3:07:413 hours, 7 minutes, 41 secondsI would prefer we do like set nodes, but yeah, that's going to throw a warning.
3:07:453 hours, 7 minutes, 45 secondsSo, I'm just going to leave it like this. We also have a very simple on connect here. And then div class name size full. So, it takes the whole space
3:07:533 hours, 7 minutes, 53 secondsand a very simple React flow with background and controls. Well, that's simple enough. Let me take a look at all
3:08:003 hours, 8 minutesthe changes here to verify. So, yes, XY Flow React package was added inside of workflow shell. We just render the
3:08:073 hours, 8 minutes, 7 secondscanvas component. And in here we have the entire new canvas component, which isn't really complicated. Simple enough.
3:08:163 hours, 8 minutes, 16 secondsAnd if I go ahead and refresh, we should see a very cool component right here
3:08:223 hours, 8 minutes, 22 secondscalled the canvas. In dark mode, it's currently broken, but if you toggle, it should look fine. Don't worry, we're obviously going to fix this and adjust
3:08:313 hours, 8 minutes, 31 secondsit so that it works in dark mode as well. But you should have this working right now. I think their llm's.txt
3:08:403 hours, 8 minutes, 40 secondsuh instructs the agent to do exactly this, which is exactly what we need at this point. So great. Now let's go ahead and modify the styles of this so it
3:08:493 hours, 8 minutes, 49 secondsmatches it a bit closely to what we expect in the uh canvas picture right here. So let's go step by step and turn
3:08:563 hours, 8 minutes, 56 secondsthe existing canvas from this into what we would expect to see. So the first thing that bothers me besides the
3:09:033 hours, 9 minutes, 3 secondsobvious uh dark mode failure is this uh connection right here. I would rather it looks like a step than this current
3:09:123 hours, 9 minutes, 12 secondscurve that we have. So let's go ahead and from XYlow React import the connection line type. Then go ahead and
3:09:213 hours, 9 minutes, 21 secondsfind the React flow component and add the following props. Connection line type and choose smooth step. set the
3:09:293 hours, 9 minutes, 29 secondsproper color of the stroke so it uses our border variable and default edge options type smooth step style and once
3:09:373 hours, 9 minutes, 37 secondsagain use the same color for the stroke and once you save that it should get closer to what we expect which is this
3:09:443 hours, 9 minutes, 44 secondskind of step connection rather than the weird curve that it was before. Let's go ahead and add some more style props
3:09:533 hours, 9 minutes, 53 secondswhich will change the look. So after these connection lines and default edge options, go ahead and add a style prop
3:10:003 hours, 10 minuteswhich is an object. Make sure to open uh double square brackets and then change these three variables and then add a
3:10:093 hours, 10 minutes, 9 secondstypecast as react. CSS properties. So this should uh a tiny bit more modify
3:10:163 hours, 10 minutes, 16 secondsthe values. You can't really see right now, but the border has kind of changed.
3:10:203 hours, 10 minutes, 20 secondsThis line has become thicker and some other small changes. And the last prop you should have here is max zoom. Make
3:10:283 hours, 10 minutes, 28 secondssure it's set to one. Now let's go ahead and add the dark mode support to our canvas. We can do this in the existing
3:10:353 hours, 10 minutes, 35 secondsconversation, but even if you add a new conversation, uh it will work equally.
3:10:403 hours, 10 minutes, 40 secondsSo this is the prompt. Add light and dark mode support to the canvas component by sensing React Flow's color mode with the app theme. Use the use
3:10:493 hours, 10 minutes, 49 secondstheme hook from next themes package to read the current theme and pass it to ReactFlow color mode prop. So the canvas
3:10:563 hours, 10 minutes, 56 secondsedges and controls switch between light and dark along with the rest of the app.
3:11:013 hours, 11 minutes, 1 secondLet's take a look at the output. The canvas now syncs React Flow's color mode with the app theme. Imported use theme
3:11:083 hours, 11 minutes, 8 secondsfrom next themes and color mode from XY Flow React. Read the current theme and passed it to the color mode prop.
3:11:163 hours, 11 minutes, 16 secondsfalling back to system during hydration before theme resolves. React Flow's color mode accepts light, dark or system. The same values next themes
3:11:253 hours, 11 minutes, 25 secondsproduces to the canvas, background, edges and controls now switch with the rest of the app. Since your background edge connection colors use the CSS
3:11:323 hours, 11 minutes, 32 secondsvariables which we've added on purpose, so we use background and border. Those already follow the theme as well. So let's actually take a look at these
3:11:403 hours, 11 minutes, 40 secondschanges here. So we have now theme from use theme hook which was imported from next themes. We also now have type color
3:11:493 hours, 11 minutes, 49 secondsmode imported from XYlow React. And let's see. So we now have color mode prop which adds the theme here as a prop
3:11:583 hours, 11 minutes, 58 secondsfrom here. It casts it as color mode. So it matches the type that XY flow expects
3:12:063 hours, 12 minutes, 6 secondsand it falls back to system if it cannot uh read the value which can happen during hydration. And just like that we
3:12:143 hours, 12 minutes, 14 secondsnow have pretty cool looking uh dark mode and switching to light mode seems to work as well. I'm just curious what happens during a refresh.
3:12:243 hours, 12 minutes, 24 secondsMhm. Okay. So this is what I was worried about. During refresh the hydration appears to fail. So let me confirm this
3:12:323 hours, 12 minutes, 32 secondsa few more times. Yes. So I'm guessing yes. Okay. When I refresh it's broken.
3:12:383 hours, 12 minutes, 38 secondsBut if I toggle from this state then it works fine. So we implemented it. But looks like there is some sync which we
3:12:463 hours, 12 minutes, 46 secondshave to implement here because we currently have an error. So the fix for this is to add a sync external store
3:12:533 hours, 12 minutes, 53 secondshook which is going to resolve the theme first and fall back to some other mode during serverside rendering and
3:13:013 hours, 13 minutes, 1 secondhydration. Since the prompt for that is a little bit longer and I don't think it makes sense for you to uh watch and copy
3:13:093 hours, 13 minutes, 9 secondsthis whole text. You can simply go inside of the specifications folder in the GitHub repository either in the main
3:13:163 hours, 13 minutes, 16 secondsbranch or in this chapters branch and then let's go ahead and in the same conversation where we implemented the
3:13:243 hours, 13 minutes, 24 secondscanvas theme let's go ahead and say implement canvas theme MD. So these are the changes that it did. It imported use
3:13:333 hours, 13 minutes, 33 secondssync external store from react in our canvas component and then it created a function called use mounted. This
3:13:423 hours, 13 minutes, 42 secondsfunction use mounted simply returns the use sync external store and uses a no op function here. It also uses some dummy
3:13:513 hours, 13 minutes, 51 secondsunmounts here. Then in the actual canvas component, we replaced the usage of theme with resolved theme value from use
3:14:003 hours, 14 minutestheme. We then grabbed the mounted value from our use mounted hook and then we
3:14:073 hours, 14 minutes, 7 secondscalculate the color mode by the value of mounted. So if we have successfully mounted meaning we have hydrated we fall
3:14:163 hours, 14 minutes, 16 secondsback to resolved theme otherwise we fall back to light theme. And if we don't have mounted at all, we go ahead and fall back to light as well.
3:14:283 hours, 14 minutes, 28 secondsAnd down here, we simply swapped the theme value and the fallback to the system to that color mode value. So the component looks like this in the end.
3:14:383 hours, 14 minutes, 38 secondsLet me show you once again. We import use sync external store. We create a no op function empty subscribe. We create a function use mounted which returns use
3:14:473 hours, 14 minutes, 47 secondssync external store. uses that no op function returns true and false respectively. And then instead of extracting theme from use theme, we
3:14:563 hours, 14 minutes, 56 secondsextract resolved theme and then the color mode is now calculated by using that mounted value from usemounted hook.
3:15:043 hours, 15 minutes, 4 secondsIf we are mounted, we attempt to use the resolved theme which we cast as color mode here or we fall back to light. And
3:15:123 hours, 15 minutes, 12 secondsif we are not mounted, we fall back to light mode as well. And then we simply replace the caller mode here to use that
3:15:193 hours, 15 minutes, 19 secondscalculated value instead of the previous one which we had which fall back to system. And if you take a look now and
3:15:263 hours, 15 minutes, 26 secondsrefresh it works. You can toggle you can refresh and everything will persist. Now as you can see we have um some white
3:15:353 hours, 15 minutes, 35 secondsflash here. So, if you want to get rid of that and if you're certain that your app will be in dark mode by default, uh you can change this light to dark value.
3:15:473 hours, 15 minutes, 47 secondsAnd then there we go. There is no flash anymore. But then if you want to use your app in light mode, there will be a
3:15:553 hours, 15 minutes, 55 secondsquite more noticeable uh flash in the other direction. So, choose whichever value uh you want to use here. So
3:16:043 hours, 16 minutes, 4 secondsdepending on your preference, you can either leave or remove the background. I personally think it looks cleaner if we
3:16:113 hours, 16 minutes, 11 secondsget rid of the background component, but you can choose for yourself. This way it looks empty. I like it that way. I feel
3:16:193 hours, 16 minutes, 19 secondslike it's cleaner. But if you prefer having those little dots, feel free to leave the background component there.
3:16:253 hours, 16 minutes, 25 secondsAnd now let's go ahead and stage commit and push our changes so we have a checkpoint and so that we can close this chapter.
Chapter 11: Custom Nodes
3:16:413 hours, 16 minutes, 41 secondsNow that we have the basic React flow example ready, let's do the necessary changes so that the nodes no longer look
3:16:483 hours, 16 minutes, 48 secondslike this but instead are more similar to this. Now, in order to achieve this, we are obviously going to have to
3:16:563 hours, 16 minutes, 56 secondsdevelop some custom node components. But it will also be a good idea for us to develop something called a node
3:17:033 hours, 17 minutes, 3 secondsregistry. You can think of that as some kind of manifest which every single node will have to satisfy. So, every node
3:17:113 hours, 17 minutes, 11 secondswill need to have a title. Every node will need to have an icon. Every node will need to have its accent color like
3:17:193 hours, 17 minutes, 19 secondsgreen, blue, red, etc. Every node will also have a type. Is it a trigger node
3:17:263 hours, 17 minutes, 26 secondslike start or is it an action node like open URL, extract, etc. And that's also how we're going to separate them here in
3:17:343 hours, 17 minutes, 34 secondsthis right sidebar. And the reason we are developing this in that kind of registry manifest is so that we only
3:17:443 hours, 17 minutes, 44 secondshave to develop one or two nodes ourselves in the beginning and then we can easily point our agent and tell it
3:17:533 hours, 17 minutes, 53 secondsusing this node registry or the manifest develop the agent node or develop the extract node develop send email node.
3:18:033 hours, 18 minutes, 3 secondsThat's how you use the Gentic coding to your advantage without losing control of the code you want to generate. So what
3:18:103 hours, 18 minutes, 10 secondsI've prepared for you in the GitHub repository is the templates folder. In here you will find two files. The first
3:18:173 hours, 18 minutes, 17 secondsone is the node registry which I was just talking about. This node registry will define the step node kind which can
3:18:243 hours, 18 minutes, 24 secondseither be trigger or action the node field node definition and the actual node registry with all the required
3:18:323 hours, 18 minutes, 32 secondstypes for each node which satisfy the node definition. We're also going to export some additional node types. And
3:18:403 hours, 18 minutes, 40 secondsin my opinion, it doesn't really make sense to try and prompt to generate this because we really cannot leave it to chance for this to be non-deterministic.
3:18:493 hours, 18 minutes, 49 secondsIt will be much easier for you to follow along if you have this manifest exactly the way it's written here. And then
3:18:573 hours, 18 minutes, 57 secondslater we can use the gentic prompting to enhance this manifest to add new properties to the node registry and to
3:19:053 hours, 19 minutes, 5 secondsuse it to create new nodes. That's why I feel it makes more sense to simply inject this into our codebase because
3:19:123 hours, 19 minutes, 12 secondsit's not really a large file, but it is very specific with its types and that's what makes it a manifest, a definition,
3:19:203 hours, 19 minutes, 20 secondssomething we have to satisfy. And the second file I've added here is a custom step node component. The reason I added
3:19:273 hours, 19 minutes, 27 secondsthis as opposed to trying generating this is because of the class names.
3:19:323 hours, 19 minutes, 32 secondsChances are you and I are not going to get the exact same class names and it will just be annoying to follow the tutorial where you have to fight with
3:19:403 hours, 19 minutes, 40 secondsyour agent in trying to generate the exact same style of the component. So make sure that you are in the main
3:19:473 hours, 19 minutes, 47 secondsbranch or simply find chapter 10 once it's available and use the templates folder. The reason I'm telling you to
3:19:543 hours, 19 minutes, 54 secondsuse the templates folder and not uh the actual features workflows where we are going to put these files is because this
3:20:023 hours, 20 minutes, 2 secondstemplates is just the initial state of these files. We're going to work and add on top of them. So I want you to have
3:20:103 hours, 20 minutes, 10 secondsthe exact version you need to have right now. That's why maybe preferably use chapter 10 branch and then get them. But
3:20:183 hours, 20 minutes, 18 secondsusing them from the main branch should work just fine. So inside of features workflows create a new folder called
3:20:263 hours, 20 minutes, 26 secondsnodes and inside put the node registry component and just ensure that you have
3:20:333 hours, 20 minutes, 33 secondseverything that I have here. So step node kind node field node definition the actual node registry which has two nodes
3:20:413 hours, 20 minutes, 41 secondsinside one start trigger node and then one open URL action node with some fields which just have a youtube.com
3:20:493 hours, 20 minutes, 49 secondsplaceholder. It uh this exact node registry needs to satisfy the record string node definition. We need to
3:20:573 hours, 20 minutes, 57 secondsexport node type which is a key of type of node registry from here. So we know which nodes are available. So this will uh result into start and open URL and as
3:21:063 hours, 21 minutes, 6 secondswe add more nodes this node type will expand and you need to have step node data and step node type. Now obviously
3:21:163 hours, 21 minutes, 16 secondswe are going to improve on this but for now uh this is a perfect start and then go inside of features workflows
3:21:243 hours, 21 minutes, 24 secondscomponents and in here add the custom step node component and when you copy it from here uh just make sure that you
3:21:333 hours, 21 minutes, 33 secondsmodify this import right here. So just change this to be workflows nodes like
3:21:403 hours, 21 minutes, 40 secondsthis. The reason I put this import in the templates folder is because if the import is invalid, it breaks the build.
3:21:503 hours, 21 minutes, 50 secondsSo just make sure that you have a valid import in the step node which you put inside of features workflows components.
3:22:003 hours, 22 minutesSo you should now have node registry inside of your features workflows nodes folder node registry and you should have
3:22:083 hours, 22 minutes, 8 secondsstep node component inside of features workflows components step node and that step node should have the features
3:22:173 hours, 22 minutes, 17 secondsworkflows nodes node registry import where it gets the node registry and it gets the type step node and you can see
3:22:243 hours, 22 minutes, 24 secondshow these two components are connected using their types I mean sharing their types and also extract racting from the node registry based on the type that
3:22:333 hours, 22 minutes, 33 secondsthis step node component data has. To not leave you in the dark, I will just quickly go over this step node component. So, majority of this styling
3:22:423 hours, 22 minutes, 42 secondshere, as you can see, when selected, add ring, uh, rounded radius, border too.
3:22:483 hours, 22 minutes, 48 secondsIt's just to make it look as in this picture right here. Okay, that's it. A bunch of these styles are just for that.
3:22:573 hours, 22 minutes, 57 secondsNow about this has target thing and the handle component. Well, that's basically to determine whether this is a start
3:23:053 hours, 23 minutes, 5 secondsnode which should only have one handle or if it's an action node which should have like an input and an output handle.
3:23:123 hours, 23 minutes, 12 secondsSo you can see that we check has target meaning a trigger starts the flow and takes no input. So it has no target
3:23:193 hours, 23 minutes, 19 secondshandle. So we make sure that we only render this first handle if we do have a target, right? And every other component has the other handle on the other side.
3:23:303 hours, 23 minutes, 30 secondsAnd everything else you see here is just making it look like it's supposed to look like. Nothing really educational in
3:23:373 hours, 23 minutes, 37 secondsme uh showing you every single Tailwind class name here. That's why I feel like it's more useful for us to just copy this template but understand what we are
3:23:453 hours, 23 minutes, 45 secondscopying. So now that we have these two files, step node and node registry, it's time to uh wire them into the actual
3:23:533 hours, 23 minutes, 53 secondscanvas component so that they appear here instead of these default nodes. So go ahead and prepare your canvas component. One thing I forgot to tell
3:24:003 hours, 24 minutesyou which could be very useful. Remember when we set up React Flow, we weren't able to find skills or MCP servers for
3:24:083 hours, 24 minutes, 8 secondsit, but we were able to find a React Flow LLMS txt. The problem is we have to remember to add that context every time
3:24:173 hours, 24 minutes, 17 secondsto cloud code. So what we could do instead is we could update our uh agents.m MD or cloud code MD whichever
3:24:263 hours, 24 minutes, 26 secondsone you use. Since we did a symbolic link, we can just update uh any of those. So go ahead and prompt your cloud
3:24:333 hours, 24 minutes, 33 secondscode something like this. So update agents MD so that every time we have to use react flow API components or just
3:24:413 hours, 24 minutes, 41 secondsusage in general we don't rely on training data but instead we search https reactflow.dev llms.ext
3:24:503 hours, 24 minutes, 50 secondsand the output should be something like this. It will probably have some differences but [snorts] react flow don't trust training data.
3:24:583 hours, 24 minutes, 58 secondsThis project uses react flow xy flow react for the canvas. Its APIs, components, hooks, and props change across versions and might may differ
3:25:053 hours, 25 minutes, 5 secondsfrom your training data before writing or changing any React Flow code. Fetch and consult the official LLM docs index at LLM's text and follow the linked pages relevant to what you're building.
3:25:163 hours, 25 minutes, 16 secondsDo not rely on memory for component names, props, hook signatures, or usage patterns. Great. I love this change. So, yours should be something similar to
3:25:253 hours, 25 minutes, 25 secondsthis. It doesn't have to be word for word. So remember, every time you don't have skills available or MCPS and the only thing you have to work with is
3:25:323 hours, 25 minutes, 32 secondsLlMS.ext, it's a pretty good idea to add that to agents MD. So every time you reference React Flow, it will know, hey,
3:25:403 hours, 25 minutes, 40 secondsI have to look at the documentation first and not rely on my training data because you can't really know uh what data this was trained on. Now, to render
3:25:483 hours, 25 minutes, 48 secondsthe new step node component inside of our cannabis, we have to do the following. I honestly think it's worth doing this by hand rather than writing a
3:25:553 hours, 25 minutes, 55 secondsprompt because writing a prompt would actually take longer. So first things first, make sure that you import the step node component from components step
3:26:023 hours, 26 minutes, 2 secondsnode and the type step node type from nodes node registry. Then let's go ahead and define the custom node types object
3:26:113 hours, 26 minutes, 11 secondshere. So node types and go ahead and import node types from XYlow React. So
3:26:193 hours, 26 minutes, 19 secondsmake sure you have that import here and simply add step step node. Now let's go ahead and modify our existing initial nodes. So right now we just have two
3:26:273 hours, 26 minutes, 27 secondsdummy nodes here. So we can replace this array with step node type array and just a single object inside ID of start type
3:26:363 hours, 26 minutes, 36 secondsstep position XY Z and then data. Now be careful here. So type needs to be start kind needs to be trigger title needs to
3:26:453 hours, 26 minutes, 45 secondsbe start and values need to be an empty object. Then let's go ahead and let's clear the initial edges. And let's go
3:26:523 hours, 26 minutes, 52 secondsahead and register the node types in the React flow here. And once you do that, if you go ahead and refresh your canvas, you should see your brand new node here.
3:27:033 hours, 27 minutes, 3 secondsSince this is a trigger node, you will notice that you only have a handle on one side. It doesn't have a handle here because it's supposed to start the data
3:27:123 hours, 27 minutes, 12 secondsflow and not accept any data flow. In your canvas component, you're now going to have one unused import. So you can
3:27:193 hours, 27 minutes, 19 secondsremove type node from XYlow React. This is a pretty good place for a checkpoint.
3:27:253 hours, 27 minutes, 25 secondsSo let's go ahead and commit these changes. This way you have a checkpoint for this custom nodes and node registry and all the wiring that went into the
3:27:333 hours, 27 minutes, 33 secondscanvas. And now you can play around and you can tell your agent to do the following. modify the canvas component so that initial nodes also render a open
3:27:423 hours, 27 minutes, 42 secondsURL node which we define in the node registry and just like that you can see how easy it us for utilize gentic coding
3:27:503 hours, 27 minutes, 50 secondsto do the work which we would usually have to do manually but we can now do very reliably because we implemented
3:27:583 hours, 27 minutes, 58 secondsthat manifest the registry right so we can trust the code that's been generated because we have such a good base of
3:28:053 hours, 28 minutes, 5 secondsexisting code the actual code change will look something like this. So no need for any new imports. Instead of the initial nodes in your cannabis
3:28:133 hours, 28 minutes, 13 secondscomponents beneath the start node, you should now have ID open URL type step some slight change in the position and then the data here. Feel free to play
3:28:223 hours, 28 minutes, 22 secondsaround a bit and maybe tell your agent to create a few more nodes and maybe connect them. But after you are done, I
3:28:303 hours, 28 minutes, 30 secondswould recommend actually just reverting the changes and making sure that the only node you have on your canvas is the start node simply because this will be
3:28:393 hours, 28 minutes, 39 secondsthe actual uh look of every new workflow which is created. Right? So every new workflow that gets created is going to
3:28:473 hours, 28 minutes, 47 secondsget initialized with a start node. And then we're going to develop a toolbar here which will allow us to add new nodes inside.
Chapter 12: Liveblocks Setup
3:29:003 hours, 29 minutesNow that we've developed custom nodes and our node registry, let's go ahead and add live blocks to our project, which will enable live collaboration in
3:29:093 hours, 29 minutes, 9 secondseach workflow room, as well as enable actual data persistence. Because right now, regardless of how many changes we
3:29:173 hours, 29 minutes, 17 secondsdo in a workflow room, if we connect some nodes, drag them around, all of that is reset when you reload the page.
3:29:253 hours, 29 minutes, 25 secondsSo, we can achieve both by adding live blocks. Creating our own sync engine and live collaboration would take months to
3:29:343 hours, 29 minutes, 34 secondsimplement to this level. But thanks to live blocks, we can achieve all of this in just a few lines of code. Using the
3:29:413 hours, 29 minutes, 41 secondslink on the screen, you can visit their page. And once you're here, go ahead and create an account. Once you create an account, go ahead and create a brand new
3:29:503 hours, 29 minutes, 50 secondsproject. I would recommend leaving the environment in development mode so that we can test it out without worrying of incurring any costs and click create
3:29:593 hours, 29 minutes, 59 secondsproject. Once you've created your account, I would recommend going into their documentation page, get started.
3:30:063 hours, 30 minutes, 6 secondsIn here, let's go ahead and select multiplayer as the collaboration feature we want to set up. Then let's choose canvases as the type of content people
3:30:153 hours, 30 minutes, 15 secondsare going to edit. That is going to provide us with several guides. Go ahead and choose React Flow with NextJS. In
3:30:223 hours, 30 minutes, 22 secondshere, you can follow the guide on adding React Flow and Livelocks integration into your app. Before we add this to our
3:30:303 hours, 30 minutes, 30 secondsproject, I would recommend doing one prompt to improve our data.ts file within features workflows. What's
3:30:383 hours, 30 minutes, 38 secondscurrently missing is the function which is going to fetch an individual workflow scoped to the organization ID. So we can
3:30:453 hours, 30 minutes, 45 secondsrun a simple prompt like this. Add a get workflow organization ID and ID as the parameters to our workflows data file
3:30:543 hours, 30 minutes, 54 secondsthat returns the single workflow row matching both ID and organization ID.
3:30:593 hours, 30 minutes, 59 secondsThat should generate a function like this. And it should also add an import for the end query from Drizzle OM. I
3:31:073 hours, 31 minutes, 7 secondswould recommend staging and committing this change as well as pushing it to the repository so we reduce the amount of uncommitted change we are going to have
3:31:143 hours, 31 minutes, 14 secondsto review once we add live blocks. So this is somewhat of a checkpoint for us.
3:31:193 hours, 31 minutes, 19 secondsBefore we add livelocks to our project, I would recommend scrolling down until you find tools agent skills. And in here
3:31:273 hours, 31 minutes, 27 secondsyou can find the command with which you can install live skills which will make our agent more reliable when it comes to
3:31:353 hours, 31 minutes, 35 secondsusing and developing with live. So let's go ahead and run this command and choose livelocks best practices and go ahead
3:31:433 hours, 31 minutes, 43 secondsand install this for your agent and select project as the installation scope and use the symbolic link as the installation method. This will once
3:31:523 hours, 31 minutes, 52 secondsagain produce a bunch of uncommitted files. So go ahead and do git add get commit and then get push so you start
3:31:593 hours, 31 minutes, 59 secondswith a clean slate and don't have to review 50 files. Remember to run reload skills and reload window so that you
3:32:093 hours, 32 minutes, 9 secondsactually have live blocks skill available. Now that we've prepared our environment for live blocks, let's go ahead and actually add it to our
3:32:173 hours, 32 minutes, 17 secondsproject. Now, usually if we were at the beginning of our coding journey, I would tell you to simply copy this prompt. But
3:32:243 hours, 32 minutes, 24 secondssince we already have a pretty large codebase at our hands, it will actually cause more harm than good initializing
3:32:323 hours, 32 minutes, 32 secondsthis prompt. Instead, let's go through the quick start manually and then utilize LiveBlocks skills to help us
3:32:393 hours, 32 minutes, 39 secondsenhance this setup which we are going to develop right now. Let's start by adding the necessary LiveLocks packages. Once
3:32:473 hours, 32 minutes, 47 secondsyou've installed the packages, go ahead and initialize a new LiveBlocks config file using the command listed below.
3:32:543 hours, 32 minutes, 54 secondsOnce you have the config generated, let's go ahead and configure it so it only holds the information which we are actually going to need. So we are not
3:33:013 hours, 33 minutes, 1 secondgoing to need pretty much any of these besides the user meta. So we can simplify this entire config. So it looks like this. Our user meta object will
3:33:103 hours, 33 minutes, 10 secondshave an ID and then an info object which holds the user's name and an optional avatar and go ahead and save that file.
3:33:183 hours, 33 minutes, 18 secondsNext step is to create a livelocks room.
3:33:203 hours, 33 minutes, 20 secondsNow, if you are in this documentation while you are logged in, it will actually load your project which you've created and it's automatically going to
3:33:293 hours, 33 minutes, 29 secondsappend the public API key here. Now, if yours hasn't done that, don't worry. I'm going to show you where you can find your key. But for now, let's actually just create a room using this snippet.
3:33:413 hours, 33 minutes, 41 secondsSo, inside of your features workflows components, create a new file called room.tsx
3:33:483 hours, 33 minutes, 48 secondsand simply paste the content inside. So if you can't find this public key, you can go inside of your project here API keys and in here you have a public key.
3:33:583 hours, 33 minutes, 58 secondsNow let's slightly modify this room component so that besides accepting children as the prop, it also accepts
3:34:043 hours, 34 minutes, 4 secondsthe room ID and then we can remove the hard-coded ID and actually use the dynamic prop. The next step is to
3:34:123 hours, 34 minutes, 12 secondsencapsulate our React flow component with that room we've just created. But I would rather we encapsulate the entire
3:34:203 hours, 34 minutes, 20 secondsworkflow shell. So go inside of your app folder dashboard workflows ID page.tsx
3:34:283 hours, 34 minutes, 28 secondsand go ahead and encapsulate this inside of this new room component which we've just developed. So make sure you add the
3:34:353 hours, 34 minutes, 35 secondsproper import features workflows components room and make sure that you pass the room ID matching the dynamic ID
3:34:423 hours, 34 minutes, 42 secondsfrom the params. Step five is to set up a collaborative react flow diagram. In their documentation, they create a new
3:34:503 hours, 34 minutes, 50 secondscomponent called flow. But in our example, we have a canvas. So what we actually need to do is we need to
3:34:583 hours, 34 minutes, 58 secondstransform this canvas from using our use nodes state, use edges state on connect
3:35:053 hours, 35 minutes, 5 secondsand actually make it use livelocks flow hook instead. Let's go ahead and create a prompt that says the following.
3:35:143 hours, 35 minutes, 14 secondsTransform the canvas component hooks to live blocks hooks. Do not modify edges
3:35:213 hours, 35 minutes, 21 secondsor nodes. Only change the API which is used desired result.
3:35:283 hours, 35 minutes, 28 secondsAnd then we can just copy this part of their example. So it understands that this is the only thing we are interested
3:35:363 hours, 35 minutes, 36 secondsin. And let's go ahead and simply append liveblocks best practices and let's
3:35:433 hours, 35 minutes, 43 secondsexecute. Let's take a look at the changes. We removed use callback import because we no longer need it. We also removed unused imports from xy flow
3:35:523 hours, 35 minutes, 52 secondsreact. We added use livelocks flow from liveblocks react flow. And we also added liveblocks react flow styles.css.
3:36:013 hours, 36 minutes, 1 secondI assume this was added because we appended livelocks best practices. If your agent didn't add that, go ahead and
3:36:083 hours, 36 minutes, 8 secondsadd it. I mean, it's a step anyway. And about the changes here. So, it completely removed use nodes state, use
3:36:173 hours, 36 minutes, 17 secondsedges state, and on connect. And it replaced it with a very uh clean use live blocks flow. And then from here
3:36:243 hours, 36 minutes, 24 secondswith the structure, the nodes, edges, on nodes change, on edges change, on connect, and on delete. And the actual configuration for nodes and edges in
3:36:333 hours, 36 minutes, 33 secondsthis hook stayed the same. So, we reused our initial nodes and our initial edges.
3:36:393 hours, 36 minutes, 39 secondsThat's also important. Make sure this wasn't modified. And the only change in the React Flow component is the wiring of the ondelete prop, which was unused
3:36:483 hours, 36 minutes, 48 secondsbefore. Brilliant. So, the component should now look like this. Pretty similar to what it was before, but
3:36:543 hours, 36 minutes, 54 secondsactually uh a bit simplified now because we get all of our API from a single hook. In step six, we have to render the
3:37:033 hours, 37 minutes, 3 secondscursors component from Liveblocks React Flow as well as add some additional styles. So let's go ahead and do that.
3:37:103 hours, 37 minutes, 10 secondsFirst things first, make sure you import cursors from Livelocks React Flow. Then make sure that you have all three styles. So XY flow style, Livelocks
3:37:203 hours, 37 minutes, 20 secondsReact UI style, and Livelocks React flow styles. So you can just verify that you have all three here. And then inside of
3:37:283 hours, 37 minutes, 28 secondsthe React flow beneath or above the controls, simply render the cursors component. You can now open another Chrome browser, login with a different
3:37:373 hours, 37 minutes, 37 secondsuser and invite yourself to the same organization. So you can see I have two different users, but both of them are in the same organization and both of them
3:37:463 hours, 37 minutes, 46 secondshave opened the exact same workflow and now their cursors are visible. Not only are their cursors visible, but all
3:37:543 hours, 37 minutes, 54 secondschanges they do are visible. Obviously, goes on both sides. And yes, there is a way to improve this throttle here. So,
3:38:033 hours, 38 minutes, 3 secondswhat you want to do is you want to go inside of the room component, find the live blocks provider, and go ahead and add throttle and set it to 16 and save.
3:38:153 hours, 38 minutes, 15 secondsAnd then go ahead and refresh your pages. And then you will see a much smoother experience. if you want to demo it to someone. This is a pretty good spot for a checkpoint. So, let's go
3:38:243 hours, 38 minutes, 24 secondsthrough our files and let's commit our changes. So, first of all, you should have liveblocks config file which has a
3:38:313 hours, 38 minutes, 31 secondsvery simple user meta object inside. You should have a package json modification with all the relevant liveelocks
3:38:383 hours, 38 minutes, 38 secondspackages. You should have a page modification which renders the room component, passes the room ID prop and
3:38:463 hours, 38 minutes, 46 secondsencapsulates the workflow shell, thus providing the live block API inside of our canvas component. Speaking of canvas
3:38:543 hours, 38 minutes, 54 secondscomponent, you should have this modification inside where we technically replace the entire local state and
3:39:013 hours, 39 minutes, 1 secondreplace it with live blocks. And we also add floating cursors around so we can see who is in the room with us. And in
3:39:103 hours, 39 minutes, 10 secondsthe actual room, you should uh have the exact snippet which we copied from the documentation. Now, since we're using the public API key, it it isn't really
3:39:193 hours, 39 minutes, 19 secondsterrible if this leaks, but let's not give anyone the opportunity anyway anyway to use your usage or anything
3:39:273 hours, 39 minutes, 27 secondslike that. So, let's replace this with an environment key. So, it's very important that you prefix your environment key with nextore public
3:39:363 hours, 39 minutes, 36 secondsbecause this will be injected in a component and inside of Nex.js JS the only environment keys which can be
3:39:443 hours, 39 minutes, 44 secondsinjected like that are those with a prefix of next public. So go ahead and name this next public liveblocks public
3:39:513 hours, 39 minutes, 51 secondskey and then the value and then inside of here let's do process dot environment next public livelocks public key and to
3:39:593 hours, 39 minutes, 59 secondsget rid of the error add an exclamation point. Don't worry we're not going to continue using this public API key. We are later going to implement proper live
3:40:083 hours, 40 minutes, 8 secondsblocks authentication and organization scoping. So only certain users from organizations can access rooms and not whoever has the URL. So go ahead and get
3:40:173 hours, 40 minutes, 17 secondsadd, get commit and get push. Remember to add the new environment variable to your railway service so that the
3:40:243 hours, 40 minutes, 24 secondsdeployment actually works if you want to test it out or share it with your friends. So click on the raw editor and after trigger secret go ahead and add
3:40:323 hours, 40 minutes, 32 secondsnext public livelocks public key update variables and click deploy.
Chapter 13: Liveblocks Auth
3:40:443 hours, 40 minutes, 44 secondsSo far we've developed a canvas component along with a live blocks integration which accepts multiple
3:40:513 hours, 40 minutes, 51 secondsparticipants. But there is a problem. So right now I'm demonstrating this with two different users both of them in the same organization.
3:41:023 hours, 41 minutes, 2 secondsBut watch this. I'm going to copy the URL of this workflow and I'm purposely going to switch my organization. So, as
3:41:103 hours, 41 minutes, 10 secondsyou can see, this organization doesn't have a single workflow. But since I know the URL, I'm just going to paste it
3:41:183 hours, 41 minutes, 18 secondshere. And would you look at that? Even though I'm in a completely different organization, I still have access to
3:41:253 hours, 41 minutes, 25 secondsthis organization's workflow. Not only do I have access, but I can actually delete the nodes as well. So what we
3:41:333 hours, 41 minutes, 33 secondsneed to focus on in this chapter is how to scope the workflow access both in our database fetcher but also in the
3:41:413 hours, 41 minutes, 41 secondslivelocks room provider so that only participants from certain organizations can access and modify our workflows and
3:41:493 hours, 41 minutes, 49 secondsrooms. First let's go ahead and protect our page.tsx which actually renders the liveblocks
3:41:563 hours, 41 minutes, 56 secondsroom and the workflow shell which eventually renders the canvas component.
3:42:013 hours, 42 minutes, 1 secondSo inside of your dashboard workflows id page.dsx right now the only thing we do is we extract the workflow ID from the params.
3:42:123 hours, 42 minutes, 12 secondsThat's the only thing we do. So let's go ahead and add out from clerk next.js server and not found from next navigation. Then let's import get
3:42:203 hours, 42 minutes, 20 secondsworkflow function from our workflows data. And then let's go ahead and extract the organization ID from out and
3:42:283 hours, 42 minutes, 28 secondsthrow the not found redirect if not available. And then let's attempt to fetch the workflow using the currently
3:42:353 hours, 42 minutes, 35 secondsscoped organization ID and the ID of the workflow we extracted from the params.
3:42:423 hours, 42 minutes, 42 secondsIf the workflow is not found, return not found. Go ahead and double check that you have the get workflow inside of your features workflows data.ts.
3:42:553 hours, 42 minutes, 55 secondsSo get workflow first accepts organization ID and then the ID. If yours is the other way around, that's
3:43:033 hours, 43 minutes, 3 secondsperfectly fine. Just make sure that you pass the props in the correct order. So just by adding this change, we should
3:43:103 hours, 43 minutes, 10 secondssee a significant improvement. Go into one of your existing workflows and copy the URL. Then go ahead and create a new
3:43:173 hours, 43 minutes, 17 secondsorganization or just switch to some other one that you have. And what you're supposed to see now is this workflow not found. The workflow you're looking for doesn't exist or may have been deleted.
3:43:293 hours, 43 minutes, 29 secondsSo make sure that you try with refresh as well. There we go. So now unless you are inside of the proper organization,
3:43:363 hours, 43 minutes, 36 secondsyou will not be able to load that workflow. So that's one big problem solved. But somehow someone could still
3:43:453 hours, 43 minutes, 45 secondsaccess the live blocks room ID and manually uh render that room and render
3:43:523 hours, 43 minutes, 52 secondsthe canvas. So we have to protect the live blocks room as well. You can find the documentation on how to add
3:43:593 hours, 43 minutes, 59 secondsauthentication to live blocks on the same page where we set up React flow using livelocks and nextJS. So here at
3:44:073 hours, 44 minutes, 7 secondsthe bottom you can click setup authentication and add user information.
3:44:113 hours, 44 minutes, 11 secondsNow this specific guide isn't really tailored to NexJS. So what I would actually recommend is scrolling a bit
3:44:183 hours, 44 minutes, 18 secondsdown and finding the authentication guide for your framework. Or you could have just clicked on authentication right here. But I just want to show you how I find my way around the docs page.
3:44:293 hours, 44 minutes, 29 secondsAnd in here you can find NextJS.
3:44:323 hours, 44 minutes, 32 secondsSo let's go ahead and first install this package and then let's add the secret key. Once you install the package, ensure that you have added the
3:44:403 hours, 44 minutes, 40 secondsLiveBlocks secret key right beneath your LiveBlocks public key. Since this is a secret key, it doesn't need and it shouldn't have the next public prefix.
3:44:503 hours, 44 minutes, 50 secondsSo make sure that it's exactly as written here. Once again, if you are connected to the docs, or should I say if you're logged in while you're reading
3:44:593 hours, 44 minutes, 59 secondsthe docs, it will automatically populate your uh secret key with your project.
3:45:033 hours, 45 minutes, 3 secondsBut in case you're not, you can find inside of the API keys your secret key and just copy it here and then paste it.
3:45:103 hours, 45 minutes, 10 secondsNow, we could follow the rest of the documentation manually, but remember that we have LiveBlocks best practices
3:45:173 hours, 45 minutes, 17 secondsskill in which we actually have all of this information available and ready for our agents to consume instead. Let's go
3:45:253 hours, 45 minutes, 25 secondsstep by step and first create the ALF endpoint route. Set up an authentication endpoint in API live AL route. DS and make it ready for ID token permissions.
3:45:383 hours, 45 minutes, 38 secondsUse clerk SDK for authentication utils.
3:45:413 hours, 45 minutes, 41 secondsUse clerk's organization ID in group ids for organization scoped access. Only create the out endpoint in route.ds. Do
3:45:503 hours, 45 minutes, 50 secondsnot perform any wiring or modification/creation of other files and make sure to include livelocks best practices. What this
3:45:583 hours, 45 minutes, 58 secondsshould do is create a single file route.ts located in this exact folder structure. And this is the API route
3:46:073 hours, 46 minutes, 7 secondswhich was created. First let's check the location API live out route.ds.
3:46:143 hours, 46 minutes, 14 secondsPerfect. Now inside we have out and current user from clerk. We have live blocks from our new package. We set up a live blocks client. We export an
3:46:233 hours, 46 minutes, 23 secondsasynchronous post function. We extract the user ID and organization ID throw if either of those doesn't exist. We
3:46:303 hours, 46 minutes, 30 secondsextract the user information. And then we use live blocks identify user passing along the user ID which we extracted
3:46:373 hours, 46 minutes, 37 secondsfrom clerk and grouping or scoping this access to an organization ID and then we
3:46:443 hours, 46 minutes, 44 secondspopulate the user info. Now your agent could have done this differently. For example, just full name would have been
3:46:523 hours, 46 minutes, 52 secondsfine but my agent decided to use a lot of fallbacks. So first it tries the full name, then it tries the username, then
3:47:003 hours, 47 minutesit tries the email address, and last it falls back to anonymous. Okay, let's leave it like that. And for the avatar,
3:47:083 hours, 47 minutes, 8 secondsit simply uses image URL. And it returns a new response with the body and the status. So this is the only file which
3:47:173 hours, 47 minutes, 17 secondsshould have been created. And it what's important is that it uses live blocks identify user and that it has these two
3:47:243 hours, 47 minutes, 24 secondsparameters. One thing I don't like from this implementation is the fact that this LiveBlocks client is initialized in
3:47:313 hours, 47 minutes, 31 secondsthe file. I would rather that it has its own file inside of the lib folder. So I would like to have liveblocks.ts
3:47:403 hours, 47 minutes, 40 secondsin here. So I'm going to highlight these lines and in the same conversation I'm going to tell it extract the liveblocks
3:47:473 hours, 47 minutes, 47 secondsclient initialization in its own lib lives. DS so it is reusable. There we go. Now my API endpoint imports from the
3:47:573 hours, 47 minutes, 57 secondsnew lib lives and now I can reuse this file whenever I need to access the livelocks client. What we have to do now
3:48:043 hours, 48 minutes, 4 secondsis we have to wire the new API endpoint into our room component. So right now we
3:48:113 hours, 48 minutes, 11 secondshave livelocks provider which uses the public API key which means that the livelocks room isn't actually verifying
3:48:193 hours, 48 minutes, 19 secondswhoever joins this room. We need to connect it to the endpoint which we've just created to make sure that the user
3:48:263 hours, 48 minutes, 26 secondshas first of all a user ID meaning it's logged in and second that it has an organization ID so that we can start scoping users to a specific organization
3:48:353 hours, 48 minutes, 35 secondsand the prompt for that would be the following wire the new API out endpoint and then tag the room tsx since I'm
3:48:433 hours, 48 minutes, 43 secondsdoing this in the same conversation I don't have to add the live blocks best practices skill but if you're doing this in a new conversation
3:48:513 hours, 48 minutes, 51 secondsThen make sure to include the live blocks best practices. If you want to, you can add it here as well. I think it will uh know that it's already loaded
3:48:593 hours, 48 minutes, 59 secondsand then it won't do it twice, but adding the scale won't hurt. And what this should do is it should get rid of the prop public API key and replace it
3:49:083 hours, 49 minutes, 8 secondswith the out endpoint. And the out endpoint should point to API live out
3:49:153 hours, 49 minutes, 15 secondswhich is the exact folder structure for our route.ts.
3:49:213 hours, 49 minutes, 21 secondsNow this isn't everything we have to do and as you can see in the message that my agent sent me here is that this right
3:49:293 hours, 49 minutes, 29 secondsnow won't work because uh ID token out means that rooms are
3:49:353 hours, 49 minutes, 35 secondsprivate by default. So they actually aren't joinable right now. What we need to do is we need to call get or create
3:49:443 hours, 49 minutes, 44 secondsroom and we need to pass the group ID using organization ID which has access
3:49:513 hours, 49 minutes, 51 secondsuh to join that room and we need to do this in a server component and the perfect place for that is our workflows
3:50:013 hours, 50 minutes, 1 secondpage.tsx with which we started this whole chapter. So the prompt we can use here
3:50:083 hours, 50 minutes, 8 secondsis wire up get or create room with org ID access and then tag that page.tsx. Just make sure it's the correct page.
3:50:163 hours, 50 minutes, 16 secondsAnd this should completely finish the wiring of live blocks out to our component. So you should now have the
3:50:233 hours, 50 minutes, 23 secondsfollowing function. Live blocks get or create room. Pass in the ID from the params. Then open the options. Set the default accesses to an empty array.
3:50:353 hours, 50 minutes, 35 secondsgroup accesses scoped to this organization ID and give it a permission of room. Right? The metadata is optional, but if your agent passed
3:50:443 hours, 50 minutes, 44 secondsanything here, it won't hurt. And I like how it created this inline because this isn't going to be reused anywhere. If
3:50:523 hours, 50 minutes, 52 secondsyours created a separate util for that, it's fine, but you can tell it to inline directly inside of page.tsx.
3:51:003 hours, 51 minutesAnd it should have also added the live blocks import. That's why I wanted to extract that in the lib because I knew I was going to reuse it in another server
3:51:093 hours, 51 minutes, 9 secondscomponent here. And as you can see, my agent just told me the full ID token flow is now wired end to end. So we have
3:51:173 hours, 51 minutes, 17 secondsa room component which now uses the out endpoint. Now that out endpoint
3:51:243 hours, 51 minutes, 24 secondsidentifies the user and scopes scopes it under its organization ID. And then whoever tries to visit the workflow's ID
3:51:333 hours, 51 minutes, 33 secondsattempts to call get or create room using their organization ID. So we can check whether they are scoped to access
3:51:403 hours, 51 minutes, 40 secondsthis or not. So I'm going to show you the full six files which were modified so you can compare with yours. Starting
3:51:483 hours, 51 minutes, 48 secondswith the package JSON we have livelocks node package added. Then inside of our
3:51:543 hours, 51 minutes, 54 secondsapp API live out we have the route.ts TS which is responsible for authenticating the user, extracting the user
3:52:023 hours, 52 minutes, 2 secondsinformation and running livelocks identify user scoped to the organization ID. We then have an extracted live
3:52:113 hours, 52 minutes, 11 secondsblocks util in lib lives. We have a room.tsx modification where we remove the usage
3:52:183 hours, 52 minutes, 18 secondsof public API key and instead we use the out endpoint which points to our new endpoint. And last we have page.tsx. tsx
3:52:273 hours, 52 minutes, 27 secondswhich now protects the database access to a specific workflow scoped to the organization ID and we use our live
3:52:353 hours, 52 minutes, 35 secondsblocks util get or create room for that workflow ID scoped with the correct group access for that organization. Now
3:52:443 hours, 52 minutes, 44 secondslet's test it out. What you should test first is two users who belong to the same organization and have access to the
3:52:523 hours, 52 minutes, 52 secondssame workflows and then try and meet each other in one workflow. Both should be able to load this live blocks room
3:53:013 hours, 53 minutes, 1 secondand you should see each other's changes in real time. Now we already know what happens if I try to copy the URL and
3:53:083 hours, 53 minutes, 8 secondsswitch my organization. We get this error workflow not found. But this isn't anything new. We know why this happens.
3:53:183 hours, 53 minutes, 18 secondsIt happens because of this block right here. But that isn't what we just spent a couple of minutes implementing. So
3:53:263 hours, 53 minutes, 26 secondslet's actually hide this function. And let's hide the metadata if you have any so you don't have errors because what's going to happen now is there is no
3:53:353 hours, 53 minutes, 35 secondslonger a database protection but only the live blocks protection. So let's see if this group access actually works.
3:53:443 hours, 53 minutes, 44 secondsWhat happens now? So I purposely hit this block and now I'm going to refresh in this correct organization where
3:53:513 hours, 53 minutes, 51 secondseverything should still work fine. But what happens in this other other user?
3:53:563 hours, 53 minutes, 56 secondsIf I refresh, as you can see, I no longer get that not found. But if I click on the error here, you will see
3:54:033 hours, 54 minutes, 3 secondsthat correctly live has responded. You have no access to this room. That is because the out endpoint has failed
3:54:123 hours, 54 minutes, 12 secondsbecause this user is currently scoped to a different organization meaning that it shouldn't be able to load this live
3:54:193 hours, 54 minutes, 19 secondsblocks room. So our ID token actually works. Brilliant. And now we can of course revert these changes. So we have
3:54:283 hours, 54 minutes, 28 secondsboth the database level protection and the liveblocks cloud level protection using ID token out. So go ahead and
3:54:353 hours, 54 minutes, 35 secondscommit all of these changes so we have a clean slate for the next feature we have to develop. Even though our current implementation works as expected, there
3:54:443 hours, 54 minutes, 44 secondsis one problem when it comes to preserving the data in live blocks about these rooms and everything inside of
3:54:513 hours, 54 minutes, 51 secondsthem. As you can see, as we developed our live blocks implementation, at first we had some public rooms and then once
3:54:593 hours, 54 minutes, 59 secondswe've implement ID token access, we now have restricted rooms. But as you can see, still all of these rooms are
3:55:073 hours, 55 minutes, 7 secondsrestricted to the same organization ID default. Even though their definitions sound similar, organizations or groups
3:55:153 hours, 55 minutes, 15 secondsserve two different purposes. Groups are used to decide who has access to a room, whereas organizations are used to scope
3:55:223 hours, 55 minutes, 22 secondswhere Liveblocks data and resources should be stored. This isn't immediately obvious, but Liveblocks is also its own
3:55:313 hours, 55 minutes, 31 secondsdatabase. And when you click on a room, you will see that they have several data tables here like comments, document,
3:55:383 hours, 55 minutes, 38 secondsmetadata, etc. If you go inside of document and select live blocks storage as the option, you will actually see
3:55:453 hours, 55 minutes, 45 secondsreact flow object inside. So that is why it's important to compartmentalize in the proper organization ID so that
3:55:533 hours, 55 minutes, 53 secondssensitive data isn't held in one shared pool with all other rooms in your database. Luckily, we can achieve this very easily in just a few lines of code.
3:56:053 hours, 56 minutes, 5 secondsFirst, go inside of your live blocks out endpoint and when you identify the user, also append the organization ID and then
3:56:143 hours, 56 minutes, 14 secondsgo inside of your page where you invoke get or create room and do the same here.
3:56:193 hours, 56 minutes, 19 secondsI would recommend going inside of your live blocks dashboard and actually deleting the existing rooms at this point just to ensure that no conflicts
3:56:283 hours, 56 minutes, 28 secondsare created. Then once you have a clean slate, go ahead and visit your app at localhost 3000. Go ahead and click on any of the workflows or simply create a
3:56:363 hours, 56 minutes, 36 secondsnew one. Nothing much should change in the UI. But if you take a look at the live blocks dashboard, you will now see
3:56:433 hours, 56 minutes, 43 secondsthat the resource is properly scoped to this organization. And if it says default here, just go ahead and give it
3:56:513 hours, 56 minutes, 51 secondsa refresh. And then it's going to load the actual organization to which this is scoped. In the organization's documentation page, we can find the
3:56:583 hours, 56 minutes, 58 secondsrecommendation on how to refresh liveblocks initialization whenever an organization needs to change. What they
3:57:073 hours, 57 minutes, 7 secondsrecommend is simply invoking location.reload.
3:57:113 hours, 57 minutes, 11 secondsEven though I wasn't really able to encounter any stale information, as I can see, everything works just fine. So
3:57:193 hours, 57 minutes, 19 secondsthe problem in theory should be if you refresh and load the initial page in this scenario, right? So no workflows
3:57:283 hours, 57 minutes, 28 secondsand then switch to a proper organization and click on the one which we've created previously. In theory, sometimes it can
3:57:363 hours, 57 minutes, 36 secondshappen that uh a stale organization ID gets access here. So, if you want to prevent any chance of that happening,
3:57:453 hours, 57 minutes, 45 secondsyou can revisit your app sidebar component, find the organization switcher, and go ahead and give it the following props. What this is going to
3:57:543 hours, 57 minutes, 54 secondsdo is it's going to refresh the page every time an organization changes, an organization is left, or an organization
3:58:023 hours, 58 minutes, 2 secondsis created. Meaning that it's going to invoke this location.
3:58:073 hours, 58 minutes, 7 secondsincreasing the chances uh or should I say reducing the change uh the chances of an organization ID being stale. So
3:58:153 hours, 58 minutes, 15 secondsnow that all of the authentication and organization scoping logic is wired, let's fix one more issue. When I switch
3:58:223 hours, 58 minutes, 22 secondsbetween my workflows, I can see that there are two different loading states.
3:58:263 hours, 58 minutes, 26 secondsThe first one is a spinner and then the second one is just a text loading. That is because we have two loading states.
3:58:323 hours, 58 minutes, 32 secondsThe first loading state is invoked from the page. tsx in our workflows ID page the loading state is invoked every time
3:58:413 hours, 58 minutes, 41 secondswe await something. So that spinner first loads out then it loads get workflow and then once the room loads we
3:58:513 hours, 58 minutes, 51 secondsrender the fallback and that's where the loading text appears. So go ahead and change that fallback to render a spinner
3:59:003 hours, 59 minutesfrom components UI spinner. So make sure you add this import and render this div which makes it full screen and centered.
3:59:083 hours, 59 minutes, 8 secondsAnd that will essentially make it look the same as our loading component here.
3:59:143 hours, 59 minutes, 14 secondsAnd then if you try you will see that it kind of uh twitches but it looks much better than the previous example we've
3:59:223 hours, 59 minutes, 22 secondshad. Let's review these four modifications we've done. We've added organization ID to our live blocks AL route when we identify the user. We've
3:59:313 hours, 59 minutes, 31 secondsdone the same in the workflows ID page when we do get or create room. We've added these three props to the
3:59:393 hours, 59 minutes, 39 secondsorganization switcher. And we modified the room component so that the fallback renders a spinner rather than the
3:59:463 hours, 59 minutes, 46 secondsloading text. Remember that we also added a new environment variable key. So go ahead inside of your railway, click
3:59:533 hours, 59 minutes, 53 secondson raw editor and add live secret key update variables. You don't have to redeploy because now we're going to
4:00:014 hours, 1 secondcommit. Actually, you do have to click deploy to apply the change. My apologies. So, click deploy anyway. And then go ahead and stage commit and push your changes.
Chapter 14: Names & Avatars
4:00:184 hours, 18 secondsThe collaboration feature in our project is starting to shape pretty well, but we are still missing a few features. So
4:00:254 hours, 25 secondsfar, we were able to see the other person's cursor, but we didn't see their name attached to the cursor. We also
4:00:324 hours, 32 secondsdidn't add the avatar stack, which displays the images of all users who are in the room with us. So, let's implement that in this chapter. First, let's
4:00:414 hours, 41 secondsmodify our canvas component. Then, import panel from XYlow React. Next,
4:00:484 hours, 48 secondsimport avatar stack from Liveblocks React UI. And the last thing we have to do is render that panel with a position of top right and avatar stack inside.
4:01:004 hours, 1 minuteAnd once you save and revisit any of your workflows, you will now see an avatar stack at the top right corner.
4:01:074 hours, 1 minute, 7 secondsThe problem is there is no user information. All users will be presented as anonymous. In order to fix the issue
4:01:144 hours, 1 minute, 14 secondsin which all of our users in the room are scoped as anonymous, I would like us to go and search for the component which
4:01:224 hours, 1 minute, 22 secondswe are using. So avatar stack in here you will find information on how to use it which we just did. But scrolling a
4:01:304 hours, 1 minute, 30 secondsbit down will also instruct you on how to add the user information. So the prop which we need to use is resolve users.
4:01:394 hours, 1 minute, 39 secondsLet's run the following prompt. Add a post endpoint at API live users route.ts
4:01:474 hours, 1 minute, 47 secondsthat takes user ids payload and returns their display info which is name and avatar in the same order and put null
4:01:564 hours, 1 minute, 56 secondsfor unknown ones. Resolve them from clerk. Require an outed user and organization. Only develop the route.ts
4:02:054 hours, 2 minutes, 5 secondsfile. Do not modify other files. and I've included LiveBlocks best practices and clerk backend API skill. Let's
4:02:134 hours, 2 minutes, 13 secondsreview what the agent has created. So I have a new route inside of my live blocks folder inside of the API folder
4:02:204 hours, 2 minutes, 20 secondscalled users. Now I'm going to read through the description of what the route does. First we have an outgate
4:02:274 hours, 2 minutes, 27 secondswhich reads out and returns 401 unless there is both user ID and organization ID. Next we have input validation. So
4:02:364 hours, 2 minutes, 36 secondsthis is something that sometimes the agent will do, sometimes it won't. So if you don't have a snippet like this, but instead maybe you just have user ids
4:02:454 hours, 2 minutes, 45 secondsextracted from request JSON, that's honestly okay. Next, it appears that we iterate over those user ids. We check if
4:02:524 hours, 2 minutes, 52 secondsthey are empty and then we return back an empty array. So we don't unnecessarily compute or initialize any clients. Then we initialize clerk client
4:03:014 hours, 3 minutes, 1 secondand we get the user list using the ids which we got from our payload. We also
4:03:084 hours, 3 minutes, 8 secondsscope the organization ID to ensure that this endpoint cannot be abused by someone just wanting to get a list of
4:03:154 hours, 3 minutes, 15 secondsusers uh using their ids. We also assign the limit to the ID's length limit. And
4:03:234 hours, 3 minutes, 23 secondsthen we map each user by ID in this exact format. and then we resolve each
4:03:304 hours, 3 minutes, 30 secondsuser's information. So, I can't really guarantee that your agent will produce the exact same code, but I assume it's going to be something similar to this.
4:03:404 hours, 3 minutes, 40 secondsWhat's important is that you in the end have something resolved which produces uh an object like this. Basically, an
4:03:484 hours, 3 minutes, 48 secondsobject with a name with an avatar inside of an array. And if it wasn't able to resolve it, it falls back to null.
4:03:584 hours, 3 minutes, 58 secondsBasically it matches the user info which we extracted from our global liveblocks interface user meta info. So that is generated in liveblocks config.ts.
4:04:104 hours, 4 minutes, 10 secondsNow just in case your API route looks wildly different from this one remember that you can always go ahead and find
4:04:184 hours, 4 minutes, 18 secondschapter 13 and go inside of app API and find the exact route. So now we have to
4:04:254 hours, 4 minutes, 25 secondswire in that new endpoint into the resolve users prop. We can achieve this with a simple prompt in the room
4:04:334 hours, 4 minutes, 33 secondscomponent. Add a resolve users prop to the live blocks provider in line in the prop. It should post the user ids to our
4:04:424 hours, 4 minutes, 42 secondsAPI live users endpoint and return the parsed response. If the request fails, return undefined. And that should
4:04:494 hours, 4 minutes, 49 secondsproduce an output similar to this. You should now have a resolve users prop attached to your live blocks provider
4:04:564 hours, 4 minutes, 56 secondswhich is an asynchronous function which extracts the user ids who are in this room. It opens a try and catch block and
4:05:044 hours, 5 minutes, 4 secondsinside of the try block it attempts to fetch the API live blocks users and passes the user ids as the body payload.
4:05:124 hours, 5 minutes, 12 secondsIf the request fails, we return undefined. If something else fails, we also return undefined in the catch.
4:05:184 hours, 5 minutes, 18 secondsOtherwise, we simply await response.json.
4:05:234 hours, 5 minutes, 23 secondsAnd now go ahead inside of your localhost 3000 and refresh your workflow. And if we've done this correctly, we should now see the user
4:05:314 hours, 5 minutes, 31 secondsavatar here and the name of the loggedin user. And if you try joining with two different users, you will now see the
4:05:384 hours, 5 minutes, 38 secondsactual name of each user next to their cursor. And in the top right corner, you will see the name of users inside of
4:05:464 hours, 5 minutes, 46 secondsthis room. So after all of these prompts, you should have one new route and two modifications to existing components, the canvas and the room.
4:05:554 hours, 5 minutes, 55 secondsLet's go ahead and commit stage and push these changes.
Chapter 15: Workflow Toolbar
4:06:064 hours, 6 minutes, 6 secondsNow that we've added collaboration to our workflows, let's focus on the right sidebar component. The right sidebar component will have several purposes.
4:06:154 hours, 6 minutes, 15 secondsThe default one is the toolbar. The toolbar is going to display two categories of nodes, triggers and actions. Clicking on the node will
4:06:234 hours, 6 minutes, 23 secondssimply add it to the canvas. The second purpose of the right sidebar is the editor. Whenever a user selects a node
4:06:314 hours, 6 minutes, 31 secondsfrom the canvas, we're going to automatically switch to the editor and display that node's information. From here, user will be able to modify the
4:06:404 hours, 6 minutes, 40 secondsnode data. To speed up development of this component, I've prepared a template in our GitHub repository. The template
4:06:474 hours, 6 minutes, 47 secondsonly focuses on the UI and avoids adding any business logic. Instead, that's what we're going to focus this lesson being
4:06:554 hours, 6 minutes, 55 secondson. So, we'll learn how to add the actual functionality to the component rather than you watching me type a thousand class names and copy after me.
4:07:044 hours, 7 minutes, 4 secondsOnce you're in the repository, you can either use the main branch or preferably go and find chapter 14 workflow toolbar
4:07:144 hours, 7 minutes, 14 secondsand then go ahead and find the templates folder. In here, you will find a new component on top of the two existing
4:07:214 hours, 7 minutes, 21 secondsones that we've had called right sidebar. Now go inside of your existing features, workflows, components, right
4:07:294 hours, 7 minutes, 29 secondssidebar and replace the entire content inside with the template. As I've said, the template exclusively focuses on the
4:07:384 hours, 7 minutes, 38 secondsUI. As you can see, writing this together honestly wouldn't be too educational. You would just have to pause the video all the time and then
4:07:464 hours, 7 minutes, 46 secondscopy a bunch of these class names. They are nothing more than compositions of chats UI components. I've also written
4:07:544 hours, 7 minutes, 54 secondsdescriptive comments so we understand exactly what each of these components is doing and we're going to go over the entire thing together. But first, let's
4:08:024 hours, 8 minutes, 2 secondssee what actually renders. Now, as you can see, our right side of our component now has the toolbar which reads from our node registry and displays the correct
4:08:124 hours, 8 minutes, 12 secondsnodes. It also separates them in their correct categories. We also have the editor tab which we're going to wire in
4:08:204 hours, 8 minutes, 20 secondsso that when we click on a node, it's loaded here and we can change its data.
4:08:254 hours, 8 minutes, 25 secondsWe also have a run button at the top as well as a drop-down with an option to delete the workflow. None of these
4:08:324 hours, 8 minutes, 32 secondsactions buttons do anything, but that's what we're going to focus on in this chapter. Enabling the right sidebar component. Let's go over the source code
4:08:394 hours, 8 minutes, 39 secondsof this component to understand what we are working with. The first function we have is the node icon. node icon is used to display the icon inside of an accent
4:08:494 hours, 8 minutes, 49 secondscolor. So exactly what you see here in the start and open URL. The actual icon as well as the accent is extracted from
4:08:574 hours, 8 minutes, 57 secondsthe node registry which matches the type which was passed for that node icon. So node registry is a very important
4:09:054 hours, 9 minutes, 5 secondscomponent in this project because it's the manifest. It is the source of truth for all nodes. So later when we point
4:09:124 hours, 9 minutes, 12 secondsour agent and tell it to create 50 new nodes, all it's going to have to do is modify the node registry and the right
4:09:214 hours, 9 minutes, 21 secondssidebar component, for example, will automatically load all of those nodes and their respective icons and their respective accent colors. Next, we have
4:09:294 hours, 9 minutes, 29 secondsthe section component. The section component is this right here. So either toolbar or editor but it also has the
4:09:394 hours, 9 minutes, 39 secondsoption to display an icon if needed for this scenario when we select a node in
4:09:464 hours, 9 minutes, 46 secondsthe canvas. So then we will be able to display its name as well as its icon. So depending on the state we can either use the section component to display the
4:09:554 hours, 9 minutes, 55 secondstext toolbar and editor or to display an icon of the node user has selected from the canvas. Next we have field input.
4:10:054 hours, 10 minutes, 5 secondsField input is this exact component right here which is used to uh render the nodes data. Next we have the
4:10:134 hours, 10 minutes, 13 secondsinspector function which is as the comment says the editor tab. So this tab right here which currently renders no
4:10:214 hours, 10 minutes, 21 secondsnode selected as you can see in this paragraph right here. So if there is no node it will render no node selected.
4:10:294 hours, 10 minutes, 29 secondsOtherwise, if we do have a node selected, we are once again going to extract its definition from the node registry and then we will be able to uh render all of the fields that it has.
4:10:404 hours, 10 minutes, 40 secondsYou can see how we iterate over the fields and depending on the field, we render the appropriate component. For
4:10:484 hours, 10 minutes, 48 secondsexample, in our node registry, the start node has no fields. So, we will simply display no properties. But if we click
4:10:554 hours, 10 minutes, 55 secondson the open URL node, we will read, hey, we have one field with a placeholder YouTube.com, which is exactly what ends
4:11:034 hours, 11 minutes, 3 secondsup being rendered here. Next, we have the toolbar tab. So that is the default view right here. And in here, we define
4:11:124 hours, 11 minutes, 12 secondsthe sections. You can think of section of sections as categories for our nodes.
4:11:174 hours, 11 minutes, 17 secondsSo we separate that into triggers and actions. Once again, we make sure that this is compatible with our node
4:11:244 hours, 11 minutes, 24 secondsregistry because each node needs a kind and so far we've only established two kinds trigger and action which is also
4:11:334 hours, 11 minutes, 33 secondsthe type step node kind here which we make sure that we strictly type here. So we not something like this cannot happen. It has to be strictly typed.
4:11:424 hours, 11 minutes, 42 secondsThat's why node registry is the source of truth. Then we go ahead and we use the entire node registry export which is
4:11:504 hours, 11 minutes, 50 secondsthis. So this exact object which holds all of our nodes and we create definitions for every single component.
4:11:584 hours, 11 minutes, 58 secondsThen we use the plet and the plet basically renders the accordians by iterating over our sections. We defined
4:12:074 hours, 12 minutes, 7 secondsthe sections here which are basically categories and inside of each accordion which can be collapsed as you can see it
4:12:144 hours, 12 minutes, 14 secondssimply goes over all of the items inside or definitions which we extracted from
4:12:204 hours, 12 minutes, 20 secondsthat uh node registry and we render a button for each of the node and we also
4:12:274 hours, 12 minutes, 27 secondsrender that node icon which we first saw at the top of the component. We then have the header component which is basically this at the top which has a
4:12:364 hours, 12 minutes, 36 secondsdrop-own menu which simply renders a delete workflow button and we also have a run button component right here. So
4:12:444 hours, 12 minutes, 44 secondsI've purposely separated those two so it's easier for us to work with and then we have the sidebar component itself which is the whole thing and all of these other things are plugged into it.
4:12:544 hours, 12 minutes, 54 secondsSo actions menu run button and then we have the editor the toolbar the plet the inspector. So now that we've established
4:13:034 hours, 13 minutes, 3 secondsthe source code and we know how it works, let's go ahead and make this right sidebar component functional.
4:13:094 hours, 13 minutes, 9 secondsBefore we implement right sidebar functionality, I would actually recommend committing this file. The reason is that git diff right now is
4:13:194 hours, 13 minutes, 19 secondsabsolutely huge. And now imagine trying to look at your agentic coding changes in this file on top of that. So to make this easier for us, go ahead and commit.
4:13:294 hours, 13 minutes, 29 secondsYou don't have to push because we're still developing. And now every change we do will be clearly visible in the git
4:13:374 hours, 13 minutes, 37 secondsdiff. The first feature I want to add is the ability to add new nodes to the canvas when we click inside of the
4:13:444 hours, 13 minutes, 44 secondstoolbar section. To understand how to implement this, we need to go into the right sidebar source code and find which
4:13:524 hours, 13 minutes, 52 secondsfunction is responsible for rendering these two buttons. Inside of the right sidebar, you can find the pallet
4:13:594 hours, 13 minutes, 59 secondsfunction, which is the toolbar tab, which renders a button per node type that it adds to the canvas. So once we
4:14:074 hours, 14 minutes, 7 secondsrender the sections, meaning the accordians, which are basically categories of nodes, inside of each category, we render the definitions.
4:14:164 hours, 14 minutes, 16 secondsEach definition is presented as a button with the node icon, which is exactly what we are seeing here. And right now
4:14:224 hours, 14 minutes, 22 secondswe already have an on click which calls the add function right here. The problem is this function currently doesn't do
4:14:304 hours, 14 minutes, 30 secondsanything. Let's construct the following prompt. This will be a prompt in three paragraphs. So don't immediately execute it. We're going to additionally add more
4:14:384 hours, 14 minutes, 38 secondscontext about how we want this function to look like. First the main functionality. When I click on a node in
4:14:454 hours, 14 minutes, 45 secondsthe pallet in our right sidebar.tsx tsx added to the canvas in the middle of the
4:14:524 hours, 14 minutes, 52 secondscurrent view. Generate the nodes ID with crypto random uyu ID. That's the first
4:15:004 hours, 15 minutesparagraph. Now let's add some more information about how this function should actually work. If I add several
4:15:074 hours, 15 minutes, 7 secondsnodes of the same type, so if I have multiple agent nodes or multiple open URL nodes, we need to differentiate
4:15:164 hours, 15 minutes, 16 secondsthem. So number them act one, act two, open URL 1, open URL 2. So they stay
4:15:234 hours, 15 minutes, 23 secondseasy to tell apart. But only allow a single trigger node. So we are not going to allow workflows which are able to be uh executed in multiple trigger nodes.
4:15:364 hours, 15 minutes, 36 secondsSo only one trigger node per workflow.
4:15:394 hours, 15 minutes, 39 secondsSo if one already exists, show an error with a soner toast instead of adding another. And then let's add the last piece of information before we execute
4:15:474 hours, 15 minutes, 47 secondsthis. The pallet lives in the sidebar component which is outside of our canvas
4:15:544 hours, 15 minutes, 54 secondscomponent. So let's actually tag that component as well. So the two need to share one react flow store. So make sure
4:16:034 hours, 16 minutes, 3 secondsto wrap the workflows ID page.tsx which we could also tag directly. So
4:16:114 hours, 16 minutes, 11 secondsdashboard workflows id page.tsx in a react flow provider. So it sits above both the canvas and the sidebar.
4:16:224 hours, 16 minutes, 22 secondsNow remember how we modified our agents.md to instruct it how to use react flow. In
4:16:314 hours, 16 minutes, 31 secondstheory it should recognize that this is a scenario where it should load that documentation. But just in case we can
4:16:384 hours, 16 minutes, 38 secondsuh slightly remind it follow the agents or cloudnd rule for using react flow. So this is our full prompt. Let's see what kind of function it's going to develop.
4:16:494 hours, 16 minutes, 49 secondsLooks like the generation was successful. Looking at the summary, it's describing exactly what we requested in our prompt. But let's look at the source code to see exactly what was generated.
4:17:014 hours, 17 minutes, 1 secondSo the first thing I would expect is that we have a modification in our dashboard workflows id page.tsx.
4:17:104 hours, 17 minutes, 10 secondsSo it imported react flow provider from xy flow react and then inside of the room component it actually encapsulated
4:17:194 hours, 17 minutes, 19 secondsmy workflow shell within the work react flow provider. That is because the workflow shell is both responsible for
4:17:264 hours, 17 minutes, 26 secondsrendering the canvas and for the right sidebar. So canvas and right sidebar are siblings, right? So we needed to put
4:17:344 hours, 17 minutes, 34 secondsthem under the same context because right now the canvas uh has access to react flow using use live blocks flow
4:17:434 hours, 17 minutes, 43 secondsbut right sidebar had no access to that component. They are siblings, right? So that's why we needed to add a react flow
4:17:514 hours, 17 minutes, 51 secondsprovider wrapping the workflow shell. So now both our canvas and our right sidebar have the same axis. Now let's
4:17:594 hours, 17 minutes, 59 secondstake a look at the right sidebar the actual component. So we have use react flow and use store imported from xy flow
4:18:074 hours, 18 minutes, 7 secondsreact and we have toast imported from sonner. Those are the import changes.
4:18:124 hours, 18 minutes, 12 secondsNow [snorts] we have no other changes besides the pallet function which is perfect exactly what we wanted. So using
4:18:194 hours, 18 minutes, 19 secondsthe use react flow we first give it a type step node type. So it matches our
4:18:254 hours, 18 minutes, 25 secondsnode registry. From here we extract get nodes, get viewport and add nodes. So my
4:18:334 hours, 18 minutes, 33 secondsagent decided to first calculate the width and the height of the canvas. So in the add function, it can calculate
4:18:434 hours, 18 minutes, 43 secondswhere to position it because I requested I wanted to position it in the center.
4:18:484 hours, 18 minutes, 48 secondsBut let's see what it does first. So inside of the add function, it first reads the definition of the node I want
4:18:564 hours, 18 minutes, 56 secondsto add by using the type from my add function here. And then it extracts the definition using node registry type.
4:19:074 hours, 19 minutes, 7 secondsThen it loads all of the nodes that I currently have in my canvas and it goes through the definition. If the
4:19:144 hours, 19 minutes, 14 secondsdefinition of the node I'm trying to add is a trigger and my nodes already have a trigger component, it throws an error
4:19:234 hours, 19 minutes, 23 secondsand an early return. A workflow can only have one trigger. So that's the guard rail which we uh set in the prompt. In
4:19:334 hours, 19 minutes, 33 secondshere it defines the count of the nodes of that same type which I'm trying to add. So it counts how many nodes do you
4:19:424 hours, 19 minutes, 42 secondshave in the canvas right now and then it constructs the title of this node which is going to add based on that count plus
4:19:514 hours, 19 minutes, 51 secondsone. So we then have open URL 1 open URL 2.
4:19:564 hours, 19 minutes, 56 secondsThen as I said it uses the get viewport to get the coordinates and the relative zoom so it can calculate the position based on our canvas's width and height
4:20:054 hours, 20 minutes, 5 secondsand whatever it needs to do to get to the center. I trust AI when it comes to math. And then it uses add nodes which
4:20:134 hours, 20 minutes, 13 secondsit extracted from the use react flow and it creates the ID using crypto random UU ID gives the type of step that is
4:20:214 hours, 20 minutes, 21 secondsbasically the name of our custom step node component gives it a position and then passes along the data the type the
4:20:284 hours, 20 minutes, 28 secondskind which is mapped to definition kind which can be action or trigger the generated title and empty values. Looks
4:20:374 hours, 20 minutes, 37 secondsvery good. Now, let's go ahead and actually see if it works. So, I like how it didn't modify any files it didn't
4:20:434 hours, 20 minutes, 43 secondsneed to modify. So, if I go ahead and first try to add another trigger node.
4:20:484 hours, 20 minutes, 48 secondsThere we go. A workflow can only have one trigger. Let's click on the open URL. And would you look at that? We can
4:20:564 hours, 20 minutes, 56 secondsnow add different nodes. And look at how it increments the number of nodes.
4:21:024 hours, 21 minutes, 2 secondsBeautiful. And since we already connected live blocks, we actually have data persistence built in. So if you do
4:21:114 hours, 21 minutes, 11 secondswhatever you want to do with these nodes and then change your workflow and then go back to the one you were in, you will see the data is persisted. That's right.
4:21:214 hours, 21 minutes, 21 secondsSo livelocks is currently the source of truth for our uh react flow data but obviously we are later going to
4:21:304 hours, 21 minutes, 30 secondssynchronize this with our schema graph field but not right now. Brilliant. So
4:21:374 hours, 21 minutes, 37 secondsthis is how the function should look like. I hope yours is something similar.
4:21:424 hours, 21 minutes, 42 secondsIf it isn't you can of course visit this exact branch. So go ahead and find a chapter 14 uh workflow toolbar and then
4:21:514 hours, 21 minutes, 51 secondsgo ahead and find uh not inside of templates right sidebar but go inside of my features workflows components and in
4:22:004 hours, 22 minuteshere you will find right sidebar and you will find this exact uh pallet functionality. So if you have this
4:22:074 hours, 22 minutes, 7 secondsworking, of course it doesn't need to be the exact same code. It can be slightly different as long as the functionality is the same and you can actually add
4:22:144 hours, 22 minutes, 14 secondsnodes and they increment in numbers. So if you did this, I would recommend actually uh committing this so you once again have a clean slate so it's easier
4:22:234 hours, 22 minutes, 23 secondsto track uh next changes. So you can commit with something like add toolbar add function. Now that we've encapsulated our canvas component and
4:22:324 hours, 22 minutes, 32 secondsour right sidebar component under the same umbrella of React flow provider, we can add another feature which makes it
4:22:394 hours, 22 minutes, 39 secondsso that whenever a node is selected in the canvas component, its information is displayed in the editor tab and we can
4:22:464 hours, 22 minutes, 46 secondsachieve this in one line. What's important is that you have use store imported from XYlow React. Then scroll
4:22:554 hours, 22 minutes, 55 secondsdown to right sidebar function and replace the template version of the selected constant into the use store
4:23:034 hours, 23 minutes, 3 secondsselector version which has access to the nodes and has the ability to find the selected node. And if you try it out,
4:23:114 hours, 23 minutes, 11 secondsselecting any node in the canvas will properly render that node information in the editor. With the selected constant
4:23:194 hours, 23 minutes, 19 secondspopulated, all we do is pass it to the inspector component. The inspector component then matches its definition
4:23:274 hours, 23 minutes, 27 secondsfrom our node registry. That's how it renders the necessary fields like URL
4:23:344 hours, 23 minutes, 34 secondsand the input. And for start node, it doesn't render anything because that's exactly what we have defined in our node
4:23:424 hours, 23 minutes, 42 secondsregistry. The start node has no fields, but open URL has one field called URL.
4:23:484 hours, 23 minutes, 48 secondsSo that's exactly what's rendered. If you were to play around and add another field in the fields array of the open
4:23:564 hours, 23 minutes, 56 secondsURL, it would immediately be displayed in the editor tab. If you've added any additional fields, make sure that you now remove them and then go ahead and
4:24:054 hours, 24 minutes, 5 secondsstage and commit this change. Now, let's make it so that the editor fields actually store the data which we type
4:24:134 hours, 24 minutes, 13 secondsinside of these fields. Right now we can't even type inside because there is no value control in these fields. So
4:24:214 hours, 24 minutes, 21 secondsinside of the right sidebar find the inspector function and go ahead and add use react flow and give it step node
4:24:304 hours, 24 minutes, 30 secondstype inside and extract update node data. Now let's scroll down until we
4:24:374 hours, 24 minutes, 37 secondsfind field input on change and in here let's remove the template to-do and let's actually use that extracted
4:24:454 hours, 24 minutes, 45 secondsfunction update node data target the correct node ID and then update the values matching that field key which we
4:24:544 hours, 24 minutes, 54 secondsare currently modifying which is currently rendered using definition fields and preserving all other values
4:25:014 hours, 25 minutes, 1 secondthis node might have and assigning the value to that specific key. If you try typing into the field now, it's going to
4:25:104 hours, 25 minutes, 10 secondswork. And if you refresh, you will see that what we've entered is persisted, but it's currently only visible in the
4:25:184 hours, 25 minutes, 18 secondseditor tab. It would be nice if it was also visible in the node component. To achieve that, we have to go inside of
4:25:254 hours, 25 minutes, 25 secondsour features workflows components step node. Then let's extract the values from the data. So we can extract the fields
4:25:344 hours, 25 minutes, 34 secondsfrom the definition of this node. And once we have the fields, all we have to do is iterate over their values and
4:25:414 hours, 25 minutes, 41 secondsrender them. We are going to render them right in between the closing tag for this div and this handle. So go ahead and add this snippet and save the file.
4:25:524 hours, 25 minutes, 52 secondsOnce you go back to your canvas, your nodes are now going to display each field and its respective value. If you
4:25:594 hours, 25 minutes, 59 secondswant to see how this snippet works in action with more fields, go inside of your node registry, find the open URL
4:26:074 hours, 26 minutes, 7 secondsnode and add an additional field. Then go into the editor and add some value to that field. You will see that the value
4:26:154 hours, 26 minutes, 15 secondsis immediately rendered in the step node component. After you've done testing, remove the additional field from the
4:26:224 hours, 26 minutes, 22 secondsopen URL node and stage and commit your changes. Let's improve the user experience of our app so that whenever we click on a node in the canvas, we make the editor tab automatically open.
4:26:344 hours, 26 minutes, 34 secondsInside of the right sidebar function, let's add a new state previous selected ID. And let's give it a default value of
4:26:424 hours, 26 minutes, 42 secondsselected do ID. Make sure that you use the optional operator in case the selected is undefined. Then let's open
4:26:504 hours, 26 minutes, 50 secondsan if clause which checks if we have any selected node and if the currently selected node is different from what we
4:26:584 hours, 26 minutes, 58 secondshave previously stored. Then let's modify this new field which we've registered. And let's change the tab to editor. And if you try it out every time
4:27:074 hours, 27 minutes, 7 secondsyou click on the node in the canvas it's going to automatically open the editor.
4:27:124 hours, 27 minutes, 12 secondsNow depending on the node, sometimes we are going to need to render a simple input, but sometimes we're going to need to render a text area. So let's create a
4:27:214 hours, 27 minutes, 21 secondsprompt which is going to enable the right sidebar to dynamically decide which component to render depending on the field property. We can achieve that
4:27:304 hours, 27 minutes, 30 secondswith the following prompt. Let a field opt into rendering as a larger multi-line text area instead of a single
4:27:384 hours, 27 minutes, 38 secondsline input. First in the node registry, add a flag to the field definition. So any field can mark itself as multi-line.
4:27:474 hours, 27 minutes, 47 secondsThen in the right sidebar component, add a new field component that reads that flag and dynamically renders either the
4:27:564 hours, 27 minutes, 56 secondssingle line input which we currently render or a multi-line text area. Use it for the fields in the editor. Let's look
4:28:034 hours, 28 minutes, 3 secondsat the output. Node registry now has an optional multi-line property which is a boolean and a flag to the node field
4:28:124 hours, 28 minutes, 12 secondstype. So any field can opt into a text area. The right sidebar has replaced our existing field input component with a
4:28:204 hours, 28 minutes, 20 secondsnew field component which dynamically renders either a text area if field multi-line is set otherwise it renders
4:28:284 hours, 28 minutes, 28 secondsthe input. So now let's look at the actual code changes. So in your node registry in the node field type all you
4:28:364 hours, 28 minutes, 36 secondsshould have is a brand new property multi-line which is a boolean and option. In your right sidebar component you should now have a new import for the
4:28:454 hours, 28 minutes, 45 secondstext area. As per the field input component it should be replaced with a new field component which has the exact
4:28:514 hours, 28 minutes, 51 secondssame props as before but it dynamically renders either the text area or the input depending if field is multi-line or not.
4:29:024 hours, 29 minutes, 2 secondsand replace the actual field input to the new field component. If you're wondering which changes I have down
4:29:104 hours, 29 minutes, 10 secondshere, it's just the auto switch to the editor tab we've developed previously.
4:29:144 hours, 29 minutes, 14 secondsSo go ahead and add another field to the open URL node and this time give it a property multi-line set to true. And if
4:29:224 hours, 29 minutes, 22 secondsyou go ahead and open it in the editor, you should now have rendered a text area instead of an input. Let's go back to
4:29:294 hours, 29 minutes, 29 secondsthe node registry and let's add one more property to the node field type right under our new property multi-line. Let's
4:29:374 hours, 29 minutes, 37 secondsregister another optional property called required. And once we've added it here, let's also add it in our URL
4:29:464 hours, 29 minutes, 46 secondsproperty. We can now also get rid of the temporary uh multi-line field we've added. Then in the right sidebar, find
4:29:544 hours, 29 minutes, 54 secondsyour inspector component and scroll down until you find the label. And beneath the label, go ahead and check if a field
4:30:034 hours, 30 minutes, 3 secondsis required. And if it is, render an asterisk with a class name text destructive. And now every required
4:30:114 hours, 30 minutes, 11 secondsfield will have an appropriate sign. So we know we need to populate this if we want to execute this workflow and use
4:30:194 hours, 30 minutes, 19 secondsthis node. This is a pretty good place for a checkpoint. So go ahead and stage your files and commit. Now let's enable
4:30:264 hours, 30 minutes, 26 secondsthe only item we have in our menu which is to delete the workflow. So let's construct the flow to enable this. First
4:30:354 hours, 30 minutes, 35 secondsmake the delete workflow item in the right sidebar delete the whole workflow and then send me back to the homepage.
4:30:444 hours, 30 minutes, 44 secondsSo that's the overall goal that we want to achieve. Now let's get a bit more technical. It needs a server action to
4:30:514 hours, 30 minutes, 51 secondsactually remove it from the database. It needs to scope it to the current organization.
4:30:564 hours, 30 minutes, 56 secondsThe same action should also clean up the workflows respective live blocks room so we don't have any orphaned rooms which uses the workflow ID as its room ID.
4:31:094 hours, 31 minutes, 9 secondsExecute it from the menu item and disable that menu item while the delete is in flight or in progress. The sidebar doesn't know which workflow it's in yet.
4:31:224 hours, 31 minutes, 22 secondsSo, we need to pass the workflow ID down to it as a prop from the workflow shell.
4:31:294 hours, 31 minutes, 29 secondsSo, the action knows what to remove. So, what does that mean? Well, take a look at the workflow shell component. We
4:31:364 hours, 31 minutes, 36 secondscurrently have a workflow ID the structured, but we don't use it. So, we need to pass it to the right sidebar. So
4:31:454 hours, 31 minutes, 45 secondsthe right sidebar is aware of which workflow it's in.
4:31:504 hours, 31 minutes, 50 secondsAnd then let's go ahead and simply give it some pointers about where to create server actions and where to create database access. And let's end it with a
4:32:004 hours, 32 minutesskill livelocks best practices for room removal API. So it doesn't invent uh any
4:32:084 hours, 32 minutes, 8 secondsuh new methods but uses the official instructions. Looks like a very uh well constructed prompt. So let's execute it.
4:32:164 hours, 32 minutes, 16 secondsLet's look through the generated files one by one. First I'm going to start with the data.ts
4:32:224 hours, 32 minutes, 22 secondsinside of my features workflows. In here the agent has added a new function delete workflow which follows the same
4:32:304 hours, 32 minutes, 30 secondsconvention as my create workflow, my get workflow and my list workflows. Then let's take a look at the second file actions.ts.
4:32:404 hours, 32 minutes, 40 secondsOnce again inside of features workflows.
4:32:434 hours, 32 minutes, 43 secondsSo in here it imports the live blocks client and the newly generated uh delete workflow from the data. It generates a
4:32:524 hours, 32 minutes, 52 secondsnew server action called delete workflow action which accepts the ID which it needs to delete. It scopes the
4:33:004 hours, 33 minutesorganization ID and throws an error if not available and then it calls the data delete workflow function which we just
4:33:084 hours, 33 minutes, 8 secondsreviewed. In case the workflow is not found, it throws the error to let the user know that whichever workflow they
4:33:154 hours, 33 minutes, 15 secondsare trying to delete doesn't exist or isn't available to the organization that they are currently in. And in here, it
4:33:244 hours, 33 minutes, 24 secondsalso performs live blocks delete room and passes the ID because the ID of the workflow is the same as the one of the
4:33:324 hours, 33 minutes, 32 secondsroom. Then it calls revalidate path and redirect which are both from next cache and next navigation.
4:33:414 hours, 33 minutes, 41 secondsSo we revalidate the workflows endpoint and the layout. Perfect. So this is great. Let's take a look at the workflow
4:33:514 hours, 33 minutes, 51 secondsshell. So as expected, we have simply passed along this unused workflow ID to the right sidebar component. In the
4:33:594 hours, 33 minutes, 59 secondsright sidebar component, we have imported delete workflow action. Then let's scroll all the way down to find
4:34:074 hours, 34 minutes, 7 secondsthe right sidebar, which now accepts a workflow ID and passes the workflow ID to the actions menu. And the actions
4:34:154 hours, 34 minutes, 15 secondsmenu now accepts the workflow ID and has a new state. Is deleting set is deleting. It disables the drop-own menu
4:34:244 hours, 34 minutes, 24 secondsitem. If is deleting prop is set to true. It prevents the default on select, sets is deleting to true, and then calls
4:34:324 hours, 34 minutes, 32 secondsdelete workflow action. Now, sometimes my agent uh performs the pending state using the use transition hook. This time
4:34:414 hours, 34 minutes, 41 secondsit chose not to do that. So, if yours did it, it's perfectly fine. As long as the on select actually executes the delete workflow action, the code is
4:34:504 hours, 34 minutes, 50 secondsperfectly fine. So, now let's go ahead and actually test this out. So, I currently have nine workflows and seven
4:34:594 hours, 34 minutes, 59 secondsrooms in Live Blocks. So, I'm going to go ahead and refresh just in case. And then I'm going to go ahead and go inside
4:35:064 hours, 35 minutes, 6 secondsof my dropdown and I'm going to click delete workflow. And let's see what the error is about. Failed to delete
4:35:144 hours, 35 minutes, 14 secondsworkflow. So, it appears that it actually deleted the workflow from here.
4:35:194 hours, 35 minutes, 19 secondsBut I'm assuming something went wrong with deleting the live blocks. Or maybe not. But we can verify by looking inside
4:35:294 hours, 35 minutes, 29 secondsof here. So, what actually happened? So, I deleted a couple of workflows and all of them have been successfully deleted
4:35:364 hours, 35 minutes, 36 secondsboth from the database and from the live blocks dashboard. And I even tried going inside of my actions and commenting out
4:35:464 hours, 35 minutes, 46 secondslive delete room to see if maybe that's the culprit. But regardless of what I did, the server action always seems to
4:35:554 hours, 35 minutes, 55 secondsthrow this toast error. So I'm beginning to think that perhaps this catch is incorrectly used here. So I'm going to
4:36:024 hours, 36 minutes, 2 secondshighlight the usage of this server action and I'm going to write the following. This dot catch is always
4:36:094 hours, 36 minutes, 9 secondsthrowing but both the database deletion and the live blocks deletion work. Can you verify your implementation using
4:36:164 hours, 36 minutes, 16 secondsNex.js node modules documentation for why this could be. So Nex.js if you don't remember uh injects the
4:36:244 hours, 36 minutes, 24 secondsdocumentation in its node modules so agents can read it. So let's see what it has to say about this. After some back and forth with the AI, I've come to the
4:36:334 hours, 36 minutes, 33 secondsconclusion that what actually threw the error was the redirect. So this specific
4:36:404 hours, 36 minutes, 40 secondsredirect works by throwing an error. I actually remembered this uh by reading some documentation or some uh problem
4:36:494 hours, 36 minutes, 49 secondssomeone wrote about. So I questioned it about that and the first thing it did
4:36:564 hours, 36 minutes, 56 secondswhich I purposely skipped in the recording is it recommended I use some weird unstable
4:37:034 hours, 37 minutes, 3 secondsuh feature. So then I told it the following. So if you're in the same situation as me simply tell it we
4:37:114 hours, 37 minutes, 11 secondsalready have create workflow action. So that's what I told it. We are using the same redirect which you deemed problematic in the create workflow
4:37:194 hours, 37 minutes, 19 secondsaction. look at how you handle its execution and apply the same and that was the solution. So in the end the code
4:37:274 hours, 37 minutes, 27 secondsshould look like this in the drop-own menu item on select simply go ahead and import use transition and get is pending
4:37:374 hours, 37 minutes, 37 secondsand start transition from here and then wrap your uh await delete workflow action inside of start transition. If
4:37:454 hours, 37 minutes, 45 secondsyou want to see the exact git diff let me show you. So import use transition from react import delete workflow action
4:37:524 hours, 37 minutes, 52 secondsfrom features workflows actions and then inside of the actions menu execute the hook use transition extract is pending
4:38:014 hours, 38 minutes, 1 secondand start transition set the disabled to be controlled by is pending and then invoke the server action inside of the
4:38:104 hours, 38 minutes, 10 secondsstart transition function. This way you won't be greeted with any errors. That brings us to the end of this chapter.
4:38:174 hours, 38 minutes, 17 secondsSo, let's go ahead and stage commit and push our changes.
Chapter 16: Workflow Execution
4:38:284 hours, 38 minutes, 28 secondsNow that we have a functional toolbar, let's go ahead and enable the run button which is going to trigger the actual workflow execution. First, let's go back
4:38:374 hours, 38 minutes, 37 secondsinto our schema. In here, we can find the workflows table. What I want to do now is assign the graph property a
4:38:464 hours, 38 minutes, 46 secondsproper type. When we first developed the schema, we didn't yet have the node registry file. But now that we do, we
4:38:544 hours, 38 minutes, 54 secondsalso have the step node type which we can now reuse inside of this schema and make it more type- safe. So first let's import the type edge from XYFlow React.
4:39:054 hours, 39 minutes, 5 secondsThen let's import the type step node type from our node registry. Then let's
4:39:114 hours, 39 minutes, 11 secondsexport a new type called workflow graph which is an object with nodes and edges.
4:39:184 hours, 39 minutes, 18 secondsAnd make sure that for the nodes type you use the step node type in an array.
4:39:234 hours, 39 minutes, 23 secondsAnd for the edges we can just use the default ones from XYlow React. And now besides exporting this type we can also
4:39:324 hours, 39 minutes, 32 secondsassign it to the graph field. Now let's add a new dependency to our project called toposort. Toposort is going to
4:39:394 hours, 39 minutes, 39 secondshelp us validate the graphs in our workflow as well as correctly order the connections, nodes, and edges. Also,
4:39:474 hours, 39 minutes, 47 secondsmake sure to add a dev dependency called typeso sort. After the installation, go inside of your package. JSON to verify
4:39:544 hours, 39 minutes, 54 secondsthat you now have toposort inside of your dependency and types inside of your dev dependencies. Now let's create a new
4:40:024 hours, 40 minutes, 2 secondsutil inside of features workflows lib folder and let's call it validate graph.ds.
4:40:084 hours, 40 minutes, 8 secondsFirst let's add our new dependency toposort. Then let's import our new type workflow graph from lib database schema.
4:40:184 hours, 40 minutes, 18 secondsThen let's create a new function validate graph which destructures the nodes and the edges from the prop workflow graph and it returns an array
4:40:274 hours, 40 minutes, 27 secondsof strings which are essentially all the problems that this function found. So let's first define that constant
4:40:354 hours, 40 minutes, 35 secondsproblems which is an array of strings and by default it's an empty array. Make sure that you return it so you no longer have the type error in the function.
4:40:444 hours, 40 minutes, 44 secondsThen let's load all the trigger nodes we have from our workflow graph.
4:40:504 hours, 40 minutes, 50 secondsIf there are more than one trigger nodes, let's push a problem. A workflow needs exactly one start trigger. And
4:40:584 hours, 40 minutes, 58 secondsthen let's write how many of them we found and why this graph isn't validated.
4:41:054 hours, 41 minutes, 5 secondsThen let's check how many edges we have.
4:41:094 hours, 41 minutes, 9 secondsIf we have no edges, let's make sure to throw another problem. connect your nodes before running. And in the else
4:41:174 hours, 41 minutes, 17 secondsblock, let's open a try and catch where we call topo sort and we map over its
4:41:244 hours, 41 minutes, 24 secondsedges. And if this topo sort fails, meaning if it goes into the catch block, let's push a new problem workflow has a cycle. Remove the loop before running.
4:41:364 hours, 41 minutes, 36 secondsSo by initializing topos sort and adding the this specific uh iteration of edges with the source and the target inside
4:41:444 hours, 41 minutes, 44 secondstoposort can detect if there is a cyclic workflow meaning that one node ends up being connected to the previous node
4:41:514 hours, 41 minutes, 51 secondswhich breaks our workflow. So this is our validate graph function which we can use to check whether our workflow has
4:41:584 hours, 41 minutes, 58 secondsany structural problems or not. Now let's go inside of our data.ts TS file where we have functions like list
4:42:074 hours, 42 minutes, 7 secondsworkflows, get workflows, create workflow, etc. And let's develop a new function which we're going to use to
4:42:144 hours, 42 minutes, 14 secondssave the workflows graph information. So first of all, let's import workflow graph type from lib database schema.
4:42:244 hours, 42 minutes, 24 secondsThen let's import validate graph function from our lib which we've just created. Then let's open a new function
4:42:324 hours, 42 minutes, 32 secondssave workflow graph which accepts organization ID ID and graph. Since we
4:42:394 hours, 42 minutes, 39 secondshave three parameters here, I like to have a practice of uh putting them inside of an object instead of just in a
4:42:464 hours, 42 minutes, 46 secondsspecific order. Then let's use our validate graph util and pass along the graph prop which is equivalent to the
4:42:554 hours, 42 minutes, 55 secondsworkflow graph type. and let's extract problems from that lib. If problems.length is larger than zero,
4:43:034 hours, 43 minutes, 3 secondslet's simply throw a new error joining all of those problems together. Since they are strings, we can display them in
4:43:094 hours, 43 minutes, 9 secondsthat manner. Other than that, let's do await database, update the workflows table, set the graph property, and
4:43:184 hours, 43 minutes, 18 secondsupdated add property to whatever is the current new date uh result. And then let's write a simple wear query. both
4:43:274 hours, 43 minutes, 27 secondsthe workflows ID and the workflows organization ID match and that is our function save workflow graph. Now let's
4:43:354 hours, 43 minutes, 35 secondsuse this new data function inside of our actions. So first things first import
4:43:424 hours, 43 minutes, 42 secondssave workflow graph from the data. Then import the workflow graph type from lib
4:43:494 hours, 43 minutes, 49 secondsdatabase schema and then let's go down until we find our run workflow action.
4:43:554 hours, 43 minutes, 55 secondsAnd first let's extend its props. So let's make it accept an object ID and graph. ID is a type of string and graph
4:44:044 hours, 44 minutes, 4 secondsis a type of workflow graph. Make sure that you validate the organization ID if you haven't so far. And then after that
4:44:124 hours, 44 minutes, 12 secondsvalidation simply await save workflow graph and pass along the organization ID, the ID of the workflow and the graph
4:44:214 hours, 44 minutes, 21 secondsfield. So now we have an action which starts a longunning task and validates our workflow. But we're also going to
4:44:284 hours, 44 minutes, 28 secondsneed a function which will be used to stop a longunning task in case the user changed their mind. So let's import runs
4:44:364 hours, 44 minutes, 36 secondsfrom trigger.dev SDK. And then at the bottom after run workflow action, let's
4:44:434 hours, 44 minutes, 43 secondsexport cancel workflow action. The only thing it needs to accept is the run ID.
4:44:484 hours, 44 minutes, 48 secondsvalidate the organization ID and then go ahead and cancel the run. This is a pretty good spot for a checkpoint. So go ahead and stage your files and then do a
4:44:574 hours, 44 minutes, 57 secondscommit. Now let's enable the run button inside of our right sidebar component so that it runs the server action which we just modified the run workflow action.
4:45:084 hours, 45 minutes, 8 secondsSo inside of the right sidebar first let's import run workflow action from
4:45:144 hours, 45 minutes, 14 secondsfeatures workflows actions. Then let's import our validate graph function. Then scroll down until you find the run
4:45:234 hours, 45 minutes, 23 secondsbutton function and first make it accept a new prop workflow ID. Then using the
4:45:304 hours, 45 minutes, 30 secondsuse react flow hook, extract the nodes and the edges using get nodes and get edges and make sure you type it with
4:45:384 hours, 45 minutes, 38 secondsstep node type. Then add the use transition hook from React and extract is pending and start transition.
4:45:464 hours, 45 minutes, 46 secondsThen attach the is pending to the disabled prop of the button. Then construct the graph using nodes which
4:45:544 hours, 45 minutes, 54 secondsinvokes the get nodes and edges which invokes get edges. Then let's find if there are any problems using our
4:46:024 hours, 46 minutes, 2 secondsvalidate graph function. If there are problems, let's go ahead and do toast.
4:46:084 hours, 46 minutes, 8 secondsAnd let's always render the first in the array.
4:46:124 hours, 46 minutes, 12 secondsThen let's call start transition and let's execute an asynchronous function which then awaits run workflow action
4:46:204 hours, 46 minutes, 20 secondsand passes along the ID which is the workflow ID from the prop which we've added and the graph so we can validate
4:46:274 hours, 46 minutes, 27 secondsit on the back end as well. And then at the bottom in the right sidebar function where we actually render the run button
4:46:364 hours, 46 minutes, 36 secondsmake sure you pass along the workflow ID. So ensure that you actually have use react flow imported and use transition.
4:46:464 hours, 46 minutes, 46 secondsYou should have both of those because we actually use use transitions in the actions menu for our delete workflow
4:46:534 hours, 46 minutes, 53 secondsaction. But just in case your agent didn't do that, go ahead and manually add this. And you should absolutely have use react flow because that's what we
4:47:014 hours, 47 minutes, 1 seconduse to update the node data and to add new nodes. And now to construct the graph using the get nodes and get edges.
4:47:104 hours, 47 minutes, 10 secondsNow make sure that your local trigger server is running and go ahead and press the run button. As you can see, we have
4:47:194 hours, 47 minutes, 19 secondsan error. Connect your nodes before running. So I have this error because I didn't connect my nodes. Meaning that our validate graph function is working.
4:47:314 hours, 47 minutes, 31 secondsSo, it noticed that I have zero edges, which meant that I didn't connect any of my nodes. And now that my node is
4:47:404 hours, 47 minutes, 40 secondsconnected, I can click on run. And as you can see, I have no errors. And inside of my uh development server here,
4:47:484 hours, 47 minutes, 48 secondsI can see that hello world was triggered and then hello world was successfully initialized. So if you play a bit more
4:47:574 hours, 47 minutes, 57 secondsand for example remove all nodes and then click run again, you will find another error. A workflow needs exactly
4:48:044 hours, 48 minutes, 4 secondsone start trigger found zero. So you need to have at least one node added. I
4:48:114 hours, 48 minutes, 11 secondsmean one start node and your nodes need to be connected otherwise you will get hit with an error. Perfect. So we have
4:48:204 hours, 48 minutes, 20 secondsnow completely wired up our data fetcher, our uh server action and our
4:48:274 hours, 48 minutes, 27 secondscomponent. But what's actually interesting is does the actual graph now update in the database? Because so far
4:48:364 hours, 48 minutes, 36 secondswe never really updated this graph field. We only defined it as this JSON field. All the data persistence was done
4:48:454 hours, 48 minutes, 45 secondsusing livelocks room because Liveblocks is a database in itself. So let's quickly check Neon to see what's up in
4:48:534 hours, 48 minutes, 53 secondsour database. Go inside of your Neon project and find the tables. And in here you will find the workflows. As you can
4:49:014 hours, 49 minutes, 1 secondsee so far I didn't have any graph field populated except this one which is the
4:49:074 hours, 49 minutes, 7 secondsfirst graph in which I hit the run button. So now let me go ahead and pick any random workflow like this one joint
4:49:174 hours, 49 minutes, 17 secondsbaboon which currently has nothing in the graph. And I'm going to go ahead and maybe add a couple of nodes here. And
4:49:244 hours, 49 minutes, 24 secondsI'm going to connect them. And I might even add some data here. And then I'm going to click run. Since there are no
4:49:324 hours, 49 minutes, 32 secondserrors, I know that this had to have been saved successfully. And there we go. Once I refresh, you can see that now joint baboon uh has this data in here.
4:49:434 hours, 49 minutes, 43 secondsBeautiful. And you can even see the exact nodes which are inside. And if I'm correct, we should also see the values
4:49:494 hours, 49 minutes, 49 secondsstored. So this data persistence inside of our graph field is used for a different purpose in comparison to live
4:49:574 hours, 49 minutes, 57 secondsblocks. So livelocks data persistence uh came as a great help to us because it's what renders the UI. So every single
4:50:054 hours, 50 minutes, 5 secondstime we move our nodes around, Liveblocks updates its database. We don't have to synchronize that. They do
4:50:124 hours, 50 minutes, 12 secondsit for us. But whenever we want to execute the workflow, this is where it's important for us to validate whether
4:50:194 hours, 50 minutes, 19 secondsthis graph is correctly uh connected, whether it has any missing edges and whether we can actually execute it. But
4:50:284 hours, 50 minutes, 28 secondsright now the task which we are executing when we click on the run button is this hello world example. So
4:50:354 hours, 50 minutes, 35 secondslet's now start working on a real workflow execution task. I want to develop this task inside of features
4:50:424 hours, 50 minutes, 42 secondsworkflows. And in here I've created a new folder called tasks. And in here let's create run workflow.ts file. Let's start with the imports.
4:50:554 hours, 50 minutes, 55 secondsLet's add toposort and let's add logger and task from trigger.dev SDK. Then
4:51:024 hours, 51 minutes, 2 secondslet's import our get workflow from workflows data. Then let's define the run workflow task. Let's give it an ID
4:51:104 hours, 51 minutes, 10 secondsof run-ash workflow and inside of the run let's simply define an empty asynchronous function. Let's go ahead
4:51:184 hours, 51 minutes, 18 secondsand make this asynchronous function accept a workflow ID and an organization ID inside of an object. Then using that
4:51:264 hours, 51 minutes, 26 secondsorganization ID and workflow ID, we can properly call our get workflow data fetcher, which gives us access to the workflow the user is trying to run.
4:51:364 hours, 51 minutes, 36 secondsNext, let's check if the workflow isn't available or if the workflow doesn't have a graph. And if they don't, let's
4:51:434 hours, 51 minutes, 43 secondsthrow an early error. the workflow has no graph. Then let's go ahead and dstructure the nodes and the edges from
4:51:514 hours, 51 minutes, 51 secondsthe other workflows which actually have a graph which have passed this validation. Then let's add a little help
4:51:584 hours, 51 minutes, 58 secondshelper called by ID. So we create a new map and we put the nodes inside in this exact format. Then let's go ahead and
4:52:074 hours, 52 minutes, 7 secondscreate a new set and we use edges.flat map. What we do here is we ensure that
4:52:154 hours, 52 minutes, 15 secondsthe nodes we're going to run are only those which are connected. So if we have any orphaned nodes which aren't
4:52:224 hours, 52 minutes, 22 secondsconnected to anything, we're just going to drop them and we are not going to run them through the topo sort and we're not going to execute them. Then [snorts]
4:52:304 hours, 52 minutes, 30 secondslet's go ahead and order our nodes using toposort array. inside of the array. In
4:52:384 hours, 52 minutes, 38 secondsthe first argument, perform a map over nodes and in the second argument, perform a map over edges. Make sure you
4:52:454 hours, 52 minutes, 45 secondsproduce an array which will end up being a matrix of sources and targets and then filter by ID of each of those and make sure they appear in the connected set.
4:52:574 hours, 52 minutes, 57 secondsSo that's how we ensure that we only uh execute those nodes for which we found a
4:53:044 hours, 53 minutes, 4 secondsconnection to another node. So there is a complete cycle and let's add a little log here running
4:53:114 hours, 53 minutes, 11 secondsworkflow workflow name and let's prepare how many steps this is going to have. By steps we mean how many nodes this is going to have. Then let's do a for loop.
4:53:224 hours, 53 minutes, 22 secondsSo for every order that we find, let's go ahead and find the node using our by
4:53:294 hours, 53 minutes, 29 secondsID helper and let's simply log running step and then let's print out exactly
4:53:364 hours, 53 minutes, 36 secondswhich step that is and let's add a to-do actually execute the node instead of just logging it and report its progress
4:53:444 hours, 53 minutes, 44 secondsso the UI can watch the run live. So that is the next step. So just make sure that you are iterating over the order right because that's what we are doing.
4:53:544 hours, 53 minutes, 54 secondsThe order is essentially going to return an array of strings and that's what we have to follow. It's basically an array
4:54:014 hours, 54 minutes, 1 secondof ids which have to be executed in that specific order and in the end simply return the steps using order.length.
4:54:094 hours, 54 minutes, 9 secondsNow that we have our new run workflow task, let's go back inside of our server actions and let's replace the usage of
4:54:164 hours, 54 minutes, 16 secondshello world task and replace it with our run workflow task. So first let's add import type run workflow task from
4:54:264 hours, 54 minutes, 26 secondsfeatures workflows task run workflow. So yes, the run workflow task as defined
4:54:334 hours, 54 minutes, 33 secondsand exported here is automatically a type. So there was nothing else we had to export. This can serve both as the
4:54:414 hours, 54 minutes, 41 secondsAPI and as the type. So now that we imported that, let's go down until we
4:54:484 hours, 54 minutes, 48 secondsfind run workflow action. And in here we trigger the hello world task. So let's now replace this with the following.
4:55:004 hours, 55 minutestasks dot trigger type of off run workflow task which makes it required for us to name the workflow like this.
4:55:094 hours, 55 minutes, 9 secondsIf you try to enter something else, it's going to throw an error because run workflow task is clearly defined to have
4:55:164 hours, 55 minutes, 16 secondsthis specific ID. So make sure that your ID isn't misspelled and then pass along the workflow ID and the organization ID.
4:55:274 hours, 55 minutes, 27 secondsAnd then as a third argument, which is something we didn't have for the hello world example, go ahead and add tags.
4:55:334 hours, 55 minutes, 33 secondsAnd tags is an array which has a constructed string workflow colon ID. If you try and click on the run button and
4:55:424 hours, 55 minutes, 42 secondsthen go inside of your uh trigger development server, you will notice that runs are not firing. So even though we
4:55:514 hours, 55 minutes, 51 secondscorrectly replaced which run we are invoking, it's not properly executing.
4:55:574 hours, 55 minutes, 57 secondsThe reason is because we didn't register the features folder to store any
4:56:044 hours, 56 minutes, 4 secondstrigger.dev tasks. So we have to go back inside of the trigger.config.ts
4:56:124 hours, 56 minutes, 12 secondsand replace trigger with features. And then I would recommend restarting your server. And let's try it one more time.
4:56:194 hours, 56 minutes, 19 secondsSo, make sure you have your uh trigger server running and then go ahead and click run. And just like that, you will
4:56:274 hours, 56 minutes, 27 secondsnow see your runs. Besides verifying the runs inside of your CLI, I would recommend also visiting the trigger.dev
4:56:354 hours, 56 minutes, 35 secondsdashboard. So, you can actually go inside of your latest runs and verify what's logging inside. Create the following scenario in your canvas. a
4:56:444 hours, 56 minutes, 44 secondsstart node connected to open URL one which is connected to open URL 2. And if you take a look at our run workflow
4:56:524 hours, 56 minutes, 52 secondstask, what we do is we topologically order the nodes based on their edges based on the source and the target of
4:57:004 hours, 57 minutesthe edge. So we are aware which node is connected to which one. which means this
4:57:064 hours, 57 minutes, 6 secondsfor loop for this specific canvas should output start node followed by open URL node and then the last node that should
4:57:154 hours, 57 minutes, 15 secondsbe outputed is the open URL 2 node. So when I click run I'm going to go ahead
4:57:224 hours, 57 minutes, 22 secondsand refresh my trigger.dev and this one which just completed let's take a look at the logs here. The first
4:57:304 hours, 57 minutes, 30 secondsstep is start node. The second step is open URL one and the third step is open
4:57:364 hours, 57 minutes, 36 secondsURL 2. Now I'm going to try and purposely remove the edges and connect it the other way around just to verify
4:57:444 hours, 57 minutes, 44 secondsthat this isn't a fluke. And just as we suspected, the order is now start open URL 2 and then open URL one. Meaning
4:57:534 hours, 57 minutes, 53 secondsthat our algorithm for topological sort is correct. And because we added a tag into our tasks trigger inside of run
4:58:024 hours, 58 minutes, 2 secondsworkflow action. If you take a look at your latest runs and scroll to the right side, you will see that our newest runs
4:58:104 hours, 58 minutes, 10 secondshave a workflow with their respective ID. Now, right now this isn't really useful for us, but later when we add the
4:58:184 hours, 58 minutes, 18 secondsreal-time feature of displaying logs of a specific run, this will come in very handy. We can now also remove the
4:58:264 hours, 58 minutes, 26 secondstrigger folder and the example file from there because it's no longer used.
4:58:314 hours, 58 minutes, 31 secondsBefore we commit and end this chapter, let's ensure that we have the proper git changes. So we removed the example.ts
4:58:394 hours, 58 minutes, 39 secondsfrom the trigger folder as well as the entire trigger folder. We modified the trigger config so that directory of the tasks is now features and not trigger.
4:58:494 hours, 58 minutes, 49 secondsWe added a new run workflow task which topologically orders the connected nodes
4:58:574 hours, 58 minutes, 57 secondswhich it extracted from the workflow graph which we loaded using the organization ID and the workflow ID. And
4:59:054 hours, 59 minutes, 5 secondsinside of this topological order, we iterate over those nodes and log which step is currently running to verify uh
4:59:124 hours, 59 minutes, 12 secondsif that order is correct and matches what we see on the canvas. We then modified our actions.ts
4:59:194 hours, 59 minutes, 19 secondsby adding that new uh run workflow task and appending it to the run workflow
4:59:274 hours, 59 minutes, 27 secondsaction. And that actually reminds me uh we should also remove the unused type hello world task from here. There we go.
4:59:374 hours, 59 minutes, 37 secondsAnd in the right sidebar, we did this actually first I believe. Uh we wired in the run workflow action which is a
4:59:454 hours, 59 minutes, 45 secondsserver action and the validate graph and wired it into the run button so we can disable it while it's running and we can
4:59:524 hours, 59 minutes, 52 secondsthrow any uh errors if validate graph doesn't uh pass. Great. So now let's go
4:59:594 hours, 59 minutes, 59 secondsahead and get add and then get commit and get push. Amazing job and see you in the next chapter.
Chapter 17: Browserbase Setup
5:00:125 hours, 12 secondsNow it's time to give our workflows, our nodes, and in the end, our agents access to the whole web. And we're going to
5:00:205 hours, 20 secondsachieve this using browserbase. Not only is this going to give our agents access to browse the web, but also to interact
5:00:285 hours, 28 secondswith any website just like a human would. Using the link on the screen, you can get to the browserbased website, and the link simply lets them know that you
5:00:365 hours, 36 secondscame from this video. Once you're here, go ahead and create an account. Once you've created your account, you're going to get greeted with the following
5:00:445 hours, 44 secondsonboarding screen. Now, given that this screen can update in the future, what I would actually recommend is clicking
5:00:515 hours, 51 secondsskip to the dashboard. This way, we can manually learn our way around the dashboard and around the documentation.
5:00:595 hours, 59 secondsSo, first things first, how to find the API key. You can find the API key using their quick access button right here. If
5:01:075 hours, 1 minute, 7 secondsthat doesn't work, you can click on the settings and you can find it here as well. This is the place where you can also regenerate it if you want to. Once
5:01:155 hours, 1 minute, 15 secondsyou've obtained your API key, go ahead and add it to the environment file under the property name browserbase API key.
5:01:225 hours, 1 minute, 22 secondsThen let's go inside of the resources and find the documentation. In here you can find the quick start and then in the
5:01:305 hours, 1 minute, 30 secondssidebar select skills. And then what we can do is we can copy this prompt which
5:01:365 hours, 1 minute, 36 secondssimply fetches the skill.md file which they have prepared for us. We could have technically just copied the prompt that
5:01:435 hours, 1 minute, 43 secondswe saw on the onboarding screen but I feel like this is more reliable. So we actually learn how to navigate the browserbased dashboard and the
5:01:515 hours, 1 minute, 51 secondsbrowserbased documentation. So now let's go ahead and run this prompt. So the agent fetched the setup guide from skill
5:02:005 hours, 2 minutesMD. Then it verified whether we have the browserbased API key. Then once it confirmed that it already exists, it
5:02:085 hours, 2 minutes, 8 secondsinstalled the CLI called browse. Then I assumed it authenticated that browse by
5:02:165 hours, 2 minutes, 16 secondscopying the browserbased API key globally somewhere on our machine. Then it run browse skills install using that
5:02:265 hours, 2 minutes, 26 secondsCLI which globally added the browse skills and here is the verification for
5:02:335 hours, 2 minutes, 33 secondsbrowserbased API credentials. So there we go. Let me verify that the API connection works with the existing key
5:02:405 hours, 2 minutes, 40 secondsand that is setup complete. So here's the summary once again. Browse CLI was installed. Since I have a Mac OS or a
5:02:495 hours, 2 minutes, 49 secondsUnix system, this is my location. Agent skills are installed. And now the browse skill is available. So unfortunately for
5:02:585 hours, 2 minutes, 58 secondsus, it didn't do it uh locally. It did it globally, which is fine. It still works. It's just not committed with the
5:03:055 hours, 3 minutes, 5 secondsproject. The API credentials were already present. So we didn't have to do anything here. And it also run browse
5:03:125 hours, 3 minutes, 12 secondscloud projects list which returned our production project which is what we have uh right here the production project. So
5:03:215 hours, 3 minutes, 21 secondsit correctly managed to authenticate the browser CLI using our browserbased API key. So everything checks out. The API
5:03:285 hours, 3 minutes, 28 secondskey was already configured. So no new credentials were needed. So now it's offering me to do some quick tests here.
5:03:385 hours, 3 minutes, 38 secondsIt even provided me with like an exact uh automation task to do. But what I would first like you to verify is whether you actually have the browser
5:03:465 hours, 3 minutes, 46 secondsskill installed just in case we end up uh using it. So make sure to do reload the skills or simply restart your coding
5:03:535 hours, 3 minutes, 53 secondsagent and also uh do a reload window if you're using a graphical user interface and then at that point you should have
5:04:025 hours, 4 minutes, 2 secondsthe browse skill available. If for whatever reasons you don't have that skill available, go inside of integrations and scroll down until you
5:04:105 hours, 4 minutes, 10 secondsfind skills introduction and then in here you will find a manual way to add the skills that you need. Now it's a
5:04:195 hours, 4 minutes, 19 secondsgood idea to try out whether the browse CLI actually works for you. But if you got a successful message from the agent, chances are that everything is set up
5:04:285 hours, 4 minutes, 28 secondscorrectly. So I'm going to run browse opencodewithantonia.com with a local flag. If you get the output
5:04:365 hours, 4 minutes, 36 secondslike I did, which is that session is already running, you can stop it with this command. And then let's try opening
5:04:435 hours, 4 minutes, 43 secondscode with Antonio once again. And the result is the metadata of my domain. So my title is build something great code
5:04:515 hours, 4 minutes, 51 secondswith Antonio. Perfect. So we have verified that our browse CLI actually works. The browse CLI is used to
5:04:595 hours, 4 minutes, 59 secondsinteract with your organization and your project in browser base and also to allow agents to open headless Chrome
5:05:085 hours, 5 minutes, 8 secondsbrowsers and test out any domain you give it. But the browser base which we are actually going to be using inside of
5:05:165 hours, 5 minutes, 16 secondsthis project is the programmatic use of browser base. So we are not going to tell cloud code uh to open uh a browser
5:05:245 hours, 5 minutes, 24 secondsand then do something for us. We could do that. But what we are building is a software as a service which allows various users to build their own
5:05:325 hours, 5 minutes, 32 secondsworkflows and then use browserbas's SDK to programmatically do that for them. So our job is to actually install the
5:05:405 hours, 5 minutes, 40 secondsbrowserbase HQ SDK package. You can find the documentation for that by going inside of APIs and SDKs and then select
5:05:485 hours, 5 minutes, 48 secondsthe NodeJS SDK. Now it's time to add stage hand. Stage hand is browserbas's open-source product which allows you to
5:05:585 hours, 5 minutes, 58 secondsprompt using natural language and instruct agents to behave or do something on a website which is that wow
5:06:075 hours, 6 minutes, 7 secondseffect which we are looking to provide to our users. So besides the documentation on the left which you can
5:06:145 hours, 6 minutes, 14 secondsfind where you are instructed once again to get your API key and then to install uh browserbased HQ stage hand which we
5:06:225 hours, 6 minutes, 22 secondsabsolutely are going to do so you can uh make sure that is installing in the background. Meanwhile, go and find the
5:06:305 hours, 6 minutes, 30 secondsactual stage hand website and in here click on the AI rules and scrolling a
5:06:375 hours, 6 minutes, 37 secondsbit down you will find the editor rule files. So instead of providing a skill they actually provide us well with a
5:06:455 hours, 6 minutes, 45 secondsskill but we have to manually add it to our claude MD. So let's go ahead and close all of these. Make sure the new
5:06:545 hours, 6 minutes, 54 secondspackages are installed and then go either in your agents or claude it doesn't matter because it's a symbolic link and then paste all of that content
5:07:025 hours, 7 minutes, 2 secondsbelow. So now we are going to have all the knowledge required to use stage hand in this specific version uh for which
5:07:115 hours, 7 minutes, 11 secondsthis documentation was added. So this agents.md or claude.md snippet which we've added which will also be available in the source code if you can't find it.
5:07:215 hours, 7 minutes, 21 secondsSo you can just visit uh my repository and then find my agents ND and you can copy it is more important than that
5:07:285 hours, 7 minutes, 28 secondsbrowser skills which we installed uh a few moments ago. So this is the actual SDK which we're going to be focusing on the stage hand. So go ahead and stage
5:07:375 hours, 7 minutes, 37 secondsand commit these changes so we have a clean slate for further development. So right now if you go inside of tasks run
5:07:455 hours, 7 minutes, 45 secondsworkflow the only thing we do when a node is executed is we log that the node
5:07:525 hours, 7 minutes, 52 secondsis actually running. So what's actually going to happen here in the future is we would somehow uh get the executor by
5:08:025 hours, 8 minutes, 2 secondshaving some kind of registry similar to node registry but we're going to have something like node executors and we're
5:08:095 hours, 8 minutes, 9 secondsgoing to map it to our current node and then type right and then we would simply
5:08:165 hours, 8 minutes, 16 secondsdo execute and this node executors will in the future
5:08:225 hours, 8 minutes, 22 secondsbe something like this. So, open URL and then in here we will do open URL.
5:08:305 hours, 8 minutes, 30 secondsWell, this is a big function something like this. This is the general idea of how we're going to develop this. So,
5:08:375 hours, 8 minutes, 37 secondslet's start by actually developing that logic which we are going to create the node executors uh registry with. So, no
5:08:475 hours, 8 minutes, 47 secondsneed to do any changes in the run workflow. But let's go inside of our nodes folder where we have the node registry and let's create open URL.
5:08:575 hours, 8 minutes, 57 secondsDS. First, let's add type stage hand from browserbased HQ stage hand. Then let's export an asynchronous function
5:09:065 hours, 9 minutes, 6 secondsopen URL. Inside of its params, let's accept stage hand and URL. I'm going to
5:09:145 hours, 9 minutes, 14 secondsexplain why we are accepting stage hand instead of initializing it here later when we add the node executor inside of
5:09:235 hours, 9 minutes, 23 secondsthe actual function. First let's get the page using stage hand context pages and then let's use page go to and then the
5:09:325 hours, 9 minutes, 32 secondsdynamic URL variable which the user will enter on the canvas and let's go ahead and decorate it with some properties like wait until and time out in
5:09:415 hours, 9 minutes, 41 secondsmilliseconds and then let's simply return the URL and the page title. So how did I know this API? Well, because it's written in agents.md.
5:09:535 hours, 9 minutes, 53 secondsI could have technically just told the agent to do this, but it's such a small function that I feel like it's easier to do it by hand than to write a perfect
5:10:025 hours, 10 minutes, 2 secondsprompt that will deterministically give us this exact output. Uh so yes, this page needs to be accessed like this and
5:10:095 hours, 10 minutes, 9 secondsthen you can uh instruct page go to a URL. Perfect. So this is our first node executor. Before we can write the node
5:10:185 hours, 10 minutes, 18 secondsexecutors registry, let's first go inside of the actual node registry because in here we have all of the necessary types that node executor needs
5:10:285 hours, 10 minutes, 28 secondsto satisfy. So let's export action node type. And now that we export the action node type, we can create the node
5:10:375 hours, 10 minutes, 37 secondsexecutors registry. So first let's import the type stage hand from browserbase hq stage hand. Make sure
5:10:445 hours, 10 minutes, 44 secondsyou're importing the type. Then let's import action node type and node type from our node registry. Then let's import the new executor we just
5:10:535 hours, 10 minutes, 53 secondsdeveloped open URL. Let's export a type node context which is an object with two properties values which is an object and
5:11:035 hours, 11 minutes, 3 secondsget stage hand. Then let's export type node executor which is simply a generic type which we're going to uh use
5:11:115 hours, 11 minutes, 11 secondswhenever we need to satisfy the node executor output. Then let's actually export the node executors. Let's give it
5:11:195 hours, 11 minutes, 19 secondsthe correct type and let's open an empty object for now. Then inside let's add the open URL. The open URL is an
5:11:285 hours, 11 minutes, 28 secondsasynchronous method which accepts values get stage hand and returns the open URL
5:11:355 hours, 11 minutes, 35 secondsutil which we developed above. The open URL also passes the stage hand using await get stage hand and URL using
5:11:425 hours, 11 minutes, 42 secondsvalues URL. And let's wrap it up by adding satisfies record action node type
5:11:495 hours, 11 minutes, 49 secondsand node executor. There we go. This is our node executors. This is where we're going to build every single nodes
5:11:575 hours, 11 minutes, 57 secondsexecutor going forward. Or should I say this is the factory which our coding agent is going to use to populate and add new nodes later. So we don't have to
5:12:065 hours, 12 minutes, 6 secondsdo it by hand anymore. Now let's wire this up inside of our run workflow.ts.
5:12:135 hours, 12 minutes, 13 secondsSo first things first, let's import stage hand. This time the actual stage hand. So don't import type import stage
5:12:225 hours, 12 minutes, 22 secondshand from browserbased HQ stage hand and add the new node executors import. Now let's implement get stage hand lazy run
5:12:315 hours, 12 minutes, 31 secondsfunction and this [clears throat] will clear up why we are passing stage hand as a prop rather than initializing it in
5:12:385 hours, 12 minutes, 38 secondsevery exeutor. So let's go inside of our run workflow task. Let's find our order
5:12:445 hours, 12 minutes, 44 secondsconst and after this logger where we log which workflow we are running and before
5:12:515 hours, 12 minutes, 51 secondsthe for loop let's go ahead and define a variable stage hand and by default let's give it a type of stage hand. So yes we
5:13:005 hours, 13 minutescan use this both as a type and as the actual client or undefined.
5:13:065 hours, 13 minutes, 6 secondsThen let's open a function get stage hand which is an asynchronous arrow function. If there is an existing stage
5:13:135 hours, 13 minutes, 13 secondshand stored in our variable, simply return that exact uh instance which we've already initialized. Otherwise,
5:13:215 hours, 13 minutes, 21 secondslet's go ahead and create a new stage hand instance. And inside of its properties, first give it an environment of browserbase. Then give it an API key.
5:13:315 hours, 13 minutes, 31 secondsNow for the model, I'm going to select the cheapest one. And no, you don't need to add your own key for this model. uh browserbase will automatically infer
5:13:405 hours, 13 minutes, 40 secondsthis for you. But if you want to, you can provide your own API keys. If you run out of browserbased API tokens, you
5:13:485 hours, 13 minutes, 48 secondscan just switch to bring your own keys method. And we're going to add this property called disable penino. So
5:13:555 hours, 13 minutes, 55 secondsdisable penino is a logging backend that basically spawns a thread stream worker which essentially breaks when run inside
5:14:045 hours, 14 minutes, 4 secondsof a trigger longunning tasks. So because of that we explicitly uh disable that. Then let's do await stage hand in
5:14:125 hours, 14 minutes, 12 secondsit and let's return stage hand. It might be useful to add a comment like this to understand why we are developing the get
5:14:205 hours, 14 minutes, 20 secondsstage hand function and to not forget that browserbase uh has its own model getaway using the browserbased API key.
5:14:285 hours, 14 minutes, 28 secondsSo this entire run this trigger.dev Devrun owns one browserbased session and
5:14:355 hours, 14 minutes, 35 secondswe lazily open it on the first browser step and then we reuse it by every later subsequent step. Otherwise if we were to
5:14:445 hours, 14 minutes, 44 secondsdo what most of us felt was natural and that is to initialize stage hand in here
5:14:515 hours, 14 minutes, 51 secondswe couldn't keep that in the same session. So the recording which we want right that's the cool part when the user
5:14:595 hours, 14 minutes, 59 secondsfinishes a workflow uh we want to give them a recording of what the agent did the only way we can do that is we if we
5:15:065 hours, 15 minutes, 6 secondssomehow preser preserve a single stage hand instance so that's why we are lazily opening it and we are going to
5:15:145 hours, 15 minutes, 14 secondspass it as a prop so it's reused across every executor until it reaches the end where we eventually close that stage
5:15:215 hours, 15 minutes, 21 secondshand session. So if you want to you can add a comment like this which will explain that. Now let's go inside of our
5:15:285 hours, 15 minutes, 28 secondsfor loop and instead of just logging which step is running let's do what's actually written here actually execute
5:15:375 hours, 15 minutes, 37 secondsthe node instead of just logging it. So first let's extract the executor. We can do that exactly as we demonstrated in
5:15:455 hours, 15 minutes, 45 secondsthe beginning of this chapter using the node executors registry and then accessing it using node data type. And
5:15:525 hours, 15 minutes, 52 secondsthen once we have the executor, if we have the executor, let's await that executor and simply pass along values
5:15:595 hours, 15 minutes, 59 secondsusing node data and then its values. And don't forget to actually close the stage
5:16:065 hours, 16 minutes, 6 secondshand instance once all of the nodes have been executed. So now make sure that you have your app running. Make sure you
5:16:135 hours, 16 minutes, 13 secondshave the trigger dev server running. And then go ahead and populate one open URL node with a valid URL. and go ahead and
5:16:225 hours, 16 minutes, 22 secondsclick run. Inside of your browserbased dashboard, you should now see a new session. And this session, if you
5:16:305 hours, 16 minutes, 30 secondsclicked on it early, will actually be a live preview of this Chrome browser in the cloud, which actually opens the URL.
5:16:405 hours, 16 minutes, 40 secondsBut if you missed it, don't worry because you get a replay of what happened. Congratulations on developing your first executor. This is now a
5:16:495 hours, 16 minutes, 49 secondsprimitive which we can leverage in agentic coding and build multiple similar nodes on top of this by pointing
5:16:565 hours, 16 minutes, 56 secondsit to a proper result which we now have working. So let's go ahead and stage commit and push our changes. Don't
5:17:055 hours, 17 minutes, 5 secondsforget that we've added a new variable to our environment file. So inside of your railway service, go inside of the raw editor and paste that environment
5:17:145 hours, 17 minutes, 14 secondsvariable. update the variables and redeploy.
Chapter 18: Data Passthrough
5:17:245 hours, 17 minutes, 24 secondsSo now we have successfully developed our first executor open URL. But before we go on to creating the rest of the
5:17:325 hours, 17 minutes, 32 secondsnodes and their respective executors, I think it's first time to completely finalize everything that the single node
5:17:415 hours, 17 minutes, 41 secondscan do. And right now our open URL node can almost do everything we wanted to do. But one thing we didn't implement is
5:17:515 hours, 17 minutes, 51 secondsdata pass through. So when I connect open URL to open URL 2 to open URL 3 and
5:17:595 hours, 17 minutes, 59 secondswhen I click on open URL 3, what I would expect is to see all of the previous connections it has. So I can interpolate
5:18:085 hours, 18 minutes, 8 secondsthe output data from the previous node and inject it into its values. This is a
5:18:155 hours, 18 minutes, 15 secondscrucial part of any workflow application. Data pass through. You might have noticed that in the previous
5:18:225 hours, 18 minutes, 22 secondsfew chapters we focused more on manual coding than on agentic coding. The reason behind that is because I wanted
5:18:305 hours, 18 minutes, 30 secondsus to establish a very deterministic state of our codebase where both you and I have the exact same code. And now that
5:18:385 hours, 18 minutes, 38 secondswe have a fully functional executor and we have fully functional write toolbar, we can now build on top of all of those
5:18:475 hours, 18 minutes, 47 secondsstable and deterministic components we've developed more reliably using agentic coding. Since some of the
5:18:555 hours, 18 minutes, 55 secondsprompts in this chapter are going to be a bit longer, I don't want you to waste time pausing the video and retyping what
5:19:015 hours, 19 minutes, 1 secondI type. So, I've prepared chapter 17, data pass through inside of the specifications folder, which you can
5:19:095 hours, 19 minutes, 9 secondslook at and then copy and paste inside of your coding agent. So, we have the exact same prompt. Let's start with
5:19:165 hours, 19 minutes, 16 secondsdeveloping an interpolation helper whose purpose is going to be to transform a value like this into an actual value
5:19:265 hours, 19 minutes, 26 secondsextracted from the output of the node to which this node is connected to and to
5:19:335 hours, 19 minutes, 33 secondsany previous node that data was passing through in this workflow. So let's review the first prompt which will be used to generate the interpolation
5:19:425 hours, 19 minutes, 42 secondshelper. I want to let a workflow field pull in another node's output by writing a placeholder like this template or this
5:19:505 hours, 19 minutes, 50 secondstemplate. To make that work, I need a small pure helper that takes one fields text plus a collection of every nodes
5:20:005 hours, 20 minutesoutput from this run and make sure that all of those outputs are keyed by node
5:20:075 hours, 20 minutes, 7 secondsID and returns the text with each placeholder swapped for the value that it actually points at from all of those
5:20:155 hours, 20 minutes, 15 secondsprevious node outputs. If a placeholder resolves to nothing, let's simply replace it with an empty string. If it
5:20:245 hours, 20 minutes, 24 secondsresolves to an object, let's drop in the JSON. It has to resolve nested paths. So lean on whatever small get by path
5:20:335 hours, 20 minutes, 33 secondsutility is cleanest. Put in put it in the workflow features helpers and call it interpolate. So hopefully it's going
5:20:415 hours, 20 minutes, 41 secondsto develop it inside of features lib right here. Let's go ahead and run this prompt. You should now have a new file
5:20:485 hours, 20 minutes, 48 secondscalled interpolate located inside of features workflows lib and its purpose is to transform placeholders like this
5:20:575 hours, 20 minutes, 57 secondstemplate into actual field for values pulled from this run's node outputs
5:21:035 hours, 21 minutes, 3 secondswhich are keyed by node ID. Perfect. So now we have this interpolate function which accepts text and all of the
5:21:125 hours, 21 minutes, 12 secondsprevious outputs in this run and then it can replace the placeholder which we defined using a regax. So that's how it
5:21:205 hours, 21 minutes, 20 secondsfinds uh the double brackets and it injects whichever value uh is referenced
5:21:285 hours, 21 minutes, 28 secondsfrom the output object. Perfect. So I'm assuming your function looks somewhat similar. Now let's go ahead onto the
5:21:365 hours, 21 minutes, 36 secondsnext prompt. The second prompt is pass outputs through the run inside of the run workflow task. Let each node use the
5:21:445 hours, 21 minutes, 44 secondsoutput of the nodes before it. Right now we run nodes in order and throw their results away. So instead keep each node's result as we go keyed by its ID.
5:21:575 hours, 21 minutes, 57 secondsThen right before running a node, replace the placeholder in its values with the matching upstream data using the interpolate helper we just made.
5:22:085 hours, 22 minutes, 8 secondsNodes already run in dependency order.
5:22:115 hours, 22 minutes, 11 secondsSo anything a node references has produced its output by the time we get there. Perfect. So a natural
5:22:195 hours, 22 minutes, 19 secondscontinuation of this interpolate helper which we just developed. So this interpolate helper by itself is just a pure function that could be used in any
5:22:285 hours, 22 minutes, 28 secondsother project. So what we have to modify now is the actual run workflow task.
5:22:335 hours, 22 minutes, 33 secondsWhat we do now is we pass the raw values from here. So we should somehow
5:22:395 hours, 22 minutes, 39 secondstransform these values by capturing all of the output that happened in the previous nodes and then run it through
5:22:475 hours, 22 minutes, 47 secondsour new interpolate function. So let's go ahead and paste that prompt here and let's execute it. I would highly
5:22:545 hours, 22 minutes, 54 secondsrecommend doing this in the same conversation so your agent has context of what we are developing. There we go.
5:23:005 hours, 23 minutesSo our run workflow task now has an accumulator as a constant called outputs which is an empty object and that
5:23:085 hours, 23 minutes, 8 secondscollects each executor's return keyed by node ID. We now interpolate before running. So each field in
5:23:165 hours, 23 minutes, 16 secondsnode.data.values values which was previously passed in raw is now passed through interpolate. So if the node data
5:23:245 hours, 23 minutes, 24 secondsvalues has any placeholder like this one it will result the upstream results just before the node executes and at the end
5:23:325 hours, 23 minutes, 32 secondswe store the result to the accumulator keyed by the ID. So await executor values get stage hand returns its value
5:23:405 hours, 23 minutes, 40 secondsstored inside of the outputs id object and we didn't do anything else because toposort already takes care of everything. So let's just go through the
5:23:495 hours, 23 minutes, 49 secondscode quickly. So we import our new interpolate util. We define the accumulator which is just a constant called outputs. And then in the for loop
5:23:585 hours, 23 minutes, 58 secondsof our uh nodes we go ahead and first check if we don't have an executor we manually continue. But if we do have an
5:24:065 hours, 24 minutes, 6 secondsexecutor, we make sure that we don't just pass in the raw values like we previously did like node data values, but instead we construct new values
5:24:145 hours, 24 minutes, 14 secondsusing our interpolate here. And then we don't just randomly throw away the results of the executor. We actually
5:24:215 hours, 24 minutes, 21 secondsstore them inside of our accumulator right here. So every subsequent step can properly interpolate using exact output.
5:24:295 hours, 24 minutes, 29 secondsNow let's do a few changes in the node registry which are simple enough for us to do by hand. in between node field and
5:24:365 hours, 24 minutes, 36 secondsnode definition. Let's go ahead and add a new type node output. Then let's go inside of the node definition. And after
5:24:445 hours, 24 minutes, 44 secondsfields, let's go ahead and make it so that each node definition also needs to have an output. So now inside of our
5:24:525 hours, 24 minutes, 52 secondsnode registry, we're going to have to strictly define exactly what each node can return from its values. For example,
5:25:025 hours, 25 minutes, 2 secondsthe start node doesn't return absolutely anything. So what does the open URL node
5:25:085 hours, 25 minutes, 8 secondsreturn? Well, to figure that out, all we have to do is go inside of the open URL inside of our nodes. And in here, we can
5:25:185 hours, 25 minutes, 18 secondssee exactly what this node returns. So let's add URL and title inside of the open URL node registry outputs. Now
5:25:275 hours, 25 minutes, 27 secondslet's construct a prompt that's going to develop the upstream outputs hook. So I want people to reference an upstream
5:25:345 hours, 25 minutes, 34 secondsnodes output without typing raw node ids. Give me a hook that takes the node I currently have selected and returns
5:25:425 hours, 25 minutes, 42 secondsevery output that any node upstream of it produces each as a ready to insert
5:25:485 hours, 25 minutes, 48 secondstemplate. a friendly label like open URL one which is the name of the node which I'm inserting and then its value and the
5:25:575 hours, 25 minutes, 57 secondssource nodes type so I can show its icon follow the connections all the way back up the graph not just the nodes direct
5:26:055 hours, 26 minutes, 5 secondsparents and recomputed as I connect and disconnect edges each node already declares which output it exposes put it
5:26:145 hours, 26 minutes, 14 secondsin the workflow features hooks and call it use upstream connections and follow the claude MD rule or agents.m MD if
5:26:225 hours, 26 minutes, 22 secondsyou're not using claude for using react flow. So what exactly is this for? Well, right now with what we currently have,
5:26:305 hours, 26 minutes, 30 secondswe are actually able to uh preview the value of the previous node. The problem
5:26:375 hours, 26 minutes, 37 secondsis we would have to manually type the template and we would have to know the ID of each previous node that came
5:26:475 hours, 26 minutes, 47 secondsbefore us which is not a good user experience. So what we need is a hook that's going to uh serve as the business
5:26:565 hours, 26 minutes, 56 secondslogic behind these chips here that the user can click on which will automatically insert uh the value of the
5:27:045 hours, 27 minutes, 4 secondsprevious node in in form of a token in form of a placeholder. So let's go ahead and run this prompt in our existing
5:27:125 hours, 27 minutes, 12 secondsconversation. Let's take a look at our new hook. So what does use upstream connection return? It returns an array
5:27:205 hours, 27 minutes, 20 secondsof upstream connections which is one entry per output of every node upstream of the selected node. Inside of the
5:27:275 hours, 27 minutes, 27 secondsupstream connection, we have a token which is a ready to insert placeholder like we expected and it matches the
5:27:345 hours, 27 minutes, 34 secondssyntax our interpolate helper resolves at runtime. We have a label which is displayed like this. So the name of the
5:27:425 hours, 27 minutes, 42 secondsnode and then the value which we are inserting the upstream nodes data title and then the outputs registry label. We
5:27:515 hours, 27 minutes, 51 secondsthen have node type the source nodes type. So the caller can render node registry node type icon which is what we
5:27:595 hours, 27 minutes, 59 secondswant for our chips components. So how does it work? Reads the selected node, all nodes and all edges reactively from
5:28:065 hours, 28 minutes, 6 secondsthe react flow store via use store. The pattern is already used inside of the right sidebar. Since edges are part of
5:28:155 hours, 28 minutes, 15 secondsthe selection, it recomputes on every connect and disconnect and on selection change. It walks the whole upstream chain, not just direct parents.
5:28:265 hours, 28 minutes, 26 secondsPerfect. So, let's actually take a look at the code here so we can see if anything is off. Even though just by
5:28:345 hours, 28 minutes, 34 secondsthis description, I can see it's exactly what we wanted here. So this is the upstream connection type which uh it just talked about and then in here we
5:28:415 hours, 28 minutes, 41 secondshave the actual hook. So what's interesting is that my agent generated a hook which doesn't accept any params. So
5:28:515 hours, 28 minutes, 51 secondsif you created a hook which accepts params, it's perfectly fine. It doesn't need to be line for line, right? Because
5:28:585 hours, 28 minutes, 58 secondswe are writing prompts which simply explain the idea what we want. They aren't necessarily, you know, very
5:29:055 hours, 29 minutes, 5 secondsstrict and made so that the next prompt that we do won't work unless your code is identical to mine. No, that's not
5:29:135 hours, 29 minutes, 13 secondsgoing to happen. Don't worry. So whether you have props here or you just directly use React Flow hooks inside, it's the
5:29:215 hours, 29 minutes, 21 secondssame thing. So yes, technically because we have access to use store, uh we don't need to pass any props. We can just access a selected node from here.
5:29:315 hours, 29 minutes, 31 secondsAnd then in here it basically does exactly what we told it to do. It goes through the outputs of all the previous
5:29:385 hours, 29 minutes, 38 secondsnodes and it returns a flat map of all the possible chips which we can insert
5:29:465 hours, 29 minutes, 46 secondsfor this selected node. Exactly what we wanted. So when I select a node I need some hook to compute how many of these
5:29:555 hours, 29 minutes, 55 secondsconnections do I have. So now that we have this, we can build the UI component which is actually going to render all of
5:30:035 hours, 30 minutes, 3 secondsthese connections. Now let's review prompt number five, connection chips in the inspector. So in the right sidebar
5:30:115 hours, 30 minutes, 11 secondsunder the selected nodes fields, add a connections section that shows up whenever use upstream connections hook
5:30:195 hours, 30 minutes, 19 secondswe just developed returns any outputs for that node. render each available output as a small chip with the source
5:30:285 hours, 30 minutes, 28 secondsnodes icon and its label. When I click on a chip, insert its token into whichever field I was last editing or
5:30:375 hours, 30 minutes, 37 secondsthe first field I haven't touched one yet. I want this for every connected node, not only the ones with a large
5:30:455 hours, 30 minutes, 45 secondstext field. And since we're once again using React Flow, it's just a little helper here. So what does this mean?
5:30:545 hours, 30 minutes, 54 secondsWell, now is the time for us to build this UI. So we now have the back end. We now have the registry and we now have
5:31:035 hours, 31 minutes, 3 secondsthe client hook which provides us with a flat map. We can simply iterate over and display to the user. These are all the
5:31:105 hours, 31 minutes, 10 secondsconnections you have. And when you click on one of those, it's simply going to insert it into whichever field you were last focused on. So let's go ahead and
5:31:195 hours, 31 minutes, 19 secondsrun this prompt in our existing conversation.
5:31:245 hours, 31 minutes, 24 secondsSo let's read through the output. Here's what I added to right sidebar connections section. It renders under
5:31:315 hours, 31 minutes, 31 secondsthe selected nodes field. Whenever our new hook use upstream connection returns any outputs because the hook reads
5:31:395 hours, 31 minutes, 39 secondsselection from react flow store and walks all the ancestors this appears for every connected node. exactly what we
5:31:475 hours, 31 minutes, 47 secondswanted regardless of whether it has big text or just single line inputs. We also render the chips. So each available
5:31:545 hours, 31 minutes, 54 secondsupstream output is now a small button showing the source nodes registry icon using node icon and its label like open
5:32:025 hours, 32 minutes, 2 secondsURL one and title wrapping it in a flex row and try truncating long labels. So we will see how this looks like. We can always tweak the design easily. And we
5:32:105 hours, 32 minutes, 10 secondshave click to insert. Clicking a chip appends its node ID path token to a target field. Field component now
5:32:185 hours, 32 minutes, 18 secondsreports focus via an onfocus prop. The inspector tracks active field key. Okay.
5:32:245 hours, 32 minutes, 24 secondsSo this is the logic to determine which was the last field the user was uh typing in. So when we click on the actual chip, it knows in in which field to insert.
5:32:345 hours, 32 minutes, 34 secondsBeautiful. Reset on selection change.
5:32:375 hours, 32 minutes, 37 secondsYes. So every time you change the nodes using the key, it simply resets the entire component. Brilliant. So just by this definition, I already know this is
5:32:465 hours, 32 minutes, 46 secondsexactly what we want. But still, let's take a look at the code here. So right sidebar component now imports use upstream connections.
5:32:555 hours, 32 minutes, 55 secondsOur field function now has on focus and it maintains on focus. If yours didn't do that, it's not it's not a big
5:33:035 hours, 33 minutes, 3 secondsmistake. Uh this is just so the chips insertion is aware in which field you're
5:33:115 hours, 33 minutes, 11 secondscurrently working because some nodes can have like three input fields. So when you click on like this is simple because we only have one field but what if we
5:33:195 hours, 33 minutes, 19 secondshad three fields how would it know into which field to insert the connection. So that's what it does here. It added the onfocus prop here and then I assume that
5:33:285 hours, 33 minutes, 28 secondsin the inspector or wherever the fields are rendered it changes the set active field key to that active field and then
5:33:375 hours, 33 minutes, 37 secondsthe insert token knows where to insert into which uh field key. In here we have
5:33:445 hours, 33 minutes, 44 secondsupdate node data which simply adds that token which is the structured from use upstream connections connections.
5:33:525 hours, 33 minutes, 52 secondsBeautiful. So very surgical change and this is where we render the actual connections we have available. So we'll see how this looks like. Uh we'll
5:34:015 hours, 34 minutes, 1 secondcompare to our design and see if we like this or not. And the inspector now has the selected ID key added here simply so it uh destroys the whole component and
5:34:105 hours, 34 minutes, 10 secondsrebuilds it. This is like an easy way of resetting whatever was loaded inside. Very very clean change. I love this.
5:34:185 hours, 34 minutes, 18 secondsRemember, if any of your changes look different or if the end result, which we're going to test now, doesn't work, feel free to simply open uh this is
5:34:265 hours, 34 minutes, 26 secondschapter 17 uh in my GitHub repository, find the branch, and take a look at all of these files, find them, and perhaps
5:34:355 hours, 34 minutes, 35 secondsdiscuss with your agent. Discuss why something didn't work or what do we need to do to make it work like these files,
5:34:435 hours, 34 minutes, 43 secondsso you have a more interactive experience in a tutorial. Now let's review these changes in our app. So
5:34:505 hours, 34 minutes, 50 secondsright now I have one start node and one open URL node and nothing looks different. So if I go ahead and attach
5:34:595 hours, 34 minutes, 59 secondsan open URL 2 to my open URL one. There we go. I can now inject the value of
5:35:085 hours, 35 minutes, 8 secondsthis previous node into this node right here.
5:35:135 hours, 35 minutes, 13 secondsOne thing we could improve, maybe give yourself a homework and maybe this can be a challenge. Try to make your fields
5:35:205 hours, 35 minutes, 20 secondsactually display the value somehow because right now we don't really care, right? Because what's actually going to
5:35:275 hours, 35 minutes, 27 secondsinterpolate the result of this template is inside of our run workflow. That's why we have uh this interpolate here. So
5:35:365 hours, 35 minutes, 36 secondsthat is now going to receive this template and it's then going to transform that into the actual value of
5:35:445 hours, 35 minutes, 44 secondsthis output right here. So I think that in theory now I should be able to access
5:35:515 hours, 35 minutes, 51 secondsboth of these nodes and both of these nodes should now open codewithantonia.com.
5:35:565 hours, 35 minutes, 56 secondsThat is because the output of our open URL as you can see is the URL that
5:36:045 hours, 36 minutes, 4 secondswe are currently on. So I think this should just translate to another version of httpsc codewithantonia.com. So make
5:36:135 hours, 36 minutes, 13 secondssure that you have trigger.dev running and execute this function. So if you now go into your latest session here, you
5:36:215 hours, 36 minutes, 21 secondswill find that two pages were were accessed. So first one was codewithantonio.com and then the second one once again
5:36:305 hours, 36 minutes, 30 secondscodewithantonio.com meaning that our data interpolation officially works. And here's the best
5:36:375 hours, 36 minutes, 37 secondspart. So if I go ahead and now chain open URL 3,
5:36:435 hours, 36 minutes, 43 secondsI can now access open URL 2 and open URL one. So that's the whole point of
5:36:505 hours, 36 minutes, 50 secondsbuilding this data pass through. And I think it was really fun developing this entire thing using a gentic coding. So
5:36:585 hours, 36 minutes, 58 secondsthis is why I kind of postponed using prompts until now because I wanted us to establish a very stable codebase because
5:37:075 hours, 37 minutes, 7 secondsnow is when it starts to be fun to build with agents because as you can see the outputs are very deterministic. It's
5:37:155 hours, 37 minutes, 15 secondsalmost exactly what we imagined. If I look at my picture, of course, there might be some slight differences in
5:37:225 hours, 37 minutes, 22 secondsthese chips, but honestly, I'm fine with them. I like them this way. Uh if yours look drastically different, you can either, you know, uh modify them
5:37:305 hours, 37 minutes, 30 secondsyourself or use this image and maybe take a screenshot of these images and then inside of the existing prompt here, go ahead and tell it make the chips look
5:37:395 hours, 37 minutes, 39 secondslike this. if your agent has um uh visibility and can access the images.
5:37:465 hours, 37 minutes, 46 secondsBeautiful. I'm so happy about how this uh went because we now have proper data interpolation and data pass through.
5:37:555 hours, 37 minutes, 55 secondsObviously, this will be a bit more exciting once we have different nodes something other than open URL. But I'm pretty satisfied with this. And now
5:38:035 hours, 38 minutes, 3 secondslet's go ahead and stage commit and get push our changes.
Chapter 19: Live Run Status
5:38:145 hours, 38 minutes, 14 secondsIn this chapter, we're going to develop the live run status. So, so far we can successfully execute our nodes. We can
5:38:235 hours, 38 minutes, 23 secondseven interpolate their values. But we don't have an indicator as to which node is currently running. Nor do we have an
5:38:305 hours, 38 minutes, 30 secondsindicator if a node fails. So just like in the previous chapter, I've prepared a specification with all of the prompts
5:38:385 hours, 38 minutes, 38 secondswhich we are going to run in this chapter. So go into our GitHub repository either on the main branch or
5:38:455 hours, 38 minutes, 45 secondsgo ahead and find chapter 18 live run status and in the specifications folder
5:38:525 hours, 38 minutes, 52 secondsyou will find the new prompts. So the live run status needs to start from somewhere and in our case the answer is
5:39:015 hours, 39 minutes, 1 secondfrom the run workflow task. This is essentially the trigger.dev environment.
5:39:075 hours, 39 minutes, 7 secondsAnd inside of this environment we have the option to store the current status of a node whether it's executing or
5:39:155 hours, 39 minutes, 15 secondswhether it failed using trigger metadata. And then we somehow have to send that to the UI. So trigger realtime
5:39:245 hours, 39 minutes, 24 secondshooks can accept that and display it accordingly. So let's go through the first prompt together in which we are
5:39:315 hours, 39 minutes, 31 secondsgoing to stream the step status from the trigger.dev run. So inside of our run workflow task stream each node's live
5:39:395 hours, 39 minutes, 39 secondsstatus so that canvas can show progress before running anything. Build a list of the steps we are about to run. each just
5:39:475 hours, 39 minutes, 47 secondsa node ID and status starting at pending and then publish it to the runs metadata under steps value. Export the step type
5:39:565 hours, 39 minutes, 56 secondsand call it run step. So we are here establishing the types and the default
5:40:045 hours, 40 minutes, 4 secondsstate we need to maintain each node's progress as we go set a node's status to running
5:40:115 hours, 40 minutes, 11 secondsbefore its executor. So before a node reaches the executor, let's go ahead and
5:40:185 hours, 40 minutes, 18 secondslabel it as running. And then after the executor is finished, mark it as done or
5:40:265 hours, 40 minutes, 26 secondsfailed if it throws. And at that point also stop the run. So no going forward.
5:40:315 hours, 40 minutes, 31 secondsAnd then republish the metadata on every change. right after marking a node running, force the metadata to flush.
5:40:405 hours, 40 minutes, 40 secondsOtherwise, that state gets overwritten by done before it's ever pushed and we never see the spinner. So, this is
5:40:475 hours, 40 minutes, 47 secondssomething that I've come to find out after a few unsuccessful implementations of this. So, when working with
5:40:545 hours, 40 minutes, 54 secondstrigger.devs metadata, you have to flush it after certain events, otherwise it simply won't reach the canvas and it would appear as broken. So that's why I have explicitly added it to this prompt.
5:41:065 hours, 41 minutes, 6 secondsAlso flush right after marking a node as failed before the run stops. A thrown run reaches no output. So the flushed
5:41:135 hours, 41 minutes, 13 secondsmetadata is the only way that failed state ever reaches the canvas. Also return the final steps from the task. So a successful run's finished state is
5:41:225 hours, 41 minutes, 22 secondsguaranteed. Keep the existing interpolation and execution as is. And finally use the trigger.dev tasks skill.
5:41:315 hours, 41 minutes, 31 secondsSo let's go ahead and implement this prompt. Let's take a look at the change.
5:41:355 hours, 41 minutes, 35 secondsSo we now have metadata imported from trigger.dev SDK. We have a new exported type called run step with node ID and
5:41:445 hours, 41 minutes, 44 secondsthe status which can either be pending, running, done or failed.
5:41:505 hours, 41 minutes, 50 secondsThen in here after we topologically sort our nodes. So we have a new constant called order. We go ahead and we
5:41:585 hours, 41 minutes, 58 secondsconstruct all of the steps from that order and we make sure that each one starts with pending and then we add
5:42:055 hours, 42 minutes, 5 secondsthose to the metadata under the steps property.
5:42:095 hours, 42 minutes, 9 secondsSo now we replaced the four const loop to a regular for uh let i loop I'm
5:42:175 hours, 42 minutes, 17 secondsassuming so we can keep track of the index here. So now we manually have to maintain the id and then we have to
5:42:245 hours, 42 minutes, 24 secondsconstruct the step using these steps and then accessing it via the index.
5:42:305 hours, 42 minutes, 30 secondsSo before we actually await the executor we go ahead and set
5:42:385 hours, 42 minutes, 38 secondsthis status to running and we modify the metadata once again and then we do metadata flush so it actually appears on
5:42:455 hours, 42 minutes, 45 secondsthe canvas. We now execute the executor instead of a try and catch because that is the only way we can uh capture if it
5:42:545 hours, 42 minutes, 54 secondsfailed. And if it did, we modify the step status to failed. We once again change the metadata steps and when then we do metadata flush. We do an early
5:43:045 hours, 43 minutes, 4 secondsstage hand close and we also throw an error. Otherwise, if it doesn't get into the catch block, we do step status done
5:43:125 hours, 43 minutes, 12 secondsand metadata set steps steps. And we have simplified the return output.
5:43:175 hours, 43 minutes, 17 secondsBrilliant. So very clean and surgical change. So now that our trigger.dev task is actually outputting the status, we
5:43:265 hours, 43 minutes, 26 secondsneed to subscribe to that workflows runs. So our next prompt is going to be the following. I want one shared
5:43:335 hours, 43 minutes, 33 secondssubscription to this workflows runs that any component on the canvas can read.
5:43:385 hours, 43 minutes, 38 secondsgive me a client provider that subscribes to workflows runs in real time by their tag which is the workflow
5:43:445 hours, 43 minutes, 44 secondsID. So remember when we added that inside of our actions.ds.
5:43:515 hours, 43 minutes, 51 secondsIf you scroll down you can find run workflow action that is why we added a tag. I told you that it's going to come in handy later. So make sure that you
5:43:595 hours, 43 minutes, 59 secondsactually have this tag right here. Using a public access token passed in as a prop. call it workflow runs provider. So
5:44:085 hours, 44 minutes, 8 secondswe are creating a new provider. So we're going to wrap our entire live blocks room, our canvas inside of it. And then
5:44:155 hours, 44 minutes, 15 secondsany component in there will be able to access which node is currently running uh and all other metadata we decide to
5:44:225 hours, 44 minutes, 22 secondspass through. Expose a use latest run steps hook that returns the most recent runs steps plus whether it's still live
5:44:325 hours, 44 minutes, 32 secondspreferring the run's initial output steps and falling back to the live metadata steps. Live means the run is cued or executing. [snorts] So we're
5:44:415 hours, 44 minutes, 41 secondsgoing to develop a hook called use latest run steps which will either return the metadata values or the current live values.
5:44:525 hours, 44 minutes, 52 secondsSo there is a difference that is because uh trigger.dev outputs values using their
5:45:015 hours, 45 minutes, 1 secondreal-time hooks of the currently running task but also preserves all the values
5:45:085 hours, 45 minutes, 8 secondsof the previous tasks which have completed. So we're going to need to create a hook which checks if the live
5:45:175 hours, 45 minutes, 17 secondsone is active. So it displays the most up-to-date data or falls back to the data which is now in the metadata which
5:45:255 hours, 45 minutes, 25 secondswe stored ourselves. You're going to see in the code it's easier that way and put it in the workflow features components.
5:45:335 hours, 45 minutes, 33 secondsUse trigger.dev realtime and front-end scale. So let's go ahead and run this prompt inside of the same conversation which has context of what we're
5:45:405 hours, 45 minutes, 40 secondsbuilding. You should now have a new component inside of features workflows components called workflow runs
5:45:475 hours, 45 minutes, 47 secondsprovider. So in here it's marked as use client and it uses trigger.dev react hooks specifically use realtime runs
5:45:565 hours, 45 minutes, 56 secondswith a tag and in here it does exactly what we described it and it uses the access token. So that's the next thing
5:46:055 hours, 46 minutes, 5 secondswhich we're going to have to create a proper consolidation uh and cascading of that access token which we are going to
5:46:125 hours, 46 minutes, 12 secondshand down as a prop. Beautiful. So use realtime runs with tag and this is how
5:46:195 hours, 46 minutes, 19 secondswe connect to whatever our run workflow is outputting. Right? So we are currently outputting uh some things using metadata set and metadata flush.
5:46:315 hours, 46 minutes, 31 secondsRight? But the only way we can subscribe to that is by using the correct tag which is workflow workflow ID because
5:46:395 hours, 46 minutes, 39 secondsthat is what we have set inside of our actions.
5:46:435 hours, 46 minutes, 43 secondsDS in here we just have a normal use memo for the value. So we have the runs, we have the error. Perfect. This is
5:46:525 hours, 46 minutes, 52 secondssimple enough. This isn't really a complicated function at all. And in here we have a hook use workflow runs. This
5:46:595 hours, 46 minutes, 59 secondsis simply so we can access the value of this provider inside of any component we might need. And then we have this which we requested use latest run steps. So in
5:47:085 hours, 47 minutes, 8 secondshere it created uh a hook which will always produce the latest run right. So
5:47:175 hours, 47 minutes, 17 secondsit maintains whether we are live which are the metadata steps and the steps.
5:47:235 hours, 47 minutes, 23 secondsAnd you can see how it falls back in between the output or the metadata steps. So that's what I was talking about. Your code, your agent should have
5:47:315 hours, 47 minutes, 31 secondsgenerated something uh similar because trigger.dev outputs multiple variations of uh their real-time status. And for
5:47:415 hours, 47 minutes, 41 secondsthe nodes which have already been finished, we need to fall back to some other value. Brilliant. So if yours is anything like this, it doesn't need to
5:47:495 hours, 47 minutes, 49 secondsbe line for line, but it should be a workflow runs provider and it should use use real-time runs with tag. Now let's
5:47:575 hours, 47 minutes, 57 secondsactually wire this up. In the workflow page, wire up the real-time subscription. Mint a readonly public
5:48:045 hours, 48 minutes, 4 secondstoken scoped in this workflows run tag good for about an hour and wrap the canvas shell in the workflow runs
5:48:115 hours, 48 minutes, 11 secondsprovider we just made. So that component we just generated passing in the workflow ID and that token use trigger dev realtime and front-end skill.
5:48:225 hours, 48 minutes, 22 secondsPerfect. So in that same conversation, let's go ahead and run this prompt. So let's take a look at the modification it did to page.tsx.
5:48:325 hours, 48 minutes, 32 secondsSo so far you should have three changes.
5:48:345 hours, 48 minutes, 34 secondsOne in the run workflow which outputs the live status. another in workflow runs provider which consumes what our
5:48:435 hours, 48 minutes, 43 secondstask is outputting and then one change in the page inside of the workflow ID which is responsible for creating the
5:48:515 hours, 48 minutes, 51 secondsaccess token to pass to the workflow run provider so we can correctly communicate with the running task and the reason this needs to be authenticated using the
5:49:005 hours, 49 minutesaccess token is so that someone some third party cannot uh maliciously uh look at our running tasks of So we
5:49:095 hours, 49 minutes, 9 secondsimport out as trigger out from trigger.dev SDK. We use an alias because we already have out from clerk next.js
5:49:175 hours, 49 minutes, 17 secondsserver and we use our new workflow runs provider. Then we generate a runs token using trigger out create public token.
5:49:265 hours, 49 minutes, 26 secondsWe go ahead and give it a read access and we tag it to the workflow ID and we give it an expiration time of 1 hour.
5:49:355 hours, 49 minutes, 35 secondsAnd then we simply wrap the workflow shell inside of the workflow runs provider passing along the workflow ID and the access token. Perfect. Very
5:49:435 hours, 49 minutes, 43 secondssimple, very precise. There's only one more thing we have to do and that is to paint the nodes. So we have to modify
5:49:515 hours, 49 minutes, 51 secondsour step node component and make each node reflect the latest run. So we have to look up this node's status using our
5:49:585 hours, 49 minutes, 58 secondshook use latest run steps by matching the node ID. When it's running, show a spinner in place of the nodes icon and
5:50:065 hours, 50 minutes, 6 secondsgive it a blue border. When it failed, give it a destructive border. Only treat a node as running while the run is
5:50:135 hours, 50 minutes, 13 secondsactually live. If the run has ended, a node left marked running should stop spinning. So, let's go ahead in the same
5:50:205 hours, 50 minutes, 20 secondsconversation and completely finalize this feature. Let's take a look at the changes in step node component. So
5:50:295 hours, 50 minutes, 29 secondsinside of the component we now import use latest run steps from our workflows run provider. We import the spinner
5:50:365 hours, 50 minutes, 36 secondscomponent from components UI spinner. We pass along the ID to the prop in the step node component.
5:50:445 hours, 50 minutes, 44 secondsWe destruct the steps and whether is live using use latest run steps. We extract the current status of our node
5:50:525 hours, 50 minutes, 52 secondsby filtering or finding our exact ID of the node. We define is running if status
5:51:005 hours, 51 minutesis running and if we extract is live from use latest run steps and we define
5:51:065 hours, 51 minutes, 6 secondsis failed if status is failed. And then very simply we have modified the most outer div uh to change the border blue
5:51:165 hours, 51 minutes, 16 seconds500 if is running and if is failed border destructive and if it's running we don't render the icon but instead we
5:51:245 hours, 51 minutes, 24 secondsrender the spinner and then we fall back on the icon otherwise. Beautiful. So once again very clean simple surgical
5:51:325 hours, 51 minutes, 32 secondschange. Now let's test it out. If you try to enter any of your existing workflows you will probably see an error like this. Steps don't find is not a
5:51:415 hours, 51 minutes, 41 secondsfunction. That is because those are existing workflows which have different metadata in them. And as you can see, we
5:51:485 hours, 51 minutes, 48 secondsactually changed the steps from being a number to being an array with object inside. So that is why all of the previous workflows are going to fail.
5:51:595 hours, 51 minutes, 59 secondsLet's go inside of our neon database.
5:52:015 hours, 52 minutes, 1 secondLet's choose our project tables. And in here, let's clean up everything we have in the workflows. So, delete all
5:52:105 hours, 52 minutes, 10 secondsrecords. I would also recommend doing the same inside of your live blocks dashboard simply so you don't have any orphaned rooms. Then go ahead and
5:52:185 hours, 52 minutes, 18 secondsconstruct a new workflow. Start node connected to open URL and make sure that this one has a working URL and then
5:52:275 hours, 52 minutes, 27 secondsconnect it to the second node. And in here, make sure you add an invalid URL.
5:52:345 hours, 52 minutes, 34 secondsWe want to test if this nodes actually fails. And now let's go ahead and click run. And let's see. There we go. So this
5:52:415 hours, 52 minutes, 41 secondsnode is currently in progress. And let's see what happens once we reach the open URL to node to which we purposely uh put
5:52:505 hours, 52 minutes, 50 secondsan incorrect URL. And as expected, this node then fails. Keep in mind that trigger.dev has builtin retries. So what
5:53:005 hours, 53 minutesit's going to do is it's going to retry I think about three times. Let's see.
5:53:055 hours, 53 minutes, 5 secondsYes, it's going to attempt a maximum of three attempts. So you will probably see this repeating and that's another
5:53:125 hours, 53 minutes, 12 secondsbenefit of using a trigger because otherwise this would have been a very complicated feature to implement ourselves. Amazing. And now after three
5:53:215 hours, 53 minutes, 21 secondsattempts it is stuck here. Beautiful. So we are pretty much finished with our main functionality. Now go ahead and
5:53:305 hours, 53 minutes, 30 secondsstage commit and push your changes.
Chapter 20: Remaining Nodes
5:53:405 hours, 53 minutes, 40 secondsSo far we've only developed two nodes with only one of them being an action node which has some kind of execution
5:53:485 hours, 53 minutes, 48 secondsbehind it. So let's quickly take a peek at our codebase. How would we go about adding a brand new node? Well, good news
5:53:565 hours, 53 minutes, 56 secondsis all the files we have to modify are inside of features workflows. We would start with defining a brand new executor
5:54:055 hours, 54 minutes, 5 secondswhich is something like this open URL file which we have. Once we define a new executor, we have to register it inside
5:54:135 hours, 54 minutes, 13 secondsof our node executors. So it satisfies the record and then we have to register the new node inside of the node
5:54:215 hours, 54 minutes, 21 secondsregistry. So not too bad actually. We only have to modify two files and create one new file and everything will
5:54:295 hours, 54 minutes, 29 secondsautomatically sit in its place because we built this using uh factory type of development, right? We don't have to
5:54:375 hours, 54 minutes, 37 secondsmodify the right sidebar. We don't have to modify the run workflow task. We essentially built small factories which
5:54:445 hours, 54 minutes, 44 secondsdo all of that for us modularly. And while that makes it easy for us to add new nodes, it also makes it very easy
5:54:535 hours, 54 minutes, 53 secondsand deterministic for agents to add new nodes for us. So instead of instructing the agent how to do that every time, one
5:55:025 hours, 55 minutes, 2 secondstrick that we can do is modify our agents.m MD or claude.md and add the following snippet. Adding a
5:55:115 hours, 55 minutes, 11 secondsworkflow node. Three edits required all under features workflows nodes. First we create the actual implementation file
5:55:205 hours, 55 minutes, 20 secondsfor example the open URL which is the nodes executor logic. We then register it inside of the node executors and make
5:55:285 hours, 55 minutes, 28 secondssure that the satisfy contract makes a missing executor a compile error for action nodes. And then we have to add
5:55:355 hours, 55 minutes, 35 secondsits manifest entry inside of the node registry. We define the kind label icon accent all of the input fields is going
5:55:435 hours, 55 minutes, 43 secondsto have and the outputs downstream nodes can then reference the run task and the canvas step are registrydriven. Never
5:55:525 hours, 55 minutes, 52 secondstouch them to add a node. So exactly what we just went through in our codebase is what we've described here.
5:55:595 hours, 55 minutes, 59 secondsYou can of course find my agents.md file in the GitHub repository and simply copy this snippet if you don't want to pause the video and write it yourself. And now
5:56:085 hours, 56 minutes, 8 secondswe can create prompts which are going to reliably create new nodes in our codebase. I have once again prepared
5:56:145 hours, 56 minutes, 14 secondschapter 19 remaining nodes specification file for you in which you can find the exact change we've added to agents MD as
5:56:225 hours, 56 minutes, 22 secondswell as all the prompts which we're going to add to generate new nodes. So let's execute the prompt which is going to add the act node to our code. Let's
5:56:315 hours, 56 minutes, 31 secondstake a look at the code which was generated. So first of all, we now have a new executor called act and it's located right next to the open URL in
5:56:405 hours, 56 minutes, 40 secondsthe nodes folder. So very similarly as to open URL, the act node accepts a stage hand instance the instruction
5:56:485 hours, 56 minutes, 48 secondsvalue and then uses stage hand API to perform an act whatever that is uh per user's instruction in the natural
5:56:575 hours, 56 minutes, 57 secondslanguage. In the return, we bring back to the user whether it was successful or not, whether there's any messages and
5:57:055 hours, 57 minutes, 5 secondsthe URL that we are now on after an act was performed. So now inside of the node executors, which is my other change,
5:57:145 hours, 57 minutes, 14 secondsthat new act executor was registered the same as the open URL. So we pass the stage hand and we pass the instruction using values.instruction.
5:57:235 hours, 57 minutes, 23 secondsAnd then inside of the node registry, I don't know which icon it's going to choose for you. For me, it chose the pointer icon and it added an act node.
5:57:335 hours, 57 minutes, 33 secondsIt gave it a label of act icon of pointer. It used the purple color, it seems. And fields is just a single
5:57:405 hours, 57 minutes, 40 secondsmulti-line required field called instruction. So whether yours is multi-line or not, it doesn't really matter. It's a preference for the agent.
5:57:485 hours, 57 minutes, 48 secondsAnd the outputs are exactly what we output inside of the act note. success message and uh the URL. Now, let's see
5:57:575 hours, 57 minutes, 57 secondsif it actually works. So, I'm going to open my website codewithantonio.com and I'm going to tell it to click on the
5:58:045 hours, 58 minutes, 4 secondsbrowse courses button. So, it should perform this right here. Let's see if it's actually going to work. So, make
5:58:115 hours, 58 minutes, 11 secondssure that you have your trigger development server running and your app running. And let's take a look at our latest session. So what I presume has
5:58:215 hours, 58 minutes, 21 secondshappened is we first went on to codewithantonia.com and then we should click on the browse
5:58:285 hours, 58 minutes, 28 secondscourses button and there we go. We clicked on the browse courses button and it did a redirect. Now go ahead and try
5:58:375 hours, 58 minutes, 37 secondschaining another action to it and make sure that you can see the output of the previous act node which should allow you
5:58:455 hours, 58 minutes, 45 secondsto interpolate the whatever output values the previous node has produced.
5:58:515 hours, 58 minutes, 51 secondsNow let's go ahead and add the extract node. Once again a stage handp powered action node with a single multi-line
5:58:585 hours, 58 minutes, 58 secondsinstruction field. It pulls data off the page described in the instruction using stage hands exact extract method.
5:59:055 hours, 59 minutes, 5 secondssurface the extracted result as an output. Follow our convention for adding a node. And once again, we have the exact same output. A new executor called
5:59:145 hours, 59 minutes, 14 secondsextract registered inside of the node executors. And then node registry has a new manifest entry called extract. The
5:59:225 hours, 59 minutes, 22 secondsexecutor for the extract is quite simple. All it does is it performs stage hand extract with natural language instruction from the user and returns
5:59:315 hours, 59 minutes, 31 secondsthe output of the extraction. I would recommend performing the test for the extract node on a very simple website
5:59:375 hours, 59 minutes, 37 secondsfor example quotestoscrape.com which is essentially a sandbox for webcraping and it's also HTML static and
5:59:475 hours, 59 minutes, 47 secondsvery simple so there shouldn't be any problems and you should get very deterministic outputs so let's go ahead and run this one so now inside of your
5:59:555 hours, 59 minutes, 55 secondsnewest browserbased session if you scroll down here you will find the exact timeline first of opening the URL and
6:00:036 hours, 3 secondsthen the result of the instruction extract five quotes and you can click on output and down here you will see five
6:00:146 hours, 14 secondsquotes extracted. I'd also recommend testing that if you connect any other node to the extract node that you can
6:00:206 hours, 20 secondsactually uh interpolate the output of that previous extract node inside. Now let's add the observe node which is
6:00:296 hours, 29 secondsanother stage handp powered action which doesn't do any acts or any extraction uh but instead it simply finds the
6:00:376 hours, 37 secondsclickable elements and other DOM elements on the website which you can then use to more precisely use the act
6:00:446 hours, 44 secondsnode. Make sure that the executor generated for the observe node looks something like this. So we use stage hand API to invoke the observe action
6:00:536 hours, 53 secondspassing the natural language which is the user's instruction and then we simply iterate over the matches and return those matches and you should also
6:01:026 hours, 1 minute, 2 secondsmake sure that this is properly uh registered in the executors and in the node registry to test it out. Let's once
6:01:116 hours, 1 minute, 11 secondsagain load our quotes scraping page and let's tell our observe node to find all clickable elements. And then inside of
6:01:196 hours, 1 minute, 19 secondsthe act node, let's go ahead and tell it click on the first item inside of our observe one matches. So I assume that
6:01:286 hours, 1 minute, 28 secondsthis will basically give us a list of all clickable elements. So let's click on the first item that it finds. And if you visit your browserbased session,
6:01:366 hours, 1 minute, 36 secondsit's going to be a bit anticlimatic because the first clickable element is the quotes to scrape button. So perhaps
6:01:446 hours, 1 minute, 44 secondswe should have told it to click on the second clickable element. And you can see all of that in here. So first we navigate to uh quotes to scrape. Then we
6:01:526 hours, 1 minute, 52 secondsfind all clickable elements. And inside of the output you can see exactly everything it found. And you can see that the first one in this array is the
6:02:016 hours, 2 minutes, 1 secondlink quotes to scrape. So the second one would have been a login link or maybe the about link. So yes, the act node in the end just clicked on the quotes to
6:02:106 hours, 2 minutes, 10 secondsscrape. It might have been more fun for if it clicked on maybe login or Albert Einstein, something like that. So yes, the video is going to be a bit
6:02:186 hours, 2 minutes, 18 secondsanticlimactic, but you can actually see that it clicks on quote to scrape. But I think we've demonstrated the power of this node, right? If you want to play
6:02:276 hours, 2 minutes, 27 secondsaround, go ahead and tell it maybe to click on the second item and see what happens. Now let's develop the star of the show, the agent node, which is
6:02:356 hours, 2 minutes, 35 secondsanother stage handpowered action node with a single multi-line instruction field. It runs an autonomous multi-step
6:02:426 hours, 2 minutes, 42 secondsbrowser task from one instruction using stage hands as agent surface whether it succeeded a summary message and whether
6:02:496 hours, 2 minutes, 49 secondsit completed as outputs and then followed our convention for adding a node. So this is basically our superpowered node which is able to act as if a human were navigating a website.
6:03:016 hours, 3 minutes, 1 secondSo once again you should have the agent exeutor registered in the node executors and the node registry and my agent has
6:03:096 hours, 3 minutes, 9 secondsgenerated the following executor. So once again stage hand API which runs the agent and runs execute on the user's instruction and returns success message
6:03:186 hours, 3 minutes, 18 secondsand whether it was completed or not. So let's test our superpowered node once again in a very simple scraping sandbox
6:03:266 hours, 3 minutes, 26 secondsand let's tell it to login with a username of admin and password admin.
6:03:316 hours, 3 minutes, 31 secondsClick on the about link in the first outor that appears and then connect the extract node and extract the information about uh that author and just make sure
6:03:406 hours, 3 minutes, 40 secondsthat you can see the connections from the previous node to ensure that that is working correctly. So we are purposely doing a very simple example even though
6:03:496 hours, 3 minutes, 49 secondsthis is a very powerful node and I'm sure you can only imagine the things you can do with this but I recommend testing
6:03:556 hours, 3 minutes, 55 secondsit out in a uh sandbox for scraping because you can get very deterministic results with this. And let's run it. And
6:04:036 hours, 4 minutes, 3 secondsif you actually visit the session on time, you will see the live session of what your agent is currently doing. So you just saw how it entered admin as the
6:04:126 hours, 4 minutes, 12 secondspassword and the uh username and you will now see the whole timeline of everything the agent did. So you can see
6:04:206 hours, 4 minutes, 20 secondshow agent has its own uh access to the act node, its own access to observe, right? So that's what the agent can do.
6:04:286 hours, 4 minutes, 28 secondsSo agent is essentially all nodes in one. But if you do want more granular access then you would combine both the
6:04:376 hours, 4 minutes, 37 secondsagent to maybe do some long task and then do some very deterministic simple task with a specific act observe or in
6:04:446 hours, 4 minutes, 44 secondsour case extract which I've now extracted the about Albert Einstein description. So you can see how useful
6:04:516 hours, 4 minutes, 51 secondsit is to create a code base which serves as a factory for your coding agents because this couldn't be further away
6:04:596 hours, 4 minutes, 59 secondsfrom vibe coding. And yet we didn't write a single line of code for any of these tools which work extremely
6:05:076 hours, 5 minutes, 7 secondsreliably and the code is exactly as we expected because we created an environment in which coding agents perform very well. And then go ahead and
6:05:166 hours, 5 minutes, 16 secondsstage commit and push your changes.
Chapter 21: Email Node
6:05:266 hours, 5 minutes, 26 secondsNow, let's use resend to add the email node to our project. Using the link on the screen, you can get onto their website and the link simply lets them
6:05:346 hours, 5 minutes, 34 secondsknow that you came from this video. Once you create an account, go inside of API keys and create a new API key. Make sure to give it full access and all domains.
6:05:456 hours, 5 minutes, 45 secondsThen copy your key and add it to the environment file under the name recent API key. Then go inside of the
6:05:526 hours, 5 minutes, 52 secondsdocumentation and scroll down until you find build with AI section. In here you can find the agent skills. Make sure
6:06:006 hours, 6 minutesthat you select resend skill as that is the one we have to install. Then go ahead and execute it in your terminal
6:06:086 hours, 6 minutes, 8 secondswithin your project. You will now be asked which skills to install. So, we are not going to need the agent email
6:06:166 hours, 6 minutes, 16 secondsinbox. We are not going to need email best practices nor the React email. We just need the resend itself, which is
6:06:236 hours, 6 minutes, 23 secondsbasically the SDK, which we're going to use to programmatically send emails using resend node. Make sure to select
6:06:306 hours, 6 minutes, 30 secondsyour coding agent and make sure to select the project installation scope and use the symbolic link and proceed with the installation. Then go ahead and
6:06:396 hours, 6 minutes, 39 secondsperform a git add and git commit so you don't have 23 changes in here and you can more closely and precisely follow
6:06:476 hours, 6 minutes, 47 secondsthe actual changes we're going to do to our codebase. Now make sure to perform reload skills and reload window if
6:06:546 hours, 6 minutes, 54 secondsyou're using a graphical interface and check if you have the recent skill available. Now let's prompt the following. Set up recent SDK client
6:07:026 hours, 7 minutes, 2 secondsinside of my lib folder in the project route. Use the recent skill. You should have the following changes. A new package added to their package JSON and
6:07:116 hours, 7 minutes, 11 secondsa recent lib located inside of the lib folder right next to where live blocks lives. You should import recent and very
6:07:196 hours, 7 minutes, 19 secondssimply export a new instance of recent using the recent API key which we've added in our environment.local. So just
6:07:286 hours, 7 minutes, 28 secondsmake sure that it isn't misspelled. Now let's construct a prompt to create this into a node. As always, this prompt is
6:07:366 hours, 7 minutes, 36 secondsavailable in the specification file in the specs folder called after chapter 20 email node. First, add a send email
6:07:456 hours, 7 minutes, 45 secondsaction node that sends an email through resend no browser session. So, it doesn't use stage hand. So, we purposely say this because all other nodes so far
6:07:546 hours, 7 minutes, 54 secondshave been using stage hand. So, just in case the agent looks through those nodes and thinks, oh, so I need to use stage hand. Let's make sure that it doesn't
6:08:016 hours, 8 minutes, 1 seconduse stage hand explicitly. It has three fields. A recipient or to like to whom
6:08:096 hours, 8 minutes, 9 secondswe are sending, a subject, and a multi-line body. When it runs, send the email with our existing resend client
6:08:166 hours, 8 minutes, 16 secondsfrom the hard-coded address onboarding atresend.dev.
6:08:216 hours, 8 minutes, 21 secondsSo, unless you purchase a domain and add it to resend, and I think you need to be on their pro plan, you need to send
6:08:296 hours, 8 minutes, 29 secondsemails through this domain. They don't allow sending it from any custom domains which is perfectly fine for development.
6:08:366 hours, 8 minutes, 36 secondsSurface descent emails ID as an output so downstream nodes can reference it.
6:08:416 hours, 8 minutes, 41 secondsResends send returns data and error and doesn't throw on API error. If there is an error throw throw so the run marks
6:08:506 hours, 8 minutes, 50 secondsthis step as failed otherwise the node would look successful even when the email is never sent. Follow our convention for adding a node and use the
6:08:586 hours, 8 minutes, 58 secondsresend skill. You should now have a new implementation executor inside of the nodes folder which uses our resend uh
6:09:076 hours, 9 minutes, 7 secondsclient library. Calls the function send email. Accepts two subject and body which are all strings. Extracts data and error using await resend emails send.
6:09:206 hours, 9 minutes, 20 secondsHardcodes from to be onboarding at recent.dev because we need this in development. then passes along the dynamic to subject and HTML as the body.
6:09:306 hours, 9 minutes, 30 secondsIn case there's an error or there's no data, go ahead and manually throw an error. So we properly register this as a
6:09:376 hours, 9 minutes, 37 secondsfailed node. And if successful, go ahead and simply return data ID. Make sure that you also have a new node registered
6:09:466 hours, 9 minutes, 46 secondsin the node registry. Same as in the node exeutor. Go ahead and construct a workflow which ends in some kind of
6:09:556 hours, 9 minutes, 55 secondsextract node and then attach your new send email node to this extract node.
6:10:016 hours, 10 minutes, 1 secondMake the subject be something of relevance to whatever is in the extract node. Same in the body and then find the connection for that extract node and
6:10:106 hours, 10 minutes, 10 secondsinterpolate its extraction. And for the two property you need to enter the email in which you are logged in into your
6:10:196 hours, 10 minutes, 19 secondsrecent account. So in development you cannot send emails anywhere besides your own uh account which you're logged in with. So make sure you use that account.
6:10:296 hours, 10 minutes, 29 secondsYou should also see all of that information in the node itself and then go ahead and run the workflow. Now go inside of the resend dashboard under
6:10:376 hours, 10 minutes, 37 secondsemails and in the sending tab you will see exactly which email you have sent.
6:10:436 hours, 10 minutes, 43 secondsAs you can see tutorial mailing is the address as I've entered. Subject is author information and inside I can see the about section of Albert Einstein.
6:10:546 hours, 10 minutes, 54 secondsAnd we can find the same email in our Gmail inbox. And now let's go ahead and stage commit and push our changes.
Chapter 22: Console Panel
6:11:096 hours, 11 minutes, 9 secondsNow that we've added all the nodes, let's go ahead and develop the logs panel. The logs panel's purpose is to
6:11:156 hours, 11 minutes, 15 secondsdisplay to the user exactly how each workflow went. We can see that more closely in this image canvas 2.png.
6:11:256 hours, 11 minutes, 25 secondsSo each run will be inside of a batch with individual steps inside. And we're going to see exactly how long each step
6:11:346 hours, 11 minutes, 34 secondstook before it was completed. And we're going to see if any step is in progress or if it was skipped or simply not there
6:11:416 hours, 11 minutes, 41 secondsyet. And each run will be uh separated with some kind of divider. The place where we have to start developing this
6:11:486 hours, 11 minutes, 48 secondsfeature is where we actually run the task. That is because in order to develop this component, we need to add some crucial metadata to our tasks. For
6:11:586 hours, 11 minutes, 58 secondsexample, we need to have duration. But right now, inside of our run workflow task, we don't calculate how long each
6:12:076 hours, 12 minutes, 7 secondsstep lasts. So this will be the first prompt we have to construct. We're going to need to add some more properties. So
6:12:146 hours, 12 minutes, 14 secondsthis run workflow actually tracks duration. You can find all of the prompts which I'm going to use in this chapter inside of this specifications
6:12:226 hours, 12 minutes, 22 secondsfolder inside of chapter 21 console panel. First, let's go ahead and install a new dependency called pretty
6:12:296 hours, 12 minutes, 29 secondsmilliseconds. So, let's explain to the agent what we are trying to achieve and what we need to modify first. I want a console under the canvas that shows what
6:12:386 hours, 12 minutes, 38 secondseach run did, a list of every run and its steps. And clicking on a step shows what that step produced or its error if
6:12:456 hours, 12 minutes, 45 secondsit failed, plus how long it took. So that's the general idea of this logs panel. A display of every single step
6:12:536 hours, 12 minutes, 53 secondswithin a run as well as how long each step took. And clicking on any of the steps should split the logs panel in
6:13:016 hours, 13 minutes, 1 secondhalf and then in the other half display either the JSON formatted output or the error if it failed. If a step hasn't
6:13:096 hours, 13 minutes, 9 secondsbeen reached yet, it should appear inactive like this. And if it's in progress, it should be spinning. So in the first sentence we simply give it a
6:13:186 hours, 13 minutes, 18 secondsgeneral idea of what we are building and then we start with the first request which is what we uh established that we need. We need to modify our run workflow
6:13:276 hours, 13 minutes, 27 secondstask. Right now a run step only records its node ID and status inside of run
6:13:346 hours, 13 minutes, 34 secondsworkflow. So there's nothing to show yet. Basically, if you go inside of the run workflow right now, you can see that
6:13:416 hours, 13 minutes, 41 secondswe are kind of storing something in the metadata here, but we are just storing the node ID and we are storing uh the
6:13:506 hours, 13 minutes, 50 secondsstatus right which is useful but we explicitly developed this for the canvas right so in the canvas when a node is
6:13:586 hours, 13 minutes, 58 secondsrunning it appears as loading which is useful for the logs as well but we are missing additional metadata like the duration and the output or the error.
6:14:106 hours, 14 minutes, 10 secondsThose are the things we now want to add to the run workflow. So that's what we described. Right now only a few things are being recorded inside of the run
6:14:186 hours, 14 minutes, 18 secondsworkflow. So there's nothing to show yet. So make each step track everything the console will show which node it is
6:14:276 hours, 14 minutes, 27 secondsso we can display its icon and title its status as it moves from pending to running to done or failed. how long it
6:14:356 hours, 14 minutes, 35 secondstook, whatever it output, and its error if it threw. Basically, exactly what we just described, uh, we need so we can
6:14:446 hours, 14 minutes, 44 secondsproperly develop that console panel. But right now, we're just focusing on adding more things to our run workflow. Once we
6:14:526 hours, 14 minutes, 52 secondshave all of those new things, it's important that we expose all of that run data through our workflow runs provider
6:15:016 hours, 15 minutes, 1 secondbecause I don't know if you remember, but we don't uh ever explicitly directly
6:15:076 hours, 15 minutes, 7 secondsuse the trigger.dev hooks. Instead, we developed the workflow runs provider, which uses the use real-time runs with
6:15:166 hours, 15 minutes, 16 secondstag. And this provider is where we keep track of everything in this value here. Right? So we have available runs here.
6:15:256 hours, 15 minutes, 25 secondsAnd then I believe we also developed use latest run steps in which we uh kind of summarize if a step is live and we
6:15:336 hours, 15 minutes, 33 secondsextract the metadata of those steps. So we also need to make sure that whichever new fields we add inside of the run workflow, we also add to the workflow
6:15:426 hours, 15 minutes, 42 secondsruns provider. So, I think this is a pretty good description of what we need. And we also give it uh a little hint.
6:15:516 hours, 15 minutes, 51 secondsDon't build the UI yet. Just get the data in place. Brilliant. And let's go
6:15:586 hours, 15 minutes, 58 secondsahead and now execute this prompt. Now, let's review the output. Keep in mind that your outcome doesn't need to be
6:16:056 hours, 16 minutes, 5 secondsexact as mine. It doesn't need to be a line for line identical change, but I will show you some of the things you should look out for. So the most obvious
6:16:146 hours, 16 minutes, 14 secondschange should start from the run step because the run step is essentially the type which describes what we are uh
6:16:236 hours, 16 minutes, 23 secondsstoring inside of a metadata of a run step. So previously we only had the status here and node ID which was now
6:16:326 hours, 16 minutes, 32 secondsextended with what we requested. We have a type, we have a title, we have duration in milliseconds, we have an output and we have the error. So if your
6:16:416 hours, 16 minutes, 41 secondsagent didn't do this, it might be a good idea to tell it uh also make sure that our runs output the error. Make sure
6:16:496 hours, 16 minutes, 49 secondsthat our runs output the output or the duration in milliseconds if it forgot to do any of those. And you can validate that simply by looking at the run step
6:16:586 hours, 16 minutes, 58 secondsbecause this is kind of the source of truth. This is the main type of the run step. So if you have anything similar to these, the names doesn't have to be
6:17:066 hours, 17 minutes, 6 secondsexact. It's probably correct. I also have some new imports. So node type from the node registry. So I can give it the
6:17:136 hours, 17 minutes, 13 secondsproper type. So each run step can only be start, open, URL, act, extract, observe, etc. Basically our nodes. Let's
6:17:216 hours, 17 minutes, 21 secondstake a look at the rest of the code here. So now when it iterates over the steps here, besides just getting the
6:17:276 hours, 17 minutes, 27 secondsnode, which was usually enough, it also makes sure to uh explicitly extract the node data type and the node data title.
6:17:376 hours, 17 minutes, 37 secondsSo, previously status was enough with the node ID, but to satisfy the new run step, now it also adds the type and the
6:17:466 hours, 17 minutes, 46 secondstitle. And here's one thing that perhaps your agent didn't do at all. So, my agent decided to save some time and
6:17:536 hours, 17 minutes, 53 secondscreate a helper function called publish steps. So, it replaces having to do metadata set steps every time. It also
6:18:026 hours, 18 minutes, 2 secondscasted steps as unknown as the serialized JSON from trigger.dev core.
6:18:086 hours, 18 minutes, 8 secondsSo this is a very unique thing. I doubt your agent did the exact same thing. But don't be afraid if it didn't. It should work just as well. This isn't required.
6:18:196 hours, 18 minutes, 19 secondsAs I can see, this is just a helper. So it doesn't have to repeat the same thing all the time. So now in all the places where we did metadata set, my agent
6:18:266 hours, 18 minutes, 26 secondsreplaced this new function publish steps. All of this is left unchanged and as you can see every time it does
6:18:336 hours, 18 minutes, 33 secondsmetadata set steps it just calls publish the steps right we change it to running now publish it let's scroll down this is
6:18:406 hours, 18 minutes, 40 secondshow it calculates how long my task my step actually lasts so it develops a new constant started that using date do now
6:18:506 hours, 18 minutes, 50 secondsand then inside of the let's find it here it is uh if it if it catches meaning if it's inside of an error it
6:18:586 hours, 18 minutes, 58 secondsstarts the uh calculation of the duration. So because it failed so we need to calculate date now minus started
6:19:056 hours, 19 minutes, 5 secondsat and it populates duration milliseconds. It populates the error right? That's what we wanted because previously the only thing we populated
6:19:126 hours, 19 minutes, 12 secondswas the status but now we populate the duration the error and we publish the steps in the successful run. Here's what we do. Previously we just did a wait
6:19:226 hours, 19 minutes, 22 secondsexecutor and we stored it inside of an ID in the outputs object. But now we extract the output in its own variable and then we do the same thing as we did
6:19:306 hours, 19 minutes, 30 secondsbefore. We store the output in the ID of the outputs object but we also add it to the step.output so it can be published
6:19:386 hours, 19 minutes, 38 secondsusing the publish steps. So exactly what we described is happening. We are now sending to the front end using the metadata inside of this step the output
6:19:466 hours, 19 minutes, 46 secondsthe duration the error the type the title all of that is what we need. And here we have one more calculation of the duration millisecond. So this one
6:19:546 hours, 19 minutes, 54 secondshappens if uh a step fails and this one happens if it successfully completes and that is the entire change. So it looks like a lot of things have changed but
6:20:026 hours, 20 minutes, 2 secondswhen you dissect it it's actually not that much. Now let's go inside of our run workflows run provider. So in here
6:20:106 hours, 20 minutes, 10 secondswhat I expect is some kind of additional helpers maybe like this. Uh I doubt it's going to be exactly the same and I
6:20:186 hours, 20 minutes, 18 secondspromise you don't have to worry about your code being different because we are going to uh add more prompts to this conversation that we are having. So your
6:20:276 hours, 20 minutes, 27 secondsagent will be aware of the changes it just created. For example, mine created a new hook called use console runs. And
6:20:356 hours, 20 minutes, 35 secondsin here it uses the use workflow runs, extracts the runs and then it goes over the runs, sort them sorts them by
6:20:426 hours, 20 minutes, 42 secondscreated at. So the latest one appears at the top and then uh creates an object with an ID status created that is live
6:20:516 hours, 20 minutes, 51 secondsand steps for a run. Your agent probably achieved something similar, but it doesn't need to be exactly like this,
6:20:596 hours, 20 minutes, 59 secondsright? But you should definitely see some changes in the workflow uh runs provider here. Great. So now let's go to
6:21:066 hours, 21 minutes, 6 secondsthe second step. So now that we've added the necessary outputs to the run a workflow task and we have attached them to our workflow runs provider, let's
6:21:156 hours, 21 minutes, 15 secondsbuild the UI. So build a console panel below the canvas that lists workflow runs every run and below it its steps.
6:21:236 hours, 21 minutes, 23 secondsEach step shows its nodes icon, its title, and how long it took. Format the duration with pretty milliseconds, which is a package we added. A step spins
6:21:326 hours, 21 minutes, 32 secondswhile it's running, turns red if it failed, and looks inactive if it never run. Clicking a step selects it.
6:21:386 hours, 21 minutes, 38 secondsClicking again deselects. The accent colored node icon already exists as node icon instead of the right sidebar. Reuse
6:21:466 hours, 21 minutes, 46 secondsit instead of building another. So if you take a look at the right sidebar component, you will see that in here we actually have a function called node
6:21:546 hours, 21 minutes, 54 secondsicon. And I think it's perfect to reuse for what we need right here. I think I still have the picture open. There we go. You can see that this icon is
6:22:026 hours, 22 minutes, 2 secondsidentical to the one we have in uh both in the step node but also in the right sidebar. Perhaps the one in the right sidebar is even more perfect because
6:22:096 hours, 22 minutes, 9 secondsit's smaller for this. So that's why I'm telling you can go inside of the right sidebar component and reuse that instead of creating a new one. And then I tell
6:22:176 hours, 22 minutes, 17 secondsit build the run list as a logs panel and wrap it in a console panel that owns the selection both new components in the workflow features components folder.
6:22:286 hours, 22 minutes, 28 secondsthen mount the console panel inside of the workflow shell component where it currently shows a logs placeholder. So let's go ahead and simply visit that
6:22:376 hours, 22 minutes, 37 secondsworkflow shell component. So that's the resizable panel that we have right and the only thing we have right now is the text which says logs. So this is the
6:22:456 hours, 22 minutes, 45 secondsplace it needs to populate and develop that console panel and use our new hooks to display the run data inside. So I
6:22:536 hours, 22 minutes, 53 secondsthink this is a pretty good description of what we want and this is how agentic coding is usually done. you focus on the outcome rather than knowing every single little thing that we are going to
6:23:026 hours, 23 minutes, 2 secondsdevelop. Obviously in here I'm kind of nudging it into the name of the components that I want. So both you and I have the same named components because
6:23:106 hours, 23 minutes, 10 secondsin the next prompts that we're going to do, we're probably going to reference those new components. So that's why I'm being very explicit with my naming. But usually when you are doing a gentic
6:23:186 hours, 23 minutes, 18 secondscoding, you wouldn't know the name of the component. You would let the agent name it whatever you want. But because I want to make this easier for you to follow and more deterministic, I'm being
6:23:276 hours, 23 minutes, 27 secondsvery explicit about the name of the components that I want. So once again, you can find all of these prompts inside of the specifications folder in our
6:23:356 hours, 23 minutes, 35 secondsGitHub repository. Just look for uh chapter, this would be 21 console panel.
6:23:406 hours, 23 minutes, 40 secondsAnd let's execute this prompt. After the prompt finishes, the first thing you might see in your app is that all
6:23:476 hours, 23 minutes, 47 secondsexisting workflows are now breaking. And that is expected. In fact, this would have happened if you tried running your app after we run the first prompt. And
6:23:566 hours, 23 minutes, 56 secondsthat is because we fundamentally changed the definition of what step outputs. So if you see this, don't worry. Just go ahead and create a brand new workflow.
6:24:076 hours, 24 minutes, 7 secondsSo first, let's test how this looks visually and then we'll look at the code. So you can compare both your UI
6:24:146 hours, 24 minutes, 14 secondsand functionality and you can compare your code to what my agent did. So the empty panel looks like this. It simply says no runs yet. I'm okay with this.
6:24:246 hours, 24 minutes, 24 secondsAnd what happens when I actually run something? Well, I've uh did that here.
6:24:296 hours, 24 minutes, 29 secondsSo, it displays all of the steps which happened. It also shows that this open URL took 7 seconds, for example. And you
6:24:366 hours, 24 minutes, 36 secondscan see that when I click on it, it stays selected, right? Unless I click again, then it's deselected. One bug I
6:24:436 hours, 24 minutes, 43 secondscan see happening is which I think was actually introduced in our first prompt and that is because I told it to make
6:24:516 hours, 24 minutes, 51 secondssure that all nodes which weren't reached uh display as inactive and the start node is technically never reached
6:24:586 hours, 24 minutes, 58 secondsbecause there's no executor. So maybe you have this bug as well where your start node looks uh disabled. We can fix
6:25:066 hours, 25 minutes, 6 secondsthat later. And let me go ahead and do one more run so you can see how this happens. So right now it's executing.
6:25:126 hours, 25 minutes, 12 secondsYou can see the start and you can see how it's currently spinning the open URL. So this state in the canvas and this state right here are both
6:25:206 hours, 25 minutes, 20 secondssynchronized. And once it finishes, you can see that both of them get in their finished state. So that is the UI and
6:25:276 hours, 25 minutes, 27 secondsthe functionality. And hopefully yours looks somewhat similar to this. And now let's quickly take a peek at the code.
6:25:336 hours, 25 minutes, 33 secondsSo, inside of the workflow shell component, you should now have replaced the previous logs to-do temporary
6:25:416 hours, 25 minutes, 41 secondsparagraph with a proper component called console panel. Now, inside of that console panel, it could be different for
6:25:496 hours, 25 minutes, 49 secondsyou, but here's what my agent did. So, first of all, it's a client component because inside of the console panel, it
6:25:566 hours, 25 minutes, 56 secondsmaintains which step is currently selected. It also developed a toggle function here. Whether yours did this or
6:26:046 hours, 26 minutes, 4 secondsnot doesn't really matter as long as the functionality works. And the only thing it returns is the logs panel. And in
6:26:126 hours, 26 minutes, 12 secondshere, it sends the currently selected node. And it also sends the on selected step, which is the toggle. And then
6:26:196 hours, 26 minutes, 19 secondsinside of the new logs panel, this is where we have all of the functionality uh needed to display each step in a row.
6:26:286 hours, 26 minutes, 28 secondsSo this is mostly just UI and cosmetics about this. So is selected is inactive uh is running which changes to spinner.
6:26:376 hours, 26 minutes, 37 secondsThat's kind of one thing I don't like. I would prefer if is running displayed the spinner in place of the icon but not by
6:26:456 hours, 26 minutes, 45 secondsreplacing the entire component. But it's okay. I want to focus on polishing those things later because for now I just want to focus on the big picture stuff. Okay.
6:26:566 hours, 26 minutes, 56 secondsAnd you should see somewhere in here the pretty milliseconds or pretty ms import from uh the package which we installed.
6:27:046 hours, 27 minutes, 4 secondsAnd in here we have the actual logs panel which uses our hook use console runs. Now whatever your agent modified in the workflow runs provider is
6:27:136 hours, 27 minutes, 13 secondsprobably what it's going to be using here uh to display these runs. But essentially as long as you can see uh
6:27:206 hours, 27 minutes, 20 secondsall of those things which we attached to the run using the step metadata in the run workflow you should now start seeing
6:27:276 hours, 27 minutes, 27 secondshere right so so far we've only had the ID but now we should also have step title step duration step type right
6:27:366 hours, 27 minutes, 36 secondsthing is like that as long as you see that it's probably okay and in here we have some calculated fields like is
6:27:436 hours, 27 minutes, 43 secondsrunning is failed is inactive so that is kind of the general general gist of how this component should look like and I think at this point both you and I
6:27:516 hours, 27 minutes, 51 secondshopefully are getting deterministic changes obviously the UI can vary a bit depending on which agent you're using but because we have such a large code
6:27:596 hours, 27 minutes, 59 secondsbase right now chances are that the agent did this incorrectly because we first started with the run workflow then we modified the workflow provider and
6:28:086 hours, 28 minutes, 8 secondsonly now we are doing the UI so the agent really understands what we are trying to achieve so now let's go ahead and continue to step three so the last
6:28:166 hours, 28 minutes, 16 secondsthing we need is that when we click on a step in the logs panel, some output shows in the other half of that console
6:28:246 hours, 28 minutes, 24 secondspanel. So the workflow console below the canvas which we just developed the console panel.tsx
6:28:326 hours, 28 minutes, 32 secondslists each runs steps and lets you select one. Add an output view showing the selected steps result, its output as
6:28:406 hours, 28 minutes, 40 secondsformatted JSON, its error if it failed, or a short note when there's nothing.
6:28:466 hours, 28 minutes, 46 secondsBuild it as an inspector panel component in the workflow features components folder rendered inside the console panel
6:28:536 hours, 28 minutes, 53 secondsnext to the logs and only while a step is selected. Let's run this. So to test if your agent developed this correctly, go ahead and select any of your steps.
6:29:046 hours, 29 minutes, 4 secondsAnd what you should see now is an inspector panel component which renders a formatted JSON of that nodes output.
6:29:126 hours, 29 minutes, 12 secondsAnd with this inspector panel, I can also debug what's actually happening with my start node because all of them
6:29:186 hours, 29 minutes, 18 secondsappear as inactive. And looks like my uh fear was correct. We have a bug. So because the start node doesn't have an executor, it is never considered done.
6:29:306 hours, 29 minutes, 30 secondsSo I assume this is the fault inside of the run workflow because when we append
6:29:366 hours, 29 minutes, 36 secondsmetadata to these steps, the step without the executor never gets assigned
6:29:446 hours, 29 minutes, 44 secondsas running because we never even reach this whole code block. So that's why it probably always appears as skipped or
6:29:526 hours, 29 minutes, 52 secondsnot yet reached. So let's go through some other bugs that I have. Now you probably don't have the exact same uh
6:30:006 hours, 30 minuteslook or functionality. But as long as you have a panel where you can see your runs and your steps and you can click on
6:30:086 hours, 30 minutes, 8 secondsindividual steps and you can see their outputs, it is good. And now what I'm going to teach you is how I approach
6:30:156 hours, 30 minutes, 15 secondsfixing bugs when a gentic coding doesn't produce something exactly as I imagined.
6:30:216 hours, 30 minutes, 21 secondsSo the first bug I have is this start node being skipped or considered skipped. The second bug I have is when I
6:30:306 hours, 30 minutes, 30 secondsclick run, my spinning node looks like this. But what I would rather prefer is that if it kept this green background
6:30:386 hours, 30 minutes, 38 secondsand then uh if it's spun inside rather than replacing the entire thing. I think it looks prettier. And another kind of a
6:30:466 hours, 30 minutes, 46 secondsbug which I have is that these two components aren't used aren't uh put together using resizable panels like the
6:30:556 hours, 30 minutes, 55 secondsrest of my layout. So I can't resize them. So now I'm going to show you how I would prompt to fix this small little bugs. So if you happen to have any
6:31:036 hours, 31 minutes, 3 secondssimilar bugs, you can follow along. Or if you have some other bugs, in that case you can adapt my prompts to your
6:31:106 hours, 31 minutes, 10 secondsspecific problems. But the overall functionality of what we wanted to achieve in this chapter is officially functional. I would also recommend
6:31:186 hours, 31 minutes, 18 secondstesting this new uh console panel on a more complicated workflow like this one just to see if all nodes are correctly
6:31:266 hours, 31 minutes, 26 secondsrendered here. So you can see how my agent renders all of the steps which are going to happen and keeps them inactive until they are either in progress or
6:31:356 hours, 31 minutes, 35 secondsthey are finished. So this even more shows how this initial start node is a bug because it infinitely appears as
6:31:426 hours, 31 minutes, 42 secondsinactive. But I think this looks super cool especially with how synchronized everything is. And that is because we used our workflow runs provider both in
6:31:516 hours, 31 minutes, 51 secondsthe canvas and in here. And let's quickly take a look at the output. I think this is really cool. And there we
6:31:586 hours, 31 minutes, 58 secondsgo. I can even see uh when it didn't manage to do something. Perfect. So, this is how useful this inspector panel
6:32:066 hours, 32 minutes, 6 secondsis because then you can uh see when something goes wrong. This technically isn't an error. The agent simply didn't
6:32:136 hours, 32 minutes, 13 secondssucceed at what we told it to do. So, perhaps we could capture this success and if it's not true, we could manually throw an error if you think that should
6:32:216 hours, 32 minutes, 21 secondsbe a failed node. But keep in mind that then uh trigger will retry that step which can waste a lot of tokens. So
6:32:296 hours, 32 minutes, 29 secondssometimes maybe the user simply prompted something that makes no sense for for example maybe I forgot completely what I
6:32:366 hours, 32 minutes, 36 secondscan uh see on this page right here and I couldn't extract this. And also make sure to test one invalid node simply to
6:32:446 hours, 32 minutes, 44 secondssee how an error looks like. So I just put invalid URL in here and let's see what happens now. Uh there we go. error
6:32:526 hours, 32 minutes, 52 secondscannot navigate to invalid URL and you can see how when it retries it actually resets the output. So the culprit behind
6:33:006 hours, 33 minutesthe bug in which my start nodes are marked as not run yet is inside of the run workflow. Specifically when we try
6:33:096 hours, 33 minutes, 9 secondsto extract the executor from the node executor I then do if there is no executor simply continue meaning that it
6:33:176 hours, 33 minutes, 17 secondsnever reaches the status of running. We can fix that with a simple prompt. In my run workflow, a node with no executor,
6:33:256 hours, 33 minutes, 25 secondsfor example, the start trigger hits if no executor, continue while still pending. So, it shows as skipped forever and its inspector says it hasn't run.
6:33:356 hours, 33 minutes, 35 secondsInstead of skipping it, mark that step as done and publish before continuing.
6:33:406 hours, 33 minutes, 40 secondsThe trigger does no work and has no output, so it should be read as completed. And the fix was very easy. So
6:33:476 hours, 33 minutes, 47 secondsinstead of immediately continuing, what we now do is we set the steps status to done and we publish the steps and then
6:33:556 hours, 33 minutes, 55 secondswe continue. So if I try running this inside a brand new workflow, hopefully the start step will now appear as
6:34:036 hours, 34 minutes, 3 secondsimmediately executed and we even have the correct uh comment here. This step produced no output. Now I want to fix
6:34:116 hours, 34 minutes, 11 secondsthe running step. So I want to fix how this looks. So what I'm going to tell it to do is to extract node icon from the
6:34:196 hours, 34 minutes, 19 secondsright sidebar component into its own file in the workflows components folder and then update the right sidebar update the logs panel and the new inspector
6:34:286 hours, 34 minutes, 28 secondspanel to all import it from there. Then [snorts] add a new running prop to the node icon which we are now going to extract that shows a spinner inside the
6:34:366 hours, 34 minutes, 36 secondsaccent chip so it preserve the background color in place of the icon and use it in the logs list. So running step spins inside its called chip
6:34:456 hours, 34 minutes, 45 secondsinstead of as a bare spinner which is precisely the issue I have right now. So we've now extracted the component node
6:34:526 hours, 34 minutes, 52 secondsicon from right sidebar into its own node icon component inside of features workflows. And as instructed we now have
6:35:016 hours, 35 minutes, 1 seconda running prop which simply switches the icon for the spinner but preserves the entire uh colored accent background. So,
6:35:106 hours, 35 minutes, 10 secondsif we test it out on a new run, the spinner should now look exactly as in the canvas. The last problem I have is
6:35:176 hours, 35 minutes, 17 secondsthe fact that these two panels aren't resizable. So, the culprit is inside of the console panel because this is where
6:35:256 hours, 35 minutes, 25 secondswe maintain the selected step. So, when a step is selected, all we do is we render a div which renders the inspector
6:35:346 hours, 35 minutes, 34 secondspanel and we maintain 50/50 layout using flex. So now I'm going to prompt to replace this with resizable panels. So
6:35:436 hours, 35 minutes, 43 secondsinside of the console panel component, replace the plain flex split between logs and the inspector with a horizontal
6:35:506 hours, 35 minutes, 50 secondsresizable panel group and the drag handle from our components UI resizable.
6:35:556 hours, 35 minutes, 55 secondsKeep the inspector rendered only while a step is selected. And there we go. I can now resize either my logs panel or my
6:36:046 hours, 36 minutes, 4 secondsinspector panel. And the console panel code now uses resizable components from chats UI. So we established a new
6:36:126 hours, 36 minutes, 12 secondsresizable panel group. And then we render the locks panel inside of one resizable panel and inspector panel
6:36:196 hours, 36 minutes, 19 secondsinside a dynamically rendered other resizable panel. So now let's go ahead and get stage get commit and get push our changes.
Chapter 23: Session Replay
6:36:366 hours, 36 minutes, 36 secondsSo we've now developed the console panel which displays all steps from individual runs. But one thing we cannot use the
6:36:446 hours, 36 minutes, 44 secondsinspector panel for is to review the replay of the entire workflow and that is something that browserbase actually offers under their observability API.
6:36:556 hours, 36 minutes, 55 secondsNow, even though we added browserbased skills in the chapter where we set it up, those skills actually only refer to
6:37:036 hours, 37 minutes, 3 secondsthe browser CLI usage, it doesn't actually refer to API or SDK
6:37:106 hours, 37 minutes, 10 secondsprogrammatic usage of browserbase. So, because of that, what I'd recommend is that you learn your way around
6:37:176 hours, 37 minutes, 17 secondsbrowserbased documentation and go ahead and find their observability right here.
6:37:226 hours, 37 minutes, 22 secondsSo make sure that you have access to the URL of the observability and find specifically session replay as well. So make sure you can find those two uh
6:37:316 hours, 37 minutes, 31 secondsdocumentation pages to let our agent know exactly which documentation it should look for while we build the session replays. Let's go inside of our
6:37:396 hours, 37 minutes, 39 secondsagents.m MD and let's add a new block here. So I'm going to add browserbased observability. Session recordings,
6:37:476 hours, 37 minutes, 47 secondsreplays, live view, and logs come from the core browserbased SDK. And then we name that package not stage hand. Before
6:37:556 hours, 37 minutes, 55 secondsbuilding any observability feature consult browserbas's observability documentation and then I paste the overall the overview of the
6:38:046 hours, 38 minutes, 4 secondsobservability. So that's this URL session replay specifically retrieving a sessions recording as an hls playlist is
6:38:116 hours, 38 minutes, 11 secondsdocumented here and then I pasted the session replay documentation. So when you copy and paste this from my agents MD file, just make sure that the URLs
6:38:206 hours, 38 minutes, 20 secondshaven't changed and that they don't point to 404. And we also just give it some additional info. The retrieval needs the secret API key. So it must be
6:38:286 hours, 38 minutes, 28 secondsproxed server side. This is also an important hint. Given that the session replay API provides us with an HLS
6:38:366 hours, 38 minutes, 36 secondsplaylist, we need to install a dependency called HLS.js.
6:38:416 hours, 38 minutes, 41 secondsSo where do we start developing this feature? Well, the answer is inside of our run workflow task. So, similarly as
6:38:486 hours, 38 minutes, 48 secondsto how we updated uh this longunning task previously for our console panel with all the relevant information like
6:38:566 hours, 38 minutes, 56 secondsnode type, node title, uh status, uh duration and milliseconds error and the
6:39:036 hours, 39 minutes, 3 secondsoutput. We now have to add one more thing to this long running task and that is the session ID every time stage hand
6:39:116 hours, 39 minutes, 11 secondsis initialized. But here's the thing. So far, we've only been adding properties to individual steps, but the session
6:39:216 hours, 39 minutes, 21 secondsreplay is the same for all steps because session replay is tied to the entire workflow, not just for individual steps.
6:39:296 hours, 39 minutes, 29 secondsSo unfortunately, yes, we cannot see a replay of every single step. We cannot just see a replay of open URL. We cannot
6:39:366 hours, 39 minutes, 36 secondssee a replay of only agent node, but we can see a replay of the entire thing and how it went together. So, let's go ahead
6:39:456 hours, 39 minutes, 45 secondsand construct a prompt to modify our run workflow uh to make that work. As always, I've prepared all the prompts
6:39:536 hours, 39 minutes, 53 secondsthat we're going to use in this chapter inside of the chapter 22. You can also find the agents.md. You can find what we
6:40:016 hours, 40 minutes, 1 secondhave to install. So let's first capture the session ID. And let's review this prompt. A run records its steps not but not the browser session that it drove.
6:40:106 hours, 40 minutes, 10 secondsSo there's no way to replay what happened. So inside of our run workflow.ts, capture the browserbased session ID when the run opens its
6:40:186 hours, 40 minutes, 18 secondssession and return it alongside the steps. Then surface that session ID on each run inside of our workflows run
6:40:276 hours, 40 minutes, 27 secondsprovider. So remember that's our data flow. It starts with the run run run workflow longunning tasks and then the
6:40:336 hours, 40 minutes, 33 secondsworkflows run provider uh optimizes it or basically makes the data compatible
6:40:406 hours, 40 minutes, 40 secondswith what we need in our UI so a panel can read it in other words right it only exists once the run has finished the
6:40:496 hours, 40 minutes, 49 secondsrecording lags on the session close so read it from the run's final output not in the live metadata so this part right here is if you remember uh long running
6:40:586 hours, 40 minutes, 58 secondstasks from trigger give us an option to read the data either from the final output or from the live metadata. So we need to uh choose which one we're going
6:41:076 hours, 41 minutes, 7 secondsto use depending on which one is available. But for the session replay, we have to rely on the final output because it's not going to exist during the run because it's not yet finished.
6:41:186 hours, 41 minutes, 18 secondsIt's not yet created. So that's why we explicitly write this. Let's go ahead and run this and let's look at the changes. So the first modification you
6:41:256 hours, 41 minutes, 25 secondsshould have is inside of the run workflow file. So alongside initializing stage hand, we should now also initialize the browserbased session ID.
6:41:356 hours, 41 minutes, 35 secondsAnd then once get stage hand runs and once we initialize it, all we do is we extract the browserbased session ID and
6:41:446 hours, 41 minutes, 44 secondswe store it inside of that new variable we've created, browserbased session ID.
6:41:496 hours, 41 minutes, 49 secondsAnd all we have to do in the end is return it alongside the steps. That's it. That's everything needed modified
6:41:566 hours, 41 minutes, 56 secondsinside of the run workflow and inside of the workflows run provider. Again, it depends how your agent is working with
6:42:046 hours, 42 minutes, 4 secondsthis uh provider. I'm pretty sure agents have various ways of achieving this, but as long as you can now see that your
6:42:136 hours, 42 minutes, 13 secondsyour provider is access accessing the browserbased session ID, everything should be fine. You don't really have to worry about how it's doing that. And it
6:42:216 hours, 42 minutes, 21 secondsdoesn't need to be exactly the same as mine. So here's what how mine did it in this use console runs which it developed
6:42:296 hours, 42 minutes, 29 secondsfor me. It added a new property browserbased session ID. So automatically all of my components which use this hook now have access to the
6:42:366 hours, 42 minutes, 36 secondsbrowserbased session ID and it looks like it generates that using the session ID for run and in here it specifically
6:42:436 hours, 42 minutes, 43 secondsgoes through my run and then through the output. So that's that hint that we gave it right don't look through the live metadata use the final output. So the
6:42:526 hours, 42 minutes, 52 secondsoutput variable in the trigger run is what's finished while the metadata is used uh to see if something is live.
6:43:006 hours, 43 minutesRight? That's why you can see how sometimes we look through metadata and then fall back to output if it doesn't exist. But as long as you can now see
6:43:086 hours, 43 minutes, 8 secondsthe browserbased session ID within your workflow runs provider, it means that it's been added here. Now in the same conversation let's construct the API
6:43:176 hours, 43 minutes, 17 secondsendpoint which is going to serve as a proxy for fetching the HLS playlist because we cannot directly just access
6:43:246 hours, 43 minutes, 24 secondsuh this browserbased session replay. We need to create a proxy from our own server to achieve that. So given a browserbased session ID play back that
6:43:336 hours, 43 minutes, 33 secondssession's recording. Browserbase serves the recording as an HLS playlist and fetching it needs the secret API key. So it has to be proxy server side. add a
6:43:416 hours, 43 minutes, 41 secondsroute at app folder API replays and then dynamic session ID that retrieves the sessions replay playlist through
6:43:496 hours, 43 minutes, 49 secondsbrowserbased SDK and returns it available only to the currently signed in organization that's also why we need to create our own endpoint to make sure
6:43:576 hours, 43 minutes, 57 secondsthat no one can hijack another organization's workflow replay that would be a very big breach our agents.md
6:44:056 hours, 44 minutes, 5 secondsfile which we modified at the beginning of this chapter points to the browserbased documentation for the retrieval API AI. So that's why I told you to add that the recording isn't ready the instant the session closes.
6:44:176 hours, 44 minutes, 17 secondsBrowserbase answers with a not ready status until it is. Have that have the route pass that through and build a session replay component in the workflow
6:44:256 hours, 44 minutes, 25 secondscomponents folder that pulls the route until the playlist is ready and then plays it using new dependency which we've added hls.js. So this prompt is
6:44:346 hours, 44 minutes, 34 secondsboth going to create the API endpoint and a new session replay component which we're going to use to render in the console panel and we also say don't wire
6:44:436 hours, 44 minutes, 43 secondsit into the console yet just get playback working from a session ID.
6:44:486 hours, 44 minutes, 48 secondsOkay, so no wiring of this component yet I just want to see it created because we pointed the agent to our agents.md file.
6:44:566 hours, 44 minutes, 56 secondsYou should now see web fetches to those URLs which we've added. You should now have a new API endpoint under API
6:45:036 hours, 45 minutes, 3 secondsreplace session ID. In here, we import out from clerk not found error from browserbase SDK. And here's one thing
6:45:106 hours, 45 minutes, 10 secondsthat perhaps your agent didn't do. So my agent decided to create a separate lib for browserbase and it's just a simple
6:45:196 hours, 45 minutes, 19 secondsinitialization of browserbase. So I actually saw during its output, it took a look at how live blocks and resend was initialized and it decided, okay, I'm going to do the same for browser base.
6:45:296 hours, 45 minutes, 29 secondsSo if your agent didn't do that and instead it initialized it here in line, it's honestly okay because it's actually
6:45:376 hours, 45 minutes, 37 secondsthe only place where we initialize browser base like that. In our run workflow task, we need to initialize it in a function uh because it needs to be
6:45:466 hours, 45 minutes, 46 secondsuh preserved through the entire task, right? So however your agent decided to add the browserbased SDK in this API
6:45:546 hours, 45 minutes, 54 secondsendpoint is correct. In here I have a small comment about what this actually does. So it's important that this is a get function. We skip the first param
6:46:026 hours, 46 minutes, 2 secondswhich is the request and then we go into the actual params from which we can extract the session ID from its uh URL actually. Then we use clerks out to
6:46:116 hours, 46 minutes, 11 secondsextract the user ID and organization ID and make sure to throw if it's not available. We extract the session ID from the params here and then we simply
6:46:206 hours, 46 minutes, 20 secondsuse the browser vase API to retrieve the replays and then here's how it decided to uh find the exact replay we need. So
6:46:286 hours, 46 minutes, 28 secondsit found the first page if it's not available it through and then it found the playlist itself. Uh I'm guessing
6:46:356 hours, 46 minutes, 35 secondsusing the first page variable from above and then passing the page ID along with the session ID. Then it turned that
6:46:426 hours, 46 minutes, 42 secondsplaylist into text which got us this constant right here. And then all we do is we return that back with content type
6:46:496 hours, 46 minutes, 49 secondsapplication and then this specific uh value inside cache control no store. So I'm assuming this is a mix of knowledge
6:46:586 hours, 46 minutes, 58 secondsof Nex.js and how it's supposed to return things and our agents.m MD which pointed it to uh the documentation page.
6:47:066 hours, 47 minutes, 6 secondsSo if your agent didn't add any headers, perhaps ask it, do we need any headers for the M3U8 HLS playlist and then it
6:47:136 hours, 47 minutes, 13 secondswill maybe add the correct headers, but maybe it can work without headers as well. And I also happen to have a catch error here. And in case it's not found
6:47:216 hours, 47 minutes, 21 secondserror, we simply return this status. So that's how my agent developed the API route. Yours can of course slightly vary, but as long as you can see
6:47:296 hours, 47 minutes, 29 secondsbrowserbased session replace retrieve page and something like this happening, it's probably correct. Now let's go
6:47:376 hours, 47 minutes, 37 secondsinside of the second modification which is a new component called session replay inside of the workflow components. So in
6:47:446 hours, 47 minutes, 44 secondshere what the first thing you should see is that it uses the import from HLS and however you're developed the polling is
6:47:536 hours, 47 minutes, 53 secondsokay. So mine decided to set up a poll interval for every 2 seconds because the uh endpoint which we just developed the
6:48:016 hours, 48 minutes, 1 secondAPI replace session ID might not immediately be available. So when the user renders the session replay uh what
6:48:096 hours, 48 minutes, 9 secondsit's going to do is inside of the use effect here it's going to wait for playlist and I'm guessing this will repeat every two seconds until it
6:48:186 hours, 48 minutes, 18 secondsreaches it. And make sure that you have if you do have that kind of polling, make sure that you have a proper cleanup function like this one. Great. So, we
6:48:276 hours, 48 minutes, 27 secondshave that. We use the HLS library here to attach the media to the video, which I'm guessing is a uh component like this
6:48:366 hours, 48 minutes, 36 secondsone. So, make sure that you just have some kind of component which renders the HLS here. And then perhaps your did the loading status, perhaps it did the error
6:48:446 hours, 48 minutes, 44 secondsstatus, perhaps it did the unsupported status, maybe it didn't. You can slightly nudge it if you want that to appear. Perfect. So you should now have
6:48:536 hours, 48 minutes, 53 secondsat minimum these two changes, new API endpoint and the new component and maybe even a third change if your agent
6:48:596 hours, 48 minutes, 59 secondsdecided to uh separate the browserbased client initialization. So now how do we surface that new session replay component inside of our console
6:49:086 hours, 49 minutes, 8 secondscomponent? Well, my first idea was to have it available in every node that we click on. We cannot really make it only
6:49:176 hours, 49 minutes, 17 secondsavailable for one node because again the replay is for the entire run not just
6:49:246 hours, 49 minutes, 24 secondsfor a single step. Okay. So my idea is to add a dummy node at the bottom called
6:49:346 hours, 49 minutes, 34 secondsreplay. Pretend like it's a step and it's always going to be the last step of any workflow we create. And then once we
6:49:426 hours, 49 minutes, 42 secondsclick on that new step which we're going to create which we're going to kind of mock instead of formatted output or
6:49:496 hours, 49 minutes, 49 secondsformatted error we're just going to render that uh session replay component which renders the video. Right? I think
6:49:566 hours, 49 minutes, 56 secondsthat's a good idea because then it is encapsulated and scoped per run and the UX isn't confusing and every user will
6:50:066 hours, 50 minutes, 6 secondssee that there's like an additional step for every run that they do. And since we're going to name it replay, it's kind of going to make sense. So let's go
6:50:136 hours, 50 minutes, 13 secondsahead and create a prompt for that once again in the same conversation. So your agent has the all the context available.
6:50:196 hours, 50 minutes, 19 secondsEach finished run has a recording. Now let's surface it to the console. So inside of our logs panel component add a
6:50:266 hours, 50 minutes, 26 secondssingle replay row under each run that has a recording. Its session ID is present and the run has finished. So
6:50:336 hours, 50 minutes, 33 secondsthat is the criteria for displaying this this fake step which we are developing.
6:50:386 hours, 50 minutes, 38 secondsIt sits with the step rows and is selectable the same way, but it stands for the whole run, not one step. So, exactly what I was just explaining. This
6:50:476 hours, 50 minutes, 47 secondsreplay step is essentially just a good user experience so that it makes sense for them. Okay, how do I see this runs
6:50:566 hours, 50 minutes, 56 secondsuh uh replay? Obviously, it would have been easier if we had an option to see the replay of an individual step, but
6:51:036 hours, 51 minutes, 3 secondsunfortunately, we don't. So, we have to uh figure out a solution like this.
6:51:076 hours, 51 minutes, 7 secondsSelecting it should play that runs recording in the output panel in the inspector panel. DSX component render
6:51:156 hours, 51 minutes, 15 secondsthe session replay for the run session ID instead of a steps output when the replay row is selected. So exactly what we said we want. When you click on that
6:51:246 hours, 51 minutes, 24 secondsnew row, let's render that new component of ours and not the output or the error.
6:51:296 hours, 51 minutes, 29 secondsThe console currently tracks the selection as run ID plus node ID. That's the console panel extended. So a selection can be either a step or a runs replay with only one active at the time.
6:51:416 hours, 51 minutes, 41 secondsPerfect. That should wrap up this feature. So now go ahead and create a brand new workflow. Remember that every time we do some modifications in the run
6:51:506 hours, 51 minutes, 50 secondsworkflow task since we don't really do backwards compatibility at this point.
6:51:546 hours, 51 minutes, 54 secondsUh perhaps some older uh workflows might have some errors. So you're just going to have to clean those up. But your new workflows shouldn't have any errors at
6:52:026 hours, 52 minutes, 2 secondsall. So go ahead and create something that opens the URL and perhaps maybe calls an agent. Then make sure that you have uh your dev server running and your Nex.js server running and click on run.
6:52:146 hours, 52 minutes, 14 secondsAnd now you should see a brand new step row after the usual nodes which you would expect. This is the replay row
6:52:226 hours, 52 minutes, 22 secondswhose purpose is to load that proxy API route we've just created and then display the HLS video replay of what
6:52:306 hours, 52 minutes, 30 secondsjust happened. And then go ahead and get add, get commit, and get push your changes.
Chapter 24: Billing
6:52:436 hours, 52 minutes, 43 secondsNow, let's learn how to monetize our app using clerk billing. Let's run the following prompt using the clerk billing
6:52:496 hours, 52 minutes, 49 secondsskill. Turn on clerk billing for this app. It's organizationbased, so enable it for organizations and add a
6:52:586 hours, 52 minutes, 58 secondspro plan that orgs can subscribe to. And let's also add a safeguard. This is configuration only. Enable billing and
6:53:076 hours, 53 minutes, 7 secondscreate the plan. Nothing else. Don't write any app code or build a pricing or billing screen yet. We'll do that next.
6:53:166 hours, 53 minutes, 16 secondsSo, with this first prompt, we just want to enable clerk billing and create a pro plan. And we can do that using the clerk
6:53:236 hours, 53 minutes, 23 secondsbilling skill which has access to the clerk CLI. Depending on the agent you have, it might ask you a question about
6:53:316 hours, 53 minutes, 31 secondsthe pro plan. In my previous runs of this prompt when I was just testing it out, it actually didn't ask me and it
6:53:396 hours, 53 minutes, 39 secondssimply set the price to be $20. So, if your agent didn't ask you, that's perfectly fine. If it did, choose any
6:53:476 hours, 53 minutes, 47 secondsamount you think it's fair for this project. Once the agent finishes, you shouldn't see any code changes in your project because this was pure
6:53:556 hours, 53 minutes, 55 secondsconfiguration. So, billing is now enabled for organizations within our project. And a pro organization plan has
6:54:026 hours, 54 minutes, 2 secondsbeen created with a Slug Pro and a $20 per month price. So, if your agent
6:54:096 hours, 54 minutes, 9 secondsfailed to do this, don't worry. You can do that manually by going inside of your project and clerk and head to billing
6:54:176 hours, 54 minutes, 17 secondstab. Since I just enabled billing using the skill, if I refresh, this page is no longer going to show onboarding, but instead it's going to show this. So, if
6:54:266 hours, 54 minutes, 26 secondsthat's what you see, it's configured correctly. Otherwise, go inside of the configure tab, and in here, you will also find billing. Make sure that enable
6:54:356 hours, 54 minutes, 35 secondsorganization billing is selected. From here, you can also manage the plans. The free plan is here automatically. The one you should have added is the pro plan.
6:54:466 hours, 54 minutes, 46 secondsWhat's important here is that the key is pro as this is how you can programmatically reference this plan. The description doesn't really matter.
6:54:546 hours, 54 minutes, 54 secondsMake sure it's publicly available. And then just go ahead and set any price you want. Now, let's build the UI and the
6:55:016 hours, 55 minutes, 1 secondreusable hook, which we can use to tell us whether the current organization is in a pro plan or not. So once again using the clerk billing skill build the
6:55:106 hours, 55 minutes, 10 secondspricing page put it in the app's dashboard route group so it sits inside the dashboard layout. Show the organization plans and let them
6:55:186 hours, 55 minutes, 18 secondssubscribe and check out. We are about to get a few things behind pro. So also add a reusable hook in the workflow features
6:55:266 hours, 55 minutes, 26 secondshooks folder that tells a component whether the active organization is on pro and can send someone to that pricing page to upgrade. You should now have two
6:55:356 hours, 55 minutes, 35 secondsfiles created. The first one being the actual billing page located within the dashboard route group. You can now visit
6:55:436 hours, 55 minutes, 43 secondsthat page by going to localhost 3000 billing. The UI can of course differ depending on the agent that you are using, but as long as you can see the
6:55:526 hours, 55 minutes, 52 secondspricing table being rendered and a prop for organization, it means the implementation is correct. The second
6:55:596 hours, 55 minutes, 59 secondsfile your agent should create is the use pro plan or any similarly named hook which is used to verify whether the
6:56:066 hours, 56 minutes, 6 secondscurrently active organization is subscribed to the pro plan or not. The implementation of this hook can differ,
6:56:146 hours, 56 minutes, 14 secondsbut what's important is that you can find the logic which extracts the has util which we can then use to check for
6:56:216 hours, 56 minutes, 21 secondsthe actual plan property. And we should check for the pro key because that's exactly what we named our plan. So if
6:56:306 hours, 56 minutes, 30 secondsyou gave your plan another key, make sure to add it here. But if you're doing all of this in the same conversation, your agent will be aware of the name of
6:56:396 hours, 56 minutes, 39 secondsyour plan. And if this plan is not active, it should redirect the user to the newly created billing page. Now,
6:56:476 hours, 56 minutes, 47 secondsit's a personal preference whether you want this billing page to be accessible through the sidebar as well. Perhaps your agent already added it here. There
6:56:566 hours, 56 minutes, 56 secondsis another way users can access the billing configuration without visiting this page and that is through the actual organization settings. So, they can now
6:57:056 hours, 57 minutes, 5 secondsfind the billing in here. So that's why I feel like it's not necessary to create an actual sidebar item. Believe it or
6:57:126 hours, 57 minutes, 12 secondsnot, that's everything we need to pretty much progate anything you can think of.
6:57:196 hours, 57 minutes, 19 secondsFor example, how about we make the agent node, our most expensive node, only available to premium organizations.
6:57:286 hours, 57 minutes, 28 secondsLet's try the following prompt. The agent node is our most expensive node, so make it premium. Only organizations
6:57:356 hours, 57 minutes, 35 secondson the pro plan can add it to the canvas. Every other node stays free. So anyone can still build workflows. So I
6:57:436 hours, 57 minutes, 43 secondstell the agent, go inside of the right sidebar where the toolbar lists every node you can add. For a nonpro
6:57:506 hours, 57 minutes, 50 secondsorganization, the agent node shows as locked and clicking it sends them to the upgrade instead of adding it. Use our
6:57:576 hours, 57 minutes, 57 secondsnew pro gate hook. The output should look something like this inside of your toolbar. When you find the agent node,
6:58:056 hours, 58 minutes, 5 secondsyou should have some kind of indicator that it's currently locked for a free organization. So, what my agent did is
6:58:126 hours, 58 minutes, 12 secondsit added a simple lock on the right side. And clicking on the agent doesn't add it to the canvas, but instead redirects me to the billing plan. There
6:58:216 hours, 58 minutes, 21 secondsare many ways your agent could have implemented this. For example, my agent opted for a very simple set of premium
6:58:306 hours, 58 minutes, 30 secondsnodes maintained inside of the right sidebar. Personally, I think it might be more modular to modify our node registry
6:58:396 hours, 58 minutes, 39 secondsand then maintain which of these nodes is premium from here because then we can also get it on the back end. But that is for further discussion with your agent.
6:58:496 hours, 58 minutes, 49 secondsWhat I wanted to show to you is that you can now reliably use Agentic coding with just a very simple setup and a set of
6:58:576 hours, 58 minutes, 57 secondsclerk billing skills. Now go ahead and proceed with the checkout and then go back inside of your canvas. And once you
6:59:056 hours, 59 minutes, 5 secondstry adding the agent node, everything should work fine like it did initially.
6:59:116 hours, 59 minutes, 11 secondsand then verify whether this is actually scoped per organization by switching to another organization and try creating a
6:59:196 hours, 59 minutes, 19 secondsnew workflow. And in here you should see the agent being locked once again unless you go back to the previous organization
6:59:286 hours, 59 minutes, 28 secondsin which you are on the pro plan which makes the agent node available to everyone in the team. Now that you've learned how to protect the agent node,
6:59:376 hours, 59 minutes, 37 secondsyou pretty much have limitless options as to what else you want to monetize with clerk billing. For example, try
6:59:446 hours, 59 minutes, 44 secondsasking your agent to only allow a total of five free workflows for every organization before being prompted to
6:59:536 hours, 59 minutes, 53 secondsupgrade. Or maybe allow an unlimited amount of workflows, but limit every canvas to a certain amount of nodes. Or
7:00:027 hours, 2 secondsmaybe try to find attractive features like session replay and make that only available for premium organizations.
7:00:117 hours, 11 secondsThe only limit is your imagination. And that's the whole point of agentic coding. A combination of being
7:00:187 hours, 18 secondscompletely in control and saving ourselves from doing some tedious work by asking the agent to do it inside of a
7:00:257 hours, 25 secondsstable codebase, which means it's going to produce deterministic results. I would highly advise you to try and experiment and protect some feature
7:00:347 hours, 34 secondsyourself. For example, I really like the idea of a session replay only being available to premium organizations
7:00:427 hours, 42 secondsbecause I feel like that's a premium feature. So, I'm going to try it out using the following prompt. I want to show you one useful trick you can do
7:00:507 hours, 50 secondswith clerk billing. Go inside of your billing tab and find the organization in which you have subscribed to the pro
7:00:567 hours, 56 secondsplan. Usually, it can be a bit tedious testing out if a plan cancels or if it ends. Luckily, Clerk gives you a super
7:01:067 hours, 1 minute, 6 secondssimple end subscription now, which can basically simulate unsubscribing, so you have a clean slate once again and don't
7:01:137 hours, 1 minute, 13 secondshave to create new organizations over and over again. And here's the result of the prompt which I ran. The replay row
7:01:207 hours, 1 minute, 20 secondsnow also has the lock icon. And when I click on it, I'm redirected to the billing page. Here's another idea. So
7:01:277 hours, 1 minute, 27 secondseven though the agent node is technically locked, if I have an older workflow which already has the agent
7:01:357 hours, 1 minute, 35 secondsnodes, I can still run it. So let's create a prompt to fix that. Inside of my actions, stop the run workflow action
7:01:437 hours, 1 minute, 43 secondsfrom running a workflow that contains an agent node unless the organization is on the pro plan. Throw for a nonpro
7:01:517 hours, 1 minute, 51 secondsorganization. do this check in the action not the run task. The action has the clerk session and the has API util.
7:02:007 hours, 2 minutesThe trigger.dev task has no out context.
7:02:047 hours, 2 minutes, 4 secondsUse the clerk billing skill for the plan check. So now even if you try running a workflow from previous session where you
7:02:117 hours, 2 minutes, 11 secondshad access to the agent node, it's going to throw an error. The agent node requires the pro plan. Once you're done monetizing your features, go ahead and stage commit and push your changes.
Chapter 25: Sentry Setup
7:02:297 hours, 2 minutes, 29 secondsIt's time to prepare our app for production. So, let's go ahead and add Sentry to our project. Using the link on
7:02:367 hours, 2 minutes, 36 secondsthe screen, you can get a special offer where you and your team can get Sentry for 3 months completely for free as well
7:02:457 hours, 2 minutes, 45 secondsas 150,000 errors included. Now, let's use Century's Agentic setup. So, instead of
7:02:527 hours, 2 minutes, 52 secondscreating a new project, head into the resources where you can find documentation and up in the toolbar, go
7:03:007 hours, 3 minutesahead and find AI and select the agent plug-in documentation. Now let's run their setup command inside of our
7:03:087 hours, 3 minutes, 8 secondsproject. Now go ahead and choose which coding agent you are using. By default, all three are selected. Cloud code,
7:03:157 hours, 3 minutes, 15 secondscodeex, and cursor. If you want to, you can leave it like this. So whoever in your team uses a different coding agent
7:03:227 hours, 3 minutes, 22 secondswill have the same sentry AI setup. Then go ahead and restart your coding agent or if you're using it within IDE like I
7:03:317 hours, 3 minutes, 31 secondsam, go ahead and reload window. Then confirm that within your coding agent, you now have a bunch of sentry commands
7:03:387 hours, 3 minutes, 38 secondsavailable. For the next step, I'd actually recommend going inside of the command line interface rather than using a graphical interface. Then go ahead and
7:03:477 hours, 3 minutes, 47 secondssearch for MCP servers. Then scroll down until you find plug-in Sentry and then
7:03:547 hours, 3 minutes, 54 secondsselect authenticate. The reason I'm telling you to do this through a command line interface rather than through a graphical interface is because I've had
7:04:027 hours, 4 minutes, 2 secondsseveral unsuccessful attempts at authenticating an MCP server through the graphical interface. But through the command line interface, it worked on the
7:04:117 hours, 4 minutes, 11 secondsfirst try. Make sure that you select all of these options and click approve and then approve once again. Once you've successfully authenticated the Sentry
7:04:197 hours, 4 minutes, 19 secondsMCP, go ahead and run Sentry get started. Since we switched from a graphical interface to the command line
7:04:277 hours, 4 minutes, 27 secondsinterface, we have to manually approve tool use or you can use shift tab to switch to auto mode here. So you can see
7:04:367 hours, 4 minutes, 36 secondsit written in the lower left corner which is the equivalent of what we had in the graphical interface which is going to let cloth code automatically
7:04:437 hours, 4 minutes, 43 secondsapprove tool use. The Sentry agent will now find your team and it's going to look through your projects and it's probably going to ask you to create a
7:04:527 hours, 4 minutes, 52 secondsnew Sentry project. Since it read the browser automation directory name from my codebase, it will probably provide
7:04:597 hours, 4 minutes, 59 secondsyou with the name of your codebase as well. And that's what I'm going to choose browser automation as my new Sentry project name. You should now have
7:05:077 hours, 5 minutes, 7 secondsSentry fully set up in your project. and you should have a brand new project added in your Sentry dashboard. My agent
7:05:157 hours, 5 minutes, 15 secondsalso developed a temporary API Sentry check endpoint and it attempted to throw an error within it. So now if I go
7:05:247 hours, 5 minutes, 24 secondsinside of my issues, I can actually see that error being handled. So from now on, every single error we have in our
7:05:327 hours, 5 minutes, 32 secondsapplication will immediately be monitored in the Sentry dashboard. The actual sentry setup should consist of files like sentry edge config, sentry
7:05:417 hours, 5 minutes, 41 secondsserver config, the global error, a modification to the proxy. So now it includes the monitoring package JSON
7:05:487 hours, 5 minutes, 48 secondswhich includes the sentry package next config which includes the with sentry config with your sentry information and
7:05:577 hours, 5 minutes, 57 secondsyou should also have additional files like instrumentation. For example, go ahead and use a free organization to run
7:06:057 hours, 6 minutes, 5 secondsa workflow which uses premium nodes. As you know, that throws an error in our app which is now actually visible in
7:06:147 hours, 6 minutes, 14 secondsSentry. So every single error that gets thrown will eventually surface in the sentry and you can see the exact stack
7:06:227 hours, 6 minutes, 22 secondstrace exactly what made that error happen helping you debug and categorize whether this is a bug or expected error.
7:06:317 hours, 6 minutes, 31 secondsThis is a pretty good place to create a checkpoint with a commit. Now you can run prompts like this. Add sentry
7:06:387 hours, 6 minutes, 38 secondslogging to all relevant places in our codebase but avoid adding it to the tasks folder as that is run in
7:06:467 hours, 6 minutes, 46 secondstrigger.dev which is a separate environment. We can connect the two later. So essentially what I want now is
7:06:537 hours, 6 minutes, 53 secondsthe sentry agent to go through our entire codebase and to add relevant places to invoke sentry logger. Sentry
7:07:027 hours, 7 minutes, 2 secondslogging is another feature of Sentry as useful as their errors and in fact they go hand in hand together because just
7:07:127 hours, 7 minutes, 12 secondsseeing the error is useful but it would have been more useful if we had proper logs in place which then connect in this
7:07:197 hours, 7 minutes, 19 secondsstack trace and the logs will tell you exactly which user tried something or which team tried something whether the team was on the pro plan on the free
7:07:277 hours, 7 minutes, 27 secondsplan whether they were trying to add an agent node or some other node. So that's what logs are extremely useful for. So
7:07:357 hours, 7 minutes, 35 secondsinstead of adding it to our codebase ourselves, let's just use the agent to do that. So add sentry logging to all relevant places in our codebase, but
7:07:447 hours, 7 minutes, 44 secondsavoid adding it to the tasks simply because that is run inside of trigger.dev, which currently doesn't have access to sentry. So I'm purposely
7:07:527 hours, 7 minutes, 52 secondsleaving it out. With such a simple prompt, we've now improved the logging and monitoring in our app, making it that much safer and ready for
7:08:007 hours, 8 minutesproduction. Let's take a look at the actions file. This is where all of our server actions are developed. A new Sentry import was added. Let's take a
7:08:097 hours, 8 minutes, 9 secondslook at the create workflow action. At the beginning of the action, Sentry is setting the attributes and defining which action this is create workflow
7:08:197 hours, 8 minutes, 19 secondsaction as well as adding the current organization ID to the scope. So every subsequent log which gets monitored will
7:08:277 hours, 8 minutes, 27 secondshave that previous scope as well. Now let's scroll a bit down. Take a look at everything that's being logged. For
7:08:357 hours, 8 minutes, 35 secondsexample, if a user attempts to delete a workflow and it wasn't found, Sentry agent has added a log here. Workflow
7:08:427 hours, 8 minutes, 42 secondsdelete skipped, not found. At first, this doesn't seem like such useful information. But if you start noticing
7:08:507 hours, 8 minutes, 50 secondsthe same ID and an invalid organization ID who doesn't belong in that workflow all the time in your dashboard, it might
7:08:597 hours, 8 minutes, 59 secondsindicate that something is wrong with your with your UI and somehow it's deleting the workflow from another
7:09:067 hours, 9 minutes, 6 secondsorganization. That's why it's so useful to have this types of information because you will see anomalies. Scroll a
7:09:137 hours, 9 minutes, 13 secondsbit down and you will find all kinds of interesting information added. For example, whenever we throw an error that the agent node requires the pro plan, Sentry now warns us about that as well.
7:09:257 hours, 9 minutes, 25 secondsSo, we can see exactly which errors appear more and which appear less. And if you scroll down, you will find even
7:09:337 hours, 9 minutes, 33 secondsmore useful information. And this is just in the actions file. Take a look at our API endpoints. All of them now also
7:09:407 hours, 9 minutes, 40 secondshave the attributes and another useful logging here. Session replay denied pro plan required. So we are basically on
7:09:487 hours, 9 minutes, 48 secondstop of every single thing that's happening. Every time that we successfully uh serve a session replay, we load the exact session ID for which
7:09:577 hours, 9 minutes, 57 secondsorganization on which page count of the browserbased session that was. Now take a look at the live blocks. We did the
7:10:057 hours, 10 minutes, 5 secondssame thing here. If we attempt to authenticate with live blocks with incorrect user ids, we simply throw an
7:10:137 hours, 10 minutes, 13 secondserror here as well. But now we also warn it in Sentry. So every single thing that's happening in your app is now
7:10:217 hours, 10 minutes, 21 secondslogged and you are aware of it. So if you now go ahead and just use your app, you don't even have to do anything
7:10:287 hours, 10 minutes, 28 secondsspecial and then go ahead and revisit your explore logs in here, you will start to notice every single thing
7:10:357 hours, 10 minutes, 35 secondshappening. So, I ran a few workflows, triggered a few errors, and now I'm going to go back to the logs page. Take
7:10:437 hours, 10 minutes, 43 secondsa look at this. You can actually see how your app breeds now. Every single thing that happened, every time a LiveBlocks
7:10:507 hours, 10 minutes, 50 secondsuser was identified or resolved, every time a workflow run was denied, we keep track of everything. Now, let's go ahead
7:10:587 hours, 10 minutes, 58 secondsand stage and commit these changes as well. At this point, we are using Sentry to track some of the most important parts of our app, but we are still not
7:11:077 hours, 11 minutes, 7 secondstracking the actual background run. So, let's go inside of features, tasks, run workflow. It would be great if somehow
7:11:177 hours, 11 minutes, 17 secondswe managed to log every single thing that's happening inside of trigger.dev.
7:11:237 hours, 11 minutes, 23 secondsNow, we have to be careful here because trigger.dev is a separate environment, not in our current Node.js JS or Nex.js
7:11:327 hours, 11 minutes, 32 secondsserver. So how exactly do we connect the two? In that case, go ahead and search for sentry and trigger.dev and that will
7:11:417 hours, 11 minutes, 41 secondstake you to trigger example sentry error tracking. And what you can do here is simply copy the entire page. Then go
7:11:497 hours, 11 minutes, 49 secondsahead and tell your agent to integrate Sentry with Trigger and paste the entire documentation you just found. So what
7:11:577 hours, 11 minutes, 57 secondsshould happen right now is a new dependency being added sentry node and another one called sentry sbu plugin.
7:12:067 hours, 12 minutes, 6 secondsThen you should have a trigger config modified which uses those new dependencies to modify the build
7:12:137 hours, 12 minutes, 13 secondsproperty. Add extensions su plugin and then use the sentry sbu plugin. You should recognize your organization and
7:12:217 hours, 12 minutes, 21 secondsyour project. The only thing we have to obtain is the sentry out token. You should now also find init.ts
7:12:297 hours, 12 minutes, 29 secondsinside of the features. Now, this isn't the best location for it. The reason it put the file here is because inside of
7:12:377 hours, 12 minutes, 37 secondstrigger.dev, if you remember, let me find it. My apologies. Trigger.config.
7:12:427 hours, 12 minutes, 42 secondsWe set the features directory to be the one where trigger is initialized. So, technically, yes, this is correct place
7:12:527 hours, 12 minutes, 52 secondsto put it. But perhaps it would have been better if it's inside of tasks. But for now, it's okay if it's here. And as
7:12:597 hours, 12 minutes, 59 secondsyou can see, we have registered trigger tasks so that every single time a failure happens, we log it to Sentry.
7:13:087 hours, 13 minutes, 8 secondsFor example, an open URL node with an invalid URL is now getting logged to Sentry as well. So every single thing
7:13:167 hours, 13 minutes, 16 secondsthat happens in your trigger run will now be logged in Sentry. So you have one unified place for all of your errors and
7:13:257 hours, 13 minutes, 25 secondsall of your monitoring. To obtain the Sentry out token, go inside of settings, organization, and scroll down until you
7:13:337 hours, 13 minutes, 33 secondsfind organization tokens and go ahead and click create new token. Give this a name, trigger.dev, and then create
7:13:427 hours, 13 minutes, 42 secondstoken. Then go ahead and copy it. And then go inside of your environment.local local and add a new field sentry out
7:13:497 hours, 13 minutes, 49 secondstoken and paste it here. The rest of the environment properties like sentry DSN and node environment already exist in
7:13:577 hours, 13 minutes, 57 secondsyour project. So these are the ones mentioned inside of init.ts which I just mentioned it's awkwardly put in the
7:14:057 hours, 14 minutes, 5 secondsfeatures folder. So the only one we actually have to take care of is inside of the trigger.config which is the
7:14:127 hours, 14 minutes, 12 secondssentry out token. to just make sure you didn't misspell it and that your agent actually uses this environment variable and added it here. It might be a good
7:14:207 hours, 14 minutes, 20 secondsidea to restart your development server and to restart your trigger.dev server.
7:14:257 hours, 14 minutes, 25 secondsNow go ahead and purposely add an invalid URL to the open URL node. This is the easiest way to make this node
7:14:327 hours, 14 minutes, 32 secondsfail. And let's go ahead and run. Now go inside of your trigger.dev dashboard and in your recent run you should see a
7:14:397 hours, 14 minutes, 39 secondsfailing task. cannot navigate to invalid URL. And because we have connected the two, the same error now appears in
7:14:487 hours, 14 minutes, 48 secondsSentry. So you officially have one place with all errors, monitoring, logging, and observability. Now let's go ahead
7:14:567 hours, 14 minutes, 56 secondsand stage and commit our changes. It's been a while since we updated our railway deployment with our newest environment variable keys. So let's make
7:15:057 hours, 15 minutes, 5 secondssure that we copy the latest ones and add them to our railway service. Those will be recent API key, next public
7:15:117 hours, 15 minutes, 11 secondssentry DSN, sentry DSN and sentry AL token. So go inside of variables raw editor and the last one as you can see
7:15:207 hours, 15 minutes, 20 secondsis browserbased API key. So let's simply add resend next public sentry sentry and sentry out token and then deploy. And if
7:15:297 hours, 15 minutes, 29 secondsyou haven't already, make sure that you push your newest changes.
Chapter 26: Polish
7:15:397 hours, 15 minutes, 39 secondsBefore we do the final deployment and officially end this tutorial, let's tie up a few loose ends. So, this empty
7:15:487 hours, 15 minutes, 48 secondspage, no workflow selected, currently doesn't create a new workflow when you click on the button. That's the first
7:15:557 hours, 15 minutes, 55 secondsthing I want to fix. And then the second thing I want to fix is the ability to stop a workflow. So we are able to start
7:16:047 hours, 16 minutes, 4 secondsa workflow by clicking on the run button. But there is actually no way of stopping it. The only thing I can do
7:16:127 hours, 16 minutes, 12 secondsonce I start the run is actually start it again. Instead, this should turn into a stop button and then cancel the run.
7:16:197 hours, 16 minutes, 19 secondsLuckily for us, we already have the cancel workflow run action developed as well as the workflow runs provider which
7:16:277 hours, 16 minutes, 27 secondskeeps track of the latest live run. The run button component is located inside of the right sidebar. So make sure that
7:16:357 hours, 16 minutes, 35 secondsyou can find run button inside. This is where we have to implement that dynamic toggle. Once it's started, it shouldn't
7:16:437 hours, 16 minutes, 43 secondsdisplay run and the play icon, but instead it should say stop and a stop icon. So just make sure you can find this run button component. Let's
7:16:517 hours, 16 minutes, 51 secondsconstruct the following prompt. The run button in our right sidebar component can only start a workflow. There is no
7:16:587 hours, 16 minutes, 58 secondsway to stop one that's running. Make it a toggle. While a run is in flight, it becomes a stop button that cancels that
7:17:077 hours, 17 minutes, 7 secondsrun. And when nothing's running, it's run as before. Then we mention the workflow runs provider and say it
7:17:157 hours, 17 minutes, 15 secondsalready tracks which runs are live. And instead of our workflows actions, we have an action that cancels a run by its ID. At most one run is live at the time.
7:17:277 hours, 17 minutes, 27 secondsLet's go ahead and run this prompt. My agent decided to add a new function use live run inside of the workflow runs
7:17:357 hours, 17 minutes, 35 secondsprovider. It extracts the run and simply finds the exact run which is currently live. Then inside of the right sidebar
7:17:447 hours, 17 minutes, 44 secondscomponent, it found the run button and it uses the new hook to find the live run and dynamically render between stop
7:17:547 hours, 17 minutes, 54 secondswhich calls the cancel workflow run action and leaves the usual one which is run otherwise. So go ahead and construct
7:18:017 hours, 18 minutes, 1 seconda workflow with an agent node and make it search for something. That should give you enough time to test whether
7:18:087 hours, 18 minutes, 8 secondsstopping the workflow actually works. So let's click on run and then let's click on stop.
7:18:167 hours, 18 minutes, 16 secondsOnce you stop inside of your console panel, you should see that it didn't manage to complete open URL one. As you
7:18:247 hours, 18 minutes, 24 secondscan see, this step is now infinitely stuck in waiting to finish. And agent one wasn't even run yet. So we can now
7:18:327 hours, 18 minutes, 32 secondsofficially stop our runs. You can make the stop button look slightly better by using the destructive variant instead of
7:18:407 hours, 18 minutes, 40 secondssecondary one. So let's take a look again. There we go. This looks like a destructive action because it's going to stop the run. And now let's fix our
7:18:487 hours, 18 minutes, 48 secondsempty state. So inside of our dashboard page, the new workflow button in the empty state doesn't do anything yet. Why
7:18:567 hours, 18 minutes, 56 secondsare we to create a workflow? Keep it simple. A direct call to create workflow action inside of our actions. No optimistic update. Give the new workflow
7:19:047 hours, 19 minutes, 4 secondsa generated name the same way the sidebar's new workflow button does. My agent decided to fix this by developing a new client component called new
7:19:137 hours, 19 minutes, 13 secondsworkflow button. So it can leave the actual page component as server component. If your client simply added
7:19:207 hours, 19 minutes, 20 secondsuse client and then developed the entire logic here, that should also work just fine. But for example, my agent created
7:19:287 hours, 19 minutes, 28 secondsa new component, new workflow button in which it uses use transition to call create workflow action with a generate
7:19:367 hours, 19 minutes, 36 secondsslug function. So let's test it out inside of localhost. I'm going to click new workflow. And there we go. We have a
7:19:447 hours, 19 minutes, 44 secondsnew workflow created. Congratulations on implementing the last code change we're going to do in this tutorial. Remember
7:19:517 hours, 19 minutes, 51 secondsto get stage, get commit, and get push your changes.
Chapter 27: Deployment
7:20:027 hours, 20 minutes, 2 secondsNow it's time to do the final deployment configuration to make this application work in production. So first things
7:20:107 hours, 20 minutes, 10 secondsfirst, go inside of your railway service. Go inside of settings and find public networking. If you haven't already, go ahead and generate a domain.
7:20:187 hours, 20 minutes, 18 secondsIf it asks you for a port, put 8080.
7:20:227 hours, 20 minutes, 22 secondsThat should generate you a domain. Now the domain should work as expected with one big problem and that is that every
7:20:317 hours, 20 minutes, 31 secondstime you try to run a workflow it will never actually execute it and instead it
7:20:377 hours, 20 minutes, 37 secondswill simply stay as cued. So go ahead and try and running any workflow. You will see that I can't even stop a
7:20:447 hours, 20 minutes, 44 secondsworkflow right. So obviously something is not working right. What we have to do is we have to follow trigger.dev dev
7:20:527 hours, 20 minutes, 52 secondsdeployment instructions. You can find that under the deployment section and click on the overview. So, first let's go ahead and run the deploy command
7:21:017 hours, 21 minutes, 1 secondwithin our codebase. This deployment will probably fail with errors like these missing API keys. Right now, what
7:21:107 hours, 21 minutes, 10 secondswe have to do is we have to transfer all of our environment variables which are used within our longunning tasks into
7:21:187 hours, 21 minutes, 18 secondsthe trigger cloud platform. So let's go ahead and copy this entire file environment.local
7:21:247 hours, 21 minutes, 24 secondsand then let's go inside of our trigger dashboard. In here you will find the environment variables and go ahead and
7:21:327 hours, 21 minutes, 32 secondsclick add new. You can see that there's a tip. Paste all of your environment variables at once into this form to
7:21:397 hours, 21 minutes, 39 secondspopulate it. There we go. Not all of these are needed, but it's a quick and easy way to add all the ones that you need. So then go ahead and mark this both as development and production.
7:21:507 hours, 21 minutes, 50 secondsObviously you should have different variables for both of those, but since it's just easier to demonstrate how to go to production this way, I'm going to
7:21:597 hours, 21 minutes, 59 secondsuse the same variables for both. And then I'm going to hit save. Once you have all of your environment variables
7:22:067 hours, 22 minutes, 6 secondsstored, go ahead and try running trigger deploy again. Now you should have a successful deployment. So go inside of
7:22:147 hours, 22 minutes, 14 secondsyour trigger dashboard and make sure that you switch your environment to production. Once you are in production, go ahead and scroll down until you find
7:22:247 hours, 22 minutes, 24 secondsAPI keys. And you should see a big label production API keys. Now go ahead and copy this API key. And the place where
7:22:327 hours, 22 minutes, 32 secondsyou're going to add this is in your deployment service. So not here. Do not change the development secret key. This
7:22:407 hours, 22 minutes, 40 secondsneeds to stay as the development environment. but instead you need to change one variable inside of your raw
7:22:487 hours, 22 minutes, 48 secondseditor here. So go ahead and find the trigger secret key and replace it with a production one. Click update variables
7:22:557 hours, 22 minutes, 55 secondsand deploy. Once you have a successful redeployment, go ahead and refresh your live URL and then attempt to run the app
7:23:057 hours, 23 minutes, 5 secondsagain. And this time you should see live feedback and actual execution happening.
7:23:117 hours, 23 minutes, 11 secondsAnd if you go inside of your uh trigger dashboard in the tasks or runs, you
7:23:187 hours, 23 minutes, 18 secondsshould also see your first production run being executed. Amazing. Amazing job and congratulations on your official deployment of this project.
Chapter 28: The End
7:23:367 hours, 23 minutes, 36 secondsIt's been an absolute pleasure building this project with you and I hope you had as much fun as I did. If you have any
7:23:437 hours, 23 minutes, 43 secondsfeedback or recommendations about what I should teach you how to build next, feel free to leave a comment below. And if you like the video, remember to leave a
7:23:517 hours, 23 minutes, 51 secondslike and subscribe. See you in the next tutorial.

Sync to video time
