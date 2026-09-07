https://www.youtube.com/watch?v=ou4t9Q7En5w



MERN AI Coding SaaS App with Node.js & React - GitHub, Bash, Sandbox, Command Code | Full Course
TechWithEmma
TechWithEmma
12.8k subscribers

Join

Subscribe

155


Share

Ask

Save

3,565 views  5 Jun 2026
🟢 Try Command Code (the coding agent that learns your taste): https://commandcode.ai/?utm_source=yo...

⭐ Become a Master in Full-Stack development: https://scrimba.com/fullstack-path-c0... 
💻 Source Code (Give a Star ⭐): https://github.com/TechWithEmmaYT/MER...

In this video, we build & deploy a MERN AI Coding SaaS App Agent from scratch,  where you can connect a GitHub account, fetch repositories, stream real-time AI responses, and run code inside isolated sandboxes.
With tools like Git, commit, push, Bash execution, file editing, writing, pull requests, a web search tool, and more
We will use Node.js, React, Next.js, MongoDB,  Command Code, Upstash Box, AI SDK, and Render

📢 Stay Connected:
🙏  Subscribe to the Channel: https://tinyurl.com/subcribe-to-techw...
💻 Join our Discord Community:   / discord  
🐦 Follow us on Twitter:  https://x.com/techwithemma

🗝️ Key Features:
🔐 Authentication
🔗 Connect GitHub repositories
🧱 Isolated sandbox execution environment
⚡ Real-time streaming responses
📝 File read, write, and edit tools
💻 Bash command tools
🌿 Git tools (status, commit, push)
🌎 Web search tool
🔀 Create pull request
🧠 AI Models
🌐  Built with MERN Stack (MongoDB, Express, React, Node.js)
🎨 Modern UI with Tailwind CSS & Shadcn UI
🚀 Production-ready deployment


⏲️ Timestamps 👇
00:00:00 - Intro & Demo
00:06:15 - Project & Command Code Setup
00:34:40- MongoDB Setup
00:41:05 - Models
01:03:20 - Authentication
01:23:14 - GitHub Connect & APIs
02:15:38 - SandBox Setup
02:25:17 - Session APIs & Tools
04:24:34 - Frontend Setup
04:38:25 - Frontend Routes & SideBar
05:02:42 - Frontend Auth Page
05:17:03 - Frontend Session List & Pull Request
05:32:42 - Frontend Chat Interface
07:13:30 - Frontend Single Session
07:32:14 - Deployment


🟢 Try Command Code (Learn the way you code): https://commandcode.ai/?utm_source=yo...

📚 Resources:
http://upstash.com/docs/box
https://dashboard.render.com
https://ai-sdk.dev
https://elements.ai-sdk.dev
https://cloud.mongodb.com

Skip this:
5 Essential Tools Every MERN Developer Needs for AI Finance
node authentication
node authentication passport
Ask



------------------------------------------------------------------------
In this video


Chapters

Transcript
Search transcript
Search transcript

Chapter 1: Intro & Demo
0:000 secondsWhat if you could build an AI agent in monster from scratch? Today you'll build a main AI coding agent where users can
0:066 secondsconnect GitHub repository, stream AI response in real time, use sandbox to run command, support tools like git,
0:1414 secondsbadge, edit, write and create pull requests. We'll be using NodeJS, MongoDB, React, render, and command
0:2121 secondscode. Command code is an AI coding CLA that supports all models including open-source model like dips v4 pro. One feature I really like in command code is
0:3030 secondscalled test. It learn exactly how you write code and how you structure your project. So I already have a test profile push into command code for
0:3838 secondsscaffolding my NodeJS architecture which I've set to public and I already have the test profile pulled into an empty folder. So with just a simple prompt
0:4646 secondslike scaffold in NodeJS project command code read the test profile and automatically set up the project structure install the packages and
0:5454 secondsconfigure everything the way I like to code. And the model I use here is D6 V4 Pro which is extremely cheap compared to a lot of top tier model right now.
1:031 minute, 3 secondsCommand code start at just $1 a month with $10 in credit and access to models like D6 V4 Pro and more. Try Command Code using the first link in the
1:121 minute, 12 secondsdescription. Now let's see how the AMN project work. Once you land on the app, you can either sign up or sign in. So I'm going to sign into my account. And
1:201 minute, 20 secondsonce I click on the sign in button, it's going to take me to the application. And there at the top left corner, you can see the list of session. And I can click
1:281 minute, 28 secondson this session. And you can see some of the chat I've asked with the AI agent.
1:351 minute, 35 secondsAnd below here, you can see the I selected a repository. and currently is disabled because you only have to select one repository for one session. So to
1:451 minute, 45 secondscreate a new session, we can click on the plus button here and this is going to take us to this page and you have to
1:521 minute, 52 secondsselect a repository. I'll just pick this repo and I can ask the AI a repository.
1:581 minute, 58 secondsWe are going to clone the repo and the AI agent is going to pull the repo inside the sandbox. So I'm going to say
2:052 minutes, 5 secondslist the file in this project and click on send. And now you can see
2:122 minutes, 12 secondsthis is going to generate the title and also this is going to add this. You can see now it has generated the title and
2:202 minutes, 20 secondsyou can see uh the name of the title here and currently we have only the readme in this project and you can see the readme has been listed out here. So
2:292 minutes, 29 secondsand you can see the branch has already been generated. Currently the PR now is disabled because they've not make any push. So I can ask the agent to create
2:382 minutes, 38 secondslet's say a landing page. So create a react app.
2:462 minutes, 46 secondsSo I'll say create a simple landing page using V react and CSS. So I click concern and then this is going to go ahead and check the files like I said.
2:552 minutes, 55 secondsSo it's going to install V react and also the CSS. So currently you can see that it is thinking. So it has to touch
3:033 minutes, 3 secondstrue. Now you can see it's um creating the V react app and now it's going to install demo CSS and you can see it has
3:123 minutes, 12 secondsdone that. So now it's you can see it's running this batch too and currently it's installing. So it's currently working and now let's wait for it.
3:243 minutes, 24 secondsSo now you can see it has installed this packages and
3:323 minutes, 32 secondsso now it's going to so it's writing the table config.json it has modified the index CS and it's writing the app jxs.
3:453 minutes, 45 secondsSo now you can see it has updated the packet addressing so it has run build.
3:503 minutes, 50 secondsSo now it want to install and now it's modifying the post CSS or
3:573 minutes, 57 secondsJSON and now we can see that it has build that's one build. So you can see now it has succeeded and has um returned
4:064 minutes, 6 secondsthe status it has commit changes and now it has push uh it has pushed and you can see the button now the pure button is
4:144 minutes, 14 secondsenabled and it's telling us what it has done. You can see that's done everything. So once you it push you can
4:224 minutes, 22 secondsclick here to create PL. You can click on this link to see the changes. So click on this link and you can see it has pushed. So go ahead and click on
4:314 minutes, 31 secondscreate PL. So let me click on this button. And this is going to go ahead and create P for us.
4:384 minutes, 38 secondsAnd it has created a P. So I can click on this button to view the P. And there we can see it has created the P for us.
4:444 minutes, 44 secondsI can ask the agent to make changes here. So I can say um change this content.
4:524 minutes, 52 secondsSo this content was I copied it from the from the app yourjx file and I wanted to edit it and just um replace it with this
5:005 minutescontent here this text. So I'll click on send now and it's going to go and find this um this content here. It's going to
5:095 minutes, 9 secondscopy it from the app.js. So it's going to sit inside the app.js. So currently you can see it's editing app.js. JSS
5:175 minutes, 17 secondsand and now you can see that it has uh updates the content and now it's going
5:245 minutes, 24 secondsto build commit changes and it's going to push to this repo and now we can see
5:315 minutes, 31 secondsum you can click here to a lot of you have been asking how to get started with full start development or how I learn to build project like this. One platform I
5:395 minutes, 39 secondsrecommend is Scream. What makes Scream different is the interactive screen format. Instead of only watching video, the video and code editor are combined
5:475 minutes, 47 secondstogether. So you can edit the code directly inside the lesson. For example, I can pause the lesson, change the code, and instantly see the result in the
5:545 minutes, 54 secondsbuilt-in browser without switching editors. They also have a lot of free courses, but their pipeline gives you full access to all parts certificates,
6:036 minutes, 3 secondscoding challenges, AI feedback, and their developer community on Discord with over 70,000 developers. Check out screen for free today and upgrade to pro
6:126 minutes, 12 secondsusing my link in the description which gives you 20% off. So I've created two folders here have the back end and the client folder. So let me quickly open my terminal and navigate into the back end.
Chapter 2: Project & Command Code Setup
6:236 minutes, 23 secondsSo I'm already in the back end folder the path. So let's do mpm in ity
6:326 minutes, 32 secondsand this is going to create the initialize mpn. So now we have um if you go into the back end we should see the
6:406 minutes, 40 secondspacket JSON and there you can see base AI coding. So we have this now. So what we going to do let's quickly create nodemon here say nodemon dot json.
6:536 minutes, 53 secondsSo we're going to use nodemon to run the server. So let's make sure to install it to npm and we going to also um we're
7:017 minutes, 1 secondgoing to set up tsop. So tsop we're going to use it to build the project. So we need to create an TSO
7:097 minutes, 9 secondstsubconig.txt here. So let's install this um dev
7:177 minutes, 17 secondsdependency first. So let's say mpm install. So this is /d and we're going to say nodemon
7:267 minutes, 26 secondsand yes. So we need to even install um typescript. So let's say TypeScript and also TS TS node for the dev server.
7:387 minutes, 38 secondsSo let's just install all of this. I'll click on enter and I'm going to wait for this to install. So we're going to see
7:457 minutes, 45 secondsthe version I'm using. If once it has installed so let me wait for this. So it has already installed. So I'll go into
7:527 minutes, 52 secondsthe package JSON. You should see nodemon ts node ts up and um typescript. So
7:597 minutes, 59 secondslet's go into let's start with the node first. So I'm going to um paste this here. So what I want is nodemon to watch
8:088 minutes, 8 secondsthe source directory. So we're going to create a source directory. We going to ignore the this folder and the node module and we're going to target
8:168 minutes, 16 secondsextension tx. So then we're going to execute cs node transparent only and we're going to point to the path
8:238 minutes, 23 secondsindex.tx. So this is the entry file inside the src folder. Then inside the
8:308 minutes, 30 secondsts we are going to um I'm going to paste it. So also I'm going to also create ts
8:378 minutes, 37 secondsconfig. So I should not forget that ts config.json like this. So so let's continue with ts.
8:468 minutes, 46 secondsSo I'm going to paste in. So I'm going to paste it here. And now you should see that this um import define config. So
8:538 minutes, 53 secondswe're going to entry file the entry path src index tx which we're going to do format a common j um out directory. This
9:029 minutes, 2 secondsis going to be the this folder and others here. So we going to also have the ts um config.json. So I'm going to
9:109 minutes, 10 secondsquickly paste that too. So let me quickly paste that here. Now you can see I have this compiler options here.
9:179 minutes, 17 secondstarget 2021 module. We're using common JS source and the roots directory which is the src folder and then our directory
9:259 minutes, 25 secondsthis folder and this is going to include some of the um we're going to add in the src and exclude uh the node module and
9:339 minutes, 33 secondsthis folder. So we have this now um we can go into the package and let's clear out the script. So I'm going to clear
9:409 minutes, 40 secondsthis out and I'm going to we're going to have the dev and the dev is going to point to the nodemon since we have defined nodemon config here. Then we're
9:499 minutes, 49 secondsgoing to also have the build script and the build command and also the start. So we can just I'll just paste this here.
9:579 minutes, 57 secondsSo um the build is going to use ts which we've installed. It's going to point to index.tx and we're going to set format
10:0410 minutes, 4 secondscgs to this. And then we're going to copy the packet address into the this folder. So to want to start the um
10:1110 minutes, 11 secondsserver after you've built the project, we going to use node this / index.jx.
10:1710 minutes, 17 secondsSo now we have uh we've set up the basic um so let's just quickly create s here.
10:2410 minutes, 24 secondsAnd now we have all of this here and we have the nodemon the packet ts config
10:3110 minutes, 31 secondsand ts. So now I'm going to show let me quickly save this guys.
10:3710 minutes, 37 secondsSo I'm going to show you um how to use command code to we're going to use command code to set up the project. So
10:4510 minutes, 45 secondsthis is going to quickly help me to and it can help you to quickly set up a NodeJS project. So I've used this I've used command code to um I've used
10:5410 minutes, 54 secondscommand code to um work. So it has understand the way I structure my NodeJS project and it's going to quickly help
11:0111 minutes, 1 secondme to scaffold a NodeJS project. So let's head over to the browser to command code. So just click the link in the description and just come over to
11:0911 minutes, 9 secondscommand code and make sure to um to install it just copy this command and install it in your terminal. So let's go back and install it. So I've already
11:1811 minutes, 18 secondsinstalled it already. So if I open my terminal and I paste it, I can also reinstall it again. And this is going to install globally. And we should wait for this to install. So let's wait for it.
11:2911 minutes, 29 secondsSo now you should see that it has already installed. So let's go back to the browser and make sure to quickly sign up. Um so
11:3611 minutes, 36 secondsI've already signed up. So I'm going to log into my account. And you can see that I've already used the amount of you can see total cost I've used out of $100
11:4511 minutes, 45 secondsand you can see token I've used to total run. So you can click here. Um you can scroll down here. So after you run
11:5311 minutes, 53 secondscommand code you can log in and then you can start the chat the CLI. So I'm going to show you guys we can click here to go
12:0012 minutesto the documentation and there we can just go down to see I think this um same thing here. So you can just come over to the doc and just read about it.
12:1012 minutes, 10 secondsSo, but we can just click on quick start here and this is going to also show you how to log in and um use the CL. So, you can see um how to run your first prompt.
12:2012 minutes, 20 secondsThis MD file is going to be created once you send in your first point with command code. So, test is going to continuously learn from you how you code
12:2912 minutes, 29 secondsand how you structure your code. So, you can see it here. It says continuously learn which package manager you use, which library you prefer and how you
12:3712 minutes, 37 secondsstructure your code. So, and this is going to continuously learn from you.
12:4112 minutes, 41 secondsSo, you don't need to touch on the test MD file. And once you're done with your project, you can push this um to command
12:4912 minutes, 49 secondscode, you can share to anyone simply like the way Git work. So, if I go to command codes and the command code if I
12:5612 minutes, 56 secondsgo to test um you can see some of the uh test that I've already pushed. So, we
13:0413 minutes, 4 secondscan see I have three. I have um just this is um Node.js. This is React and this is so NodeJS2. So I have two NodeJS
13:1113 minutes, 11 secondshere. So I've made them public and this is going to be available for you to pull. So I'm going to pick let's pick
13:1713 minutes, 17 secondsthis one. And if I go into this test, we can see that I have two files. I have
13:2413 minutes, 24 secondsthe node.js node.js and scaffolding. And this is the test MD file. And if I go back now, we also have another test MD.
13:3413 minutes, 34 secondsWe can see all resource scaffolding. and um NodeJS um scaff is pointing to the NodeJS
13:4213 minutes, 42 secondsfolder. Yeah. So we can come over here on how to install this. So we can use MPX um the test CLI. So we can use uh we
13:5113 minutes, 51 secondscan pull this or we can use command code to pull this. So I'm going to copy this now and we going to pull this inside
13:5813 minutes, 58 secondscommand code. So let's go um to let's go back to the code and let me open my terminal.
14:0814 minutes, 8 secondsAnd there we can see that we can we've already install command code. So we can um initialize command code in this
14:1714 minutes, 17 secondsfolder that like the um the roots directory we have here or you can move it. You can do that inside the back end folder. So I'm I'm not going to do it
14:2614 minutes, 26 secondsinside the backend folder. The um the test we just copied I did it inside the back end folder. So
14:3314 minutes, 33 secondsand also the client was inside client folder. So I'm going to just do it inside the wood directory here. So I'm just going to say so you can just type in cmd and this is going to run the CLI.
14:4414 minutes, 44 secondsSince I'm using window, I'm going to just type command code here.
14:4814 minutes, 48 secondsCommand dash code. And I'm going to click on enter. And this is going to initialize command code. So once you run this and you've not logged in, it's
14:5614 minutes, 56 secondsgoing to ask you to login. Like I said earlier on, I've already signed up and I've already lo and you can see that the command code folder has been created and
15:0515 minutes, 5 secondsyou can see okay the test folder has been created. If I click on test MD you can see that it has already created this folder now. So um we can pull this now.
15:1615 minutes, 16 secondsSo what I'm going to I'm going to open a new terminal and
15:2315 minutes, 23 secondslet me open a new terminal here and I can paste this here. So this is going to pull this. So instead of using cmd I'm
15:3015 minutes, 30 secondsgoing to use command code and I'm going to click on enter and this
15:3915 minutes, 39 secondsis going to pull this and you should see it inside this test. Now you can see we have no joding and we have the other
15:4815 minutes, 48 secondstest md file. Now if I come over here now we can look at how we can change the model. So let's click here and change
15:5615 minutes, 56 secondsmodel. So I can click on model. I can pick let's say open. Let's pick deep V4 V4 Pro. We can also pick Kim 2.6. So it
16:0616 minutes, 6 secondsdepends on the one you want. Let me just go with the default. Uh let me let me pick.
16:1316 minutes, 13 secondsSo we can also click here um slash and you can see some of the commands we have here. We can see learn you can learn
16:2116 minutes, 21 secondslearn this command is going to learn from other coding agent and we have login log out we have memories plan
16:2916 minutes, 29 secondspre-commit we have rename resume rewind and we have also skills then we also
16:3716 minutes, 37 secondshave um skills then then let me go up we have MCP servers
16:4616 minutes, 46 secondstoo and here you can just initialize an agent to MD file and we also have
16:5316 minutes, 53 secondsthey also have design. So you can click on design and then you can use some of this command here. So let's just um
17:0217 minutes, 2 secondslet's go ahead and and ask command code to scaffold the project inside this backend folder. So I'm just going to say
17:1117 minutes, 11 secondsscaffold nodejs nodejs project
17:2017 minutes, 20 secondsand I'm going to point to the back end folder to the back end directory and it's going to go ahead and first of all
17:2717 minutes, 27 secondsread the test uh the test md files inside this on command code and let's click on enter and let's wait for it.
17:3717 minutes, 37 secondsSo it's going to first for read it. Then it's going to go ahead and read this um back end folder. So you can see it has found seven items, two directory and
17:4517 minutes, 45 secondsfile and five files. And then let's wait for it. So it's going to start creating this folder. This t I usually create my
17:5317 minutes, 53 secondsown. So let's wait for it.
18:0918 minutes, 9 secondsSo now you can see that it has created the to-do and you can see that it's created it is structuring the to-do. You can see to do we have the folder structure controller service model route
18:1818 minutes, 18 secondstype validator config and middleware and if you've watched my video you know this is how I usually um I just structure my
18:2618 minutes, 26 secondscode and you can see npm package we have express it's going to install all this package um cookie pry
18:3418 minutes, 34 secondsjust nx sword helmet all of this going to add it then it's going to add the app
18:4118 minutes, 41 secondsthe app error ts get env tx and brick uh brick crypt.tx async handler middle async handler and
18:5018 minutes, 50 secondserror handler and it's going to create an error. So we can let me just click on yes.
18:5818 minutes, 58 secondsSo in order for it not to always accept I'm going to just use shift tab and this is going to accept any it's not going to
19:0519 minutes, 5 secondsask me again. So it's going to continue running. So it's it's installing the package. So we're going
19:1319 minutes, 13 secondsto wait for it. So now it's installing the dev dependency. You can see and type express type course type
19:2319 minutes, 23 secondsand brick jx. So let's wait for it. So now I started to create the app error.x
19:3019 minutes, 30 secondsand let me come to here. Now you should see the folder structure. This exactly how I usually create my folders
19:3819 minutes, 38 secondshow structure my nodejs project. And this is so beautiful to see. So u let's
19:4519 minutes, 45 secondsgo into so it does not I think it has created the utilities. So if I go to app error now you can see. So let me not close this. I'll just collapse this.
19:5819 minutes, 58 secondsYou should see we have the app error extending from error. So I'm going to go over this. So you should not worry.
20:0420 minutes, 4 secondsLet's wait for it to finish and I'm going to go I'm going to go through each files.
20:1320 minutes, 13 secondsSo it's almost done. So it is just running the server and let's wait for it.
20:2120 minutes, 21 secondsSo let's wait.
20:2420 minutes, 24 secondsSo now you can see that it is done. So if you scroll up now we can see what it did. So I've created so the NS back end stuff which is complete. So we have the
20:3320 minutes, 33 secondsconfig controller route middleware utils and model service validator and index
20:4020 minutes, 40 secondsand this is the package installed. Then created and health apex
20:4820 minutes, 48 secondsbut at least it did it right. So we also have the so it has compiled to verify the server is working. So use port 4,000
20:5620 minutes, 56 secondssetup config and um cause config and error handling. So it added this Z error
21:0421 minutes, 4 secondsfor since we're going to be using Z for validation and it also added the um app error. So no database config. So okay,
21:1121 minutes, 11 secondsthis is so let's just close this and let me go into all the files. So we can just so inside the back end folder. So the first thing I'm going to do is the EMV.
21:2021 minutes, 20 secondsSo it's created this EMV. So, I'm going to change this from to 8,000.
21:2521 minutes, 25 secondsSorry. Yeah, 8,000. Then I'm going to change this uh I don't want to use I love using front end um front end
21:3621 minutes, 36 secondsorigin. This is fine. Uh front end origin, we're going to change this later on since we're going to be using V not.
21:4421 minutes, 44 secondsSo inside the LRC folder. So the first thing we're going to see is so if you click on YouTube click on get EMV. So
21:5321 minutes, 53 secondsthis um get EMV you can see that it has imported ported EMV/config and create this function. So this is
22:0122 minutes, 1 secondgoing to help us to get the EMV and if the EMV is not passed it's going to throw an error unless you pass in a default value.
22:0922 minutes, 9 secondsAnd u so this envig um inside the config folder envig
22:1922 minutes, 19 secondsand here you can see that the env get env was used. We have the node env.
22:2622 minutes, 26 secondsAnd let me change this to front end origin like I did here. So I will go into config env config. I'm
22:3522 minutes, 35 secondsgoing to replace this with this and replace this with this and let me save this. So I will set here
22:4322 minutes, 43 secondsdefault to 8,0002. So now we have MV config. So let's check HTTP config. So now I think it made a mistake here. This is not exactly what I want to be here.
22:5522 minutes, 55 secondsSo let me ask it to move this course into the index.tx.
23:0023 minutesSo it should move it there and also the health route. So I'm going to say uh I will just point to so use the add
23:0923 minutes, 9 secondscommand to point to the file. So I'll say http config. So
23:1523 minutes, 15 secondsso um this should I'll say this should be
23:2423 minutes, 24 secondshttp status. So here is statusconfig not status move
23:3423 minutes, 34 secondsthe course and the health API in the index.
23:4323 minutes, 43 secondsSo I'm going to click on enter.
23:4823 minutes, 48 secondsSo if you look at it, you can see that the test is going to continuously from us as we accept or ask it to make
23:5523 minutes, 55 secondschanges. So yeah, I've already set it to accept edit on. If we switch tab now, you can change this to plan mode and you
24:0224 minutes, 2 secondscan remove this and this is going to um once you need to make changes is going to allow alert us. So I'm going to change it back to accept.
24:1324 minutes, 13 secondsSo let's wait for it. So it's searching for the file.
24:2624 minutes, 26 secondsSo it hased this um http config.tx and it should create the http status.config.tx instead.
24:4224 minutes, 42 secondsSo if I go into http status now you can see that it has updated it. Now, this is exactly what I want. So, I forgot to add in the type. So, let me quickly add in
24:5124 minutes, 51 secondsthe type. So, I'm going to paste it here. So, I'm going to change this um to HTTP
24:5824 minutes, 58 secondsstatus like this. And I'm going to make this I'm going to say export. This is fine.
25:0825 minutes, 8 secondsSo, let's check this. So, it is done with it. So, it has removed the healthc controller and it has removed the hp
25:1525 minutes, 15 secondsconfig. So I think it did well. So um we can copy this now and let's go into the index.tx
25:2225 minutes, 22 secondsand let's okay we can see the um the health route. So it has added the health. Yeah.
25:3425 minutes, 34 secondsSo so let's continue from where I stop.
25:3725 minutes, 37 secondsSo inside this HTP config. So we've already seen how it should be. So after this we're going to have the middle. So
25:4525 minutes, 45 secondsthe first we're going to have the async handler. So this is just wrap.
25:5025 minutes, 50 secondsSo I think it should have wrapped this with Okay, you can see it uses um um catch next here. So you can use try
25:5925 minutes, 59 secondscache too if you prefer to use that. So let me quickly update this. So this is fine, but I'm going to be using try
26:0726 minutes, 7 secondscatch instead. So I'm going to just paste this here. And this is exactly how it um I should I love to do my so um the
26:1626 minutes, 16 secondsasync handler is going to is going to um be created here to wrap all the controllers. So this is going to help us
26:2326 minutes, 23 secondsto catch any error and send it to the next middleware. So and the next middleware is going to be the handler.
26:3126 minutes, 31 secondsSo inside the error handler you can see that it did absolutely well. Yeah. So we have this function to catch um to handle
26:3926 minutes, 39 secondsZ error. So you can see imported it from Z and then we have the error handler here is where you can see it return um
26:4826 minutes, 48 secondsthe status. So here we can change this to HTTP HTTP status let's say bad request
26:5726 minutes, 57 secondsand you can see the error code. So the error code we can use the error code.
27:0327 minutes, 3 secondsSo let me do error code dot um so you didn't add it inside here. We can
27:1027 minutes, 10 secondsyou can we can later add it too. So we have the app error and this is the internal server um error. So inside the
27:1927 minutes, 19 secondsapp error if you go into YouTube go into app error you can see the custom error here and here you can see the error
27:2827 minutes, 28 secondscode. So we can quickly add that validation here. So I'll say error validation and I'm going to come into
27:3427 minutes, 34 secondsapp error and I can just add it here and pass it here and you can see error
27:4227 minutes, 42 secondscode type is used here and we have the status code number. So the status code I
27:4927 minutes, 49 secondscan use. So let me put it back here. So this is going to be pass here. So here I'm going to use the HTTP enter. So let
27:5727 minutes, 57 secondsme import HTTP status and then we can also change this two. So I say HTTP.
28:0528 minutes, 5 secondsSo instead of uh internal server we can use um bad request here.
28:1328 minutes, 13 secondsAnd there we can also sorry this should be four for not found.
28:1928 minutes, 19 secondsAnd we can replace this two to use bad request.
28:2728 minutes, 27 secondsAnd there is going to be unauthorized.
28:3428 minutes, 34 secondsYeah, you can see there. So, so this is a custom error we're going to use across the app. So, this is extending from error. So, typically you're going to do
28:4228 minutes, 42 secondsthrow throw new error. And the problem with this is this
28:5028 minutes, 50 secondsis going to if you use this inside the service or controller, it's going to fall down to the internal server error we have here. So it's going to be cached
28:5828 minutes, 58 secondsby error handler and it's going to return as internal ser error. So we don't have we don't have so if I go back to app, we don't have
29:0729 minutes, 7 secondsthe ability to customize the uh status or change the message only the message but the status is going to always be 500
29:1529 minutes, 15 secondsinternal server. So that's the reason why we had to um extend from error and we can pass in our custom status code
29:2329 minutes, 23 secondsthere and error code too and then you can see that we have this export class our exception which extend also from the
29:3129 minutes, 31 secondsapp error. Now we can just say th we can say u troll new
29:3829 minutes, 38 secondsbad request exception and you can see that this is going to this we know that this is going
29:4429 minutes, 44 secondsto be um 400 and we can see that we're going to use it inside the service or controller. So, and once you run once
29:5429 minutes, 54 secondsyou once you define this in your in your service inside the error handler, we're going to catch the error. And since it's
30:0230 minutes, 2 secondsan instance of app error, it's going to we're going to get the status code, the message, and the error code. And there you can see internal server error is
30:1230 minutes, 12 secondspassed here too. So, we can also just remove this. It's not a must. So we can just set this here since
30:2030 minutes, 20 secondswe know what internal server error status is. So I can just say u http status
30:2930 minutes, 29 secondsuh internal server error and for the message we can say we can just say this should be internal server error message
30:3630 minutes, 36 secondsand then we can just import the error code. So I'll just come over here copy error code go to handler and I'll just pass it here.
30:4730 minutes, 47 secondsI say let's import error code dot uh we can say
30:5430 minutes, 54 secondsum so use error internal this is one so now
31:0231 minutes, 2 secondsthis is it so we have discussed the uh we've seen the error handler so this is used to capture error and we've looked
31:1031 minutes, 10 secondsat the app error which is also known as custom error we're going to use inside the controller or service and then
31:1731 minutes, 17 secondsinside the index.tx we can see how this is used here. So if we scroll down now
31:2531 minutes, 25 secondswe can see we have the error hander. So this is added at the last um middleware before the app um listener and we can
31:3531 minutes, 35 secondsthis um API. So this is where we're going to have all the routes. So inside the route tx you can see index tx and it
31:4331 minutes, 43 secondshas added this u route here. So u the models is empty
31:5031 minutes, 50 secondsand we can see so the controller is also empty and I think we we are done with this.
31:5931 minutes, 59 secondsSo the let's try and run the server to see everything is working fine.
32:0432 minutes, 4 secondsSo adding um the big cryptotx. So you can see here I just added a pre. So we're going to use this for the um for
32:1232 minutes, 12 secondsauthentication where we creating the user model and that's the only thing left. So let's go into
32:2132 minutes, 21 secondsEMV. So it has changed changed this. So I'm going to change it back to it. Let me quickly change it back. So I've
32:2832 minutes, 28 secondschanged it to fronted origin inside the EMV config and remove 3000
32:3632 minutes, 36 secondsand inside the index.x I need to change this two to front end origin and the error should stop. So let's run the server. So I'm going to remove this API.
32:4732 minutes, 47 secondsI'll just set it to / health and this is so let me open my terminal. So I open a new terminal here. I'll clear this and
32:5432 minutes, 54 secondsI'm going to CD into back end CD into back end folder and let's mpm
33:0033 minutesrundev and we can see that this is already running.
33:0833 minutes, 8 secondsSo let me confirm this.
33:1333 minutes, 13 secondsSo um to test it out I'm going to create inside the back end there I'm going to create a folder called https.
33:2133 minutes, 21 secondssay https and we're going to install we're going to add in an extension. So let me open
33:3033 minutes, 30 secondsthis and let's go to the extension tab and we need to install
33:3733 minutes, 37 secondslet me close this http yak.
33:4433 minutes, 44 secondsSo just type in http yak here. So I don't know why it's not coming up.
33:5033 minutes, 50 secondsLet me close this. So I've already added it already. So this is it http and make sure to install this package. So now
33:5833 minutes, 58 secondsonce you have this already. So I'll go into http and then let me just say health.
34:0534 minutes, 5 secondsSo health http like this. And here we can see get
34:1334 minutes, 13 secondsthe http locals 8,000 / health.
34:2434 minutes, 24 secondsSave this and let's click on the send button here. And then we can see the server is running. So this is great. So
34:3234 minutes, 32 secondswe are done with the h. We're done with the project setup. So let's go ahead and add in a database.
34:3934 minutes, 39 secondsIn this chapter, we're going to go ahead and connect MongoDB database. So search for MongoDB Atlas and make sure you log
Chapter 3: MongoDB Setup
34:4734 minutes, 47 secondsinto your account. So I've lo and let's create a new project. So I'll click on the new project. I'm going to call this
34:5434 minutes, 54 secondsbase B base 64. And let's click on next.
35:0135 minutes, 1 secondAnd let's click on create project.
35:0635 minutes, 6 secondsSo we're going to uh once this is created, let's go ahead and create the cluster. So let me wait for this to
35:1335 minutes, 13 secondsload. So let's click on create cluster and then
35:2035 minutes, 20 secondsso let's select a free version and let's click on create deployment.
35:3035 minutes, 30 secondsSo it's going to create a cluster. So let's click on copy. So I'm going to copy the password and let's click on create database and let's choose the connection.
35:4135 minutes, 41 secondsSo we're going to select VS code and we can copy this now. So let's click on
35:4735 minutes, 47 secondsdone and let's go to let's go to network.
35:5535 minutes, 55 secondsSo click on database and network access and let me wait for this and let's click on
36:0336 minutes, 3 secondslet's say IP access list and let's select click on add IP
36:1136 minutes, 11 secondsaddress. I'm going to select for so let me let me type it. So just type
36:1836 minutes, 18 secondsthis inside here and let me click on confirm and then this is going to be included
36:2536 minutes, 25 secondshere. And now we can go back to the clusters.
36:2936 minutes, 29 secondsSo let me go back and click on constants.
36:3436 minutes, 34 secondsAnd I think let me just copy this again and then click on done. And let's go
36:4336 minutes, 43 secondsback to the code and inside the envir
36:5436 minutes, 54 secondsmong URI.
36:5936 minutes, 59 secondsSo I've pasted database here and let's just say base 64 db.
37:0837 minutes, 8 secondsSave this. And now let's go into src folder inside the config env. And then we can use this here. So I'll go and copy this.
37:1937 minutes, 19 secondsGo to env. And I'm going to pass it here.
37:2737 minutes, 27 secondsLet's say get env. And let's pass it here.
37:3537 minutes, 35 secondsLet me add in comma. And now let's create database database.config.tx.
37:4737 minutes, 47 secondsAnd now we can say export constant connect
37:5637 minutes, 56 secondsdatabase async. Sorry async.
38:0638 minutes, 6 secondsAnd let's return let's return let's use try catch here
38:1438 minutes, 14 secondsand we can say await and we need to install so let me cancel the server let's do mpm install
38:2438 minutes, 24 secondsmongus so click on enter and this should
38:3238 minutes, 32 secondsinstall it in this um under this back inside the backend folder. So let's wait for this to install. And now it has
38:4038 minutes, 40 secondsalready installed. So we can import it here. Say import mongus
38:4838 minutes, 48 secondsfrom mongos. And then we're going to also import um env config.
39:0139 minutes, 1 secondSo let me just copy it. I'll go into EMV config and let me copy this
39:0839 minutes, 8 secondsand then I can just let me just pass it here and see config from
39:1639 minutes, 16 secondsEMV config and let's use mongos
39:2439 minutes, 24 secondsconnect and let's say config do mongodb url and then we can just say console
39:3439 minutes, 34 secondslog database connected
39:4139 minutes, 41 secondsand you can catch any error. So you can just console lock the error
39:4839 minutes, 48 secondsyou see database connection
39:5539 minutes, 55 secondserror and let's pass in the error and then we can see process sis one.
40:0640 minutes, 6 secondsSo now we have the database method. Now we have the connect database method. So let's go into index.tx
40:1540 minutes, 15 secondsand here we can pass it here. So say await pass this and let's add in async
40:2240 minutes, 22 secondshere and let's import it.
40:3040 minutes, 30 secondsSo let's run the s. So clear my terminal mpm rundev and let's see.
40:4840 minutes, 48 secondsSo now we can see database is connected.
40:5040 minutes, 50 secondsSo now let's go ahead and um start working on the modules the models. So we're going to create all the models
40:5840 minutes, 58 secondswe're going to use for this project. And after that we're going to work on the authentication. So let's go ahead and implement that. In this chapter we're
Chapter 4: Models
41:0541 minutes, 5 secondsgoing to start working on the models. So let's go into the back folder in LC and models. So we're going to start with the
41:1241 minutes, 12 secondsuser model. So I'm going to say user model.tx.
41:1841 minutes, 18 secondsAnd there we're going to we're going to import mongus. So let's import as import mongus.
41:2741 minutes, 27 secondsSo, we're going to import it from mongus. Sorry, I made a mistake here.
41:3641 minutes, 36 secondsAnd then we're going to import and document and schema. So, say document and then the schema.
41:4841 minutes, 48 secondsSo, let's create the type. So, say export interface is going to be uh let's call this user document.
41:5841 minutes, 58 secondsLet's extend extend from document and let's pass a name of which is of
42:0742 minutes, 7 secondstype string and email of type string. We have password of type string.
42:1942 minutes, 19 secondsThere we say created at type dates
42:2642 minutes, 26 secondsand we have updated at which is of type date two. So we're
42:3442 minutes, 34 secondsgoing to have a method. So the type is going to be compare. We're going to have a function. We're going to call it compare password.
42:4442 minutes, 44 secondsAnd it's going to take in a value which is of time string. and say promise and boolean.
42:5642 minutes, 56 secondsSo it's going to return boolean there.
42:5942 minutes, 59 secondsSo let's create a schema. So constant user schema is equals to new schema.
43:1143 minutes, 11 secondsAnd let's pass in the type user document. And we're going to have the name first.
43:2043 minutes, 20 secondsSo name is going to be type of string. And we're going to set this to required.
43:2943 minutes, 29 secondsSorry, required true. So we have email.
43:4043 minutes, 40 secondsI said this type string required
43:4743 minutes, 47 secondstrue and we're going to set this to unique
43:5443 minutes, 54 secondstrue and we can also set this local um lower
44:0144 minutes, 1 secondcase true and we can add dream
44:1344 minutes, 13 secondsSo let's add in password there. See um password
44:2144 minutes, 21 secondsand this is just going to have I'm going to set type and required there and let's come down here and let's add
44:3044 minutes, 30 secondscomma let's set time stamp to true.
44:4144 minutes, 41 secondsand we're going to say to JSON.
44:5044 minutes, 50 secondsSo we're going to delete the password from the response. So once we fet in the user, we don't want to return the password. So we're going to use
44:5744 minutes, 57 secondstransform and we're going to say doc rec.
45:0845 minutes, 8 secondsAnd let's this say if
45:1545 minutes, 15 secondsthen let's delete does password.
45:2545 minutes, 25 secondsAnd then let's return.
45:3345 minutes, 33 secondsSo I'm going to set this to um as any.
45:4245 minutes, 42 secondsSo the error should stop. Now we are done with this.
45:4745 minutes, 47 secondsSo now we can use um user schema pre
45:5745 minutes, 57 secondsSo before the user data is saving to the database, we want to hash the password.
46:0346 minutes, 3 secondsSo I say async function next
46:1146 minutes, 11 secondsand then let's return this. So we're going to say if this dot password
46:2046 minutes, 20 secondsand sorry and this dot is modify and then we get we're going to say password there.
46:3046 minutes, 30 secondsThen we need to say this password is equals to. So let's go into brypt.tx.
46:4246 minutes, 42 secondsThis is it here inside YouTube. So we can copy hash password
46:4846 minutes, 48 secondsand then we can say await hash password and say this dot password
46:5946 minutes, 59 secondsand let's import sorry the hash password from brcript. So we're going to create a
47:0747 minutes, 7 secondsmethod now. We say user schema method dot compare which we define here compare password.
47:1747 minutes, 17 secondsWe're going to pass in the password here. So I'll copy this paste it here and this is going to be equals to async
47:2647 minutes, 26 secondsfunction and it's going to take in value. So say type string and let's return
47:3747 minutes, 37 secondsum let's return the let's go into bit again the tx and let's copy this compare password and let's pass it here. So okay
47:4747 minutes, 47 secondsthis is using the same thing. So what I'll do, I'll go into break it. Let me just change this to compare
47:5647 minutes, 56 secondshash password. So I'll save this.
48:0248 minutes, 2 secondsSo I'll change this to um hash password.
48:0648 minutes, 6 secondsAnd then I can pass in I can pass in the value
48:1248 minutes, 12 secondssorry value and this dot password
48:2248 minutes, 22 secondsand the error should stop. So we can say constant user model is equals to mongus
48:3048 minutes, 30 secondsdot model and this going to have type of user document
48:3948 minutes, 39 secondsand we're going to set the name this is going to be user and pass in the user schema
48:4648 minutes, 46 secondsand then I'm going to return the user model here. So let me copy this replace it here to user model.
48:5748 minutes, 57 secondsSo now we have the user already. So now we're going to create the next one. So let's create a So since we going to allow user to connect their kit account.
49:0749 minutes, 7 secondsSo we need a model to um a table in the database to save this um account. So I'm
49:1549 minutes, 15 secondsgoing to call this GitHub account.tx.
49:2549 minutes, 25 secondsSo let me just copy this and let's head over into the GitHub um
49:3349 minutes, 33 secondsmod account model. So I'm going to change this to GitHub account. So I'll
49:3949 minutes, 39 secondssay GitHub account um document and we're going to change all of this. We're going to set user ID.
49:5049 minutes, 50 secondsSo we need the user ID which is a foreign key from the user model. So we're going to store the GitHub ID which
49:5949 minutes, 59 secondsis going to come from GitHub. Then we also have a field we're going to call
50:0550 minutes, 5 secondsGitHub login and this is going to be of type string. Then access token
50:1450 minutes, 14 secondswhich we're going to save in a D but we're going to encrypt it. So we also have the refresh um
50:2250 minutes, 22 secondsrefresh token which is of type string or no
50:2950 minutes, 29 secondsand we also have token expire expires at so let's call it expired at
50:3750 minutes, 37 secondsand this is going to be date or and then we have created at
50:4750 minutes, 47 secondsof type dates and updated at type dates.
50:5750 minutes, 57 secondsSo let me remove this method here and now we can create the schema. as a consign
51:0851 minutes, 8 secondsget account schema is going to be equals to new sorry
51:1651 minutes, 16 secondsmongus al so let's use the schema so new schema
51:2551 minutes, 25 secondsand let's pass in type here github documents u github account document and Let's
51:3551 minutes, 35 secondslet's open an object here and then we can say user ID and this is going to be of type string
51:4751 minutes, 47 secondssorry should be comma and this is going to be required to true
51:5751 minutes, 57 secondsand so I make a mistake this should not the um string we can just use mongus
52:0752 minutes, 7 secondsmongle schema sorry this schema type object and let's pass in reference
52:1552 minutes, 15 secondsand this is going to be user so let's also change this two to
52:2052 minutes, 20 secondsschema and type object id and let me add comma here and the error should stop so let's pass in github ID Okay.
52:3252 minutes, 32 secondsSo, I'll just quickly paste it here. So, let me format it.
52:4752 minutes, 47 secondsSo, let's add in the time stamp here.
52:5452 minutes, 54 secondsTime stamp. I'll set this to true.
53:0353 minutes, 3 secondsAnd then we can say constant sorry yeah let's say constant
53:1053 minutes, 10 secondsit up account is equals to um mongus
53:1953 minutes, 19 secondsdot model let's pass in github account
53:2853 minutes, 28 secondsdocument So let me quickly copy it and let's pass in.
53:3653 minutes, 36 secondsSo I'll call this GitHub account and we can pass in this schema. So I'll copy this and pass it here.
53:4753 minutes, 47 secondsAnd then below here we can export
54:0154 minutes, 1 secondSo we done with the GitHub account, the GitHub account model. So let's create the next one. So the next one is going to be sessions.
54:1054 minutes, 10 secondsSorry, sessions domod.tx.
54:1554 minutes, 15 secondsSo let's quickly copy. Let me go into GitHub model and let me copy this. So I
54:2254 minutes, 22 secondsremove this. Let me just let me copy all of this and save it. And then go into session model and I'm going to paste it
54:3154 minutes, 31 secondshere. So we can modify this. So I'm going to change this to session.
54:3754 minutes, 37 secondsSo session session here is you can call this a chat a chat. Yes. So we're going to save the chat history. So I'm just
54:4654 minutes, 46 secondscalling it session. So it's still so can also call it as chat. So I'm going to use user ID here. And then let me remove all of this.
54:5654 minutes, 56 secondsSo I'm going to say sl. So the user um from the client side we're going to generate lock ID and we're going to save it here in the um this session the DB.
55:0655 minutes, 6 secondsSo I'm going to set this of type string here.
55:1055 minutes, 10 secondsAnd we're going to set the title of the session or the title of the chat. So we're going to have string. I'll just set this on.
55:2155 minutes, 21 secondsThen since we're going to be using sandbox and we're going to save the ID of the sandbox. So we're going to be using up sand upstarch box. So I'm going
55:3055 minutes, 30 secondsto save the ID of the box. So I'm going to say string
55:3755 minutes, 37 secondsuh string on no. And then we're going to save the repo URL the selected repo from the client side.
55:4955 minutes, 49 secondsAnd we're going to set let's save also the repo name.
55:5555 minutes, 55 secondsUh we can say string or no.
56:0256 minutes, 2 secondsAnd then we need to save the default branch. So this is going to be either main or master. So let's set this to string.
56:1456 minutes, 14 secondsOh no.
56:2256 minutes, 22 secondsSo now we're going to also generate branch. So I'm going to call this branch name. So this is going to be the branch the AI is going to push any changes to.
56:3156 minutes, 31 secondsSo instead of pushing to the default branch, the main branch is going to create it own branch is going to push to. So we're going to generate it by
56:3956 minutes, 39 secondsourself. So we're going to also save it into that um session. So uh the chart.
56:4556 minutes, 45 secondsSo I'm going to say this is going to be string or no.
56:5356 minutes, 53 secondsAnd then we're going to have repo initialize um initialize. Yes.
57:0257 minutes, 2 secondsSo I'm going to say initialize at this type date or no. So we're going to
57:1057 minutes, 10 secondsuse this to so we're going to use to track um if the user has already initialized let's say the user has um
57:1757 minutes, 17 secondssent a message from the client side and we have already cloned the repo and we have changed we have check out to this
57:2557 minutes, 25 secondsgenerated to the um to the branch. So we want to use this. So if the user send
57:3157 minutes, 31 secondsnew messages so instead of checking to that same branch again we going to use this to track. So if this is already saved to the database then there's no
57:4057 minutes, 40 secondspoint and changing to the branch so that um so the user can the message can go through and then the the branch is
57:4957 minutes, 49 secondsalready already set and the agent is going to push to that branch. So that is the reason we have this. So now we can
57:5757 minutes, 57 secondsthen copy this uh session document and let's replace it here. So I'm going to change this to session.
58:0858 minutes, 8 secondsSo now we have the user ID and I'm going to remove this. So I'm going to set um we're going to have stock ID
58:1658 minutes, 16 secondsand this is going to be type string.
58:2958 minutes, 29 secondsAnd then we're going to have required. And this is going to be required.
58:3958 minutes, 39 secondsAnd then we're going to set this to unique too.
58:5158 minutes, 51 secondsSet it to true. And then we're going to have I'm going to um pass in orders here. So the box id reple name default
59:0059 minutesbranch generated branch is branch name and then rep initialize that. Then I also forget to pass in title here.
59:1159 minutes, 11 secondsSo title is just going to be type and I'm just going is not going to be required. So I'm just going to say
59:2059 minutes, 20 secondsdefault is going to be null.
59:2659 minutes, 26 secondsSo now we can copy the session schema and let's go straight to this and just pass it here and I'm going to change
59:3559 minutes, 35 secondsthis to session and change this to session
59:4259 minutes, 42 secondssorry session this will be session document and um then this is going to be section
59:5059 minutes, 50 secondssession schema So let me replace it here and then I'm
1:00:021 hour, 2 secondsgoing to copy this and then change it pass it here.
1:00:101 hour, 10 secondsSo let's just call it session model. This is fine model. So I'll copy this and replace it here.
1:00:221 hour, 22 secondsSo we are done with this. So let me save this now and we can create the last model here and that is going to be message model.tx.
1:00:361 hour, 36 secondsSo let's go into session model and let's copy this. So just copy only this part and let's go into message model and
1:00:441 hour, 44 secondslet's paste it here. Let's change this from document from session document to message document. And there instead of
1:00:521 hour, 52 secondsuser ID, we're going to change this to session ID session ID. So I'm going to remove all of this.
1:01:031 hour, 1 minute, 3 secondsAnd we're just going to only let me remove this um lock ID too.
1:01:091 hour, 1 minute, 9 secondsSo we're going to save the ID row and path. And this is going to store whatever SDK the VC SDK is going to send to us. So we're going to save it here.
1:01:211 hour, 1 minute, 21 secondsSo now let's create a constant message schema is equals to new schema.
1:01:341 hour, 1 minute, 34 secondsAnd let me copy this message document message here.
1:01:411 hour, 1 minute, 41 secondsAnd then I'm just going to paste it here. So we're going to get the session ID which is going to be um type
1:01:501 hour, 1 minute, 50 secondsschema type object ID reference and then required. Then ID is going to be required. And then we can see the row
1:01:571 hour, 1 minute, 57 secondsuser assistant and then system and then the path is going to be MongoDB schema type domix. So I'm going to um let's add
1:02:071 hour, 2 minutes, 7 secondscomma here and let's pass in time stamp and set this to true.
1:02:191 hour, 2 minutes, 19 secondsSo you can say custom message constant message model is going to be equals to mongus
1:02:301 hour, 2 minutes, 30 secondsdot model and let's pass in the document message documents
1:02:421 hour, 2 minutes, 42 secondsand then we can say message and let's pass in the message schema.
1:02:521 hour, 2 minutes, 52 secondsAnd then we can export default message model.
1:03:021 hour, 3 minutes, 2 secondsSo we are done with all of the schemas.
1:03:041 hour, 3 minutes, 4 secondsSo now let's go ahead and work on implementing or implement the um authentication. So we're going to add authentication into a project. We're
1:03:131 hour, 3 minutes, 13 secondsgoing to be using passport and JWT with cookie. So let's go ahead and implement that in this chapter. We're going to go ahead and start working on the authentication.
Chapter 5: Authentication
1:03:231 hour, 3 minutes, 23 secondsSo we're going to ask command code to add. So if we go into the command code test MD so inside scronding. So it already knows how to add authentication.
1:03:331 hour, 3 minutes, 33 secondsSo the way I usually add authentication um passport using passport JWT and J web token. So, I'm going to go ahead open
1:03:421 hour, 3 minutes, 42 secondsthis and let's say um let's say add
1:03:491 hour, 3 minutes, 49 secondsand the uh add in project. I'll type in the back folder
1:03:591 hour, 3 minutes, 59 secondsand I'm going to click on enter. So, it's going to go ahead and um look through the um test MD file. Then it's
1:04:061 hour, 4 minutes, 6 secondsgoing to read the project and it's going to go ahead and um add authentication into the project. So it's going to add
1:04:141 hour, 4 minutes, 14 secondspassport passport um and JW token with passport JWT and it's going to also create the cookie.tx file. So I'm going
1:04:221 hour, 4 minutes, 22 secondsto go through all the file going to create. So let's wait for it to finish.
1:04:281 hour, 4 minutes, 28 secondsNow you can see that created the the todo. So you can see it's going to install passport passport JWT with Jose
1:04:371 hour, 4 minutes, 37 secondsweb token. Then it's going to update the env.con.tx and it's going to add JWT JWT secret
1:04:451 hour, 4 minutes, 45 secondsinside the EMV file. It's going to create utilities cookie.tx using it's going to create this method here you can see here. Then it's going to create so
1:04:541 hour, 4 minutes, 54 secondsI've already created the model. So you can see that it even wanted to create the model but it's going to confirm that I've already created the model. Then
1:05:011 hour, 5 minutes, 1 secondit's going to create passport.config.tx and it's going to add the O validator, the O service, the O controller, and the
1:05:091 hour, 5 minutes, 9 secondsO route. Then it's going to initialize passport in index.tx. So I'm going to click on yes for it to install. So let's
1:05:161 hour, 5 minutes, 16 secondswait for it to finish. So now it want to add in the J beauty secret in the EMV.conig.
1:05:251 hour, 5 minutes, 25 secondsSo I'm going to click on enter and it's going to add it in the EMV. So let's enter. So I think the only thing that it didn't add is the JWT um expiring art.
1:05:371 hour, 5 minutes, 37 secondsSo we going to add it manually. So it is going to go ahead. So it started to create the cookie.
1:05:441 hour, 5 minutes, 44 secondsSo inside the s folder YouTube. So it's going to create this. So let's wait for it. So okay, I'm going to accept it. And
1:05:531 hour, 5 minutes, 53 secondsnow we can see that it has created a cookie. And if I go into the file, we can see that it added 30 days. Yeah.
1:06:031 hour, 6 minutes, 3 secondsSo, and then we can see clear cookie.
1:06:091 hour, 6 minutes, 9 secondsSo, let's wait for it. So, it's creating the user service. So,
1:06:161 hour, 6 minutes, 16 secondsit's going it just added these two um method here. Find user by ID and find
1:06:231 hour, 6 minutes, 23 secondsuser by email. So it's going to go ahead and create the um passport config. So we going to loop through each of the file
1:06:311 hour, 6 minutes, 31 secondsit create once it is done. So click on enter and let's just quickly wait for this to finish. So it's already done
1:06:381 hour, 6 minutes, 38 secondswith it. So let's go into each of the files. So let's go into the cookie.tx.
1:06:441 hour, 6 minutes, 44 secondsSo I really want to update this. So instead I'm going to go into my where we have JWT secret. I'm going to add JWT
1:06:531 hour, 6 minutes, 53 secondsexpired in. Then I'm going to copy this and I'm going to config where we have
1:06:591 hour, 6 minutes, 59 secondsthe EMV and I'm going to add it here. So I'm going to pass in expired in I save this and then let's go
1:07:091 hour, 7 minutes, 9 secondsback to the cookie. So instead of um this way I'll come over here. I'm going to replace this. So I'm going to replace
1:07:181 hour, 7 minutes, 18 secondsthis and or let's just leave it as So let's change this to 7 days.
1:07:301 hour, 7 minutes, 30 secondsSo replace 7 days. Yeah. So let's replace this to 7 days. And then we have the set JW
1:07:391 hour, 7 minutes, 39 secondscookie. So I'm going to be passing the user ID here. So I'm going to remove this. Then I'm going to just uh request for we're going to pass in the response response end user ID.
1:07:521 hour, 7 minutes, 52 secondsThen we can set a type here. So I'm going to set a type here. So you copy cookie and I'm going to set cookie here.
1:08:001 hour, 8 minutesSo now we going to say constant payload.
1:08:041 hour, 8 minutes, 4 secondsPayload is equals to user ID. And then I'm going to say um constant expire in.
1:08:151 hour, 8 minutes, 15 secondsSo instead of this I'm going to use let's use the EMV. So say EMV config
1:08:221 hour, 8 minutes, 22 secondsJWT. So let me import it dot this then we're going to say let's
1:08:301 hour, 8 minutes, 30 secondsuse this as as time.
1:08:341 hour, 8 minutes, 34 secondsNow we're going to use the JWT. So I say um constant token is equals to JWT
1:08:431 hour, 8 minutes, 43 secondsdo sign payload. We're going to pass in the configwt secret and then the expire in um expire in here.
1:08:551 hour, 8 minutes, 55 secondsSo let me also add audience here.
1:09:001 hour, 9 minutesSo this is going to be user So let's import the JWT.
1:09:111 hour, 9 minutes, 11 secondsSo now we have this now we have the maximum age
1:09:181 hour, 9 minutes, 18 secondsonly true and then the secure then we have same site. So I'm going to
1:09:261 hour, 9 minutes, 26 secondsuh we can leave it as or we can just say um EMV config
1:09:331 hour, 9 minutes, 33 secondslike this EMV config production sorry EMV config production is going to be
1:09:401 hour, 9 minutes, 40 secondsstreet and then I can also change this to to use EMV config
1:09:501 hour, 9 minutes, 50 secondsand let's update this too. So I'm going to return return this. And for a clear
1:09:571 hour, 9 minutes, 57 secondsJW key, we don't really need all of this. So I'll just remove this. And we can just set let's set part to SL.
1:10:081 hour, 10 minutes, 8 secondsSo this is fine. So now we can go over into let's go into um the controller inside the controller first.
1:10:191 hour, 10 minutes, 19 secondsAnd then if I go into controller then we can see we have the register
1:10:281 hour, 10 minutes, 28 secondscontroller here and inside the validation let's go into validation validator you see that it is all name
1:10:371 hour, 10 minutes, 37 secondsemail and password and for the login schema we have email and password there.
1:10:421 hour, 10 minutes, 42 secondsSo now we can go back into the controller so we're going to use this cookie. So I'm going to set GW beauty cookie and
1:10:511 hour, 10 minutes, 51 secondsinside the controller we can use this here. So we can just get the user ID. So say constant user id is going to be
1:10:581 hour, 10 minutes, 58 secondsequals to user do ID and we can
1:11:061 hour, 11 minutes, 6 secondswe can then say return import jwt cookie. And then I'm just going to
1:11:131 hour, 11 minutes, 13 secondsreturn it like this. And let's just move this um of JSON. We can also add in let's add in status here too.
1:11:251 hour, 11 minutes, 25 secondsSo let's import HTTP status dot created.
1:11:371 hour, 11 minutes, 37 secondsSo let's import this um um imported
1:11:441 hour, 11 minutes, 44 secondsset. Let me import it too. And the error should stop
1:11:521 hour, 11 minutes, 52 secondsto stop. So I don't know why this is. So let's go into the register service. And
1:11:591 hour, 11 minutes, 59 secondswe can see the register service here. So I'm going to remove this token. Don't need to return generate any token. So let's just remove it.
1:12:101 hour, 12 minutes, 10 secondsAnd you can see that it created this create user and you can see user model create and we pass in the data here. So
1:12:181 hour, 12 minutes, 18 secondsthis is still okay. Then let me uh let me of pass data. I'm just going to open it like this and just pass it like this
1:12:281 hour, 12 minutes, 28 secondsinstead. So now we have the user. We can just return the user directly like this. return user.
1:12:371 hour, 12 minutes, 37 secondsSo this is fine. So we have the register service here and and you can see that the error the error has stopped. So
1:12:461 hour, 12 minutes, 46 secondslet's go um let's go back to the controller and let's um look at the login. So we can see that it's um
1:12:541 hour, 12 minutes, 54 secondsimplemented created the function there and it's using the login schema which you can see it and then it's going to um
1:13:021 hour, 13 minutes, 2 secondsget the body and it's passing the body into the login service. So we're going to copy the same thing we have here
1:13:111 hour, 13 minutes, 11 secondsand let me um add it here too. So I'm just going to remove this and just paste it here. And we need to get the user ID.
1:13:201 hour, 13 minutes, 20 secondsSo we can just get like this. So user dot user. So I'm going to change this to user id.
1:13:291 hour, 13 minutes, 29 secondsSo we're going to update this response.
1:13:321 hour, 13 minutes, 32 secondsSo instead of u register I'll say user um let's say login
1:13:411 hour, 13 minutes, 41 secondssuccessful and let's change this to okay.
1:13:451 hour, 13 minutes, 45 secondsSo let's go into the login service. Now we can see find user email and you see
1:13:521 hour, 13 minutes, 52 secondswe can have we have it's importing the uh um the exception we created and then it's going to check if the password
1:14:011 hour, 14 minutes, 1 secondmatch so invalid email service. So instead of unauthorized let's use not not found there not found exception.
1:14:131 hour, 14 minutes, 13 secondsSo this is fine. So it's using the compare password we define inside the user model. So this is good like this.
1:14:231 hour, 14 minutes, 23 secondsSo I'm going to remove this generate up.
1:14:261 hour, 14 minutes, 26 secondsThen I'm going to remove all of this and I'm going to just pass in user like this. So let me remove this.
1:14:351 hour, 14 minutes, 35 secondsAnd you can see that everything is fine.
1:14:381 hour, 14 minutes, 38 secondsSo we can go ahead and let's go into the O controller and the error should stop.
1:14:441 hour, 14 minutes, 44 secondsSo this is great. So for the logout I'm going to so inside the cookie you can see that we return
1:14:521 hour, 14 minutes, 52 secondsum response cookie. So let's go into the out. So what I'm going to do I'm just
1:15:001 hour, 15 minutesgoing to remove um let's just do return here.
1:15:041 hour, 15 minutes, 4 secondsreturn clear cookie hot cookie response dot status. Okay. And then we're going to say JSON.
1:15:151 hour, 15 minutes, 15 secondsAnd you can see that everything. So let me fix this error.
1:15:281 hour, 15 minutes, 28 secondsAnd this is not public. Let's go into the cookie. And we didn't return this.
1:15:341 hour, 15 minutes, 34 secondsSo I just return and the controller.
1:15:411 hour, 15 minutes, 41 secondsLet me see if we import it. And then the error should stop. So instead of login user, I'm going to change this to login
1:15:491 hour, 15 minutes, 49 secondscontroller. Yeah, this is going to be log out controller too. And for the all status, we can just say all status controller.
1:16:011 hour, 16 minutes, 1 secondSo let me collapse this. So for this we're just going to return the user. You can see we are returning the user and we
1:16:081 hour, 16 minutes, 8 secondscan see authenticated there. So this is fine. So let's now go into the route.
1:16:141 hour, 16 minutes, 14 secondsSo inside the route it created all routes and then inside the route we can see we need to remove all of this and
1:16:221 hour, 16 minutes, 22 secondslet's import um login.
1:16:281 hour, 16 minutes, 28 secondsSo I'm going to remove all these passports.
1:16:331 hour, 16 minutes, 33 secondsSo let me import login controller and then log out controller
1:16:401 hour, 16 minutes, 40 secondsand then the status controller too and then now let's go and look at the
1:16:471 hour, 16 minutes, 47 secondspassport. So this is fine. So before we look at the passport let's look at the index.tx TX and you can see that it has imported the it has created the route
1:16:551 hour, 16 minutes, 55 secondsfor the O and import the route the O route here. So now we have look at this
1:17:021 hour, 17 minutes, 2 secondsum the O from the O controller to the O service and then the O validator. So we
1:17:091 hour, 17 minutes, 9 secondscan go ahead and let me remove this and this. So let's go into passport. So
1:17:161 hour, 17 minutes, 16 secondslet's go into config and then passport config. And if you scroll up now you can
1:17:231 hour, 17 minutes, 23 secondssee that it's imported the passport and it got JWT strategy extract JWT. So you
1:17:311 hour, 17 minutes, 31 secondscan see cookie extractor. So it's going to extract the cookie the access token and then it has created the JWT option.
1:17:381 hour, 17 minutes, 38 secondsSo it's using JWT from request and extract from extractor. Then I pass in the cookie extractor. Then we have
1:17:461 hour, 17 minutes, 46 secondssecret or cookie and then we have config. So import config and then we can also add in the audience
1:17:551 hour, 17 minutes, 55 secondsto the log to it. So now you can see that use passport use
1:18:051 hour, 18 minutes, 5 secondsstrategy and then JWT options here. So I think something I saw. So if I let me remove this.
1:18:201 hour, 18 minutes, 20 secondsOkay. The error has stop. So I use the audience. Yeah. So JWT options and then
1:18:261 hour, 18 minutes, 26 secondsthe payload and we have the sub. So passport do sub. Yeah.
1:18:341 hour, 18 minutes, 34 secondsSo instead of sub I'm going to this is supposed to be user ID. So I'll say user
1:18:401 hour, 18 minutes, 40 secondsID and then let's change this to payload user ID. So we have the user and if I go
1:18:471 hour, 18 minutes, 47 secondsinto find user by id you should see id is passed here and then if user we just return the user else just return false
1:18:561 hour, 18 minutes, 56 secondsand we return error and then we can see passport o jwt and now we can use this inside the route like inside the out
1:19:051 hour, 19 minutes, 5 secondsroute you can see it was used here so only authenticated user can use um this authorized to access this um endpoint
1:19:141 hour, 19 minutes, 14 secondspoint. So then inside the index tx you can see that imported the passport
1:19:201 hour, 19 minutes, 20 secondshere and it didn't initialize passport here. So everything is fine. So we've gone through everything. Let me confirm
1:19:271 hour, 19 minutes, 27 secondseverything is save. So let me save this and let me clear this.
1:19:341 hour, 19 minutes, 34 secondsSo let's go into the backend folder s. So let's go ahead and test this out.
1:19:391 hour, 19 minutes, 39 secondsEverything is working. So I'm going to run my server. So let me go there and then let's see mpm rundev.
1:19:471 hour, 19 minutes, 47 secondsSo let me cd into my back end mpm rundev and then let's go into https and then
1:19:561 hour, 19 minutes, 56 secondslet's create http and I'm just going to paste it here. So we can see api
1:20:051 hour, 20 minutes, 5 secondsregister the name email and password. Then we have um the login endpoint and then we
1:20:131 hour, 20 minutes, 13 secondscan do get API user. So let's make sure server is running and the database is connected.
1:20:211 hour, 20 minutes, 21 secondsSo let's quickly click on send and let's see.
1:20:251 hour, 20 minutes, 25 secondsSo let's see. And now we can see that the user is registered. This is great.
1:20:301 hour, 20 minutes, 30 secondsSo uh let's try and um log. So I'm going to try and remove the email and let's
1:20:381 hour, 20 minutes, 38 secondssee. So click on login. Now we can see validation is working. So invalidation failed email and invalid email address.
1:20:471 hour, 20 minutes, 47 secondsSo if I click on send now we should see that this is login. And to see the
1:20:541 hour, 20 minutes, 54 secondsaccess cookie we can just click on http yak. And then if you click on sessions let me see variable. Okay. Yeah, we can
1:21:011 hour, 21 minutes, 1 secondsee session now. We can see the cookie and cookie is created. Yeah. And there you can also see the history.
1:21:101 hour, 21 minutes, 10 secondsSo, uh let's try and get the user. So, I'm going to click on send.
1:21:161 hour, 21 minutes, 16 secondsAnd I think this failed. So, let's check this. Okay. I think this is me. So, let's confirm this inside the
1:21:241 hour, 21 minutes, 24 secondsroute. Out route. Okay. Here you can see me. So, let's click on send and then you can see the response.
1:21:361 hour, 21 minutes, 36 secondsThis is great. Then for log out, let's click on log out and you can see user log out successful. So if we go to the
1:21:431 hour, 21 minutes, 43 secondshttp now let's click on sessions and u or let's just try to click on get me.
1:21:551 hour, 21 minutes, 55 secondsYou can see unauthorized here. So this is working. This is working fine.
1:22:021 hour, 22 minutes, 2 secondsSo great.
1:22:051 hour, 22 minutes, 5 secondsSo to see uh the data in the database, I can copy this URL. Then click on MongoDB. So make sure you can add it.
1:22:161 hour, 22 minutes, 16 secondsYeah, you can just search for and DB and then just install this
1:22:231 hour, 22 minutes, 23 secondsum extension. And then inside the MongoDB, let's add connections. I'll click on connect
1:22:321 hour, 22 minutes, 32 secondsand I'll paste it here and click on enter. And this is connecting.
1:22:401 hour, 22 minutes, 40 secondsSo let's see.
1:22:431 hour, 22 minutes, 43 secondsSo now it's connected. Then we should see this. So I'm going to close this.
1:22:481 hour, 22 minutes, 48 secondsAnd we can see database here. So we can see users. We can see one in document.
1:22:551 hour, 22 minutes, 55 secondsSo let's wait for it.
1:22:581 hour, 22 minutes, 58 secondsAnd now you can see the email the password is hashed and other and the name. So this is this is it. So we are
1:23:061 hour, 23 minutes, 6 secondsdone with the authentication. So now we're going to go ahead and work on the GitHub connection. In this chapter we're
Chapter 6: GitHub Connect & APIs
1:23:141 hour, 23 minutes, 14 secondsgoing to go ahead and work on the GitHub connection. Then also retrieving the repositories. So inside the EMV for we
1:23:231 hour, 23 minutes, 23 secondsneed to add in some EMV. So I'm going to do that here. So we're going to later on get use GitHub client ID client secret.
1:23:301 hour, 23 minutes, 30 secondsThen we're going to have our own. So this is going to be created by o state secret and then the token um encryption
1:23:381 hour, 23 minutes, 38 secondskey. So this is going to we're going to we're going to encrypt the access token refresh token and we're going to send him some state. So we're going to also
1:23:461 hour, 23 minutes, 46 secondshave to sign the the sign the state. So we're going to also have a secret for it so we can verify this state. So let's go
1:23:541 hour, 23 minutes, 54 secondsinto src folder and inside let's create a folder here. So lib
1:24:011 hour, 24 minutes, 1 secondand here I'm going to create a folder social o
1:24:071 hour, 24 minutes, 7 secondsand then we can just do index here and we can create the state file.
1:24:141 hour, 24 minutes, 14 secondsSo say state tx and we're going to create the encryption file. So I'll say encryption
1:24:251 hour, 24 minutes, 25 secondstx. So I forgot to use so inside the um config envig
1:24:331 hour, 24 minutes, 33 secondswe are going to get them. Yes. So I'm going to so I've paste it here. And inside the env again I need to add in
1:24:411 hour, 24 minutes, 41 secondsthe base. Let me just call it base. So I'll do that above here at the top here.
1:24:471 hour, 24 minutes, 47 secondsSo I'll say base URL and this is going to be the base URL for backend service server and this is
1:24:561 hour, 24 minutes, 56 secondsgoing to be added in the callback URL in GitHub. So I will go into the env config
1:25:031 hour, 25 minutes, 3 secondsand I'm going to just paste it here. So now inside the index tx so we can have this. So it's going to be called a
1:25:101 hour, 25 minutes, 10 secondsredirect URL. So call back. So inside there we can have it here. So I can say constant
1:25:181 hour, 25 minutes, 18 secondsGitHub redirect URL
1:25:251 hour, 25 minutes, 25 secondsand I'm going to just let's import it like this. So let's import the EMV config. Yeah. So this is
1:25:351 hour, 25 minutes, 35 secondsgoing to be the redirect URL. So now we going to add in. So I'm going to add them this here the GitHub URL. So the
1:25:431 hour, 25 minutes, 43 secondslogin URL, the token URL, the API URL and the scope. So we have repo read user
1:25:491 hour, 25 minutes, 49 secondsand read. So now let's add in the first we're going to create is the create
1:25:561 hour, 25 minutes, 56 secondsGitHub connect URL. So let's create this method here. So I say constant sorry constant um function.
1:26:051 hour, 26 minutes, 5 secondsIt's going to be create uh GitHub connect URL
1:26:151 hour, 26 minutes, 15 secondsand this is going to have value here and this is going to or let's change this to data
1:26:231 hour, 26 minutes, 23 secondsand this is going to have we're going to pass in the user ID which is of type string and then the redirect
1:26:301 hour, 26 minutes, 30 secondsthe redirect to then I'm going to open this thing. We're going to go ahead and create the state. So after we create
1:26:391 hour, 26 minutes, 39 secondsa state, we're going to create the params. So let me just u define the state here. I say constant state is
1:26:481 hour, 26 minutes, 48 secondsgoing to be equals to u we're going to call this create o state
1:26:551 hour, 26 minutes, 55 secondshere and we're going to come back to it. So state is going to take an object here.
1:27:031 hour, 27 minutes, 3 secondsIt's going to be user ID with data user id and then this data redirect.
1:27:121 hour, 27 minutes, 12 secondsSo let me data redirect to so let me sorry let me change this to data redirect to so copy this and let me change this.
1:27:221 hour, 27 minutes, 22 secondsLet me also change this. So now we're going to create the params. So say constant params new search params and
1:27:301 hour, 27 minutes, 30 secondswe're going to pass in the client ID the scope and it's going to we're going to have
1:27:371 hour, 27 minutes, 37 secondsthe state here and I'm going to say allowed sign of true and response type here response type code.
1:27:481 hour, 27 minutes, 48 secondsSo we have this uh we have this method there. So why is
1:27:561 hour, 27 minutes, 56 secondsthis string error export
1:28:061 hour, 28 minutes, 6 secondsso the error is stopped now. So let's go ahead and create a state. So copy this and let's go into state. So I can ask the AI agent to create the state for me.
1:28:151 hour, 28 minutes, 15 secondsSo it it's going to know how to create it because inside the command code scaffold I think scaffold or there you can see here. So let me just tell it to
1:28:251 hour, 28 minutes, 25 secondsum add it. So, I'm going to go to this and I'm going to um I'm going to say
1:28:341 hour, 28 minutes, 34 secondscreate this state for the social
1:28:431 hour, 28 minutes, 43 secondso only in the I'll point to the states
1:28:521 hour, 28 minutes, 52 secondsuh states.tx TX and we can just point to the um sushu o.
1:29:001 hour, 29 minutesSo now we can just click on enter and this should start working on it. So let's click and click on enter and let's wait for it.
1:29:111 hour, 29 minutes, 11 secondsSo it's going to go ahead and read the test. Then it's going to go ahead and create this state. So let me wait for
1:29:191 hour, 29 minutes, 19 secondsit. So it has started even though I told it to create only the state. So it also want to create the uh encryption here.
1:29:261 hour, 29 minutes, 26 secondsSo I click on yes. So it has created the uh state.tx now.
1:29:371 hour, 29 minutes, 37 secondsSo let's also wait for it to create the encryption.x.
1:29:441 hour, 29 minutes, 44 secondsSo let's wait for here.
1:29:491 hour, 29 minutes, 49 secondsNow it's creating the uh encryion.tx. So I click on yes and then index.tx. So let's wait.
1:29:571 hour, 29 minutes, 57 secondsSo I think it is done with it. So we can look at the state.tx.
1:30:021 hour, 30 minutes, 2 secondsAnd now you can see that has created the create o state and we can see the payload here which we we pass in the
1:30:101 hour, 30 minutes, 10 secondsindex. TX. We pass in the user ID and the redirect to. Then we have the
1:30:171 hour, 30 minutes, 17 secondspayload base 64 and this is going to we're going to buffer payload string for base and 64
1:30:251 hour, 30 minutes, 25 secondsURL. Then we're going to create signature. We're using crypto and this is it imported it. Then you can see
1:30:321 hour, 30 minutes, 32 secondsthat's pass it pass the payload B 64 to this and we have the scripture signature and then we have payload B 64 signature.
1:30:411 hour, 30 minutes, 41 secondsThen we also have now the verify or what state and there we are going to split this to get the payload base 64 and
1:30:511 hour, 30 minutes, 51 secondssignature and then if it's not there we're going to return an error and we're going to expect um expected signature.
1:30:591 hour, 30 minutes, 59 secondsSo it's going to create a signature again and then we're going to use time save equals to equal. So if this does
1:31:061 hour, 31 minutes, 6 secondsnot m it's going to return an error and then it's going to we're going to also have the payload to get the user and the so I also want to add expired to this.
1:31:151 hour, 31 minutes, 15 secondsSo I can just come over here and so I'm going to paste expire. So this is going to expire in 10 minutes. So I'm going to
1:31:241 hour, 31 minutes, 24 secondscheck that here too. So I'm going to say if payload expired is less than date now then we're just going to throw and error
1:31:331 hour, 31 minutes, 33 secondsand then we return this um user ID the payload. So we're going to encryption.tx
1:31:401 hour, 31 minutes, 40 secondsand then we can see that it has added the gradient so the advanc encryption standard and it's using 256 bits. Then
1:31:491 hour, 31 minutes, 49 secondswe have the IV length and the key. So we can see that it has defined the IV here with the IV length. We have the cipher
1:31:581 hour, 31 minutes, 58 secondsand the tag and the encrypted. Then it's going to return this here. And then you can see it has also created the decrypt
1:32:051 hour, 32 minutes, 5 secondstoken. So now let's go into the index.tx.
1:32:091 hour, 32 minutes, 9 secondsAnd there we can import. Let's import this. So imported from state. Now we
1:32:151 hour, 32 minutes, 15 secondshave the create github um connect URL with the state passed to it. Now we're going to create the next method which is
1:32:231 hour, 32 minutes, 23 secondsgoing to be the method to exchange the code that's going to return when we connect the user. So we're going to exchange the code for the access token
1:32:311 hour, 32 minutes, 31 secondsand the refresh token. So let's say export async function exchange code for token. Uh I
1:32:401 hour, 32 minutes, 40 secondsdon't want or use exchange github code for toko and we're going to pass in
1:32:481 hour, 32 minutes, 48 secondsthe code then string. I'm just going to remove this.
1:32:521 hour, 32 minutes, 52 secondsAnd then we're going to define the param. So I'm going to say params. This is going to be equals to new search params. H. Sorry. And let me close this.
1:33:031 hour, 33 minutes, 3 secondsAnd then here we're going to pass in the client ID and we're going to pass in the client secret and then the code and the
1:33:101 hour, 33 minutes, 10 secondsredirect URL. Then for the we're going to create the endpoint here. So what I'm going to I'm going to define it here.
1:33:171 hour, 33 minutes, 17 secondsSo, I'm going to say function uh I'm going to call it request request GitHub
1:33:251 hour, 33 minutes, 25 secondsum GitHub token and there we're going to just pass in params. So, the reason why I'm doing
1:33:321 hour, 33 minutes, 32 secondsthis is because I'm going to use this for the refresh method we're going to create. So, let me add a care and then
1:33:391 hour, 33 minutes, 39 secondsfor the params. So say params and this is going to be of type URL search params and then we're going to say constant
1:33:481 hour, 33 minutes, 48 secondsresponse is going to be equals to wait fetch and we're going to use the get token URL and let me close this and
1:33:561 hour, 33 minutes, 56 secondswe're going to say method post and then we're going to have the headers uh application and then we're going to have
1:34:041 hour, 34 minutes, 4 secondsaccept here. Let's also pass in user agent. So say user agent sorry user
1:34:121 hour, 34 minutes, 12 secondsagent and we're going to just use base um base
1:34:191 hour, 34 minutes, 19 secondsbase 64 agent here and we're going to pass in the body and we're going to return um
1:34:271 hour, 34 minutes, 27 secondsthe response. So let me instead of doing it like this I'm going to say constant um data
1:34:341 hour, 34 minutes, 34 secondsis equals to response JSC and if there is any error if this is not complete it's going to return error
1:34:421 hour, 34 minutes, 42 secondsand then we're going to return the data here. So let's return data
1:34:491 hour, 34 minutes, 49 secondsand now we can use this here. So we say constant data is equals to refresh tok refresh
1:34:581 hour, 34 minutes, 58 secondstoken and then I'm just going to say um return sorry return. So instead of data I'm
1:35:061 hour, 35 minutes, 6 secondsjust going to say access token then we're going to um say refresh
1:35:141 hour, 35 minutes, 14 secondsrefresh token then expired in. So I'm going to remove this for the expired in.
1:35:201 hour, 35 minutes, 20 secondsI'm going to have this here. So we're going to get expired in here. So let's say constant
1:35:271 hour, 35 minutes, 27 secondsconstant expired in. And then we're going to pass in expired in here.
1:35:341 hour, 35 minutes, 34 secondsSo expires at so this is fine. So now let's create the
1:35:411 hour, 35 minutes, 41 secondsmethod uh say export async function refresh token
1:35:511 hour, 35 minutes, 51 secondsand we're going to do the same thing here. We going to have this and then we're going to return the access token
1:35:581 hour, 35 minutes, 58 secondsrefresh token and the expired at we're going to create. So let me call this is to get the user information. So we're going to say con export async get user
1:36:081 hour, 36 minutes, 8 secondsall and we're going to say fetch. So let me close this here. So we're going to pass in the header the barrier token and
1:36:151 hour, 36 minutes, 15 secondswe going to pass the accept user agent base 64 agent and here I'm going to say
1:36:221 hour, 36 minutes, 22 secondsif not okay let's return this and then we're going to get the data. So I don't
1:36:301 hour, 36 minutes, 30 secondswant to get all the information. So I'm going to say constant data and then we're just going to return only the
1:36:371 hour, 36 minutes, 37 secondsGitHub ID. So say GitHub id and then we going to so get a GitHub uh login.
1:36:471 hour, 36 minutes, 47 secondsSo this is the only thing we need and now we have this method now. And the last method we're going to create is to
1:36:531 hour, 36 minutes, 53 secondsget all repos. So I say export um async
1:37:001 hour, 37 minutesfunction get GitHub repose.
1:37:091 hour, 37 minutes, 9 secondsLet me let me make a say get GitHub repos and we're going to pass in the access
1:37:161 hour, 37 minutes, 16 secondstoken. So we're going to define let's say uh let's do constant repos
1:37:251 hour, 37 minutes, 25 secondswhich is going to be I'm going to set the type here. So let me add the type here. So I've placed it here and
1:37:341 hour, 37 minutes, 34 secondsGitHub repo the repository and then I'm going to come down here. I'm going to set like this and let's say I say let
1:37:431 hour, 37 minutes, 43 secondspage um one and then we can just say y true
1:37:511 hour, 37 minutes, 51 secondsand then we going to say constant response
1:37:571 hour, 37 minutes, 57 secondsis equals to await page and we're going to use the API GitHub
1:38:041 hour, 38 minutes, 4 secondsAPI user um repo per page we can say 100 page is going to be page and then I'm going to say um and
1:38:141 hour, 38 minutes, 14 secondssort updated then we're going to also add and sorry and direction is going to be decrease is
1:38:231 hour, 38 minutes, 23 secondssending and then we are going to add
1:38:291 hour, 38 minutes, 29 secondslet's add affiliation owner collaborator um organization members then we are
1:38:371 hour, 38 minutes, 37 secondsgoing to pass in header Yeah. So let me pass in.
1:38:411 hour, 38 minutes, 41 secondsYeah. Let's pass object headers and pass in the access token. So let's say authorization
1:38:501 hour, 38 minutes, 50 secondsbearing and then the user agent and accept. So now we have this.
1:38:571 hour, 38 minutes, 57 secondsSo let me close this first.
1:39:001 hour, 39 minutesAnd there we're going to say if not okay.
1:39:061 hour, 39 minutes, 6 secondsSo let's return this. Now we can say constant page reposry and then we can just say repo.push repo.
1:39:181 hour, 39 minutes, 18 secondsThen I also want to say if um not response
1:39:251 hour, 39 minutes, 25 secondsresponse to header include this we're going to break and then we're going to so let me
1:39:321 hour, 39 minutes, 32 secondschange this here response and then below here we're going to say page++ and then we can return the repositories.
1:39:421 hour, 39 minutes, 42 secondsSo we are done with all the method.
1:39:451 hour, 39 minutes, 45 secondsNow we are going to go ahead and start working on the controllers and the uh service. So let me save this.
1:39:581 hour, 39 minutes, 58 secondsSo let's create the controller. So I'm going to um inside the controller and I'm going to say github
1:40:071 hour, 40 minutes, 7 secondsum githubcontrollers txt. So I'm going to also create. So I'm going to ask command code to create the
1:40:161 hour, 40 minutes, 16 secondsGitHub um the controllers and the surface. So let's open the terminal and then I'm going to say should create the
1:40:231 hour, 40 minutes, 23 secondsconnect GitHub controller the GitHub call controller and and ripple the get
1:40:301 hour, 40 minutes, 30 secondsrepos controller also we can also add this connect user controller. So let's say um create
1:40:401 hour, 40 minutes, 40 secondsthe uh GitHub um GitHub let's say GitHub O
1:40:511 hour, 40 minutes, 51 secondslet's say now let's create the GitHub
1:41:001 hour, 41 minutesa GitHub connect controller
1:41:071 hour, 41 minutes, 7 secondsUm, call back call back and the repost
1:41:141 hour, 41 minutes, 14 secondsand let's say controller. Let me do let me remove this
1:41:221 hour, 41 minutes, 22 secondsrepost and controller and service.
1:41:311 hour, 41 minutes, 31 secondsSo well what I can do I can just create the connect first. Let's do connect first and service only.
1:41:401 hour, 41 minutes, 40 secondsSo we're going to do them one after the other. I say only and let's click on enter. So I forgot. Let me cancel this.
1:41:461 hour, 41 minutes, 46 secondsYou can use escape key. I'm going to um click on the arrow key. Then I'm going to point to the file I've just created.
1:41:551 hour, 41 minutes, 55 secondsSo I'm going to say GitHub controller. Then click on enter.
1:42:011 hour, 42 minutes, 1 secondand let's wait for it to start. It's going to create the um connect GitHub controller. Yeah, we're going to ask to
1:42:081 hour, 42 minutes, 8 secondscreate the um callback and the get GitHub repo controller. So, it's reading
1:42:151 hour, 42 minutes, 15 secondsthe files the um model the o another of the files. So, let's wait for
1:42:221 hour, 42 minutes, 22 secondsit. So, now it want to create the service file. So, let's click on enter and then let's click enter. So now um we
1:42:311 hour, 42 minutes, 31 secondscan see it added all the control. Wow, it added the um all the method. So let's see.
1:42:411 hour, 42 minutes, 41 secondsSo it is done. Let me just cancel this and let's go over. So now we have the GitHub connect controller. So this is
1:42:501 hour, 42 minutes, 50 secondsgoing to take in we're going to get the user as user document. So let me see inside.
1:42:581 hour, 42 minutes, 58 secondsSo let's create inside the TX.
1:43:011 hour, 43 minutes, 1 secondLet's create express sorry express dx
1:43:101 hour, 43 minutes, 10 secondsand then I'm just going to add um id in the um global uh in the user. So we can go back into
1:43:191 hour, 43 minutes, 19 secondsthe github controller. Now in all of this I can just say request um request do user dot
1:43:281 hour, 43 minutes, 28 secondsunderscore ID and then we can just remove this here.
1:43:401 hour, 43 minutes, 40 secondsSo let's just say to to string.
1:43:481 hour, 43 minutes, 48 secondsSo this can be undefined. Yeah, you can see the error has stop.
1:44:001 hour, 44 minuteschange this to user ID sort of um so it should be user ID so the user from the
1:44:081 hour, 44 minutes, 8 secondsclient side we're going to send in the um query to redirect um sorry the
1:44:141 hour, 44 minutes, 14 secondsredirect to so this is fine so so let's return let's return
1:44:231 hour, 44 minutes, 23 secondsresponse let's add a status HTTP. Okay.
1:44:341 hour, 44 minutes, 34 secondsSo now let's go ahead and look at the uh service. So I'll go into GitHub
1:44:421 hour, 44 minutes, 42 secondsum get GitHub connect URL and we can see we pass in the user ID the directory and then we can see that it imports the
1:44:511 hour, 44 minutes, 51 secondscreate GitHub connect URL which we have here. And last I'm just going to also check for the user ID. So I'm just going
1:44:581 hour, 44 minutes, 58 secondsto say if um if not user ID user unable to find user or user
1:45:061 hour, 45 minutes, 6 secondslet's just use unauthorized instead unauoriz
1:45:171 hour, 45 minutes, 17 secondsum authentication required to connect GitHub account and this is fine. So and
1:45:251 hour, 45 minutes, 25 secondsthen this is okay. So we can go into the controller and let's look at the next one. So it also implemented the call
1:45:321 hour, 45 minutes, 32 secondsback the GitHub call back um controller and we can see that it's got the state
1:45:391 hour, 45 minutes, 39 secondsthe um the code and the state. So what I'm going to do I'm going to use create a validator. So let's create GitHub
1:45:491 hour, 45 minutes, 49 secondsgithub validator.tx TX
1:45:561 hour, 45 minutes, 56 secondsand I'm just going to import let's import Zord from
1:46:051 hour, 46 minutes, 5 secondsZ and then I'm just going to paste this here.
1:46:111 hour, 46 minutes, 11 secondsSo we can use this inside this um GitHub controller. So here instead of um using
1:46:181 hour, 46 minutes, 18 secondsas here so I'm just going to say uh so let me remove this.
1:46:241 hour, 46 minutes, 24 secondsWe're going to just pass in GitHub callback query schema and then we're going to just pass this. I'm just going to import this.
1:46:351 hour, 46 minutes, 35 secondsSo, let me see if I export this. So, let me export it and then let me import it here.
1:46:531 hour, 46 minutes, 53 secondsSo we can see this is fine. So I'm just going to just change this to uh GitHub
1:47:011 hour, 47 minutes, 1 secondGitHub call back service.
1:47:061 hour, 47 minutes, 6 secondsSo we pass in the code and state and then we can just return return this and then add a state status too.
1:47:171 hour, 47 minutes, 17 secondsSo let me change this again.
1:47:211 hour, 47 minutes, 21 secondsAI is changing this call back service.
1:47:351 hour, 47 minutes, 35 secondsSo I just update this here and then let's go into the service and we can just change in
1:47:451 hour, 47 minutes, 45 secondsI'll just change this to GitHub call back service and the error should stop.
1:47:521 hour, 47 minutes, 52 secondsSo now here we have the we pass in the code and state and to from the verify or
1:47:591 hour, 47 minutes, 59 secondsstate and then we pass in the state here. So now we are going to so instead of this I'm just going to remove this.
1:48:071 hour, 48 minutes, 7 secondsWe can just remove this. Then I'm just going to remove this catch. So since we wrap this we try catch in the AC can is
1:48:151 hour, 48 minutes, 15 secondsgoing to catch the error. So I'm going to just say constant.
1:48:201 hour, 48 minutes, 20 secondsSo I'll just say constant um token. I'll just call it token data.
1:48:281 hour, 48 minutes, 28 secondsAnd this is going to be equals to the exchange GitHub code for tokco. And then we're passing the code. Now we can get
1:48:351 hour, 48 minutes, 35 secondsthe user data. I say constant user data is going to be equals to github user to
1:48:441 hour, 48 minutes, 44 secondsopen data access to. Now I'm going to just remove all of this. It's w here. So let me just move this.
1:49:001 hour, 49 minutesSo, I'm just going to say um so we can just say await GitHub um account find and update. Then
1:49:101 hour, 49 minutes, 10 secondswe're going to pass in the user ID. Then this is going to be uh let me remove this. I'll just say user ID and then we can pass this here.
1:49:231 hour, 49 minutes, 23 secondsSo C string error find and update user ID user ID is this of string.
1:49:361 hour, 49 minutes, 36 secondsOkay. So the problem the problem why this is showing underscore I'm showing um error it's coming from the GitHub
1:49:441 hour, 49 minutes, 44 secondsaccount model. So I need to remove the schema and the error should stop now. So let's go into GitHub service and now we
1:49:521 hour, 49 minutes, 52 secondscan see the error has stopped. So then we're going to remove this. So we're going to remove this.
1:49:591 hour, 49 minutes, 59 secondsSo we're going to um say redirect to. So if redirect was not pass I can just say constant
1:50:071 hour, 50 minutes, 7 secondsredirect say URL is equals to redirect to
1:50:221 hour, 50 minutes, 22 secondsso redirect to so if redirect to is passed. So let me copy this. So if a directory is passed, we're
1:50:301 hour, 50 minutes, 30 secondsgoing to pass it else we just going to build this. So we're going to say env
1:50:361 hour, 50 minutes, 36 secondssorry EMV config
1:50:431 hour, 50 minutes, 43 secondsdot front end origin and then we can say slash and we can
1:50:511 hour, 50 minutes, 51 secondsjust do new github is equals to connected
1:51:001 hour, 51 minutesthen let's return here So just say let's direct and then I'm going to just
1:51:101 hour, 51 minutes, 10 secondssave this. So now we've update the call back service and inside get controller and we can see that this
1:51:171 hour, 51 minutes, 17 secondsis return here too. So let me remove this.
1:51:221 hour, 51 minutes, 22 secondsNow let's create the controller to fetch all the repos. So I'm going to say export
1:51:321 hour, 51 minutes, 32 secondsconstant get GitHub um GitHub repos
1:51:411 hour, 51 minutes, 41 secondscontroller and we say AC handler
1:51:521 hour, 51 minutes, 52 secondsand let's pass in the request which is of type request
1:51:591 hour, 51 minutes, 59 secondsand response is of type response and then let's return.
1:52:081 hour, 52 minutes, 8 secondsSo we can get the user ID.
1:52:131 hour, 52 minutes, 13 secondsUser ID is equals to request dot user dot ID.
1:52:231 hour, 52 minutes, 23 secondsAnd then we can say constant data is equals to await
1:52:291 hour, 52 minutes, 29 secondsum let's call this get up service
1:52:391 hour, 52 minutes, 39 secondssorry repose service
1:52:481 hour, 52 minutes, 48 secondsand then we're going to pass in the user ID and Let's return
1:52:591 hour, 52 minutes, 59 secondsresponse status http http status. Okay.
1:53:161 hour, 53 minutes, 16 secondsAnd we're going to just do a JSON and we just return the data.
1:53:251 hour, 53 minutes, 25 secondsSo let me just pass data is going to be data and let's go ahead and
1:53:341 hour, 53 minutes, 34 secondsuh create this method. So let's go into the GitHub service and let's do this here.
1:53:421 hour, 53 minutes, 42 secondsSo it it created the get access token.
1:53:451 hour, 53 minutes, 45 secondsSo let me so you can see fresh the user user ID. So I just replace this with user ID like this.
1:53:591 hour, 53 minutes, 59 secondsAnd then if account is not found, you just throw an exception. Then so you say if account um if account token expired
1:54:081 hour, 54 minutes, 8 secondsexpired um expired at refresh token. Then we're going to
1:54:161 hour, 54 minutes, 16 secondsdecrypt the refresh token. Then we're going to call the refresh github token method.
1:54:231 hour, 54 minutes, 23 secondsPass in the refresh token. And then we can then um account access token. Then
1:54:301 hour, 54 minutes, 30 secondswe're going to encrypt the newly fetch access token. And if we fresh token um passed or it is we're going to add it.
1:54:391 hour, 54 minutes, 39 secondsThen we're going to also update the uh token expired. And then we're going to save in the account. So this is so and this is going to throw an error.
1:54:511 hour, 54 minutes, 51 secondsSo let's and this is going to return the um token. So this is fine. So instead of
1:54:571 hour, 54 minutes, 57 secondsI'll just change this to get GitHub access token. So now let's create the
1:55:051 hour, 55 minutes, 5 secondsmethod to fetch the service to fetch the repos. So say constant
1:55:121 hour, 55 minutes, 12 secondsum get. So let me go ahead and copy this get repos service. So go into the into
1:55:191 hour, 55 minutes, 19 secondsthe uh service and let me replace this with this and we can see async and we're
1:55:261 hour, 55 minutes, 26 secondsgoing to get we're going to pass in so the user ID is going to be passed. So let's say user ID type string
1:55:351 hour, 55 minutes, 35 secondsand let's return this. So I say if not user
1:55:411 hour, 55 minutes, 41 secondsID then we can just show new bad request
1:55:491 hour, 55 minutes, 49 secondsor let's say new unauthorized exception and then we're going to give this uh let's say
1:55:571 hour, 55 minutes, 57 secondsunauuthorize or let's say usern
1:56:091 hour, 56 minutes, 9 secondsLet me change it to unauthorized instead.
1:56:141 hour, 56 minutes, 14 secondsSo we have this now. So we can call the method constant. Um let's get the access token first.
1:56:241 hour, 56 minutes, 24 secondsLet's say get get GitHub access token. Let's pass in the user ID.
1:56:341 hour, 56 minutes, 34 secondsAnd then we can say constant repos is equals to await
1:56:421 hour, 56 minutes, 42 secondsget github repos and we pass in the access token.
1:56:541 hour, 56 minutes, 54 secondsSo now we can just return we can return.
1:57:001 hour, 57 minutesSo I'm just going to map this here. So let me come over here
1:57:081 hour, 57 minutes, 8 secondsaccess to so I'm just going to add a wait here and the error should stop.
1:57:231 hour, 57 minutes, 23 secondsSo now let's map this. I'll just say um repose.
1:57:291 hour, 57 minutes, 29 secondsUh let's call this um what should I give this mapped repost and this is going to be post to right.
1:57:401 hour, 57 minutes, 40 secondsSo we're going to say map repos map. We're going to pass in the ID name, full name, um HTTP URL, the clone URL.
1:57:501 hour, 57 minutes, 50 secondsSo the clone URL is going to have the kit. Why this is just going to have the normal URL. Then we say um private
1:57:571 hour, 57 minutes, 57 secondsdefault branch description fork and then the owner. So we can just pass this. I
1:58:061 hour, 58 minutes, 6 secondsdon't think we even need the owner. Um the login we don't need it.
1:58:141 hour, 58 minutes, 14 secondsSo I'll just comment it out. I don't think we need it. So let's return.
1:58:201 hour, 58 minutes, 20 secondsSo let me remove this and let's return repos here.
1:58:301 hour, 58 minutes, 30 secondsSo ripples is going to be map reple.
1:58:431 hour, 58 minutes, 43 secondsSo I think now the error should stop. So let's go back to G. So let's import this.
1:58:551 hour, 58 minutes, 55 secondsSo now we are done with this this GitHub now. So let's look at the disconnect in GitHub. So GitHub disconnect
1:59:051 hour, 59 minutes, 5 secondsuh controller that we have the user ID. So let's just change this to
1:59:121 hour, 59 minutes, 12 secondsum dot ID and change this to ID.
1:59:191 hour, 59 minutes, 19 secondsAnd then we can just say user ID. I'm going to remove this.
1:59:271 hour, 59 minutes, 27 secondsSo we can return these two. So return
1:59:361 hour, 59 minutes, 36 secondsreturn uh response of status and we say http status dot.
1:59:481 hour, 59 minutes, 48 secondsOkay.
1:59:531 hour, 59 minutes, 53 secondsSo if we go into disconnect github and we can just remove this
2:00:042 hours, 4 secondsand then we can see if no account we're going to throw an error and then we just say await um account disconnect. So let
2:00:112 hours, 11 secondsme just return success true.
2:00:202 hours, 20 secondsOh, let's change this to instead of success, let me use connected us.
2:00:282 hours, 28 secondsSo, this is fine. So, we have this now.
2:00:302 hours, 30 secondsSo, inside the controller, everything is correct. So, let's go into So, I can remove this now and let's go into the
2:00:392 hours, 39 secondsroute. So, inside the route. So, you didn't create the route. So, I'll say GitHub.
2:00:482 hours, 48 secondsCX and we can copy this. So copy this, paste it here.
2:00:562 hours, 56 secondsAnd now we can change this. So I'll change this to G. Then this is going to so I can also connect combine this together like this.
2:01:062 hours, 1 minute, 6 secondsAnd I'm going to change this to get let's say connect.
2:01:142 hours, 1 minute, 14 secondsAnd let's import passport passport JWT authenticate JWT. And we're going to uh
2:01:232 hours, 1 minute, 23 secondsgo into controller and let's copy GitHub connect controller. And then I'm going to just update this here. And I'm going
2:01:302 hours, 1 minute, 30 secondsto I change this to instead of say GitHub
2:01:382 hours, 1 minute, 38 secondscontroller and I'm going to paste it here. So now this one we're going to say call back.
2:01:442 hours, 1 minute, 44 secondsSo let me remove this and this is going to be get
2:01:522 hours, 1 minute, 52 secondsand this is going to be call back call back and then we can uh we can go
2:02:022 hours, 2 minutes, 2 secondsto controller and let's say GitHub call back controller and then we're going to just
2:02:082 hours, 2 minutes, 8 secondspass it here and let's import it to then I'm going remove this
2:02:162 hours, 2 minutes, 16 secondsand this is going to so get and I'm going to uh let me remove this.
2:02:262 hours, 2 minutes, 26 secondsSo I'll say repos and then we're going to pass in passport
2:02:352 hours, 2 minutes, 35 secondshere and let's go into the controller and let's copy get GitHub repo controller
2:02:422 hours, 2 minutes, 42 secondsand let's update this and let's import it too. And lastly, we can just say disconnect.
2:02:512 hours, 2 minutes, 51 secondsAnd I'm going to just set delete.
2:03:012 hours, 3 minutes, 1 secondAnd I'm going to remove this. I'll set this to disconnect. Disconnect.
2:03:102 hours, 3 minutes, 10 secondsWe're going to go into the GitHub controller and let's copy GitHub disconnect controller.
2:03:162 hours, 3 minutes, 16 secondsAnd let me update this. And then let's import it.
2:03:212 hours, 3 minutes, 21 secondsAnd then we're going to return GitHub route. And then let's go into index.tx.
2:03:302 hours, 3 minutes, 30 secondsAnd we can duplicate this. And I'm going to say GitHub.
2:03:342 hours, 3 minutes, 34 secondsAnd then inside the GitHub route, we can just copy this inside index.tx. We can pass it here. And let's import it.
2:03:462 hours, 3 minutes, 46 secondsAnd um so we are done with this now. So we're going to test this on the client side once we once we implement the front
2:03:532 hours, 3 minutes, 53 secondsend. So now we are done with the GitHub connection uh the GitHub O connect and
2:03:592 hours, 3 minutes, 59 secondsthen to fetch all the repos. Now we go I I also forgot inside the EMV we've now
2:04:072 hours, 4 minutes, 7 secondsretrieved the GitHub clients and GitHub and client secret and we've not generated the secret for this. So let's
2:04:142 hours, 4 minutes, 14 secondsdo it now. Open your terminal. So I'm going to open my terminal. Let me go into back end and I'm going to cancel
2:04:212 hours, 4 minutes, 21 secondsthe server. I'll clear my terminal and I'm going to run this. So open SSL to generate the secret. It's going to
2:04:292 hours, 4 minutes, 29 secondsgenerate a secret. So let's wait for this.
2:04:362 hours, 4 minutes, 36 secondsWhy is it taking time?
2:04:402 hours, 4 minutes, 40 secondsSo it has generate this. So I'm going to copy it. I'll paste it here.
2:04:482 hours, 4 minutes, 48 secondsSo let's generate another one.
2:04:522 hours, 4 minutes, 52 secondsSo copy and then I'm going to paste it here. So
2:04:592 hours, 4 minutes, 59 secondslet's go to GitHub and get the GitHub client ID and secret. So I'll go on the client side.
2:05:062 hours, 5 minutes, 6 secondsSo I'm going to plug into my GitHub account. So I can click here and then I'm going to go to settings.
2:05:162 hours, 5 minutes, 16 secondsLet's scroll down to developer settings and then let's go to O app. And then we
2:05:242 hours, 5 minutes, 24 secondscan click on new and let's give this a name. a base 64.
2:05:312 hours, 5 minutes, 31 secondsUm for the home uh we need to pass in homepage URL and author
2:05:382 hours, 5 minutes, 38 secondsback URL. So I'm going to go back. So I'm going to use Benro. So you can just
2:05:462 hours, 5 minutes, 46 secondssearch for this and make sure you log into your account.
2:05:512 hours, 5 minutes, 51 secondsSo I've already um um installed Ang. So is I've already I already have it in my system. So let me quickly log in first.
2:06:022 hours, 6 minutes, 2 secondsSo once you install you just have to install this and then add config add and then we can run this. So
2:06:102 hours, 6 minutes, 10 secondsI already have it in my system. So I'm just going to run this. Let me go back to the code and I'm going to open my terminal and let me just run this here.
2:06:212 hours, 6 minutes, 21 secondsSo our back end is running at 8,000. So, I'm just going to say sorry 8,000
2:06:282 hours, 6 minutes, 28 secondsand let's wait for this.
2:06:342 hours, 6 minutes, 34 secondsSo, copy this now.
2:06:382 hours, 6 minutes, 38 secondsI'll go into the EMV and then I can just say base URL.
2:06:482 hours, 6 minutes, 48 secondsSo, let me just comment this out and I'm going to replace this with it.
2:06:562 hours, 6 minutes, 56 secondsSo let's um let's go back to the front end. So what I'm going to do, I'm just
2:07:032 hours, 7 minutes, 3 secondsgoing to go into index and I'm going to change this to slash. So the health is going to be uh slash. So I'll change
2:07:112 hours, 7 minutes, 11 secondsthis to to slash. So let me close this
2:07:172 hours, 7 minutes, 17 secondsand then let me go to the um browser and then I can add this here.
2:07:242 hours, 7 minutes, 24 secondsSo O I'll just add it here and this will point to the health endpoint URL. So we're going to add the call back and the
2:07:312 hours, 7 minutes, 31 secondscall back we can go back to the code and inside the socials social index
2:07:392 hours, 7 minutes, 39 secondsand we should scroll up and we should see uh sorry this should not be this should be GitHub call back. I think that's what I have in the route. So
2:07:482 hours, 7 minutes, 48 secondslet's go to GitHub route. We should say GitHub um call back. Yeah. So, I'll go back to
2:07:582 hours, 7 minutes, 58 secondsI'll go back to um index.tx and then we can just copy this
2:08:052 hours, 8 minutes, 5 secondsand let's go back to the browser and we can just pass it here.
2:08:112 hours, 8 minutes, 11 secondsSo, slash github/back and we can just click on register app
2:08:192 hours, 8 minutes, 19 secondsand now we can copy the client ID in client secret. So go back to the code my EMV and I'm going to paste it here.
2:08:302 hours, 8 minutes, 30 secondsSo let's go back again and let's copy.
2:08:332 hours, 8 minutes, 33 secondsI'll click on generate new client secret. So I'm going to delete this. So let me verify my email first. Now I can copy this. Copy this now. So I'll copy
2:08:422 hours, 8 minutes, 42 secondsthe client secret and then I'm going to go back to the code editor and I'm going to paste it here. So now we have I also
2:08:522 hours, 8 minutes, 52 secondsforgot to run the server. So let me click here and let's run the server and
2:08:582 hours, 8 minutes, 58 secondscd back end and let's say mpn rundev
2:09:112 hours, 9 minutes, 11 secondsand let's uh let me create the github https
2:09:172 hours, 9 minutes, 17 secondsso we can test it. HTTP and then I'm going to quickly add all
2:09:242 hours, 9 minutes, 24 secondsthe HTTP. So now I've already added this HTTP so we can try out local to connect on GitHub. So server is running. So
2:09:322 hours, 9 minutes, 32 secondslet's click on send and okay. So I need to login first. So let me quickly log my account.
2:09:412 hours, 9 minutes, 41 secondsSo I log to GitHub and then and let me click on send now.
2:09:472 hours, 9 minutes, 47 secondsAnd you can see the URL. So I can copy this URL now. And let's go to the browser.
2:09:562 hours, 9 minutes, 56 secondsAnd I'm going to paste it here. And something is wrong.
2:10:062 hours, 10 minutes, 6 secondsOkay.
2:10:092 hours, 10 minutes, 9 secondsSo I think I made a mist. I didn't copy this way. So let me go back to the code editor and click on it.
2:10:182 hours, 10 minutes, 18 secondsSo I'm just going to do that now. So I've seen the issue. So I had to click on this again. So I had to go ahead and save this because the client ID was not
2:10:272 hours, 10 minutes, 27 secondsvisible. You can see the client ID now is added here. So I tried to and I click on the send again. That's why we can see
2:10:342 hours, 10 minutes, 34 secondsthe client ID here. So, so make sure to check the uh env point ID is the same as what we have.
2:10:452 hours, 10 minutes, 45 secondsUm, yeah. And inside the social index tx. So, the client ID is passed here. So, now let me try this again.
2:10:532 hours, 10 minutes, 53 secondsHopefully, it should work. So, I'll copy this now again and I'll go to the browser and let's see.
2:11:052 hours, 11 minutes, 5 secondsI'll paste this. Click on send. Now we can see that it work. So we can verify the session and make sure the angrog is
2:11:152 hours, 11 minutes, 15 secondswork for verify. Make sure um angrog is running. So let's go back to the browser. And let's click on continue.
2:11:262 hours, 11 minutes, 26 secondsAnd this is going to ask for read only you can see. And then we're going to click on um so repost public and
2:11:342 hours, 11 minutes, 34 secondsprivate. and unauuthorize and let's see visit.
2:11:452 hours, 11 minutes, 45 secondsSo we can see this now.
2:11:482 hours, 11 minutes, 48 secondsSo this is so it's trying to go back to to GitHub.
2:11:552 hours, 11 minutes, 55 secondsSorry, I think we made a mistake. So let's go back here.
2:12:022 hours, 12 minutes, 2 secondsuh inside sorry inside the settings
2:12:092 hours, 12 minutes, 9 secondsso uh developer settings then go to o
2:12:162 hours, 12 minutes, 16 secondslet's edit this so the call back I forgot to add API so API
2:12:242 hours, 12 minutes, 24 secondsclick on update so let's do the same thing inside the code.
2:12:312 hours, 12 minutes, 31 secondsSo inside the index text, I forgot to add API here
2:12:392 hours, 12 minutes, 39 seconds/ API. Let's try this again. So let's go into GitHub HTTP and let's click on send and this should give us the connect URL.
2:12:512 hours, 12 minutes, 51 secondsSo let's copy this now and let me head over to the browser and I'm going to paste it here again.
2:13:002 hours, 13 minutesClick on enter and now I'm going to click on continue.
2:13:072 hours, 13 minutes, 7 secondsLet's see. Now we can see GitHub account connected successfully and we can see
2:13:132 hours, 13 minutes, 13 secondsredirect to. So this is working fine. So I think we also made a mistake. This should redirect to the front end
2:13:202 hours, 13 minutes, 20 secondsimmediately. So let's go back to the code and inside the controller
2:13:302 hours, 13 minutes, 30 secondsinside GitHub controller. So let me GitHub controller. So yeah I'll scroll to call back instead of returning this
2:13:392 hours, 13 minutes, 39 secondswe just like this. So response redirect to redirect to. So this so easy. So we can check this now.
2:13:512 hours, 13 minutes, 51 secondsSo inside the GitHub. So let me open.
2:13:592 hours, 13 minutes, 59 secondsIf I go into MongoDB, let me reload this.
2:14:102 hours, 14 minutes, 10 secondsSo let me just refresh.
2:14:142 hours, 14 minutes, 14 secondsNow open the database and we can see one in there.
2:14:232 hours, 14 minutes, 23 secondsSo we can see one is added. Now we can finish in the repo. So I can go back into
2:14:302 hours, 14 minutes, 30 secondsexplorer then go to GitHub and then we can click on get repo.
2:14:362 hours, 14 minutes, 36 secondsSo let's see now we can see that this has fetch all the repos I have in that
2:14:422 hours, 14 minutes, 42 secondsaccount. So this is great. So let's try and delete this to see. So click on send.
2:14:512 hours, 14 minutes, 51 secondsSo disconnect field.
2:14:562 hours, 14 minutes, 56 secondsSo let's check in the route. Um GitHub route.
2:15:042 hours, 15 minutes, 4 secondsOkay. I forgot to put slash here.
2:15:072 hours, 15 minutes, 7 secondsSo let me go back into GitHub. Make sure the server is running
2:15:172 hours, 15 minutes, 17 secondsand let me click on send.
2:15:212 hours, 15 minutes, 21 secondsNow we can see GitHub disconnected. So we can come over here and let's just reload this and we can see Zo is inside
2:15:292 hours, 15 minutes, 29 secondsthe GitHub account table. So great. So this is working fine. So now let's go ahead and start working on the sessions.
Chapter 7: SandBox Setup
2:15:382 hours, 15 minutes, 38 secondsIn this chapter, we are going to set up Ostach. So, Upstatch box is what we're going to use um for the sandbox in a
2:15:472 hours, 15 minutes, 47 secondsproject. So, just make sure to come over to upstart.com and to sign up into just log or sign up and we're going to be
2:15:572 hours, 15 minutes, 57 secondsusing the um upstart box. So, I've already lo once you lo and then we're going to create API key.
2:16:062 hours, 16 minutes, 6 secondsSo I already have this already. So we can click here to create a box. But we're going to do it in the code. And if I click here API key
2:16:152 hours, 16 minutes, 15 secondsand this should create a new API key for us. So let me click on this.
2:16:242 hours, 16 minutes, 24 secondsBefore we create the API key, let's look at the quick startup the quick start. So the first we're going to do we're going to have to install um upside and then we
2:16:332 hours, 16 minutes, 33 secondscan see example of how to use it. So we're not going to use it with this.
2:16:362 hours, 16 minutes, 36 secondsWe're going to we have the code and this is if you're using the agent inside but what we're going to use it for. We're
2:16:442 hours, 16 minutes, 44 secondsgoing to use this for we're going to do execute files G. So these are it we're going to use it for and you can go to the
2:16:522 hours, 16 minutes, 52 secondsdocumentation. Just click on click on this talk and it will take you here and you can see the quick and start and
2:17:022 hours, 17 minutes, 2 secondswe can see you have to install set API key. So we need to um add obstach box API key and then to create a box we just
2:17:102 hours, 17 minutes, 10 secondspass in box create and then runtime node. So you can add um Python runtime and other runtime. So you can see it
2:17:182 hours, 17 minutes, 18 secondshere. And this is optional. We're not going to use agent. So we're going to
2:17:252 hours, 17 minutes, 25 secondsjust go straight to um let me go to box basic.
2:17:322 hours, 17 minutes, 32 secondsAnd then you can just read they have G shell P system snapshot and then you can see all of the runtime they have which
2:17:402 hours, 17 minutes, 40 secondsyou can change and then let's just go straight to G. So this is the most
2:17:462 hours, 17 minutes, 46 secondsimportant one here. If I click on G and now we can see how to configure G.
2:17:542 hours, 17 minutes, 54 secondsSo we're going to uh add the G. So we have the access token already saved. So we're going to pass in the access token
2:18:032 hours, 18 minutes, 3 secondsin the obstach box. So we can use the G which is inside the sandbox. So we can
2:18:092 hours, 18 minutes, 9 secondssee um you also have to you can add in G identity. So we just going to add our name like a base 64 and the email. So
2:18:182 hours, 18 minutes, 18 secondsonce the um agent push to uh push to the repo we'll be able to see the um changes
2:18:262 hours, 18 minutes, 26 secondsor the u push came from us. Then we can see this is how to clone a repository
2:18:332 hours, 18 minutes, 33 secondsbox. Clone then you pass in the default branch and that's why we have the default branch. Then we have um a status
2:18:442 hours, 18 minutes, 44 secondsum div. Then we have commit push uh open p request. So we have shell here.
2:18:532 hours, 18 minutes, 53 secondsSo click on shell. Then we are going to use this as you can see it we can use this to we're going to
2:19:012 hours, 19 minutes, 1 secondcreate a bash tool which a can run um different scripts inside it. So we also have file system. So let's go to file.
2:19:102 hours, 19 minutes, 10 secondsSo we're going to come up come back to this once we start working on the session. But for now we're just going to set up this first. Then for the file
2:19:182 hours, 19 minutes, 18 secondssystem you can you can read file. You can see file read file.right file um
2:19:242 hours, 19 minutes, 24 secondslist. This will list all the files and some other stuff you can read from here.
2:19:302 hours, 19 minutes, 30 secondsSo now let's just go ahead and create the API key. So click on this again.
2:19:372 hours, 19 minutes, 37 secondsNow we can see the API key. So I'll copy this. Click on okay. And in the if you look at the doc if I go to quick start.
2:19:482 hours, 19 minutes, 48 secondsSo we need to create add this up box API key. So let's go to the code and let's go to the EMV.
2:20:012 hours, 20 minutes, 1 secondSo I already added it here. So I'm just going to paste in the API key. Now let's go back and install this package. So
2:20:082 hours, 20 minutes, 8 secondsI'll go back to browser and I'm going to copy this and let's go to the code. So
2:20:152 hours, 20 minutes, 15 secondsI'm going to install it. Then I'm going to show you the version. So cancel my server and I'm going to paste this and install.
2:20:232 hours, 20 minutes, 23 secondsSo once it's installed, I'm going to show you the version of installed. So now it has installed. So let me go into packet.json. And if I scroll down to dependency, you should see 0.4.3.
2:20:352 hours, 20 minutes, 35 secondsSo let me close this. And now let me close all of this.
2:20:412 hours, 20 minutes, 41 secondsCollapse this. And inside the back end, I'm going to create inside the leaf folder I'm going to create a file. Uh let's create
2:20:502 hours, 20 minutes, 50 secondssandbox.x here.
2:20:562 hours, 20 minutes, 56 secondsAnd then inside the sandbox dx. So since we are using we are using common jx. So if you look at the um ts config here we
2:21:052 hours, 21 minutes, 5 secondsare using common js and upstarch the off box is using. So what we're going to
2:21:122 hours, 21 minutes, 12 secondswe're going to have to um import the off um package dynamically. So we're going
2:21:202 hours, 21 minutes, 20 secondsto dynically um import it. So I'm just going to import the type here. So I'll say import and type.
2:21:332 hours, 21 minutes, 33 secondsSo I'm going to say box and this is going to come from at box here.
2:21:412 hours, 21 minutes, 41 secondsSo now I'm going to say constant get box access equals to
2:21:502 hours, 21 minutes, 50 secondsand let's just say import of search box. So just remove this
2:22:032 hours, 22 minutes, 3 secondslike this. So now let's create the method. So let's say export export constants create box for session.
2:22:172 hours, 22 minutes, 17 secondsSo since we're going to be using it only for the session. So I say create box for session and it's going to be async
2:22:262 hours, 22 minutes, 26 secondsand this is going to let's sorry
2:22:342 hours, 22 minutes, 34 secondslet's return this and we're going to pass in the access token like I showed you we need to pass
2:22:422 hours, 22 minutes, 42 secondsin access token since we're using it. So I'm going to say if not as a token then
2:22:512 hours, 22 minutes, 51 secondswe can just throw an error. Now we can say constant box a
2:23:012 hours, 23 minutes, 1 seconduh a get box and then we can say um
2:23:092 hours, 23 minutes, 9 secondslet's just change this to okay let's change this to box model is okay. So let's just sorry let me just do
2:23:182 hours, 23 minutes, 18 secondslike this box here and then we can just say return
2:23:302 hours, 23 minutes, 30 secondsbox dot create one time
2:23:392 hours, 23 minutes, 39 secondsis going to be node then it.
2:23:452 hours, 23 minutes, 45 secondsWe're going to pass in token access token and then let's pass in username.
2:23:542 hours, 23 minutes, 54 secondsSo username we're going to say base 64 AI.
2:24:042 hours, 24 minutes, 4 secondsAnd for the email user email we can just give a base 64 at
2:24:152 hours, 24 minutes, 15 secondsand just say base 64.ai.
2:24:202 hours, 24 minutes, 20 secondsThis is fine. So now we're going to create another method. So constant export constant get box.
2:24:292 hours, 24 minutes, 29 secondsSo let me just instead of u I'll say create box and let me change
2:24:352 hours, 24 minutes, 35 secondsthis to create box get box model module and I'm going to change this then
2:24:432 hours, 24 minutes, 43 secondswe have get box and it's going to be async we're going to pass in the box ID
2:24:492 hours, 24 minutes, 49 secondsand so if ID is not passed just going to return this let's also add promise here box.
2:25:012 hours, 25 minutes, 1 secondSo, so this is it. So, we are done with the setup. Now, we can go ahead and start working on the session controller
2:25:092 hours, 25 minutes, 9 secondsand the service and where we are going to use the upstatch box inside the um project. In this chapter, we're going to
Chapter 8: Session APIs & Tools
2:25:182 hours, 25 minutes, 18 secondsstart working on the sessions. So let's go into the controller and let's create session
2:25:262 hours, 25 minutes, 26 secondscontroller tx and then let me uh quickly copy this
2:25:362 hours, 25 minutes, 36 secondsum express and um a handler. So I'm just going to go into session controller. I'm going to paste this here
2:25:442 hours, 25 minutes, 44 secondsand then we can say uh export constant So the first end we're going to
2:25:522 hours, 25 minutes, 52 secondsdo is to get user sessions controller
2:26:002 hours, 26 minutesand let's get the ID ID and I'm going to change this to user ID
2:26:092 hours, 26 minutes, 9 secondsand then we can just let me close this.
2:26:152 hours, 26 minutes, 15 secondsSo I'm going to add validation. So I'm going to use um s. So I'm going to say session
2:26:242 hours, 26 minutes, 24 secondsdo validator tx.
2:26:302 hours, 26 minutes, 30 secondsSo let's import site from z.
2:26:392 hours, 26 minutes, 39 secondsSo paste it here. So this is going to be query bar. So first the sessions we're going to um pass insert. So they can
2:26:472 hours, 26 minutes, 47 secondssearch, they can pass in a page size and then page number. So save this. And now
2:26:542 hours, 26 minutes, 54 secondslet's go back to session controller. Now we can use this as a constant.
2:27:002 hours, 27 minutesThis is equals to session query search query schema. So
2:27:062 hours, 27 minutes, 6 secondslet me import this and then we can get in search
2:27:182 hours, 27 minutes, 18 secondspage size and page number. Now we're going to uh so let me close this.
2:27:272 hours, 27 minutes, 27 secondsSo we can then say constant data is going to be equals to await get useration
2:27:362 hours, 27 minutes, 36 secondsservice and we can pass in the user ID.
2:27:462 hours, 27 minutes, 46 secondsSo I'm going to let me remove this and I can pass in search page and page number here.
2:27:592 hours, 27 minutes, 59 secondsSo this is going to be query. So let's now return constant sorry instead of constant return response to like this.
2:28:122 hours, 28 minutes, 12 secondsSo let's go ahead and create a service.
2:28:142 hours, 28 minutes, 14 secondsSo I'll go straight to the service folder and let's create session service.
2:28:242 hours, 28 minutes, 24 secondsSo let's create a method. So export constant
2:28:342 hours, 28 minutes, 34 secondspage number and let's save this. I'll change this to query.
2:28:472 hours, 28 minutes, 47 secondsSo, so the first we're going to do, we need to build the query. So, I'm going to we have the user ID here. So, let's just
2:28:572 hours, 28 minutes, 57 secondssay um let's say constants query. So let me change this instead of query let me
2:29:032 hours, 29 minutes, 3 secondsset this to um filters.
2:29:122 hours, 29 minutes, 12 secondsSo filter is okay. So now I'm just going to say um if filter search
2:29:202 hours, 29 minutes, 20 secondsand and filter
2:29:262 hours, 29 minutes, 26 secondsdot search is not equals to undefined
2:29:362 hours, 29 minutes, 36 secondsthen we can say query search um instead of it I'm going to remove this. So inside the model if you go into
2:29:452 hours, 29 minutes, 45 secondssearch model we have title ripple name I think both of them we can search for
2:29:522 hours, 29 minutes, 52 secondstitle name even ID if you want so I'm going to just use I think it's best to use um title and name. So I'm just going
2:30:002 hours, 30 minutesto say dot dollar sign or it's going to be equals to um array and we're going to
2:30:072 hours, 30 minutes, 7 secondssay title and we're going to sect um filter search
2:30:142 hours, 30 minutes, 14 secondsoption and I we're going to pass in the let's do it again here response
2:30:232 hours, 30 minutes, 23 secondsname and we're going to pass this. I think this is okay.
2:30:302 hours, 30 minutes, 30 secondsSo now we have this we can then say constant um
2:30:412 hours, 30 minutes, 41 secondsso I say page pagation pageation
2:30:512 hours, 30 minutes, 51 secondslet's pass in um page size and the page number. Now I can say
2:30:592 hours, 30 minutes, 59 secondsconstant skip is equals to pation dot page number
2:31:062 hours, 31 minutes, 6 secondsminus one * pation dot page size. And now we can say constant
2:31:132 hours, 31 minutes, 13 secondsum so we're going to get the total and this and the um sessions. So we're going to say um session sorry total is equals
2:31:222 hours, 31 minutes, 22 secondsto promise all and let's import the um the session model. Then we're going to pass in the query and we're going to
2:31:302 hours, 31 minutes, 30 secondssort the send order. Then we're going to pass in skip.
2:31:362 hours, 31 minutes, 36 secondsSorry,
2:31:472 hours, 31 minutes, 47 secondsand then limit and we can then say link and then we're going to count the
2:31:552 hours, 31 minutes, 55 secondsdocuments. So now we can return this as a return session and then the pagation.
2:32:092 hours, 32 minutes, 9 secondsSo let's also get the total count total pages. So I say um total pages
2:32:182 hours, 32 minutes, 18 secondsis equals to total uh change this to total count here
2:32:252 hours, 32 minutes, 25 secondsand replace this with this. So now we have total count to pages. Then for the page size we can just say page nation page size page nation page number.
2:32:362 hours, 32 minutes, 36 secondsSo this is it.
2:32:382 hours, 32 minutes, 38 secondsSo we can now go ahead and let's go into session controller and let's import it.
2:32:472 hours, 32 minutes, 47 secondsSo now we need to also create an endpoint to fetch uh to fetch a single session. So I'll paste this here and I'm going to get session by log ID.
2:33:032 hours, 33 minutes, 3 secondsThen we're going to remove this. So let's create a validate the validation for uh we're going to get this id. So
2:33:102 hours, 33 minutes, 10 secondslet's go into session validator and then let's create this here. So I'm going to just import this inside the controller
2:33:182 hours, 33 minutes, 18 secondsand then we can say constant uh constant sl ID and we're going to pass in the
2:33:262 hours, 33 minutes, 26 secondsrequest params. Now I'm just going to remove um let me import it.
2:33:332 hours, 33 minutes, 33 secondsSo I'm just going to remove this. So I'm going to change this to um get
2:33:402 hours, 33 minutes, 40 secondsget session get get session by sl ID and we pass in
2:33:472 hours, 33 minutes, 47 secondsa user ID and the log ID and then we can we're going to return this. I'm going to say return
2:33:562 hours, 33 minutes, 56 secondsokay user um session retrieve you can just say session retrieve let me just change this session
2:34:042 hours, 34 minutes, 4 secondsretrieve successfully so let's go ahead and create this method so let's go into the service
2:34:112 hours, 34 minutes, 11 secondsand say export constant so let's say constant
2:34:182 hours, 34 minutes, 18 secondssession find one user id and load L then if not this we're going to use not found
2:34:272 hours, 34 minutes, 27 secondsuh session not found not found exception sorry not
2:34:352 hours, 34 minutes, 35 secondsnot found exception and then we're going to return
2:34:422 hours, 34 minutes, 42 secondsthe session so I think user ID here is let's go into a session model and let's remove schema here.
2:34:562 hours, 34 minutes, 56 secondsLet's also do the same thing for GitHub.
2:34:582 hours, 34 minutes, 58 secondsOkay, for message model okay is this is fine. So let's go into the service now and the
2:35:062 hours, 35 minutes, 6 secondserror should stop. Now this is not found exception and then we need to also get in we're going to retrieve the messages.
2:35:142 hours, 35 minutes, 14 secondsSo um once we get the uh sessions we going to retrieve the messages and this is going to we're going to go into the
2:35:232 hours, 35 minutes, 23 secondsmessages model and then we're going to fetch all the messages. So let's quickly create um the message service here. So I
2:35:302 hours, 35 minutes, 30 secondssay message service.
2:35:362 hours, 35 minutes, 36 secondsSo inside the um session service we are going to create a method. plus a constant and this is going to be equals
2:35:442 hours, 35 minutes, 44 secondsto await get session
2:35:512 hours, 35 minutes, 51 secondsmessages and we're going to pass in this and we're going to then retrieve the um
2:35:582 hours, 35 minutes, 58 secondsso messages here let's say messages and this is going to return session let's say session
2:36:072 hours, 36 minutes, 7 secondsand message so let's go ahead and create this method So I'll go I'll copy this U
2:36:132 hours, 36 minutes, 13 secondsget session messages service and let's just copy this.
2:36:222 hours, 36 minutes, 22 secondsLet's go into message service and let's say export constant
2:36:292 hours, 36 minutes, 29 secondsas sync and then we're going to say if not session ID. I'm going to uh I'm just
2:36:372 hours, 36 minutes, 37 secondsgoing to import this bad request exception and then we can then retrieve the
2:36:442 hours, 36 minutes, 44 secondsmessage say constant messages messages is equals to await
2:36:522 hours, 36 minutes, 52 secondsmessage find message model find session id and then we're going to sort and then
2:36:592 hours, 36 minutes, 59 secondswe say and then let's import in the message model.
2:37:092 hours, 37 minutes, 9 secondsSo let's go into session service and let's import this.
2:37:162 hours, 37 minutes, 16 secondsAnd now we've retrieved uh we've implemented the get uh sl service and let's go into session controller and let's import this.
2:37:292 hours, 37 minutes, 29 secondsSo now we are done with this now.
2:37:322 hours, 37 minutes, 32 secondsService error. So let me just say string
2:37:472 hours, 37 minutes, 47 secondssession. Okay. The error stop.
2:37:572 hours, 37 minutes, 57 secondsSo let me remove this.
2:38:002 hours, 38 minutesSo now the next thing we're going to create is the chat controller. So we're going to create that here. Let's say export constant.
2:38:092 hours, 38 minutes, 9 secondsI'm going to say as uh let's say session chat
2:38:182 hours, 38 minutes, 18 secondscontroller and we need to install some packages.
2:38:252 hours, 38 minutes, 25 secondswe're going to so let me post this. So let's create the validation for this.
2:38:332 hours, 38 minutes, 33 secondsSo I'm going to remove this. So let's go into session validator
2:38:402 hours, 38 minutes, 40 secondsand I'm going to pass it. Yeah. So we're going to get the messages from the client side the slid the repository URL
2:38:502 hours, 38 minutes, 50 secondsand the default um branch. you know, we're going to fetch the um we're going to fetch all the repos and all the repos
2:38:582 hours, 38 minutes, 58 secondshas the branch. So, we're not saving the repos in DB. So, we going the client is going to have to pass in the default
2:39:052 hours, 39 minutes, 5 secondsbranch. So, we're going to come over here and then we can say constant
2:39:152 hours, 39 minutes, 15 secondsuh messages and let's just get this and then we can say um session
2:39:252 hours, 39 minutes, 25 secondschat service and we're going to pass in all of this
2:39:332 hours, 39 minutes, 33 secondshere. the user ID u ID messages
2:39:402 hours, 39 minutes, 40 secondsrepo uh sorry repo and then the default branch.
2:39:492 hours, 39 minutes, 49 secondsSo let's import this.
2:39:562 hours, 39 minutes, 56 secondsSo we're going to also pass in the response. So this is going to send um we're going to be using the AI SDK which
2:40:042 hours, 40 minutes, 4 secondsis going to stream the response to the client side. So we're going to pass in the response here and let's just import
2:40:102 hours, 40 minutes, 10 secondsthis. So no import the session chat schema. So now let's go ahead and
2:40:182 hours, 40 minutes, 18 secondsinstall the packages we're going to use like the AI SDK. So let's go to the browser.
2:40:252 hours, 40 minutes, 25 secondsSo we're going to be using AI SDK which is um own by VU. So we're going to install this um package MPI install AI.
2:40:352 hours, 40 minutes, 35 secondsSo if you go to the okay this is how to use it. Just import generate text from AI and then you can generate text. So if
2:40:442 hours, 40 minutes, 44 secondsyou want to stream, so I think if I go to the documentation here, we can see generating and streaming text and we can scroll down here and see how to use it.
2:40:552 hours, 40 minutes, 55 secondsGenerate text AI and this is using AI AI gateway from V. So but you can use other
2:41:022 hours, 41 minutes, 2 secondsprovider like andropic. You can also add your own custom uh we can see um this
2:41:092 hours, 41 minutes, 9 secondsalso generate text and we can see the result object of generate text um the
2:41:152 hours, 41 minutes, 15 secondstwo call to two usage warning request and all and if we scroll down the case
2:41:222 hours, 41 minutes, 22 secondsfor unfinish let's go to um stream text now you can see text if I'm
2:41:302 hours, 41 minutes, 30 secondsusing the AI gateway I don't need to import any package page. I'll just use it directly and then we can just say text stream and this is going to stream
2:41:392 hours, 41 minutes, 39 secondsthe content the text. So if I scroll down now you can see you can use stream text on its own and combine it to a SDK UI. So we're going to use the SDK UI2.
2:41:512 hours, 41 minutes, 51 secondsSo we just do return to UI message. So the UI message is what we're going to be sending the client is going to send to
2:41:582 hours, 41 minutes, 58 secondsus on the back end and we're going to save. So now since we're using NodeJS and we're going to be streaming text. So you can see for NodeJS if we're using streaming the text we're going to have
2:42:072 hours, 42 minutes, 7 secondsto use pipe UI stream to response. So the UI message is what we're going to be sending to the client side and the client will send us the UI message. So
2:42:152 hours, 42 minutes, 15 secondswe're going to convert the streams to say UI message stream to response. So we're going to be using it and you can
2:42:242 hours, 42 minutes, 24 secondscome over to the documentation to read more about this.
2:42:292 hours, 42 minutes, 29 secondsSo we can see um what will be sent to the client side from the um this is this is the model. This is um the result once
2:42:392 hours, 42 minutes, 39 secondswe stream. So we're going to get the type and you can see all the type that is sent. So if it's text you see text um
2:42:472 hours, 42 minutes, 47 secondsdata text and so these are the events that will be sent. If it's reasoning this is it. We have two core. So we're
2:42:542 hours, 42 minutes, 54 secondsgoing to add two into um our age. So this is what it's going to be sending to the client. Two core, two core imput
2:43:012 hours, 43 minutes, 1 secondstart, two core imput delta end, and two two results. And I think that's it. So
2:43:092 hours, 43 minutes, 9 secondslet's just go ahead and install the package first. So I'll copy this and I'll go to code and then let's open terminal.
2:43:182 hours, 43 minutes, 18 secondsLet me clear this. So I'm going to be installing a version. So let me type it here.
2:43:262 hours, 43 minutes, 26 seconds6 6.0.5 and let's click on enter. So make sure you install it under the back inside the
2:43:332 hours, 43 minutes, 33 secondsbackend folder and let's wait for this to install. So now this has already installed. So now we're going to go ahead and create the
2:43:412 hours, 43 minutes, 41 secondsservice. So before we create the service I also want to if the user on the client side and the um chat let's say the chat
2:43:482 hours, 43 minutes, 48 secondsthe endpoint is running the streaming and then the user click on stop. So we need to abort the AI. So since we're going to be using um custom streaming.
2:44:002 hours, 44 minutesSo we are going to let's just create um the abot controller and send the abot signal to the um service. So I'll just
2:44:092 hours, 44 minutes, 9 secondsdo constant abot controller and then we can just say um
2:44:162 hours, 44 minutes, 16 secondslet's do response do close and abort um dot about controller and we can just say
2:44:262 hours, 44 minutes, 26 secondssignal. So let move this up here and now let's go ahead and create a service. So uh let me clear all of this here.
2:44:402 hours, 44 minutes, 40 secondsSo inside the service X session service. So let's so I'm going
2:44:482 hours, 44 minutes, 48 secondsto say export constant.
2:44:562 hours, 44 minutes, 56 secondsAnd now we're just going to let's get everything. So I'll go into session controller and let me copy all of this.
2:45:112 hours, 45 minutes, 11 secondsAnd inside the service I'll just paste it here.
2:45:162 hours, 45 minutes, 16 secondsI'll say type let me remove this change to signal
2:45:272 hours, 45 minutes, 27 secondsand response to response. So let's import response here from express.
2:45:402 hours, 45 minutes, 40 secondsSo now the first thing we're going to do we going to and since we're going to be using only this endpoints. So once the
2:45:472 hours, 45 minutes, 47 secondsuser um send the first message we need to create the session and then install
2:45:552 hours, 45 minutes, 55 secondsthe stock ID repo URL and default branch into the DB. So when the user send the
2:46:022 hours, 46 minutes, 2 secondssecond message we need to check if the um use the um session has been created
2:46:092 hours, 46 minutes, 9 secondswe just retrieve the session with his log ID so that um we don't have to keep on recreating the session any time the
2:46:182 hours, 46 minutes, 18 secondsuser send a message. So we are going to create a method that's going to um check if the slug ID has been added in a DB.
2:46:272 hours, 46 minutes, 27 secondsWe are going to retrieve it but if not we're going to then create the session.
2:46:312 hours, 46 minutes, 31 secondsSo let's say let's um this is going to be equals to a wait
2:46:392 hours, 46 minutes, 39 secondsI'll say create create or get session
2:46:482 hours, 46 minutes, 48 secondsand then we're going to pass in this we're going to pass in user ID stock ID repository URL and default branch and we
2:46:572 hours, 46 minutes, 57 secondscan create it here let's just say export sorry not export was constant wait and that's it there.
2:47:102 hours, 47 minutes, 10 secondsSo I'm just going to say uh string I'll set this to mean then I'm just
2:47:182 hours, 47 minutes, 18 secondsgoing to do a check here. So let me see if we have let me import the bad request exception
2:47:272 hours, 47 minutes, 27 secondsand now we're going to select session is equals to await session model find user id and sl ID and now we going to then
2:47:352 hours, 47 minutes, 35 secondsalso create the box then once we create a box uh the sandbox we're going to store the box ID in the um the session
2:47:442 hours, 47 minutes, 44 secondsmodel so I'm just going to say let box so let is going to be equals to no. So
2:47:522 hours, 47 minutes, 52 secondswe're going to say if first we're going to say if um if not session.
2:47:592 hours, 47 minutes, 59 secondsSo if we cannot find the session where the user ID and stock ID has been is added is passed. So we're going to say constant first. We need to
2:48:092 hours, 48 minutes, 9 secondsget the repo name. So we're going to split a slash. Then we're going to slice and and replace to empty string. And
2:48:172 hours, 48 minutes, 17 secondsthis is going to give us the repository name. Uh we can just uh um I think I will just leave it like this.
2:48:272 hours, 48 minutes, 27 secondsSo let me just do on repo.
2:48:312 hours, 48 minutes, 31 secondsAnd now let's say session session model. And we're going to pass in log id the
2:48:402 hours, 48 minutes, 40 secondsrepository URL the repository name default branch. And now we're going to say box
2:48:482 hours, 48 minutes, 48 secondsis equals to await rate box. And we're going to pass in the access token sources.
2:49:012 hours, 49 minutes, 1 secondSo let's go into the GitHub service and let's export. So you can see get
2:49:082 hours, 49 minutes, 8 secondsGitHub access token. Let's go back to service and I can just get it here. I'll say constant
2:49:172 hours, 49 minutes, 17 secondsum access token is equals to get github access token. Let's import it.
2:49:332 hours, 49 minutes, 33 secondsSo we're going to pass in the access token here.
2:49:402 hours, 49 minutes, 40 secondsLet's import this create box session.
2:49:442 hours, 49 minutes, 44 secondsOkay, it's not create box session. I think it's great box.
2:49:482 hours, 49 minutes, 48 secondsSo, let's import it from the sandbox. Now we're just going
2:49:572 hours, 49 minutes, 57 secondsto say um await session update session id box um box id
2:50:062 hours, 50 minutes, 6 secondsbox dot id and now we can just say uh session
2:50:142 hours, 50 minutes, 14 secondsdo box id like this um then let's say else
2:50:232 hours, 50 minutes, 23 secondsif session if session dot box id. We are going to say um
2:50:342 hours, 50 minutes, 34 secondswe going to say box is equals to await get box
2:50:462 hours, 50 minutes, 46 secondsand we're going to pass in we're going to just pass in sessionbox id sorry this should not be not so let me import this there.
2:51:032 hours, 51 minutes, 3 secondsThen lastly, if we have if we have session, we're going to say else, then we're going to create the box
2:51:102 hours, 51 minutes, 10 secondsagain. Then we're going to do the same thing. Now let's return um session and and the box.
2:51:192 hours, 51 minutes, 19 secondsSo now collapse this now and then we can just get session and so the next thing we are going to do is we're going to get
2:51:272 hours, 51 minutes, 27 secondsthe message from the um message list. So the message is going to be of type UI
2:51:352 hours, 51 minutes, 35 secondsmessage UI message which is coming from the AI package we can see there. So we are
2:51:442 hours, 51 minutes, 44 secondsgoing to get the last message. So um this is going to send a list like you can see array of messages. So we're
2:51:522 hours, 51 minutes, 52 secondsgoing to get the last the last message is is the message user just sent. So we're going to say constant
2:52:002 hours, 52 minutessorry constant last message is message length minus one. Now we're
2:52:092 hours, 52 minutes, 9 secondsjust going to say u constant I'll say user prompt is equals to we're going to find this.
2:52:202 hours, 52 minutes, 20 secondsSo I'm going to say um is equals to last message um
2:52:282 hours, 52 minutes, 28 secondspart and we're just going to find this. dot find
2:52:382 hours, 52 minutes, 38 secondspart type is equals to text.
2:52:472 hours, 52 minutes, 47 secondsSo I'm just going to remove this text here. So instead of um instead of
2:52:562 hours, 52 minutes, 56 secondsno provider just say on by two section.
2:53:012 hours, 53 minutes, 1 secondSo we want to use this to um or let me just remove this.
2:53:082 hours, 53 minutes, 8 secondsSo we want to generate the title of the uh the session. So if you don't know how I get the part. So if I go into the UI
2:53:182 hours, 53 minutes, 18 secondsmessage. If you scroll down now and we can scroll to where we have you can see we have the text UI part and you should
2:53:272 hours, 53 minutes, 27 secondssee the type text the type text and then the text state and this and this is
2:53:352 hours, 53 minutes, 35 secondsgoing to be added into this part here or we can see it inside the documentation.
2:53:412 hours, 53 minutes, 41 secondsSo if I go to here execute documentation and we can just search for UI message
2:53:512 hours, 53 minutes, 51 secondsand click on it and if you scroll down here you can see um we can scroll down here
2:54:012 hours, 54 minutes, 1 secondand you can see all the parts. So this is going to be in the um parts array. So the array can have the text part, the
2:54:092 hours, 54 minutes, 9 secondsreason part, the tools part, all of the file parts and all here. So that's reason why I had to loop through the
2:54:162 hours, 54 minutes, 16 secondspart. Yeah. So let's go back to the code and let me close this.
2:54:242 hours, 54 minutes, 24 secondsAnd now we're going to um use AI to generate the title. So we're going to say if not
2:54:322 hours, 54 minutes, 32 secondssession sorry if not session dot title. So we don't want to generate the
2:54:412 hours, 54 minutes, 41 secondstitle again after we've done it. So we're going to say if not title then we're going to generate the title. So
2:54:472 hours, 54 minutes, 47 secondswe're going to say constant title is equals to await. So we're going to create this method a generate session
2:54:562 hours, 54 minutes, 56 secondstitle. We going to pass in the user prompt.
2:55:002 hours, 55 minutesThat's the last message. So now if we get a title, we're going to say update update um updated session.
2:55:142 hours, 55 minutes, 14 secondsAnd we say find session ID um title. So just update the title. This is fine like this.
2:55:272 hours, 55 minutes, 27 secondsAnd then we can just set so we're not here we can say session
2:55:342 hours, 55 minutes, 34 secondsuh session okay we can say session title is equals to update title or we can just use
2:55:402 hours, 55 minutes, 40 secondssession is equals to updated session like this or let's just use only the title instead it's better set title and
2:55:502 hours, 55 minutes, 50 secondslet's just remove this I'll just add in
2:55:592 hours, 55 minutes, 59 secondsuh we're going to just say on um on title section. So I'm just going to leave it like this. Let's just go ahead and um so I'm just going to set this.
2:56:102 hours, 56 minutes, 10 secondsOkay, let's add in on session here and this is either string or no.
2:56:222 hours, 56 minutes, 22 secondsSo this is an error the error has stopped. So let's go ahead
2:56:312 hours, 56 minutes, 31 secondsand create this method now. So let's copy this and let's create it here.
2:56:382 hours, 56 minutes, 38 secondsI say for instance, so I'm going to say try catcher
2:56:512 hours, 56 minutes, 51 secondsand then we're going to import we're going to say constant result is equals to
2:56:592 hours, 56 minutes, 59 secondsalways generate generate text.
2:57:072 hours, 57 minutes, 7 secondsThen we're going to pass in the model, the system, and the pro. So I'm just going to pass this here. So I'm going to
2:57:152 hours, 57 minutes, 15 secondsadd in the model, and I'm going to use Google/Gemini
2:57:242 hours, 57 minutes, 24 seconds2.5 bytes. So I'm going to save this.
2:57:352 hours, 57 minutes, 35 secondsAnd now we have this. So I'm going to return the result. I'm going to say return result dot text stream
2:57:452 hours, 57 minutes, 45 secondsand we can just say all on title session.
2:57:492 hours, 57 minutes, 49 secondsSo this is fine. Then here we're just going to return on title session. So the reason why
2:57:572 hours, 57 minutes, 57 secondsadding this um the model like this so you need to provide the AI gateway that is AI gateway. So, I'll go to the
2:58:072 hours, 58 minutes, 7 secondsbrowser and we can uh let's go to AI
2:58:142 hours, 58 minutes, 14 secondsAI. Um let's say AI gateway and we're going to click here.
2:58:252 hours, 58 minutes, 25 secondsClick on this AI gateway.
2:58:292 hours, 58 minutes, 29 secondsSo to use AI gateway you will need to um buy credit. So if you don't want to buy credit or don't want to use you can use
2:58:382 hours, 58 minutes, 38 secondsopen router. You can just come over to a um a SDK and you can find open router
2:58:462 hours, 58 minutes, 46 secondshere. So let me just search for open router.
2:58:522 hours, 58 minutes, 52 secondsYou can see open router and if I click on this you can see how to use it. So just install open router AI SDK provider
2:59:012 hours, 59 minutes, 1 secondand then you can just create a file like inside the leaf folder and just add it with your API key then you can just use
2:59:082 hours, 59 minutes, 8 secondsthis um let's see with the generate text so you can just to open that chat then you
2:59:152 hours, 59 minutes, 15 secondscan add in the Google um 2.5 flashlight there. So, I'm going to be using AI
2:59:222 hours, 59 minutes, 22 secondsgateway. AI gateway. So, I already have, let me see, AI gateway.
2:59:332 hours, 59 minutes, 33 secondsSo, yes, I can go into my VC account and I can create an API. So, let me wait for this to load. So, we can just come over.
2:59:432 hours, 59 minutes, 43 secondsSo, I've lo into my account. Then we can just click on create API key and then you can create API key. So I'm going to I've already created the API key
2:59:522 hours, 59 minutes, 52 secondsalready. I'm going to use it inside. So I'm just showing you how you can do it or you can go ahead and use open router.
2:59:592 hours, 59 minutes, 59 secondsSo let's go back to the code and let's go into so we're going to collapse this.
3:00:063 hours, 6 secondsSo we done with the generate title session session title. So now uh the next thing we are going to do is to
3:00:133 hours, 13 secondsgenerate the branch name. So this is showing an error here.
3:00:213 hours, 21 secondsSo let me just on title session
3:00:323 hours, 32 secondsor we can just add in front.
3:00:443 hours, 44 secondsSo, what I can do, I'll just remove this. And I'm just going to say no.
3:00:513 hours, 51 secondsAnd then I'm going to come over here just say or no. And then I'll just return. So
3:00:593 hours, 59 secondsjust say if if not, I'm just going to return on to session.
3:01:083 hours, 1 minute, 8 secondsSo error should stop. Now let's go ahead. Let's say let branch name. So we are going to set branch name is equals
3:01:173 hours, 1 minute, 17 secondsto it's going to be of type string col and this going to be close to session.
3:01:243 hours, 1 minute, 24 secondsSo session dot branch name branch name.
3:01:313 hours, 1 minute, 31 secondsSo uh we're going to say if not if not branch name
3:01:393 hours, 1 minute, 39 secondsthen we're going to say branch name is equals to um let's say await generate
3:01:473 hours, 1 minute, 47 secondsbranch name. We're going to pass in the user um user prompt and I'll just say
3:01:563 hours, 1 minute, 56 secondsawait uh session find and we can just say session
3:02:043 hours, 2 minutes, 4 secondsid we pass in the branch name and then we set session branch name equals to um
3:02:113 hours, 2 minutes, 11 secondsbranch name like this. So let's go ahead and create this method here. So, I'll come up here and I'm going to say constant.
3:02:223 hours, 2 minutes, 22 secondsAnd then we're going I'll just go ahead and copy this um where we have the branch name. So,
3:02:313 hours, 2 minutes, 31 secondsI'm just going to paste it here and I'll come over come here and I'm going to generate unique ID here. So, let's say
3:02:393 hours, 2 minutes, 39 secondsmath random and to string 36 to 8. So I'm just going to say if no prompt I'll
3:02:463 hours, 2 minutes, 46 secondsjust I'll just do um I'll just say let's do like this. So I'm going to
3:02:543 hours, 2 minutes, 54 secondschange this to base 64 / um I'll just say changes
3:03:023 hours, 3 minutes, 2 secondsthen I'm going to update this I'm going to update the system and um prompt here.
3:03:093 hours, 3 minutes, 9 secondsSo let me paste it.
3:03:143 hours, 3 minutes, 14 secondsSo now we're going to then I'm just going to remove this return. I'm going to say constant.
3:03:243 hours, 3 minutes, 24 secondsSo we're going to get the suffix. So return result text.
3:03:293 hours, 3 minutes, 29 secondsSo instead of trim, I'll just say um dot replace like this.
3:03:373 hours, 3 minutes, 37 secondsLet's uh let's update and set um let's set this to sub string to 30 or
3:03:463 hours, 3 minutes, 46 secondschanges. So um instead of user prompt I'm going to change this to prompt.
3:03:563 hours, 3 minutes, 56 secondsSo or we can set all to um all changes here and then we can just return this
3:04:033 hours, 4 minutes, 3 secondsand there we just return B 64 and changes unique ID and let's save this. So now we can use this now.
3:04:143 hours, 4 minutes, 14 secondsSo let's go. So we are done with this check. We done with the branch now. Now we're going to save the user message
3:04:223 hours, 4 minutes, 22 secondsinto the DB. So I'm going to say await uh create
3:04:283 hours, 4 minutes, 28 secondsmessage. So create a message service and we're going to pass in session
3:04:373 hours, 4 minutes, 37 secondsdot ID to string.
3:04:433 hours, 4 minutes, 43 secondsAnd I'm going to remove this. So I'm going to add in an object. I'll set ID
3:04:503 hours, 4 minutes, 50 secondsas latest sorry last message ID which is going to if there's no ID I'll just use
3:04:573 hours, 4 minutes, 57 secondsgenerate uh generate ID which is going to come from AI
3:05:043 hours, 5 minutes, 4 secondsuh from AI. You can see we can pass it here. So let me import it. So let's import it from the AI package.
3:05:143 hours, 5 minutes, 14 secondsAnd then we're going to pass the row.
3:05:163 hours, 5 minutes, 16 secondsI'll say um last message row and the path.
3:05:233 hours, 5 minutes, 23 secondsSo now we have this. Let's go into the message service and let's create it. So go into me message service and then we
3:05:323 hours, 5 minutes, 32 secondscan say export constant and we can pass in uh
3:05:423 hours, 5 minutes, 42 secondsso let me change this like this and here I'll just import UI message
3:05:503 hours, 5 minutes, 50 secondsfrom AI And then we can just say if not I'll
3:06:013 hours, 6 minutes, 1 secondjust do this. If not um s ID an error and let's import uh I think I made mistake here. It's a message model.
3:06:133 hours, 6 minutes, 13 secondsSo we are done with this now. So we can import it.
3:06:223 hours, 6 minutes, 22 secondsSo we're going to retrieve the messages of a constant messages and this is going to be equals to await
3:06:303 hours, 6 minutes, 30 secondsand inside the message service we're going to say get message service and I'm going to just return this here pass this
3:06:393 hours, 6 minutes, 39 secondshere and we're going to pass in the uh session ID. So now I'll just change this to DB um messages.
3:06:533 hours, 6 minutes, 53 secondsSo now we're going to then we're going to say constant history um let's see history
3:07:023 hours, 7 minutes, 2 secondsmessages and we're going to sanitize the UI messages. So I'm going to go into the
3:07:103 hours, 7 minutes, 10 secondsservice and we're going to sanitize this too. So I'm going to come over here and I'm going to create the method. So you
3:07:173 hours, 7 minutes, 17 secondscan copy it from the GitHub. So I'm just going to paste it here. So just copy this and sanitize your message. I'm
3:07:243 hours, 7 minutes, 24 secondsgoing to collapse this here. So I'll come over to where we have the messages and this is send order and then we can
3:07:323 hours, 7 minutes, 32 secondsjust say we can map the um messages. So just say constant I'll say UI messages.
3:07:413 hours, 7 minutes, 41 secondsUm let's add in UI messages.
3:07:463 hours, 7 minutes, 46 secondsSorry I'll say equals to sanitize messages.
3:07:533 hours, 7 minutes, 53 secondsAnd then I can just say dot map
3:08:023 hours, 8 minutes, 2 secondsand then we can just return ID. We can return the row and we can return the path and then can close this
3:08:123 hours, 8 minutes, 12 secondsand then let's just say messageages equals to message.
3:08:183 hours, 8 minutes, 18 secondsSo I think the error should stop.
3:08:343 hours, 8 minutes, 34 secondsSo now we can use this now inside.
3:08:383 hours, 8 minutes, 38 secondsOkay. So since we've already san um go into the service and there's no need to
3:08:453 hours, 8 minutes, 45 secondssanitize. So we can just say DB message here. This is fine. So you can either slice it if you want. You can slice uh you can limit it to let's say 10.
3:08:573 hours, 8 minutes, 57 secondsLet's say minus 10.
3:08:593 hours, 8 minutes, 59 secondswhich will be set here. So I'm just going to leave it for now like this. So now we're going to then go ahead and
3:09:073 hours, 9 minutes, 7 secondsstart working on the stream. So I'm going to say constant UI stream.
3:09:153 hours, 9 minutes, 15 secondsSo we're going to be creating a custom stream. So we're going to be using create uh create UI message
3:09:253 hours, 9 minutes, 25 secondsstream. And here we're going to pass an object. So I'm going to first of all generated
3:09:313 hours, 9 minutes, 31 secondsI'll say generated ID and we're going to pass in generate ID
3:09:393 hours, 9 minutes, 39 secondshere. So make sure we've imported create. So let me import it.
3:09:473 hours, 9 minutes, 47 secondsSo say copy this create UI. Let's import it. And then we're going to just pass in original messages. We'll pass in the
3:09:543 hours, 9 minutes, 54 secondshistory. Now we are going to say um so we're going to say if this is
3:10:023 hours, 10 minutes, 2 secondsfinished we're going to save we're going to save the messages from the AI. So I'm going to use messages here messages. So
3:10:103 hours, 10 minutes, 10 secondswe're going to come back to it. So let's implement the stream. So the next thing we're going to add there is the execute.
3:10:243 hours, 10 minutes, 24 secondsSo now inside the execute here we going to set this sorry this should be like this async and we going to get writer.
3:10:373 hours, 10 minutes, 37 secondsSo with the writer we can use this to send custom event. So let me add an arrow here. So we can see this in the
3:10:443 hours, 10 minutes, 44 secondsdocumentation. So if you search for custom if I click on the streaming custom data. Now if I scroll down now
3:10:523 hours, 10 minutes, 52 secondsyou can see the UI message. You can add in your own custom UI messages. So if I scroll down you can see that we use
3:10:593 hours, 10 minutes, 59 secondscreate UI message stream and you can see the writer which I showed you. So you can see send initial status and this if
3:11:073 hours, 11 minutes, 7 secondsyou add this is not going to be added to the message list. But if you do not add it this is going to be like this. It's going to be added to the message list.
3:11:163 hours, 11 minutes, 16 secondsSo we going to implement that one like this and we're going to have some message we're going to most of custom message we're going to create we we add
3:11:253 hours, 11 minutes, 25 secondsthis but if you don't want to if you want to add it to the chat history then there's no need to add it just set this to false. So we're going to have writer
3:11:343 hours, 11 minutes, 34 secondswrite the type then data and we pass in information you want to add there and
3:11:423 hours, 11 minutes, 42 secondsthen once we done we can then we can see the stream then we can come over here and do writer do merge resource to you
3:11:523 hours, 11 minutes, 52 secondsum during message stream. So this is going to merge all the custom messages inside um together with the um result
3:12:003 hours, 12 minuteshere. So it's going to compile them and we're going to we're going to then create UI message stream response and we're going to pass in the UI stream here. So that is what we're going to do.
3:12:123 hours, 12 minutes, 12 secondsSo let's go ahead and implement it. So we're going to be using we're going to be using it for um to send title the
3:12:223 hours, 12 minutes, 22 secondssession title to the client side. Like here they're using it to send notification to the client side. So this is not going to be added to the message
3:12:303 hours, 12 minutes, 30 secondsbecause of this. So let's go to the code. And now we are going to emit um
3:12:393 hours, 12 minutes, 39 secondsthe session title like I mentioned. So we're going to say writer write
3:12:473 hours, 12 minutes, 47 secondsand we're going to say um type.
3:12:533 hours, 12 minutes, 53 secondsSo we're going to call this data session title
3:13:023 hours, 13 minutes, 2 secondsand we're going to pass in the data and this is going to be title session
3:13:113 hours, 13 minutes, 11 secondsdot title and we are going to then add
3:13:203 hours, 13 minutes, 20 secondsset to So I think error should stop now.
3:13:363 hours, 13 minutes, 36 secondsSo now we have this. So I'll just say emit session title.
3:13:453 hours, 13 minutes, 45 secondsSo now we are going to say um writer write
3:13:573 hours, 13 minutes, 57 secondsand I'm going to send in we can send in the um repository the branch and also the let's say the
3:14:063 hours, 14 minutes, 6 secondsrepository name. So I'm going to say type I'll call it data repo info.
3:14:173 hours, 14 minutes, 17 secondsI'll say data rep name
3:14:253 hours, 14 minutes, 25 secondsthen then we can pass in the branch name.
3:14:323 hours, 14 minutes, 32 secondsSo we have I'll just set this to branch like this and we can set we can pass in the the ripple URL.
3:14:473 hours, 14 minutes, 47 secondsSo we have and then we can pass this in.
3:14:553 hours, 14 minutes, 55 secondsSo the error should stop. Yeah.
3:15:003 hours, 15 minutesSo now we have this now we are going to create a method which we are going to use to u handle the cloning of the
3:15:103 hours, 15 minutes, 10 secondsrepository and then cding cd into the branch which we generated. So I'm just
3:15:173 hours, 15 minutes, 17 secondsgoing to call this a wait. I'll just say ensure uh let's call this ensure session
3:15:263 hours, 15 minutes, 26 secondsum workspace workspace ready. Let's see ready.
3:15:333 hours, 15 minutes, 33 secondsAnd then we're going to pass in section um box
3:15:423 hours, 15 minutes, 42 secondssorry branch name
3:15:483 hours, 15 minutes, 48 secondsrepo name. So repo session repo repo name
3:15:553 hours, 15 minutes, 55 secondsand the default branch session dot default default branch.
3:16:043 hours, 16 minutes, 4 secondsSo let's go ahead and create this method. So I can create it here.
3:16:113 hours, 16 minutes, 11 secondsConstant um show. So pass in the session
3:16:183 hours, 16 minutes, 18 secondsthe branch name the repro and the default branch.
3:16:253 hours, 16 minutes, 25 secondsSo I'm going to change this session and I'm going to just replace this with this. So let's import session um
3:16:333 hours, 16 minutes, 33 secondsdocument and the box. So I'm going to import all of this above here. So let's come over here and let's say uh session
3:16:423 hours, 16 minutes, 42 secondsdocument session do model. So I'm just going to use at oach
3:16:513 hours, 16 minutes, 51 secondsal sandbox box and I'm going to set type here.
3:17:003 hours, 17 minutesSo let's come down.
3:17:053 hours, 17 minutes, 5 secondsYeah. So now we're going to say if not um session
3:17:123 hours, 17 minutes, 12 secondsif not session rile
3:17:203 hours, 17 minutes, 20 secondsURL then we're just going to th request session ripple URL then we're going to
3:17:283 hours, 17 minutes, 28 secondssay so the next thing we're going to do we're going to check if we've already um clone the repository So to check we're
3:17:363 hours, 17 minutes, 36 secondsgoing to say constant um repo exist.
3:17:443 hours, 17 minutes, 44 secondsSo say exist is going to be equals to we're going to run a command here. We're going to say box execute.
3:17:563 hours, 17 minutes, 56 secondsI say command text let me say dashd and we're going to
3:18:073 hours, 18 minutes, 7 secondspass in the repo name I'll say slash dot git
3:18:163 hours, 18 minutes, 16 secondsso when we cl the um the repository so the name is going to the name is going to be the folder so that is reason so
3:18:243 hours, 18 minutes, 24 secondsonce we have this We can say if if ripple
3:18:313 hours, 18 minutes, 31 secondsif ripple exist dot um instead of code exist
3:18:443 hours, 18 minutes, 44 secondscode is not um equals to zero then we
3:18:493 hours, 18 minutes, 49 secondscan just say wait box dot it
3:18:573 hours, 18 minutes, 57 secondsdo clone and we're going to pass in let me remove this
3:19:063 hours, 19 minutes, 6 secondspass in the repo which is going to be session the repo URL and then branch is
3:19:153 hours, 19 minutes, 15 secondsgoing to be the default branch so now we're going to then cd into it so say await
3:19:233 hours, 19 minutes, 23 secondsdo cd cd ribbon name.
3:19:313 hours, 19 minutes, 31 secondsSo I'm just going to say if branch name
3:19:393 hours, 19 minutes, 39 secondsand not session dot repo initialize at
3:19:483 hours, 19 minutes, 48 secondsthen we can just say so let me use try here
3:19:563 hours, 19 minutes, 56 secondswe can use um get box check out to branch and I'm Just going to remove this
3:20:023 hours, 20 minutes, 2 secondsto branch name then I'll just say so if this is going to give us any we
3:20:123 hours, 20 minutes, 12 secondscan just use the command I'll say box
3:20:163 hours, 20 minutes, 16 secondsdot get dot execute
3:20:233 hours, 20 minutes, 23 secondsand let's just say object Sorry.
3:20:313 hours, 20 minutes, 31 secondsAnd we can just check out B um branch name. So now I'm just going to say if
3:20:383 hours, 20 minutes, 38 secondsif not initialize we just update this and we can just say session like this.
3:20:463 hours, 20 minutes, 46 secondsSo now we we're done with this.
3:20:503 hours, 20 minutes, 50 secondsSo now we know that you've cloned the repository and we've navigated the user um the AI we've navigated to this
3:20:583 hours, 20 minutes, 58 secondsrepository. So session of repository name. So this is showing an error.
3:21:103 hours, 21 minutes, 10 secondsSo I don't know why it's showing an error here.
3:21:173 hours, 21 minutes, 17 secondsSo let me scroll back session. No, it's not string.
3:21:333 hours, 21 minutes, 33 secondsSo let me just say constants repo name is equals to
3:21:513 hours, 21 minutes, 51 secondsSo even the first branch too.
3:21:583 hours, 21 minutes, 58 secondsSo default branch session the default branch.
3:22:123 hours, 22 minutes, 12 secondsSo I don't know why this is showing error.
3:22:163 hours, 22 minutes, 16 secondsSo but this is working out. So now we can go ahead and let me see if this error is going to show again.
3:22:383 hours, 22 minutes, 38 secondsSo I think I did a check.
3:22:473 hours, 22 minutes, 47 secondsSo I think this is because of a test script. So let me go into the model and let me fix it. So I'll go into model and let me remove.
3:22:573 hours, 22 minutes, 57 secondsSo this must have we must have this and
3:23:063 hours, 23 minutes, 6 secondsand I think the repository v is important and the box id
3:23:153 hours, 23 minutes, 15 secondsso we can see required required default branch I'm going to set this to require too and repository name is required.
3:23:283 hours, 23 minutes, 28 secondsThen box is required.
3:23:313 hours, 23 minutes, 31 secondsSo I think the error should stop now. So let's go into the session service.
3:23:403 hours, 23 minutes, 40 secondsNow we can see the error has stop. So I can remove this default branch. So now we have this. Now
3:23:483 hours, 23 minutes, 48 secondswe can go ahead and let's go ahead and create the um let's go ahead and create
3:23:553 hours, 23 minutes, 55 secondsthe prompt system prompt. So I'm going to just let me do that inside here. So I'll just create a folder of say AI and then we can say prompt.
3:24:083 hours, 24 minutes, 8 secondsCX and we can also create a file. So we're going to create tools too.
3:24:183 hours, 24 minutes, 18 secondsYou can call it tools.ex here. So I'm going to paste in the prompt. So I paste it here. And this is the prompt here.
3:24:293 hours, 24 minutes, 29 secondsSo you can see get um code system prompt and we have the um identity of the the
3:24:383 hours, 24 minutes, 38 secondsenvironment. We pass in the repository name and we tell that the tools we have.
3:24:423 hours, 24 minutes, 42 secondsSo we're going to go ahead and create all these tools. Let's read, write, edit, script, get status, commit, and
3:24:493 hours, 24 minutes, 49 secondsthen get push with web search. And this is just some front end style. And then
3:24:563 hours, 24 minutes, 56 secondswe have okay, we have these two. Look at the workflow. Then we say first check
3:25:043 hours, 25 minutes, 4 secondswhether this is in your brand new repo and existing project. If the project rep look empty only has a s to skip the
3:25:123 hours, 25 minutes, 12 secondspacking reading. So if it if it has like content inside the repo is going to first for the packet of ch and then it's
3:25:203 hours, 25 minutes, 20 secondsgoing to fall align with what already exist. But if it's a new repo is going to go and start from scratch. So you can see coding rule and then some important
3:25:283 hours, 25 minutes, 28 secondsand the above one here is just the URL rules. So I'm going to save this. Copy this. Get code system prompt. And let's
3:25:363 hours, 25 minutes, 36 secondsgo into the session service. And then we can just say constant system system
3:25:433 hours, 25 minutes, 43 secondsprompt. I will just paste this here. And I'm going to pass in the U session.
3:25:503 hours, 25 minutes, 50 secondsDrupal name. And let's import this.
3:25:533 hours, 25 minutes, 53 secondsSo I'm going to go ahead and say constant constant um result
3:26:033 hours, 26 minutes, 3 secondsis equals to stream. So let's import stream text
3:26:103 hours, 26 minutes, 10 secondsand then I'm going to set the model. So, I'm going to be using Antropic and I'll just pick let's say let's pick this one.
3:26:243 hours, 26 minutes, 24 secondsLet me go with Sonic Sonic 4.5.
3:26:313 hours, 26 minutes, 31 secondsAnd then we're going to pass in system and this is going to be system.
3:26:413 hours, 26 minutes, 41 secondsSo system prompt and let's import this.
3:26:553 hours, 26 minutes, 55 secondsThen we're going to pass in the messages.
3:27:013 hours, 27 minutes, 1 secondSo we can't pass in UI message. So we need to convert this into a model message. So we can do it here.
3:27:093 hours, 27 minutes, 9 secondsSo just say I wait or let me do it here constant
3:27:173 hours, 27 minutes, 17 secondsmodel um messages
3:27:243 hours, 27 minutes, 24 secondsis going to be equals to so let's say um await
3:27:313 hours, 27 minutes, 31 secondsconvert so let's import this convert to model message
3:27:393 hours, 27 minutes, 39 secondsand then we can pass in the history messages.
3:27:483 hours, 27 minutes, 48 secondsSo I'm just going to instead of history I'm going to use DB here.
3:27:543 hours, 27 minutes, 54 secondsWe can use DB to pass all the original message. And for the history message we can just say slice
3:28:023 hours, 28 minutes, 2 secondsminus 10. I'll just copy cut this out, but let's leave it here. So, you can move this to the top if you want. So,
3:28:093 hours, 28 minutes, 9 secondsI'm just going to pass this here. And I'm going to pass this here.
3:28:143 hours, 28 minutes, 14 secondsSo, now we need to go ahead and um and create a tools. So, before I do that, let's pass in provider options. So, want
3:28:233 hours, 28 minutes, 23 secondsto enable thinking for anthropic. So, I'll say anthropic
3:28:363 hours, 28 minutes, 36 secondsThen I'm going to set thinking type enabled and budget token. Then we're going to then pass in step count. So the
3:28:443 hours, 28 minutes, 44 secondsnumber of step the AI can so say stop when and we're going to import step count.
3:28:543 hours, 28 minutes, 54 secondsSo since the air can call multiple tools like list read and grip badge too. So
3:29:023 hours, 29 minutes, 2 secondsI'm going to give this 20 and step count. So the maximum is going to be 20.
3:29:073 hours, 29 minutes, 7 secondsIt can call um the tools at once. So I say it's calling it it's going over and over different tools. So the maximum is
3:29:163 hours, 29 minutes, 16 seconds20. You can reduce it to 10, but I'll leave it at 20. Then let's pass in let's
3:29:223 hours, 29 minutes, 22 secondspass in the abot signal here about signal and this is going to be let's see what did I pass here signal.
3:29:363 hours, 29 minutes, 36 secondsSo let me change this to our signal.
3:29:443 hours, 29 minutes, 44 secondsSo copy this and then pass it here.
3:29:543 hours, 29 minutes, 54 secondsSo we're going to go ahead and add the tool. So I can add tools here for I'm just going to leave it empty. So we're going to go ahead and create the
3:30:023 hours, 30 minutes, 2 secondstools. But before we go ahead and create the tools, let's uh let's complete this.
3:30:073 hours, 30 minutes, 7 secondsSo I'm going to then use writer mage
3:30:153 hours, 30 minutes, 15 secondsAnd we're going to say result dot to UI UI stream.
3:30:243 hours, 30 minutes, 24 secondsSo I'm going to wrap this inside try catch here.
3:30:303 hours, 30 minutes, 30 secondsSo let me say try and then let me just drag this. So come
3:30:423 hours, 30 minutes, 42 secondshere and I'm just going to say uh catch
3:30:543 hours, 30 minutes, 54 secondslike this then we can just write dot
3:31:013 hours, 31 minutes, 1 seconddot uh so I'm not going to select just to console log
3:31:093 hours, 31 minutes, 9 secondserror here and or we can skip adding this catch here since um the AIK has the on error.
3:31:203 hours, 31 minutes, 20 secondsSo I'm just going to say on error I'll pass in error
3:31:303 hours, 31 minutes, 30 secondsand then we can just return we can we can just return console.log
3:31:383 hours, 31 minutes, 38 secondslog um error
3:31:473 hours, 31 minutes, 47 secondsstream error like this. So then lastly we are going
3:31:563 hours, 31 minutes, 56 secondsto type the UI message to uh stream to response. So I'm going to pass this here and let's import it.
3:32:093 hours, 32 minutes, 9 secondsSo this is showing an error.
3:32:183 hours, 32 minutes, 18 secondsSo let me see this is correct.
3:32:333 hours, 32 minutes, 33 secondsOkay. So I made a mistake. This is supposed to return a string. So, I'm just going to say
3:32:393 hours, 32 minutes, 39 secondsextreme error error message should stop.
3:32:563 hours, 32 minutes, 56 secondsYou can see it return only string.
3:32:593 hours, 32 minutes, 59 secondsSo, now we can go ahead and work on the tools. So I'm going to open this and then
3:33:063 hours, 33 minutes, 6 secondswhere we have the tools. So I can so there's an error here. So I'm just going to remove let's just remove this stream error.
3:33:183 hours, 33 minutes, 18 secondsSo let's come over here and let's define the tools. So I'll say constant tools is going to be equals to coding
3:33:273 hours, 33 minutes, 27 secondssay coding tools and this is going to take um we're going
3:33:343 hours, 33 minutes, 34 secondsto pass in the box we're going to pass in the repo URL. So say sessionrele
3:33:443 hours, 33 minutes, 44 secondsURL and we're going to pass in the repo
3:33:513 hours, 33 minutes, 51 secondsname and the branch name
3:33:593 hours, 33 minutes, 59 secondsthe session.log ID and then we're going to pass in writer
3:34:123 hours, 34 minutes, 12 secondsSo I'm just going to say constant active tools is going to be equals to.
3:34:213 hours, 34 minutes, 21 secondsSo we're going to pass in web um search to. So I'm just going to comment this out. So we're going to add that later.
3:34:283 hours, 34 minutes, 28 secondsBut let's create the tools and then we can then copy active tools and then let's pass it here.
3:34:353 hours, 34 minutes, 35 secondsSo let's go ahead and create a coding tools. So I'm going to um AI tools. So
3:34:433 hours, 34 minutes, 43 secondslet's change this to folder. So say tools and then inside here we can then move
3:34:503 hours, 34 minutes, 50 secondsthis inside. Then we can change this to um
3:34:593 hours, 34 minutes, 59 secondsum I wanted to separate it. So let's change this to GitHub. Let's say GitHub
3:35:073 hours, 35 minutes, 7 secondsto um
3:35:143 hours, 35 minutes, 14 secondsGitHub to this is fine. You can just leave it as GitHub 2. And then let's say export constants
3:35:213 hours, 35 minutes, 21 secondscoding tools is equals to
3:35:293 hours, 35 minutes, 29 secondslet's return on this. So I'm just going to pass in this here. So let's import
3:35:373 hours, 35 minutes, 37 secondstype box from upstage box.
3:35:523 hours, 35 minutes, 52 secondsSo now we're going to then return we're going to return an object. So the first thing we're going to have is a
3:36:003 hours, 36 minuteslist two. So let's import two from AI package. And then the first thing we're going to have in two, we're going to have the description.
3:36:113 hours, 36 minutes, 11 secondsSo description, we're going to have the impute schema.
3:36:173 hours, 36 minutes, 17 secondsSo in schema, we're going to be using S. So let's import S.
3:36:263 hours, 36 minutes, 26 secondsYeah. So let's say subobject.
3:36:303 hours, 36 minutes, 30 secondsSo for the list two the air is going to pass in it's going to pass in the part
3:36:383 hours, 36 minutes, 38 secondsand this is going to be s string and this is going to be default I'm
3:36:463 hours, 36 minutes, 46 secondsgoing to set default to dot and then we can describe
3:36:533 hours, 36 minutes, 53 secondsdescribe this say part relative
3:37:003 hours, 37 minutesto the ripple root. So we can give this um we can say
3:37:103 hours, 37 minutes, 10 secondseg srlc/ component and um use dot for the root. So I'm
3:37:183 hours, 37 minutes, 18 secondsgoing to pass in the description and you can see this directory as a given part relative to the current repos
3:37:273 hours, 37 minutes, 27 secondsroot use for the root or system component for sub folders. So we going
3:37:343 hours, 37 minutes, 34 secondsto have this now and then I think here here we're going to have execute
3:37:403 hours, 37 minutes, 40 secondsand we say async and then we can get the part
3:37:483 hours, 37 minutes, 48 secondsand then sorry we can just return this and we can say constant constant files
3:37:573 hours, 37 minutes, 57 secondsis equals to weight box.list
3:38:093 hours, 38 minutes, 9 secondspart and then we can return this. We say return success
3:38:173 hours, 38 minutes, 17 secondstrue parts and then the files.
3:38:253 hours, 38 minutes, 25 secondsSo the next to we going to create is the grip tool. So I'm going to paste this here.
3:38:323 hours, 38 minutes, 32 secondsSo let me format this. So let me remove this.
3:38:393 hours, 38 minutes, 39 secondsSo uh for the group two we are going to um define description. So search for text across file in the repository and
3:38:483 hours, 38 minutes, 48 secondsthe impute is query and path. Then we're going to use box.execute execute and then we can grip files and then we're
3:38:563 hours, 38 minutes, 56 secondsgoing to split the result and then return this. So I'm going to paste this method at the top here.
3:39:043 hours, 39 minutes, 4 secondsSo I've paste it here. We're going to split lines and escape shell.
3:39:093 hours, 39 minutes, 9 secondsSo we've passed it here. So you can just copy this from the GitHub. So the next
3:39:163 hours, 39 minutes, 16 secondsthe next to we're going to have is the read two and I'm going to um paste it here. So
3:39:263 hours, 39 minutes, 26 secondsI'll just replace it with so let me remove this.
3:39:313 hours, 39 minutes, 31 secondsSo we can have we have the description read the full content of a file. So we're going to pass in the path and then
3:39:383 hours, 39 minutes, 38 secondswe can say content is equals to a box pass with path. Then we can count the
3:39:453 hours, 39 minutes, 45 secondsline. So line split line content length we pass in the part the content and the line count. So we have the read two now.
3:39:543 hours, 39 minutes, 54 secondsSo let me just add two.
3:39:593 hours, 39 minutes, 59 secondsSo we're going to have the right two here. So I'll say all right two and I'm going to paste it here too.
3:40:093 hours, 40 minutes, 9 secondsAnd we can see a description create a new file with given content the impute schema the part related to the repo
3:40:193 hours, 40 minutes, 19 secondsrepository and then we have the content and we're going to use box file. Write part and content then we split it to get
3:40:273 hours, 40 minutes, 27 secondsthe number of lines. Then we are going to have the edit to.
3:40:353 hours, 40 minutes, 35 secondsYeah. So I'm going to pass it. So the edit is going to also return the um div.
3:40:413 hours, 40 minutes, 41 secondsSo we're going to use the command get command to get div. So we can see edit to edit u the difference the description
3:40:513 hours, 40 minutes, 51 secondsover write an existing file with new content. The impute we're going to pass in the path and the content. So we have
3:40:593 hours, 40 minutes, 59 secondsum the part content and we're going to use box file.right um part and then the content. Then we're going to so get the dives.
3:41:093 hours, 41 minutes, 9 secondsSo this is going to we're going to return a difference so users can see. So we're going to say patch is equals to difference and the div results output
3:41:163 hours, 41 minutes, 16 secondstree and then we want to get the addition and deletion from the patch we pass from the div result. So I'm going to add the method there.
3:41:283 hours, 41 minutes, 28 secondsSo we can see it there.
3:41:303 hours, 41 minutes, 30 secondsSo we're going to have the addition, delet, and deletion. Then we're going to for constant split. We're going to split lines. And then we're going to say line
3:41:393 hours, 41 minutes, 39 secondsthat start with plus+ or lines that start with minus continue. Then we're going to start with um anyone that start with plus, we're going to add this.
3:41:483 hours, 41 minutes, 48 secondsAnyone that starts with minus, then we're going to add the the deletion deletion um variable there. So now we have this sorry the edit the edit two.
3:42:013 hours, 42 minutes, 1 secondSo I think next one we're going to have is the batch two. So I'm going to so I'm
3:42:073 hours, 42 minutes, 7 secondsgoing to pass this here and the batch two is going to return. So it's going to run short command in the repository like
3:42:163 hours, 42 minutes, 16 secondsmpm test delete. So it's going to the uh agent is going to pass in the command
3:42:233 hours, 42 minutes, 23 secondsand then we can then pass in a command here. It's a box command. Then lines we
3:42:303 hours, 42 minutes, 30 secondscan split lines and the result. So we're going to get the result. Then we're just going to return the output line and the
3:42:373 hours, 42 minutes, 37 secondsSS code. So this is for the bash to now we're going to have the um G status 2.
3:42:463 hours, 42 minutes, 46 secondsSo I'll say get status two.
3:42:523 hours, 42 minutes, 52 secondsSo I'm going to pass it here. So um for the g status to we have the description.
3:43:003 hours, 43 minutesSo run get status to get the current change or status file in the repository.
3:43:043 hours, 43 minutes, 4 secondsAnd this is not going to take in any impute. So it's just to run to just retrieve the status when you want to retrieve the status. Then this is just a simple let me change this.
3:43:173 hours, 43 minutes, 17 secondsAnd now this one is kind of long. So this is to commit commit changes. So commit um
3:43:283 hours, 43 minutes, 28 secondstwo and we can just have it here. Commit to so I'm just going to
3:43:363 hours, 43 minutes, 36 secondsum paste it now. So I'll just replace it with this. And let me remove this.
3:43:433 hours, 43 minutes, 43 secondsSo this is just to state changes and create a comet. Use a short conventional commit subject only. And you can see the
3:43:513 hours, 43 minutes, 51 secondsmessage and I've given it an example in future add new future. So I just a short commit message. Now we can just clean
3:43:583 hours, 43 minutes, 58 secondsthe message to remove any leading bullet or extra white space. So this is just to clean the message. Then we're going to
3:44:053 hours, 44 minutes, 5 secondsalso get the li. So we want to use to get the um the addition and deletion.
3:44:113 hours, 44 minutes, 11 secondsThe difference is the um the add and the deleted files. Then we're going to have a result. So we're going to commit now
3:44:203 hours, 44 minutes, 20 secondswith the message using box.getkit commit. And then we're going to return all of the results here and including
3:44:283 hours, 44 minutes, 28 secondsthe time addition deletion and then the branch the branch name. Let me see.
3:44:383 hours, 44 minutes, 38 secondsI think I passed the branch here at the top here. So this is it. So um now we have the commit. I think the
3:44:483 hours, 44 minutes, 48 secondslast one is going to be um I think um PR. Yes. No push. Sorry. We're going to
3:44:553 hours, 44 minutes, 55 secondshave the push commit. I'm not going to add in um PR.
3:45:023 hours, 45 minutes, 2 secondsSo P we're going to handle P by ourself.
3:45:053 hours, 45 minutes, 5 secondsSo I'm going to paste it here. So for the um get push you see description push
3:45:123 hours, 45 minutes, 12 secondscommitted changes to the remote branch and we're not going to pass in any impute. There's no schema. So we're
3:45:203 hours, 45 minutes, 20 secondsgoing to say if not branch we're going to just throw an error. Um instead of showing an error we can just return.
3:45:323 hours, 45 minutes, 32 secondsUm let's return a message here. say return um
3:45:393 hours, 45 minutes, 39 secondsbranch not um not passed
3:45:483 hours, 45 minutes, 48 secondssomething like this. Then we can say um box.git. push to the branch. Then we can
3:45:543 hours, 45 minutes, 54 secondsjust um repository with without git. So we're going to uh reposit we're going to remove the kit from the repository URL.
3:46:053 hours, 46 minutes, 5 secondsThen repos repo with branch. So we're going to say if we ask kit then we're going to we trying to um implement we're
3:46:143 hours, 46 minutes, 14 secondstrying to structure the the path to the um to the repo. So once we push changes
3:46:223 hours, 46 minutes, 22 secondsonce we push any changes we're going to return the URL. So the user can click on the URL to to the GitHub to see the
3:46:303 hours, 46 minutes, 30 secondschanges to see the um the post. Let's take the user to the repository with the
3:46:373 hours, 46 minutes, 37 secondsbranch name there. So we're going to also have the commit result. You can see box get execute and then we're going to
3:46:473 hours, 46 minutes, 47 secondsso get in the commit title and why this is error.
3:46:563 hours, 46 minutes, 56 secondsSo this is ether commit sorry.
3:47:073 hours, 47 minutes, 7 secondsOkay, so I need to remove the results. There's no resource only output.
3:47:143 hours, 47 minutes, 14 secondsSo we're just going to trim it and then we're going to say update all updates with the repository name. Then we're going to say um body creates a pull
3:47:233 hours, 47 minutes, 23 secondsrequest for the branch in this. And so the reason why we're having this right here is because I need to notify the
3:47:313 hours, 47 minutes, 31 secondsfront end. So in the front end we're going to have a button where the user is going to click to create pre. So we need
3:47:383 hours, 47 minutes, 38 secondsto notify the client side that the AI has called the tool to push uh has push
3:47:453 hours, 47 minutes, 45 secondsthe changes. So this is going to help us to we're going to just add it to the data to the state and then we're going to enable the button and then we can
3:47:533 hours, 47 minutes, 53 secondssend the stock ID the branch the body that is the P body to the back end.
3:47:583 hours, 47 minutes, 58 secondsWe're going to create an endpoint for that which is going to then um pull request. So this is just to send um
3:48:083 hours, 48 minutes, 8 secondsso notify the client and you can see the body here create a request for branch in the repository name. So we just pass the
3:48:173 hours, 48 minutes, 17 secondsbody here and then we have the title we pass in the com and then the branch and branch name. Then we can see we return these two. We have done the compare URL.
3:48:293 hours, 48 minutes, 29 secondsSo the compare URL now is repo with branch. So this is the full URL. So the URL to the GitHub is going to be
3:48:373 hours, 48 minutes, 37 secondsreturned by the AI. And then we have the um time stamp here. So
3:48:453 hours, 48 minutes, 45 secondsnow we have the gate um gate push with the um ripple and then we also notifying
3:48:553 hours, 48 minutes, 55 secondsthe client side that the AI has got the um the push to the get push to. So we're going to make the um PR button enable.
3:49:073 hours, 49 minutes, 7 secondsSo if you want to add in um want to enable AI to create P. So I'm just going to add the two for you. So but I'm going
3:49:163 hours, 49 minutes, 16 secondsto disable I'm going to um comment it out. So uh since we are handling it on the on the client side so the front end
3:49:233 hours, 49 minutes, 23 secondsthe um user is going to um be able to create P by itself. So we can skip that for the AI. But I'm just going to add in
3:49:323 hours, 49 minutes, 32 secondsthe two. So if you want to um if you prefer to enable AI to create PR. So I'm just going to say create
3:49:413 hours, 49 minutes, 41 secondsPR then I'm going to pass in the two here. So description open a pull request
3:49:483 hours, 49 minutes, 48 secondson GitHub. We call this if the user asks. So this is the case user asks.
3:49:533 hours, 49 minutes, 53 secondsThen we're going to have the title body and then the the base. So we need to also pass in.
3:50:033 hours, 50 minutes, 3 secondsSo I don't think we need to add in the base here. So what we can do is we can pass in
3:50:103 hours, 50 minutes, 10 secondsuh we can pass in the default branch here.
3:50:183 hours, 50 minutes, 18 secondsSo you can just say default branch.
3:50:263 hours, 50 minutes, 26 secondsDefault branch sorry.
3:50:393 hours, 50 minutes, 39 secondsAnd if you pass in a default branch, then you can just come back
3:50:463 hours, 50 minutes, 46 secondsto this. I'll just remove the base and I remove this. So say if not branch
3:50:543 hours, 50 minutes, 54 secondsname, I'll just return this as a branch um not passed.
3:51:043 hours, 51 minutes, 4 secondsAnd for the default branch you can just pass you can just say um con sorry
3:51:133 hours, 51 minutes, 13 secondsyou can pass title body and then you can just say default branch
3:51:193 hours, 51 minutes, 19 secondshere. Then for the base we can pass this. So let me check this.
3:51:293 hours, 51 minutes, 29 secondsOkay, I think I need to see base here.
3:51:333 hours, 51 minutes, 33 secondsDefault branch. So, this is how you're going to do it. So, I'm going to just comment it out.
3:51:413 hours, 51 minutes, 41 secondsI will comment these two out.
3:51:443 hours, 51 minutes, 44 secondsThis the first branch. So, now we have the tools now. So, we can go ahead and
3:51:523 hours, 51 minutes, 52 secondsum and import it. So, I'm going to import coding tools.
3:52:013 hours, 52 minutes, 1 secondAnd here you can pass in the default branch if you can just pass in default branch here. So if you want to add. So
3:52:093 hours, 52 minutes, 9 secondslet's go ahead and add the web to. So we're going to search for ak web search and then we're going to click on this
3:52:173 hours, 52 minutes, 17 secondsweb search agent and then we can scroll down. So we can use website from um um
3:52:243 hours, 52 minutes, 24 secondsfrom the models like we have different ways to get website to get to use um get webs to so I'm going to be using this.
3:52:323 hours, 52 minutes, 32 secondsSo I'm going to have to install this package. And then once you install it, you can just pass it like this.
3:52:403 hours, 52 minutes, 40 secondsVery simple. So let's go ahead and um open this. We can get the API key from
3:52:473 hours, 52 minutes, 47 secondsS1 dashboard or in order to see this just click in order to see this um the tools properly. So I'm just going to
3:52:553 hours, 52 minutes, 55 secondscome over here click on tools registry and then we can just click on Ezra
3:53:033 hours, 53 minutes, 3 secondsand then we can see how we can can see the um EMV we're going to add and the package. So I'm going to click on MPN.
3:53:103 hours, 53 minutes, 10 secondsI'm going to install this package and let's just go and add this to the EMV.
3:53:163 hours, 53 minutes, 16 secondsSo go to the code editor and then let's go into the back end. I'm going to paste this here. Then I'm going
3:53:243 hours, 53 minutes, 24 secondsto um let me add this here and let's install it. So 2.0.1 and this is going to install this. So
3:53:333 hours, 53 minutes, 33 secondswhile this is installing we can go to we can go to the dashboard.
3:53:393 hours, 53 minutes, 39 secondsSo we can just search for we can click on get API key and this will open the uh the website.
3:53:463 hours, 53 minutes, 46 secondsSo let me wait for this to load. So this is going to open this website.
3:53:523 hours, 53 minutes, 52 secondsyou can see um the website. So, make sure to sign in. So, I've already signed into my account already. So, you can
3:53:593 hours, 53 minutes, 59 secondsclick here and um okay, I need to log in again. So, let me wait for this to load.
3:54:063 hours, 54 minutes, 6 secondsSo, let me log into my account. And once you log into the app, you can copy the API key. So, we can click view more and
3:54:133 hours, 54 minutes, 13 secondsyou can create an API key. So, let me create an API key. So, I'm going to say base 64 and click on create create key.
3:54:223 hours, 54 minutes, 22 secondsand I can copy this key. So I'm going to copy this and I'm going to go for back to the code and in the code we're going to add in XA API key and we're going to
3:54:323 hours, 54 minutes, 32 secondspass this here. So once we have this we can go back to the session service and let's scroll up to the top and let's we
3:54:413 hours, 54 minutes, 41 secondscan import it. So I'm going to import it here. I'll paste it here. So I'm going to import web search from this package
3:54:473 hours, 54 minutes, 47 secondsand we can copy website. Um, let's scroll down to where we have the
3:54:553 hours, 54 minutes, 55 secondsYeah, here. So, we can just pass web search. So, I'm going to name it web search.
3:55:023 hours, 55 minutes, 2 secondsAnd then we can pass in web search. Then call it like this.
3:55:083 hours, 55 minutes, 8 secondsAnd now we can see that um the active tool will be passed to pass into the tools. And I think everything is fine. I think we are done with this.
3:55:203 hours, 55 minutes, 20 secondsSo let's go into the controller. So I'll go to let me close this and inside the
3:55:303 hours, 55 minutes, 30 secondscontroller we can go to session controller and let's import the service.
3:55:383 hours, 55 minutes, 38 secondsSo I think we are done with the search uh session chat controller get session by ID stock ID controller and then get
3:55:463 hours, 55 minutes, 46 secondsuser sessions. So the last endpoint we're going to create is the endpoint like I mentioned previously inside the GitHub to. So I'm going to scroll down
3:55:553 hours, 55 minutes, 55 secondsto where uh we have the push to the GitHub push to. So I mentioned that once
3:56:013 hours, 56 minutes, 1 secondthe AI call is two, it's going to um push the changes push to this branch and
3:56:083 hours, 56 minutes, 8 secondsthen we're going to try to remove the G from the rep URL that is a clone URL and we're going to construct the um the
3:56:163 hours, 56 minutes, 16 secondsGitHub URL. So once the user once the air so we can have the link display on the client side and the user can click
3:56:243 hours, 56 minutes, 24 secondsit and go to the GitHub. Then we we also have the comet. Uh we're just going to just get title for it.
3:56:333 hours, 56 minutes, 33 secondsAnd we can even ask the AI to even generate um the commit title or we can just leave it like this. And then what
3:56:423 hours, 56 minutes, 42 secondswe're going to do, you're going to then um we're going to send a custom event to the client side. So this is going to um
3:56:513 hours, 56 minutes, 51 secondsnotify the client side that the air has made a push and we're going to enable a button which if the user click is going
3:56:583 hours, 56 minutes, 58 secondsto call an endpoint to um to create a pull request. So that's the endpoint we're going to create now. So the client
3:57:063 hours, 57 minutes, 6 secondsis going to be sending us f ID I think the title and the body and then we are going to um call the endpoint then use
3:57:153 hours, 57 minutes, 15 secondsthis box uh the box the obstach box and we're going to create a pull request. So let's go ahead and create that endpoint.
3:57:233 hours, 57 minutes, 23 secondsSo I will go back let's go into session controller and we can create the endpoint here. So
3:57:313 hours, 57 minutes, 31 secondsI'll collapse this. So we can call this export constant create uh a session
3:57:383 hours, 57 minutes, 38 secondscreate pull request or let's call it create p request. So
3:57:453 hours, 57 minutes, 45 secondslet me leave it like this create pull request
3:57:513 hours, 57 minutes, 51 secondsand we can say async handler async and let's pass in request here.
3:58:013 hours, 58 minutes, 1 secondtype request response and let's return this. So we're going to
3:58:103 hours, 58 minutes, 10 secondsget the user ID. So say constant user id is going to be equals to request dot
3:58:173 hours, 58 minutes, 17 secondsuser doc ID and we're going to get this log id. So we're going to get sl ID from the params and then we can also create
3:58:253 hours, 58 minutes, 25 secondsyou can you can also create um a validator to get the log and we need to also get the body and the title and the
3:58:333 hours, 58 minutes, 33 secondsbody. So say title um body is going to be equals to so let's
3:58:413 hours, 58 minutes, 41 secondsquickly go and create the validator. So I'll go into file folder and go into
3:58:483 hours, 58 minutes, 48 secondsokay I think it's session here and here we also have this log id. So we can use this for this log ID and pass in the
3:58:553 hours, 58 minutes, 55 secondsrequest par. So let's add so I paste it here. So this is going to be title optional body and then we can use it. So
3:59:043 hours, 59 minutes, 4 secondsI just copy create pull request schema and I'll go into the controller session controller and we can pass this here and
3:59:123 hours, 59 minutes, 12 secondssay pass and then we can pass in the request body.
3:59:213 hours, 59 minutes, 21 secondsSo we can also do the same thing for the search bar. So I just go to validator. We can copy this. So this is compulsory.
3:59:293 hours, 59 minutes, 29 secondsThe user need to pass in this log ID. So let me save this first and then we can
3:59:363 hours, 59 minutes, 36 secondspass this here. So uh instead of so just pass and I'm going to say dot just I
3:59:443 hours, 59 minutes, 44 secondspass in the the query par. So let's import both of them.
3:59:533 hours, 59 minutes, 53 secondsSo I think I've used this before. So let me import create P request schema.
4:00:024 hours, 2 secondsSo now we're going to create a service. So say constant data is equals to await uh session.
4:00:134 hours, 13 secondsSo let me just change this to create um p
4:00:194 hours, 19 secondsrequest service and I'm going to just change this to
4:00:284 hours, 28 secondscreate create p request controller
4:00:374 hours, 37 secondsand then we're going to pass in the user ID stock ID
4:00:454 hours, 45 secondstitle and then body.
4:00:514 hours, 51 secondsAnd we're just going to return response
4:00:594 hours, 59 secondsstatus http status.
4:01:094 hours, 1 minute, 9 secondsOkay.
4:01:134 hours, 1 minute, 13 secondsAnd we're going to say dot JSON and let's just return data. Yeah. So we can
4:01:214 hours, 1 minute, 21 secondsjust say object data data and you can add a message if you want.
4:01:284 hours, 1 minute, 28 secondsSo let's quickly go ahead and create this um create the P request service. So I'm going to session service and I'm going to collapse this.
4:01:444 hours, 1 minute, 44 secondsSo let me remove this constants.
4:01:484 hours, 1 minute, 48 secondsSo let's go this and then we can just say export constant
4:01:564 hours, 1 minute, 56 secondsFacebook request service async and then
4:02:024 hours, 2 minutes, 2 secondsso we can have user ID which is of type string stock ID ID which is of type string.
4:02:164 hours, 2 minutes, 16 secondsSorry, I think I made a mistake. It should be like this.
4:02:244 hours, 2 minutes, 24 secondsAnd then we're going to have um I think title and um body.
4:02:364 hours, 2 minutes, 36 secondsSo, let me just add string here. Type string.
4:02:494 hours, 2 minutes, 49 secondsYeah, this is fine. So the first thing we're going to do is we're going to first of all get the session using the SL ID and the user ID. So we're going to
4:02:584 hours, 2 minutes, 58 secondssay constant session is equals to await session
4:03:054 hours, 3 minutes, 5 secondssession model dot find one.
4:03:124 hours, 3 minutes, 12 secondsI'll pass in the user ID and this log ID.
4:03:194 hours, 3 minutes, 19 secondsThen we're going to say if if not session
4:03:254 hours, 3 minutes, 25 secondsthen we can throw let's say new um not found exception is a session not found.
4:03:404 hours, 3 minutes, 40 secondsAnd we're going to so check if if not session box id
4:03:494 hours, 3 minutes, 49 secondsand then we can throw new bad requests
4:03:574 hours, 3 minutes, 57 secondsa session we say um session um
4:04:054 hours, 4 minutes, 5 secondsor we can just say sandbox not available.
4:04:154 hours, 4 minutes, 15 secondsAnd then we're going to check if if not repo name then sorry session reple name.
4:04:304 hours, 4 minutes, 30 secondsSo we can just throw new um bad request exception is a repository
4:04:394 hours, 4 minutes, 39 secondsrepository uh not available
4:04:484 hours, 4 minutes, 48 secondsand lastly if um if not branch name. So I think uh this
4:04:554 hours, 4 minutes, 55 secondsis going to be compulsory. you might not need a check for both reple and the branch name because we've added in a database that must exist. So I'm just
4:05:054 hours, 5 minutes, 5 secondsgoing to just add it for so let me just add it here. I'll just say um branch.
4:05:164 hours, 5 minutes, 16 secondsSo let me add session here.
4:05:204 hours, 5 minutes, 20 secondsSo now the next thing we are going to do is to retrieve the box. We're going to say constant box for the sandbox is equals to await
4:05:294 hours, 5 minutes, 29 secondsand let's say get box and we're going to pass in session dobox
4:05:384 hours, 5 minutes, 38 secondsid and then we need to cd into the branch
4:05:494 hours, 5 minutes, 49 secondssorry into the repository. We're going to say box cd
4:05:554 hours, 5 minutes, 55 secondssay session do repo name
4:06:034 hours, 6 minutes, 3 secondsand then we can do try catch here and we're going to say await um boxkit
4:06:144 hours, 6 minutes, 14 secondssorry dot check out we are going to check out to the branch check note
4:06:224 hours, 6 minutes, 22 secondsbranch session uh the session branch name
4:06:354 hours, 6 minutes, 35 secondsand if this is going to give us any error we can just use box it get execute
4:06:444 hours, 6 minutes, 44 secondsuh ax and we can just use checkout out
4:06:524 hours, 6 minutes, 52 secondssession dot branch uh name.
4:07:014 hours, 7 minutes, 1 secondSo let me confirm is the same I have here inside the ensure.
4:07:084 hours, 7 minutes, 8 secondsOkay, I added be here. So let me copy this just add it here. So now we have this.
4:07:174 hours, 7 minutes, 17 secondsNow we can create a pull request. We can say constant B r is equals to await
4:07:254 hours, 7 minutes, 25 secondsum box.get execute dot create PR
4:07:344 hours, 7 minutes, 34 secondsand we can give this title which is going to be title the title and we can just say all we can
4:07:424 hours, 7 minutes, 42 secondsconstruct a title update uh session
4:07:494 hours, 7 minutes, 49 secondsrepo name and we can give this a body body
4:07:584 hours, 7 minutes, 58 secondsum um I'll just say create a pull request
4:08:114 hours, 8 minutes, 11 secondssession do reple name so we can okay let's add session here.
4:08:244 hours, 8 minutes, 24 secondsSo the title and the body you can ask the AI to pass it here in the MU schema.
4:08:314 hours, 8 minutes, 31 secondsThe AI can pass in the um the commit
4:08:374 hours, 8 minutes, 37 secondscan pass in the commit title and also um we can ask it to add in the PL body. So
4:08:474 hours, 8 minutes, 47 secondsthis if you want you can ask it to add it but I'll just leave it for now.
4:08:544 hours, 8 minutes, 54 secondsSo instead of getting the result um this here instead of getting the comet result we can just use um you can pass in uh
4:09:044 hours, 9 minutes, 4 secondsthe impure schema. So the AI is going to give us the comet title and also the body if you want. So I'm just going to
4:09:124 hours, 9 minutes, 12 secondsleave it like this and then I'm going to go back to the service and let's return this. So we need to pass in the base. So
4:09:204 hours, 9 minutes, 20 secondswe forgot this is the default branch. So say session dot default default branch
4:09:314 hours, 9 minutes, 31 secondsand then let's return um the URL. So plural.
4:09:394 hours, 9 minutes, 39 secondsSo I think on the client on the controller side we return data.
4:09:484 hours, 9 minutes, 48 secondsSo let's import this.
4:09:544 hours, 9 minutes, 54 secondsSo there's an error here. So let's go into the service and let me add option here. And yeah.
4:10:054 hours, 10 minutes, 5 secondsSo I think this should stop the error. Let me check.
4:10:124 hours, 10 minutes, 12 secondsYeah, the error has stopped. So guys, um let's let's go ahead and test this test this um the back end. So let's go into
4:10:204 hours, 10 minutes, 20 secondsHTTPS and let me create a session http.
4:10:284 hours, 10 minutes, 28 secondsBefore we do this, let's go into the service. Sorry, the uh source directory.
4:10:334 hours, 10 minutes, 33 secondsWe forgot to create a route. So let's go into route.
4:10:374 hours, 10 minutes, 37 secondsLet's create session route.tx and I'll just copy I just copy this.
4:10:504 hours, 10 minutes, 50 secondsI'll come into session route and I'll paste this here. I'll change this to session route. So here we're going to say all.
4:11:004 hours, 11 minutesSo this is going to fetch all the uh session. So let me come inside there and we can just copy get user session and
4:11:084 hours, 11 minutes, 8 secondslet's go into the route. So let me scroll to or let me just go into session
4:11:164 hours, 11 minutes, 16 secondswork like this and I'm going to import this. I remove this I pass this here.
4:11:214 hours, 11 minutes, 21 secondsI'll change this to session controller. So we need to also pass in let me remove this. Go back. I'll just
4:11:304 hours, 11 minutes, 30 secondsduplicate the first one and instead of all we're going to so to get a single um
4:11:384 hours, 11 minutes, 38 secondsa single um uh what do you call it a single session
4:11:444 hours, 11 minutes, 44 secondssorry I'll say snug snug ID
4:11:514 hours, 11 minutes, 51 secondsand I can go into the controller again and I can copy this get single And I'm going to just replace this here.
4:12:034 hours, 12 minutes, 3 secondsI will import it too.
4:12:074 hours, 12 minutes, 7 secondsSo we can also get the PL. So I'll say SL ID / PL.
4:12:174 hours, 12 minutes, 17 secondsSo I can go into into the uh let me remove this.
4:12:234 hours, 12 minutes, 23 secondsI think it's create create um
4:12:314 hours, 12 minutes, 31 secondsokay create pull request controller so I move this up here and lastly we have we're going to change
4:12:404 hours, 12 minutes, 40 secondsthis to post and this is going to be chat and this is going to be session
4:12:474 hours, 12 minutes, 47 secondssession session chat controller and let me change this to
4:12:574 hours, 12 minutes, 57 secondsand now we can go into the index of cxs tx sorry and let's say router
4:13:044 hours, 13 minutes, 4 secondsdo use slash session
4:13:124 hours, 13 minutes, 12 secondswe can pass in session route here and let's import session route so import
4:13:204 hours, 13 minutes, 20 secondssession route from dot session route.
4:13:284 hours, 13 minutes, 28 secondsSo I think everything is fine.
4:13:314 hours, 13 minutes, 31 secondsSo let me try and see if we can test this in the in uh with um http. So I'm going to clear the um the endpoint here.
4:13:424 hours, 13 minutes, 42 secondsSo I've already um have already written the u the endpoint. So there's some
4:13:484 hours, 13 minutes, 48 secondsmistake we made made inside the route inside session route this should be post
4:13:584 hours, 13 minutes, 58 secondsnot get the p should be post not get then inside the session controller we
4:14:054 hours, 14 minutes, 5 secondsdidn't return we return this so I need to remove this and I'm going to say return
4:14:124 hours, 14 minutes, 12 secondsa wait session chat service we need You can remove the await here.
4:14:224 hours, 14 minutes, 22 secondsSo let me just leave it there. So inside the service session service, let me see.
4:14:324 hours, 14 minutes, 32 secondsWe have a sync here. Okay, this is fine.
4:14:364 hours, 14 minutes, 36 secondsSo let's go ahead and test it. So what we're going to do first is to let me go into the HTTP
4:14:444 hours, 14 minutes, 44 secondsuh section. on the HTTP. So the first endpoint we're going to test is this local API chart. So I need to get a SL
4:14:534 hours, 14 minutes, 53 secondsID. So I'm just going to generate a SL ID. I'll just pick this one I have here.
4:14:584 hours, 14 minutes, 58 secondsI'll just pass it here. So I need to set a repo URL and a stock ID. So I'll go into GitHub.
4:15:074 hours, 15 minutes, 7 secondsSo I can just let me clear all of this.
4:15:084 hours, 15 minutes, 8 secondsto the SL and then inside session. So let's go
4:15:154 hours, 15 minutes, 15 secondsinto G http and I'm going to just click on send. So I want to retrieve all the repository.
4:15:254 hours, 15 minutes, 25 secondsLet me check my server.
4:15:304 hours, 15 minutes, 30 secondsOkay, my server is not running. So npm npm rundev.
4:15:404 hours, 15 minutes, 40 secondsSo the server is running now and let me try again. Click on get repository.
4:15:484 hours, 15 minutes, 48 secondsSo it say GitHub account not found.
4:15:514 hours, 15 minutes, 51 secondsOkay. Yeah it's true. Remember I disconnected my account. So let me try and connect again. So I'm going to click
4:15:584 hours, 15 minutes, 58 secondson send and then let me click let me copy this and I'm going to quickly connect my account. I've already
4:16:054 hours, 16 minutes, 5 secondsconnected my account and we can see all the repos. So I'm going to pick this one. Let me pick um we can see the repo
4:16:124 hours, 16 minutes, 12 secondsURL here the clone URL. So I'll copy this and I'll click on this then click on session. Then I'm going to pass this
4:16:224 hours, 16 minutes, 22 secondshere. Then we need to get a default branch. The default branch here you can see the default branch here is
4:16:304 hours, 16 minutes, 30 secondsthis. So this is an example of let me pick the one that I so I worked on this um branch. This branch was used when I
4:16:394 hours, 16 minutes, 39 secondswas creating this project. That's why you can see default branch is base 44.
4:16:454 hours, 16 minutes, 45 secondsSo we can just pick a different branch. So let me pick this one.
4:16:524 hours, 16 minutes, 52 secondsThis one I have a sample. I'll just use this one that has main.
4:16:574 hours, 16 minutes, 57 secondsSorry, let me paste it here. So, I'm just going to type in main. And this is it. So, let me say list the or send this
4:17:064 hours, 17 minutes, 6 secondsum message. So, make sure you've added the um AI SDK key. So, let me click on it. So, I've added AI gateway API key.
4:17:154 hours, 17 minutes, 15 secondsSo, I'm going to delete this API key once the once I'm done with the video.
4:17:184 hours, 17 minutes, 18 secondsSo let me cancel this and I'm going to click on send. So let's see hopefully this work. So let me click on send there.
4:17:304 hours, 17 minutes, 30 secondsSo internal server error. So let me see.
4:17:334 hours, 17 minutes, 33 secondsSo let's go ahead and check why internal server error. So I'll go into the service and I'm going to go into the
4:17:404 hours, 17 minutes, 40 secondserror med first. Let's go into the error handler and let's um pass in error here.
4:17:484 hours, 17 minutes, 48 secondsSo we can see the error. Say error. So error dot message
4:17:554 hours, 17 minutes, 55 secondsand save this. Now let's go into let's go back to the HTTP
4:18:014 hours, 18 minutes, 1 secondsession and let's click on save now. So I'm going to click on this.
4:18:084 hours, 18 minutes, 8 secondsAnd now we can see the error session validation fite. Okay. Yeah. So I think the problem is coming from the model. So
4:18:154 hours, 18 minutes, 15 secondsin the model uh session model we set box ID uh I think box ID required and if we go back to the session service.
4:18:284 hours, 18 minutes, 28 secondsSo if I go scroll to where we create a get session notice that we create the model first before we attach the
4:18:354 hours, 18 minutes, 35 secondssession. So what I'm going to do I'm going to move this to the top and I'm just going to remove this.
4:18:434 hours, 18 minutes, 43 secondsI'm going to just pass in box ID. Yeah, this is going to be box ID.
4:18:514 hours, 18 minutes, 51 secondsHopefully, this should fix it.
4:18:554 hours, 18 minutes, 55 secondsThis will fix the issue. So, I'm going to change this to let's call this report.
4:19:014 hours, 19 minutes, 1 secondBut this must be aable. So, let's just try it again. So, make sure the server is running. So, let me check my server
4:19:084 hours, 19 minutes, 8 secondsis running and let me wait for Okay, database is connected. So let me go back again into
4:19:164 hours, 19 minutes, 16 secondsuh the session HTTP and let me click on send.
4:19:224 hours, 19 minutes, 22 secondsNow I'm going to click concern. Okay, no export.
4:19:294 hours, 19 minutes, 29 secondsNo export mean in this part. So we having issue with the box now. So I'm
4:19:364 hours, 19 minutes, 36 secondsgoing to just go no export main.
4:19:434 hours, 19 minutes, 43 secondsSo let's go to where we have the sandbox.
4:19:514 hours, 19 minutes, 51 secondsSo that should be inside the leaf folder inside sandbox.
4:19:584 hours, 19 minutes, 58 secondsSo the problem is coming from upst like I said upst and in our ts config we're
4:20:054 hours, 20 minutes, 5 secondsusing common JS and this is going to give us more issues. So I think I found a trick on how we going to handle this.
4:20:134 hours, 20 minutes, 13 secondsSo the sidecript does not complain. So I'm going to update this and I'm going to use this like this. I'll just change
4:20:204 hours, 20 minutes, 20 secondsthis to load box and hopefully this should um work. So I'm going to just um
4:20:284 hours, 20 minutes, 28 secondsI'm going to save this now and make sure my server is running. So let's wait for it.
4:20:394 hours, 20 minutes, 39 secondsSo the server is running now. I'm just going to try it again. So I'll go to session types uh session session http and I'm going to click on send over.
4:20:524 hours, 20 minutes, 52 secondsLet's see.
4:20:574 hours, 20 minutes, 57 secondsSo this might take some time but let's wait for it. And now we can see the results. Now we can see um the type we
4:21:074 hours, 21 minutes, 7 secondscan see the title was generated list file session this file session and then
4:21:154 hours, 21 minutes, 15 secondswe can see the repo data we can see uh the rep name the rep URL and then the branch name so the branch name that was
4:21:234 hours, 21 minutes, 23 secondsgenerated list file and the unique ID then we can see the first type that was sent by the AI.
4:21:324 hours, 21 minutes, 32 secondsSo if you look at this is reasoning data and this is the two core you can see the two code that was called was list uh
4:21:414 hours, 21 minutes, 41 secondsthis is the impute data the part was dot and the impute data the then the two
4:21:494 hours, 21 minutes, 49 secondsinput available we can see two name list part provider uh this is um entropic and then two output this is where the output
4:21:584 hours, 21 minutes, 58 secondsis you can see file readme workspace is uh home base um demo base
4:22:054 hours, 22 minutes, 5 secondsfor for example readme.md. So basically it is working. So this only read inside the file inside the repository and we
4:22:134 hours, 22 minutes, 13 secondscan see it's done. So if you go to the browser and confirm this if I go to the repository this repository we can see only readme and you can see what is
4:22:224 hours, 22 minutes, 22 secondsinside the um readme. So guys this is working fine. So before we go ahead and start working on the client, I notice we
4:22:314 hours, 22 minutes, 31 secondsum something we've now implement. So if you go to the session service, we have um the unfinish messages where the
4:22:404 hours, 22 minutes, 40 secondsmessages all these message the AI is going to return is supposed to save and we need to create this inside the
4:22:464 hours, 22 minutes, 46 secondsmessage service. So I'll go into message service and this is it here message service and I'm going to paste in the uh
4:22:554 hours, 22 minutes, 55 secondsthe service here. So basically this is just to obsert the messages. So we're going to pass in session ID and the
4:23:024 hours, 23 minutes, 2 secondsmessages and we're going to say if not if not session ID just throw this and we're going to check if the array if the
4:23:094 hours, 23 minutes, 9 secondsmessage is an array. If not we train just return empty array. Then we're going to sanitize the message. We're going to use this method we have here
4:23:194 hours, 23 minutes, 19 secondsand then we're going to loop through the message the we're going to loop through it. So we're going to say synize messages and then we are going to say
4:23:264 hours, 23 minutes, 26 secondsconstant message ID. So we're going to get the ID or we're going to generate one from AI. So just import it from AI
4:23:344 hours, 23 minutes, 34 secondsand then we're going to call message model dot find one and update pass in the session ID the message ID and then
4:23:424 hours, 23 minutes, 42 secondsthe session ID there. We're going to set this the row and the and the path. Then we're going to offset new true and then we're going to return the messages. So
4:23:504 hours, 23 minutes, 50 secondsI'm just going to copy the offsert uh session message service and then we can pass it here. We can just say await
4:23:594 hours, 23 minutes, 59 secondspass this here and make sure you import it. So I'll pass in uh session ID
4:24:064 hours, 24 minutes, 6 secondssession dot ID and then we can pass in messages here. So test script. So I'm just going
4:24:154 hours, 24 minutes, 15 secondsto do um dot two string.
4:24:224 hours, 24 minutes, 22 secondsSo I see if the error will stop and the error should stop there. So that
4:24:294 hours, 24 minutes, 29 secondsis it. So now you can go ahead and start working on the client side. In this chapter we're going to start working on the client side. So in command code I
Chapter 9: Frontend Setup
4:24:384 hours, 24 minutes, 38 secondshave the test for client which can be we can use it to scaffold a react app. So I'm going to use it to create the folder
4:24:464 hours, 24 minutes, 46 secondsstructure but I'm going to just um try and install it myself first to show you how to install the ad fit CSS shant and
4:24:554 hours, 24 minutes, 55 secondsand router. Then I'm going to use command code which also know how to install it. You can see it knows how to install it and add CSS and chant and
4:25:044 hours, 25 minutes, 4 secondsalso add a page structure. So I use it for the base structure that I'm going to install. So let's just go to fit and let's install by ourself. So the first
4:25:124 hours, 25 minutes, 12 secondsthing we're going to do is to copy MPS create fit the test. So I'll copy this and let's head back to the code and then inside the client I'm going to open a
4:25:214 hours, 25 minutes, 21 secondsterminal and I'm going to go into a new um so I'm going to clear this and then
4:25:284 hours, 25 minutes, 28 secondsI'm going to cd into client and then I'm going to clear the terminal. Then I'm going to paste this here and click enter.
4:25:394 hours, 25 minutes, 39 secondsSo um this is going to um create a new vit app and let's just give it um dot
4:25:474 hours, 25 minutes, 47 secondshere and click on files and continue. Let's pick
4:25:544 hours, 25 minutes, 54 secondsreact type script and just click on yes. And this is going to sc the project and you can see that it has created a folder
4:26:034 hours, 26 minutes, 3 secondsstructure. So we can go to the browser now and let's go and copy the CSS. So we can close this out now. Let's go to the
4:26:114 hours, 26 minutes, 11 secondsCSS and go to documentation. Just click on this button and should take you can see V. So we need to install this.
4:26:204 hours, 26 minutes, 20 secondsSo we can copy this and let's go back to the code and let's wait for V to install. Then we're going to add we're
4:26:284 hours, 26 minutes, 28 secondsgoing to install things CSS vit. While this is installing, let's go and um pull the client from command code. So, I'll
4:26:364 hours, 26 minutes, 36 secondsgo to command code client and let me copy this cmd and this is going to be cmd test pull um my username and the client/client.
4:26:474 hours, 26 minutes, 47 secondsSo, I'll go back to the code and I'm going to open a new tab and since command code is already inside this main
4:26:564 hours, 26 minutes, 56 secondsum directory so I'm going to add it here. So, I'll paste it now. It's going to pull this test and then oh sorry I
4:27:044 hours, 27 minutes, 4 secondsthink command code p client. So let me try it again.
4:27:124 hours, 27 minutes, 12 secondsSo something is wrong. So let me try and use mpx and see. Oh there's no problem.
4:27:174 hours, 27 minutes, 17 secondsWe can use um this to pull this. I'll just u paste it here inside.
4:27:254 hours, 27 minutes, 25 secondsI'll paste it inside here.
4:27:304 hours, 27 minutes, 30 secondsSo let me remove all of this and click on enter.
4:27:394 hours, 27 minutes, 39 secondsSo you should know I should add the it should pull this test inside directory. Let's see
4:27:474 hours, 27 minutes, 47 secondscuz while this is running I think this uh the client side has already installed. So we can just
4:27:534 hours, 27 minutes, 53 secondscancel the server and let's go to the browser.
4:27:584 hours, 27 minutes, 58 secondsAnd then let's go to the CSS and copy this again.
4:28:034 hours, 28 minutes, 3 secondsLet's go back to the code and let me paste this here. And this should install. While this is
4:28:104 hours, 28 minutes, 10 secondsinstalling, let's go back to the browser and let's go ahead and copy this. So,
4:28:164 hours, 28 minutes, 16 secondswe're going to add in CSS here. So, copy this and then we're going to add CSS here. So, let's go back.
4:28:274 hours, 28 minutes, 27 secondsAnd then let's go into vit.ts. And then let's add it here.
4:28:364 hours, 28 minutes, 36 secondsThen let's add CSS here.
4:28:434 hours, 28 minutes, 43 secondsAnd then inside the index.tx inside um index CSS. So I'm going to remove this app CSS.
4:28:574 hours, 28 minutes, 57 secondsAnd let's go into index CSS. I'm going to remove all of this. And then we can import CSS here. So now let's let's add
4:29:064 hours, 29 minutes, 6 secondsShanty UI. So we can go back to the browser and we can remove CSS now. And let's go to talk.
4:29:154 hours, 29 minutes, 15 secondsLet's click on okay. First we need to initialize this. So I click on copy this or we can click on V here.
4:29:234 hours, 29 minutes, 23 secondsSo we can also copy this again. Um MPS shant in it. So go back to the um code and let
4:29:324 hours, 29 minutes, 32 secondsme open my terminal. Let me clear this and I'm going to paste it now and click on enter.
4:29:404 hours, 29 minutes, 40 secondsSo remember this is under the client directory client directory. So let's wait for it. So I'm using Shanti 4.8.0
4:29:494 hours, 29 minutes, 49 secondsand this is going to add Shanti into the project. So let's wait. So we're going to pick reict. Pick the first one.
4:29:584 hours, 29 minutes, 58 secondsAnd we can see it says CSS V4.
4:30:034 hours, 30 minutes, 3 secondsOkay. We need to add in the TS to tracing. So let's go back to the browser
4:30:114 hours, 30 minutes, 11 secondsand let's scroll. So scroll down. You see you should see how to add it. So scroll down to the bottom.
4:30:194 hours, 30 minutes, 19 secondsOkay. After. So we add this. Now you can see we need to go to um need to go to TS config JSON and then TS config app JSON.
4:30:304 hours, 30 minutes, 30 secondsSo just copy this and let's go back to the code and I'm going to
4:30:384 hours, 30 minutes, 38 secondsuh TS config first and we need to add it here.
4:30:464 hours, 30 minutes, 46 secondsSo let's go to the browser.
4:30:504 hours, 30 minutes, 50 secondsSo let's scroll down now. So TS config app JSON I'll copy it
4:31:014 hours, 31 minutes, 1 secondand let me go to the code and TS config app JSON. So I'm going to add it here.
4:31:164 hours, 31 minutes, 16 secondsOkay. I think I supposed to add this here
4:31:274 hours, 31 minutes, 27 secondsand the error should stop.
4:31:304 hours, 31 minutes, 30 secondsSo let's go back to the code to the browser and we need to install this. So I'll
4:31:364 hours, 31 minutes, 36 secondscopy it and then let's go back to the code and let me install this. So paste it and
4:31:464 hours, 31 minutes, 46 secondsclick on enter and this should stop.
4:31:574 hours, 31 minutes, 57 secondsOkay, we can just leave this. Let's go back to the browser again and we can copy this resolve.
4:32:074 hours, 32 minutes, 7 secondsSo I'll go back to the code editor and going to F vit config and I'm going to pass it here.
4:32:164 hours, 32 minutes, 16 secondsLet's import part
4:32:274 hours, 32 minutes, 27 secondsand let's save this. So let's make sure everything is fine. So close this open
4:32:344 hours, 32 minutes, 34 secondsmy terminal and this has already installed. Now we can run um shanti in it. So let me still confirm this.
4:32:494 hours, 32 minutes, 49 secondsSo let's pick radics and this should install all of this. So let me go back to this and you can see let's click on enter.
4:33:064 hours, 33 minutes, 6 secondsSo while this is going, we're going to add in let's go into um inside C index for CSS app. Let's
4:33:164 hours, 33 minutes, 16 secondsremove this. Let's remove everything here.
4:33:244 hours, 33 minutes, 24 secondsSo we just have here all of this
4:33:354 hours, 33 minutes, 35 secondsand then we're going to go into index CSS and you already add in the stars.
4:33:574 hours, 33 minutes, 57 secondsOkay, it's still installing. So, let's wait for it. So, Shant has already installed. So, let me go into index CSS
4:34:054 hours, 34 minutes, 5 secondsand I'm going to replace this with the one I have. So, we can copy it from GitHub. So, I'll just remove this. I'm going to paste this here. And you can
4:34:134 hours, 34 minutes, 13 secondssee it's just it's still the same um root t and um the theme. So just copy
4:34:214 hours, 34 minutes, 21 secondsthe one we have. Then we can go ahead and install um components here. So I'm going to go into the component folder.
4:34:274 hours, 34 minutes, 27 secondsAnd we see that we have only the button here. So let's add in some component. So I'll say um
4:34:344 hours, 34 minutes, 34 secondsthis to add.
4:34:384 hours, 34 minutes, 38 secondsSo let's select um let's select alert and then I'm going to select um avatar
4:34:474 hours, 34 minutes, 47 secondsbadge button group. Then we're going to synthesize um let's come back to
4:34:544 hours, 34 minutes, 54 secondsum SS collapsible command dialog
4:35:034 hours, 35 minutes, 3 secondsdropown menu empty state we're going to add in form
4:35:094 hours, 35 minutes, 9 secondsand this is impute impute group label
4:35:184 hours, 35 minutes, 18 secondswe can pop profile and scroll area. Select separator side
4:35:264 hours, 35 minutes, 26 secondsbusing sona spinner um table I think test area and to tip
4:35:364 hours, 35 minutes, 36 secondsI think that is all. So let's click on enter and then we can wait for this to um to
4:35:444 hours, 35 minutes, 44 secondsadd all the components. So let's go to let's go to the browser. So we're going to add in the dark mode. So let's scroll
4:35:524 hours, 35 minutes, 52 secondsto the bottom and we should see um dark mode here. This is fit and let's copy
4:35:594 hours, 35 minutes, 59 secondsthis and let's go back to the code and I'm going to create the file inside
4:36:064 hours, 36 minutes, 6 secondscomponent here. So let's say team provider tx and let's paste this here.
4:36:194 hours, 36 minutes, 19 secondsSo let's go back to the browser and then we can scroll down.
4:36:254 hours, 36 minutes, 25 secondsSo we need to add this to let's copy it.
4:36:304 hours, 36 minutes, 30 secondsLet's go back to the code and then we're going to add it inside the main.tx. TX.
4:36:384 hours, 36 minutes, 38 secondsSo just paste this here. I move this inside. Remove the children. And then I'm going to import this from team
4:36:474 hours, 36 minutes, 47 secondsprovider. And then I also want to add import toaster toaster from UI.
4:36:594 hours, 36 minutes, 59 secondsAnd then we also need to add in I think yeah the two tip. So I'm just going to add it here.
4:37:084 hours, 37 minutes, 8 secondsSo let me just add it here.
4:37:114 hours, 37 minutes, 11 secondsAnd I'm going to import it from UI. So make sure you add which color here. And I'm going to change this to M.
4:37:204 hours, 37 minutes, 20 secondsSo now we have this. Now we can go into the app.tx tx and then we can just
4:37:264 hours, 37 minutes, 26 secondsimport button component here
4:37:314 hours, 37 minutes, 31 secondsand just say um click me and save this and let's make sure the server is running.
4:37:414 hours, 37 minutes, 41 secondsSo I'll just go to mpm rundev and let's wait for this to run. Now you
4:37:514 hours, 37 minutes, 51 secondscan see so before we go to the browser check this out. So let's copy this.
4:37:554 hours, 37 minutes, 55 secondsLet's go to the back end and let's make sure to update this. Okay you can see update this with it. So now
4:38:054 hours, 38 minutes, 5 secondslet's go ahead and check this out. So I'll go to the browser and go to it. And now we can see the
4:38:124 hours, 38 minutes, 12 secondsbutton. So it's a blue color and this is it. So now we going to go ahead and start working setting up the react
4:38:194 hours, 38 minutes, 19 secondsrouter. Then we're going to um create the pages.
Chapter 10: Frontend Routes & SideBar
4:38:254 hours, 38 minutes, 25 secondsLet's go ahead and install router. So I'll cancel my server and npm install
4:38:324 hours, 38 minutes, 32 secondsrouter done and click on enter. And this let's wait for this to install. Now we have router installed. Let's check the
4:38:394 hours, 38 minutes, 39 secondsversion. So I'm going to package JSON and you should see we have router 7.15.1.
4:38:474 hours, 38 minutes, 47 secondsSo now we have this. So the first thing I'm going to do, I'm going to create the pages folder. So I need to create the uh first of all create the the pages. Then
4:38:564 hours, 38 minutes, 56 secondsinside here I'm going to create uh I'm going to create a folder.
4:39:024 hours, 39 minutes, 2 secondsAnd inside the I'm going to create a sign in signin.tx.
4:39:084 hours, 39 minutes, 8 secondsAnd here we can just do fce. I'll just call this sign in page.
4:39:174 hours, 39 minutes, 17 secondsand let's remove this. So I just copy this and I'm going to create sign up page
4:39:254 hours, 39 minutes, 25 secondssign up cxx and I'll paste this just change this to sign up
4:39:334 hours, 39 minutes, 33 secondsand this to up and then we going to create another
4:39:404 hours, 39 minutes, 40 secondspage. So I'll call this home home and we can just say index index dot um index cx
4:39:514 hours, 39 minutes, 51 secondsand we say rce home page so I'll remove this and the last page
4:40:004 hours, 40 minuteswe're going to create is too much page two more pages so I'll just create in um
4:40:074 hours, 40 minutes, 7 secondslet's call it single session We can call this session. Let's call it session.
4:40:174 hours, 40 minutes, 17 secondsUm session and let's do index
4:40:244 hours, 40 minutes, 24 secondscxce session.
4:40:354 hours, 40 minutes, 35 secondsOh, let me just change it to single session.
4:40:394 hours, 40 minutes, 39 secondsSo say single single session. Yeah, session by by log something like that.
4:40:514 hours, 40 minutes, 51 secondsLet me just leave it there. All right.
4:40:524 hours, 40 minutes, 52 secondsSo I'm just going to change this to session page.
4:41:034 hours, 41 minutes, 3 secondsSo let me add page here.
4:41:094 hours, 41 minutes, 9 secondsSo I just I just create um so just create not found
4:41:174 hours, 41 minutes, 17 secondsand then I'm going to give this um index tx and just place this here not found page.
4:41:254 hours, 41 minutes, 25 secondsSo now we have the pages. We can create two more folder. Now we can create the route folder and we need to create the layout folder.
4:41:384 hours, 41 minutes, 38 secondsSo inside the layout I'm going to create base sorry let me create a file inside the layout folder it's going to call base
4:41:464 hours, 41 minutes, 46 secondslayout cxx. So this is going to use for the um public route. So I'm just going to say a
4:41:554 hours, 41 minutes, 55 secondsf I'll say base layout and I'm going to remove this and then we
4:42:044 hours, 42 minutes, 4 secondscan give this a class name. So let's give it a class name height full
4:42:114 hours, 42 minutes, 11 secondsminimum height zero and um so I'm going to add in width full
4:42:184 hours, 42 minutes, 18 secondsand let's give a flex flex column and I'm going to add um okay let me not add anything here. So I'm going to give this a div here.
4:42:304 hours, 42 minutes, 30 secondsGive this a first name and we're going to say flex and I'm going to say flex sorry item
4:42:384 hours, 42 minutes, 38 secondscenter justify between. So let me remove this.
4:42:454 hours, 42 minutes, 45 secondsI don't think I need this flex here.
4:42:524 hours, 42 minutes, 52 secondsSo here we have justify center. So we justify between and I'm going to also add width for this
4:42:594 hours, 42 minutes, 59 secondstwo. So let me add width height full and then
4:43:084 hours, 43 minutes, 8 secondsuh let me add overflow or let me leave overflow and then we're going to have a div here and then we're going to import
4:43:154 hours, 43 minutes, 15 secondsoutlet from react router do
4:43:224 hours, 43 minutes, 22 secondsI just give this to a class name and there's a maximum
4:43:314 hours, 43 minutes, 31 secondsright full and then with photo.
4:43:394 hours, 43 minutes, 39 secondsSo something like this. Now let's go into let's create a um let's create app layout
4:43:484 hours, 43 minutes, 48 secondscxx app layout.
4:43:574 hours, 43 minutes, 57 secondsSo I remove this and then we need to import a sidebar. So sidebar
4:44:054 hours, 44 minutes, 5 secondsside um bar from chant UI sidebar provider.
4:44:124 hours, 44 minutes, 12 secondsSo I'm going to increase the size of the sidebar. So I'm going to add it here this. So I'm going to just add this. Let
4:44:204 hours, 44 minutes, 20 secondsme just add it sty. So, I'm just going to
4:44:304 hours, 44 minutes, 30 secondsSo, why is this like this? So, I think should be here.
4:44:404 hours, 44 minutes, 40 secondsSo, here we're going to have the app side the app side bar. So, we're going
4:44:484 hours, 44 minutes, 48 secondsto create a component later on, but let's import um sidebar insert.
4:44:584 hours, 44 minutes, 58 secondsSo, I'll give this a class name heightful.
4:45:024 hours, 45 minutes, 2 secondsAnd then we're going to say overflow um overflow hidden bg background and text foreground.
4:45:144 hours, 45 minutes, 14 secondsAnd let's import outlet. So let's create the uh component source.
4:45:224 hours, 45 minutes, 22 secondsSo I just copy app sidebar and let's go into the components. So I'm going to create a folder as a sidebar
4:45:304 hours, 45 minutes, 30 secondsand then I'm going to index cx and then we can see
4:45:364 hours, 45 minutes, 36 secondsI'll just call it app side bar and then we can import sidebar
4:45:454 hours, 45 minutes, 45 secondsfrom um UI UI. So, let me update this.
4:45:514 hours, 45 minutes, 51 secondsAnd then we're going to add set this to collapsible icon.
4:45:584 hours, 45 minutes, 58 secondsAnd then I'm going to give this a class name border, right? Um, border
4:46:074 hours, 46 minutes, 7 secondsside bar border. Let's give this a header. Say sidebar.
4:46:164 hours, 46 minutes, 16 secondsum side by header I give a class name
4:46:224 hours, 46 minutes, 22 secondsand I'm going to say wing bottom to next. So there's no need for
4:46:304 hours, 46 minutes, 30 secondsthe flex. I'll just use justify or let me just add it.
4:46:434 hours, 46 minutes, 43 secondsAnd then I'm going to give this um padding. So I say padding Y3 and I'm going to say padding uh sorry padding top three padding bottom zero.
4:46:554 hours, 46 minutes, 55 secondsAnd then I'm going to say padding left three.
4:46:584 hours, 46 minutes, 58 secondsAnd then we're going to create a logo component.
4:47:034 hours, 47 minutes, 3 secondsAnd then I'm going to also import a sidebar trigger.
4:47:114 hours, 47 minutes, 11 secondsSo let's go ahead and create the component. So I'll just create the logo component here. So I just logo tx
4:47:204 hours, 47 minutes, 20 secondsand I'm going to paste it. So I'm pasting the logo. So we just have it.
4:47:244 hours, 47 minutes, 24 secondsI'm passing class name and show text. So you can copy it too from the GitHub. So let's go into sidebar and let's import this.
4:47:354 hours, 47 minutes, 35 secondsSo I'm going to also import constant state.
4:47:414 hours, 47 minutes, 41 secondsI'll import this from use use sidebar.
4:47:474 hours, 47 minutes, 47 secondsThen I'm going to say show show text if state
4:47:554 hours, 47 minutes, 55 secondsis equals to expanded like this. And then I'm going to set class name.
4:48:044 hours, 48 minutes, 4 secondsI'll set this to hidden large flex.
4:48:104 hours, 48 minutes, 10 secondsI'm going to do margin minus margin two and MB0.
4:48:154 hours, 48 minutes, 15 secondsSo let's import sidebar contents.
4:48:224 hours, 48 minutes, 22 secondsSo let me give this a class name.
4:48:254 hours, 48 minutes, 25 secondsLet's grab zero padding X0 and P button three. And then I'm going to create a
4:48:334 hours, 48 minutes, 33 secondscomponent here. So this is going to be the navs call items.
4:48:404 hours, 48 minutes, 40 secondsAnd then sorry I'm going to just close this. And then let's go ahead and create these two. So get nav
4:48:494 hours, 48 minutes, 49 secondsitems tx n items.
4:48:594 hours, 48 minutes, 59 secondsAnd I'll save this. Go here. And I'm going to import it.
4:49:074 hours, 49 minutes, 7 secondsSo let's create the nav. this uh the nav item. So before we create the nav items, let's quickly create the routes first.
4:49:144 hours, 49 minutes, 14 secondsSo let me fix this error. Let me import this and then let's go let me collapse all of this.
4:49:234 hours, 49 minutes, 23 secondsAnd now we can go into the route and let's create index x here. So I'm going to create route
4:49:314 hours, 49 minutes, 31 secondsagain.x and this is going to have we're going to create a route. So we're going to have
4:49:394 hours, 49 minutes, 39 secondsthe out single and sign in sign up. Then new is going to be the home route. When the user login to new and then we have
4:49:484 hours, 49 minutes, 48 secondssingle session session id now we're going to have to export constant hot rout.
4:50:014 hours, 50 minutes, 1 secondI'm going to pass this here. So I'm going to import the pages the sign in page. Okay, let's import the signup page.
4:50:114 hours, 50 minutes, 11 secondsLet me import the homepage. Let me import section page.
4:50:204 hours, 50 minutes, 20 secondsSo now the next thing we're going to create is inside the index here. So I'm going to import real. So import all of
4:50:284 hours, 50 minutes, 28 secondsthis from D. I'm going to say constant root layout
4:50:374 hours, 50 minutes, 37 secondsis equals to I'm going to return
4:50:444 hours, 50 minutes, 44 secondsthen I'm going to say scroll restoration and then I'm going to import outlet here
4:50:534 hours, 50 minutes, 53 secondsand then I'm going to say export constant browser is equals to create
4:51:014 hours, 51 minutes, 1 secondcreate browser router and then we're going to say create route
4:51:094 hours, 51 minutes, 9 secondselement and then we say route element
4:51:174 hours, 51 minutes, 17 secondsand I'm going to just pass in the book layout here and now we're going to have a route
4:51:244 hours, 51 minutes, 24 secondsagain and I'm going to pass in elements here
4:51:334 hours, 51 minutes, 33 secondsand later on we're going to create a component. So I'm just going to do this going to have we're going to add in the route guard component but for now I'm
4:51:414 hours, 51 minutes, 41 secondsjust going to leave it now and let's create a route for the base as a route.
4:51:584 hours, 51 minutes, 58 secondsSo rout and this is going to have elements
4:52:044 hours, 52 minutes, 4 secondsand I'm going to import base layout
4:52:114 hours, 52 minutes, 11 secondssorry base layout and then we're going to look through the
4:52:184 hours, 52 minutes, 18 secondsout route route part
4:52:264 hours, 52 minutes, 26 secondsmap and we're going to get the path and the element
4:52:384 hours, 52 minutes, 38 secondsand then I'm just going to return this and then we can have route
4:52:484 hours, 52 minutes, 48 secondsand there we're going to pass in the key which is part and then part is going to be
4:52:574 hours, 52 minutes, 57 secondsAnd the element is going to be elements here.
4:53:064 hours, 53 minutes, 6 secondsSorry. Sorry. This should be a complaint.
4:53:174 hours, 53 minutes, 17 secondsSo we're going to do the same thing for the protected route. So let me paste it here.
4:53:234 hours, 53 minutes, 23 secondsSo instead of I'll do app layout and I'll change this to protected route
4:53:364 hours, 53 minutes, 36 secondsand then after outside this this I'm going to add route.
4:53:474 hours, 53 minutes, 47 secondsUm let me close this. So, I made a mistake.
4:53:534 hours, 53 minutes, 53 secondsI should have moved this out here. I'll move this here.
4:53:584 hours, 53 minutes, 58 secondsAnd I'm going to copy this again. I'm going to paste it here.
4:54:044 hours, 54 minutes, 4 secondsAnd I'm going to move this protected route with the layout up here. So, let me format this like this. So we're going
4:54:124 hours, 54 minutes, 12 secondsto say part asteric and element is going to be not found from.
4:54:314 hours, 54 minutes, 31 secondsSo we're going to save this. So let's go and create the route card. So route card here.
4:54:454 hours, 54 minutes, 45 secondstxx.
4:54:494 hours, 54 minutes, 49 secondsa constant route guard
4:54:584 hours, 54 minutes, 58 secondsuh this is going to be equals to so I'm going to pass in type and I'm
4:55:064 hours, 55 minutes, 6 secondsgoing to pass it here and there for now we're just going to
4:55:124 hours, 55 minutes, 12 secondslet's say location constant location
4:55:194 hours, 55 minutes, 19 secondsis equals to use location from auto and since we don't have we've
4:55:274 hours, 55 minutes, 27 secondsnot yet implemented the endpoint to get the user I'll just say constant is loading
4:55:344 hours, 55 minutes, 34 secondsto false and then I'm going to say if
4:55:404 hours, 55 minutes, 40 secondsif required um required sorry let me get it Okay,
4:55:494 hours, 55 minutes, 49 secondsrequired and I'm going to say constant
4:55:594 hours, 55 minutes, 59 secondsis equals to false and I'm going to say um and not is
4:56:114 hours, 56 minutes, 11 secondsthen we can return sorry some
4:56:194 hours, 56 minutes, 19 secondsnavigate import it I'll say two
4:56:284 hours, 56 minutes, 28 secondsand this is going to be also sign in and just say replace
4:56:374 hours, 56 minutes, 37 secondsand I can set state from application
4:56:484 hours, 56 minutes, 48 secondsand I can copy this and I'm just going to say if not
4:56:564 hours, 56 minutes, 56 secondsrequired and there's al then we're going to change this to protected
4:57:044 hours, 57 minutes, 4 secondsbrowse new sorry new then I'm going to remove this and then I just going to outlet here.
4:57:184 hours, 57 minutes, 18 secondsLet me import it.
4:57:264 hours, 57 minutes, 26 secondsSorry, let me move this out.
4:57:314 hours, 57 minutes, 31 secondsSo now we have this. Now we can export this. I say export
4:57:394 hours, 57 minutes, 39 secondsexport default route card.
4:57:474 hours, 57 minutes, 47 secondsSo let's use it inside index and I can just import it here and just say route guard.
4:57:564 hours, 57 minutes, 56 secondsI'm going to say required boss.
4:58:024 hours, 58 minutes, 2 secondsWhy I'm just going to set required sorry
4:58:104 hours, 58 minutes, 10 secondsroute card required true.
4:58:194 hours, 58 minutes, 19 secondsSo now we're going to copy this and let's go into the app.tx.
4:58:244 hours, 58 minutes, 24 secondsNow let's replace this with it with this. Sorry, let me replace this properly
4:58:324 hours, 58 minutes, 32 secondsand let's import the uh router provider and then import the route.
4:58:414 hours, 58 minutes, 41 secondsSo we have this. Now we can go ahead and implement the sidebar. So I'll go to sidebar nav items. So I'm just going to come over here.
4:58:514 hours, 58 minutes, 51 secondsI'm just going to add this here. So, let me import this icon. Import protected route.
4:58:594 hours, 58 minutes, 59 secondsAnd then we're going to import sidebar group.
4:59:084 hours, 59 minutes, 8 secondsAnd let me update this side by group.
4:59:114 hours, 59 minutes, 11 secondsAnd I'm just going to give this a class name PX2.
4:59:164 hours, 59 minutes, 16 secondsAnd then P top two. And let's import side group. Sidebar group content.
4:59:274 hours, 59 minutes, 27 secondsLet's do sidebar.
4:59:294 hours, 59 minutes, 29 secondsSidebar menu.
4:59:354 hours, 59 minutes, 35 secondsSo I'll give this a class name space Y 1.5.
4:59:424 hours, 59 minutes, 42 secondsAnd then we can map 3D nav item.
4:59:464 hours, 59 minutes, 46 secondsThen I say map item
4:59:534 hours, 59 minutes, 53 secondsum item side by menu button. So menu item.
5:00:075 hours, 7 secondsSo we're going to pass in a key. I'll say um item dot title.
5:00:145 hours, 14 secondsAnd now we can import sidebar menu button
5:00:265 hours, 26 secondsand I can just say to tip um item title and I'll set this to try
5:00:355 hours, 35 secondsand let's import link from react router ding to this going to be item dot ref.
5:00:465 hours, 46 secondsLet's import um item do icon
5:00:565 hours, 56 secondsand as a span tag import span tag and we're going to say item title here.
5:01:055 hours, 1 minute, 5 secondsSo below we're going to have another menu item. So I'll paste this here. This is just for search
5:01:125 hours, 1 minute, 12 secondsand I think that is all. So for the group I can just add in sidebar
5:01:195 hours, 1 minute, 19 secondsuh sidebar uh separator
5:01:265 hours, 1 minute, 26 secondsand I'll just give this a class name M12 and we're done. So let's go ahead and
5:01:355 hours, 1 minute, 35 secondstest it out. So, make sure the server is running.
5:01:445 hours, 1 minute, 44 secondsMake sure we've imported this inside the layout app layout.
5:01:515 hours, 1 minute, 51 secondsSo, I will go to the browser now and we can see the sign in page and if I
5:01:585 hours, 1 minute, 58 secondsgo to SL sign up, we should see sign up now. If I go to slash new.
5:02:095 hours, 2 minutes, 9 secondsSo, it's taking me to the signin page.
5:02:115 hours, 2 minutes, 11 secondsSo, I can go back to the code and just set this to let me set this to true.
5:02:205 hours, 2 minutes, 20 secondsAnd I can go back to the code to the browser.
5:02:265 hours, 2 minutes, 26 secondsAnd let me reload this. Now, we can see we can see this now. So I need to make
5:02:325 hours, 2 minutes, 32 secondsthis um row so we can see the new and the search. So we going to go ahead to
5:02:405 hours, 2 minutes, 40 secondsfetch all the sessions here. In this chapter we're going to start working on the I'm going to first of all install DQ
Chapter 11: Frontend Auth Page
5:02:485 hours, 2 minutes, 48 secondsquery. So I open my terminal cancel my server. I do mpm install query. So once it install I'm going to
5:02:575 hours, 2 minutes, 57 secondsshow you the version. While this is installing, let's create our env.
5:03:045 hours, 3 minutes, 4 secondsAnd let's say base API URL. And this is going to be http
5:03:145 hours, 3 minutes, 14 seconds/ localhost localhost 8,000 / ai slash.
5:03:235 hours, 3 minutes, 23 secondsSo like this. So let me check the packet now. And we can see 5.14.
5:03:335 hours, 3 minutes, 33 secondsSo let's create let's create um so let's come into um component and
5:03:425 hours, 3 minutes, 42 secondslet's say query provider provider tx
5:03:495 hours, 3 minutes, 49 secondsand I'm there's not even need for me to create this file. So I'm going to remove this file and I'm going to just do it inside the main.tx.
5:03:585 hours, 3 minutes, 58 secondsSo I'm just going to say constant query client
5:04:055 hours, 4 minutes, 5 secondsis equals to new query query client
5:04:165 hours, 4 minutes, 16 secondsand let me import query client.
5:04:205 hours, 4 minutes, 20 secondsSo let me import it from tack query at the top here. I say import
5:04:285 hours, 4 minutes, 28 secondsand I say from tack query and I'm going to copy this
5:04:365 hours, 4 minutes, 36 secondspaste it here and then I'm going to wrap this. Let me wrap this from here as a query client provider.
5:04:495 hours, 4 minutes, 49 secondsAnd I'm going to move all of this
5:05:045 hours, 5 minutes, 4 secondsand then I'm going to pass in client client.
5:05:125 hours, 5 minutes, 12 secondsSo we have this. So let's install asus.
5:05:225 hours, 5 minutes, 22 secondsSo let's wait for it. While this is installing, let's go into leave and let's create a file. So I'll say as
5:05:315 hours, 5 minutes, 31 secondsclient cx.
5:05:355 hours, 5 minutes, 35 secondsThen I'm going to create a file. I'll call it envx.
5:05:425 hours, 5 minutes, 42 secondsAnd I'm just going to say export export constant
5:05:495 hours, 5 minutes, 49 secondsbase API URL is going to be equals to import
5:06:005 hours, 6 minutesmeta and then we're going to say envit um base API URL. So make sure you update
5:06:075 hours, 6 minutes, 7 secondsthis to API URL. And now we can go into the asio client and then I'm going to paste this here. So the first thing I do
5:06:155 hours, 6 minutes, 15 secondsis going to import as then we import the API base. We have this custom type here
5:06:215 hours, 6 minutes, 21 secondsand then we have the base with credentials. So since the back end we using cookie so we need to add this.
5:06:295 hours, 6 minutes, 29 secondsThen we create as we add interceptor response and then if there's any if it's unauorized status for one then we to
5:06:395 hours, 6 minutes, 39 secondsstart and then we have this error and then we we export default API. So now we have this now we can create
5:06:485 hours, 6 minutes, 48 secondsapi.tx and I'm going to create a folder here.
5:06:545 hours, 6 minutes, 54 secondsI'll say types and then we can create the API for login. So we're going to say export
5:07:025 hours, 7 minutes, 2 secondsconstant login modation
5:07:085 hours, 7 minutes, 8 secondsf is going to be equals to async
5:07:145 hours, 7 minutes, 14 secondsand then data I need to write the type. So let's go
5:07:205 hours, 7 minutes, 20 secondsand create the type. So I'll say type dot sorry O type dot typex and I'm going to paste in all the type.
5:07:325 hours, 7 minutes, 32 secondsSo in the all user we're going to later go ahead and return connected. So I've added it here. So inside the API we're
5:07:415 hours, 7 minutes, 41 secondsgoing to pass in login type and I'm going to also say promise
5:07:525 hours, 7 minutes, 52 secondswe can say al response.
5:08:015 hours, 8 minutes, 1 secondSo I say constant response
5:08:085 hours, 8 minutes, 8 secondsis equals to wait. So let's import API from client. I'll say post
5:08:175 hours, 8 minutes, 17 secondsand then we can just set the type to response
5:08:245 hours, 8 minutes, 24 secondsand res/ login and then we can pass in the data
5:08:325 hours, 8 minutes, 32 secondsand then we can return response data.
5:08:385 hours, 8 minutes, 38 secondsSo the reason why we adding slash at the front. So in the env you can see I have API and the forward slash.
5:08:475 hours, 8 minutes, 47 secondsSo we have the login now. So let's let's write the um the sign up. Then we can go ahead and work on the pages. So for the
5:08:555 hours, 8 minutes, 55 secondsregister I'm just going to pass it here and I'm going to import register.
5:09:005 hours, 9 minutesSo I have this. Now let's go ahead and work on the UI. So in the pages al
5:09:075 hours, 9 minutes, 7 secondssignin page. So I'm going to um add the component here. So we're going to be using react hook form. I think we've
5:09:145 hours, 9 minutes, 14 secondsalready installed it. Um if you see okay I think it didn't add together with
5:09:215 hours, 9 minutes, 21 secondsum shantui. I think we also added um form here.
5:09:285 hours, 9 minutes, 28 secondsOkay. We didn't add form. So let's quickly add it.
5:09:335 hours, 9 minutes, 33 secondsSo, let me open my terminal and I'm going to say mpm uh in shanty add form.
5:09:455 hours, 9 minutes, 45 secondsOkay, sorry. Uh MPX and let me wait for this. So, I think
5:09:545 hours, 9 minutes, 54 secondsthere's no log form again in Shanti for some reason it's not added. So let me just install
5:10:005 hours, 10 minutesthis packet the react hook for and I'm going to also inform resolver and so I'm
5:10:075 hours, 10 minutes, 7 secondsgoing to click on enter and let me install one after the other
5:10:195 hours, 10 minutes, 19 secondsset install. So let me try and install her phone.
5:10:285 hours, 10 minutes, 28 secondsOkay, maybe doesn't exist. So let me check um we had to form
5:10:375 hours, 10 minutes, 37 secondssay added there. Sorry guys, I'm making a mistake. I should have removed this all there.
5:10:475 hours, 10 minutes, 47 secondsSo let's wait for it to install. Okay, now it has installed. Now I'll just go close this and I'm going to create the
5:10:545 hours, 10 minutes, 54 secondscomponents. Sorry, the signin page. So I'm going to quickly paste it.
5:11:025 hours, 11 minutes, 2 secondsSo it's very So I've import all of the package all of the um packages we need like the um use
5:11:095 hours, 11 minutes, 9 secondsform from um buttons and then the login mutation. You can see the login mutation is here.
5:11:165 hours, 11 minutes, 16 secondsThen we have validator. Then we import and use navigate
5:11:235 hours, 11 minutes, 23 secondsquery client. Then use motation. We pass in the login mutation function. Then if
5:11:305 hours, 11 minutes, 30 secondson success we just um we navigate the user to this route. So we're going to let that create the endpoint for the current user.
5:11:395 hours, 11 minutes, 39 secondsThen there's any error we throw an error. So we have the use form hook resolver Z resolver which we're
5:11:475 hours, 11 minutes, 47 secondsgetting from the hook form um resolvers and then we have the default follow email and password and we have register
5:11:565 hours, 11 minutes, 56 secondsum handle submit and then the form state to get the errors we have the unsubmit here so we're importing the logo and
5:12:045 hours, 12 minutes, 4 secondsthen this is the form here we can see the form so we attach the um handle submit and then our phone on submit
5:12:135 hours, 12 minutes, 13 secondshere. Then we have the H1, the P tag and this is where we have the email, the impute and the password. So the email
5:12:235 hours, 12 minutes, 23 secondsinput and the password input and then we have the sign in. So if um login notation
5:12:315 hours, 12 minutes, 31 secondspending then we should sign in signing in and then we should sign in here then this is it. So we can do the same thing
5:12:395 hours, 12 minutes, 39 secondsfor sign up. So I'm going to come over here and I'm going to add this and
5:12:465 hours, 12 minutes, 46 secondsthere's this for the sign up just add an email and password and the employ register notation function. So now this
5:12:545 hours, 12 minutes, 54 secondsis it. So we need to create a hook for the current user. So I will go into this
5:13:015 hours, 13 minutes, 1 secondhook. I will say use use user.tx.
5:13:085 hours, 13 minutes, 8 secondsSo before we work on let's go into the le folder API and let's write API for the current user. I'm going to add it
5:13:165 hours, 13 minutes, 16 secondshere and then we can go into can see all me and we can go into the
5:13:245 hours, 13 minutes, 24 secondsuse hook use user hook and I'm going to add it here. So we import use query from
5:13:305 hours, 13 minutes, 30 secondsthat query. We get get current user from lib API and then we return use query and
5:13:385 hours, 13 minutes, 38 secondsyou can see the query key current user and query function get current user.
5:13:445 hours, 13 minutes, 44 secondsThen we're going to save this. Now we can use this hook inside the route guard. So we can go into the route guard
5:13:545 hours, 13 minutes, 54 secondsand then instead of this loading and all we just remove this and I'm going to say I'll just say
5:14:025 hours, 14 minutes, 2 secondsconstant is equals to use user
5:14:125 hours, 14 minutes, 12 secondsand we can get data is loading
5:14:185 hours, 14 minutes, 18 secondsand then I'll just say if it's loading
5:14:255 hours, 14 minutes, 25 secondsthen I'm going to show I'm going to return a div here
5:14:325 hours, 14 minutes, 32 secondsand then I'm going to just type like this
5:14:425 hours, 14 minutes, 42 secondsand then we going to import the logo and then the spinner. So import that. Now we
5:14:495 hours, 14 minutes, 49 secondshave the data can just say boolean sorry boolean
5:14:575 hours, 14 minutes, 57 secondssay data dot user.
5:15:045 hours, 15 minutes, 4 secondsSo if um the user exist then we're going to navigate user to the protected new but if not just going to redirect user
5:15:125 hours, 15 minutes, 12 secondsto the sign in page. So now we are done with the let's check this error. So let me before we run the server, let's go to
5:15:215 hours, 15 minutes, 21 secondslet's fix this. So I'm going to go into um let's go into the folder and then inside the as client make sure you
5:15:295 hours, 15 minutes, 29 secondscomment this out. You comment this um detail to unauorize and then inside the hook I'm just going to make sure we add
5:15:375 hours, 15 minutes, 37 secondsa state time to this end point to the um use query hook for current user and once you do that we can then run the server.
5:15:465 hours, 15 minutes, 46 secondsSo I think I've run the server already.
5:15:495 hours, 15 minutes, 49 secondsSo let me go to the browser now. And if I go to browser, we can see this app. I can click here to sign up. I can give
5:15:575 hours, 15 minutes, 57 secondsthis a name. I'll just say um tech with Emma.
5:16:045 hours, 16 minutes, 4 secondsI'll just give it an email. Tech withgmail.com.
5:16:155 hours, 16 minutes, 15 secondsAnd I'm going to just give this a password.
5:16:205 hours, 16 minutes, 20 secondsAnd I'm going to click on create password. So before I click on create password, let me open the def.
5:16:275 hours, 16 minutes, 27 secondsAnd let me go to U network tab.
5:16:365 hours, 16 minutes, 36 secondsAnd I'm going to click on create account.
5:16:405 hours, 16 minutes, 40 secondsAnd let's see. So now we can see that we've created the account here.
5:16:475 hours, 16 minutes, 47 secondsSo if I go to payload and preview, we can see the response. So now we we are
5:16:545 hours, 16 minutes, 54 secondson the protected route page. So let's go ahead and implement the endpoint to fetch all session. In this chapter,
5:17:025 hours, 17 minutes, 2 secondswe're going to work on fetching all sessions. So let's go into the typex and let's create session
Chapter 12: Frontend Session List & Pull Request
5:17:105 hours, 17 minutes, 10 secondstypex and I'm going to just paste this here.
5:17:165 hours, 17 minutes, 16 secondsSo we need to install AI. So let's um install AI. So I'm going to back let's
5:17:235 hours, 17 minutes, 23 secondssee the version I used here 6.0.5 and then let me quickly install it too.
5:17:295 hours, 17 minutes, 29 secondsSo I'm going to say mpm install AI at 6.0.5
5:17:365 hours, 17 minutes, 36 secondsand click on this and this it should install and we're going to install AIDK.
5:17:425 hours, 17 minutes, 42 secondsSo just paste it here ak react for react and then this is going to install. Now
5:17:495 hours, 17 minutes, 49 secondsonce it's installed, we can then go into the L folder inside the um
5:17:585 hours, 17 minutes, 58 secondsinside the API. TX and then we can create the endpoint here. So I paste it here and I'm going
5:18:055 hours, 18 minutes, 5 secondsto import this. So once we have this get user sessions and we just use / session/all.
5:18:155 hours, 18 minutes, 15 secondsI'm going to save this and let's go into the sidebar. So inside component sidebar index.
5:18:245 hours, 18 minutes, 24 secondsSo I'm going I'm going to say um a state is equals to expanded. Then
5:18:335 hours, 18 minutes, 33 secondsI'm going to I'm going to create a component. I'll call this chart sessions.
5:18:425 hours, 18 minutes, 42 secondsSo let's go ahead and create a component. So I'll just do it here.
5:18:485 hours, 18 minutes, 48 secondsas a chat sessions tx chat session.
5:19:015 hours, 19 minutes, 1 secondSo let me go ahead and import it and then let's go into the chat session.
5:19:105 hours, 19 minutes, 10 secondsSo I'm going to first import use query from t query and let's also import use
5:19:195 hours, 19 minutes, 19 secondslocation from and then the get user session from API.
5:19:265 hours, 19 minutes, 26 secondsSo now we have this. So I'll just do constants items is going to be equals to data do
5:19:345 hours, 19 minutes, 34 secondssessions do sessions and then I'm just going to map this.
5:19:445 hours, 19 minutes, 44 secondsSo what I'm going to I'm going to say sessions or we can just I wanted to structure the
5:19:515 hours, 19 minutes, 51 secondsdata in a way we loop through it with the side side group. So there's no need.
5:19:555 hours, 19 minutes, 55 secondsI'll just do it here. So let's just import sidebar group.
5:20:025 hours, 20 minutes, 2 secondsSorry, sidebar group. So let's pass this here.
5:20:105 hours, 20 minutes, 10 secondsAnd I'm going to import sidebar sidebar group um label.
5:20:165 hours, 20 minutes, 16 secondsAnd I can give this a class name as a px2 text as small. And I'm just going to say text muted forground.
5:20:305 hours, 20 minutes, 30 secondsAnd I'm going to say sessions.
5:20:345 hours, 20 minutes, 34 secondsAnd then we can import sidebar group content.
5:20:415 hours, 20 minutes, 41 secondsGroup content.
5:20:455 hours, 20 minutes, 45 secondsAnd then we can just say sorry if it's pending
5:20:535 hours, 20 minutes, 53 secondsthen let's import sidebar menu.
5:21:005 hours, 21 minutesI'll give a class name of gap um one and then I'm going to
5:21:095 hours, 21 minutes, 9 secondsarray dot from length let's say six and we're going to map
5:21:175 hours, 21 minutes, 17 secondsthis I'll set it to underscore index
5:21:265 hours, 21 minutes, 26 secondsand then we're going to import u so I'm Just going to do side
5:21:325 hours, 21 minutes, 32 secondsside side uh sorry sidebar menu item first
5:21:415 hours, 21 minutes, 41 secondsand let's import skeleton sorry I'll say side
5:21:525 hours, 21 minutes, 52 secondsbar side menu skeleton I'll say
5:22:005 hours, 22 minutesicon and let me add a key here index.
5:22:115 hours, 22 minutes, 11 secondsSo I'm just going to do else.
5:22:165 hours, 22 minutes, 16 secondsSo let's loop through this. So I'm going to come back up here. I say constant items is equals to data. So let's do con
5:22:265 hours, 22 minutes, 26 secondssessions is equals to d sessions
5:22:345 hours, 22 minutes, 34 secondsand then we can loop it through as a session map uh session.
5:22:565 hours, 22 minutes, 56 secondsSo let me remove this first.
5:22:595 hours, 22 minutes, 59 secondsSo I'm going to do session umlength is equals to zero.
5:23:075 hours, 23 minutes, 7 secondsI'll just have a div here.
5:23:125 hours, 23 minutes, 12 secondsno session yet. And then I'm going to paste this now.
5:23:205 hours, 23 minutes, 20 secondsSo, we're going to um get this sidebar menu. So, let me copy the sidebar menu.
5:23:305 hours, 23 minutes, 30 secondsLet me paste it there.
5:23:325 hours, 23 minutes, 32 secondsLet me move this uh session loop up. And then I'm going to wrap this
5:23:425 hours, 23 minutes, 42 secondsSo let's import a sidebar menu item.
5:23:495 hours, 23 minutes, 49 secondsI'll paste it here. And here I'm going to set this session do ID ID.
5:24:015 hours, 24 minutes, 1 secondSo let's import sidebar group um menu button
5:24:115 hours, 24 minutes, 11 secondssorry sidebar menu button.
5:24:195 hours, 24 minutes, 19 secondsSo I'm going to import link from outer do
5:24:285 hours, 24 minutes, 28 secondsand then I'm going to set this to as child and let's give this
5:24:395 hours, 24 minutes, 39 secondsso this is going to be set session slash
5:24:495 hours, 24 minutes, 49 secondssession log id.
5:24:555 hours, 24 minutes, 55 secondsThen we're going to I'm going to add this here. So have a div and we're going to have the title session title and
5:25:045 hours, 25 minutes, 4 secondsbelow we're going to have um the session repo name. So I'm going to also add a class here.
5:25:145 hours, 25 minutes, 14 secondsSo before I add let me add is active session. Oh sorry we can use the part
5:25:235 hours, 25 minutes, 23 secondsname here. So what I'm going to I'm just going to cut this out and I'm going to return
5:25:325 hours, 25 minutes, 32 secondslike this. So I can just do constant is addive
5:25:405 hours, 25 minutes, 40 secondsis equals part name dot name is equals to/ session/ session sub ID and then I
5:25:485 hours, 25 minutes, 48 secondscan just put as um active here and then I'm going to add in a class. So let me
5:25:555 hours, 25 minutes, 55 secondsadd it here. So paste it here. So I'm going to import
5:26:035 hours, 26 minutes, 3 secondsand I'll say if it's active like this.
5:26:105 hours, 26 minutes, 10 secondsSo I think we are fine. Then let's add in a class for this class name.
5:26:265 hours, 26 minutes, 26 secondsSo we done with this now.
5:26:295 hours, 26 minutes, 29 secondsI can go and we can go ahead and check it out. So, let's make sure our server is running. So, let me m run def.
5:26:405 hours, 26 minutes, 40 secondsSo, let's go to the browser.
5:26:445 hours, 26 minutes, 44 secondsGo to the browser and let's wait for this. We should see sessions here and it's saying no session.
5:26:555 hours, 26 minutes, 55 secondsSo, let's confirm this. I think I created I created I created I tested the endpoints before. So let me go to the
5:27:025 hours, 27 minutes, 2 secondsback end. Let me quickly um let me open this. Let me check my MongoDB DB.
5:27:205 hours, 27 minutes, 20 secondsSo I've opened this. Now you can see we have one session.
5:27:295 hours, 27 minutes, 29 secondsSo we can see we have one session. So let me check this again. Let's go back to the front side.
5:27:385 hours, 27 minutes, 38 secondsAnd let me reload this.
5:27:415 hours, 27 minutes, 41 secondsLet me check the end point first. So I'm going to open the dev tool now. And let me reload this.
5:27:525 hours, 27 minutes, 52 secondsSo I think This is coming from the okay from the pagation. So let's go back
5:28:015 hours, 28 minutes, 1 secondto the code and I'll go back here and let me go to where I have uh let me go
5:28:095 hours, 28 minutes, 9 secondsto the front first the chat session and let me go to session.
5:28:175 hours, 28 minutes, 17 secondsOkay, I think I didn't pass any page nation here.
5:28:225 hours, 28 minutes, 22 secondsSo I'm going to go to the back end now and I'm going to go to controller
5:28:295 hours, 28 minutes, 29 secondsuh session controller sorry validator session validator
5:28:355 hours, 28 minutes, 35 secondsand I think I set this to one. So let me go to the service first and then session service. So let me scroll to the top.
5:28:455 hours, 28 minutes, 45 secondsLet me collapse this. Let me go this.
5:28:565 hours, 28 minutes, 56 secondsSo I think yeah this is pation page number minus one pion size.
5:29:045 hours, 29 minutes, 4 secondsSo I'm the one that made a mistake. I I use a different account. So if you go to let's go to https.
5:29:125 hours, 29 minutes, 12 secondsIf I go to session so I'm using uh sorry I'm using this account. This was the
5:29:195 hours, 29 minutes, 19 secondsaccount I used to create the session but I was I logged in with a different account. I signed up with a different account. So that was the problem. So
5:29:285 hours, 29 minutes, 28 secondsthat's why on the client side um I go to the client you can see that we don't have any uh
5:29:365 hours, 29 minutes, 36 secondsdata. So this is working and I have to log in with the mother account. So I'm going to log and check it out. I've lo
5:29:455 hours, 29 minutes, 45 secondswith the account and I can see the sessions here. So, let me go back and check why it's not showing up. So, I'll
5:29:525 hours, 29 minutes, 52 secondsgo uh let's go back to the code and I'll go straight to the front the side chat
5:30:005 hours, 30 minutessection and we have data session. So, let me console log of this. Okay, I need to remove this.
5:30:115 hours, 30 minutes, 11 secondsLet me cons.
5:30:245 hours, 30 minutes, 24 secondsSo let me go back to the client side and let me check the console up.
5:30:335 hours, 30 minutes, 33 secondsSo this is empty. Let me this.
5:30:395 hours, 30 minutes, 39 secondsThis is showing empty.
5:30:455 hours, 30 minutes, 45 secondsSo I have to console log the data and I can see the data show in the response here. So the problem is coming from the
5:30:525 hours, 30 minutes, 52 secondsway I send this data. So what I'm going to do I'm just going to go back to the client side. So we can just do data data
5:31:015 hours, 31 minutes, 1 secondhere. you can do data dot sorry dot um data
5:31:095 hours, 31 minutes, 9 secondsor it's going to show an error. So what I will do I just go to the um client side session sorry the back end and
5:31:175 hours, 31 minutes, 17 secondsthere I can just return this data. So I'll just remove this
5:31:265 hours, 31 minutes, 26 secondsum I don't really want to remove the message. So let me try and go to
5:31:335 hours, 31 minutes, 33 secondsthe client sorry IPI NMC data.
5:31:405 hours, 31 minutes, 40 secondsSo this is going to throw an error. So I'll go to the response.
5:31:455 hours, 31 minutes, 45 secondsSo I'm going to just cut this out. I say data and I'll paste this here.
5:31:565 hours, 31 minutes, 56 secondsAnd let me see. So missing data in the response.
5:32:065 hours, 32 minutes, 6 secondsSo this is giving an error.
5:32:095 hours, 32 minutes, 9 secondsSo I think I fixed it. So what I'm going I'm just going to remove this data. Then inside the type insert session type
5:32:165 hours, 32 minutes, 16 secondsremove the data. Then I'll just go to the controller and I'm just going to destructure the data here. And this should work. So I'm going to save this.
5:32:265 hours, 32 minutes, 26 secondsI'll remove this now. Save this. And let's go back to the browser. And let's wait for this to load. Now we can see
5:32:345 hours, 32 minutes, 34 secondsthe session. We can see the session. So let's go ahead and then work on the chat interface. So in this chapter, we're
Chapter 13: Frontend Chat Interface
5:32:425 hours, 32 minutes, 42 secondsgoing to start working on the chart interface. So the chart interface, we're going to create a chat interface which is a single component which we're going
5:32:505 hours, 32 minutes, 50 secondsto use inside the homepage and the session the single session page. So I'm going to go into the home first. I'm going to go into index here. So, I'm
5:32:595 hours, 32 minutes, 59 secondsgoing to create um I'm going to just say chart interface
5:33:075 hours, 33 minutes, 7 secondsand I'm going to give this a class name first and I'll say widthful uh minimum height screen.
5:33:185 hours, 33 minutes, 18 secondsI'll give this overflow hidden.
5:33:235 hours, 33 minutes, 23 secondsAnd I think this is okay. So for the chat interface, I'm going to just create a component here. Let's go into
5:33:295 hours, 33 minutes, 29 secondscomponent. I'll just say chat and let's just do index
5:33:405 hours, 33 minutes, 40 secondstxx as a chart interface.
5:33:545 hours, 33 minutes, 54 secondsSo I remove this.
5:33:565 hours, 33 minutes, 56 secondsSo inside a chat inside a homepage. So since I'm going to be generating the log
5:34:035 hours, 34 minutes, 3 secondsID and I'm going to also have some state there. So I want to force this component
5:34:095 hours, 34 minutes, 9 secondsto always um amount um to amount when we click let's say the user click away from this from the chat interface that home
5:34:185 hours, 34 minutes, 18 secondsscreen or click on the logo to take them to the news the/ new. So you need to know that this chat component is going
5:34:265 hours, 34 minutes, 26 secondsto be responsible to show the um the empty state like the um homepage where
5:34:335 hours, 34 minutes, 33 secondsthere's no chat history. But once you send a message, you're going to then show the um chat history. So from the
5:34:435 hours, 34 minutes, 43 secondsuser side, the user is going to see think that we have navigated them to a different let's say the session/
5:34:505 hours, 34 minutes, 50 secondslog id page, but instead we are they are still on the homepage. We're just going to change the URL to / session/lo ID.
5:34:595 hours, 34 minutes, 59 secondsMeanwhile, they on the homepage so that we can be able to see they can instantly see the streaming from the AI. So what
5:35:075 hours, 35 minutes, 7 secondsI'm going to do I'm going to import location from use location.
5:35:185 hours, 35 minutes, 18 secondsSo I'm going to pass in key here. So let me import this component first.
5:35:245 hours, 35 minutes, 24 secondsSo I'm going to pass in key. I'm going to say location dot key. So why I'm adding this is
5:35:325 hours, 35 minutes, 32 secondsbecause we are going to be generating this log ID and we don't want a situation where the user click out of the let's say navigate to the um to the
5:35:405 hours, 35 minutes, 40 secondshome screen/ new page and the user is not seeing the history or the log ID
5:35:485 hours, 35 minutes, 48 secondschange then send a new message and the SLO ID of the previous chart is still showing is still on the state. So we
5:35:555 hours, 35 minutes, 55 secondsjust want it once user click away we add amount and everything reset. So once it set send a new message it's a brand new sl ID a brand new um view that we see.
5:36:075 hours, 36 minutes, 7 secondsSo I'm just going to do like this. And now let's go ahead and create this component. So we're going to chat inside the index.tx.
5:36:165 hours, 36 minutes, 16 secondsAnd so we're going to um have a props we're going to send. Like I said earlier, we're going to use this chart interface inside the single session page
5:36:245 hours, 36 minutes, 24 secondslike inside the session page. This is where we're going to fetch the um session by the SLO ID. And we need to pass in the initial messages and the
5:36:335 hours, 36 minutes, 33 secondssession title and the SLO ID with the repo URL and others. So that's why we're going to add them here. We're going to
5:36:415 hours, 36 minutes, 41 secondshave this um in the type, but we're going to make most of them optional. So I'm going to just paste this here.
5:36:495 hours, 36 minutes, 49 secondsSo I'm going to import this UI message from AI. So we're going to just get all
5:36:565 hours, 36 minutes, 56 secondsof this here. And then you can see that I have this a single session. This is going to allow us to know if the user is
5:37:025 hours, 37 minutes, 2 secondson a single session page or the user is on the um home screen. So that's why we have this here.
5:37:125 hours, 37 minutes, 12 secondsSo most of them are optional. So what we going to do now?
5:37:195 hours, 37 minutes, 19 secondsSo the first thing I'm going to do here I'm going to have a state. So this state is going to hold the repository the
5:37:265 hours, 37 minutes, 26 secondsrepo. So let's say repo set repo. So the user is going to select the repository URL. So I'm going to say
5:37:365 hours, 37 minutes, 36 secondsuse state and this is going to be what I'm going
5:37:435 hours, 37 minutes, 43 secondsto do. I'm going to have a type for this. So, let me set this here and I'm going to pass the type. So, I've pasting
5:37:515 hours, 37 minutes, 51 secondsthis type. So, we're going to have the value that is the repo the user select and then we're going to also have the default branch. Like I said, the back end does not know the default branch.
5:38:015 hours, 38 minutes, 1 secondSo, it's the client side is going to send the um default branch. So I'll just put selected repo here
5:38:095 hours, 38 minutes, 9 secondsand I'll say this to all and there I'm going to say if repo URL so which is going to be passed from the
5:38:185 hours, 38 minutes, 18 secondssingle session page. So if there's repo URL then I can just say value is repo
5:38:275 hours, 38 minutes, 27 secondsURL and then default branch is going to be default branch which is
5:38:335 hours, 38 minutes, 33 secondsgoing to be passed from the um which is going to be passed
5:38:415 hours, 38 minutes, 41 secondsfrom the single session page. So I don't know why this is showing error here. Okay. Sorry, I didn't pass this type.
5:38:505 hours, 38 minutes, 50 secondsSo, let me add it here.
5:38:555 hours, 38 minutes, 55 secondsStop. So, now then I'm going to say else no.
5:39:095 hours, 39 minutes, 9 secondsSo, let me just zoom in like this.
5:39:155 hours, 39 minutes, 15 secondsSo now we're going to have another state to hold the um session session title.
5:39:225 hours, 39 minutes, 22 secondsSo session title and this is going to be so we have set
5:39:305 hours, 39 minutes, 30 secondssession title on use string on and then we're going to pass in the prop if we
5:39:365 hours, 39 minutes, 36 secondshave else just show no here. Also for the branch name we going to have this the same thing. So I'm just going to copy this and paste it here.
5:39:465 hours, 39 minutes, 46 secondsSo I have this here. Now we're going to also have two states. Now one state is going to be for the track the P. So like
5:39:565 hours, 39 minutes, 56 secondsum remember I said once the AI make a to call it to a push get push to we are
5:40:045 hours, 40 minutes, 4 secondsgoing to send an event to the client side and we need to store that um we need to store the data from the event.
5:40:115 hours, 40 minutes, 11 secondsSo, we're going to have a state. I'm going to say um P ready. We can call it P ready. And if this have data, that
5:40:205 hours, 40 minutes, 20 secondsmeans we know that it's ready for P. But if there's no data, we know that the button we going to um have is going to
5:40:275 hours, 40 minutes, 27 secondsbe disabled. So, I'm going to say set P sorry P um ready.
5:40:405 hours, 40 minutes, 40 secondsAnd this is going to be use state and I'm going to set the type here.
5:40:485 hours, 40 minutes, 48 secondsSo I've past in the type. So we have this log ID tit to body and then branch.
5:40:545 hours, 40 minutes, 54 secondsSo if I scroll down. So I don't think we even need this branch here because we're going to fetch the branch from the back end. So I'm just going to leave it
5:41:025 hours, 41 minutes, 2 secondsthere. So I'm just going to add the type I say pull request
5:41:115 hours, 41 minutes, 11 secondsno and we're just going to set this to no.
5:41:165 hours, 41 minutes, 16 secondsThen once we create the pull request we need to return the created pull request URL. So user can click on it and then it
5:41:245 hours, 41 minutes, 24 secondstakes them to the repository. So I'm just going to have a state for it. Now we need a state which we're going to
5:41:305 hours, 41 minutes, 30 secondsgenerate. We're going to hold the SLO id. So I'm going to say constant sl
5:41:385 hours, 41 minutes, 38 secondsID and this is going to be equals to use state.
5:41:445 hours, 41 minutes, 44 secondsSo I'm going to call this I'm going to if we have the stock id which is passed here. So if the user is on the single
5:41:535 hours, 41 minutes, 53 secondspage that is a session stock ID. So the stock ID is going to be available and this is going to be passed here. But
5:42:005 hours, 42 minutessince if this is on the home screen the homepage and they send a message we know there will not be any sl ID pass. So we
5:42:075 hours, 42 minutes, 7 secondsneed to generate a sl ID. So we'll say oh generate sl
5:42:165 hours, 42 minutes, 16 secondsID and then let's go ahead and create this method. So I'll go into let's go into libs
5:42:245 hours, 42 minutes, 24 secondsand I'm going to do it here. say export function and generate log id.
5:42:335 hours, 42 minutes, 33 secondsSo I'm going to import import from nanoid.
5:42:415 hours, 42 minutes, 41 secondsSo let me install it. Let me cancel my server.
5:42:495 hours, 42 minutes, 49 secondsSo I made mistake. Should be.
5:42:545 hours, 42 minutes, 54 secondsOkay, I think it's here. So, no need to install it. We can get custom alphabet and then I'm just going to have this
5:43:025 hours, 43 minutes, 2 secondshere and I'm going to return nanoid. So, let me copy this paste it here and then we can import it inside the chart. So, let me import it here.
5:43:155 hours, 43 minutes, 15 secondsSo we've imported now we need to get we need to get u check if the user let's get the user equals to use user.
5:43:295 hours, 43 minutes, 29 secondsSo we need to get the user um sorry we need to check if the user um GitHub is
5:43:375 hours, 43 minutes, 37 secondsconnected like GitHub account is connected. So what we're going to do I'm going to go back into the back end and I'm going to add it here. So let's go
5:43:455 hours, 43 minutes, 45 secondsinto back end and inside service not service let's do it inside controller al
5:43:525 hours, 43 minutes, 52 secondsand then if I scroll down here so we returning the user we can get the um the
5:44:015 hours, 44 minutes, 1 secondgithub account here just to check if the github account exist. So what I can do I can use a constant
5:44:095 hours, 44 minutes, 9 secondsuser id is equals to request dot user.
5:44:185 hours, 44 minutes, 18 secondsOh, let me just do user like this and I'll say constant
5:44:245 hours, 44 minutes, 24 secondsuser id is equals to user dot id
5:44:325 hours, 44 minutes, 32 secondsid and then I'll just do if this then user
5:44:415 hours, 44 minutes, 41 secondsum dot id dot to string
5:44:505 hours, 44 minutes, 50 secondselse no so I will just um just do user here
5:44:595 hours, 44 minutes, 59 secondslike this so what I'm going to do I'm going to say constants
5:45:065 hours, 45 minutes, 6 secondsgithub and connected so connected
5:45:165 hours, 45 minutes, 16 secondsis equals do. So, I'm going to check if user ID um
5:45:235 hours, 45 minutes, 23 secondsor let me just do it here. if if not.
5:45:305 hours, 45 minutes, 30 secondsSo, let me just so if you ID um I want to make sure I'm able to get
5:45:395 hours, 45 minutes, 39 secondsfetch the G. So, I can just do Okay. So, what I'm going to I'm just going to set this to false like this.
5:45:505 hours, 45 minutes, 50 secondsThen I'm going to say if um
5:45:565 hours, 45 minutes, 56 secondsif user ID then I'm going to say um constant
5:46:065 hours, 46 minutes, 6 secondsum is GitHub
5:46:145 hours, 46 minutes, 14 secondsequals to a let's import GitHub account sis
5:46:275 hours, 46 minutes, 27 secondsI'll pass in the user ID so let me set this to
5:46:385 hours, 46 minutes, 38 secondsso yes I'm just going to come down here I'm going to say GitHub
5:46:435 hours, 46 minutes, 43 secondsGitHub connected is equals to is let me change this to is exist.
5:46:545 hours, 46 minutes, 54 secondsSo just to boolean is ex is
5:47:025 hours, 47 minutes, 2 secondsthen I'm just going to return GitHub sorry get up connected.
5:47:145 hours, 47 minutes, 14 secondsSo now we have this. So I'll just go back to let me go back to uh index sorry the
5:47:225 hours, 47 minutes, 22 secondscharts and then I can just get data is going to be current
5:47:295 hours, 47 minutes, 29 secondsuser user. So let me go back to what I'm going to I'm just going to
5:47:385 hours, 47 minutes, 38 secondslet me dructure this or I can do if user
5:47:475 hours, 47 minutes, 47 secondsum sorry if user user then we can just do the structure
5:47:565 hours, 47 minutes, 56 secondsuser and then I can pass in the GitHub GitHub connected else.
5:48:075 hours, 48 minutes, 7 secondsSo let me remove this.
5:48:115 hours, 48 minutes, 11 secondsSo I can go back now and then I can just say I can just do constant
5:48:215 hours, 48 minutes, 21 secondsis GitHub connected
5:48:325 hours, 48 minutes, 32 secondsand we're going to say boo um current user user.gettop Let's get up connected.
5:48:415 hours, 48 minutes, 41 secondsNow we have this. So now we can then fetch the repository. We can get the
5:48:485 hours, 48 minutes, 48 secondsrepo. So I will just go to inside the API and let's add in the
5:48:555 hours, 48 minutes, 55 secondsendpoint to fetch all the repository. So just add in a type first. Let me go and create a type. So just say github
5:49:045 hours, 49 minutes, 4 secondstype.tx TX and then let me pass it here. So we have
5:49:115 hours, 49 minutes, 11 secondsthis here. So I'm just going to save it and I'll go to API and I'm going to add
5:49:185 hours, 49 minutes, 18 secondsexport and then I'm going to import GitHub repo response.
5:49:265 hours, 49 minutes, 26 secondsAnd now we have this. So we can also add in the endpoint to connect GitHub. So I'm going to paste it here. And I'm going to import GitHub connect repo.
5:49:375 hours, 49 minutes, 37 secondsSo this is going to we're going to pass in the param we direct to. So now we have this. We can go ahead
5:49:445 hours, 49 minutes, 44 secondsand use this. So I'm just going to copy this. Now let's go into use chat and
5:49:505 hours, 49 minutes, 50 secondsthen we can just fetch this. So say data I'll call this GitHub repo and is pending.
5:50:035 hours, 50 minutes, 3 secondsAnd we can just say is GitHub
5:50:105 hours, 50 minutes, 10 secondsum repo and pending and then we can just do equals to use
5:50:195 hours, 50 minutes, 19 secondsquery. So let's import use query pass. Then we going to import the G repo.
5:50:315 hours, 50 minutes, 31 secondsSo now I'm going to map this. So constant. So just add it here. So let me
5:50:395 hours, 50 minutes, 39 secondsreplace this with GitHub repos and we can import this.
5:50:465 hours, 50 minutes, 46 secondsSo just label which is going to be rep item full name the value clone URL and then the default branch. So we have this
5:50:565 hours, 50 minutes, 56 secondsnow. So now it's going to we're going to then import the AISDK chart. So I'll do
5:51:025 hours, 51 minutes, 2 secondsthat here. Let me move this to the top and I'm going to import the two. So use
5:51:115 hours, 51 minutes, 11 secondscharts from here we say constant is equals to use chat hook.
5:51:225 hours, 51 minutes, 22 secondsWe're going to say messages empty array and I'm going to get messages send
5:51:285 hours, 51 minutes, 28 secondsmessage set message status error and stop and we're going to set transport
5:51:395 hours, 51 minutes, 39 secondsto transport. This is going to be equals to new default. So let me import new default transport from AI package. And
5:51:495 hours, 51 minutes, 49 secondsnow we need to set the API. So the API is going to be we're going to import base
5:51:565 hours, 51 minutes, 56 secondsbase URL from the li folder lib lib env session
5:52:055 hours, 52 minutes, 5 seconds/ chat and I'm going to do credential
5:52:135 hours, 52 minutes, 13 secondsinclude and then we're going to say prepare
5:52:205 hours, 52 minutes, 20 secondsprepare send message request and we're going to get message
5:52:265 hours, 52 minutes, 26 secondsmessages and we're going to get body. So the body is going to be what we're going to pass we're going to send the message
5:52:345 hours, 52 minutes, 34 secondsgoing to send there and we're going to also pass in the body like this log and the default branch. So I'm just going to say body.
5:52:455 hours, 52 minutes, 45 secondsSo the structural body and I'll pass in messages
5:52:535 hours, 52 minutes, 53 secondsand the error should stop. So now I'm going to below here.
5:53:005 hours, 53 minutesLet's add comma here. Sorry, not here. So we're going to have on data.
5:53:105 hours, 53 minutes, 10 secondsSorry, on data. And we're going to so we're going to get data path.
5:53:235 hours, 53 minutes, 23 secondsSo and data is going to is where um this custom um event will be returned here.
5:53:305 hours, 53 minutes, 30 secondsSo the custom events are the ones that um they're not going to be saved inside the messages. So if I go back to lib
5:53:385 hours, 53 minutes, 38 secondsfolder AI2 to or inside the u inside the service
5:53:465 hours, 53 minutes, 46 secondssession service so where we have we first of all send
5:53:525 hours, 53 minutes, 52 secondsthe title we wrote writer write title so because we added this this is going to
5:53:595 hours, 53 minutes, 59 secondsum appear on the in the on data method there so but anyone that send that does
5:54:075 hours, 54 minutes, 7 secondsnot have this is going to be added to the message list. So because of that we're going to get the title now from
5:54:145 hours, 54 minutes, 14 secondsthe on data. So we're going to say data part and together we're going to say
5:54:225 hours, 54 minutes, 22 secondsconstant part is equals to data um part
5:54:315 hours, 54 minutes, 31 secondsand we can just say constant data. So let me just change this to part um part like this.
5:54:425 hours, 54 minutes, 42 secondsI remove this. I'll just say equals to part dot data.
5:54:545 hours, 54 minutes, 54 secondsSo let's use a switch statement. It's a switch part um part type.
5:55:065 hours, 55 minutes, 6 secondsSo So now I'm going to say um case
5:55:135 hours, 55 minutes, 13 secondsand what was the inside service? This was data session title. So copy it. I'll
5:55:215 hours, 55 minutes, 21 secondspaste it here. And I'm going to say if so let me remove this if data dot title.
5:55:335 hours, 55 minutes, 33 secondsSo if you look at it we pass in title here. So let me add in as any here
5:55:435 hours, 55 minutes, 43 secondserror stop. So if we have this we're going to say set session title and we're going to say data title.
5:55:555 hours, 55 minutes, 55 secondsSo now we set this now. So once we set this but if we update the title the
5:56:025 hours, 56 minutes, 2 secondssidebar does not have the recent um data that recent session that was created. So
5:56:095 hours, 56 minutes, 9 secondswe need to since we're using TQ query we can use query client to invalidate the um query and this is going to fetch it's going to refetch the uh sessions here.
5:56:215 hours, 56 minutes, 21 secondsSo we're going to use this query key. So I'm going to import query client here.
5:56:285 hours, 56 minutes, 28 secondsSo let me do top here. So just say constant query client
5:56:365 hours, 56 minutes, 36 secondsis equals to use query client and now I can just say query client then
5:56:455 hours, 56 minutes, 45 secondsI'll come down here and I'll just say u query client dot invalidate
5:56:545 hours, 56 minutes, 54 secondsmy queries and we say query key
5:57:005 hours, 57 minutesand on this uh chat session we call the key user sessions.
5:57:065 hours, 57 minutes, 6 secondsSo copy this and I'm going to paste it here and now we can just say break here.
5:57:145 hours, 57 minutes, 14 secondsThen also if we go back to the chat sorry not chat session um
5:57:225 hours, 57 minutes, 22 secondsso I think I've got it. So inside the session service we used to send another event here data rep info. Let's copy it
5:57:325 hours, 57 minutes, 32 secondsnow. Let's go back to the chat. Then we're going to so write a case for this.
5:57:385 hours, 57 minutes, 38 secondsyou say case sorry I'm going to paste this here
5:57:455 hours, 57 minutes, 45 secondsand I'm going to say if data dot ripple URL
5:57:555 hours, 57 minutes, 55 secondsso let me make sure okay I need to move this out of this
5:58:035 hours, 58 minutes, 3 secondsURL I think that's what we pass here repo URL then we can get repo URL and
5:58:095 hours, 58 minutes, 9 secondsthe default branch. So I say follow say
5:58:165 hours, 58 minutes, 16 secondssorry set reple value is going to be data
5:58:265 hours, 58 minutes, 26 secondsrepo url and default branch
5:58:345 hours, 58 minutes, 34 secondsis going to be data do default branch branch.
5:58:465 hours, 58 minutes, 46 secondsSo this is for the data u data URL and I think we also sent in the branch name.
5:58:525 hours, 58 minutes, 52 secondsSo we can use that. So we can just say set branch name here.
5:58:575 hours, 58 minutes, 57 secondsUh let me just do it here. Say if data do branch name
5:59:045 hours, 59 minutes, 4 secondsthen we can just set branch name data branch
5:59:125 hours, 59 minutes, 12 secondsname and then we can say uh break.
5:59:235 hours, 59 minutes, 23 secondsSo now we have this. So the last one the custom message we sent.
5:59:335 hours, 59 minutes, 33 secondsOkay. I think here I need to move this out of this if block. Yeah. So the last um event custom event we sent in the uh
5:59:425 hours, 59 minutes, 42 secondssession service was inside the tool. So if I go to um
5:59:495 hours, 59 minutes, 49 secondssorry inside li github 2 we have the data pl ready. So I'm going to copy this and we're going to write a case for it.
6:00:026 hours, 2 secondsSo I say case we pass in data p
6:00:096 hours, 9 secondsand we're going to say if data does log id then we're going to say set p r
6:00:196 hours, 19 secondsuh ready and we can pass in this log id
6:00:266 hours, 26 secondsdata log id title data
6:00:326 hours, 32 secondsdot title and then body
6:00:416 hours, 41 secondsdata dot body and then branch I think I passed in um I
6:00:496 hours, 49 secondsalso added branch branch name so I'll say branch data dot branch
6:00:586 hours, 58 secondsoh we can fall back to the branch name Yeah.
6:01:036 hours, 1 minute, 3 secondsThen I'm going to set once this sent, we're going to set um set create P URL to no.
6:01:126 hours, 1 minute, 12 secondsSo we clear out the previous P URL that was stored in the state. So we can say break here.
6:01:236 hours, 1 minute, 23 secondsAnd then I'm just going to say default break.
6:01:326 hours, 1 minute, 32 secondsSo, I'm going to collapse this now. And we're going to say um on error error.
6:01:456 hours, 1 minute, 45 secondsI'll just say console.log error.
6:01:536 hours, 1 minute, 53 secondsAnd we can just s error failed to generate response.
6:02:046 hours, 2 minutes, 4 secondsSo let's import toast from sona. So now we're going to have a use effect.
6:02:136 hours, 2 minutes, 13 secondsSo since we are sending the single session page, we're going to send the initial message. So we need to um set
6:02:226 hours, 2 minutes, 22 secondsthe messages in the use chat book. So I'm just going to say and let's return
6:02:296 hours, 2 minutes, 29 secondsthis. I'll say if not if not single
6:02:356 hours, 2 minutes, 35 secondssingle session a single session then I'm just going to return. But if we in the
6:02:446 hours, 2 minutes, 44 secondssingle session, we're going to say if initial message was passed, initial messages, then we can just set messages.
6:02:546 hours, 2 minutes, 54 secondsSet messages and we're going to pass in the initial initial message. Then we're going to say
6:03:016 hours, 3 minutes, 1 secondif session title, sorry, if yeah, if session title prop
6:03:096 hours, 3 minutes, 9 secondswas passed, we just say set session um title which is going to be session um session title props.
6:03:206 hours, 3 minutes, 20 secondsWe are going to do the same thing for um branch. We say if branch
6:03:256 hours, 3 minutes, 25 secondsname prop set branch name uh we just say oh sorry
6:03:356 hours, 3 minutes, 35 secondsbranch name and props. Then we're going to add a dependency here.
6:03:416 hours, 3 minutes, 41 secondsSo I say initial messages um set messages
6:03:526 hours, 3 minutes, 52 secondsuh session title set session um title
6:04:036 hours, 4 minutes, 3 secondsbranch name branch name props site branch name and a single session.
6:04:206 hours, 4 minutes, 20 secondsSo I think okay let me add comment here.
6:04:246 hours, 4 minutes, 24 secondsSo now we have the unsub um the handle submit I say handle submit
6:04:326 hours, 4 minutes, 32 secondsthis is going to be equals to um message. So the message is um we're
6:04:396 hours, 4 minutes, 39 secondsgoing to say this um any for now and I'm going to return this. So I'm going to check for this if GitHub is not
6:04:486 hours, 4 minutes, 48 secondsconnected. So please connect to GitHub first. If there's not select a repo and we're going to say if no
6:04:566 hours, 4 minutes, 56 secondsmessage so this is going to we're going to install um a component called prompt
6:05:036 hours, 5 minutes, 3 secondsfrom AI element which is owned by V. So once we add it, we're going to add a type here. So we're going to use the
6:05:116 hours, 5 minutes, 11 secondscomponent and the component is going to return messages dot message.ext or message do files. So I'm going to then
6:05:206 hours, 5 minutes, 20 secondsthen once user send a message we're going to say set PR ready
6:05:276 hours, 5 minutes, 27 secondsto know and set create
6:05:366 hours, 5 minutes, 36 secondsour URL to know then I'm going to say if not a single
6:05:466 hours, 5 minutes, 46 secondssession Then like I said earlier, we're going to update the URL. If this is on the
6:05:536 hours, 5 minutes, 53 secondshomepage, we going to update the URL to point to the single session page. But the page does not change. So in case the
6:06:016 hours, 6 minutes, 1 seconduser refresh the page, the user will land on the single page and see the message, the history, the chat history.
6:06:086 hours, 6 minutes, 8 secondsSo I'm going to do window.history history dot push
6:06:166 hours, 6 minutes, 16 secondsstate is set here to null uh empty string
6:06:236 hours, 6 minutes, 23 secondsand there we're going to pass in session slash sl
6:06:326 hours, 6 minutes, 32 secondsID then I'm going to also check if not session title then we're going to set
6:06:416 hours, 6 minutes, 41 secondssession title to on on title session. So this is only going to be possible when and the user is on the homepage. So
6:06:506 hours, 6 minutes, 50 secondsinstead of showing title as empty um blank like that, we're just going to instead just set on title session. Then
6:06:596 hours, 6 minutes, 59 secondsnow we're going to send the message. You say send message
6:07:076 hours, 7 minutes, 7 secondsand we're going to set it to sorry text message do text
6:07:176 hours, 7 minutes, 17 secondsand then I'm going to pass in body.
6:07:236 hours, 7 minutes, 23 secondsWe going to pass in the stock ID, the repo URL,
6:07:296 hours, 7 minutes, 29 secondsand the default branch. So we have this now. So we are done with the handle submit. Now I'm going to create a
6:07:386 hours, 7 minutes, 38 secondsmethod. I'll call handle handle back.
6:07:456 hours, 7 minutes, 45 secondsAnd this is just going to call the stop method from the use um use chat hook.
6:07:536 hours, 7 minutes, 53 secondsAnd then we're going to have a method to select repository. So handle repo change. This is once we pass in a value,
6:08:006 hours, 8 minuteswe're going to find a value from the repo option. So we can get value and then sorry we can just say if repo then
6:08:096 hours, 8 minutes, 9 secondswe pass in else just say default branch to main. So now we are done with this.
6:08:156 hours, 8 minutes, 15 secondsNow we can just add a class here. So I'll say class name and then I'm just going to
6:08:236 hours, 8 minutes, 23 secondsimport CN from YouTube and I'm going to say flex. I'm going to give this a height of um
6:08:326 hours, 8 minutes, 32 seconds100 dvh and minimum height zero width full.
6:08:406 hours, 8 minutes, 40 secondsI'll say it's reflex column two and this should be overflow hidden
6:08:496 hours, 8 minutes, 49 secondsand if we passing class name we just pass in the class name here
6:08:546 hours, 8 minutes, 54 secondsand then I'll say if messagelength
6:09:026 hours, 9 minutes, 2 secondsuh so if messages length is equals to zero
6:09:116 hours, 9 minutes, 11 secondsand it's not um a single a single session then I'm going to add a class
6:09:216 hours, 9 minutes, 21 secondsI'll call this chart interface so this is going to show like a gradient
6:09:286 hours, 9 minutes, 28 secondsso I added this class if you go to um index dot css if you copied it inside
6:09:356 hours, 9 minutes, 35 secondsindex css if you scroll down to the bottom you should it here. So I have light chart interface and for that we
6:09:446 hours, 9 minutes, 44 secondsjust set this to more. So I'm just going to save this and then now we're going to show the
6:09:526 hours, 9 minutes, 52 secondstitle. I'll say if we have session title then we have a div here.
6:10:066 hours, 10 minutes, 6 secondsLet's give this a class name.
6:10:096 hours, 10 minutes, 9 secondsI'll say border B padding X
6:10:146 hours, 10 minutes, 14 secondsand P Y three. And then let's say H5 H5
6:10:236 hours, 10 minutes, 23 secondsand let's give this a class name and text base and font
6:10:346 hours, 10 minutes, 34 secondsmedium. Then let's pass in session by two.
6:10:406 hours, 10 minutes, 40 secondsSo now then below here we're going to have a div.
6:10:456 hours, 10 minutes, 45 secondsSo I'll give this a class relative flex minimum height zero width flex one and flex column. So we're going to have the conversation list here.
6:10:586 hours, 10 minutes, 58 secondsThat is a chart history. So, we're going to have um conversation.
6:11:076 hours, 11 minutes, 7 secondsYeah. So, let me comment. Let me like this.
6:11:116 hours, 11 minutes, 11 secondsAnd we're going to also have the chart or the prompt. Let me call the chart impute.
6:11:236 hours, 11 minutes, 23 secondsSo, we need to install this component I said we're going to install. So, let's go to the browser.
6:11:316 hours, 11 minutes, 31 secondsSo let's go to AI element. Click on this
6:11:386 hours, 11 minutes, 38 secondsand let's go to component.
6:11:456 hours, 11 minutes, 45 secondsSo we're going to install some of these components. We're going to install chain of chain of thought conversation. So let's click on conversation. Let's first
6:11:546 hours, 11 minutes, 54 secondsof all add conversation. So you can click on shanti cla copy it let's head over to the code and then let me um stop
6:12:026 hours, 12 minutes, 2 secondsmy server my client side stop this I'll paste this here and click on enter
6:12:096 hours, 12 minutes, 9 secondswhile this is installing let's go back to the browser and let's go ahead and copy prompt impute so I'll just scroll
6:12:196 hours, 12 minutes, 19 secondsdown click on cla copy this and once we install um prompt we inst install message then we install chain of dot. So let's go back.
6:12:326 hours, 12 minutes, 32 secondsLet's wait for this to install. So now let's paste in the prompt impute.
6:12:386 hours, 12 minutes, 38 secondsAnd while this is installing, let's go back and then let's um go to the browser and let's copy message
6:12:516 hours, 12 minutes, 51 secondsCLA and click on copy and then let's go back to the code. And let's wait for this to install.
6:12:596 hours, 12 minutes, 59 secondsSo let's say no no no.
6:13:126 hours, 13 minutes, 12 secondsSo let's paste this um message and enter. So let's go back to the browser
6:13:186 hours, 13 minutes, 18 secondsagain and then let's go ahead and copy chain of thoughts.
6:13:256 hours, 13 minutes, 25 secondsSo click on CLI. Copy this. And I think the next thing is the reason. We're going to copy reason
6:13:336 hours, 13 minutes, 33 secondsand reason. And um I think reason.
6:13:406 hours, 13 minutes, 40 secondsSo let's just shimmer. So let's go um into let's go to the back end. Sorry,
6:13:496 hours, 13 minutes, 49 secondsthe code editor. And then let's wait for this to install. So let's uh say no.
6:13:576 hours, 13 minutes, 57 secondsNo.
6:14:026 hours, 14 minutes, 2 secondsAnd now I paste this one chain of thought. Then let's go back to the browser again and let's copy. We have comet. So let me look for comet first.
6:14:136 hours, 14 minutes, 13 secondsSo in code we can see comet here. So let me copy comet first for the reason. So
6:14:216 hours, 14 minutes, 21 secondscopy comet. Let's head back to the code editor and let me wait for this to install.
6:14:296 hours, 14 minutes, 29 secondsThen I'm going to just say no.
6:14:346 hours, 14 minutes, 34 secondsLet me clear the terminal and let's commit. Click on enter. So there's many two components we need to
6:14:426 hours, 14 minutes, 42 secondscopy the um need to let's scroll up reasoning and shimmer. So let's go and copy these components.
6:14:566 hours, 14 minutes, 56 secondsAnd then let's go back to the um code editor.
6:15:016 hours, 15 minutes, 1 secondOkay, I think I mistically copied the one for copy AI element. So let me go back and copy commit CLI.
6:15:176 hours, 15 minutes, 17 secondsSo I'll cancel this past this and click on enter. Then I'll go back again and copy
6:15:246 hours, 15 minutes, 24 secondsuh let me scroll back up. Copy reason CLI and I'm going to go back.
6:15:356 hours, 15 minutes, 35 secondsI'll wait for this to install. So now it is done. So let me paste in.
6:15:466 hours, 15 minutes, 46 secondsSo let's go back to the um content sorry to the browser and let's copy the last
6:15:536 hours, 15 minutes, 53 secondsshimmy. So let's click on shanty cla and let's go back to code
6:16:036 hours, 16 minutes, 3 secondsand let me wait for this to install. So I'm going to say no.
6:16:096 hours, 16 minutes, 9 secondsSo okay, it has added the shimmer component too. So I think there's no need for that again. So um I also want
6:16:166 hours, 16 minutes, 16 secondsto add this component. So this is not for AI SDK AI elements. This is going to
6:16:226 hours, 16 minutes, 22 secondsbe inside assistant UI.com and I want to copy I want to install this package div viewer. So we have a file we have split.
6:16:336 hours, 16 minutes, 33 secondsSo I'm going to install this package and you can use shantui to install it. So I'll copy this command and then let's go
6:16:416 hours, 16 minutes, 41 secondsback to the code. So this is going to be the last components we're going to add.
6:16:466 hours, 16 minutes, 46 secondsSo I'll click on enter and let's wait for this to install. So this has already add. So now we can go back and let's um
6:16:546 hours, 16 minutes, 54 secondslet's let me collapse the back end. And then we should see
6:17:016 hours, 17 minutes, 1 secondwe should see all the components. we have the AI element and we have this um component the F viewer.
6:17:146 hours, 17 minutes, 14 secondsSo what I'm going to do now we're going to implement the we're going to add the conversation. So I'm going to paste this here
6:17:226 hours, 17 minutes, 22 secondsand let me import the components conversation.
6:17:286 hours, 17 minutes, 28 secondsUh let's import this from AI element and let's import conversation content to from AI element. So we're going to have
6:17:376 hours, 17 minutes, 37 secondsa div here. So I'll say div and I'm going to give this a class name.
6:17:456 hours, 17 minutes, 45 secondsSo I'm going to say um flex minimum height full width full flex flex one
6:17:526 hours, 17 minutes, 52 secondsflex column gap um two. And we going to say if message length was zero and it's
6:17:596 hours, 17 minutes, 59 secondsnot single then we're going to center it to the center. Now we're going to say if messagelength.
6:18:086 hours, 18 minutes, 8 secondsSo let me just copy what I have here.
6:18:126 hours, 18 minutes, 12 secondsIf message sorry if message.length length and then
6:18:196 hours, 18 minutes, 19 secondswe going to import conversation uh conversation empty.
6:18:286 hours, 18 minutes, 28 secondsSo I'm going to pass in a class name here exis.
6:18:366 hours, 18 minutes, 36 secondsSo I'm going to add the empty state. So I'm going to paste it here and I'm going to import the logo component.
6:18:476 hours, 18 minutes, 47 secondsSo here we're going to say else and I'm going to um load through the
6:18:546 hours, 18 minutes, 54 secondsmessages. So say messages dot messages do me.
6:19:056 hours, 19 minutes, 5 secondsWe're going to get message and message index and let's return
6:19:156 hours, 19 minutes, 15 secondslet's return this. So let's import message from AI element.
6:19:236 hours, 19 minutes, 23 secondsSo we're going to pass in from message dot row.
6:19:336 hours, 19 minutes, 33 secondsWe're going to pass in key message do ID and I'm going to give this a class name.
6:19:446 hours, 19 minutes, 44 secondsI'm going to say maximum width gap zero.
6:19:536 hours, 19 minutes, 53 secondsSo, we're going to import message content
6:20:016 hours, 20 minutes, 1 secondand we're going to give this a class name.
6:20:116 hours, 20 minutes, 11 secondsSorry.
6:20:146 hours, 20 minutes, 14 secondsSo, this is going to be widthful text 14.5 pixel. And if is user, we're
6:20:216 hours, 20 minutes, 21 secondsjust going to add margin button one. So we can look through the message part. So I can say um
6:20:306 hours, 20 minutes, 30 secondsmessage dot part sorry dot map
6:20:436 hours, 20 minutes, 43 secondspart index and then I can just return this. So we
6:20:516 hours, 20 minutes, 51 secondscan use switch statement and we're going to say part type.
6:20:596 hours, 20 minutes, 59 secondsSo the first case we're going to use is reason. So let me say reason.
6:21:146 hours, 21 minutes, 14 secondsSo why is it showing error?
6:21:226 hours, 21 minutes, 22 secondsSo for I'm going to just say constant message text is equals to part text.
6:21:346 hours, 21 minutes, 34 secondsSo let me see.
6:21:396 hours, 21 minutes, 39 secondsOkay, I made a mistake. My spelling here.
6:21:466 hours, 21 minutes, 46 secondsThe error should stop.
6:21:526 hours, 21 minutes, 52 secondsSo I'm going to say constant is streaming. Let's define the is last message here. So at the top here I'm
6:22:006 hours, 22 minutesgoing to say constant last message
6:22:076 hours, 22 minutes, 7 secondsis going to be sorry let me use is last message and then this is going to be equals to
6:22:156 hours, 22 minutes, 15 secondsmessage index is equals to messages dotlength minus one.
6:22:276 hours, 22 minutes, 27 secondsSo we're going to say is um pass message and status
6:22:356 hours, 22 minutes, 35 secondsis equals to streaming.
6:22:416 hours, 22 minutes, 41 secondsSo I'm just going to move this here.
6:22:466 hours, 22 minutes, 46 secondsAnd then once we have this, we're just going to return and let's import reasoning component
6:22:566 hours, 22 minutes, 56 secondsfrom AI element and we need to pass in key here. So I'm going to say key
6:23:046 hours, 23 minutes, 4 secondsis um we're going to use this. I'm going to pass in message
6:23:116 hours, 23 minutes, 11 secondsID dash reason and I'm going to pass in the path index here.
6:23:226 hours, 23 minutes, 22 secondsSo we're going to pass in a streaming equals to a streaming
6:23:316 hours, 23 minutes, 31 secondsand I'm going to set default open to false.
6:23:386 hours, 23 minutes, 38 secondsSo let's import reason trigger.
6:23:426 hours, 23 minutes, 42 secondsReason trigger it's going to be safe close and then we're going to import raising content.
6:23:516 hours, 23 minutes, 51 secondsOkay. Content and let's pass a message message here. Message text.
6:24:066 hours, 24 minutes, 6 secondsSo now we have for reason we are going to for text. So I'm going to add in case
6:24:156 hours, 24 minutes, 15 secondstext. So if part type is text, we going to return.
6:24:226 hours, 24 minutes, 22 secondsLet's import message response from a message. And I'm going to
6:24:306 hours, 24 minutes, 30 secondsadd key. Yeah. And this is going to be message dot id
6:24:396 hours, 24 minutes, 39 secondstext and um part index.
6:24:466 hours, 24 minutes, 46 secondsAnd let's pass in part text.
6:24:516 hours, 24 minutes, 51 secondsOh, sorry message text.
6:25:056 hours, 25 minutes, 5 secondsSo I'm making a mistake. Type text message text is for the reason. So this
6:25:126 hours, 25 minutes, 12 secondsis fine. So um inside the message response so message response is is using let me go into the component
6:25:206 hours, 25 minutes, 20 secondsit's using if I scroll to the top. So it's using a component uh package called stream down and stream down code. So we
6:25:286 hours, 25 minutes, 28 secondsneed to um add some sty because of this stream down code we're using. So before I add a sign in the CSS I need to first
6:25:376 hours, 25 minutes, 37 secondsof all add let me add um a prop here. So I'm going to say
6:25:456 hours, 25 minutes, 45 secondsa team. So I'm going to add it. I'm going to use the dracula
6:25:536 hours, 25 minutes, 53 secondsand let me also say dracula here and then inside the index of CSS I'm
6:26:006 hours, 26 minutesgoing to add in at the top here. Let me go to the top and I'm going to add it
6:26:076 hours, 26 minutes, 7 secondshere. So paste it here. So this is what I'm going to add. So just add this and then let's go back to the code and let's
6:26:156 hours, 26 minutes, 15 secondsgo ahead and continue this. So I'm going to then the next um case we're going to write is for the tools. So um the tools
6:26:236 hours, 26 minutes, 23 secondswe have inside the back end um s
6:26:306 hours, 26 minutes, 30 secondsum lib AI tools GitHub tools. So we need to uh we need to write the case for
6:26:386 hours, 26 minutes, 38 secondsthis. So since we using the tools um is inbuilt this going to be return my visdk.
6:26:476 hours, 26 minutes, 47 secondsSo we are going to just use you can just say case and this is going to be two dash list.
6:26:596 hours, 26 minutes, 59 secondsSo two dash list. So list is going to be the name of the two we set here. So if you see we have the first two we wrote
6:27:086 hours, 27 minutes, 8 secondshere is list. So we're going to have two grip two read two right to edit and like
6:27:166 hours, 27 minutes, 16 secondsthat. So I'm just going to add everything here.
6:27:256 hours, 27 minutes, 25 secondsSo let me just push this.
6:27:296 hours, 27 minutes, 29 secondsSo you can see it's two G status two commit to G push create PL and then the
6:27:366 hours, 27 minutes, 36 secondsweb search. So now for this we're going to create our custom two component for each of the tools we have here. So I'm
6:27:466 hours, 27 minutes, 46 secondsgoing to say return render to part and there we going to pass in
6:27:546 hours, 27 minutes, 54 secondsthe message ID for message id we're going to pass in the path. I'm just going to set this as any
6:28:036 hours, 28 minutes, 3 secondsand we're going to pass in the index. So part index and after this so we're going to create
6:28:126 hours, 28 minutes, 12 secondsa component. So let me first of all set default here.
6:28:176 hours, 28 minutes, 17 secondsUh return no.
6:28:216 hours, 28 minutes, 21 secondsSo let's go ahead and create this component. So I'm going to create let me call out everything inside the client
6:28:286 hours, 28 minutes, 28 secondsinside of C4. So let's do it inside component chat.
6:28:346 hours, 28 minutes, 34 secondsLet's see here say two render two parts CX6 or we can call it two parts.
6:28:506 hours, 28 minutes, 50 secondsSo the first thing we going to do before we create the render component we going to create a custom component called two core. So you can copy all of this from
6:28:596 hours, 28 minutes, 59 secondsthe GitHub. I'm going to be pasting them one after the other. So I'm going to paste in the first one. So the first one here is to go. So I'm going to import all of the packages of the import here.
6:29:106 hours, 29 minutes, 10 secondsSo I've import them. You can see we going to import the div from assistant UI UI the comet component the chain of
6:29:196 hours, 29 minutes, 19 secondsthought the um the UI message the UI message and some other prof package. So
6:29:286 hours, 29 minutes, 28 secondsbasically this is just the two code. So this is going to wrap the this is going to be the parent component and we are going to create an inner component here
6:29:366 hours, 29 minutes, 36 secondswhich we're going to call twostep. So this is going to be the header part. As you can see we have um we have if this
6:29:456 hours, 29 minutes, 45 secondsis running um if it's running we going to show we're going to just animate this and we're going to show dot for each of
6:29:536 hours, 29 minutes, 53 secondsthe N2 and the name the title of the two. And if subtitle is there, we're going to just render it there. And if
6:30:016 hours, 30 minutes, 1 secondit's not running, then we're going to show in the step of the tribe here below here. So this is the two core. So we're
6:30:096 hours, 30 minutes, 9 secondsgoing to have another component called two step. So I'm going to paste it here.
6:30:146 hours, 30 minutes, 14 secondsSo this is two core step. So now let me write in the render component here. So say constant export constant
6:30:246 hours, 30 minutes, 24 secondsrender to part is equals to
6:30:316 hours, 30 minutes, 31 secondslet's return this. So like we pass we pass a message id
6:30:406 hours, 30 minutes, 40 secondswhich is going to be of a string part.
6:30:456 hours, 30 minutes, 45 secondsSo we can say this to any or we can say this to two parts.
6:30:526 hours, 30 minutes, 52 secondsAnd then we have the parts index which is type number.
6:31:036 hours, 31 minutes, 3 secondsSo now we're going to get in the the part has the state. So if I go here we
6:31:086 hours, 31 minutes, 8 secondscan see the two part has states impute output error text. So we going to pick
6:31:176 hours, 31 minutes, 17 secondsthe state and with the state we're going to know when the um AI is loading or stream or is running the two is running.
6:31:246 hours, 31 minutes, 24 secondsSo I'm going to just say constant is running
6:31:316 hours, 31 minutes, 31 secondsand this is going to be equals to math do state is equals to impute streaming
6:31:416 hours, 31 minutes, 41 secondsor path do state is equals to impute available
6:31:496 hours, 31 minutes, 49 secondsthen we can have so I'm going to say constant is done. So once it is done running we can say state
6:31:596 hours, 31 minutes, 59 secondssorry path state is equals to output available
6:32:096 hours, 32 minutes, 9 secondsthen if is error so constant is error
6:32:176 hours, 32 minutes, 17 secondsis equals to part state is equals to output error.
6:32:276 hours, 32 minutes, 27 secondsSo to get the title and the subtitle, I'm going to create a method here. So I'm going to paste it here. So this is
6:32:366 hours, 32 minutes, 36 secondsgoing this is method is going to get give us a title and the subtitle. So we're going to pass in the part and we can get the impute. you can get the
6:32:446 hours, 32 minutes, 44 secondsoutput and then we can so for this for the hash part if you look at the two
6:32:526 hours, 32 minutes, 52 secondsgithub to if I go to edit you can see we pass in
6:32:586 hours, 32 minutes, 58 secondspatch and we pass in part and additions and um deletion so the part is coming from the diff result so we want to know
6:33:086 hours, 33 minutes, 8 secondsif the user is making if the AI is making an edit an existing file is going to return a patch. But if it's a new file, you just create it and you
6:33:176 hours, 33 minutes, 17 secondsjust edit the file. It might not return a not there might not be a patch. So we are going to have a custom
6:33:266 hours, 33 minutes, 26 secondsum we're going to have a custom component that's going to handle this.
6:33:306 hours, 33 minutes, 30 secondsSo we say if it has patch then we're going to render the edit um edit subtitle. Else we just only show the impute.path.
6:33:406 hours, 33 minutes, 40 secondsSo I'm going to create this component.
6:33:426 hours, 33 minutes, 42 secondsSo I'm going to add it here. So let me paste it here. So you can see the edit subtitle. We pass in a part input
6:33:516 hours, 33 minutes, 51 secondsoutput. Now we have the patch. We are going to also have um get the different uh start from the patch and this is it.
6:34:006 hours, 34 minutesSo we just have it here. So I think there's no need to even use this because we passed
6:34:076 hours, 34 minutes, 7 secondsdeletion and um addition. So I'll just remove this. So let me remove this.
6:34:156 hours, 34 minutes, 15 secondsSo if we have this we can just say um we can get this from
6:34:236 hours, 34 minutes, 23 secondsI'll say output output or we can just say constant addition.
6:34:336 hours, 34 minutes, 33 secondsSo I'll just copy this pass it here is equals to
6:34:406 hours, 34 minutes, 40 secondsum output dot addition and then we can also do for deletion.
6:34:496 hours, 34 minutes, 49 secondsSo let me say constant deletion output dot deletion. So I'm going to remove
6:34:586 hours, 34 minutes, 58 secondsthis. So we don't need this method because we've already done it in the two. So I'm going to remove it.
6:35:086 hours, 35 minutes, 8 secondsSo this patch, we don't need this patch here.
6:35:136 hours, 35 minutes, 13 secondsSo for the sorry um edit subtitle, we just only have the addition and deletion
6:35:206 hours, 35 minutes, 20 secondshere. This is going to show in the edit title. So this is only going to be displayed at the heading which is a two
6:35:276 hours, 35 minutes, 27 secondscall this two call here. So we also have normalize commit and subject
6:35:356 hours, 35 minutes, 35 secondssubject. Let me check the two call to did I handle these two inside the commit.
6:35:446 hours, 35 minutes, 44 secondsLet me see clear message.
6:35:486 hours, 35 minutes, 48 secondsOkay, we can see if there's no text, we just say come change and if there's a text just um so I think I'll just remove this.
6:35:576 hours, 35 minutes, 57 secondsSo I'll just remove this.
6:36:026 hours, 36 minutes, 2 secondsI'll just say if no value just say come change and if let me
6:36:106 hours, 36 minutes, 10 secondschange this to text or message. I'll say if um message.
6:36:206 hours, 36 minutes, 20 secondsYeah, that's what we call it. Message text.
6:36:306 hours, 36 minutes, 30 secondsI'll just return the message. There's no need for slicing.
6:36:356 hours, 36 minutes, 35 secondsSo the reason why I I have to remove this is because in the G I've already done this. I've clean it up.
6:36:426 hours, 36 minutes, 42 secondsOkay, I didn't slice this. That's the reason why I had it there.
6:36:496 hours, 36 minutes, 49 secondsWell, at least I told the AI to to return a short commit message. So, I think this is fine.
6:36:586 hours, 36 minutes, 58 secondsOr if if we can just leave it like that is still fine. So, I'll just reverse it back and just leave it like this.
6:37:086 hours, 37 minutes, 8 secondsSo, this is fine. So, we have it here now. Commit message. So we can use this now to get the title and subtitle. So
6:37:166 hours, 37 minutes, 16 secondsI'm going to just come down here. I'm going to say constant title subtitle
6:37:276 hours, 37 minutes, 27 secondsand I'll pass in the path here. So let me get subtitle and now we can render the component. I'll say u return so
6:37:376 hours, 37 minutes, 37 secondsreturn the component so to call and then I'm going to say
6:37:466 hours, 37 minutes, 46 secondslet's pass in key and this is going to be
6:37:536 hours, 37 minutes, 53 secondsmessage message ID
6:38:016 hours, 38 minutes, 1 secondpart um part dot type and I'm going to so pass in the index
6:38:096 hours, 38 minutes, 9 secondspart index and then we can just say part
6:38:186 hours, 38 minutes, 18 secondsor let me remove all of these remove type here I'll just pass in part
6:38:266 hours, 38 minutes, 26 secondsdo core id so now we need to pass in the title.
6:38:346 hours, 38 minutes, 34 secondsSubtitle subtitle is equals to subtitle
6:38:436 hours, 38 minutes, 43 secondsis running is equals to is running.
6:38:506 hours, 38 minutes, 50 secondsSo now it's remaining done and error. So we need to we need a component for each of the u each of the parts or each of the tools. So we can go back to the top.
6:39:026 hours, 39 minutes, 2 secondsNow we have this now. So I'm going to collapse both of this and let me move this. Let me move this.
6:39:116 hours, 39 minutes, 11 secondsSo okay, there's no need. I can leave it there. So I'm going to add another component which we are going to have. So this is that this component is going to
6:39:206 hours, 39 minutes, 20 secondsbe called fire grid. So I'm going to paste it. So I'm going to paste this two. So we have two called drift and
6:39:276 hours, 39 minutes, 27 secondsdrift and then the file grid. So these are just helper components. We've not really created the two components for um
6:39:366 hours, 39 minutes, 36 secondsthe two components we're going to render inside the render and two part. So now I'm going to start with the list now. So
6:39:436 hours, 39 minutes, 43 secondsI'll paste in the list the list two components. Now you can see it. We pass in the parts. We get the files and then
6:39:516 hours, 39 minutes, 51 secondswe list to the file. So each of these component each of these two has a different um component to render the output properly. So we have the list.
6:40:006 hours, 40 minutesNow we're going to have for the grid grip. So this is for grip. We using a twostep call. Yeah. And you can see
6:40:096 hours, 40 minutes, 9 secondswe're using two step. So if file length if there's no file, it's going to just return no file found. And we have grip.
6:40:166 hours, 40 minutes, 16 secondsWe have two called step. And then you can see if lines is greater than zero, we're just going to use the file grid to
6:40:236 hours, 40 minutes, 23 secondsrender it like we have here. So we have um read content write content. So I'm
6:40:316 hours, 40 minutes, 31 secondsgoing to paste it here too. So you see we just calling the two core step pass
6:40:376 hours, 40 minutes, 37 secondsin the command line the amount of line and then we the right content we are
6:40:456 hours, 40 minutes, 45 secondspassing in the um two call steps and then we say command created this um
6:40:526 hours, 40 minutes, 52 secondsoutput dotline count. So this is just the content the output of from the tools. So we're going to have the bash
6:41:016 hours, 41 minutes, 1 secondtwo. So I past in the bash two. So this is for the bash two.
6:41:066 hours, 41 minutes, 6 secondsSo the bash contain the output from the bash two. Here we just confirm if the lines if it's an array then if the lines
6:41:166 hours, 41 minutes, 16 secondslength is equals to zero or don't have any content in the lines it will just return a two course type command else we
6:41:246 hours, 41 minutes, 24 secondsjust return a f grid to display the lines. So you can see we just do trading.
6:41:316 hours, 41 minutes, 31 secondsSo uh we have this. Now we're going to have for the G status comment. So the G
6:41:386 hours, 41 minutes, 38 secondsstatus. So I'm going to pass this here too. We can see um the G status. I'm just going to
6:41:476 hours, 41 minutes, 47 secondsf like this. And this is going to render the status here. So we're getting the status from the two inside the G.
6:41:566 hours, 41 minutes, 56 secondsthe G status. You can see status here.
6:41:596 hours, 41 minutes, 59 secondsSo now we going to have the comet to and this is a bit long. So I'll paste it
6:42:056 hours, 42 minutes, 5 secondshere and you can see so this is coming from the um output message brand time
6:42:136 hours, 42 minutes, 13 secondsstep addition deletion and then the component we're using is the comet component from AID AI element. So let me remove this.
6:42:336 hours, 42 minutes, 33 secondsSo so we adding colors for this for the addition and subtraction addition and deletion. Sorry. Now we going to have
6:42:416 hours, 42 minutes, 41 secondsthe push to. So I'm going to paste it here.
6:42:456 hours, 42 minutes, 45 secondsAnd we can see the push to is going to render. We're going to use a two call step and we're going to pass in detail.
6:42:516 hours, 42 minutes, 51 secondsSo if output or compare URL then we're going to show this link this um a tag
6:42:586 hours, 42 minutes, 58 secondsand then the user can click on it to view um the the branch or the repository.
6:43:056 hours, 43 minutes, 5 secondsThen lastly um I didn't handle this one GitHub I mean sorry the push the P out2
6:43:146 hours, 43 minutes, 14 secondsbut I'm just going to add a component here if you want to enable it. So I'm just going to comment it out. So, let me paste it here. But I'm going to comment
6:43:226 hours, 43 minutes, 22 secondsit out. I'm not going to use it, but I'm just going to leave it there for anyone that want to use it. So, I'm going to um
6:43:296 hours, 43 minutes, 29 secondsadd the last two content we're going to have is the web search to let me paste it here. And now you can see the web
6:43:376 hours, 43 minutes, 37 secondssearch to if it's an array of results, we're just going to use two step. And then we're going to pass in two of chain of tots.
6:43:496 hours, 43 minutes, 49 secondsand we're going to list all the um the result. So this is great. So now we have
6:43:576 hours, 43 minutes, 57 secondsall of this. We going to come down here and we're going to create a map like an object. And then this is going we're
6:44:056 hours, 44 minutes, 5 secondsgoing to uh we're going to get the the two the two names. So two grip and point
6:44:126 hours, 44 minutes, 12 secondsthem to their um component to their content. So I'm going to paste it here.
6:44:186 hours, 44 minutes, 18 secondsAnd you can see for P I just comment this out. And now we can use this now.
6:44:256 hours, 44 minutes, 25 secondsSo I'll copy this here. I'm going to say constant content is equals to content map. And we're going to pass in the type pass dot type.
6:44:396 hours, 44 minutes, 39 secondsAnd then we can say if if not uh let me make this upper case if not
6:44:496 hours, 44 minutes, 49 secondscontent let's return no.
6:44:586 hours, 44 minutes, 58 secondsSo now if so we're going to say if done we're going to show the content.
6:45:066 hours, 45 minutes, 6 secondsSo if running if running is false we going to then output the content. Now we're going to say if is error
6:45:156 hours, 45 minutes, 15 secondswe're going to use let's use the two call step two step
6:45:246 hours, 45 minutes, 24 secondsand we can pass in command I'll just say part dot error text
6:45:356 hours, 45 minutes, 35 secondsor something went wrong.
6:45:446 hours, 45 minutes, 44 secondsI can also change it to an error. I think this is better. An error occurred.
6:45:546 hours, 45 minutes, 54 secondsSo I think that is all. We can go back to the index.tx and let's import it.
6:46:026 hours, 46 minutes, 2 secondsSo now we are done with this um with the conversation um side the
6:46:096 hours, 46 minutes, 9 secondslisting of the the um messages. Now we're going to work on the chat impute.
6:46:146 hours, 46 minutes, 14 secondsSo I forgot to uh show the loading states here. So I'm going to scroll up here and I'm going to add constant is
6:46:226 hours, 46 minutes, 22 secondsloading is equals to status
6:46:296 hours, 46 minutes, 29 secondsis equals to submitted or status is equals to streaming.
6:46:416 hours, 46 minutes, 41 secondsSo let's go down to here and let's add it. So I'll paste it here. So we have
6:46:496 hours, 46 minutes, 49 secondsloading. If message is greater than zero then we're going to show the loading state and for the error we're going to show this and this is just to give um a
6:46:586 hours, 46 minutes, 58 secondsspace here this div. So I'm going to add the loader component. So inside the component I'm going to create
6:47:076 hours, 47 minutes, 7 secondsloader cx. So I'm going to paste a component here. So I'll paste this here.
6:47:156 hours, 47 minutes, 15 secondsSo this a loader component and for this load component if you go into the index CSS we also added a style here. If you
6:47:236 hours, 47 minutes, 23 secondscopy the um style from the GitHub if I scroll down you can see the bounce dot
6:47:296 hours, 47 minutes, 29 secondsthis was a style that u I added and you can see the component
6:47:356 hours, 47 minutes, 35 secondstoo. So this is dot loader. So let me go ahead and import it.
6:47:486 hours, 47 minutes, 48 secondsSo now let's go ahead and create a component for the chart impute. So we're going to say chart impute.
6:47:596 hours, 47 minutes, 59 secondsThen we're going to pass in the prop like the status and branch name the P ready state. I'm going to just pass everything like this.
6:48:106 hours, 48 minutes, 10 secondsAnd let me check this properly. So inside
6:48:176 hours, 48 minutes, 17 secondswe are ready and also
6:48:246 hours, 48 minutes, 24 secondsthe um is fetching repo. So I think we added an endpoint to fetch repository here.
6:48:326 hours, 48 minutes, 32 secondsSo here it is.
6:48:386 hours, 48 minutes, 38 secondsSo, okay, it's pending. So, let me just copy this.
6:48:456 hours, 48 minutes, 45 secondsLet me change it to is fing instead of um expanding. Oh, let me leave it like that. So, I'm just going to scroll down
6:48:536 hours, 48 minutes, 53 secondsback to the bottom and I'm just going to replace it
6:48:596 hours, 48 minutes, 59 secondslike this. So for the sandbox, I'm just going to just have
6:49:076 hours, 49 minutes, 7 secondsSo this is not going to do anything. I'm just going to just add it there. So the user know that this is um in a sandbox
6:49:146 hours, 49 minutes, 14 secondsis working on. I'm just going to leave it there, but you can remove it if you want. Then later on, we're going to create we're going to add a method to
6:49:236 hours, 49 minutes, 23 secondscreate PL. So I say create PL. I'll just add it for now.
6:49:316 hours, 49 minutes, 31 secondsAnd then we're going to so pass in is creating PL.
6:49:416 hours, 49 minutes, 41 secondsAnd I'll just say this to false.
6:49:456 hours, 49 minutes, 45 secondsSo I'll save this. Now let's go ahead and create a chart impute. So I'll say chart impute. TXX.
6:49:556 hours, 49 minutes, 55 secondsSo R A S C E
6:50:046 hours, 50 minutes, 4 secondsand let's remove this. So add the types here and let me import all of this
6:50:126 hours, 50 minutes, 12 secondsfrom message and we can see it's creating
6:50:206 hours, 50 minutes, 20 secondsPR. So let's pass in. So I'll copy this impute um impute prop. I'll pass it
6:50:286 hours, 50 minutes, 28 secondshere. I'm going to pass all the state sorry all the props. I think I made a mistake on create PR. So I'll pass this here.
6:50:406 hours, 50 minutes, 40 secondsAnd now we can go ahead and create. So the first thing I'm going to do I'm going to say constant is repo. So we
6:50:476 hours, 50 minutes, 47 secondsneed to lock the repo. um the se the select option where users select the rep. So if the user selected a repo so
6:50:556 hours, 50 minutes, 55 secondsthey can create select a different repository. So instead we're going to just lock or disable the select um the
6:51:046 hours, 51 minutes, 4 secondsselect components which is going to list all the repository. So I'm going to say is
6:51:116 hours, 51 minutes, 11 secondsI'll say is select lock is equals to is fetching repository or has messages.
6:51:256 hours, 51 minutes, 25 secondsSo if has message we're just going to disable the um select component. So I'm going to say rep label
6:51:356 hours, 51 minutes, 35 secondsis equals to repository repo options dot find
6:51:426 hours, 51 minutes, 42 secondsoption option do
6:51:546 hours, 51 minutes, 54 secondsis equals to repo do and then we can get labor.
6:52:046 hours, 52 minutes, 4 secondsThen we have constant handle submit
6:52:116 hours, 52 minutes, 11 secondshandle click. Let's handle click. Um uh and click
6:52:226 hours, 52 minutes, 22 secondssay message which is type of prompt
6:52:326 hours, 52 minutes, 32 secondsprompt message impute message and then let's return this and I'm just going to turn.
6:52:436 hours, 52 minutes, 43 secondsUm, unsubmit message
6:52:596 hours, 52 minutes, 59 secondsand prompt submit.
6:53:026 hours, 53 minutes, 2 secondsThis is best. So here we're going to have a class name absolute
6:53:106 hours, 53 minutes, 10 secondsinsert x0 bottom zero said index
6:53:186 hours, 53 minutes, 18 seconds20 I'll say shrink zero and let's have a div again
6:53:256 hours, 53 minutes, 25 secondslet's give this a class name um max so I'm going to give maximum max with 4 xl
6:53:356 hours, 53 minutes, 35 secondsX0 and I'm going to also add a widthful
6:53:436 hours, 53 minutes, 43 secondsand padding um B4 and I'm going to add a backrop of small.
6:53:536 hours, 53 minutes, 53 secondsSo now we are going to say is GitHub connected
6:54:016 hours, 54 minutes, 1 secondand branch name and ripple.
6:54:096 hours, 54 minutes, 9 secondsAnd so we're going to have a div.
6:54:186 hours, 54 minutes, 18 secondsWe're going to give this a class name.
6:54:226 hours, 54 minutes, 22 secondsSo margin bottom two flex first item center justify between gap three rounded to excel border border border bg
6:54:306 hours, 54 minutes, 30 secondstransparent px4 py 1.5 and shadow small and then we're going to have another div
6:54:396 hours, 54 minutes, 39 secondsand we'll give this a class name of flex um minimum with zero center gap
6:54:486 hours, 54 minutes, 48 secondsthree and then we're going to have this here we're going to show the branch. So I'm going to import this icon get branch and then the branch name.
6:54:586 hours, 54 minutes, 58 secondsThen below here we're going to say if created be our URL we're going to show a
6:55:056 hours, 55 minutes, 5 secondsbutton. So let's import button from UI but and let's give this a class name.
6:55:126 hours, 55 minutes, 12 secondsSo I'm going to set this to try first.
6:55:156 hours, 55 minutes, 15 secondsUh let me give it a class name. Yeah, class name. I'm going to set the um background color to black.
6:55:276 hours, 55 minutes, 27 secondsI'll set opacity of 0.7.
6:55:306 hours, 55 minutes, 30 secondsAnd then I'm going to set the color to text white.
6:55:366 hours, 55 minutes, 36 secondsAnd and uh for the button, we going to add this here. And I'm going to import this
6:55:456 hours, 55 minutes, 45 secondsicon. So if there's a PR URL, let's say the user has clicked on the um button to
6:55:526 hours, 55 minutes, 52 secondscreate a PR, we're going to then show the view um PR. So we're going to say else.
6:56:016 hours, 56 minutes, 1 secondAnd now we're going to have a button to create the PL. So I'm going to give this um a class name too. It's going to be
6:56:106 hours, 56 minutes, 10 secondsthe same thing. BG black then 70 and text
6:56:186 hours, 56 minutes, 18 secondswhite and then I'm going to set um on click
6:56:256 hours, 56 minutes, 25 secondshere we're going to set this on create PL and disabled is going to be
6:56:346 hours, 56 minutes, 34 secondsis creating PL or not PL ready and then inside the button I'm going to
6:56:436 hours, 56 minutes, 43 secondspaste this I will import spinner so if create else just say un on
6:56:516 hours, 56 minutes, 51 secondsunavailable and now we are done with this now let's import the prompt impute
6:57:056 hours, 57 minutes, 5 secondsprompt impute so let me move this inside there.
6:57:166 hours, 57 minutes, 16 secondsOkay, I think I made a mistake. So, let me move it inside here like this. So, this is the correct way. And now we say prompt impute.
6:57:296 hours, 57 minutes, 29 secondsWe're going to pass in.
6:57:326 hours, 57 minutes, 32 secondsSo, I'll give this a class name. So if you don't have class name in your own so just make sure you replace the prompt impute with the one you would copy from
6:57:416 hours, 57 minutes, 41 secondsGitHub. So I've already updated my prompt impute. So I'm going to paste this here.
6:57:486 hours, 57 minutes, 48 secondsSo let me paste the class name. So the class we're going to set border adding
6:57:546 hours, 57 minutes, 54 secondsXO BG primary sorry BG background then shadow and rounded DXL and then we're
6:58:016 hours, 58 minutes, 1 secondgoing to set on submit I'll say handle prompt submit and then we can import the prompt impute body.
6:58:156 hours, 58 minutes, 15 secondsSo we're going to pass in the prompt text serial. So let's import this impute um beria. So now below here we're going
6:58:236 hours, 58 minutes, 23 secondsto then import prompt impute
6:58:316 hours, 58 minutes, 31 secondsand I'm going to give this a class name margin top three flex item center tree.
6:58:426 hours, 58 minutes, 42 secondsSo here we're going to say uh we're going to import prompt prompt impute tools.
6:58:536 hours, 58 minutes, 53 secondsI'll say if and if kit is connected then I'm going to say has we have
6:59:026 hours, 59 minutes, 2 secondsmessage then I'm going to um show a button and let me move this
6:59:196 hours, 59 minutes, 19 secondsSo instead of showing the select option, we are going to then show the button that will display the name of the repository since we already have um
6:59:286 hours, 59 minutes, 28 secondssince we already have um um the GitHub is already connected.
6:59:346 hours, 59 minutes, 34 secondsBut if the GitHub is not connected, we are going to then show uh let me do this here.
6:59:426 hours, 59 minutes, 42 secondsand then does not have any messages. So I'm going to then show we're going to import prompt impute
6:59:516 hours, 59 minutes, 51 secondsprompt impute select and this is we're going to pass in the value and then on value change.
7:00:047 hours, 4 secondsSo let me quickly import this GitHub logo. So I'm going to add it inside the asset. So I've past it here and I'm
7:00:117 hours, 11 secondsgoing to go ahead and import it. So let me import it and the error should stop.
7:00:217 hours, 21 secondsSo let's pass in um the prompt impute select trigger.
7:00:367 hours, 36 secondsThen we're going to pass this here. So I'm going to import prompt input select
7:00:437 hours, 43 secondsvalue. So we're going to say if this is loading, we just show a spinner and else we just show um GitHub logo and we just
7:00:537 hours, 53 secondsshow we have the prompt impute select value. So I'm going to say add in
7:00:597 hours, 59 secondsremember we added this is text lock. So I'm going to disable this here. So I'm going to say um I'm passing this class
7:01:087 hours, 1 minute, 8 secondsname here. So I'm going to say if is select lock not allowed or positive 60
7:01:187 hours, 1 minute, 18 secondslike this. Then I add in add in this.
7:01:307 hours, 1 minute, 30 secondsSo now let's import um select impute compon and content. It's a prompt impute
7:01:397 hours, 1 minute, 39 secondsselect content.
7:01:427 hours, 1 minute, 42 secondsSo I'm going to give this a class name shadow large
7:01:507 hours, 1 minute, 50 secondsand then we're going to look through the option the repo options. So I'll pass this here. I'll say if option is equals
7:01:587 hours, 1 minute, 58 secondsto zero and then we're going to say no repository found and we can see here we say um we added a element div here to
7:02:087 hours, 2 minutes, 8 secondsshow all repositories and then we're going to go through the um repository options and we um have the option label
7:02:177 hours, 2 minutes, 17 secondshere and we have some class here we pass in the key and the value. So let's import the prompt impure select items
7:02:257 hours, 2 minutes, 25 secondsand then then here we're going to have a button which the user is going to click to connect the GitHub account. So let's
7:02:337 hours, 2 minutes, 33 secondsmake body variant sorry variant
7:02:437 hours, 2 minutes, 43 secondsoutline and then we can say on click and we can have a method there for it.
7:02:557 hours, 2 minutes, 55 secondsWe can say constant handle handle connect
7:03:077 hours, 3 minutes, 7 secondsAnd then we can just add in let's add in async here.
7:03:147 hours, 3 minutes, 14 secondsSo let's go to the API leave folder API text. Okay, we've already added connect
7:03:227 hours, 3 minutes, 22 secondsin GitHub. So we can go back and let's pass it here. Say await.
7:03:307 hours, 3 minutes, 30 secondsLet's import GitHub connect.
7:03:357 hours, 3 minutes, 35 secondsAnd this is going to return a URL. It's a constant is equals to URL.
7:03:447 hours, 3 minutes, 44 secondsAnd then we're going to do window location sorry
7:03:517 hours, 3 minutes, 51 secondslocation is equals to URL. So, let's copy handle connect and then we're going to pass it.
7:04:037 hours, 4 minutes, 3 secondsLet me scroll down. Pass it here. And then I'm going to just pass this here.
7:04:127 hours, 4 minutes, 12 secondsSo, let me also add type button. So, I'll copy this two.
7:04:217 hours, 4 minutes, 21 secondsYeah, we added type button here too.
7:04:257 hours, 4 minutes, 25 secondsSo what we're going to have here is for the sandbox. So you can skip this. This is not compulsory. I'll just paste it
7:04:327 hours, 4 minutes, 32 secondshere. Sandbox options. And lastly, we're going to have let me format this.
7:04:407 hours, 4 minutes, 40 secondsUm the So we're going to do that here.
7:04:437 hours, 4 minutes, 43 secondsThe submit button. So let's import prompt impute submit.
7:04:527 hours, 4 minutes, 52 secondsI will pass in the unstop and the status. So now we are done with this. So we can go into the index.txs and let's import this.
7:05:057 hours, 5 minutes, 5 secondsSo I think we are done with this. So let's go into home index.tx and everything should be fine. So let me
7:05:147 hours, 5 minutes, 14 secondscheck um inside the chat index cxs and confirm everything.
7:05:207 hours, 5 minutes, 20 secondsYeah, I think everything is fine. So, we can go ahead and test it out. So, let's check it. Let me check my server is
7:05:277 hours, 5 minutes, 27 secondsrunning. So let me put this let me let me run the server cd client
7:05:377 hours, 5 minutes, 37 secondsmpm rundev and then let me see the back end
7:05:497 hours, 5 minutes, 49 secondsmpm rundev. So the backing server is running and the client is running. So let's go to the um to the client side
7:05:577 hours, 5 minutes, 57 secondsand then we can see this now we can see all the repositories. So let me click here.
7:06:037 hours, 6 minutes, 3 secondsLet me try and reload this for some reason this is not open.
7:06:127 hours, 6 minutes, 12 secondsThis is opening. This is opening. So let me go ahead and check it out. So I go back to the code and then let me go to
7:06:207 hours, 6 minutes, 20 secondsthe chat and build and let me see.
7:06:277 hours, 6 minutes, 27 secondsSo I think I found the issue. The issue is coming from the endpoint. So let's go into index. CXX
7:06:357 hours, 6 minutes, 35 secondsand then I think this is where we fetch in the repository. Let's go into GitHub repos.
7:06:427 hours, 6 minutes, 42 secondsum this is going to be the problem again we had with um I think the endpoint to fetch all sessions. So I'll go back to
7:06:507 hours, 6 minutes, 50 secondsthe back end and then inside the lc inside the controller github controller
7:06:587 hours, 6 minutes, 58 secondsand where we have the repo. So I just I'll just structure data here and let me just pass a message.
7:07:107 hours, 7 minutes, 10 secondsUm let me just leave the data. I'll just remove this and pass data.
7:07:217 hours, 7 minutes, 21 secondsSo save this and the back end should be running. So this
7:07:287 hours, 7 minutes, 28 secondsis running now. Let's go to the client side and let me click now.
7:07:367 hours, 7 minutes, 36 secondsOkay. Now we can see the repository.
7:07:387 hours, 7 minutes, 38 secondsYou can see all the repository. So I can click on this now.
7:07:437 hours, 7 minutes, 43 secondsSo let me pick this repo. So before we go ahead and test this out, I still need us to fix some things. So let's go back
7:07:497 hours, 7 minutes, 49 secondsto the code. So um first of all, make sure you update changes. If has a message, you just want to reduce the um
7:07:587 hours, 7 minutes, 58 secondsthe width of the impute. Then we should go back to the back end. So if you go to
7:08:057 hours, 8 minutes, 5 secondsthe back end inside the index tx, see I commented this out because the streaming was not working. So I had to comment
7:08:137 hours, 8 minutes, 13 secondsthis out to confirm and the stream started working. So just comment this out. And once you do that, I think uh
7:08:207 hours, 8 minutes, 20 secondsthat is all. We can go ahead and test it out. So let's go make sure your server is running.
7:08:297 hours, 8 minutes, 29 secondsLet me check your server is running. And then let's go back to browser and let's select a project. So I
7:08:377 hours, 8 minutes, 37 secondsjust say which framework framework
7:08:477 hours, 8 minutes, 47 secondswas used in this project and click on enter and now you can see
7:08:557 hours, 8 minutes, 55 secondsthe prompt has increased because we have message um in this session. So let's wait for this now. Now we can see the
7:09:037 hours, 9 minutes, 3 secondsbranch name has been generated and we can see the name too and the session name. Now we can see that this is
7:09:097 hours, 9 minutes, 9 secondsthinking. So it's going to read the file and now that's saying that um we are
7:09:167 hours, 9 minutes, 16 secondsusing react and doing CSS. So I can just ask you to
7:09:237 hours, 9 minutes, 23 secondsedit a file. So say change change change it see
7:09:297 hours, 9 minutes, 29 secondsum of this project uh pick any one of pick
7:09:407 hours, 9 minutes, 40 secondsany one you prefer
7:09:487 hours, 9 minutes, 48 secondsI think this is fine let's just ask to do this so click on send. So before I click on send, if you
7:09:567 hours, 9 minutes, 56 secondshave any issue, let me inspect this um developer too. So if I click on send,
7:10:077 hours, 10 minutes, 7 secondsclick on send. Now if I click on this and check the period, you can see the default branch has not been passed. So
7:10:137 hours, 10 minutes, 13 secondsmake sure you go to the um validator and set the default branch optional. So I
7:10:207 hours, 10 minutes, 20 secondsremove this. And now we can see that this has list all the project.
7:10:277 hours, 10 minutes, 27 secondsAnd now let's wait for it.
7:10:337 hours, 10 minutes, 33 secondsSo it says going to change the team to ocean blue and midnight. So it's editing the index of CSS.
7:10:427 hours, 10 minutes, 42 secondsAnd let's wait for it.
7:10:467 hours, 10 minutes, 46 secondsAnd now we can see the div component. As you can see that it's showing
7:10:547 hours, 10 minutes, 54 secondsproperly. So if I scroll to the bottom now. So it's also editing the TS CSS um table CSS config.
7:11:047 hours, 11 minutes, 4 secondsAnd now it's editing the app.jx.
7:11:107 hours, 11 minutes, 10 secondsAnd so let's see.
7:11:197 hours, 11 minutes, 19 secondsSo now we can see it want to edit enough nav.
7:11:377 hours, 11 minutes, 37 secondsSo let us edit.
7:11:457 hours, 11 minutes, 45 secondsSo it's remaining some of the components the future and the pricing components.
7:11:497 hours, 11 minutes, 49 secondsLet us edit the feature. Now you want to edit the pricing. So now
7:11:587 hours, 11 minutes, 58 secondsso it's remaining the two other components testimonial and footer. So it is done with this one.
7:12:067 hours, 12 minutes, 6 secondsSo I think this is the last one. So now it want to build and you notice that there's no fit install. It's going to
7:12:147 hours, 12 minutes, 14 secondsinstall the dependencies. So that is what you want to do. It want to use the bash command. So it has installed this.
7:12:227 hours, 12 minutes, 22 secondsNow it's running build and it does build the project. Now it's going to um now we can see the status and then it's going to commit changes.
7:12:347 hours, 12 minutes, 34 secondsSo now you can see it has generated the um you can see gened the title the commit title. Now it's going to push the
7:12:417 hours, 12 minutes, 41 secondschanges and once it push the changes we should see this button is enabled now. So this is great.
7:12:487 hours, 12 minutes, 48 secondsSo now we can click here to view. So it has stop here. So let's click on the view changes
7:13:007 hours, 13 minutesand now we can see the branch here that was generated.
7:13:047 hours, 13 minutes, 4 secondsSo guys this is great. So let's go ahead and um implement the single session page. So if I reload this page now, if
7:13:147 hours, 13 minutes, 14 secondsyou see we're going to have a plan screen. So let's go ahead and implement this uh page. Then we're going to then
7:13:217 hours, 13 minutes, 21 secondsalso work on the create PL implement the create PL um or integrate the uh create PL endpoint. So let's go ahead and do
Chapter 14: Frontend Single Session
7:13:307 hours, 13 minutes, 30 secondsthat. In this chapter, we're going to start working on the single session page. So let's add the end point first.
7:13:367 hours, 13 minutes, 36 secondsSo I'm going to add the end point for So I've already added the endpoint for pull request. So I'm going to also add for um
7:13:447 hours, 13 minutes, 44 secondslog out and the single session. So we can do everything at once. So this is a log out endpoint. So I'll move it to the
7:13:517 hours, 13 minutes, 51 secondslast and then I'm going to import this
7:13:597 hours, 13 minutes, 59 secondsand then we can use this now. So we're going to implement the get single session uh endpoint and the create pull
7:14:067 hours, 14 minutes, 6 secondsrequest. So let's quickly start with this one. So I'll go to let's go to the page
7:14:147 hours, 14 minutes, 14 secondshome. So now home session index and let's import
7:14:217 hours, 14 minutes, 21 secondsuh chat interface
7:14:297 hours, 14 minutes, 29 secondsand let's get this log id from the URL we say equals to use param
7:14:387 hours, 14 minutes, 38 secondsand then we can see sl ID. So let's make sure is what we have here inside rout ID. Okay, you see I made a mistake.
7:14:527 hours, 14 minutes, 52 secondsSo let me copy the one I have here. I'll just pass it here.
7:15:007 hours, 15 minutesSo let's we're going to call the so I'm going to the end point. I'm going to import use query and then get session by slope.
7:15:127 hours, 15 minutes, 12 secondsAnd then we're going to say if is pending or not data
7:15:207 hours, 15 minutes, 20 secondsor let's remove let's say if is um sorry if is pending not this
7:15:277 hours, 15 minutes, 27 secondsthen I'm going to return this and then we can just say if not data
7:15:357 hours, 15 minutes, 35 secondsand not is pending Then we can just return
7:15:497 hours, 15 minutes, 49 secondsand say session not found.
7:15:557 hours, 15 minutes, 55 secondsSo let's give this a class name.
7:16:017 hours, 16 minutes, 1 secondLet's say width full height full and then overflow hidden
7:16:127 hours, 16 minutes, 12 secondsand then we're going to pass in all the props. So I'm going to just paste this here. So we're going to set key using
7:16:187 hours, 16 minutes, 18 secondsthe session snug ID. We set a section to true initial message messages data
7:16:247 hours, 16 minutes, 24 secondsmessages session title sn ID repository URL default branch and branch name. So
7:16:347 hours, 16 minutes, 34 secondslet me also check the back end where return the response. So I'll go to controller session.
7:16:437 hours, 16 minutes, 43 secondsLet's go to where we have single session and then we have data here. So let me
7:16:517 hours, 16 minutes, 51 secondsjust structure this or you can just um we can add it. We can
7:16:597 hours, 16 minutes, 59 secondsadd data to this.
7:17:037 hours, 17 minutes, 3 secondsIf I add data here this train an error sorry. Yeah,
7:17:157 hours, 17 minutes, 15 secondssingle session is returned. Okay, I think this is fine. So, I'm just going to leave it like this. So, let's go back here and I think we should go ahead and
7:17:237 hours, 17 minutes, 23 secondstest it out. So, let's go back to the browser. So, I think something is wrong.
7:17:337 hours, 17 minutes, 33 secondsSo, let me go and fix it. I think there's no issue. Let me I should reload the page. So, let me go back. Okay, now
7:17:407 hours, 17 minutes, 40 secondsyou can see it has come up. So we can see the messages here. So guys, this is
7:17:477 hours, 17 minutes, 47 secondsgreat. So I can click on this one session and we can also see this one too. So great. This is great. So let's
7:17:547 hours, 17 minutes, 54 secondsgo ahead to create the um p request. So go back to the code and then let me collapse everything.
7:18:077 hours, 18 minutes, 7 secondsSo inside inside the uh component inside the component chat index.tx.
7:18:187 hours, 18 minutes, 18 secondsSo I'm going to add the endpoint here the motation. So I'll paste it here and I'm going to import use motation hook
7:18:267 hours, 18 minutes, 26 secondsfrom tquery and I'm going to import the create session p request from the API in the li folder. And now we have passed in
7:18:337 hours, 18 minutes, 33 secondsthe payload as log and also the title and body. And if we get any response we going to add in the URL to the state.
7:18:447 hours, 18 minutes, 44 secondsNow we can create a method for this. So I can do that here. So let me add it here. So handle create P. And now I can
7:18:527 hours, 18 minutes, 52 secondsscroll down to the bottom and pass this here.
7:18:597 hours, 18 minutes, 59 secondsSo secret create we are mutation is pending.
7:19:067 hours, 19 minutes, 6 secondsSo we are done with this. So the last thing we're going to do before we go before we end this chapter let's go to
7:19:137 hours, 19 minutes, 13 secondscomponent sidebar and we need to add in the logout. So I think it's inside index.tx.
7:19:237 hours, 19 minutes, 23 secondsLet me add it here. So let's import constants.
7:19:277 hours, 19 minutes, 27 secondsUm let's get data uh data
7:19:357 hours, 19 minutes, 35 secondsis equals to use user and let's get constant uh sorry query
7:19:447 hours, 19 minutes, 44 secondsclient is equals to use query
7:19:527 hours, 19 minutes, 52 secondsclient and then we're going to get navigate is equals to use
7:20:017 hours, 20 minutes, 1 secondnavigate and then we're going to create the motation for the logout. So I'm going to
7:20:087 hours, 20 minutes, 8 secondspaste them here and the first thing you can see here is the use mutation hook.
7:20:157 hours, 20 minutes, 15 secondsLet's import it. The log out mutation function import it to and now once we log out we're just going to remove all
7:20:237 hours, 20 minutes, 23 secondsthese queries and remove queries. And then I'm going to we're going to get data
7:20:307 hours, 20 minutes, 30 secondsdot user. And then we have the initial data initial. So we're using user here.
7:20:377 hours, 20 minutes, 37 secondsAnd I'm going to scroll down to where we have sidebar content. And I'm going to just paste in this here.
7:20:477 hours, 20 minutes, 47 secondsSo let me uh yeah. So the sidebar footer. So let me import it.
7:20:557 hours, 20 minutes, 55 secondsImport cm.
7:20:587 hours, 20 minutes, 58 secondsSo import avatar from your avatar image. Avatar image
7:21:057 hours, 21 minutes, 5 secondsand fallback and then let me import button
7:21:127 hours, 21 minutes, 12 secondsand then log out component a log out icon. So I don't think we created this um module to so let's do that. So inside
7:21:227 hours, 21 minutes, 22 secondsthe component I'm going to do it here modx.
7:21:337 hours, 21 minutes, 33 secondsSo I've paste it here. It's very simple component. So we can import it now.
7:21:407 hours, 21 minutes, 40 secondsSo let's import it.
7:21:447 hours, 21 minutes, 44 secondsSo that's it for the footer. So the last thing we're going to create is the search. So I'm going to add another use
7:21:527 hours, 21 minutes, 52 secondsstate hook here. So So I'm going to pass it here and I'm going to import use search open and I'm going to pass this
7:22:027 hours, 22 minutes, 2 secondsto the navbar. So I'm going to say on search
7:22:107 hours, 22 minutes, 10 secondson search click is going to be equals to
7:22:177 hours, 22 minutes, 17 secondsset search open to true
7:22:247 hours, 22 minutes, 24 secondsand then let's go into here. Let's pass it here.
7:22:397 hours, 22 minutes, 39 secondsSo, I'm going to add it to this button and click um on search.
7:22:557 hours, 22 minutes, 55 secondsSo, let's go back. So, we're going to add a component here, the search. So I'm going to just pass it here. And let's
7:23:027 hours, 23 minutes, 2 secondscreate this component inside here. Let's say search dialog txx.
7:23:147 hours, 23 minutes, 14 secondsWe can call it session search dialog instead.
7:23:247 hours, 23 minutes, 24 secondsAnd I'm going to just paste in the component. So you can just copy this from the GitHub. So I'll paste this here and let's save this.
7:23:357 hours, 23 minutes, 35 secondsSo okay, I need to create add this um API. So I'll go to lib API.tx
7:23:447 hours, 23 minutes, 44 secondsand I'm going to just add it. Let me add it here. So I'm going to paste it here.
7:23:497 hours, 23 minutes, 49 secondsAnd this is it. Search. So I can go back now and let me import session search dialog.
7:23:597 hours, 23 minutes, 59 secondsAnd this is it. So guys, we are done with this. So let's go and test it out. So make sure your server is running. Let's go to the browser.
7:24:087 hours, 24 minutes, 8 secondsAnd now we can click on the search bar and you can see this. So you can search for list and this is going to search. So for the
7:24:167 hours, 24 minutes, 16 secondsPL, I'm just going to tell it to just edit a single file so we can test it out. So, I'm looking for something to
7:24:237 hours, 24 minutes, 23 secondstell to change. Let me go to this. Let me go to the component.
7:24:327 hours, 24 minutes, 32 secondsLet's say we want to change only the the title. So, let me find for where it had the title.
7:24:477 hours, 24 minutes, 47 secondsBuild product with your team. So I'm going to say build product. Let's change it to build product with
7:24:587 hours, 24 minutes, 58 secondsor let me just come over here and change this and clare is the modern platform for Zim. So I'll copy this.
7:25:087 hours, 25 minutes, 8 secondsI'm going to just say uh update the hero
7:25:147 hours, 25 minutes, 14 secondsum component um with a subtitle or paragraph.
7:25:297 hours, 25 minutes, 29 secondsSo I'm going to just pass it here. So instead of clair is a modern platform for collaborator. So I've already said
7:25:377 hours, 25 minutes, 37 secondsum update the session subtitle component to this. So let's click on send.
7:25:467 hours, 25 minutes, 46 secondsAnd now it is working. So let's wait for it.
7:25:537 hours, 25 minutes, 53 secondsSo now you can see it's changing.
7:25:577 hours, 25 minutes, 57 secondsSo it's going to edit the hero component.
7:26:077 hours, 26 minutes, 7 secondsand let's wait for it. So now you can see it has updated the file and it's going to build the project
7:26:177 hours, 26 minutes, 17 secondsand then so it has commit changes and it does push. So now we can create the P.
7:26:307 hours, 26 minutes, 30 secondsSo let's click on create P. So I'll click on the create PR now. So creating PR.
7:26:397 hours, 26 minutes, 39 secondsSo something failed again. So let's check.
7:26:537 hours, 26 minutes, 53 secondsSo let's see.
7:26:587 hours, 26 minutes, 58 secondsInternet error. So let's go back and check this.
7:27:077 hours, 27 minutes, 7 secondsLet me check the back end.
7:27:127 hours, 27 minutes, 12 secondsSo we didn't console the error. So I need to always console the error.
7:27:407 hours, 27 minutes, 40 secondsSo let's go into let me go into controller session
7:27:497 hours, 27 minutes, 49 secondscreate p request pass in log id and the title. So let's go into create request service.
7:28:007 hours, 28 minutesSo get box city cd into it and create pull request. So let me try it again so you can see the error. So I'll go back
7:28:087 hours, 28 minutes, 8 secondsto the client side and let me click on it.
7:28:227 hours, 28 minutes, 22 secondsSo let's go back and check.
7:28:287 hours, 28 minutes, 28 secondssays error occ
7:28:487 hours, 28 minutes, 48 secondsuh let's console the clock the session let me console of the box
7:28:577 hours, 28 minutes, 57 secondsID and a session JSON stringify.
7:29:077 hours, 29 minutes, 7 secondsSo like this. So let me save this and see why it's not creating the
7:29:147 hours, 29 minutes, 14 secondsrequest. So let's wait. So let's go to the browser again and let me click on it again.
7:29:267 hours, 29 minutes, 26 secondsSo let's go back to code and then we can see the response. So we
7:29:337 hours, 29 minutes, 33 secondscan see default branch. So we have the default branch here. But this is the filling.
7:29:427 hours, 29 minutes, 42 secondsWe have the default branch.
7:29:457 hours, 29 minutes, 45 secondsWe have the box ID and the box ID is returning. We have the box ID.
7:29:567 hours, 29 minutes, 56 secondsSo you see because of the branch
7:30:067 hours, 30 minutes, 6 secondsto console this console this to check what was the issue.
7:30:127 hours, 30 minutes, 12 secondsSo I think um so you can see the remote branch here base branch
7:30:217 hours, 30 minutes, 21 secondsand what what I'm going to do let me try and um make a push again. So what I'm going to do I'm going to come down here
7:30:307 hours, 30 minutes, 30 secondsand I'm going to just run this. So just to test let's go to the browser
7:30:377 hours, 30 minutes, 37 secondsand let me try and click on create pull request.
7:30:417 hours, 30 minutes, 41 secondsLet's see.
7:30:527 hours, 30 minutes, 52 secondsSo, it's still filled. So, let's go back to code.
7:31:037 hours, 31 minutes, 3 secondsIt's still filling. So, I just tried it again. and it went.
7:31:117 hours, 31 minutes, 11 secondsSo I just comment out this and save changes. And if I go to the browser now,
7:31:187 hours, 31 minutes, 18 secondsyou can see it. I just click on it now and it went through.
7:31:257 hours, 31 minutes, 25 secondsSo I think it was because maybe we have some other um mismatch com. So let's click on view PR.
7:31:377 hours, 31 minutes, 37 secondsAnd this has work. We can see the PR. So it merge two commit into it.
7:31:467 hours, 31 minutes, 46 secondsSo this is working fine. So we can just we can test it with a brand new with a different um repo that is not changes.
7:31:547 hours, 31 minutes, 54 secondsSo but we can still leave the push there just in case. But let me just comment it out.
7:32:027 hours, 32 minutes, 2 secondsSo you can leave this if you want. So now I think that is all for this tutorial. Let's go ahead and deploy this application.
7:32:127 hours, 32 minutes, 12 secondsSo let's go ahead and do that. In this chapter, we going to go ahead and deploy the entire app. So we're going to you we're going to deploy this app to
Chapter 15: Deployment
7:32:207 hours, 32 minutes, 20 secondsrender. And the way we're going to deploy it, we're going to use the back end to serve the client side. So we are going to go into the src inside index.tx.
7:32:317 hours, 32 minutes, 31 secondsAnd at the top here I'm going to import let me import um
7:32:377 hours, 32 minutes, 37 secondspart from part and then I'm going to scroll down to the
7:32:457 hours, 32 minutes, 45 secondsbottom here and where we have this app use we are going to we going to check if
7:32:527 hours, 32 minutes, 52 secondsEMV so let's say EMV config node EMV is equals to production we going to get a part to client the client folder / this.
7:33:037 hours, 33 minutes, 3 secondsSo we are going to build the client then we going to serve the client uh we're going to use um express static passing the path and then we're going to serve.
7:33:147 hours, 33 minutes, 14 secondsSo what I'm going to do I'm going to change this to health.
7:33:187 hours, 33 minutes, 18 secondsSo so this is going to serve it on slash. You can see it's going to save it on slash. So this is going to be / health. So now we're going to go ahead
7:33:277 hours, 33 minutes, 27 secondsand push this. So I'm going to push this to the repository.
7:33:317 hours, 33 minutes, 31 secondsSo I'm going to add this. Let me just send you update and just push this to main.
7:33:397 hours, 33 minutes, 39 secondsSo to test it out that everything is working fine. What I'm going to I'm going to build the client side. So let's go see the into client and do mpm run build.
7:33:537 hours, 33 minutes, 53 secondsAnd this should build the client side for us.
7:33:577 hours, 33 minutes, 57 secondsSo we're having an error. So what will happen is that inside the U TX
7:34:057 hours, 34 minutes, 5 secondsthink ts app script error. So I'm going to just copy this here. You can see this.
7:34:137 hours, 34 minutes, 13 secondsLet's just copy this and let me add it here.
7:34:227 hours, 34 minutes, 22 secondsI think this should solve the error.
7:34:317 hours, 34 minutes, 31 secondsSo let me wait for it. Yeah.
7:34:477 hours, 34 minutes, 47 secondsSo I just add this and the T script should stop. So I'm going to just run the build now.
7:34:547 hours, 34 minutes, 54 secondsSo let me run this mpm run build and you can see that it's going to go through.
7:35:037 hours, 35 minutes, 3 secondsSo let's wait for it.
7:35:067 hours, 35 minutes, 6 secondsSo it is done. Now we can go to the back end now and we should go to EMV. The EMV I'll change this to production.
7:35:187 hours, 35 minutes, 18 secondssave the and then I'm just going to let me see the out of see the out of client
7:35:267 hours, 35 minutes, 26 secondsI'll into back end let me stop the server
7:35:337 hours, 35 minutes, 33 secondsand then let me do MP and run build and now we can see it has build um it
7:35:437 hours, 35 minutes, 43 secondshas view this so we can just see the into just mpm on mpn start
7:35:557 hours, 35 minutes, 55 secondsand let's wait for it. So now we can see it's connected. So we can go to the client side and let me just open let's go to local
7:36:037 hours, 36 minutes, 3 secondshost 8000.
7:36:107 hours, 36 minutes, 10 secondsSo, I think it's not going to um Okay, we didn't see the name. There's no usern. Let's check profile.
7:36:247 hours, 36 minutes, 24 secondsOkay, we're getting the content. For some reason, we're not seeing the name of the user here. So, let me go and fix
7:36:307 hours, 36 minutes, 30 secondsit. So, we're getting it. So, we can click on new, click on search, and I think everything is working fine.
7:36:397 hours, 36 minutes, 39 secondsSo I think this is working fine. So we can go back and then let's go to the client side and fix it.
7:36:497 hours, 36 minutes, 49 secondsSo inside the component then inside sidebar index cx.
7:36:597 hours, 36 minutes, 59 secondsSo let me see data dot user the footer.
7:37:117 hours, 37 minutes, 11 secondsOkay. If expanded user name user email.
7:37:167 hours, 37 minutes, 16 secondsSo let me console lock user. Console.lo user.
7:37:257 hours, 37 minutes, 25 secondsI'll save this. I'll go back to the browser and let me consum this.
7:37:347 hours, 37 minutes, 34 secondsSo I'll open the dev to click on console log.
7:37:417 hours, 37 minutes, 41 secondsSo let me reload this.
7:37:527 hours, 37 minutes, 52 secondsSo I'm really sorry this will not work because we've already bu this already.
7:37:577 hours, 37 minutes, 57 secondsSo I'll just go ahead and see that it's working. So I'm going to just load this in local so I can see this. So let me
7:38:057 hours, 38 minutes, 5 secondscancel this and let me see the to clients.
7:38:107 hours, 38 minutes, 10 secondsSorry, let me see the out of back. CD to client and do MP and rundev.
7:38:197 hours, 38 minutes, 19 secondsAnd then I'm going to run the back end too.
7:38:247 hours, 38 minutes, 24 secondsSo it's going to the back end is still going to give it's still going to use production. So I'll go back and I'll change this to development and then I'm just going to run it again.
7:38:377 hours, 38 minutes, 37 secondsSo let's go to the um front end to the browser. So it's a local host.
7:38:487 hours, 38 minutes, 48 secondsSo now I can inspect and then we can see the user object.
7:38:567 hours, 38 minutes, 56 secondsOkay, something is wrong with the response. So let me go back to the code. So I'll go back to where I
7:39:057 hours, 39 minutes, 5 secondshave controller controller and let me see.
7:39:137 hours, 39 minutes, 13 secondsSo what I'll do, I'll create a method here. So let me add it here.
7:39:187 hours, 39 minutes, 18 secondsI will copy to all user. I'll just wrap this here.
7:39:287 hours, 39 minutes, 28 secondsAnd I think everything should be fine.
7:39:307 hours, 39 minutes, 30 secondsRequest user. So I'm going to use console.pl.
7:39:417 hours, 39 minutes, 41 secondsSo let's go back to the browser and I go to the browser now. And we should see the name and email. And this is working
7:39:487 hours, 39 minutes, 48 secondsfine. So we can go ahead and push this to the repository. So I have my repository here. So I'm going to push
7:39:557 hours, 39 minutes, 55 secondsit. And then we're going to go to um render.
7:40:047 hours, 40 minutes, 4 secondsSo let's click on render and then let's try and login. So before
7:40:127 hours, 40 minutes, 12 secondsI lo and push the changes. So I'll go back. I'll cancel to the server.
7:40:197 hours, 40 minutes, 19 secondsSo I'll see the out of back end and I'm going to say get add it.
7:40:347 hours, 40 minutes, 34 secondsNew changes.
7:40:377 hours, 40 minutes, 37 secondsGet push origin.
7:40:487 hours, 40 minutes, 48 secondsSo I've pushed everything. So we can go back now. Let's go to the browser and
7:40:547 hours, 40 minutes, 54 secondsthen let me log in. So, so I've logged into my account and I'm going to create
7:41:017 hours, 41 minutes, 1 seconda new web service and let's select this.
7:41:087 hours, 41 minutes, 8 secondsSo, I give this a name call base uh 64.
7:41:167 hours, 41 minutes, 16 secondsSo, I'm going to say app um B 64. AI.
7:41:247 hours, 41 minutes, 24 secondsLet me leave that is um this 64 app is okay because I've already used base AI my previous um deployment. So I'm going
7:41:337 hours, 41 minutes, 33 secondsto select node and then so for the SLC in order to deploy this let's go back to the code.
7:41:427 hours, 41 minutes, 42 secondsOh so there's no need to go back to the code. So in order to okay not in the SLC in the build command. So what I'm going to I'm going to paste in this command there. So let me move to the beginning.
7:41:547 hours, 41 minutes, 54 secondsSo what I want is I want to um um render to first of all I'm setting production to false. So you can install the dev dependency and and I'm adding preface.
7:42:057 hours, 42 minutes, 5 secondsSo it's um CD into the client and then install the client then run build
7:42:127 hours, 42 minutes, 12 secondsthen like you can see it to install it then it's also going to run build in the client then it will then navigate once
7:42:197 hours, 42 minutes, 19 secondsit's done it's going to navigate into the back end it's going to run this command to navigate in the back end then it's going to also um install all the
7:42:287 hours, 42 minutes, 28 secondspackages and then it's going to build the back end then we are going to and do node node um back end this index.jx.
7:42:407 hours, 42 minutes, 40 secondsSo it's going to serve the index.js inside the back end. And you remember the back end is going to point to the client this folder. So we're going to set it free.
7:42:537 hours, 42 minutes, 53 secondsThen we're going to add in our environment variable. So let's let me quickly add it. So we're going to copy all of this. So set node env to
7:43:027 hours, 43 minutes, 2 secondsproduction. Once we push the um once we build or once we deploy, we're going to later change the base URL and the front
7:43:107 hours, 43 minutes, 10 secondsend origin. And then we're going to still add in the EMV2 for the front end.
7:43:157 hours, 43 minutes, 15 secondsWe're going to replace it to with the same um URL. So I'm going to copy that EMV and let me go back to the um browser and I'm just going to add it here.
7:43:287 hours, 43 minutes, 28 secondsSo add I remove this. Then I'll go back to the client side and copy this one too.
7:43:377 hours, 43 minutes, 37 secondsAnd then I'm going to go back to the browser and I'm going to add this here.
7:43:497 hours, 43 minutes, 49 secondsSo we can see all of it has been added here production.
7:43:547 hours, 43 minutes, 54 secondsSo I'm just going to um deploy. So let's click on deploy web service.
7:44:037 hours, 44 minutes, 3 secondsAnd then I'm going to copy this. You can see the URL has been generated for us.
7:44:097 hours, 44 minutes, 9 secondsWe can go to um so let me close this.
7:44:147 hours, 44 minutes, 14 secondsSo environment variable and we can update it. source is show
7:44:227 hours, 44 minutes, 22 secondsedit and we can I'm going to edit this to this and also
7:44:317 hours, 44 minutes, 31 secondsthe base URL I'll edit this one too I place move this
7:44:397 hours, 44 minutes, 39 secondsand paste it like this okay the base U Okay, I'll just remove this and put this in.
7:44:527 hours, 44 minutes, 52 secondsSo, I think everything is complete.
7:45:037 hours, 45 minutes, 3 secondsSo, I can save and redeploy. So, let me go back to the event.
7:45:167 hours, 45 minutes, 16 secondsSo let me just cancel this one so it to start deploying the other one.
7:45:257 hours, 45 minutes, 25 secondsSo I think I can see both of them.
7:45:327 hours, 45 minutes, 32 secondsOkay, I I can't see the second one. Let me reload this. Okay, we can see it here.
7:45:417 hours, 45 minutes, 41 secondsSo let me click this and now see it's running the build command.
7:45:517 hours, 45 minutes, 51 secondsSo it has um installed the client side.
7:45:557 hours, 45 minutes, 55 secondsSo it's building the um the client and I think it is done with the client.
7:46:057 hours, 46 minutes, 5 secondsSo it has bu the um the back end. Now it's uploading the build.
7:46:167 hours, 46 minutes, 16 secondsSo it has been successful. So it's deploying.
7:46:237 hours, 46 minutes, 23 secondsSo now you can see it is running node back end. This index server is running.
7:46:307 hours, 46 minutes, 30 secondsSo let me click on this link. So you can see that it's working fine.
7:46:407 hours, 46 minutes, 40 secondsSo let me quickly log into my account.
7:46:427 hours, 46 minutes, 42 secondsSo you can see now I've lo into my account. So let me select a repository.
7:46:477 hours, 46 minutes, 47 secondsI'll just pick something simple. I'll just list the files in the project
7:46:597 hours, 46 minutes, 59 secondsand let's see if this is working. Now we can see that it is working.
7:47:107 hours, 47 minutes, 10 secondsSo it does need the project and I think it's only read me that is inside this project. So you can just say
7:47:177 hours, 47 minutes, 17 secondscreate uh let's say edit the readme
7:47:257 hours, 47 minutes, 25 secondsthe read me and let's say write hunting.
7:47:507 hours, 47 minutes, 50 secondsSo we can see that it has edit the that's edit the dream. So guys, so this
7:47:567 hours, 47 minutes, 56 secondsis working fine. So make sure you make sure you like, share this video, subscribe and also click the first link
7:48:057 hours, 48 minutes, 5 secondsto um sign up for command code.

Sync to video time
