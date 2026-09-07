https://www.youtube.com/watch?v=k_D_C3ExypU




Don't Pay for Claude Code | Build This Instead
Code With Antonio
Code With Antonio
419k subscribers

Join


3k


Share

Ask

Save

79,082 views  19 May 2026
In this video, we build our own AI coding agent inspired by tools like Claude Code completely from scratch and learn how modern AI engineering workflows actually work under the hood.

💎 Join the cohort: https://cwa.run/cohort
💻 GitHub: https://cwa.run/nightcode

⭐ CodeRabbit: https://cwa.run/coderabbit
⭐ Clerk: https://cwa.run/clerk
⭐ Neon: https://cwa.run/neon
⭐ Railway: https://cwa.run/railway
⭐ Sentry: https://cwa.run/sentry
⭐ Polar: https://cwa.run/polar

Timestamps:
00:00:00 Intro
00:06:25 Cohort
00:07:38 Project Setup
1:16:14 UI Infrastructure
2:51:25 Routing & Screen Layout
3:25:56 Server, Shared Package & Database
5:08:06 Sentry Monitoring
5:26:13 AI Chat Streaming
7:04:20 Session Management
7:39:58 Tool Calling
8:53:05 Completing The User Experience
10:02:57 Usage Based Billing
10:36:27 Client-Side Tool Execution
11:54:43 The End
Ask
Get answers, explore topics and more

Ask questions





-------------------------------------------------------------------------------------------------

In this video


Chapters

Transcript
Search transcript
Search transcript

Chapter 1: Intro
0:000 secondsTerminal coding agents are taking over.
0:033 secondsClode, Codex, Open Code, a new one drops every week. But have you ever wondered how they actually work? In this course,
0:1212 secondsyou're going to find out by building one yourself. This is Night Code, a Cloud Code alternative built entirely from
0:2121 secondsscratch. You will build the harness, wire up the tool calls, and understand exactly how these agents work under the
0:2828 secondshood. And here is the fun part. Once night code is functional, you can use it to help you finish the rest of this
0:3535 secondstutorial or on any project you are working on just like you would with cloud code. Let's see it in action. I'll
0:4343 secondsopen night code in my project and ask it to refactor my authentication middleware to support role based access control.
0:5252 secondsThe agent reads the codebase, identifies the right files, and writes the full implementation.
0:5858 secondsAll streamed token by token right here in the terminal. Now, if the UI looks familiar, that's because the design is
1:071 minute, 7 secondsinspired by open code. But don't worry, this is not a fork. We are building this entire project from scratch with a
1:151 minute, 15 secondscompletely original implementation. That was build mode. In this mode, the agent has access to every tool. It can read,
1:241 minute, 24 secondswrite, edit, and execute commands in your project. Now, let me switch to plan mode and ask it to review what I just
1:331 minute, 33 secondsbuilt. It reads the files, analyzes the architecture, and gives me a full breakdown. But notice what's different.
1:421 minute, 42 secondsIn plan mode, the agent has no write tools, no edit tools, and no shell access. It can only read and search.
1:521 minute, 52 secondsThat's not a limitation. That's by design. And once you understand how this works, you can create your own modes. A
2:002 minutesreview mode, a test mode, a documentation mode. You control which tools the agent gets and that changes
2:082 minutes, 8 secondseverything about how it behaves. So how does this work? Night Code is a monor repo with four packages. a terminal UI
2:172 minutes, 17 secondsbuilt with Open Tui, a back-end server powered by Hono, a shared types and schemas package, and finally a database
2:262 minutes, 26 secondslayer. The terminal UI uses open to first class React bindings. That means
2:322 minutes, 32 secondswe build terminal interfaces with the same component model and syntax you already know from the web. Your existing
2:402 minutes, 40 secondsReact knowledge transfers directly. Each tool the agent uses like bash, edit file or grap is its own module. You will
2:502 minutes, 50 secondsbuild every single one of them and every response streams in real time through server sent events with live reasoning
2:582 minutes, 58 secondson display. Now let's try something different. There's a bug in my credits calculation logic. I will point it to
3:053 minutes, 5 secondsthe file and ask it to find and fix the issue. It reads the file, identifies the problem, and applies a targeted fix. No
3:143 minutes, 14 secondsfull rewrites, no unnecessary changes, just a clean surgical edit exactly where it needed to go. Now, let me explore the
3:233 minutes, 23 secondssessions command. Here are all of my past conversations. I can click into the one from earlier, the outreactor, and
3:313 minutes, 31 secondsit's all still here. every message, every tool call, every file change, I can pick up right where I left off. Now,
3:413 minutes, 41 secondshere is something interesting. Let me try one more generation. And there it is. Not enough credits. That's because Night Code is not just a coding agent.
3:513 minutes, 51 secondsIt's a complete software as a service business. We're building a full credits-based billing system powered by
3:583 minutes, 58 secondsPolar. Every request costs credits based on the model and token usage. If you have ever wanted to monetize a CLI tool,
4:084 minutes, 8 secondssell inference for your own LLM, or ship a paid developer product, this will teach you exactly how to do it. Getting
4:164 minutes, 16 secondsmore credits is simple. Using the upgrade command, we can open the checkout screen from which we can purchase new credits. And just like
4:244 minutes, 24 secondsthat, we're back in business. I can check my balance anytime with the usage command. No web hooks, no complicated Stripe integration. Polar handles the
4:334 minutes, 33 secondsmetering and the credit system and it all just works. And what's a CLI app without themes using the theme command?
4:424 minutes, 42 secondsYou can pick a color scheme and it will instantly apply across the entire UI. I can switch models on the fly using the
4:514 minutes, 51 secondsmodels command. I can ask one question with Haiku, the next one with Opus, and the third one with GPT all in one
4:594 minutes, 59 secondssession. Night Code is fully provider agnostic. The six models I've included are just a starting point. The Versel AI
5:085 minutes, 8 secondsSDK under the hood means that you can plug in Google, Mistral, Grock, or any other provider. And in this course, you will learn exactly how to add your own.
5:205 minutes, 20 secondsAnd then there is authentication.
5:225 minutes, 22 secondsMost CLI tools just ask you to paste an API key. Night Code does it properly using the login command. Your browser
5:315 minutes, 31 secondsopens and you authorize through clerk using an OFF flow and the session is communicated back to the terminal automatically. No copy pasting tokens.
5:415 minutes, 41 secondsThis is real browser to CLI authentication and it's something you rarely see explained anywhere. This
5:495 minutes, 49 secondsisn't just a coding tutorial. We're going to follow a proper Git workflow with commits, branches, and real pull
5:565 minutes, 56 secondsrequests. Every pull request gets reviewed by Code Rabbit, our AI code reviewer, catching logic issues, best
6:056 minutes, 5 secondspractices, and critical mistakes early on. Besides that, we're going to get a preview deployment thanks to Railway,
6:126 minutes, 12 secondsour deployment solution for this project. We're also going to get logs and error monitoring with Sentry. This
6:196 minutes, 19 secondshas been one of my favorite projects to complete. Let's go ahead and build it together. Before we jump into the tutorial, I want to share something with
Chapter 2: Cohort
6:286 minutes, 28 secondsyou. Tutorials like this are great for learning how to build something step by
6:346 minutes, 34 secondsstep, but they usually skip over a lot of what real engineering actually looks
6:416 minutes, 41 secondslike. You never see me do any debugging, refactoring, architecture changes, fix dead ends, or make technical decisions.
6:506 minutes, 50 secondsAnd honestly, that's where most of the real learning actually happens. That's exactly why for the first time I made
6:586 minutes, 58 secondstwo different ways of finishing this tutorial. One is by watching this polished step-by-step YouTube tutorial.
7:067 minutes, 6 secondsAnd the other one is the cohort where you'll learn how to code like me, not just copy what I type in a YouTube
7:147 minutes, 14 secondsvideo. This YouTube tutorial shows you how to build a project step by step. But the cohort is where I show you how I
7:227 minutes, 22 secondsactually approach building projects like these from scratch. how I solve errors, refactor code, how I make technical
7:297 minutes, 29 secondsdecisions, and most importantly, how I think while building. If you want to learn that process, check out the link
7:377 minutes, 37 secondson the screen. In this chapter, we're going to set up our project and develop the initial component architecture.
Chapter 3: Project Setup
7:447 minutes, 44 secondsWe're going to scaffold the monor repo using bun. We're going to add our initial package called CLI. and we're
7:517 minutes, 51 secondsgoing to bootstrap it using open to his React template that will allow us to build terminal user interfaces using a
7:597 minutes, 59 secondsfamiliar React syntax. We're then going to evolve that simple example into a proper component architecture by having
8:088 minutes, 8 secondsan app component, header, input bar, text area, status bar, and finally a quite complex component called command
8:168 minutes, 16 secondsmenu. Let me show you exactly what you will have by the end of this chapter. By the end of this chapter, you will be
8:238 minutes, 23 secondsable to run this command in your project and you will open this home screen. You will have an ASKI code of your logo or
8:328 minutes, 32 secondsyour uh name of the project. And beneath it, you will have this pretty looking text area. You will have a left border
8:418 minutes, 41 secondshere that kind of indicates what mode we are on. beneath it a text which tells you what mode we are on. Hard-coded
8:498 minutes, 49 secondsmodel that we are using and you will be able to say something like hello world.
8:558 minutes, 55 secondsCurrently submitting does nothing but you do submit with enter. If you want a new line you hold shift and enter. All
9:039 minutes, 3 secondsright. And if you enter a forward slash you get command menu. This one looks
9:109 minutes, 10 secondsvery simple, but that is because you are used to web applications. Keep in mind that this is a terminal and this type of behavior doesn't exist in the terminal.
9:219 minutes, 21 secondsSo, you're going to learn how to create it to build beautiful experiences for your users even within the terminal.
9:309 minutes, 30 secondsWhen you select a command, you will be able to pass it along to text area or if it has an action like exit, it will
9:389 minutes, 38 secondsexecute that action. So that is what we are going to have by the end of this chapter. Let's go ahead and start by
9:469 minutes, 46 secondscreating a night code folder or whatever is the name of your project. Let's go inside and let's start by initializing a
9:559 minutes, 55 secondsgit repository. Then in here, uh, I'm going to go ahead and open that repository.
10:0210 minutes, 2 secondsSo, open folder and that new folder we just created.
10:0810 minutes, 8 secondsHere it is. Inside of night code, I'm going to create uh a.get ignore
10:1610 minutes, 16 secondsfile and I'm going to add node modules inside. Then I'm going to add a readme.md
10:2310 minutes, 23 secondsand I'm just going to add night code like this.
10:2810 minutes, 28 secondsSo we just have these two files. Then I'm going to go ahead and run git add get commit. And I'm just going to run initial commit.
10:4010 minutes, 40 secondsThere we go. Then let's go ahead and create a new repository. So I'm going to call this night code.
10:4910 minutes, 49 secondsI'm going to make it private. I'm not going to add anything here. I'm just going to click create repository. And then I'm going to use the second option,
10:5810 minutes, 58 secondspush an existing repository from the command line. And I'm going to paste those commands inside of my night code folder which has git initialized in it.
11:0811 minutes, 8 secondsWhat this is going to do is it's going to synchronize my local changes with remote. And here it is. Git ignore and
11:1511 minutes, 15 secondsreadme are now on GitHub. Perfect. So now we can go ahead and develop knowing that our changes will be safe.
11:2511 minutes, 25 secondsSo the first thing we have to do is we have to scaffold the monor repo. So for that we're going to be using bun. If you don't have bun installed you can install
11:3411 minutes, 34 secondsit using curl for Mac OS and Linux PowerShell on Windows or if you have npm
11:4111 minutes, 41 secondshomebrew or scoop you can do it with those as well. Once you have it installed, you can run bun version to verify like this.
11:5211 minutes, 52 secondsThe reason we are using bun is for two things. Bun when looked at as a package manager has a feature called workspaces.
12:0312 minutes, 3 secondsJust make sure you change from runtime to package manager in the documentation.
12:0812 minutes, 8 secondsAnd then you can find workspaces here which is exactly what we need. We are going to build a monor repo with multiple packages. We're going to have a
12:1612 minutes, 16 seconds2e package or CLI package, a server package, database package, and a shared package. This can also be done with
12:2412 minutes, 24 secondsPNPM. But because we are going to be using Open TUI to build terminal UIs,
12:3112 minutes, 31 secondsthey also heavily rely on bun. So I would just suggest using bun for this project and then maybe switching later if you find it easier to work with PNPM.
12:4112 minutes, 41 secondsSo let's go ahead and define a very simple package JSON in our project here.
12:4712 minutes, 47 secondsSo I'm just going to create a new file package.json and I'm just going to paste this in
12:5512 minutes, 55 secondshere. I'm going to change this to be night code aka the name of your project.
13:0013 minutesAnd I'm going to remove dev dependencies and a trailing comma here because I don't need it. Great. So now that we
13:0913 minutes, 9 secondshave packages defined as our workspaces, let's go ahead and create packages.
13:1513 minutes, 15 secondsJust like that. Now in here, let's go inside of that packages directory and
13:2113 minutes, 21 secondslet's learn how to scaffold open. So the cool thing about open 2 is while it's
13:2913 minutes, 29 secondsintended to be used like this, they also built first class React bindings
13:3813 minutes, 38 secondsallowing us to write it like this instead which is exactly what we need because we come from web or at least a
13:4613 minutes, 46 secondslot of my followers do because I do web tutorials. So let's go ahead and run the following template here. So just make
13:5413 minutes, 54 secondssure you are inside of your packages folder and run the following template and call this project CLI.
14:0414 minutes, 4 secondsOnce this is initialized, you will have packages CLI in here. Open CLI. And now
14:1314 minutes, 13 secondslet's go ahead and copy git ignore entirely. And let's paste it in the root git ignore. So let's improve this simplified git ignore that we had.
14:2614 minutes, 26 secondsThen I'm going to delete the git ignore which was just added in the CLI because this is a monor repo and we only need
14:3314 minutes, 33 secondsone at the top. Let's also remove bun lock because the lock file will be kept in the root. Let's remove readme or we
14:4114 minutes, 41 secondsalso have readme in the root. Let's go inside of package.json JSON JSON in the CLI and let's simply change its name
14:4814 minutes, 48 secondsfrom not just CLI but let's make it an obvious extension night code CLI like
14:5514 minutes, 55 secondsthis. The reason I'm typing night code here is because that's what's typed here in the name night code. So make sure it
15:0415 minutes, 4 secondsmatches for the TS config. This is a pretty good set of base defaults. So, I'm going to
15:1115 minutes, 11 secondscopy it here. And in the root of my project, I'm going to add tsconfig.base.json.
15:1915 minutes, 19 secondsAnd I'm going to paste it here. I'm only going to remove these two because these two are open to specific. So, I'm going
15:2715 minutes, 27 secondsto remove them. And then I'm going to go inside of packages CLI tsconfig.json
15:3415 minutes, 34 secondsand I'm going to modify it a bit. So instead of it being all of this, I'm
15:4215 minutes, 42 secondsgoing to simplify it by extending our base config which we just moved and then
15:5015 minutes, 50 secondsadding those two compiler option JSX and JSX import source. So that is uh what
16:0016 minuteswe've done now is we've gotten pretty good defaults thank to thanks to this bun create 2y but since since this is a
16:0716 minutes, 7 secondsmonor repo it makes no sense that it has all of those options defined since those are pretty good base standards for all
16:1616 minutes, 16 secondsof our packages. So that's why I am extending it instead of having it written uh all in here. So great, we now
16:2416 minutes, 24 secondssimplify the package JSON, the TS config, and the CLI is now much leaner.
16:3216 minutes, 32 secondsNow what I want to do before we continue is go back in the root. So make sure you
16:3816 minutes, 38 secondsare in night code and just run bun install. And you can see one package
16:4616 minutes, 46 secondsinstalled, one removed. So obviously something was synchronized. And this is how we're going to install packages from
16:5316 minutes, 53 secondsnow on. All right. Thanks to this simple package JSON monorreo which we have established in package JSON using the
17:0017 minutesworkspaces, we can now keep track of all packages across all of our well
17:0617 minutes, 6 secondsworkspaces or packages. So what do we actually have in the source folder?
17:1217 minutes, 12 secondsWell, nothing much. It's just a simple scaffolding here which allows us to see an asky font and a text which says what
17:2217 minutes, 22 secondswill you build and it calls create cli renderer and it simply renders the root app component
17:3017 minutes, 30 secondsright here. So in order to see that we have to change directory uh into packages.
17:3717 minutes, 37 secondsLet me just go back.
17:4117 minutes, 41 secondsMy apologies. I keep changing where I'm going. Uh, so I'm just gonna go to work
17:5217 minutes, 52 secondsnight code. All right. So let's go inside of packages inside of CLI and then let's run bun
18:0018 minutesrundev. So this is what you should have right now. The problem is right now the only way you can run this is by doing
18:0918 minutes, 9 secondsthis change directory to packages change directory to CLI and then bon rundev. So
18:1518 minutes, 15 secondsinstead how about we add a script in the root of our package JSON uh allowing us
18:2418 minutes, 24 secondsto do that. So, I'm just going to add a comma here and then some scripts. dev
18:3018 minutes, 30 secondsbunr run watch. Uh, and my apologies, not this one.
18:3718 minutes, 37 secondsI meant this one. Here it is. Bun d--watch packages cli sourceindex.tsx.
18:4818 minutes, 48 secondsAnd now what I can do is when I am inside of my root project I can run bun rundev cli like this.
19:0019 minutesSo I no longer have to change directory.
19:0319 minutes, 3 secondsI can just do it from the root of my project which is exactly what we wanted to achieve.
19:1019 minutes, 10 secondsNow let's go ahead and modify CLI source right here.
19:2019 minutes, 20 secondsand remove the ASKI font.
19:2419 minutes, 24 secondsLet's also remove the text. Let's remove text attributes. And let's very simply render a text area here.
19:3419 minutes, 34 secondsSo now when you run bun rundev CLI, you will be able to type just like that. And
19:4219 minutes, 42 secondsthe cool thing about this command bun rundev cli uh is that it has hot reload
19:5019 minutes, 50 secondsenabled. So if I add something like placeholder here, hello world, you will see it's immediately reflected.
20:0020 minutesPretty cool. So that is the initial step scaffolding the monor repo. Now let's go
20:0720 minutes, 7 secondsahead and evolve this into this more advanced uh component architecture.
20:1620 minutes, 16 secondsSo what I want to start with is by creating a few components. I want to
20:2420 minutes, 24 secondsstart with a header component because it's pretty simple. So, inside of packages CLI
20:3320 minutes, 33 secondssource, let's create a new folder called components.
20:3720 minutes, 37 secondsAnd in here, I'm going to create header.tsx.
20:4420 minutes, 44 secondsLet's export the header component.
20:4820 minutes, 48 secondsAnd in here, I'm going to go ahead and render a box with justify content center, another box with flex direction,
20:5720 minutes, 57 secondsand then two asy fonts. It appears I'm having an error here. This could be just
21:0321 minutes, 3 secondsmy IDE bugging up. There it is. You can see that the moment I changed something, it restarted the server and now it
21:1121 minutes, 11 secondsworks. So, ask font is a built-in component from Open Tui. You can read
21:1921 minutes, 19 secondsmore about it in the documentation actually. So if you find the components here, you can find asi font and you can
21:2721 minutes, 27 secondssee all the ways you can use it. This is my way of using it. And let me go ahead
21:3521 minutes, 35 secondsand actually render the header so that we can uh see this in action. So I'm going to
21:4321 minutes, 43 secondsgo inside of index.tsx tsx and what I'm going to do is I'm going to clean the entire return here and I'm
21:5121 minutes, 51 secondsgoing to start with an empty box with an align items justify content background color with height and gap and then in
21:5921 minutes, 59 secondshere I'm just going to render my new component header from components header and here is the result night code just
22:0622 minutes, 6 secondslike that so if you go back into header here you can play around with these uh asy fonts for example Example, you can
22:1522 minutes, 15 secondshide this one, just have code and change the font to shade or to whatever else
22:2222 minutes, 22 secondsautocomp completion tells you. You can have it huge. You can have it in a grid, right? A billion options for you here.
22:3222 minutes, 32 secondsSlick. I prefer having tiny. And I like to have a combination of two of them so that one can be a different color. And then the result is this.
22:4422 minutes, 44 secondsAll right.
22:4622 minutes, 46 secondsSo now uh that we have this developed, let's go ahead and develop another simple component. So at this point, what
22:5422 minutes, 54 secondsI'm going to do is I'm also going to show you what the end result is going to look like because sometimes it's hard to understand what we are building without
23:0323 minutes, 3 secondslooking at the end result. Bon rundev CLI. This is the end result. Okay, so right now we have this. Okay, we are
23:1223 minutes, 12 secondsgetting close. So, what I want to build now is this component right here. I want to build the input bar. I want to build
23:2123 minutes, 21 secondsthe status bar. And I want to show you how you can add this small little border which kind of makes it cool because it matches the color of the current mode.
23:3323 minutes, 33 secondsSo, let's start with the status bar because it's very simple. Okay, let's go inside of packages CLI source
23:4223 minutes, 42 secondscomponents and I'm going to create a new file status bar.tsx.
23:4923 minutes, 49 secondsThe status bar simply uses text attributes from open to core export function status bar and return a box.
23:5723 minutes, 57 secondsreturn a text with a foreground color of cyan rendering the text build and then text attributes dim with a foreground of
24:0724 minutes, 7 secondsgray rendering a chevron. Uh now I'm not entirely sure how we can
24:1524 minutes, 15 secondsuh you can I'm not sure how to render these elements in in like this type of
24:2224 minutes, 22 secondsformat. Maybe something like this. I don't really know. Uh you can basically search for like uni code for chevron.
24:3624 minutes, 36 secondsLet me go ahead and try and find here it is html entity for it. So if you
24:4524 minutes, 45 secondsdon't know how to type it, you can type it like this. And I think I think it
24:5224 minutes, 52 secondsshould work. We'll see if it doesn't work. Uh, yeah, you can basically just Google
25:0125 minutes, 1 secondthis and I think you should be able to copy it from Google then like an arrow and
25:0825 minutes, 8 secondsthen just paste it here. All right. So that is status bar. So if I go inside of
25:1425 minutes, 14 secondsindex here and render status bar now you can see how that looks like. build
25:2425 minutes, 24 secondsan Opus 46. Basically, we are hard coding uh the current mode we are in and we are hard coding the current model
25:3225 minutes, 32 secondsthat we are using. So, getting close to the end result here.
25:3825 minutes, 38 secondsNow that we have uh the status bar, let's go ahead and develop the input.
25:4725 minutes, 47 secondsSo, I'm going to go ahead inside of components new file input bar.tsx. tsx.
25:5325 minutes, 53 secondsLet's define the props. The props are going to be onsubmit and disabled. And
26:0026 minutesthen let's go ahead and export function input bar with the same props. And in
26:0826 minutes, 8 secondshere I'm going to go ahead and return a box.
26:1526 minutes, 15 secondsThen in here I am very simply going to open
26:2226 minutes, 22 secondsanother box and I'm going to add a little comment
26:2826 minutes, 28 secondshere to do add left border. So I'm purposely going to leave this box empty
26:3626 minutes, 36 secondsattribute wise. And then inside of this box we're going to add another box with all of these properties inside.
26:4626 minutes, 46 secondsAnd then finally, we can render the text area.
26:5326 minutes, 53 secondsAnd let's go ahead and make sure that it's not focused if it's disabled.
26:5826 minutes, 58 secondsAnd let's go ahead and give it a placeholder. Ask anything, for example, fix a bug in the database. So now we can
27:0727 minutes, 7 secondsgo and beneath the text area, render the status bar, actually. So make sure you
27:1427 minutes, 14 secondshave added this import here. And now we can go back inside of the index here.
27:2027 minutes, 20 secondsRemove the status bar. Uh and instead open a box and render the input bar in
27:2927 minutes, 29 secondshere. So remove this. We just have input bar and add on
27:3527 minutes, 35 secondssubmit here. And for now it can just be an empty arrow function.
27:4427 minutes, 44 secondsAnd as per the box which is encapsulating the input give it a width of 100 and some limitations on the max
27:5027 minutes, 50 secondswidth. And you can see we are getting pretty close already. Good. Uh so what I
27:5827 minutes, 58 secondswant to do now is I want to show you how you can add um that left border. It's
28:0428 minutes, 4 secondsnot as intuitive as you might think. Uh so let me go ahead and show you. I'm going to go back inside of the uh input
28:1428 minutes, 14 secondsbar. So what I thought I was going to do is just define border
28:2128 minutes, 21 secondsand then left and then border color and set it to scan. Uh let me see if
28:3128 minutes, 31 secondsthat's even visible. And it looks okay, right? But it's not exactly this, right?
28:3728 minutes, 37 secondsIn in original open code, they have this thick line. If you're satisfied with this, you can leave it at this. I mean,
28:4628 minutes, 46 secondsthis is just cosmetics talk, right? But if you really want to have it the same
28:5328 minutes, 53 secondsway they are having it, the way I f found out is by picking at open code
29:0029 minutessource code. And I found that they have this handy little util which has this
29:0829 minutes, 8 secondskind of thick pipe which I have no idea how to render in uniode. So if you want
29:1629 minutes, 16 secondsto you can add that. If you don't care about it, you don't have to add it. is just cosmetics. I'm going to do it to stay true to my original source code.
29:2429 minutes, 24 secondsSo, I'm going to add border.tsx and I'm just going to render that inside. Okay. So, now that I have that,
29:3329 minutes, 33 secondsI'm going to go back inside of the input bar right here, and I'm going to add the following custom border characters.
29:4729 minutes, 47 secondsimport empty border from dot /border.
29:5029 minutes, 50 secondsAdd vertical and add bottom left. And again, this is an even shorter one which I also found in their source code right
29:5929 minutes, 59 secondshere. I have no idea what character that actually is. So, if you want to, you can add it and then you'll have like a
30:0830 minutes, 8 secondsthicker line here and it will be more similar to open code. If you don't care about it, it really does not matter.
30:1830 minutes, 18 secondsOkay. Uh, good. So, pretty cool, right? So, what are the current differences?
30:2530 minutes, 25 secondsWell, in my current implementation, if I try to submit, I have a new line.
30:3130 minutes, 31 secondsWhereas in the finished implementation, if I try to submit, it actually submits.
30:3630 minutes, 36 secondsSo, uh, the way we do that is by adding key bindings. So you can actually go
30:4530 minutes, 45 secondsinside of text area here and I think quite soon you will come across key bindings. So this is how you can uh make
30:5430 minutes, 54 secondsa combination of user pressing on return and control being pressed as well trigger the submit action. So that's
31:0331 minutes, 3 secondswhat we have to do. Uh now we have to define uh the
31:1031 minutes, 10 secondswhat how should I say bindings right that we're going to need.
31:1631 minutes, 16 secondsSo uh I think that we should do this here in the input bar
31:2731 minutes, 27 secondsand let's just import key binding from open toy core. So return should trigger the submit action same as enter. But if
31:3531 minutes, 35 secondsreturn or enter are held with shift, they should open a new line. And now that we have the text area key bindings,
31:4231 minutes, 42 secondslet's go ahead key bindings and pass along text area key bindings.
31:5131 minutes, 51 secondsAnd I think that uh this should now work. Let me check. try to
32:0032 minutessubmit. There we go. Nothing happens because we don't have submit implemented. But it doesn't do a new
32:0732 minutes, 7 secondsline. But if I hold shift, then it does a new line exactly as the end result.
32:1432 minutes, 14 secondsGreat. I'm very satisfied with this. Uh, now it's time to start developing the
32:2132 minutes, 21 secondsbig one. Now it's time to start developing the command menu which opens on forward
32:2832 minutes, 28 secondsslash. So that is this and it's a very complex one. So let's go ahead and have
32:3732 minutes, 37 secondsour app running here and we're going to start with kind of a simplest thing we can do which is just defining what
32:4732 minutes, 47 secondscommands should exist. So, instead of source components, let's open a new folder called command menu. And then in here, I'm going to add commands.tsx.
33:0033 minutesUh, and in here, I'm going to export const commands.
33:1133 minutes, 11 secondsOkay. And then I'm just going to add some commands. Let's for example add new
33:1933 minutes, 19 secondsand let's for example add an exit command.
33:2533 minutes, 25 secondsNow right now we don't have proper types for this. So we should add those as
33:3433 minutes, 34 secondswell. I'm going to add it inside of command menu types.ts.
33:4133 minutes, 41 secondsAnd let's define the command context which for now should only have the exit function
33:4933 minutes, 49 secondsbecause it's the only command which we are executing at the moment. We can't really add any more types. But later
33:5733 minutes, 57 secondsthis will have access to our toast provider. This will have access to our dialogue provider. This will have access
34:0434 minutes, 4 secondsto our uh prompt config provider which will encapsulate what model we are on uh
34:1134 minutes, 11 secondswhat build what mode we are on right but right now the only one we have defined is the exit function so that's why we
34:1934 minutes, 19 secondsare having such a shallow command context and then let's create the type for a command item in general with name
34:2834 minutes, 28 secondsdescription value and then an optional action and then we can go ahead and define that. So command from types and
34:3634 minutes, 36 secondsthen an array. And you can see the error has gone away because now exit is a proper function that is passed to every
34:4534 minutes, 45 secondscommand. So every command can you know access the context and exit.
34:5334 minutes, 53 secondsSo that is how we're going to define uh what commands exist uh in our uh well command menu.
35:0435 minutes, 4 secondsNow let's actually develop the component itself. In order to do that, we first
35:1135 minutes, 11 secondsneed to add a simple filter commands function.
35:1835 minutes, 18 secondsSo what this is going to do is it's going to go over our commands array and
35:2635 minutes, 26 secondsit's simply going to filter uh by user input or should I say users
35:3335 minutes, 33 secondsquery. So if users query is empty, it will fall back to returning the full list of commands. Otherwise, it's going
35:4135 minutes, 41 secondsto filter over them if they start with lower uh it's going to filter over them in a way that it lowercases the command
35:5035 minutes, 50 secondsname lowercases the user's query and uses a very simple starts with API to
35:5735 minutes, 57 secondscheck if we actually have the command that the user is trying to search for.
36:0236 minutes, 2 secondsSo, right now nothing happens in our code. But what is supposed to happen is this, right?
36:1136 minutes, 11 secondsIt's supposed to query. Okay, that's what that function is for.
36:1936 minutes, 19 secondsSo now that we have that, let's go ahead inside of command menu and develop the actual component.
36:2936 minutes, 29 secondsSo for the component, we're going to need ref object from React text
36:3636 minutes, 36 secondsattributes and type scrollbox renderable from open to core and then our newly
36:4336 minutes, 43 secondscreated get filtered commands and the actual commands array. In here we have a bug saying that types react isn't added and I believe it is not.
36:5636 minutes, 56 secondsSo let's go ahead and quickly add it. So I'm going to go inside of packages.
37:0337 minutes, 3 secondsThen I'm going to go inside of CLI bonad d types react. Just like that. Then I'm
37:1037 minutes, 10 secondsgoing to go back bondev cli. And I believe this error has been solved now.
37:1737 minutes, 17 secondsAnd my CLI package. JSON should now also have types react added here.
37:2537 minutes, 25 secondsUh, I'm pretty sure this should be the same version, but I guess they are minor enough that it's not causing any
37:3437 minutes, 34 secondsincidents. Let's just focus on developing our command menu component.
37:3937 minutes, 39 secondsSo, let's define the maximum number of visible items, which is basically this.
37:4437 minutes, 44 secondsWhen you uh do a forward slash, how many of these should be visible? So, 1 2 3 4 5 6 7 8. Everything else should be
37:5337 minutes, 53 secondsoverflown. Okay, that's what this constant is doing. And now we have to define the command column width.
38:0438 minutes, 4 secondsBasically, we have to align all command names in a fixed width column so that their descriptions start at the same
38:1138 minutes, 11 secondshorizontal position for a clean tabular look. Again, simpler to explain by looking at this. regardless of the
38:1938 minutes, 19 secondslength of the name of the command. You can see that all descriptions start at the same line almost like a table. So
38:2738 minutes, 27 secondsthat's what we're trying to do here because it looks very weird if every single description starts like here then
38:3538 minutes, 35 secondshere then here then one here. It just doesn't look as good as this. So I'm just trying to show you how how
38:4238 minutes, 42 secondsextensive open 2 is and how much you can actually care if you want to. So let's
38:4938 minutes, 49 secondsdefine the command column width using this math max which simply iterates over the commands and simply finds the length
38:5838 minutes, 58 secondsof the command names and then defines like the maximum value of it and adds a buffer of four.
39:0639 minutes, 6 secondsThen let's go ahead and define the command menu props which is this component that we are building. Let's go ahead and export the component itself.
39:1839 minutes, 18 secondsAnd let's start by finding out which commands we should render. So what was the user's query? Should we render all
39:2639 minutes, 26 secondscommands or just some of them? Then let's go ahead and get the visible height. So now that we have filtered the
39:3539 minutes, 35 secondselements, how many elements are visible, right? Should it be a maximum of eight or should or can it be less than that if
39:4439 minutes, 44 secondsthere's not enough results or if there are zero results, should we show something? Yes, we should. We should say
39:5239 minutes, 52 secondsno matching commands with a simple attributes uh text attributes dim.
40:0140 minutes, 1 secondAnd then let's go ahead and return and let's render scroll box here which
40:1040 minutes, 10 secondsis another open 2 component with a ref and a height. And in here we just have to iterate over uh our commands.
40:2340 minutes, 23 secondsSo let's first check if the user is highlighting a certain command by using the selected index prop and defining
40:3240 minutes, 32 secondsthat in the is selected constant. And then in here we can go ahead and return a box element.
40:4340 minutes, 43 secondsLet's go ahead and give this box element some attributes here. So the key is going to be the command value. It's
40:5140 minutes, 51 secondsgoing to have some flex, some padding, some height, overflow, and then it will change background color depending on if the user is hovering or not. Let me show
41:0041 minutesyou exactly what I mean. When I hover, it changes to blue. But notice that I also have to change the foreground color of the text so the contrast looks good.
41:1141 minutes, 11 secondsSo, right now, again, we don't have any of that. But let's go ahead and uh simply continue developing.
41:1941 minutes, 19 secondsSo now I have to render the name of the command like this. So we define the
41:2641 minutes, 26 secondswidth command column width which we have calculated above in a tabular like fashion and then we have a text
41:3341 minutes, 33 secondsattribute and we change the foreground depending on if it's selected. So we create a contrasting color and we simply
41:4141 minutes, 41 secondsrender the command name along with a forward slash to indicate that it's a command. And then beneath that another
41:4941 minutes, 49 secondsbox which is used to render the description which does a very similar thing but instead of black and white it uses black and gray.
41:5941 minutes, 59 secondsBrilliant. So that is our command menu component.
42:0542 minutes, 5 secondsNow what I want to do is I want to check if we are able to already render it inside of input bar. Uh perhaps we
42:1442 minutes, 14 secondscannot do it yet. I just want to try just in case. So, let me go ahead and
42:2242 minutes, 22 secondsfind this where I'm supposed to render this. All right. So, we have to render it within the box which has a position
42:3042 minutes, 30 secondsrelative. So, just above the text area here. I'm going to go ahead and simply hardcode true and because this is this
42:4042 minutes, 40 secondswill later be dynamic. And let's start by rendering a box.
42:4842 minutes, 48 secondsLet me go ahead and close the box.
42:5242 minutes, 52 secondsSo a box with position absolute, bottom 100, left zero, width 100, background color, and zindex of 10. And then in
43:0043 minuteshere, let's see, can we render the command menu? So it's a self-closing component. And make sure you have
43:0843 minutes, 8 secondsimported it. And let's see. I'm currently having an error. So for the query, I'm going to start with just an
43:1643 minutes, 16 secondsempty string. And I think that that's enough.
43:2143 minutes, 21 secondsThere we go. You can see new. And you can see exit. Uh, obviously we need a
43:2843 minutes, 28 secondslot more here, but I just wanted you to see how it's going to kind of like float
43:3543 minutes, 35 secondsabove our text area. So right now you cannot click on it, you cannot control it with the keyboard and it's always
43:4443 minutes, 44 secondsvisible. So now we have to change that and we have to make it actually dynamic and this is the most complex part.
43:5443 minutes, 54 secondsActually in order to achieve this we have to develop uh use command menu
44:0144 minutes, 1 secondhook. So let's go inside of source components command menu use command menu.ts.
44:1144 minutes, 11 secondsIn here I'm going to add use ref use state use memo ref object scrollbox
44:1844 minutes, 18 secondsrenderable type use keyboard hook and get filtered commands along with the command type. Let's define the return
44:2844 minutes, 28 secondstype of this hook. So, it's going to return all of these. Show command menu, command query, selected index, scroll
44:3644 minutes, 36 secondsref, handle content change, resolve command, and set selected index. Let's go ahead and map those return types to
44:4444 minutes, 44 secondsthe actual hook so we can start developing it. I'm going to go ahead and start by defining all of the states and
44:5144 minutes, 51 secondsrefs. So text value selected index show command menu string integer boolean and
44:5944 minutes, 59 secondsfinally a scroll ref with a type of scrollbox renderable from open toy with the default value of null. Let's go
45:0745 minutes, 7 secondsahead and define the command query. So command query checks if show command
45:1545 minutes, 15 secondsmenu is true and it checks if text value starts with forward slash. If it does
45:2445 minutes, 24 secondssimply extract the part after the slash otherwise fall back to an empty string
45:3245 minutes, 32 secondsand then using that command query we can filter the commands using get filtered commands.
45:4145 minutes, 41 secondsNow that we have a list of commands that the user is searching for, we can develop the rest of our functions. So
45:4945 minutes, 49 secondslet's start with handle content change which accepts text inside.
45:5845 minutes, 58 secondsThe first thing we're going to do is we're going to change the value of text to that text passed. We're going to change the selected index back to zero.
46:0846 minutes, 8 secondsSo it restarts whatever was highlighted again because user just entered something new. And then what we're going to do is we're going to jump back to the
46:1746 minutes, 17 secondstop of the list when the user types a new character. So we find the scroll box. And if we successfully found the
46:2446 minutes, 24 secondscontainer, we are scrolling back to the top.
46:2946 minutes, 29 secondsThen let's go ahead and check if the prefix starts with a forward slash and then extract everything after the slash exactly like we do here.
46:4146 minutes, 41 secondsAnd then let's go ahead and do an if else. So if the prefix is not null and if the prefix doesn't include an empty
46:4946 minutes, 49 secondswhite space after the forward slash, let's go ahead and show the command menu. Otherwise, let's go ahead and hide the command menu.
47:0147 minutes, 1 secondSo, what is that logic? Well, let me show you the finished result. If I type a forward slash, we should open the
47:0847 minutes, 8 secondscommand menu. If I go ahead and search for something that's filterable, I will continue showing this. If I search
47:1647 minutes, 16 secondsagain, I will show empty. But if I add whites space, we're going to assume the user literally means forward slash and
47:2447 minutes, 24 secondswants to send the forward slash character to the agent. So that's why we developed that logic.
47:3247 minutes, 32 secondsNow let's go ahead and develop a function to resolve a command. So resolve a command at a specific index.
47:4047 minutes, 40 secondsUh the way this is going to function is as follows. So the resolve command function accepts the index and returns
47:4947 minutes, 49 secondsthe command or undefined. It will attempt to find the command from a list of filtered commands using the index. If
47:5747 minutes, 57 secondsthe command exists, it's simply going to hide the command menu and it's going to return the entire command to the
48:0548 minutes, 5 secondsprovider. The entire command is basically this. So then the provider
48:1248 minutes, 12 secondswill see okay you have returned me this command does it have an action if it does I'm going to execute it. So that's
48:2148 minutes, 21 secondshow it's going to work. We are not going to make this hook know exactly how to you know execute every single command.
48:2948 minutes, 29 secondsWe're just going to make it return to the provider.
48:3448 minutes, 34 secondsAnd now we get to I think the most complicated part which is arrow keys to
48:4048 minutes, 40 secondsmove the selection. So right now you can I mean you can't do anything
48:4848 minutes, 48 secondsyet. I'm showing you the finished result. But you can see how easy it is to you know control the scroll box component from open 2 with your cursor.
48:5848 minutes, 58 secondsBut we also wanted to do with your keyboard. It looks simple because you're used to web components, but none of this
49:0649 minutes, 6 secondsis actually built in. We have to develop this experience from zero. So that's why
49:1449 minutes, 14 secondswe are now going to use the use keyboard hook.
49:2249 minutes, 22 secondsSo let's first check if the show command menu is false, we can do an early
49:2849 minutes, 28 secondsreturn. If the key pressed is escape, we can do an early return.
49:3649 minutes, 36 secondsBut if the key pressed is the up key,
49:4349 minutes, 43 secondsin that case we should do something else. We can again prevent default and
49:5049 minutes, 50 secondsthen we should call set selected index and open up a function.
50:0050 minutesNow in here let's go ahead and define the new index.
50:0550 minutes, 5 secondsSo using math domax the first value is zero. The second value is the current
50:1350 minutes, 13 secondsnumber minus one. And let's go ahead and add a little comment here. Keep the highlighted item visible when arrowing
50:2050 minutes, 20 secondspast the edge. Let's find the scroll bar. And if scroll bar exists and the
50:2750 minutes, 27 secondsnew index is less than scroll bar scroll top value, in that case scroll bar
50:3650 minutes, 36 secondsscroll to the new index. I'm not going to pretend like this is crystal clear.
50:4350 minutes, 43 secondsuh it's just easier to understand by looking at it. Basically, it's one of these two. Uh right now, we are
50:5050 minutes, 50 secondstargeting key up. So to demonstrate, I'm going to go to the bottom. You can see that when I go up after models, I scroll.
51:0151 minutes, 1 secondI scroll again. And now we have to develop the same for down. So that's what this function is doing. It's just not that clear. It's complicated, you
51:1051 minutes, 10 secondsknow, scrollable calculation code. It's not really fun. Uh, and let's just return the new index.
51:1751 minutes, 17 secondsAnd now we have to do uh a similar thing for down key. So again we are preventing default.
51:2851 minutes, 28 secondsWe are going to open this set selected index.
51:3551 minutes, 35 secondsLet's first check if the filtered commands length of zero and then return back zero. Otherwise, let's calculate
51:4251 minutes, 42 secondsnew index again but in the opposite way because we are scrolling down now. Let's
51:4951 minutes, 49 secondsfind the scroll bar again. If we have the scroll bar, let's go ahead and define the viewport height.
51:5951 minutes, 59 secondsThen let's check if there is a visible end with the combined scroll bars scroll
52:0752 minutes, 7 secondstop plus viewport height minus one which is a buffer. And then let's do an if clause to check if new index is greater
52:1652 minutes, 16 secondsthan the visible end. And finally, scroll too. Again, not fun to develop,
52:2452 minutes, 24 secondsbut it is necessary to have a nice experience. Uh, and as I said, so this is exactly the opposite. This is if we
52:3352 minutes, 33 secondsare at the top uh and we go down, it pushes the thing down. That's what that is. Again, you don't have that yet.
52:4352 minutes, 43 secondsWe're going to connect it in a second.
52:4652 minutes, 46 secondsAnd to wrap up the hook, we obviously have to return all of these. So make sure you return all of these.
52:5652 minutes, 56 secondsBrilliant. So now we can go back to the input bar and finally connect these. So input bar.dsx.
53:0653 minutes, 6 secondsLet me check uh what I am missing. So I'm going to import use ref, use callback, use effect. I'm going to import type text area renderable.
53:1953 minutes, 19 secondsI'm going to import use renderer from open toy react.
53:2453 minutes, 24 secondsI already have command menu but I don't have the command type. So I'm going to add that. And I'm also going to add use
53:3453 minutes, 34 secondscommand menu. And I already have the status bar. So that's solved. Now let's go inside of the input bar itself and
53:4253 minutes, 42 secondslet's add the following three elements text area ref onsubmit ref and the renderer itself.
53:5253 minutes, 52 secondsSo now what I want to do is I want to wire up the text area submit handler
54:0154 minutes, 1 secondonce so it always reads the latest state. So this is a trick I came up with with because whenever I was submitting
54:0954 minutes, 9 secondstext area, I just couldn't get the latest value from it. So this is how I ended up this is what I ended up having
54:1654 minutes, 16 secondsto do to be able to read that. And we just have to register this onsubmit ref.
54:2354 minutes, 23 secondsSo let's just do this onsubmit ref.curren. If disabled return if show command menu const command comes from
54:3254 minutes, 32 secondsresolve command and then simply call handle command otherwise handle submit.
54:3854 minutes, 38 secondsI I will explain what this is in a second. I just want to get rid of the errors and we can get rid of the errors
54:4454 minutes, 44 secondsvery simply by just calling this big hook use command menu and just extract
54:5254 minutes, 52 secondseverything from it. All right. All right, handle command is not yet developed, nor is handle submit. So what
55:0055 minutesdoes this do? Well, first of all, if the user attempts to submit using the text area, what happens? Well, if it's
55:0855 minutes, 8 secondsdisabled, nothing. If the show command menu is opened, then we're not going to submit, but we are just going to execute
55:1655 minutes, 16 secondsthe command. But if the show command menu is not open, then we're going to
55:2255 minutes, 22 secondssubmit. Right? So when I go ahead and do submit this, it will submit it. But if I
55:2955 minutes, 29 secondsgo ahead and press enter now, it doesn't submit it. It just executes the command. Okay.
55:3855 minutes, 38 secondsSo now uh let's go ahead and develop these one by one. So how about we do
55:4555 minutes, 45 secondshandle command? I'm going to go ahead and do that here. So use callback.
55:5255 minutes, 52 secondsWe need to define a function and we need a dependency array.
55:5955 minutes, 59 secondsSo what use callback is going to accept here is a command with a type of command or undefined.
56:0756 minutes, 7 secondsIf we have no text area or if we have no command, let's do an early return here.
56:1456 minutes, 14 secondsThen let's go ahead and change the text area text. And then let's go ahead and check if we have command.action.
56:2456 minutes, 24 secondsIf we have command.action, we are going to execute that action. But in order for the action to work, we have to expand its context.
56:3656 minutes, 36 secondsFor example, our current command exit expects an exit function. The reason
56:4456 minutes, 44 secondsthere is no error here is because we have defined the command context to have it. But right now the action doesn't
56:5256 minutes, 52 secondsreally have the exit. So let's go ahead and add it for that command.
57:0057 minutesSo renderer.destroy destroy and just like that we have added context to our command and then our
57:0957 minutes, 9 secondscommand can access that context and fire it. Let's go ahead and add an else here.
57:1557 minutes, 15 secondsSo what if there is no action defined for a command because that's a type of command as well. Well, I'm just going to
57:2357 minutes, 23 secondsinsert it into the text area and add a white space at the end. That's it.
57:2957 minutes, 29 secondsThat's all I'm going to do. And let's add renderer here.
57:3557 minutes, 35 secondsUh, and I feel like I'm doing something wrong here. Okay, now all good. Handle command finished. Now we need handle submit.
57:4957 minutes, 49 secondsSo I'm going to go ahead and develop that above handle command here. This one will be pretty similar as well in a sense that it is also a use callback.
58:0158 minutes, 1 secondIt's not going to accept any props. It's just going to check if disabled. Let's do an early return. If text area ref not
58:0958 minutes, 9 secondsfound, early return. If text value when trimmed is empty, early return.
58:1658 minutes, 16 secondsOtherwise, let's call the actual onsubmit function which we are passing through the prop.
58:2358 minutes, 23 secondsand pass along the text. And once we submit, let's clear the value of the text area. And in the props here, let's add disabled and onsubmit.
58:3558 minutes, 35 secondsGreat. So, we now have pretty much all the functions we need, but we don't have
58:4258 minutes, 42 secondsa way to keep track of the value of the text area. For that uh we need a
58:4958 minutes, 49 secondsfunction called handle text area content change. So let's go ahead and develop
58:5658 minutes, 56 secondsthat one as well. I'm going to do it here. Again it's a use callback
59:0659 minutes, 6 secondsand I'm going to go ahead and again check if we have text area. If we don't let's do an early return. And then let's
59:1559 minutes, 15 secondssimply call handle content change and pass along text area plain text. And then the handle content change here is
59:2359 minutes, 23 secondsgoing to do what it needs to do. Meaning that it's either going to show the command menu or hide the command menu
59:3159 minutes, 31 secondsdepending on what the user is typing. So we are just going to pass along whatever text area has received. And we're just
59:4059 minutes, 40 secondsgoing to go ahead uh and let the use command menu hook decide should I open the command menu
59:4759 minutes, 47 secondsfor that or should I not open the command menu for that. Basically, it's looking for a forward slash.
59:5459 minutes, 54 secondsUh and the reason this functions seem complicated is because we have to access them through the ref to read their
1:00:041 hour, 4 secondsvalues because otherwise the values keep being stale. At least that was the case for me when I was developing. Uh so in case you're wondering like why am I
1:00:121 hour, 12 secondsdoing so many checks of these areas like why don't I just keep track of the value. Uh it just caused bugs for me. So I'm just staying true to my source code.
1:00:211 hour, 21 secondsBut obviously feel free to experiment.
1:00:231 hour, 23 secondsIt is encouraged. It is even better if you don't have the same project as me if you have something different. Uh brilliant. So now that we have handle
1:00:321 hour, 32 secondstext area, content change, we can actually add it to the text area. So on
1:00:401 hour, 40 secondscontent change, handle text area, content change, we have the key bindings, but we don't have the ref. So
1:00:481 hour, 48 secondslet's add the ref. And then we can extend our command menu here with all
1:00:551 hour, 55 secondsthe props uh except handle command execute. So we didn't develop all of them. My apologies. But all of these
1:01:031 hour, 1 minute, 3 secondsother ones come from the use command menu hook. Okay. So that's why we have them.
1:01:091 hour, 1 minute, 9 secondsOkay. Let me see what this function is.
1:01:121 hour, 1 minute, 12 secondsHandle command execute. Uh okay. Let's go ahead and just develop it.
1:01:241 hour, 1 minute, 24 secondsconst handle command execute is use callback
1:01:321 hour, 1 minute, 32 secondsand let me just go ahead and add an empty array.
1:01:391 hour, 1 minute, 39 secondsAll right, it's going to accept an index which is a type of number
1:01:471 hour, 1 minute, 47 secondsand then in here it's going to find the command using the resolve command
1:01:561 hour, 1 minute, 56 secondsand then it's simply going to forward it to the handle command which can execute
1:02:031 hour, 2 minutes, 3 secondsthe command itself. So we're doing some jumping through the hoops here. Let me dive into the resolve command.
1:02:141 hour, 2 minutes, 14 secondsSo in here, it's just checking if we have it through here. I'm
1:02:231 hour, 2 minutes, 23 secondstrying to understand why we are hooping through hoops like that here. I think there is a reason. I ended up doing it
1:02:301 hour, 2 minutes, 30 secondsthis way, but I don't know how to explain myself at the moment. Um, let's
1:02:371 hour, 2 minutes, 37 secondsjust leave it at this. Okay. The only thing left to fix right now is this
1:02:441 hour, 2 minutes, 44 secondshardcoded true. So, instead of the hardcoded true, this should be show command menu like this.
1:02:541 hour, 2 minutes, 54 secondsAnd I think that if I go ahead and type a forward slash, I can now see my commands. The only problem is we can't
1:03:041 hour, 3 minutes, 4 secondsreally demonstrate whether all of that uh keyboard things are working because our commands are pretty shallow right
1:03:121 hour, 3 minutes, 12 secondsnow. So I'm going to go ahead and just add every single one of them. So in
1:03:201 hour, 3 minutes, 20 secondsbetween new and exit we have usage, upgrade, logout,
1:03:271 hour, 3 minutes, 27 secondslogin, oops, theme, sessions, models, and agents.
1:03:381 hour, 3 minutes, 38 secondsThose are all of the commands we're going to have right now. The only one with action is the exit command. So if
1:03:451 hour, 3 minutes, 45 secondsyou try and use agents, you will just, you know, have it added to your uh text here.
1:03:541 hour, 3 minutes, 54 secondsIf you try uh the arrow keys, all of them should be working. You can scroll with your arrow
1:04:011 hour, 4 minutes, 1 secondkeys just as easily as with your cursor, your mouse. If you hit exit, it should
1:04:081 hour, 4 minutes, 8 secondsimmediately execute that because that's the only kind of context provider that we have at the moment. Uh, brilliant.
1:04:171 hour, 4 minutes, 17 secondsThat is, I believe, everything we wanted to achieve. That was the big one. I kind of purposely wanted us to experience a
1:04:251 hour, 4 minutes, 25 secondsmore complex implementation of Open Tui just so you can kind of get the feel of developing with it. But don't worry, not
1:04:331 hour, 4 minutes, 33 secondseverything is this complicated. In fact, the command menu is one of the most complicated components in the entire uh
1:04:401 hour, 4 minutes, 40 secondsapp. I mean, simply experience-wise, it's it's not complicated in a sense that it has some magic functionality.
1:04:491 hour, 4 minutes, 49 secondsIt's just hard, you know, to get that experience right. Uh the entire UX and
1:04:551 hour, 4 minutes, 55 secondsUI is obviously expire inspired by open code and I've been so amazed by how much better open codes coding agent is in
1:05:051 hour, 5 minutes, 5 secondscomparison to cloud code or codex right so you can definitely feel the high quality in their terminal coding agents
1:05:131 hour, 5 minutes, 13 secondsand that's what I want to teach you to do or at least my uh way of how I would do it uh because I'm really really
1:05:211 hour, 5 minutes, 21 secondsimpressed by it. Brilliant. So, uh I'm just going to go ahead and double check that we did everything we were supposed
1:05:281 hour, 5 minutes, 28 secondsto do and then we're going to create a new branch uh and commit these changes.
1:05:351 hour, 5 minutes, 35 secondsSo, there is just one tiny thing we could potentially do. You don't even have to do it, but maybe we can. Uh so,
1:05:441 hour, 5 minutes, 44 secondsinside of the create CLI renderer, let's go ahead and add target FPS to be 60.
1:05:521 hour, 5 minutes, 52 secondsAnd let's add exit on Ctrl C and set it to false. So now you can no longer exit
1:05:591 hour, 5 minutes, 59 secondswith Ctrl C. You can only exit with the exit command. But that's not going to be the case. The reason I'm turning this
1:06:081 hour, 6 minutes, 8 secondsoff is because we are going to implement something called a keyboard layer. Uh basically a registry of which component
1:06:161 hour, 6 minutes, 16 secondsowns the screen. Again, that's something you have to implement when working with a TUI app which has dialogues, right?
1:06:241 hour, 6 minutes, 24 secondsYou have to know which one owns the keyboard. On the web, all of that is solved for you with native elements with
1:06:301 hour, 6 minutes, 30 secondsHTML. But in TUI, you have to develop it yourself. So, it's an interesting challenge for you to kind of reimplement
1:06:381 hour, 6 minutes, 38 secondsweb components from from nothing from scratch. So the way this is going to work, we are going to manually write code for what Ctrl C is going to do.
1:06:501 hour, 6 minutes, 50 secondsThat's why I'm turning it off. Not because I don't want it to be able to close the app. It will close the app, but only after it confirms that, for
1:06:591 hour, 6 minutes, 59 secondsexample, nothing was written in the input. If it is, and if it presses Ctrl C, it should clear the entire input. If
1:07:081 hour, 7 minutes, 8 secondsthe command menu is open and then the user hits control C, it should close the command menu. If a dialogue is open, it should close the dialogue first and only
1:07:181 hour, 7 minutes, 18 secondsthen only when we are back to the base layer and then the user hits Ctrl C which would be now for example I'm
1:07:251 hour, 7 minutes, 25 secondspressing it now but it's not doing anything in the next chapter or maybe in the subsequent chapters we are going to implement uh programmatic code to
1:07:351 hour, 7 minutes, 35 secondsactually close this. Brilliant. I'm super satisfied. And it looks exactly uh as the end result, which is exactly what
1:07:441 hour, 7 minutes, 44 secondswe wanted, right? Why would there be any differences? Uh, brilliant. Let's go ahead uh and commit all of these
1:07:521 hour, 7 minutes, 52 secondschanges. So, we do have a lot of our changes here. So, the last thing that
1:07:591 hour, 7 minutes, 59 secondswas here is just, you know, get ignore and read me. So what I'm going to do now is I'm just going to go ahead and open a
1:08:061 hour, 8 minutes, 6 secondsbranch called project setup and component architecture. So let me go ahead and exit
1:08:161 hour, 8 minutes, 16 secondsget checkout-b01 project setup and component architecture. The idea is that basically
1:08:231 hour, 8 minutes, 23 secondswe have every chapter under a branch so that we can easily go back and see our progress and so that you when you are
1:08:311 hour, 8 minutes, 31 secondswatching this tutorial and looking at my source code you can see exactly when I implemented what. So if you want to go uh back to this branch you can just
1:08:381 hour, 8 minutes, 38 secondsselect this branch and you will see all of these changes that we just did and I would suggest you do the same so it's kind of easier for you to keep track of
1:08:461 hour, 8 minutes, 46 secondswhat happened. So this is our chapter 1 project setup and component architecture. So I'm creating a branch here and then I'm going to go ahead and
1:08:541 hour, 8 minutes, 54 secondsadd all of these. I'm going to commit and I'm going to do the same thing 01 project setup and component
1:09:021 hour, 9 minutes, 2 secondsarchitecture like this. And you can see that right now I am on this new branch.
1:09:081 hour, 9 minutes, 8 secondsAnd you can also see the same branch here in my IDE.
1:09:141 hour, 9 minutes, 14 secondsSo now I'm going to do git push- origin01 project setup component
1:09:201 hour, 9 minutes, 20 secondsarchitecture which will push the branch uh to my GitHub here. And now I can create a pull request. If it's not
1:09:291 hour, 9 minutes, 29 secondsappearing here for whatever reason, you can manually go in pull request, click new pull request, select base main, and
1:09:361 hour, 9 minutes, 36 secondscompare your new branch and then create a pull request. And now we're just going to review the changes.
1:09:451 hour, 9 minutes, 45 secondsMy poll requests are reviewed by Code Rabbit. Code Rabbit is an AI code reviewer which you can get by using the
1:09:551 hour, 9 minutes, 55 secondslink on this screen. You can get it completely for free and connect it to your GitHub with a two-click install and
1:10:041 hour, 10 minutes, 4 secondsevery single subsequent pull request will be reviewed uh by code rabbit. You can use it to create diagrams to find
1:10:131 hour, 10 minutes, 13 secondsserious serious bugs and even brainstorm off or teach it something new if it made
1:10:211 hour, 10 minutes, 21 secondsa mistake. But what's most impressive will actually come to light later. The more pull requests we have, the better code rabbit understands our codebase.
1:10:321 hour, 10 minutes, 32 secondsSo, Code Rabbit will actually reference this pull request in maybe our ninth pull request because it knows that there
1:10:411 hour, 10 minutes, 41 secondsis a potential conflict or something like that. So, it's a really amazing tool that has become a daily part uh of
1:10:491 hour, 10 minutes, 49 secondsmy pull request reviewing. And when when doing this types of project yourself, it's actually very important that you
1:10:581 hour, 10 minutes, 58 secondshave another pair of eyes take a look at your code. Uh so let's take a look at everything code rabbit found because it
1:11:041 hour, 11 minutes, 4 secondsalready found a major issue. So summary, we added a command pallet interface. We introduced keyboard navigation within
1:11:121 hour, 11 minutes, 12 secondsthe command menu. We added an interactive input bar supporting command execution. And we implemented the CLI header with branding and status
1:11:211 hour, 11 minutes, 21 secondsinformation display. And in here we have a minor mistake. We shouldn't be returning commands just like this.
1:11:311 hour, 11 minutes, 31 secondsInstead, it is proposing to return a shallow copy of it just in case something mutates the returned list. So
1:11:391 hour, 11 minutes, 39 secondsthat's a good tip. For example, this is minor, right? It's not something that's going to break the code, but it's a good suggestion. Down here on the other hand,
1:11:481 hour, 11 minutes, 48 secondswe have a major uh suggestion. It says that we have forgotten to add anything to our dependency array, which is true.
1:11:571 hour, 11 minutes, 57 secondsWe don't have anything in handle command execute. Uh but I'm pretty sure handle command execute should have both resolve
1:12:061 hour, 12 minutes, 6 secondscommand and handle command added to its dependency arrays. Otherwise, it
1:12:131 hour, 12 minutes, 13 secondswouldn't work. In here, it told me that uh I should have a proper onsubmit, but we can skip this recommendation simply
1:12:221 hour, 12 minutes, 22 secondsbecause we know that that's currently not what we are implementing. In here, it's warning us that we turned off uh a
1:12:291 hour, 12 minutes, 29 secondsvery standard uh exit mechanism, but I explained previously that we are going to enable it just in a different way. So
1:12:391 hour, 12 minutes, 39 secondsthis one is actually very very important. Uh I'm going to resolve it
1:12:451 hour, 12 minutes, 45 secondsthe following way. So if you already merged your pull request or decided not
1:12:511 hour, 12 minutes, 51 secondsto follow uh pull request architecture then you can just do it in the next session. It really doesn't matter. But
1:13:001 hour, 13 minutesfor example let me go inside of components here. Uh command menu. My apologies not command menu. This will be
1:13:081 hour, 13 minutes, 8 secondsinput bar. And let's go ahead and let's find the handle.
1:13:141 hour, 13 minutes, 14 secondsWhere is it? Handle command execute. So we are missing resolve command and we are missing handle
1:13:241 hour, 13 minutes, 24 secondscommand uh blocked scope variable used before.
1:13:311 hour, 13 minutes, 31 secondsOkay, I see what's going on.
1:13:341 hour, 13 minutes, 34 secondsLet me move this below handle command.
1:13:411 hour, 13 minutes, 41 secondsThere we go. Just like that. So, one file changed. So, I'm going to go ahead and do the following. Get add
1:13:491 hour, 13 minutes, 49 secondsget commit 01 project setup and component architecture
1:13:581 hour, 13 minutes, 58 secondsPR fix. And then I'm just going to do get push because I'm already uh pushed
1:14:051 hour, 14 minutes, 5 secondsthe branch. And you can see that now that's going to re-trigger the pull request. Uh and if you have added code
1:14:151 hour, 14 minutes, 15 secondsrabbit, which I'm going to demonstrate now, you will see the updated or resolved comment.
1:14:241 hour, 14 minutes, 24 secondsAnd after the review goes through, you can see that now this is set to outdated, meaning that it was addressed
1:14:321 hour, 14 minutes, 32 secondsin a commit. So, Code Rabbit automatically marks something as resolved. I could have technically fixed
1:14:401 hour, 14 minutes, 40 secondsthis as well, but I think it's okay. I I don't think we ever mutate commands, but maybe in the next pull request, uh, I'm
1:14:471 hour, 14 minutes, 47 secondsgoing to do that as well. For now, I just want to close our first pull request. Let's go ahead and merge it.
1:14:541 hour, 14 minutes, 54 secondsLet's confirm merge. I'm not going to delete my branch. I think it's very useful for them to be here. So right now
1:15:021 hour, 15 minutes, 2 secondsmy main branch has all of the changes I have developed. But I can always go back to 01 which is now identical to main.
1:15:111 hour, 15 minutes, 11 secondsIt's one commit behind because that's the merge commit. But uh codewise it's identical. So then when we merge
1:15:181 hour, 15 minutes, 18 secondssubsequent pull requests in here we have a history and we can always go back to whatever state we want. What's important
1:15:261 hour, 15 minutes, 26 secondsnow is to check out main here and get pool origin main so that you are
1:15:341 hour, 15 minutes, 34 secondssynchronized right there we go and in here you should see all of the files now
1:15:411 hour, 15 minutes, 41 secondsare on the main branch. So, packages, CLI, source, components, command menu, everything is here. Just confirm you are
1:15:491 hour, 15 minutes, 49 secondson your main branch and try running this. If it works, everything is fine.
1:15:571 hour, 15 minutes, 57 secondsBrilliant, amazing, amazing job. So, that marks the end of this chapter. We implemented both steps. We got very
1:16:051 hour, 16 minutes, 5 secondsfamiliar with Open Tui and how we're going to build this terminal interface. and see you in the next chapter.
Chapter 4: UI Infrastructure
1:16:141 hour, 16 minutes, 14 secondsIn this chapter, we're going to develop the UI infrastructure. We're going to develop toasts, dialogues, theme system,
1:16:221 hour, 16 minutes, 22 secondsand even a keyboard layer. We're going to develop this in three steps. Step one is going to be toast notifications.
1:16:291 hour, 16 minutes, 29 secondsWe're going to have a toast provider, a toast component, and several variants like success, error, and info. And we
1:16:371 hour, 16 minutes, 37 secondswill be able to invoke them using toast.show. show and then some options inside and the notifications will automatically dismiss after 3 seconds.
1:16:481 hour, 16 minutes, 48 secondsIn step two, we're going to develop the dialogue and the keyboard layers which I'm going to explain more in a second
1:16:551 hour, 16 minutes, 55 secondswhen I show you the end result of this chapter. But it's basically uh a system to let us maintain which layer owns the
1:17:051 hour, 17 minutes, 5 secondskeyboard and the shortcuts in this ca in this case C.
1:17:111 hour, 17 minutes, 11 secondsWe will also have a theme system in step three. So, we're going to develop the actual theme provider, a theme dialogue,
1:17:181 hour, 17 minutes, 18 secondsand we're going to add uh color presets, which I'm going to show you how you can add yourself, or you can just copy all that I'm going to add. And we're going
1:17:271 hour, 17 minutes, 27 secondsto save them to night code preferences uh so user can well save their selected theme and it will load the next time they open up the CLI.
1:17:391 hour, 17 minutes, 39 secondsSo let me go ahead and show you uh the end result especially because of the keyboard layer thing.
1:17:471 hour, 17 minutes, 47 secondsSo what we currently have is the following. We have an ASI uh logo here
1:17:541 hour, 17 minutes, 54 secondsand we have the command menu which can be used to populate the text area with
1:18:011 hour, 18 minutes, 1 secondthe command value. What we cannot do at the moment is quit the app using Ctrl C.
1:18:101 hour, 18 minutes, 10 secondsWe also cannot close this command menu using any shortcuts as well. But in the
1:18:171 hour, 18 minutes, 17 secondsend result, it's going to be a little bit different. So let me show you. This is what we're going to have at the end of this chapter. We will be able to
1:18:251 hour, 18 minutes, 25 secondstrigger notifications like this. We will be able to open dialogues like this. And
1:18:321 hour, 18 minutes, 32 secondsthen we will be able to control which layer owns the keyboard. What does that mean? Well, for example, if I start
1:18:411 hour, 18 minutes, 41 secondstyping something and if I press Ctrl C, that will clear
1:18:481 hour, 18 minutes, 48 secondsthe input. If I have command menu open and if I type control C then it's not going to clear the input because there
1:18:561 hour, 18 minutes, 56 secondswas a layer above text area which owned the keyboard at the time or if I open a
1:19:051 hour, 19 minutes, 5 secondsdialogue again Ctrl C is not going to clear my input but it's going to close the dialogue instead and only if there
1:19:151 hour, 19 minutes, 15 secondsis no other layer that owns the keyboard we are going to allow the user to use Ctrl C uh to actually close the app. And
1:19:241 hour, 19 minutes, 24 secondsone more thing I didn't show you are the themes. So, we're going to develop all of these themes and it's going to be quite simple. And the reason we are
1:19:321 hour, 19 minutes, 32 secondsdoing it already is so we don't spend time uh modifying hardcoded hex colors later in the project. So, we are doing it relatively early into the project.
1:19:441 hour, 19 minutes, 44 secondsAll right. So let's go ahead and see uh how we are going to develop this. I want to start with obviously step one which is adding toast notifications.
1:19:561 hour, 19 minutes, 56 secondsSo, I'm going to go ahead inside of my project here and I'm going to go inside
1:20:021 hour, 20 minutes, 2 secondsof packages CLI source and then in here I'm going to create a new folder providers and then another folder types.
1:20:141 hour, 20 minutes, 14 secondsInside I will create types.ts.
1:20:181 hour, 20 minutes, 18 secondsAnd I made a little mistake with the naming here. It's not going to be called types. It's going to be called toast. I
1:20:251 hour, 20 minutes, 25 secondswas thinking of types so that's why I named the folder the same. So we are going to have a toast folder and then
1:20:321 hour, 20 minutes, 32 secondstypes file inside. The types are simply going to export everything we need to develop the actual toast component such
1:20:411 hour, 20 minutes, 41 secondsas the variant which is success error or info toast options consisting of message the variant we defined above and how
1:20:491 hour, 20 minutes, 49 secondslong the message should be shown as well as a default version of 3 seconds. Then let's go ahead and create the actual
1:20:571 hour, 20 minutes, 57 secondsprovider and the component within an index file. So in here I'm going to go ahead and start with adding some imports. Whoops.
1:21:061 hour, 21 minutes, 6 secondsSo let's go ahead and import create context, use context, use ref, use state, and use callback all from React.
1:21:161 hour, 21 minutes, 16 secondsThen let's import a type react node.
1:21:201 hour, 21 minutes, 20 secondsThen let's import use terminal dimensions from open TUI. Let's go ahead and import our newly created types toast options and toast variant from types.
1:21:321 hour, 21 minutes, 32 secondsLet's export the default duration from the types as well. And then let's export
1:21:381 hour, 21 minutes, 38 secondsthe toast context value. So our provider will allow us to have the show method
1:21:461 hour, 21 minutes, 46 secondswhich we can then trigger everywhere within the app as long as our app is wrapped within the toast provider. So now we're going to simply do the classic
1:21:551 hour, 21 minutes, 55 secondscomposition of React context. So let's develop the toast context and let's pass in the proper types inside. And then
1:22:031 hour, 22 minutes, 3 secondslet's go ahead and develop the use toast hook which will return toast context
1:22:101 hour, 22 minutes, 10 secondsvalue which is an object which has the show function inside. Inside of this hook we're going to attempt to extract
1:22:191 hour, 22 minutes, 19 secondsthe value using use context and passing along the toast context. And then we're going to check if it's not available.
1:22:261 hour, 22 minutes, 26 secondsAnd if it's not available we're going to throw an error. use toast must be used within the toast provider because if it's not available it means it wasn't
1:22:341 hour, 22 minutes, 34 secondsinitialized properly and to make the TypeScript errors go away we have to return the value itself. Now let's go
1:22:421 hour, 22 minutes, 42 secondsahead and define the actual props for the toast provider and let's go ahead and export function toast provider with
1:22:501 hour, 22 minutes, 50 secondsthe props we just mentioned. Let's go ahead and create a state to maintain the current toast. The type of that is going
1:22:591 hour, 22 minutes, 59 secondsto be toast options. So message variant and duration or null.
1:23:051 hour, 23 minutes, 5 secondsAnd let's go ahead and add a timeout handle ref. Now in here you might come across this error. Maybe you will, maybe
1:23:141 hour, 23 minutes, 14 secondsyou won't. I'm going to show you several ways you can fix this. So as you can see I have a problem with NodeJS timer uh
1:23:231 hour, 23 minutes, 23 secondsnamespace. So my NodeJS namespace seems to completely not exist within this project and which is kind of odd because
1:23:311 hour, 23 minutes, 31 secondsin my initial development I didn't have this problem. So here's one way we can fix this. We can go inside of base
1:23:381 hour, 23 minutes, 38 secondsconfig and we can add types and we can specify bun and once you save
1:23:461 hour, 23 minutes, 46 secondsthe file it goes away. That's one way of doing it. But since I didn't need to do this in the original project, I just
1:23:541 hour, 23 minutes, 54 secondscouldn't figure out, you know, why am I having a problem. Uh, and the way I debugged this is by opening this exact
1:24:031 hour, 24 minutes, 3 secondsproject in another editor of mine. And then I figured out, oh, the problem is VS Code. Because if I open it in Zed,
1:24:131 hour, 24 minutes, 13 secondsfor example, uh, in here I have no problem. This works, but in VS Code, there's a
1:24:201 hour, 24 minutes, 20 secondsproblem. And you can fix it by clicking on this curly brackets down here. And you can see that TypeScript version is 6.0.2.
1:24:281 hour, 24 minutes, 28 secondsAnd if I click select version, it will allow me to use VS codes version or to use my workspace version, my node
1:24:361 hour, 24 minutes, 36 secondsmodules TypeScript version, which is the one I actually want. So when I switch to that, it fixes it. So I think this would
1:24:441 hour, 24 minutes, 44 secondsbe a preferred fix. The only issue might be if you are working within a team and then all of you have to do this. So you
1:24:531 hour, 24 minutes, 53 secondswould most likely have to uh add like a VS code. I think it will automatically do this for you. VS Code settings.json
1:25:001 hour, 25 minutesand then in here like uh specify what TypeScript version you're using and that fixes those errors.
1:25:081 hour, 25 minutes, 8 secondsNow let's go ahead and develop the clear current timeout function. So it's a use callback which simply looks for the
1:25:151 hour, 25 minutes, 15 secondstimeout handle ref and it will clear the timeout and reset the ref and it will have no dev dependencies. Now let's
1:25:221 hour, 25 minutes, 22 secondsdevelop the actual show method. So this is going to be a use callback.
1:25:281 hour, 25 minutes, 28 secondsLet me go ahead and define that.
1:25:321 hour, 25 minutes, 32 secondsSo what we're going to have here are options. So let's go ahead and pass that as the prop. It's a type of toast options. And then we're going to see if
1:25:411 hour, 25 minutes, 41 secondsuser specified a duration. If it didn't, we're going to default to 3 seconds. And the first thing we're going to do is
1:25:481 hour, 25 minutes, 48 secondswe're going to clear if we have any active timeout. So let's immediately clear it. And then let's go ahead and set the current toast. Let's give it a
1:25:571 hour, 25 minutes, 57 secondsvariant. Again, check if user passed a variant. If it didn't, fall back to info. And this should error if you type
1:26:051 hour, 26 minutes, 5 secondssomething incorrectly. So it will very strictly follow the toast variant that we have defined. So it can either be
1:26:111 hour, 26 minutes, 11 secondssuccess, error or info and then we just spread the rest of the options and we pass along the duration. And now we have
1:26:191 hour, 26 minutes, 19 secondsto start the timeout handle for this. So let's go ahead and add timeout handler ref.curren current equals set timeout
1:26:281 hour, 26 minutes, 28 secondsset current toast null pass in the duration dot unref and in the dev dependencies here we need clear current
1:26:371 hour, 26 minutes, 37 secondstimeout so a lot of things we've written here will be an error if you don't have an incorrect typescript version in your
1:26:441 hour, 26 minutes, 44 secondsIDE you can see if I switch back to VS codes version set timeout is the problem clear timeout is a problem everything is
1:26:521 hour, 26 minutes, 52 secondsa problem right so just make sure that you are using uh workspace version or that you add types bun in here. One of the two.
1:27:031 hour, 27 minutes, 3 secondsAll right. Now that we have that, let me go ahead and prepare the value that we're going to return from here. So value is a type of toast context value.
1:27:111 hour, 27 minutes, 11 secondsAnd we pass along the show function we have developed here. And then finally we can go ahead and just return the
1:27:191 hour, 27 minutes, 19 secondsprovider. So that's going to be toastcontext.provider.
1:27:231 hour, 27 minutes, 23 secondspass along the value children and then the toast component with current toast property of current toast. We don't have
1:27:311 hour, 27 minutes, 31 secondsthis component yet and we're going to develop it now. Let's go ahead and give it a type toast props. It is going to
1:27:391 hour, 27 minutes, 39 secondshave a singular prop which is the current toast which is basically the toast options. Let's go ahead and
1:27:471 hour, 27 minutes, 47 secondsdevelop the toast component. So here is that prop we were just talking about. Now let's see
1:27:541 hour, 27 minutes, 54 secondswhat the width of this toast should be using use terminal dimensions from open
1:28:001 hour, 28 minutesto react. Once we have the width, let's go ahead and check if we actually have a current toast to render. And if we
1:28:071 hour, 28 minutes, 7 secondsdon't, let's do an early return. And now let's go ahead and hardcode these variant colors. And let's give it a
1:28:151 hour, 28 minutes, 15 secondsstrict object type. So it needs to match the toast variant. So if you type a typo like this, it's going to show you an
1:28:221 hour, 28 minutes, 22 secondserror. So you can only define colors for the variants that we have which are success, error or info. And then let's
1:28:291 hour, 28 minutes, 29 secondsgo ahead and do the same thing. Uh once again, I mean not exactly the same thing. I meant to say let's use this map
1:28:361 hour, 28 minutes, 36 secondsinto border color definition. So if we have a variant past, let's go ahead and choose a variant from the variant colors. Otherwise, we're going to fall back to info coloring.
1:28:471 hour, 28 minutes, 47 secondsAnd now let's go ahead and return uh the actual JSX the actual look for this. So
1:28:541 hour, 28 minutes, 54 secondswe're going to develop this uh within a box here. And it's going to have a bunch of attributes.
1:29:011 hour, 29 minutes, 1 secondSo the first three are going to be position, justify content, and align items. Then we're going to have top and right. Then we're going to go ahead and calculate the width using math max.
1:29:121 hour, 29 minutes, 12 secondsLet's go ahead and add some padding. So, we're going to have padding left, right, top, and bottom. Let's go ahead and
1:29:201 hour, 29 minutes, 20 secondsspecify the background color. Let's go ahead and add the dynamic border color.
1:29:271 hour, 29 minutes, 27 secondsAnd let's go ahead and specify the border, which is going to be left or right.
1:29:341 hour, 29 minutes, 34 secondsAnd then inside of this box, let's render another box with a flex direction and gap as well as the width. And
1:29:411 hour, 29 minutes, 41 secondsfinally, a text element with foreground of this hex color, which is kind of a grayish white wrap mode word with 100%
1:29:511 hour, 29 minutes, 51 secondsand render the toast message inside. And I'm going to go ahead and add uh a
1:29:581 hour, 29 minutes, 58 secondscomment to do add split border just so I don't forget about this. Uh all right.
1:30:071 hour, 30 minutes, 7 secondsNow that we have developed the component and the provider, what we can do is we can go back instead
1:30:141 hour, 30 minutes, 14 secondsof source index.tsx and we can import toast provider
1:30:231 hour, 30 minutes, 23 secondsand we can now render the toast provider and
1:30:291 hour, 30 minutes, 29 secondsencapsulate our entire application within it.
1:30:351 hour, 30 minutes, 35 secondsAnd uh I don't think that at the moment we can trigger it in any way because what we have to do is we have to go
1:30:421 hour, 30 minutes, 42 secondsinside of the input bar and then inside of here after the renderer let's add
1:30:491 hour, 30 minutes, 49 secondstoast from use toast which we can now import from providers toast. And once we have it we can find our command
1:30:581 hour, 30 minutes, 58 secondsexecution here. And here it is. So now I'm going to add toast here. As simple as that.
1:31:051 hour, 31 minutes, 5 secondsAnd let's not forget to add toast to the uh dependency array.
1:31:121 hour, 31 minutes, 12 secondsNow what we have to do is we have to go inside of the command menu and go inside of the types of the command menu and we have to expand the command context and
1:31:201 hour, 31 minutes, 20 secondsallow it to accept toast which is basically uh toast context value which you can import from providers toast.
1:31:301 hour, 31 minutes, 30 secondsAnd now what we have to do is we have to actually make some uh commands trigger
1:31:381 hour, 31 minutes, 38 secondsthe toast. So let's go inside of commands.tsx like the new one and let's add an action context. And now we can access
1:31:461 hour, 31 minutes, 46 secondscontext.toast show message starting new conversation. Let's save the file and let's try it out. So if I click on new,
1:31:541 hour, 31 minutes, 54 secondsthere we go. starting new conversation and you could go ahead and add a variant
1:32:021 hour, 32 minutes, 2 secondshere make it error and then you will see that in action as well. Uh so this is
1:32:091 hour, 32 minutes, 9 secondshow it looks like when it's in error mode and you can also try success mode.
1:32:161 hour, 32 minutes, 16 secondsLet me go ahead and add success. Whoops.
1:32:221 hour, 32 minutes, 22 secondsHere it is. Perfect. works like a charm.
1:32:261 hour, 32 minutes, 26 secondsI'm just going to bring this back to be a usual one. And then I'm just going to add uh a bunch of actions for all of my commands.
1:32:381 hour, 32 minutes, 38 secondsUh you you can do that if you want to just so all of them are kind of doing something because we don't really have
1:32:471 hour, 32 minutes, 47 secondsany actions for them now. So we have log in, then we have log out,
1:32:561 hour, 32 minutes, 56 secondsthen we have upgrade, and then we have the last one, uh, which is the usage. So
1:33:041 hour, 33 minutes, 4 secondsthe only one that doesn't have an action at the moment is this one. So now every single one of your command should be uh,
1:33:121 hour, 33 minutes, 12 secondsshowing you something. Great. Pretty cool. Now, uh, I want to go back to my providers toast index.tsx.
1:33:251 hour, 33 minutes, 25 secondsAnd I just want to show you what I meant, uh, by this right here. So,
1:33:331 hour, 33 minutes, 33 secondsuh, to do add split border. Uh, so I'm not sure if you even notice, but the way
1:33:411 hour, 33 minutes, 41 secondsthis border is rendered and the way this border is rendered is a little bit different. This one is kind of thicker and it looks better. So, it's basically
1:33:491 hour, 33 minutes, 49 secondsthe same cosmetic change that we did for this line right here. I purposely left it out to demonstrate that you don't
1:33:571 hour, 33 minutes, 57 secondshave to add this at all. Uh simply because uh you need to have border.tsx
1:34:051 hour, 34 minutes, 5 secondsdsx in your components which includes this odd character which I don't really know how you can find except by copying
1:34:121 hour, 34 minutes, 12 secondsand pasting from my or open codes um source code. So I just want to let you know that it's completely optional. You
1:34:191 hour, 34 minutes, 19 secondsdon't need it. Uh but if you want to make the border of the toast thicker,
1:34:261 hour, 34 minutes, 26 secondswe have to import split border uh character from components border
1:34:351 hour, 34 minutes, 35 secondsuh split border. My apologies. Uh it's split border like this.
1:34:441 hour, 34 minutes, 44 secondsAnd then down here, let's add custom border characters split
1:34:541 hour, 34 minutes, 54 secondsborder. Looks like there's a mistake here. Let me just check what I'm doing incorrectly.
1:34:591 hour, 34 minutes, 59 secondsAll right. So, I'm just going to briefly modify the split border that I have here. I'm going to simplify it like
1:35:081 hour, 35 minutes, 8 secondsthis. And I'm going to rename it to split border characters. Again, you don't have to do this. This is just co cosmetics.
1:35:191 hour, 35 minutes, 19 secondsAnd once you add this, you should have a thicker line here. If that's something you care about, feel free to do it.
1:35:261 hour, 35 minutes, 26 secondsOtherwise, the current implementation works just fine. So, that is step one finished. They are out of dismissing and we are able to call them through
1:35:351 hour, 35 minutes, 35 secondscommands using the context. Now, it's time for step two, which is basically the dialogue and the keyboard layers.
1:35:421 hour, 35 minutes, 42 secondsI'm going to start with developing the actual keyboard layer simply because we need some parts of it to develop the dialogue provider. So let's go inside of
1:35:511 hour, 35 minutes, 51 secondspackages source providers and let's create a new folder keyboard layer and inside let's add index.tsx.
1:36:031 hour, 36 minutes, 3 secondsLet's go ahead and import react and then create context. use context, use state, use callback, use ref all from react.
1:36:131 hour, 36 minutes, 13 secondsAnd from open two, we need use keyboard and use renderer. Let's go ahead and define the type for a responder, which
1:36:211 hour, 36 minutes, 21 secondsis basically a function which returns a boolean. And then let's develop the type keyboard layer context value. Now in
1:36:281 hour, 36 minutes, 28 secondshere, we're going to have push, pop, is top layer, and set responder. basically a set of functions that will allow us to
1:36:361 hour, 36 minutes, 36 secondsuse this API throughout our app. We're going to use push to add something to the layer. For example, when you open a
1:36:431 hour, 36 minutes, 43 secondsdialogue, we're going to push the dialogue to the layer stack so it's at the top of the layer. When we close the dialogue, we're going to pop it from the
1:36:511 hour, 36 minutes, 51 secondsarray so it's removed from the layer. So shortcuts no longer work on uh the dialogue. Is top layer is just a handy
1:36:581 hour, 36 minutes, 58 secondslittle util to help us define if something is a top layer. So we know whether the shortcut should be working on that layer and set responder is a
1:37:071 hour, 37 minutes, 7 secondssimilar helper to help us well set a responder. Now let's go ahead and define the keyboard layer context using create context. Pass along the type or null.
1:37:181 hour, 37 minutes, 18 secondsThen let's go ahead and define uh the keyboard layer provider. The only prop this provider will have are its children which are a type of react react node.
1:37:291 hour, 37 minutes, 29 secondsAnd then let's go ahead and define the stack using use state. It's basically going to be an array of strings. And by default, it's going to be an array with a single element inside called base.
1:37:391 hour, 37 minutes, 39 secondsThis is basically the home screen. Now let's go ahead and define the stack ref using ref. And let's go ahead and assign the stack ref.curren to be the stack.
1:37:491 hour, 37 minutes, 49 secondsLet's go ahead and create our responders. And let's make that a map.
1:37:561 hour, 37 minutes, 56 secondsSo there are no duplicates inside. So using a map is a very easy way to filter out any duplicates so that doesn't happen. Let's go ahead and define our
1:38:051 hour, 38 minutes, 5 secondsrenderer here. And then let's go ahead and define the push function. So this is going to be a use callback. So I need uh
1:38:141 hour, 38 minutes, 14 secondsthat the use callback will accept an ID in the first argument and the optional responder in the second argument. So what happens when the user pushes? First
1:38:231 hour, 38 minutes, 23 secondsthings first, we check if there is a responder being passed. If it is, we're going to add it to the current set of responders. I mean current map of
1:38:301 hour, 38 minutes, 30 secondsresponders. And we're going to map the key ID and the value of the responder.
1:38:361 hour, 38 minutes, 36 secondsAnd then we do a very easy set stack here. And we are going to open a callback here.
1:38:461 hour, 38 minutes, 46 secondsUh and basically we are getting the previous value or some some like to call this the current value. previous, current, whatever. We are going to
1:38:541 hour, 38 minutes, 54 secondsmodify it this way. So, we are going to check if the previous value already includes that stack. If it does, just
1:39:031 hour, 39 minutes, 3 secondsreturn it. Otherwise, we're going to uh add it to the list uh to the array. So,
1:39:111 hour, 39 minutes, 11 secondsif it includes, we're not going to add any duplicates because we have to do it this way because this is an array. We don't have to do it for the responders
1:39:191 hour, 39 minutes, 19 secondsas you can see because there will be no duplicates here. So that's the way we do that and nothing is needed in the
1:39:271 hour, 39 minutes, 27 secondsdependency array. And now we're going to do a pop method which is even simpler.
1:39:321 hour, 39 minutes, 32 secondsSo this one only accepts ID. So what element do we want to remove from the layer? Uh and we simply delete it from the responders and we filter it out from
1:39:411 hour, 39 minutes, 41 secondsour stack array. Now let's go ahead and develop the handy is top layer function.
1:39:481 hour, 39 minutes, 48 secondsSo is top layer is a use callback which accepts an id and it simply uh goes through the existing stack and if the
1:39:561 hour, 39 minutes, 56 secondsstack is zero uh or if the stack.length minus one is identical to the ID meaning
1:40:041 hour, 40 minutes, 4 secondsit's at the top of the array. So that way we can return a true value or a value of true back to this function.
1:40:141 hour, 40 minutes, 14 secondsGreat. Now let's go ahead and add a set responder here. So set responder is
1:40:201 hour, 40 minutes, 20 secondsgoing to be a use callback and in its arguments here it's going to accept an
1:40:291 hour, 40 minutes, 29 secondsID which is a type of string and a responder which is a type of responder.
1:40:381 hour, 40 minutes, 38 secondsLet me go ahead and open this and array.
1:40:421 hour, 40 minutes, 42 secondsIf there is a responder being sent, we are going to add it to the current ref,
1:40:491 hour, 40 minutes, 49 secondsthe current map and map it as ID and the value will be responder. Otherwise, we are simply going to delete it uh from
1:40:571 hour, 40 minutes, 57 secondsthe array from the map. And now let's go ahead and develop a single control plus
1:41:051 hour, 41 minutes, 5 secondsC handler that walks the responder chain. So this is what will keep track of what should control C be doing.
1:41:141 hour, 41 minutes, 14 secondsThat's why we uh turned it off from the index, right? That's why in here we set
1:41:211 hour, 41 minutes, 21 secondsit to false because we're going to programmatically do it now. So first things first, we let's immediately close
1:41:281 hour, 41 minutes, 28 secondsthis use keyboard hook if there is no control key being pressed or if the other key name is not C. But if it is,
1:41:371 hour, 41 minutes, 37 secondslet's go ahead and load the current stack. And then what we're going to do is we're going to do a loop over the
1:41:451 hour, 41 minutes, 45 secondsitems in our stack in the opposite direction because we need to go through the top ones. And let's go ahead and get the current layer ID.
1:41:551 hour, 41 minutes, 55 secondsThen let's go ahead and get the responder for that layer. And then finally, if we have a responder and if
1:42:021 hour, 42 minutes, 2 secondsit's executable, let's go ahead and do an early return.
1:42:071 hour, 42 minutes, 7 secondsAnd finally, outside of here, no responder handled it. Let's go ahead and exit. So what does this mean? What's a
1:42:161 hour, 42 minutes, 16 secondsresponder? So responder is a way for us to define what should control C do when
1:42:231 hour, 42 minutes, 23 secondsit when So let me try and explain. Uh I think I have to go back here. If I open
1:42:301 hour, 42 minutes, 30 secondsthe command menu and if I press Ctrl C, I want it to close. If I type something in the text area and I press Ctrl C, I
1:42:391 hour, 42 minutes, 39 secondswant it to clear. Those are two distinctively different actions. So the way to maintain what happens for each
1:42:491 hour, 42 minutes, 49 secondselement is by when we add it right when we push it to the layer we're also going to set the
1:42:581 hour, 42 minutes, 58 secondsresponder for that layer right so when we do pop we're going to get the ID and then we're going to register a responder
1:43:051 hour, 43 minutes, 5 secondswith the same ID and then we will be able to say all right so when the user
1:43:111 hour, 43 minutes, 11 secondspresses controll See, I want you to do this specific thing. So that's what we're doing here. Okay, we are simply
1:43:211 hour, 43 minutes, 21 secondsexecuting the responder. So if the if we decide that when we mount text area, we're going to set a responder saying
1:43:291 hour, 43 minutes, 29 secondswhen you press Ctrl C, I want you to clear the value. That's what I want you to do. I don't want you to close the app and I don't want you to do anything
1:43:371 hour, 43 minutes, 37 secondselse. Uh, alternatively, when we open a dialogue, we're going to register another responder where we're going to say, okay, when the user presses Ctrl C,
1:43:471 hour, 43 minutes, 47 secondsI want to close the dialogue. So, that's what a responder is. I hope I cleared that up because I kind of went fast through this. My apologies. Uh, but I think this kind of cleared it up, right?
1:43:571 hour, 43 minutes, 57 secondsBasically, whenever we register a new item in our layer, we are also going to register a responder so that we can
1:44:051 hour, 44 minutes, 5 secondscustomize the behavior. But if there is no responder being set, it means we can just close the app because nothing is
1:44:131 hour, 44 minutes, 13 secondscurrently owning uh the keyboard. Uh brilliant. And we can return back
1:44:201 hour, 44 minutes, 20 secondskeyboard layer context with provider and pass along the value prop. The value prop should have push pop is top layer
1:44:281 hour, 44 minutes, 28 secondsand set responder and render the children inside. And then at the end, let's just have a little hook use
1:44:351 hour, 44 minutes, 35 secondskeyboard layer, which will read the context. Keyboard layer context. And if there is no context available, it's going to throw an error. Use keyboard
1:44:441 hour, 44 minutes, 44 secondslayer must be used within a keyboard layer provider.
1:44:481 hour, 44 minutes, 48 secondsGreat. So now that we have that set, let's go ahead and register this
1:44:551 hour, 44 minutes, 55 secondsprovider. So I'm going to go inside of packages source index.tsx DSX and around the toast provider I'm going
1:45:041 hour, 45 minutes, 4 secondsto add keyboard layer provider like this. So now we can start registering our layer and registering the responders.
1:45:141 hour, 45 minutes, 14 secondsAnd now let's go ahead and develop the dialogue so we can see this in action.
1:45:201 hour, 45 minutes, 20 secondsUh or actually maybe it would be a good idea.
1:45:261 hour, 45 minutes, 26 secondsLet me see.
1:45:291 hour, 45 minutes, 29 secondsMaybe we can already do this. Let's go inside of source components input bar
1:45:361 hour, 45 minutes, 36 secondsand let's go ahead and find where we
1:45:431 hour, 45 minutes, 43 secondshere it is. Input bar. Let's add use keyboard layer from providers keyboard layer. Make sure you have is top layer and set responder.
1:45:551 hour, 45 minutes, 55 secondsAnd let's scroll down here.
1:45:581 hour, 45 minutes, 58 secondsuh after I think we can do it here. So before return let's do the following. So let's
1:46:081 hour, 46 minutes, 8 secondsregister the base layer responder for control + C dismissal. So we're going to register using use effect because that's
1:46:171 hour, 46 minutes, 17 secondsthe equivalent of onmount right. So when this component mounts what should happen? Well let's call set responder.
1:46:261 hour, 46 minutes, 26 secondsWe're going to register a responder called base. And what I want this responder to do is the following. I want
1:46:341 hour, 46 minutes, 34 secondsto first check if this is disabled. If it is, let's just do an early return.
1:46:401 hour, 46 minutes, 40 secondsOtherwise, what I want to do is I want to extract the text area here. And then
1:46:471 hour, 46 minutes, 47 secondsI'm simply going to check if text area container exists. And if I can
1:46:541 hour, 46 minutes, 54 secondsread its value and its length of that value is above zero, meaning something is written inside the responder should
1:47:021 hour, 47 minutes, 2 secondsclear the text area. And let's return true. Otherwise, let's simply go ahead and return false. And what's important is that we do an unmount function here.
1:47:141 hour, 47 minutes, 14 secondsSo let's call set responder base and set it to null. So we clear that and let's go ahead and add
1:47:231 hour, 47 minutes, 23 secondsdisabled and set responder in the uh dependency array. So if I type hello world now and Ctrl C, you can see it clears the value.
1:47:361 hour, 47 minutes, 36 secondsAnd after the value has been cleared, if you press Ctrl C again, it closes the app because nothing owns the responder
1:47:431 hour, 47 minutes, 43 secondsanymore. So that is how we're going to develop this. If if there is a value and
1:47:491 hour, 47 minutes, 49 secondswe press Ctrl C, the responder is right now registered for text area and it clears it. If I press again, it's no
1:47:581 hour, 47 minutes, 58 secondslonger registered. I mean, it is, but it doesn't match the conditions. What are the conditions? Well, these are the conditions. Text area plain text.length.
1:48:071 hour, 48 minutes, 7 secondsRight? So, that's how uh that is going to work. It could be a good idea to maybe standardize use effect and set
1:48:151 hour, 48 minutes, 15 secondsresponder into one hook like um use responder and then you can easily register components. But I mean it's
1:48:231 hour, 48 minutes, 23 secondsjust like two lines. It's not too difficult. But yeah, that could be a good idea to standardize this. All right. So that's how I demonstrated
1:48:321 hour, 48 minutes, 32 secondsthat. Uh and another cool thing that we can do now is we can do it w because of
1:48:391 hour, 48 minutes, 39 secondsthis because of is top layer. So down here we are currently only using if not
1:48:481 hour, 48 minutes, 48 secondsdisabled to allow this text area to be focused. But what we can do now is we can combine it. If not disabled and if
1:48:561 hour, 48 minutes, 56 secondsis top layer base or
1:49:041 hour, 49 minutes, 4 secondswhoops or is top layer command
1:49:121 hour, 49 minutes, 12 secondslike this. So what is the scenario uh when text area can be focused if it's
1:49:191 hour, 49 minutes, 19 secondsnot disabled and if the top layer in our layer stack or keyboard layer stack is
1:49:261 hour, 49 minutes, 26 secondsbase right now this is the scenario because the only uh responder
1:49:341 hour, 49 minutes, 34 secondsregistration we are doing is this one so it's only base so now I want to do the following I want
1:49:421 hour, 49 minutes, 42 secondsto go inside of the command menu. Uh I'm going to go inside of index.tsx
1:49:501 hour, 49 minutes, 50 secondsand I'm going to add keyboard layer from providers keyboard layer and I'm going to extract down here in the command
1:49:591 hour, 49 minutes, 59 secondsmenu. Uh let me see. Um do I want to do it here?
1:50:091 hour, 50 minutes, 9 secondsUh I think uh or sorry no I don't want to do it here. Let me remove this. Not here. Uh
1:50:181 hour, 50 minutes, 18 secondsuse command menu. This is what I meant to do. So make sure you are inside of the use command menu hook and import use keyboard layer.
1:50:291 hour, 50 minutes, 29 secondsThen after the scroll ref push pop and is top layer. And then what you can do here
1:50:381 hour, 50 minutes, 38 secondsuh is you can find where we set show command to true. And then we can go ahead and also push the command layer.
1:50:501 hour, 50 minutes, 50 secondsAnd let's go ahead and add a responder here. Uh set show command menu to false and then pop the command. So that's what
1:50:581 hour, 50 minutes, 58 secondshappens uh on unmount basically not on unmount on like close
1:51:051 hour, 51 minutes, 5 secondsand in here let's explicitly also pop the command. So whenever we open the command menu let's push it and then
1:51:131 hour, 51 minutes, 13 secondslet's pop it. Uh you can obviously see how this can be improved. For example, this is already sketchy. It's magic
1:51:211 hour, 51 minutes, 21 secondsstrings. If I add command one here, command two here, this is a broken component. So obviously it can be improved and standardized, but I think
1:51:301 hour, 51 minutes, 30 secondsyou get the gist what we're trying to do. We're adding a simplistic keyboard layer responder chain here. All right,
1:51:371 hour, 51 minutes, 37 secondslet's go ahead and find everywhere else where we uh close something. For example, after we select a command, let's also pop the command layer
1:51:461 hour, 51 minutes, 46 secondsentirely. Let's go ahead and find some other examples right here. If we press escape, let's also pop the command. So
1:51:541 hour, 51 minutes, 54 secondsobviously we could standardize this into a single function called close command menu and then that will set show command menu to false and pop the command. Feel
1:52:031 hour, 52 minutes, 3 secondsfree to do those improvements. Uh you know I'm here guiding you uh to a predefined path to completing this project but that doesn't mean you can you shouldn't do any improvements.
1:52:141 hour, 52 minutes, 14 secondsObviously feel free to uh standardize some things. I'm just going to stay true to my source code so it's easier for me to finish uh the project.
1:52:221 hour, 52 minutes, 22 secondsUh let's go ahead and see what else we have to do. I think that's all regarding popping.
1:52:291 hour, 52 minutes, 29 secondsNow let's go ahead uh and see uh what we should do next. So instead of use
1:52:371 hour, 52 minutes, 37 secondskeyboard here when we define a key let me go ahead and do this. So when should we do an early return? currently
1:52:451 hour, 52 minutes, 45 secondsif there is if the command menu is not shown but let's also explicitly listen
1:52:521 hour, 52 minutes, 52 secondsto the stack so if the command is not the top layer we also shouldn't register
1:52:591 hour, 52 minutes, 59 secondskeyboard shortcuts as well so that's the thing this seems super complex because usually you don't think about these things on the web but what does this
1:53:071 hour, 53 minutes, 7 secondsmean well it means this when I open the command menu I have keyboard shortcuts
1:53:141 hour, 53 minutes, 14 secondsThese are the shortcuts. But if for some reason command menu is open and also a
1:53:231 hour, 53 minutes, 23 secondsdialogue is open. Right now this is a scenario that doesn't exist because even in the finished example you can see when I open a dialogue the command menu
1:53:311 hour, 53 minutes, 31 secondscloses. But let's say that isn't the behavior. What would happen is the command menu would still receive these
1:53:411 hour, 53 minutes, 41 secondsevents up and down even though it makes no sense because we have a whole you know dialogue open. So that's why we
1:53:501 hour, 53 minutes, 50 secondshave to prevent the use keyboard hook from registering any of these if it's
1:53:571 hour, 53 minutes, 57 secondsnot the top layer. All right, that is uh what we are doing here. And we added a
1:54:041 hour, 54 minutes, 4 secondspop command here. And I think that uh we are good. So now
1:54:111 hour, 54 minutes, 11 secondsuh let's go ahead uh and let me demonstrate something to you. If we go back inside of the input
1:54:181 hour, 54 minutes, 18 secondsbar and you go down here and in the focused prop if you remove
1:54:251 hour, 54 minutes, 25 secondsthis part is top layer command. So just make it is top layer base.
1:54:311 hour, 54 minutes, 31 secondsWhat will happen then is that you can, you know, type here freely. But if I'm
1:54:371 hour, 54 minutes, 37 secondscorrect, once the command menu opens, notice how it's no longer focused. I can
1:54:441 hour, 54 minutes, 44 secondsno longer type. So, this just proves that we successfully uh created an API
1:54:511 hour, 54 minutes, 51 secondsthat allows us to keep track of what owns the keyboard. It's not perfect, but
1:54:581 hour, 54 minutes, 58 secondsI think you get the general idea. uh we have to implement this because it doesn't come built in in terminal apps.
1:55:061 hour, 55 minutes, 6 secondsWe have to develop our own responder chain. Great. So just make sure that you are allowing the user to type even if the command menu is open.
1:55:191 hour, 55 minutes, 19 secondsAnd now let's go ahead and develop uh the dialogue. I wanted to leave it last so we can kind of take in what we just
1:55:281 hour, 55 minutes, 28 secondsdeveloped and not just you know go uh quickly through it. I hope it's a bit clearer now why we need it. We will I
1:55:351 hour, 55 minutes, 35 secondswill go again through the changes just to kind of clarify but I think this demonstration kind of cleared it up. Uh
1:55:421 hour, 55 minutes, 42 secondsnow let's go inside of providers and let's create a new one called dialogue and let's define types.ts
1:55:501 hour, 55 minutes, 50 secondsts in here. We're going to add the React node dialogue config with title and children.
1:56:001 hour, 56 minutesAnd now let's go ahead and implement the dialogue provider.
1:56:061 hour, 56 minutes, 6 secondsI'm going to store that inside of an index file in the dialogue.
1:56:111 hour, 56 minutes, 11 secondsSo let's go ahead and add create context use context use state use callback react node type text attributes rgba from open
1:56:201 hour, 56 minutes, 20 secondsto a core use keyboard use terminal dimensions uh dialogue config from types and our newly created use keyboard
1:56:271 hour, 56 minutes, 27 secondslayer. Let's go ahead and define the values. So those are going to be open and close. This is the API that we will be able to use for example in commands.
1:56:381 hour, 56 minutes, 38 secondswe will have context and then we will do context dialogue.open or we will have context dot dialogue doc
1:56:471 hour, 56 minutes, 47 secondsclose. So that's what we are doing right now. We are defining the API. So just as we did three times already, let's define
1:56:551 hour, 56 minutes, 55 secondsthe dialogue context. Let's go ahead and do a very simple use dialogue function which attempts to read the value and if
1:57:041 hour, 57 minutes, 4 secondsit doesn't read it, it will warn the user that it must be using use dialogue within a dialogue provider. Let's define
1:57:121 hour, 57 minutes, 12 secondsthe props dialogue provider props and let's export the actual dialogue provider.
1:57:201 hour, 57 minutes, 20 secondsIn here, I'm going to go ahead and define the current dialogue in a state with the options of dialogue config or
1:57:261 hour, 57 minutes, 26 secondsnull. This is super similar to toast index.tsx.
1:57:331 hour, 57 minutes, 33 secondsSo, feel free to like copy most of it if you don't want to type it. Uh, I'm going to go, you know, through it one by one simply because there are some
1:57:411 hour, 57 minutes, 41 secondsdifferences because toast isn't interactive. So, for example, for dialogue provider, we need push and pop from use keyboard layer. Then let's go
1:57:491 hour, 57 minutes, 49 secondsahead and define the close method. So when we close a dialogue, we're going to set the current dialogue uh to null. And
1:57:581 hour, 57 minutes, 58 secondsthen we're going to pop the dialogue al together.
1:58:011 hour, 58 minutes, 1 secondAnd now let's go ahead and define the open function. So the open function will accept a prop called config and it's going to be basically title and
1:58:101 hour, 58 minutes, 10 secondschildren. And we're going to set the current dialogue to that config. And then we're going to push the dialogue
1:58:171 hour, 58 minutes, 17 secondslayer with a call back of the close method right here and an early return.
1:58:241 hour, 58 minutes, 24 secondsSo use keyboard layer and in here we have the push and as you can see this is
1:58:321 hour, 58 minutes, 32 secondsthe responder. So what happens on Ctrl C we are going to close the dialogue.
1:58:381 hour, 58 minutes, 38 secondsThat's what the second uh argument in push is. It's a quick way to
1:58:451 hour, 58 minutes, 45 secondsto define uh the responder on the let me go ahead and find
1:58:531 hour, 58 minutes, 53 secondsum in the input bar. We do it differently simply because this is the base layer.
1:59:011 hour, 59 minutes, 1 secondSo we are directly using the set responder API here.
1:59:081 hour, 59 minutes, 8 secondsTechnically, we could do it with um push as well, but no, we couldn't. Let
1:59:181 hour, 59 minutes, 18 secondsme tell you why we are using set responder here. I was thinking of maybe changing it, but not because in the keyboard layer, what is the default
1:59:271 hour, 59 minutes, 27 secondslayer? It's base. So, if we did push, it would attempt to add bass and then base
1:59:351 hour, 59 minutes, 35 secondsagain, which is incorrect. So that's why we are simply registering the responder without calling uh push and everywhere
1:59:451 hour, 59 minutes, 45 secondselse we are using push because this is only a specific case for base. All right. So now we have close and we have
1:59:531 hour, 59 minutes, 53 secondsopen for our dialogue provider here and we are using set current dialogue and then push dialogue and the responder. So what should happen on Ctrl C close.
2:00:062 hours, 6 secondsGreat. Now let's go ahead and uh define the value dialogue context value open and close.
2:00:172 hours, 17 secondsAnd finally, let's do a return. So dialog context provider with the value render the children and render the
2:00:242 hours, 24 secondsdialogue component which we don't have yet and we're going to develop now.
2:00:292 hours, 29 secondsand make sure you pass in the current dialogue which is basically the config and the close which controls the uh
2:00:352 hours, 35 secondslayer. So the dialogue props are those two which we just talked about and let's go ahead and define the function current
2:00:442 hours, 44 secondsdialogue and close. In here I'm going to add is top layer from use keyboard layer and then just as I did in toast I'm going to get the dimensions.
2:00:552 hours, 55 secondsI'm going to go ahead and open the use keyboard hook here and I'm going to check if the current dialogue is set and
2:01:042 hours, 1 minute, 4 secondsif uh the top layer is dialogue. So if either of those is not true, I'm going to do an early return, meaning I
2:01:122 hours, 1 minute, 12 secondsshouldn't register any shortcuts because either there is no dialogue open or the
2:01:192 hours, 1 minute, 19 secondsdialogue is open but something is uh owning the keyboard above it, right?
2:01:282 hours, 1 minute, 28 secondsMaybe an input within the dialogue, right? So if I have an input within my dialogue and I press Ctrl C, maybe I
2:01:372 hours, 1 minute, 37 secondswant to clear that input and not close the dialogue, right? So that's why we are doing that check. Otherwise, if the
2:01:442 hours, 1 minute, 44 secondstop layer indeed ease the dialogue, let's register the escape key here and let's close it.
2:01:532 hours, 1 minute, 53 secondsBefore we render anything, let's check if we can render null.
2:01:582 hours, 1 minute, 58 secondsAnd otherwise, let's extract the title and the children from the config.
2:02:052 hours, 2 minutes, 5 secondsLet's go ahead and return.
2:02:082 hours, 2 minutes, 8 secondsWe're going to add a box element here with position, left, top, width, and
2:02:152 hours, 2 minutes, 15 secondsheight, justify content, align items, background color, and we are using RGBA
2:02:222 hours, 2 minutes, 22 secondsfrom open to a core to create a transparent background color, kind of like an overlay. We are adding a z-index
2:02:292 hours, 2 minutes, 29 secondsso it is above everything and on mouse down we are calling close which will automatically pop the dialogue from the
2:02:372 hours, 2 minutes, 37 secondslayer so we don't have to worry about that. So this is basically what I maybe want to do in the com sorry use command
2:02:452 hours, 2 minutes, 45 secondsmenu because on so many places we are calling set show command menu to false and then
2:02:532 hours, 2 minutes, 53 secondsindividually pop command and then we do it again here and again here and again here. Right? So maybe we should just
2:03:022 hours, 3 minutes, 2 secondsdevelop the close one. Uh, okay. Let's go back and focus on the dialogue here.
2:03:102 hours, 3 minutes, 10 secondsUh, Zindex on mouse down. And then in here, let's go ahead and render another box. This box will control the width,
2:03:202 hours, 3 minutes, 20 secondsthe height, the background color of the actual dialogue because this is just the background, right? Padding, flex, gap,
2:03:282 hours, 3 minutes, 28 secondswhat happens on mouse down, which is just stop propagation.
2:03:322 hours, 3 minutes, 32 secondsAnd then let's go ahead and add another box which is basically just flex box with flex direction row align items
2:03:402 hours, 3 minutes, 40 secondscenter and justify content space between in here I'm going to add a text element
2:03:472 hours, 3 minutes, 47 secondsand then uh so this is for the title with bold text attributes and next to it I'm going to add an escape kind of
2:03:562 hours, 3 minutes, 56 secondsindicator. So we can either click on it and it's going to close using on mouse down or thanks to use keyboard hook we
2:04:052 hours, 4 minutes, 5 secondscan press down on that button and then very simply outside of this box
2:04:132 hours, 4 minutes, 13 secondswe are going to add a flex grow to the children. So that's the main content and that's what's going to be rendered in
2:04:202 hours, 4 minutes, 20 secondsthe end. All right. So now that we have that, we have to go back inside of CLI
2:04:302 hours, 4 minutes, 30 secondssource index.tsx and we have to add the dialogue provider. But be careful,
2:04:382 hours, 4 minutes, 38 secondsmake sure that you do it after keyboard layer provider because dialogue provider
2:04:462 hours, 4 minutes, 46 secondsis using use keyboard layer. So if you were to render this above, it would give
2:04:532 hours, 4 minutes, 53 secondsyou an error because use keyboard layer must be used within a keyboard layer provider.
2:05:012 hours, 5 minutes, 1 secondGreat. So we now have that. What I want to do next is go inside of the input bar.
2:05:122 hours, 5 minutes, 12 secondsLet me go inside of my components input bar. I want to find my command execution
2:05:222 hours, 5 minutes, 22 secondsand besides toast I'm now going to add dialogue
2:05:282 hours, 5 minutes, 28 secondsand I'm going to go here where I add use toast and I'm just going to add dialogue
2:05:352 hours, 5 minutes, 35 secondsuse dialogue and I'm going to import it from providers use dialogue. Now, this
2:05:422 hours, 5 minutes, 42 secondsis throwing an error because we didn't uh define the type. So, let's go inside
2:05:502 hours, 5 minutes, 50 secondsof the command menu types. And in here, I'm going to add dialogue dialogue context value. Just like that.
2:06:022 hours, 6 minutes, 2 secondsAnd now, let me go ahead and replace some of the commands. So, in commands.tsx, tsx I'm going to find
2:06:092 hours, 6 minutes, 9 secondsagents and I'm going to replace the action oh whoops I'm going to replace the toast action here
2:06:172 hours, 6 minutes, 17 secondswith context dialogue open title select uh mode agent selection coming soon
2:06:252 hours, 6 minutes, 25 secondsthen in the models I'm going to delete the toast and instead I'm going to use context dialogue open with select model
2:06:332 hours, 6 minutes, 33 secondsand model selection coming soon. So if I go ahead and select agents here it is and you can see that if I press Ctrl C
2:06:422 hours, 6 minutes, 42 secondsthat closes the dialogue. So let me try uh I'm not sure can I okay I can't yeah
2:06:492 hours, 6 minutes, 49 secondsI I wanted to demonstrate like a multiple scenario but for example let me show you let me show you why we need the
2:06:572 hours, 6 minutes, 57 secondskeyboard layer. This is a good way to learn inside of source components input bar. I'm going to go down here
2:07:072 hours, 7 minutes, 7 secondson focused and I'm going to remove this.
2:07:132 hours, 7 minutes, 13 secondsSo just if not disabled. Okay, like it was before. Watch what happens when I open a dialogue. I can still type behind.
2:07:242 hours, 7 minutes, 24 secondsThis is broken behavior. As you can see, I can do new lines.
2:07:302 hours, 7 minutes, 30 secondsThis doesn't happen on the web and you don't have to think about it because the responder chain is built in. It's native. It's the basics, right? But it's
2:07:382 hours, 7 minutes, 38 secondsdifferent here. In here, this concept doesn't exist. So, we have to implement
2:07:452 hours, 7 minutes, 45 secondsthis. Okay. Uh before I mark this step as completed, I really want to go inside
2:07:512 hours, 7 minutes, 51 secondsof the use command menu and let me just, you know, develop a const close, I guess.
2:08:042 hours, 8 minutes, 4 secondsLet me see.
2:08:072 hours, 8 minutes, 7 secondsAnd in the close, I'm going to go set show command menu set to false. And then I'm going to do pop command.
2:08:192 hours, 8 minutes, 19 secondsLet me see if that is correct. And can I now just call close?
2:08:282 hours, 8 minutes, 28 secondsCan I call close again? Right here. Here.
2:08:362 hours, 8 minutes, 36 secondsHere.
2:08:402 hours, 8 minutes, 40 secondsSomewhere else as well. I think I think that's all of it.
2:08:462 hours, 8 minutes, 46 secondsI feel like this is cleaner now. So, we don't have to repeat this three times because it's kind of I don't want to say
2:08:542 hours, 8 minutes, 54 secondsunsafe, but yeah. So, let's see. Uh, this should clear that value.
2:09:012 hours, 9 minutes, 1 secondCtrl C should clear that value.
2:09:062 hours, 9 minutes, 6 secondsOkay, basically a lot of things working properly now. Uh, it's up to you.
2:09:132 hours, 9 minutes, 13 secondsBasically, I would recommend having that close button. If you don't want to, you can also, you know, just have these
2:09:202 hours, 9 minutes, 20 secondsthree. Let me see how many of them it is. Set show command menu to false.
2:09:322 hours, 9 minutes, 32 secondsOkay. So, it's three of them, right? So, if you want to go ahead and develop this, let's go find the first one here.
2:09:412 hours, 9 minutes, 41 secondsReplace it with close. Find the second one.
2:09:472 hours, 9 minutes, 47 secondsReplace it with close.
2:09:502 hours, 9 minutes, 50 secondsFind the last one. Replace it with close.
2:09:562 hours, 9 minutes, 56 secondsSo now you should have only one set show command menu false and only one pop command.
2:10:072 hours, 10 minutes, 7 secondsGreat. So that is step three done.
2:10:142 hours, 10 minutes, 14 secondsUh my apologies. Step two done. And as we explained here, we now have a layer stack where the top always wins. And for
2:10:232 hours, 10 minutes, 23 secondsexample, we have a control C which now walks down. We are able to quit the app using Ctrl C. But if there is a top
2:10:312 hours, 10 minutes, 31 secondslayer, we are first going to look for the responder of that layer and decide what should happen. And then we're going to go down, down, down until we hit
2:10:392 hours, 10 minutes, 39 secondsbase. And once we hit base and there is no input in the text area, we finally close the app. Now let's go to step three, the theme system.
2:10:522 hours, 10 minutes, 52 secondsSo I understand that for some of you who are watching this, you're purely interested in the agentic coding aspect of this. So if you want to skip the theming system, uh feel free to do so.
2:11:032 hours, 11 minutes, 3 secondsBut keep in mind that we're going to develop an important component in step three. So I would suggest at least uh waiting until we do that. I'm going to
2:11:122 hours, 11 minutes, 12 secondstell you what component that is. Uh and then you will be able to just you know skip this theming if you don't like it.
2:11:202 hours, 11 minutes, 20 secondsSo what component is that? Well, let me show you a finished example of this chapter. So when I go into theme, I am able to open a dialogue which I can
2:11:292 hours, 11 minutes, 29 secondssearch through. I can select and I can also of course well I said it initially search through but I mean type filter
2:11:382 hours, 11 minutes, 38 secondsright and we're going to use this for various other uh dialogues like for agents for models for sessions all of
2:11:472 hours, 11 minutes, 47 secondsthose things will have the same search dialogue so that's the component that we're going to implement.
2:11:532 hours, 11 minutes, 53 secondsUh let's go ahead and do that first. So for those of you who don't want to add theming, you can just implement this
2:12:002 hours, 12 minutescomponent and then uh you can go to the next chapter. I would suggest at least saying till the end of the video maybe fast forward mode just so you don't miss like any uh important things.
2:12:142 hours, 12 minutes, 14 secondsAll right. So I'm going to go inside of components and I'm going to create dialogue search list.
2:12:222 hours, 12 minutes, 22 secondsDSX.
2:12:242 hours, 12 minutes, 24 secondsI'm going to go ahead and import all the things from React, then from
2:12:302 hours, 12 minutes, 30 secondsopen toy core, then from open toy react, then from our keyboard layer provider.
2:12:392 hours, 12 minutes, 39 secondsUh, and I'm going to stop here.
2:12:432 hours, 12 minutes, 43 secondsSo, let's go ahead and set the maximum visible items to be six. Then let's go
2:12:512 hours, 12 minutes, 51 secondsahead and set the dialogue search list props to be items on select on highlight
2:12:582 hours, 12 minutes, 58 secondsfilter function render item get key placeholder and empty text.
2:13:052 hours, 13 minutes, 5 secondsThen let's go ahead and export function dialogue search list and let's add all
2:13:122 hours, 13 minutes, 12 secondsof those props with default values for the placeholder and for the empty text.
2:13:182 hours, 13 minutes, 18 secondsNow in here I'm going to go ahead and create the selected index state, the
2:13:252 hours, 13 minutes, 25 secondsselected value state, I mean search value state, the input ref, the scroll
2:13:342 hours, 13 minutes, 34 secondsref because we have to simulate the entire thing we did with the command menu. And let's go ahead and add is top
2:13:432 hours, 13 minutes, 43 secondslayer. And I'm going to go ahead and add one thing which I'm going to comment out because we don't have it yet. So we are later going to enable the theme here.
2:13:542 hours, 13 minutes, 54 secondsLet's go ahead and implement uh whoops the handle content change
2:14:012 hours, 14 minutes, 1 secondmethod in here. I'm going to go ahead and get the current text value through the input
2:14:092 hours, 14 minutes, 9 secondsref. And then I'm going to set the search value to be that. I'm going to reset the selected index to zero. And
2:14:182 hours, 14 minutes, 18 secondsthen I'm going to get the value of the scroll box. I mean the container of the scroll box. And if it's found, I'm going to scroll back to the top.
2:14:272 hours, 14 minutes, 27 secondsBeneath this function, I'm going to go ahead and add a filtered constant. And let me go ahead and collapse this a little bit so it's easier to look at.
2:14:362 hours, 14 minutes, 36 secondsHere it is. So if we have search value, let's go ahead and filter the items according to that value. Otherwise, just
2:14:442 hours, 14 minutes, 44 secondsreturn a list of all the items. Let's go ahead and calculate the visible height using math min. The amount of uh items
2:14:522 hours, 14 minutes, 52 secondswe have rendered and then uh limit by maximum visible items.
2:14:592 hours, 14 minutes, 59 secondsLet's go ahead and open a use keyboard hook in which we are going to which we
2:15:052 hours, 15 minutes, 5 secondsare going to block if the top layer is not a dialogue.
2:15:122 hours, 15 minutes, 12 secondsAnd then let's go ahead and register the following key bindings. So if the
2:15:212 hours, 15 minutes, 21 secondsuser attempts to select something, let's attempt to find that item. And if we are able to find it, let's simply call on select which is a prop.
2:15:342 hours, 15 minutes, 34 secondsThen let's go ahead and develop the else. If key dotname
2:15:432 hours, 15 minutes, 43 secondsis up and this is now getting very similar to
2:15:502 hours, 15 minutes, 50 secondsuse command menu. So if you want to you can keep that open simply because uh we are going to do some similar
2:15:592 hours, 15 minutes, 59 secondscalculations like this one. So back here if key.name is up we're going to set the selected index.
2:16:132 hours, 16 minutes, 13 secondsWe're going to define the new index.
2:16:162 hours, 16 minutes, 16 secondsWe are then going to find the uh scroll area.
2:16:222 hours, 16 minutes, 22 secondsAnd if the scroll area container exists and if new index is less than scroll top value of the scroll area, we're going to scroll to the new index.
2:16:342 hours, 16 minutes, 34 secondsAnd then let's just go ahead and select what is that next item that we should highlight. And if we are able to find it
2:16:442 hours, 16 minutes, 44 secondsthrough that new index, let's highlight it. And finally, let's return the new index. And now we're going to do the
2:16:532 hours, 16 minutes, 53 secondssame but in the opposite direction if we are going down. So again
2:17:022 hours, 17 minutes, 2 secondswe go ahead and open the set selected index. We calculate what should the new index be.
2:17:122 hours, 17 minutes, 12 secondsWe find the scroll area.
2:17:162 hours, 17 minutes, 16 secondsAnd if the scroll area is found, let's go ahead and get viewport height.
2:17:232 hours, 17 minutes, 23 secondsLet's get the visible end by adding to scroll top value the viewport height
2:17:312 hours, 17 minutes, 31 secondsminus one. And then if the new index we have calculated is greater than the visible end, let's scroll to that new
2:17:402 hours, 17 minutes, 40 secondsindex. Once we have that new index, let's go ahead and attempt to extract an item from our filtered list.
2:17:492 hours, 17 minutes, 49 secondsAnd let's go ahead and highlight it. And finally, let's return new index. There we go.
2:17:592 hours, 17 minutes, 59 secondsSo that's the hard part. Now, let's go ahead and render the UI. So we're going
2:18:042 hours, 18 minutes, 4 secondsto have a box and this box will have an input with input ref placeholder focused
2:18:132 hours, 18 minutes, 13 secondsvalue and on content change calling the handle content change.
2:18:192 hours, 18 minutes, 19 secondsNow if the user has attempted to search something for which uh we have nothing
2:18:262 hours, 18 minutes, 26 secondsto show for let's go ahead and render that and indicate that to the user. So
2:18:332 hours, 18 minutes, 33 secondswe're going to add empty text attribute here.
2:18:392 hours, 18 minutes, 39 secondsOtherwise we are going to go ahead and use scroll box with ref scroll ref and height visible
2:18:482 hours, 18 minutes, 48 secondsheight. And let's go through the filtered items until we find the one
2:18:552 hours, 18 minutes, 55 secondsthat our uh I mean let's go uh and iterate over the filtered items that the
2:19:022 hours, 19 minutes, 2 secondsuser is searching for. So let's go ahead and find uh the currently selected index so we can properly highlight it. And
2:19:102 hours, 19 minutes, 10 secondsthen in here we're going to go ahead and return the box element.
2:19:152 hours, 19 minutes, 15 secondsLet's go ahead and calculate the key using get key which comes from the prop.
2:19:212 hours, 19 minutes, 21 secondsSo we are using this function because we don't know what kind of data will be passed here. So perhaps it will be an ID, perhaps it will be a value. We don't
2:19:302 hours, 19 minutes, 30 secondsknow what it is, right? Because there can be many data types that we can pass through this.
2:19:372 hours, 19 minutes, 37 secondsThen let's go ahead and add the following flex direction row height one overflow hidden.
2:19:452 hours, 19 minutes, 45 secondsUh let's go ahead and define the background color. So the background color will depend on is selected.
2:19:552 hours, 19 minutes, 55 secondsIf it is selected we're going to use this otherwise undefined.
2:20:022 hours, 20 minutes, 2 secondsAnd let's go ahead and add an onmouse move function which will set the selected index. And uh so which selected
2:20:112 hours, 20 minutes, 11 secondsindex? Well, itself, right? We don't need any prop. And if on highlight function has been passed, go ahead and
2:20:192 hours, 20 minutes, 19 secondstrigger it and pass that item along. And then let's go ahead and do on mouse down. And then finally, let's do render
2:20:272 hours, 20 minutes, 27 secondsitem inside. Perfect. So that's it. That is the important component I was telling
2:20:352 hours, 20 minutes, 35 secondsyou about. And I'm just going to add a little to-do here. Replace with theme coloring. Obviously, if you don't intend
2:20:432 hours, 20 minutes, 43 secondsto add themes to this project, you don't have to do that. Great. So, we now have dialogue search list, which is basically
2:20:522 hours, 20 minutes, 52 secondsthis. So, we will be able to highlight uh on cursor movement. we will be able to calculate when we are supposed to
2:21:002 hours, 21 minutesscroll in both directions and kind of select uh the newest uh item from the
2:21:072 hours, 21 minutes, 7 secondslist and we are automatically able uh to search as well. So a pretty powerful component.
2:21:162 hours, 21 minutes, 16 secondsLet's go ahead and see what we should develop next. So we should start uh with
2:21:232 hours, 21 minutes, 23 secondsthe theme configuration now. So, I'm going to go inside of packages source and I'm going to create theme.ts.
2:21:322 hours, 21 minutes, 32 secondsUh, and in here, I'm going to go ahead and define the values for my theme colors, which are going to be primary,
2:21:392 hours, 21 minutes, 39 secondsplan mode, selection, thinking, success, error, info, background, surface, dialogue, surface, thinking border, and
2:21:462 hours, 21 minutes, 46 secondsdim separator. And then let's go ahead and export type theme name string colors
2:21:532 hours, 21 minutes, 53 secondstheme colors. And let's go ahead and export an array of themes. For now, I'm just going to go ahead and add the very
2:22:012 hours, 22 minutes, 1 secondfirst one, the basic one, which is what currently exists. The name of this theme
2:22:082 hours, 22 minutes, 8 secondswill be nightf fox. And then in here, we have to define an array or should they say an object of colors. So, I'm just
2:22:172 hours, 22 minutes, 17 secondsgoing to go ahead and paste all of them here. You can pause the screen and copy or go into the source code or ask AI to create a color scheme for you. It's surprisingly good at this.
2:22:282 hours, 22 minutes, 28 secondsUh it's basically all the colors that I've been using so far in this project. This is like the the base base uh theme.
2:22:362 hours, 22 minutes, 36 secondsUh all right. Now what I want to do is I want to create uh the hook. So, let's go
2:22:442 hours, 22 minutes, 44 secondsinside of packages source providers new folder theme. Perhaps I'm going to move
2:22:512 hours, 22 minutes, 51 secondsthis theme to that folder. And let me get index.tsx.
2:22:582 hours, 22 minutes, 58 secondsAnd now in here, I'm going to add a couple of file system uh and operating
2:23:042 hours, 23 minutes, 4 secondssystem and path uh imports so we can uh update our preferences file. Let's also add the usual React context things.
2:23:172 hours, 23 minutes, 17 secondsLet's import the types here.
2:23:202 hours, 23 minutes, 20 secondsAnd I believe that we forgot uh one thing in our
2:23:292 hours, 23 minutes, 29 secondstheme.ts and that is export condefault theme.
2:23:392 hours, 23 minutes, 39 secondsAnd in here we can basically define what should the default theme be. I'm going
2:23:462 hours, 23 minutes, 46 secondsto make it be nightf fox because that's the only one that we have.
2:23:542 hours, 23 minutes, 54 secondsAnd now we have the default theme set up. All right.
2:24:002 hours, 24 minutesUh now I'm going to go back inside of the providers theme index.tsx. tsx
2:24:092 hours, 24 minutes, 9 secondsand I can import default theme and an array of themes. I'm going to define the config directory by joining home
2:24:192 hours, 24 minutes, 19 secondsdirectory and dot night code folder. So, it's going to be pretty similar to how
2:24:252 hours, 24 minutes, 25 secondsmost CLI tools store preferences in the home directory. Create a new folder
2:24:322 hours, 24 minutes, 32 secondsnight code. And then inside, I'm simply going to append to that path a file preferences.json.
2:24:412 hours, 24 minutes, 41 secondsLet's go ahead and define the theme preferences. Theme name will be a string. And then I'm going to define a function to get the initial theme.
2:24:532 hours, 24 minutes, 53 secondsAnd I'm going to go ahead and try and get the theme.
2:25:002 hours, 25 minutesWe're going to try to get the preferences using JSON.parse using read file sync theme preferences
2:25:092 hours, 25 minutes, 9 secondspath and using UTF8 encoding. And I'm going to cast it as theme preferences.
2:25:162 hours, 25 minutes, 16 secondsAnd if I am able to extract something from this file, I'm going to attempt to use that value preferences theme name.
2:25:272 hours, 25 minutes, 27 secondsAnd I'm going to attempt to iterate over my array of themes. And I'm going to try to find that name so I can find the
2:25:342 hours, 25 minutes, 34 secondssaved theme. And if I'm able to find it, I'm going to use it. Otherwise, I'm going to fall back to default theme. or
2:25:422 hours, 25 minutes, 42 secondsif any other error happens I will just default to the default theme. Now let's go ahead and create a function to
2:25:512 hours, 25 minutes, 51 secondspersist the theme. So when user selects a theme uh let's go ahead and store it into that file. So how do we do that?
2:26:002 hours, 26 minutesLet's open a try and catch. So we're going to do make directory synchronize config directory recursive true.
2:26:112 hours, 26 minutes, 11 secondsAnd then in here, let's go ahead and do write file sync with the theme preferences path. And then the content
2:26:192 hours, 26 minutes, 19 secondswill be JSON.stringify theme name theme.name satisfies theme preferences. And then just some additional properties here and encoding.
2:26:322 hours, 26 minutes, 32 secondsAnd in the catch here, we we need to do try and catch. And we're purposely going to like kind of let it catch simply
2:26:412 hours, 26 minutes, 41 secondsbecause we don't want this to break the app. So we are just going to ignore any write failures. So theme switching will still work but only for this session.
2:26:522 hours, 26 minutes, 52 secondsIt's not going to work by it's not going to persist it basically.
2:26:582 hours, 26 minutes, 58 secondsNow let's go ahead and define the theme context value with colors current theme and set theme.
2:27:052 hours, 27 minutes, 5 secondsthen theme context.
2:27:072 hours, 27 minutes, 7 secondsThen let's go ahead and define the use theme hook.
2:27:132 hours, 27 minutes, 13 secondsA very familiar pattern by now. We've done this I think four times now or three. Then the theme provider props
2:27:232 hours, 27 minutes, 23 secondsand then let's go ahead and render the actual theme provider.
2:27:302 hours, 27 minutes, 30 secondsLet's set the actual current theme.
2:27:342 hours, 27 minutes, 34 secondsthen a call back to set the theme. So we are going to set the current theme in a
2:27:412 hours, 27 minutes, 41 secondsstate and we're going to try and persist it. And the initial value of the state
2:27:482 hours, 27 minutes, 48 secondsis this function get initial theme which is trying to read it from the
2:27:592 hours, 27 minutes, 59 secondsfrom the preferences.json file. Uh obviously this is quite easy to
2:28:052 hours, 28 minutes, 5 secondsturn off. So for example, you can just put let me see
2:28:132 hours, 28 minutes, 13 secondsname fox. I think you can or maybe not.
2:28:222 hours, 28 minutes, 22 secondsYou can just do themes.
2:28:272 hours, 28 minutes, 27 secondsOkay, that's not working either. Okay, let's just uh reset it to this basically. I'm not sure how this will
2:28:352 hours, 28 minutes, 35 secondsbehave on other machines because I only tested it on Unix or Mac OS, but
2:28:442 hours, 28 minutes, 44 secondsoh yeah, you you can just do default theme.
2:28:492 hours, 28 minutes, 49 secondsYou can just do that if it breaks uh your if it doesn't work on Windows or something like that.
2:28:552 hours, 28 minutes, 55 secondsUh great. So, we have set theme. We are able to reload the initial theme and let's just return the theme context
2:29:032 hours, 29 minutes, 3 secondsprovider wrapping the children and passing along the value of colors current theme and of course set theme.
2:29:132 hours, 29 minutes, 13 secondsPerfect.
2:29:152 hours, 29 minutes, 15 secondsNow what I want to do is I want to create the theme provider.
2:29:222 hours, 29 minutes, 22 secondsSo the theme provider or sorry the theme dialogue that's the one I want.
2:29:272 hours, 29 minutes, 27 secondsThankfully, it won't be difficult to implement it because we can reuse the dialogue search list. So, I'm going to go inside of source. I'm going to create
2:29:362 hours, 29 minutes, 36 secondsa new folder called dialogues. And in here, I'm going to create theme dialogue. DSX.
2:29:442 hours, 29 minutes, 44 secondsI'm going to import callback use effect and use ref use dialogue. Uh, we don't
2:29:522 hours, 29 minutes, 52 secondshave providers dialogue. Did I miss that?
2:29:582 hours, 29 minutes, 58 secondscannot find module providers.
2:30:042 hours, 30 minutes, 4 secondsDid I forgot to export function use dialogue?
2:30:122 hours, 30 minutes, 12 secondsLet me see what I did incorrectly.
2:30:152 hours, 30 minutes, 15 secondsWhat I did incorrectly is this should be inside of the components folder.
2:30:202 hours, 30 minutes, 20 secondsThere we go. So make sure the dialogues is inside of components and then the path is correct.
2:30:272 hours, 30 minutes, 27 secondsGreat. And now we can also add use theme from providers theme. And that reminds
2:30:332 hours, 30 minutes, 33 secondsme I forgot to add it to the index the theme provider. Let's import our dialogue search list. Let's import our
2:30:432 hours, 30 minutes, 43 secondsarray of themes and let's import the theme type.
2:30:492 hours, 30 minutes, 49 secondsSo, what I quickly want to do now is just encapsulate my
2:30:582 hours, 30 minutes, 58 secondsentire app uh within the theme provider. But we have to do it carefully because
2:31:092 hours, 31 minutes, 9 secondslet me show you in source index.tsx. The problem is we are already using some colors here. So I'm thinking of a way uh
2:31:182 hours, 31 minutes, 18 secondsbecause I can just add for example the theme provider. Let's add a theme provider.
2:31:262 hours, 31 minutes, 26 secondsI can add it here.
2:31:282 hours, 31 minutes, 28 secondsBut if I there is no way for me to like initialize a hook used theme here so I
2:31:362 hours, 31 minutes, 36 secondscan get the color here. So I have to extract this into its own root.
2:31:442 hours, 31 minutes, 44 secondsThat's exactly what I'm going to do. So above here, I'm going to define a function called themed root and I'm
2:31:512 hours, 31 minutes, 51 secondsgoing to import use theme from providers theme. And then I'm going
2:31:592 hours, 31 minutes, 59 secondsto copy the contents in here. I'm going to return like this.
2:32:082 hours, 32 minutes, 8 secondsAnd I can now replace the hard-coded background color with colors do background like that. And then instead
2:32:162 hours, 32 minutes, 16 secondsof this I can render themed root
2:32:222 hours, 32 minutes, 22 secondslike that. Perfect. And uh let me just check. Okay. Let's add the theme provider
2:32:312 hours, 32 minutes, 31 secondsoutside like this. And let's properly indent all
2:32:382 hours, 32 minutes, 38 secondsof that. Uh, perfect. So now we have that. So let's go ahead and finish uh
2:32:462 hours, 32 minutes, 46 secondsdeveloping the the theme dialogue. So inside of
2:32:532 hours, 32 minutes, 53 secondscomponents dialogues theme dialogue. Now that we have the theme here,
2:33:002 hours, 33 minuteswe can export theme dialogue content.
2:33:062 hours, 33 minutes, 6 secondsWe can add a hook use dialogue.
2:33:112 hours, 33 minutes, 11 secondsWe can then also add set theme and current theme. From use theme hook, we can set the original theme ref and give
2:33:202 hours, 33 minutes, 20 secondsit a value of current theme. So why are we doing this? Well, take a look at this behavior in the final result. When I
2:33:272 hours, 33 minutes, 27 secondsopen the theme dialogue, uh, highlighting automatically lets you preview the theme.
2:33:352 hours, 33 minutes, 35 secondsSo, this technically calls set theme.
2:33:392 hours, 33 minutes, 39 secondsBut if I cancel it, reverts back. So, we need a way to store the original theme,
2:33:462 hours, 33 minutes, 46 secondsand we are using a ref for that. So we're also going to keep track if the user actually confirmed they want that theme. And now let's add that
2:33:552 hours, 33 minutes, 55 secondsfunctionality. So let's revert to original theme if the user dismisses without confirming. We're going to use use effect for that. So let's add an
2:34:042 hours, 34 minutes, 4 secondsunmount function if the confirmed ref is false. Set theme to the value of the original theme ref which is the value of
2:34:112 hours, 34 minutes, 11 secondsthe current theme that was loaded at the time the dialogue was opened. So that is the best solution we can do at the moment. Let's go ahead and implement
2:34:192 hours, 34 minutes, 19 secondshandle select which is a callback which uses the theme config sets the confirmed ref to be true sets the theme and closes
2:34:282 hours, 34 minutes, 28 secondsthe dialogue. So even if this unmount fires the confirmed ref will be set to true meaning that the user purposely
2:34:352 hours, 34 minutes, 35 secondsselected that theme and didn't just highlight it. Whereas the highlight function is simply going to call set
2:34:422 hours, 34 minutes, 42 secondstheme and then this unmount will take care and make sure that it resets.
2:34:492 hours, 34 minutes, 49 secondsAnd then finally let's go ahead and add a return here.
2:34:552 hours, 34 minutes, 55 secondsAnd we can now just use our dialogue search list component. So the items that
2:35:032 hours, 35 minutes, 3 secondsis going to render are going to be the themes.
2:35:072 hours, 35 minutes, 7 secondsOn select is going to call handle select.
2:35:112 hours, 35 minutes, 11 secondsOn highlight it's going to call handle highlight. The filtering function is going to work in the following way. It will accept the T argument the theme.
2:35:222 hours, 35 minutes, 22 secondsThe query and then it's going to get the theme's name and it's going to see if it includes the query that the user is
2:35:312 hours, 35 minutes, 31 secondstyping. And we are lowercasing both so we don't make it case sensitive.
2:35:372 hours, 35 minutes, 37 secondsAnd now we have to render the item. So how do we render this item? Well, we're
2:35:442 hours, 35 minutes, 44 secondsgoing to render it uh within a text element. And we're not going to use any theme elements here. We just want black and white.
2:35:552 hours, 35 minutes, 55 secondsAnd let's go ahead and check if theme.name name is equal to original theme ref.tc
2:36:052 hours, 36 minutes, 5 secondscurrent.name. And what do we want to do here? So we want to display that the current theme is selected. So for that
2:36:132 hours, 36 minutes, 13 secondsI'm going to go ahead and show this entity this uni code right here. So I found a way so that you can write it as
2:36:202 hours, 36 minutes, 20 secondswell like that. And beneath it render theme.name.
2:36:282 hours, 36 minutes, 28 secondsNow let's go ahead and define the key which will be the original theme name
2:36:352 hours, 36 minutes, 35 secondsbecause each theme has an original name, the placeholder and the empty text.
2:36:442 hours, 36 minutes, 44 secondsGreat. So now we have the theme dialogue ready. And now we can go inside of dialogues and create a barrel export here.
2:36:542 hours, 36 minutes, 54 secondsAnd inside of here, let's just export the theme dialogue content from theme dialogue like that.
2:37:032 hours, 37 minutes, 3 secondsAnd now that we have that, let's go ahead inside of commands. DSX
2:37:142 hours, 37 minutes, 14 secondsand let's find the theme and let's go ahead and modify this now. So this is
2:37:212 hours, 37 minutes, 21 secondsnow going to be context dialogue. Open
2:37:272 hours, 37 minutes, 27 secondstitle is going to be select theme and the children are going to be theme
2:37:352 hours, 37 minutes, 35 secondsdialogue content which I can import from dialogues the barrel barrel export we just did.
2:37:452 hours, 37 minutes, 45 secondsAnd if I've done this correctly it should allow us to open the theme dialogue just like this. And if I search
2:37:542 hours, 37 minutes, 54 secondsfor something random, it will tell me that it doesn't exist. If I control C, it will close the dialogue just as we develop.
2:38:012 hours, 38 minutes, 1 secondAnd what we have to do now is we have to add some more themes. So to see if this actually works.
2:38:102 hours, 38 minutes, 10 secondsSo I'm going to go inside of packages source theme.ts DS. And what I'm going
2:38:172 hours, 38 minutes, 17 secondsto do is I'm just going to add all of the themes that I have uh made for this
2:38:232 hours, 38 minutes, 23 secondsproject. And all of them were done with AI simply because AI is quite good at like randomizing these themes.
2:38:332 hours, 38 minutes, 33 secondsSo I'm just going to paste all of them here. All right. you can go inside of the source code or just I'm going to I don't know pause the screen at some
2:38:422 hours, 38 minutes, 42 secondsrandom theme and copy it or just create your own you know random theme. So a bunch of popular themes here that are
2:38:502 hours, 38 minutes, 50 secondsfound in various like uh um code editors and things. I mean it's just random hex
2:38:572 hours, 38 minutes, 57 secondscolors. I don't think they are exactly the same. And that should allow you now to,
2:39:052 hours, 39 minutes, 5 secondsas you can see, for now only change the the background. Why only the background?
2:39:112 hours, 39 minutes, 11 secondsBecause we haven't added the uh color hook to be used anywhere. But if we've
2:39:182 hours, 39 minutes, 18 secondsdone this correctly, uh we should now be able to select Dracula for example. I should be able to
2:39:242 hours, 39 minutes, 24 secondsexit. And when I do bun rundev C cli I am still let's check using Dracula mode
2:39:342 hours, 39 minutes, 34 secondsmeaning that the preferences were successfully saved. Now if you're a Windows user or it simply doesn't work
2:39:412 hours, 39 minutes, 41 secondson your machine you can simplify the theme provider entirely and you don't even have to call persist theme. You can
2:39:492 hours, 39 minutes, 49 secondscomment this out and you can just set the default theme here. You can see that it will work exactly the same. So when I
2:39:562 hours, 39 minutes, 56 secondsgo in themes, I can change it. But if you exit and re-enter, it won't be
2:40:022 hours, 40 minutes, 2 secondspersisted. So that way you can avoid all of these right files because I don't know if this works the same on Windows
2:40:102 hours, 40 minutes, 10 secondsas it does on Mac OS and Linux. So you know, choose if that works for you or not. You can see that the moment I bring it back, it reads from the configuration.
2:40:202 hours, 40 minutes, 20 secondsBrilliant. So what we have to do now uh is we have to find all the places where
2:40:272 hours, 40 minutes, 27 secondswe should be using uh uh the theme instead of hardcoded
2:40:332 hours, 40 minutes, 33 secondscolors. So let's start with command menu index.tsx.
2:40:432 hours, 40 minutes, 43 secondsI'm going to go ahead and add my hook. Use theme from providers
2:40:512 hours, 40 minutes, 51 secondstheme. And in here, I'm going to go ahead and uh let me see command menu.
2:41:022 hours, 41 minutes, 2 secondsHere it is. Background color is selected will now be colors.
2:41:102 hours, 41 minutes, 10 secondsMy apologies. selection like that. That's one.
2:41:152 hours, 41 minutes, 15 secondsUh now let's go ahead uh and go inside of dialogues.
2:41:222 hours, 41 minutes, 22 secondsActually let's go inside of dialogue search list and let's do a similar thing here. So you can see I've prepared myself, right? I'm going to import used
2:41:312 hours, 41 minutes, 31 secondstheme from providers theme and down here again I'm not going to use this. I'm going to use colors dot
2:41:402 hours, 41 minutes, 40 secondsselection and then I can remove this to-do right here. Great.
2:41:462 hours, 41 minutes, 46 secondsUh now, uh let's see what else we ought to do. I'm going to go inside of input bar component
2:41:552 hours, 41 minutes, 55 secondsand I'm going to go ahead add to top here and I'm going to add cons theme.
2:42:022 hours, 42 minutes, 2 secondsUse theme execute. Make sure you've imported it from providers theme
2:42:102 hours, 42 minutes, 10 secondsand we can immediately extract colors because that's the only thing we need. We're not going to assign anything else.
2:42:172 hours, 42 minutes, 17 secondsLet's go ahead and find where we mention cyan and let's replace it with colors primary like that. Then
2:42:272 hours, 42 minutes, 27 secondslet's go ahead and replace this background color here colors dot surface.
2:42:352 hours, 42 minutes, 35 secondsThen let's go ahead and repeat colors.
2:42:382 hours, 42 minutes, 38 secondsDown here when we show the command menu like that.
2:42:432 hours, 42 minutes, 43 secondsAnd I think that is all regarding the input bar. Now let's go ahead inside of
2:42:512 hours, 42 minutes, 51 secondsthe status bar and let's do a similar thing. So const colors use theme
2:43:012 hours, 43 minutes, 1 secondand let me see again instead of cyan is going to be colors. primary and instead
2:43:092 hours, 43 minutes, 9 secondsof gray it's going to be colors dim separator.
2:43:182 hours, 43 minutes, 18 secondsLet's go ahead and see what else we have to do. Let me close all of these other components. Let's go inside of
2:43:262 hours, 43 minutes, 26 secondsuh let's see let's go inside of the providers
2:43:322 hours, 43 minutes, 32 secondsdialogue index dsx and inside of the actual
2:43:412 hours, 43 minutes, 41 secondsdialogue function. Let's go ahead and extract colors here. So use theme.
2:43:502 hours, 43 minutes, 50 secondsMake sure you've imported it. And then let's go ahead and find the hex color. Here it is. Background color.
2:43:592 hours, 43 minutes, 59 secondsColors dot dialogue surface.
2:44:042 hours, 44 minutes, 4 secondsAll right, we have that. Now, let's go ahead and go inside of the toast right here. Index.
2:44:132 hours, 44 minutes, 13 secondsLet's scroll down to the actual toast component. const colors.
2:44:202 hours, 44 minutes, 20 secondsuse theme.
2:44:242 hours, 44 minutes, 24 secondsAnd let's go ahead and replace all three of these with colors. Colors error
2:44:322 hours, 44 minutes, 32 secondscolors.info. So they all match. And let's also find this here and replace with colors.
2:44:442 hours, 44 minutes, 44 secondsGreat.
2:44:452 hours, 44 minutes, 45 secondsNow that we have that, let me see if there are any left. Let me see. Did we
2:44:522 hours, 44 minutes, 52 secondsdo the command menu? Command menu index.tsx. We did. Perfect.
2:45:002 hours, 45 minutesAnd I think that should be it then. You should now be able to open theme and
2:45:082 hours, 45 minutes, 8 secondsthey should be more vibrant now, more random.
2:45:142 hours, 45 minutes, 14 secondsVery very cool.
2:45:172 hours, 45 minutes, 17 secondsUh, and let me go ahead and just, you know, do a search hex code.
2:45:242 hours, 45 minutes, 24 secondsLooks like we do still have one.
2:45:282 hours, 45 minutes, 28 secondsUh, and it's this one. It's in toast.tsx. My apologies. Toast index.
2:45:362 hours, 45 minutes, 36 secondsUh, I'm not sure if we have a color for this one. I think we can just leave it as is.
2:45:452 hours, 45 minutes, 45 secondsI'm not sure. Let me see. Themeds info surface.
2:45:542 hours, 45 minutes, 54 secondsI'm not sure. I'm going to leave it as is.
2:45:572 hours, 45 minutes, 57 secondsBrilliant. So, that is step three finished. We have the theme provider, keyboard layer, dialogue provider, toast
2:46:052 hours, 46 minutes, 5 secondsprovider, and theme root. So, a very big lesson in providers.
2:46:102 hours, 46 minutes, 10 secondsuh and more importantly in keyboard layers. I think this was kind of the most important concept of this chapter.
2:46:172 hours, 46 minutes, 17 secondsSo let's go ahead and review our code now before we uh merge everything. So I'm going to get checkout B 0 to
2:46:272 hours, 46 minutes, 27 secondsUI infrastructure get add get commit
2:46:352 hours, 46 minutes, 35 seconds02 UI infrastructure get push- origin 02 UI infrastructure
2:46:452 hours, 46 minutes, 45 secondslike that and then let's go ahead and open a poll request UI my infrastructure to demand branch.
2:46:552 hours, 46 minutes, 55 secondsLet's create a poll request and let's review the changes.
2:47:002 hours, 47 minutesAnd here we have the summary by code rabbit. So we added the theming system with multiple color scheme options.
2:47:062 hours, 47 minutes, 6 secondsUsers can now switch themes via command menu. We enhanced the command interactions with toast notifications providing real-time feedback for
2:47:142 hours, 47 minutes, 14 secondsactions. We added dialogues for theme selection and upcoming features like agent and model management. We improved
2:47:212 hours, 47 minutes, 21 secondskeyboard navigation with refined focus handling for better command menu and input responsiveness aka the responder chain. We have a few comments here.
2:47:312 hours, 47 minutes, 31 secondsLuckily this time uh not too serious in here. It's telling me this path doesn't exist. So when code rabbit makes a
2:47:402 hours, 47 minutes, 40 secondsmistake, you can actually simply tell it this is a valid VS code settings as VS
2:47:482 hours, 47 minutes, 48 secondscode itself uh filled this file from UI input. And
2:47:562 hours, 47 minutes, 56 secondsonce you leave a comment, it will actually remember this and it will not make the same mistake. It will kind of extend its learning. And you will see at
2:48:042 hours, 48 minutes, 4 secondsthe end uh if we have time it will answer. In here it's simply telling it I have a missing semicolon for
2:48:112 hours, 48 minutes, 11 secondsconsistency. All right. This is this is a simple one. We don't have to resolve that. But in here another serious issue
2:48:182 hours, 48 minutes, 18 secondshere. Well serious I mean it can cause bugs. We are missing dialogue in the dependency array. So let me go ahead and
2:48:262 hours, 48 minutes, 26 secondsquickly see if that is true which certainly is. Um, inside of my components I have input bar
2:48:342 hours, 48 minutes, 34 secondsand in here I have handle command which now uses the
2:48:422 hours, 48 minutes, 42 secondsdialogue. So yes, uh, the dialogue definitely needs to be here. Let's add it here.
2:48:502 hours, 48 minutes, 50 secondsI'm not going to commit yet simply so I see what other issues are about in here.
2:48:552 hours, 48 minutes, 55 secondsis telling me that clamp dialogue width a positive value for narrow terminals.
2:48:592 hours, 48 minutes, 59 secondsSo the way I tested this width is basically by not caring if the terminal
2:49:062 hours, 49 minutes, 6 secondsbecomes absurdly small like this. I I don't really I'm not going to make this app support that it expects a normal
2:49:152 hours, 49 minutes, 15 secondswidth. Everything looks broken in a terminal when it's small. So this is not exactly uh an issue for me.
2:49:232 hours, 49 minutes, 23 secondsUh, and now what I'm going to do is I'm just going to push this dialogue fix right here. So I'm going to do get add
2:49:322 hours, 49 minutes, 32 secondsget commit 02 UI infrastructure
2:49:402 hours, 49 minutes, 40 secondsfix. And I'm just going to do get push because I'm still in that branch and I already pushed the origin. And what
2:49:482 hours, 49 minutes, 48 secondsthat's going to do is it's going to re-trigger code rabbit and then it's going to tell us that it's okay.
2:49:562 hours, 49 minutes, 56 secondsAnd you can see that it responded to that comment of mine that this is a valid VS code settings. And then it has
2:50:032 hours, 50 minutes, 3 secondsa learning which is added. So it now knows that this is a valid officially documented VS code workspace settings.
2:50:122 hours, 50 minutes, 12 secondsAnd you can see that this was automatically set as outdated and addressed in a commit I just pushed additionally. So we can go ahead and
2:50:202 hours, 50 minutes, 20 secondsmerge this pull request. Now I'm not going to delete my branch. So I have a history. So I'm going to go inside of
2:50:282 hours, 50 minutes, 28 secondshere. And you can now see that I can go back to my first chapter or I can go back to the second chapter. Perfect. We
2:50:362 hours, 50 minutes, 36 secondsare now on the main branch which means that we also have to check out main here. and then gitpool origin main. So
2:50:442 hours, 50 minutes, 44 secondswe synchronize that merge that just happened. And if you go ahead and simply do bund rundev cli and if you have your
2:50:522 hours, 50 minutes, 52 secondstheme here you should be able to well confirm that you successfully merged
2:50:592 hours, 50 minutes, 59 secondsmain back. Beautiful. Amazing. Amazing job. This was a longer chapter, but we
2:51:072 hours, 51 minutes, 7 secondsadded some fundamental components that we need which we're going to use further on and we are not going to need to
2:51:142 hours, 51 minutes, 14 secondsimplement them again. We learned some important concepts and we made our app look really really good. Amazing job and see you in the next chapter.
Chapter 5: Routing & Screen Layout
2:51:262 hours, 51 minutes, 26 secondsIn this chapter, we're going to add routing and screen layout to our project. We're going to achieve this in two steps. In step one, we're going to
2:51:352 hours, 51 minutes, 35 secondsinstall React Router and we're going to replace our index entry point with create memory router and we're going to
2:51:432 hours, 51 minutes, 43 secondsmove all of our provider composition into a new component called root layout.
2:51:482 hours, 51 minutes, 48 secondsWe are then going to use React Router's outlet component which will allow us to inject these three screens within those
2:51:572 hours, 51 minutes, 57 secondsproviders. And the screens that we are going to create are home screen, new session screen, and session screen. And
2:52:042 hours, 52 minutes, 4 secondsthese are the URLs quote unquote uh that we are going to maintain them on. We will also have a very simple navigation
2:52:132 hours, 52 minutes, 13 secondsfunctionality. Whenever user submits using the input bar component from the home screen, we're going to redirect to
2:52:212 hours, 52 minutes, 21 secondsnew session screen and we are going to uh demonstrate how we can pass along the data through the router. So we are going
2:52:292 hours, 52 minutes, 29 secondsto take whatever message the user has sent and we're going to send it along using the router. And then in step two,
2:52:382 hours, 52 minutes, 38 secondswe're going to add UI to the new session component by developing session shell, user message, bot message, error
2:52:472 hours, 52 minutes, 47 secondsmessage, reusing the input bar, and finally a spinner, which is another package you will learn how to use.
2:52:542 hours, 52 minutes, 54 secondsBasically, by the end of chapter 3, you will be able to send a message like this, and you will be redirected to a session shell uh which demonstrate all components available like this. Great.
2:53:062 hours, 53 minutes, 6 secondsSo let's go ahead and develop that.
2:53:082 hours, 53 minutes, 8 secondsRight now if you run bun rundev CLI uh nothing really happens on submit. Let's go ahead and fix that. So the first step
2:53:162 hours, 53 minutes, 16 secondsis to install React Router into our CLI package. And while you can find on bun
2:53:222 hours, 53 minutes, 22 secondsdocumentation how to filter installing packages in their workspace, uh it just
2:53:302 hours, 53 minutes, 30 secondsdoesn't work for me. So what I do is I manually go inside of my CLI package
2:53:362 hours, 53 minutes, 36 secondslike this. So night code packages CLI and I simply do bun add react router. As
2:53:442 hours, 53 minutes, 44 secondssimple as that. And let's go ahead and confirm. There we go. Package JSON and I
2:53:522 hours, 53 minutes, 52 secondshave React router. Great. So now I'm going to go ahead and do some modifications to my existing components
2:54:002 hours, 54 minuteshere. So inside of CLI source index tsx, we have something called themed root.
2:54:082 hours, 54 minutes, 8 secondsLet's go ahead and copy that and let's go inside of source. Let's create a new
2:54:152 hours, 54 minutes, 15 secondsfolder layouts. And in here I'm going to create themedroot. DSX.
2:54:232 hours, 54 minutes, 23 secondsand I'm going to paste it here. I'm going to go ahead and export. I'm going to import use theme from providers.
2:54:332 hours, 54 minutes, 33 secondsAnd I'm going to make it uh drastically simpler actually. Let me go ahead and define the types first. So it will be
2:54:412 hours, 54 minutes, 41 secondsmore like a layout as it indicates here in where it is. So let me go ahead and
2:54:482 hours, 54 minutes, 48 secondspass this along. Let's go ahead and import the React node.
2:54:562 hours, 54 minutes, 56 secondsAnd then let me remove everything from return actually because it's going to be simpler than that. And let's just have a
2:55:032 hours, 55 minutes, 3 secondsbox with a background color with a full width, full height, and flex grow.
2:55:102 hours, 55 minutes, 10 secondsAnd then in here, we just render the children just like that. So that is our themed route.
2:55:192 hours, 55 minutes, 19 secondsNow what I want to do is I want to go inside of the layouts and create a new file root layout.tsx.
2:55:282 hours, 55 minutes, 28 secondsIn here I'm going to import outlet from React router. I'm going to import toast provider. I'm going to import dialogue
2:55:372 hours, 55 minutes, 37 secondsprovider, keyboard layer provider, theme provider, and finally themed root. And then in
2:55:462 hours, 55 minutes, 46 secondshere, let's go ahead and export our root layout. And in here, we're going to do
2:55:532 hours, 55 minutes, 53 secondsour usual composition. Theme provider, toast provider, keyboard layer provider, dialogue provider, and then themed root
2:56:022 hours, 56 minutes, 2 secondswrapping the outlet like that. Great.
2:56:072 hours, 56 minutes, 7 secondsNow that we have that set up, uh let's go ahead and create the actual memory
2:56:152 hours, 56 minutes, 15 secondsrouter. So we have to go inside of source index.dsx.
2:56:212 hours, 56 minutes, 21 secondsAnd in here we can actually remove a lot of things. And let's go ahead. I removed too much actually. Let's not remove all
2:56:292 hours, 56 minutes, 29 secondsof it. Uh let me go ahead and see what we can remove. We can definitely remove the components header, input bar, the
2:56:372 hours, 56 minutes, 37 secondsproviders. We don't need those. We don't need the entire function themed root. So
2:56:442 hours, 56 minutes, 44 secondswe can remove all of this as well. So let's just leave create cli renderer and let's leave create root. And then the
2:56:532 hours, 56 minutes, 53 secondsimports that we're actually going to add are going to be create memory router and router provider from React router. We
2:57:022 hours, 57 minutes, 2 secondsare then going to add a root layout layout root layout like that. And let's
2:57:092 hours, 57 minutes, 9 secondsgo ahead and create the memory router here.
2:57:152 hours, 57 minutes, 15 secondsSo this is where we are going to maintain our routes.
2:57:202 hours, 57 minutes, 20 secondsGo ahead and open an object. So I'm going to go ahead and add a initial path here. And the element rendered is going to be root layout.
2:57:322 hours, 57 minutes, 32 secondsAnd then the children of that path are going to be the following. So for the
2:57:382 hours, 57 minutes, 38 secondsindex meaning for this path and let me actually replace this with double quotes
2:57:472 hours, 57 minutes, 47 secondswe are going to use a specific element which for now I'm just going to add a box which says home. I think this works
2:57:552 hours, 57 minutes, 55 secondslike that. Uh I mean I think this can be box directly. I don't think it has to have any other wrappers, but we'll see.
2:58:022 hours, 58 minutes, 2 secondsUh, and then let's duplicate this two times. And for the second one, I'm going to add a path attribute. And the path
2:58:102 hours, 58 minutes, 10 secondsattribute will be sessions forward slash new. And I'm going to replace this with sessions forward slash new like that.
2:58:172 hours, 58 minutes, 17 secondsAnd in here, I'm going to do sessions forward slash ID. And let me fix this sessions. And let me fix the key here.
2:58:262 hours, 58 minutes, 26 secondsLet's make it path. And this will then be session forward slash id.
2:58:332 hours, 58 minutes, 33 secondsThere we go. So now we have our router.
2:58:362 hours, 58 minutes, 36 secondsAnd then in here we can return router provider which is a self-closing
2:58:422 hours, 58 minutes, 42 secondstag and give it a router prop just like that.
2:58:512 hours, 58 minutes, 51 secondsGreat. So before we proceed, I do want you to see the exact React Router version I'm using. Just in case
2:59:002 hours, 59 minutessomething doesn't work for you, you can use my exact version uh and have it working. Even though I think it will work regardless of the version.
2:59:092 hours, 59 minutes, 9 secondsSo now let's see what's happening in our bondev CLI. How about that? Let me go back to my root.
2:59:202 hours, 59 minutes, 20 secondsUh text must be created inside of a text node.
2:59:252 hours, 59 minutes, 25 secondsOkay, it is because yes, that's what I told you that I wasn't sure if I can render it this way.
2:59:382 hours, 59 minutes, 38 secondsOkay, one more text.
2:59:422 hours, 59 minutes, 42 secondsAnd let's go ahead and end the element here.
2:59:462 hours, 59 minutes, 46 secondsThere we go. You can see that now we just have a text which says home. Great.
2:59:532 hours, 59 minutes, 53 secondsSo now let's go inside of packages source and let's go ahead and start creating some screens. How about that?
3:00:033 hours, 3 secondsSo I'm going to create a new folder screens. And in here I'm going to create home.tsx.
3:00:103 hours, 10 secondsI'm going to go ahead and import header and input bar. And I'm also going to
3:00:163 hours, 16 secondsimport use callback from React and use navigate from React router.
3:00:233 hours, 23 secondsLet's go ahead and export the home function.
3:00:273 hours, 27 secondsLet's add the navigate hook and let's develop a simple handle submit
3:00:353 hours, 35 secondscallback which accepts the text the user has entered and triggers the navigate function to forward slash sessions new
3:00:453 hours, 45 secondswhich is something we have registered here like that. And we're going to pass along a text that the user has entered and submit.
3:00:563 hours, 56 secondsAnd let's go ahead and do a return here.
3:01:003 hours, 1 minuteWe're going to render a box with all of these properties. And then inside we're
3:01:083 hours, 1 minute, 8 secondsgoing to add a header and then another box encapsulating the input bar like this.
3:01:173 hours, 1 minute, 17 secondsNow that we have the home screen, we can go back in here and we can import
3:01:233 hours, 1 minute, 23 secondshome from screens home and we can replace this with the home element
3:01:323 hours, 1 minute, 32 secondslike this. And just like that, you should see a familiar screen here. And when you type in hello world, it should
3:01:393 hours, 1 minute, 39 secondsredirect you to sessions slash uh new just like that. So let's go ahead and develop the rest of these screens now.
3:01:503 hours, 1 minute, 50 secondsSo I'm going to go ahead uh inside and I'm going to create new dash session.tsx.
3:02:003 hours, 2 minutesI'm going to import use effect use navigate use location and use theme. I'm going to return I mean export function
3:02:083 hours, 2 minutes, 8 secondsnew session. We're going to add the following hooks here. So, navigate use
3:02:153 hours, 2 minutes, 15 secondslocation and use theme from which we can already extract the colors because that's the only thing we're going to need. Let's go ahead and prepare the
3:02:233 hours, 2 minutes, 23 secondsstate using location.state and let's go ahead and cast an object containing a optional message or the entire thing
3:02:313 hours, 2 minutes, 31 secondsbeing null. It's basically a way to access this right here.
3:02:383 hours, 2 minutes, 38 secondsSo now that we have that, let's go ahead uh and
3:02:443 hours, 2 minutes, 44 secondslet's do like a little I guess redirect or protection. So let's imagine that
3:02:533 hours, 2 minutes, 53 secondsthis new session screen should only be rendered if we have location state. So
3:02:593 hours, 2 minutes, 59 secondsif we don't have state message, let's go ahead and immediately return null. And what we can also do is we can
3:03:083 hours, 3 minutes, 8 secondsredirect away from this like this. If there is no state message, let's navigate back to the root page.
3:03:183 hours, 3 minutes, 18 secondsAnd usually this would make sense if we had a browser and the URL and everything. Uh but let's go ahead and
3:03:273 hours, 3 minutes, 27 secondsstay true to the web. So we are replacing the URL. So you can't go back to it, right? That's how we are handling
3:03:343 hours, 3 minutes, 34 secondsthe redirect if there is no state dossage being passed. So technically this scenario can never happen but this
3:03:413 hours, 3 minutes, 41 secondsisn't type safe enough. So we have to do it like this.
3:03:463 hours, 3 minutes, 46 secondsAnd then in the return here what we can do is just a box element uh containing
3:03:523 hours, 3 minutes, 52 secondstwo text elements. The first one saying create text and the second one stay uh saying state uh message.
3:04:043 hours, 4 minutes, 4 secondsAnd let me just see what is going on here. Uh this shouldn't be color. This should be foreground.
3:04:133 hours, 4 minutes, 13 secondsUh and let me just see. Oh no, we don't have to do anything here. I think this will be just fine as is. Let's keep it
3:04:223 hours, 4 minutes, 22 secondssimple. So that's our new session. We can remove theme entirely from here.
3:04:293 hours, 4 minutes, 29 secondsAnd let's go ahead and register that now as well.
3:04:373 hours, 4 minutes, 37 secondsSo now if I say a message hello world, you can see I'm redirected to a screen creating session and I have the text hello world.
3:04:483 hours, 4 minutes, 48 secondsPerfect. Now let's go ahead and copy this session. Paste it. And let's rename this to be session.tsx.
3:04:563 hours, 4 minutes, 56 secondsAnd this one will be well drastically simpler. It's just a session function here.
3:05:043 hours, 5 minutes, 4 secondsAgain, we can remove this. So super super simple one. And we we don't even have a way to access this at the moment.
3:05:133 hours, 5 minutes, 13 secondsSo let's just keep it as simple as it is. It's just uh going to render the ID
3:05:193 hours, 5 minutes, 19 secondsthat it's being passed here. So let me render session from screens session. So
3:05:283 hours, 5 minutes, 28 secondswhatever is the ID that we decide to load this component from, we will
3:05:353 hours, 5 minutes, 35 secondsdisplay it in here. But we currently don't even have a way of doing it. I guess we can try uh let's go ahead and
3:05:423 hours, 5 minutes, 42 secondstry replacing the handle submit instead of being sessions new sessions 1 2 3 4 5 6 and I think that now if you do hello
3:05:513 hours, 5 minutes, 51 secondsworld you should see session 1 2 3 4 5 6 there we go so just like that we enabled that now let's revert this back to new
3:06:013 hours, 6 minutes, 1 secondand that is essentially step one finished we have a memory router we have
3:06:083 hours, 6 minutes, 8 secondsa new root layout which contains all of our providers and renders the outlet and
3:06:153 hours, 6 minutes, 15 secondsthe outlet is then injected with all of these screens home screen new session or session and we are able to submit message and pass along the router state.
3:06:263 hours, 6 minutes, 26 secondsNow let's go ahead and let's develop the session screen UI. So for this we're going to need to install one package. So
3:06:353 hours, 6 minutes, 35 secondsagain, I'm going to go inside of my CLI package directly and do bun add uh open toe-
3:06:433 hours, 6 minutes, 43 secondsspinner. Just like that. Let me go ahead and show you my package JSON. So I've added React router and open toe spinner.
3:06:543 hours, 6 minutes, 54 secondsGreat. We can now bring this back. Let me go back here. Bondev
3:07:023 hours, 7 minutes, 2 secondsC cli. Great. So now we're going to be working on this screen right here. Let
3:07:093 hours, 7 minutes, 9 secondsme go ahead and close all of these. And uh well we can start by creating all of the components which we're going to need. Let me show you which those are.
3:07:193 hours, 7 minutes, 19 secondsSo this is the finished state that I'm showing you now. When I send hello world, we need a user message, we need a
3:07:263 hours, 7 minutes, 26 secondsbot message, and we need an error message. How about we create those three components? because currently we don't have them. I'm going to start with the error message. That one is quite simple.
3:07:383 hours, 7 minutes, 38 secondsSo I'm going to go inside of CLI source components and I'm going to create bot message.tsx.
3:07:463 hours, 7 minutes, 46 secondsAnd in here I'm going to import text attributes. I'm going to import use
3:07:533 hours, 7 minutes, 53 secondstheme. And let me just see how about we go inside of components here and change
3:08:013 hours, 8 minutes, 1 secondthis bot message to be rendered within a message folder like this. And then this
3:08:093 hours, 8 minutes, 9 secondsimport path should be correct. So bot message is within message folder. And let's rename it to messages. There we
3:08:183 hours, 8 minutes, 18 secondsgo. All right. So text attributes and use theme props is just going to be a simple message. And let's go ahead and
3:08:283 hours, 8 minutes, 28 secondsexport the function error message. Let's extract the colors from the theme. And
3:08:343 hours, 8 minutes, 34 secondslet's go ahead and render a very simple box.
3:08:403 hours, 8 minutes, 40 secondsInside of that box, let's go ahead and render another box.
3:08:483 hours, 8 minutes, 48 secondsAnd let's go ahead and style it a bit.
3:08:513 hours, 8 minutes, 51 secondsSo I'm going to give it border left border colors dot error. And I'm going to give it a width of 100%.
3:09:023 hours, 9 minutes, 2 secondsThen inside of that I'm going to render another box with all of these content.
3:09:073 hours, 9 minutes, 7 secondsBe mindful of background color which is themed. And let's render the text right here.
3:09:173 hours, 9 minutes, 17 secondsJust like that. And this is more than enough. But uh I think you already know what I'm going to show you. So this will currently show a very very thin border.
3:09:313 hours, 9 minutes, 31 secondsHow about we render it in new session here. Uh let me go ahead and render error message.
3:09:413 hours, 9 minutes, 41 secondsMessage will be oops like that. So, if I go ahead and do hello world, there we go. It's quite thin, but perfectly fine.
3:09:543 hours, 9 minutes, 54 secondsUh, but if you want to, you can extend it, make it thicker by importing empty
3:10:023 hours, 10 minutes, 2 secondsborder and adding the following attributes to this box with the border.
3:10:083 hours, 10 minutes, 8 secondsCustom border characters, empty border vertical, and then this weird uni-ode.
3:10:153 hours, 10 minutes, 15 secondsand this one. And now it's going to be just as thick as all of these other ones.
3:10:223 hours, 10 minutes, 22 secondsLet me check. There we go. It's much thicker. Now, if you care about those sort of things, you can add this, but know that it's completely optional.
3:10:313 hours, 10 minutes, 31 secondsOkay. And now I'm going to go ahead inside of messages and I'm going to create uh a barrel export here. So, I'm going
3:10:403 hours, 10 minutes, 40 secondsto go ahead and export error message uh from dot / uh oh yes, this is an error
3:10:473 hours, 10 minutes, 47 secondsmessage, not a bot message. Sorry about that. Error message. And if it asks you to update imports, you can select yes.
3:10:553 hours, 10 minutes, 55 secondsAnd to fix this, I'm just going to go ahead and attempt to find it again.
3:11:033 hours, 11 minutes, 3 secondsAnd in here, I'm just going to end this and start it again. Looks like I'm
3:11:103 hours, 11 minutes, 10 secondsmaking some mistake. Oh, it's the new session here. So, yes, make sure you update the new session to also read.
3:11:183 hours, 11 minutes, 18 secondsWell, now it can read from messages directly because we have a barrel export. So, we can just change it to that because this is now export thing
3:11:253 hours, 11 minutes, 25 secondshere. So, if I do hello world, there we go. Looks good.
3:11:303 hours, 11 minutes, 30 secondsSo now uh that we have error message let's copy and paste this and let's add
3:11:383 hours, 11 minutes, 38 secondsuh user message. This one will be quite similar.
3:11:433 hours, 11 minutes, 43 secondsLet's go ahead and rename it to user message. Uh this box will be identical.
3:11:503 hours, 11 minutes, 50 secondsThis will use colors primary.
3:11:543 hours, 11 minutes, 54 secondsThis width will be identical same as the custom border prop.
3:12:003 hours, 12 minutesThe background color here is identical and the only thing that's different is there will be no dim attribute on the
3:12:073 hours, 12 minutes, 7 secondstext which I believe means we can also remove the import from here.
3:12:133 hours, 12 minutes, 13 secondsOkay, we have that. Now let's go ahead and develop the bot message. So the bot message will be a tiny bit different. If
3:12:213 hours, 12 minutes, 21 secondsyou want to you can still copy user message and then adapt it. So, bot message, just make sure you have renamed the
3:12:303 hours, 12 minutes, 30 secondsprevious bot message into error message because I made a mistake. It should have been error message, the first one that we did.
3:12:373 hours, 12 minutes, 37 secondsSo, bot message, it's going to have two things. It's not going to have uh just
3:12:453 hours, 12 minutes, 45 secondsthis. It will have content and it will have a model.
3:12:503 hours, 12 minutes, 50 secondsSo, let me just go ahead and update that. colors will still exist and the first box will be identical but
3:12:593 hours, 12 minutes, 59 secondsthen the second box uh is quite different. So let's remove everything inside. So I'm going to add the
3:13:073 hours, 13 minutes, 7 secondsfollowing. We're going to add this box another box inside. They have paddings.
3:13:123 hours, 13 minutes, 12 secondsThey're full width and within just a simple render of the content.
3:13:183 hours, 13 minutes, 18 secondsThen outside of this box here, let's add another one. Then let's add a flex with
3:13:253 hours, 13 minutes, 25 secondssome gap. And then in here, I'm going to go ahead and render the following and
3:13:323 hours, 13 minutes, 32 secondsrender the model. Uh, again, I have no idea what character this is. Let me try and uh find this for you. Here it is.
3:13:453 hours, 13 minutes, 45 secondsHTML entity is just that. I have no idea. Fisheye unicode character. So maybe try googling this and then you
3:13:543 hours, 13 minutes, 54 secondswill be able to copy it from here and then paste it here.
3:13:583 hours, 13 minutes, 58 secondsAll right. So that is bot message. Let's go inside of index.tsx and let's go ahead and change this to be
3:14:063 hours, 14 minutes, 6 secondsuser message from user message.
3:14:123 hours, 14 minutes, 12 secondsAnd finally bot message just like that.
3:14:193 hours, 14 minutes, 19 secondsNow that we have all three, we can develop the session shell component. So
3:14:273 hours, 14 minutes, 27 secondsinside of components, let's create session-shell.tsx. Whoops. Session shell tsx.
3:14:373 hours, 14 minutes, 37 secondsAnd in here, we're going to import text attributes node, I mean react node, the input bar,
3:14:463 hours, 14 minutes, 46 secondsand then let's go ahead and add the props. So it's going to be optional children on submit input disabled and
3:14:533 hours, 14 minutes, 53 secondsloading booleans. We can go ahead and export a function with those props. Now let's give some defaults to input disabled and loading.
3:15:043 hours, 15 minutes, 4 secondsAnd let's go ahead and return.
3:15:083 hours, 15 minutes, 8 secondsI'm going to go ahead and return a box with flex direction, flex grow, width, height, padding, and some gap here. And
3:15:163 hours, 15 minutes, 16 secondsthen in here we're going to add a scroll box. And this is one of the coolest
3:15:223 hours, 15 minutes, 22 secondsthings ever. Usually it takes a bit of, you know, trial and error. I mean it's not difficult but uh when you use scroll
3:15:323 hours, 15 minutes, 32 secondsbox with open tuy these two attributes basically allow you to reverse the way scroll bo scroll box works which is
3:15:403 hours, 15 minutes, 40 secondsperfect for LLMs because new content is appearing on the bottom not on the top.
3:15:463 hours, 15 minutes, 46 secondsSo it's kind of uh doing sticky scroll in the opposite direction. So if new content appears like during streaming,
3:15:553 hours, 15 minutes, 55 secondsit will just automatically scroll for you. So it's a it saved us so much custom implementation. This is usually one of those things that, you know, we
3:16:043 hours, 16 minutes, 4 secondswould have to do ourselves like we did with use command uh menu, you know, for all of this scrolling up and down. But
3:16:133 hours, 16 minutes, 13 secondsthankfully with just two props, Open 2 library does it for us. Amazing. So inside of here, I'm going to go ahead
3:16:213 hours, 16 minutes, 21 secondsand render the children. And now outside of the scroll box, let's render the
3:16:273 hours, 16 minutes, 27 secondsinput bar. Once again, pass along the onsubmit and disabled specifically for the input disabled prop.
3:16:363 hours, 16 minutes, 36 secondsNow in uh outside of that box rendering the input bar, let's have another box which is mostly a flex composition with some height, gap, padding, and width.
3:16:483 hours, 16 minutes, 48 secondsAnd in here we are going to go ahead and take take up space on purpose because we
3:16:553 hours, 16 minutes, 55 secondshave space between. So we actually need two elements here regardless. So this is the first element that will be rendered
3:17:033 hours, 17 minutes, 3 secondson the left side and this is the second element that will be rendered on the right side. In this element we are going
3:17:103 hours, 17 minutes, 10 secondsto dynamically render something. So if we have loading, let's have a text which says loading. Otherwise, let's render
3:17:193 hours, 17 minutes, 19 secondsnull. But even if we render null, it will still take up space. And in this
3:17:263 hours, 17 minutes, 26 secondsone, we are simply going to remind the user that they can switch their mode,
3:17:343 hours, 17 minutes, 34 secondstheir agent by pressing tab, which we don't have implemented yet, but we will when it's time to do prompt config. So
3:17:423 hours, 17 minutes, 42 secondsfor now, let's just leave it like a little hint here.
3:17:463 hours, 17 minutes, 46 secondsOkay. So now that we have the session shell, uh let's go ahead and use it. So
3:17:563 hours, 17 minutes, 56 secondsI'm going to go ahead and close everything. I'm going to go inside of my screens. I'm going to go inside of new
3:18:033 hours, 18 minutes, 3 secondssession. And in here I am going to import
3:18:103 hours, 18 minutes, 10 secondssession shell I'm going to import user message and bot message. So I should have four new components now.
3:18:213 hours, 18 minutes, 21 secondsAll right. And now let's go ahead and do the following. Let's modify our
3:18:283 hours, 18 minutes, 28 secondsrendering entirely here and render a session shell with a no op uh onsubmit
3:18:353 hours, 18 minutes, 35 secondslike a completely empty onsubmit. Mark input as disabled and mark it as loading. And then in here let's render a
3:18:443 hours, 18 minutes, 44 secondsuser message with the state from the router. Let's render a bot message with content
3:18:513 hours, 18 minutes, 51 secondswhich is kind of hard coding what an output from AI could be. And just for fun, let's render an error message so we
3:18:593 hours, 18 minutes, 59 secondsare aware of how our components look like. So now when I do hello world,
3:19:063 hours, 19 minutes, 6 secondsyou can see that I am pretty much uh at the exact state as I should be in my end
3:19:133 hours, 19 minutes, 13 secondsresult here. So we have the user message uh we have bot response and we have the
3:19:203 hours, 19 minutes, 20 secondserror message. We have reused our input bar. The only thing we don't have is the spinner. So this is how it's supposed to look like. It's supposed to be a
3:19:283 hours, 19 minutes, 28 secondsspinner. Ours is just plain text. So let's go ahead and implement uh the
3:19:343 hours, 19 minutes, 34 secondsspinner component. It's quite simple really. We're going to go inside of packages CLI source components and let's
3:19:433 hours, 19 minutes, 43 secondsadd spinner.tsx and let's import open to spinner react
3:19:503 hours, 19 minutes, 50 secondsuse theme providers theme. And there are quite a lot of these spinners. So if you
3:19:573 hours, 19 minutes, 57 secondswant to quickly test them out and you can't decide which all exist well one way is of just you know going to open to
3:20:063 hours, 20 minutes, 6 secondsspinner documentation and then uh you can see all examples there. But if you quickly want to try how it looks in your app, I recommend going on the home
3:20:153 hours, 20 minutes, 15 secondsscreen and just rendering it here like this and import the spinner from
3:20:243 hours, 20 minutes, 24 secondscomponents spinner. And now you can see exactly how it looks like. So if you go inside of the spinner here, you can see
3:20:313 hours, 20 minutes, 31 secondsyou have the name aesthetic and you can see all of these options. There are a lot of them. So you can I don't know
3:20:373 hours, 20 minutes, 37 secondsselect something, save and you will see how this spinner looks like. So there are a lot of them. Choose some fun ones.
3:20:473 hours, 20 minutes, 47 secondsI don't know. Uh I like the initial one.
3:20:523 hours, 20 minutes, 52 secondsAesthetic looks cool. Okay. Now remove it from home because that's not the place for it.
3:21:023 hours, 21 minutes, 2 secondsand instead go into uh not new session but go inside of session shell
3:21:103 hours, 21 minutes, 10 secondscomponent. And then here instead of the text loading you will now render
3:21:163 hours, 21 minutes, 16 secondsthe spinner which you can import from not type the component spinner which you can import from dot / spinner.
3:21:263 hours, 21 minutes, 26 secondsAnd now if you type in hello world there we go. Great. Uh, amazing. And there is
3:21:363 hours, 21 minutes, 36 secondsone more thing left to do here, and that is to go inside of screens session.tsx.
3:21:443 hours, 21 minutes, 44 secondsUh, and in here, we're just going to do a very simple oneline return of the session shell for now, completely
3:21:543 hours, 21 minutes, 54 secondsdisabled. And we can remove use params entirely. Just like that. So a completely empty session shell. If you
3:22:033 hours, 22 minutes, 3 secondswant to see how it looks like, go inside of home screen and change the redirection to sessions 1 2 3 4 whatever. Do hello
3:22:123 hours, 22 minutes, 12 secondsworld and you will just see a completely empty session shell.
3:22:183 hours, 22 minutes, 18 secondsSwitch back to new and you should see your new session shell. So what even is sessions new? Why do we even need it?
3:22:273 hours, 22 minutes, 27 secondsWell, the reason I uh want to do it this way, whoops, how did I open that? The reason I want to do it this way uh is
3:22:363 hours, 22 minutes, 36 secondsbecause when the user submits something from this screen right here, before we can
3:22:453 hours, 22 minutes, 45 secondsredirect to session ID, we have to create it in the database. And that can
3:22:523 hours, 22 minutes, 52 secondstake a couple of seconds. uh but in a terminal user interface I think that's a
3:22:583 hours, 22 minutes, 58 secondsvery bad experience. So because of that we are using sessions new as an let's
3:23:053 hours, 23 minutes, 5 secondscall it optimistic mutation. So the second I hit submit, it looks like it's already working on it. Even though this
3:23:123 hours, 23 minutes, 12 secondswill actually be the screen where it's going to initialize the post request to the database uh and create a new session
3:23:203 hours, 23 minutes, 20 secondsin the database and only then redirect to the actual session ID and then
3:23:273 hours, 23 minutes, 27 secondssession ID is going to start streaming the response back to us.
3:23:353 hours, 23 minutes, 35 secondsAnd that is pretty much it for this chapter. So this was a simpler one after a couple of long ones. Uh but we did
3:23:443 hours, 23 minutes, 44 secondssome important things. We set up routing and screens which we can now of course use throughout our app. We learned how
3:23:513 hours, 23 minutes, 51 secondsto uh send the state along with the routing the navigation and we built a session screen UI with just a few
3:24:013 hours, 24 minutes, 1 secondcomponents. we managed to get uh very very close to the end result. So I'm very very happy about that. So let's go
3:24:103 hours, 24 minutes, 10 secondsahead and commit this chapter 3 routing and screen layout. I'm going to go ahead and check out
3:24:173 hours, 24 minutes, 17 seconds03 routing screen layout get addit commit
3:24:253 hours, 24 minutes, 25 secondsrouting and screen layout and then get push origin 03 routing and
3:24:333 hours, 24 minutes, 33 secondsscreen layout. And once we do that get push we should be able to open a new pull request. So let's go ahead and do that.
3:24:443 hours, 24 minutes, 44 secondsAnd since none of the code we actually wrote is complete, it doesn't really make sense to wait for any code review
3:24:523 hours, 24 minutes, 52 secondssimply because it's all uh kind of in a demo state or in a nonworking fake state. So we are definitely going to get
3:25:013 hours, 25 minutes, 1 secondsome comments but I think we understand exactly what we have to do next. So I would rather we go ahead and merge this
3:25:093 hours, 25 minutes, 9 secondsimmediately and then do a code review when we have actual business logic going
3:25:163 hours, 25 minutes, 16 secondson. So just like that we completed our third chapter and once we've merged this
3:25:233 hours, 25 minutes, 23 secondswe have to go back here. So get checkout main gitpool origin main. So everything is up to date. There we go.
3:25:343 hours, 25 minutes, 34 secondsYou should have no active changes. You should be on the main branch. And you should still have all of the folders you've just created. And you can do one final check by running this hello world.
3:25:463 hours, 25 minutes, 46 secondsThere we go. Exactly as our end result.
3:25:503 hours, 25 minutes, 50 secondsBeautiful. Amazing. Amazing job. And see you in the next chapter.
Chapter 6: Server, Shared Package & Database
3:25:573 hours, 25 minutes, 57 secondsIn this chapter, we're going to add server shared package and the database package. By the end of this chapter, we're going to have four monor repo
3:26:063 hours, 26 minutes, 6 secondspackages. Our CLI, our Hono server, our shared package, and finally our Prisma client stored in the database package.
3:26:153 hours, 26 minutes, 15 secondsWe're going to start by building the shared package so that we can create the server package using Hono. Our Hono
3:26:233 hours, 26 minutes, 23 secondsserver is going to have the following session routes. get all sessions, get an individual session, and create a
3:26:303 hours, 26 minutes, 30 secondssession. All with Zod validation coming from the shared package. We're also
3:26:373 hours, 26 minutes, 37 secondsgoing to use Hono's app type, or should I say Hono RPC. So even though we are in a monor repo, we're going to have end to end type safety.
3:26:473 hours, 26 minutes, 47 secondsOnce we have our server, we're going to go ahead and add our database which will which will include Prisma for our OM and
3:26:563 hours, 26 minutes, 56 secondsNeon as our posgress database. And we're going to build the schema which will include a session which has a message
3:27:033 hours, 27 minutes, 3 secondsand then some entities like RO, mode, message status. Let me go ahead and show you exactly what we're going to have uh
3:27:113 hours, 27 minutes, 11 secondsat the end of this chapter. So right now uh if I go ahead and run bun rundev cli
3:27:213 hours, 27 minutes, 21 secondsI can say I can type hello world and I will just see this sample page.
3:27:273 hours, 27 minutes, 27 secondsBut by the end of this chapter if you type in hello world this is a new message. We are going to actually store
3:27:363 hours, 27 minutes, 36 secondsthis in the database. You can see how the loading at the bottom has finished and it has actually redirected the user
3:27:433 hours, 27 minutes, 43 secondsto the session ID page and we're going to be able to run server as you can see
3:27:503 hours, 27 minutes, 50 secondsright here and we will be able to run Prisma and by the end of that when you create a new
3:27:593 hours, 27 minutes, 59 secondsmessage you will be able to see it in your database here it is hello world this is a new message so and we should also have a session with you. Perfect.
3:28:103 hours, 28 minutes, 10 secondsSo that's what we are going to have uh at the end. So let me just close those
3:28:173 hours, 28 minutes, 17 secondsthings and let's just focus on our build at the moment. I want to start by
3:28:253 hours, 28 minutes, 25 secondsbuilding the shared package as it is the simplest one to do.
3:28:323 hours, 28 minutes, 32 secondsI'm going to go ahead and go inside of my packages and just like I've created my CLI
3:28:403 hours, 28 minutes, 40 secondspackage, I'm going to create a new folder called shared.
3:28:443 hours, 28 minutes, 44 secondsSo, I'm not going to bootstrap this in any way because it's just reexporting some useful things for us. So, let's go ahead and create a package.json.
3:28:553 hours, 28 minutes, 55 secondsAnd let's create a tsconfig.json.
3:28:583 hours, 28 minutes, 58 secondsLet's go ahead and do the package JSON first. Uh so in here I'm going to go ahead and give this a name
3:29:093 hours, 29 minutes, 9 secondsnight code shared. And then let's just go ahead and add a couple of other
3:29:163 hours, 29 minutes, 16 secondsproperties here like type module private set to true. And let's go ahead and also add exports to be source index.ds.
3:29:283 hours, 29 minutes, 28 secondsThen let's go ahead and add a TS config here. So the TS config is going to be uh quite simple. We're just going to extend
3:29:363 hours, 29 minutes, 36 secondsthe base config. So when you controlclick on this, you should open the base config. All right. Now that we have that, let's go ahead and go inside of our packages and go inside of shared.
3:29:483 hours, 29 minutes, 48 secondsAnd in here, I'm going to do bun add zod.
3:29:523 hours, 29 minutes, 52 secondsAnd just like that, you should now have zod inside of your night code shared dependencies.
3:29:593 hours, 29 minutes, 59 secondsNow I'm going to go ahead and I'm going to create a source folder here.
3:30:053 hours, 30 minutes, 5 secondsAnd then I'm going to create schemas.ts inside.
3:30:123 hours, 30 minutes, 12 secondsI'm going to import Z from zod. And in here, I'm just going to create a bunch of uh uh schemas and some I guess
3:30:233 hours, 30 minutes, 23 secondsinferences of schemas so they can be turned into types which we're going to use across our app to stream new
3:30:303 hours, 30 minutes, 30 secondsmessages um to validate our API inputs and even outputs. Right? So let's go
3:30:383 hours, 30 minutes, 38 secondsahead and start with our tool calling arguments. Uh I'm going to refer back to this when we actually end up using it.
3:30:473 hours, 30 minutes, 47 secondsBut for now, I just want us to have this entire file uh existing here simply because we cannot build anything without
3:30:543 hours, 30 minutes, 54 secondsit. So I'm going to start with this tool called arguments schema. Basically a
3:31:013 hours, 31 minutes, 1 secondsuper simple primitive object described in zod. Uh so we have the explicit key
3:31:083 hours, 31 minutes, 8 secondsschema and then we can use it later when we implement tool calling. Now let's go ahead and implement message part schema.
3:31:183 hours, 31 minutes, 18 secondsSo message part schema is going to be a type of discriminated union. So let's go
3:31:253 hours, 31 minutes, 25 secondsahead and open an array for that. And let's go ahead and add the first option
3:31:323 hours, 31 minutes, 32 secondswhich is if type is reasoning. If the type is reasoning, a message is going to have text.
3:31:413 hours, 31 minutes, 41 secondsThen if the message type is tool call, we're going to have an ID, name,
3:31:483 hours, 31 minutes, 48 secondsarguments, and even the result. And then if the message type is text, we are once
3:31:553 hours, 31 minutes, 55 secondsagain just going to have text. Basically what we're doing here is a zod definition that will help us validate
3:32:033 hours, 32 minutes, 3 secondswhat kind of message is LLM uh streaming back to us. So is that a reasoning where
3:32:113 hours, 32 minutes, 11 secondswe have to show the user what the AI model is thinking or is it a tool call where it's going to have some arguments
3:32:193 hours, 32 minutes, 19 secondslike uh a file to read a file to create or a command to run as well as the
3:32:263 hours, 32 minutes, 26 secondsresult was the tool call successful or not and the ID to keep track of all the tools that we have. So this is actually
3:32:353 hours, 32 minutes, 35 secondsthe only complex uh thing that LLM can return back when we do streaming again.
3:32:413 hours, 32 minutes, 41 secondsI'm going to uh come back to this file later and it will be a bit more clear why we need it. And now that we have a
3:32:503 hours, 32 minutes, 50 secondssingle message part, let's go ahead and export message parts schema in which we
3:32:573 hours, 32 minutes, 57 secondsare just going to turn into an array a singular message part.
3:33:023 hours, 33 minutes, 2 secondsAnd then from that we can go ahead and infer a type and make sure you're using message part
3:33:103 hours, 33 minutes, 10 secondsnot message parts because that's incorrect. So message part schema.
3:33:153 hours, 33 minutes, 15 secondsNow I'm going to go ahead uh and once again define all the tool calling arguments that can happen during the
3:33:253 hours, 33 minutes, 25 secondschat stream event. So that is once again going to be a discriminated union.
3:33:343 hours, 33 minutes, 34 secondsLet's go ahead and give it the first type which is text delta which only has
3:33:423 hours, 33 minutes, 42 secondstext. Then we have reasoning delta which also only has text. This is basically this right reasoning and text. And then
3:33:513 hours, 33 minutes, 51 secondswe're going to go ahead and define the tool call.
3:33:543 hours, 33 minutes, 54 secondsTool call. will have tool call ID, tool name and arguments which are basically what we defined above tool call arguments schema.
3:34:053 hours, 34 minutes, 5 secondsThen let's go ahead and define the tool result type. We're going to have tool call ID and the result.
3:34:143 hours, 34 minutes, 14 secondsThen let's go ahead and define done which will have message ID and duration in milliseconds. And finally, let's go
3:34:233 hours, 34 minutes, 23 secondsahead and grab the error type, which will have a message. So, what are all of these types? These types are what's
3:34:313 hours, 34 minutes, 31 secondspossible to receive back from Versel's AI SDK.
3:34:373 hours, 34 minutes, 37 secondsSo, that's why they are more thorough than this, which is basically what we are going to keep track of. This is what
3:34:443 hours, 34 minutes, 44 secondswe care about, right? And this is everything that uh Verscell's AI SDK can
3:34:503 hours, 34 minutes, 50 secondsreturn. And we are going to need this in zod form. So we can easily parse against in a should I say industry standard way.
3:35:023 hours, 35 minutes, 2 secondsSo we don't just have to do JSON parse and then check if we have message ID and duration and then guess that that is a
3:35:093 hours, 35 minutes, 9 secondsdone type. So this will be uh much easier to work with in the future.
3:35:163 hours, 35 minutes, 16 secondsAnd last thing let's just export type chat stream event which will infer chat
3:35:233 hours, 35 minutes, 23 secondsstream event schema like that. And once we have uh schemas defined let's go
3:35:303 hours, 35 minutes, 30 secondsahead and define our models. So what models can we work with? Uh that's what we're going to define in the shared
3:35:393 hours, 35 minutes, 39 secondspackage here. Let's go ahead and define a type called model pricing. So, we're going to keep track of input in US
3:35:463 hours, 35 minutes, 46 secondsdollars per million tokens and output in US dollars per million tokens because that's kind of a standard way of doing pricing uh for LLMs.
3:35:563 hours, 35 minutes, 56 secondsLet's go ahead and create a type of supported provider. For now, we're just going to make uh either anthropic or
3:36:043 hours, 36 minutes, 4 secondsopen AI. Later, you will be able to extend this and add Google and add Mistral or whatever, right? But let's
3:36:113 hours, 36 minutes, 11 secondskeep it simple. These are the two most popular ones. Uh so that's what I'm going to teach you how to support. Let's
3:36:193 hours, 36 minutes, 19 secondscreate a type for a supported chat model definition with ID provider and pricing.
3:36:243 hours, 36 minutes, 24 secondsAnd this supported provider has to be used here and model pricing has to be used here as well. Now let's go ahead
3:36:323 hours, 36 minutes, 32 secondsand export an array of supported chat models. So in here we are defining which chat models we are going to support for
3:36:403 hours, 36 minutes, 40 secondsour agentic coding CLI. So the first one will be an ID claude set for six
3:36:483 hours, 36 minutes, 48 secondsprovider anthropic and then we define the pricing. So I grabbed the pricing from their official uh pricing table.
3:36:573 hours, 36 minutes, 57 secondsKeep in mind that uh I optimize this so that we are kind of always I mean when when we when we when it comes time for
3:37:063 hours, 37 minutes, 6 secondsus to implement billing what I imagined is that we always stay profitable in a way because it will actually be cheaper
3:37:143 hours, 37 minutes, 14 secondsfor us to run certain models simply because there's a concept of input uh sorry prompt caching which we are not
3:37:233 hours, 37 minutes, 23 secondsgoing to provide to our users but our providers are going to uh handle for us.
3:37:283 hours, 37 minutes, 28 secondsSo technically we're going to have it cheaper than our users which is good for us because we are going to have a bit higher margins.
3:37:383 hours, 37 minutes, 38 secondsThen in here I'm just going to keep adding some models that I want to support like Clyde Haiku Anthropic again
3:37:463 hours, 37 minutes, 46 secondssome pricing I extracted from their table. Uh then let's add OPUS 46.
3:37:563 hours, 37 minutes, 56 secondsThen I'm going to add some open AI models like GPT54,
3:38:033 hours, 38 minutes, 3 secondsGPT 54 mini, and finally 54 Nano. And now to not
3:38:133 hours, 38 minutes, 13 secondsbreak this, let's go ahead and do I mean to not break this to make sure that we don't
3:38:203 hours, 38 minutes, 20 secondsadd anything that we are accidentally not supporting. Let's cast as const satisfies
3:38:293 hours, 38 minutes, 29 secondsreadonly supported chat model definition and then an array of those
3:38:373 hours, 38 minutes, 37 secondslike this. So if I for example do Google here, you can see I have an error,
3:38:443 hours, 38 minutes, 44 secondsright? The only thing we have to keep track of is the ids because the ids
3:38:513 hours, 38 minutes, 51 secondscannot be uh confirmed. Well, they can, but um the thing is you will simply
3:38:583 hours, 38 minutes, 58 secondsreceive an error from Versel AI SDK if you use something that isn't supported.
3:39:033 hours, 39 minutes, 3 secondsBut they don't exactly offer you the types for this or more accurately this can change. So you just have to
3:39:103 hours, 39 minutes, 10 secondskeep track of what exists. This is kind of stable. This should always exist. But you know there are like snapshots I
3:39:173 hours, 39 minutes, 17 secondsguess like 2025 and then some month and then some date. You've probably seen things like that. So that's why I tend
3:39:253 hours, 39 minutes, 25 secondsto just add the simplest IDs because these should always be available.
3:39:323 hours, 39 minutes, 32 secondsAll right. We have that and then let's just go ahead and export a couple of useful types here. For example, supported chat model is going to be a
3:39:403 hours, 39 minutes, 40 secondstype of supported chat models and then a simply uh one of them. Right? So when we hover over this, you can see exactly
3:39:483 hours, 39 minutes, 48 secondswhich are our options. So later in the project when we are verifying whether we are allowed to send
3:39:573 hours, 39 minutes, 57 secondsa specific model and provider to Verscell's AI SDK we are going to type check it against supported chat model
3:40:063 hours, 40 minutes, 6 secondsand if it's not in here we simply don't allow it and then let's go ahead and export type
3:40:123 hours, 40 minutes, 12 secondssupported chat model ID and let's create a simple function here. Find supported chat model by the model ID.
3:40:253 hours, 40 minutes, 25 secondsAnd finally, let's export the default chat model ID. Make sure to it uses the proper type. So if we type something
3:40:323 hours, 40 minutes, 32 secondsincorrect, we get an error. So I'm going to use Opus 46 as my default type here.
3:40:383 hours, 40 minutes, 38 secondsGreat. So we have now developed the models uh and the schemas. And now let's
3:40:453 hours, 40 minutes, 45 secondsgo ahead inside of source index.ds and let's reexport all of that. So from
3:40:533 hours, 40 minutes, 53 secondsmodels we need all of these things and types exported and from schemas we need all of those as
3:41:023 hours, 41 minutes, 2 secondswell. So every single schema and all of the types. The reason we are doing this index here is because in package JSON we
3:41:123 hours, 41 minutes, 12 secondsmade sure that that is what we're exporting from this package. Uh great.
3:41:173 hours, 41 minutes, 17 secondsSo we have shared the package fully complete. So now it's time for us to develop the server package.
3:41:303 hours, 41 minutes, 30 secondsLet's go ahead and scaffold the server package now. So, instead of packages, I'm going to go ahead and create server.
3:41:383 hours, 41 minutes, 38 secondsAnd in here, let's go ahead and create tsconfig.js. Um, my apologies, tsconfig.json.
3:41:463 hours, 41 minutes, 46 secondsAnd inside of here, let's just extend the base config.
3:41:513 hours, 41 minutes, 51 secondsThen, let's go ahead and create a package.json here. I'm going to open my shared and I'm going to copy everything in here and
3:41:593 hours, 41 minutes, 59 secondspaste it here. And I'm just going to remove the dependencies and the trailing comma. And for the package JSON, what I
3:42:073 hours, 42 minutes, 7 secondsreally want here is first to change the name to be server. Private is true.
3:42:133 hours, 42 minutes, 13 secondsExports can stay the same. Uh, and yeah, let's just let's just leave it at this for now. And then what I'm going to do
3:42:213 hours, 42 minutes, 21 secondsis add Hono here, but also I want to add my shared package to the server so I can
3:42:293 hours, 42 minutes, 29 secondsuse this types of models and schemas I've created. And the way we do that is by adding dependencies. And then inside
3:42:393 hours, 42 minutes, 39 secondsof dependencies here I simply add I at night code slashshared
3:42:453 hours, 42 minutes, 45 secondsand I simply make it use workspace like this
3:42:513 hours, 42 minutes, 51 secondsand then if I go ahead in the root here and run bun install uh it should take care of it. Okay.
3:43:033 hours, 43 minutes, 3 secondsSo how do we add our hono server here?
3:43:073 hours, 43 minutes, 7 secondsWell, we can do that quite easily just by looking at Hono documentation. So, in
3:43:133 hours, 43 minutes, 13 secondssimplest terms possible, Hono is a fast, lightweight uh I guess express alternative,
3:43:223 hours, 43 minutes, 22 secondsExpress.js alternative. Uh I really really like working with it. Uh whenever I need a server, I reach for Hono over
3:43:313 hours, 43 minutes, 31 secondsanything else. And uh I really like its RPC which you're going to see us uh use in
3:43:393 hours, 43 minutes, 39 secondsthis chapter. I'm uh the reason I'm stuttering is because I see this new thing called LLM and I just wonder what it is. So it's just the documentation.
3:43:483 hours, 43 minutes, 48 secondsOkay. So how do we get started? Well, super simple. You can just click on bun which we're using. So they offer this,
3:43:563 hours, 43 minutes, 56 secondsbut since we are kind of using an existing project, we can just install Hono right here. So that's exactly what I'm going to do.
3:44:073 hours, 44 minutes, 7 secondsLet's go inside of packages server bun add hono and you should have hono
3:44:143 hours, 44 minutes, 14 secondsinstalled just like that. And then let's go ahead and add scripts here as well.
3:44:203 hours, 44 minutes, 20 secondsSo after exports, I'm going to add scripts.
3:44:233 hours, 44 minutes, 23 secondsSo our dev is bun run hot source index.ds.
3:44:283 hours, 44 minutes, 28 secondsAll right. And then let's go ahead and add this simple hello world here. So I'm
3:44:353 hours, 44 minutes, 35 secondsgoing to go ahead and create source and inside I'm going to create index.ts.
3:44:413 hours, 44 minutes, 41 secondsAnd let's just paste this and save the file.
3:44:463 hours, 44 minutes, 46 secondsAnd then let's go ahead and do so I'm I am inside of packages server. Make sure you are here as well. And let's do bun rundev. And that should start the server
3:44:553 hours, 44 minutes, 55 secondsat localhost 3000. And if you visit it, you should see hello bun just like that.
3:45:043 hours, 45 minutes, 4 secondsIf you change this to hello bun hot reload and save uh it should immediately reflect. So just refresh your browser.
3:45:133 hours, 45 minutes, 13 secondsBut you can see that the server is automatically refreshed. Uh brilliant.
3:45:173 hours, 45 minutes, 17 secondsSo that is all it took really to set up our server. Now let's go ahead and just add some more packages here. So make sure you are inside of your server here.
3:45:283 hours, 45 minutes, 28 secondsLet's go ahead and add zod. And let's go ahead and add at hono zod validator.
3:45:363 hours, 45 minutes, 36 secondsSo you should have hono zod validator and zod itself. Great.
3:45:423 hours, 45 minutes, 42 secondsNow that we have that, what I want to do is I want to make us uh able to start
3:45:493 hours, 45 minutes, 49 secondsthe server from the root. So let's go inside of our root package JSON here.
3:45:543 hours, 45 minutes, 54 secondsLet's duplicate this script. Let's add a trailing comma here. I mean just a normal comma. And let's run uh dev
3:46:023 hours, 46 minutes, 2 secondsserver. And for this, I'm just going to go ahead and change this to be bun run hot packages server source index.
3:46:123 hours, 46 minutes, 12 secondsTS.
3:46:143 hours, 46 minutes, 14 secondsI think this should be good. Let me check.
3:46:193 hours, 46 minutes, 19 secondsBun rundev server works. Perfect. So you might be wondering why am I just not invoking the
3:46:293 hours, 46 minutes, 29 secondsbunr rundev command of each package respectively.
3:46:333 hours, 46 minutes, 33 secondsuh you can do that but I found it behaves odd when it when you add environment files into the mix. So because of that I'm running it this way
3:46:423 hours, 46 minutes, 42 secondsto kind of preserve the directory from which I'm running it. Um if you feel like uh this makes no sense and you want
3:46:493 hours, 46 minutes, 49 secondsto do it uh just by like calling bun uh the packages bun rundev you can do that also you can also use watch or hot here.
3:47:003 hours, 47 minutesHonestly, I'm not sure what is the difference, but both are doing exactly the same. Let me try and do bun.com
3:47:103 hours, 47 minutes, 10 secondsand maybe search here in the docs uh d-watch
3:47:173 hours, 47 minutes, 17 secondswatch a directory for changes. So that's watch mode. Okay. And dash hot is hot reloading.
3:47:273 hours, 47 minutes, 27 secondsI don't know. Um, the documentation for Hono says to use hot, but uh I'm not
3:47:353 hours, 47 minutes, 35 secondseven sure what the documentation for Open Tui says, but this is working for me. So, I'm just going to keep it this way. If you run into problems, try switching into watch or hot. Uh, great.
3:47:463 hours, 47 minutes, 46 secondsSo, that is uh what we need to start building the API. So, what I'm going to do next is the following.
3:47:583 hours, 47 minutes, 58 secondsI'm going to go inside of packages server source index.ts. And I'm just going to change things up a bit. So, uh,
3:48:063 hours, 48 minutes, 6 secondslet me go ahead and change this like this. So, hono. Then, let's go ahead and import HTTP exception here. Let's go
3:48:153 hours, 48 minutes, 15 secondsahead and change the app to initialize new hono.
3:48:203 hours, 48 minutes, 20 secondsAnd then let's go ahead and define the general on error here. The reason we are capturing on error is because I want to
3:48:303 hours, 48 minutes, 30 secondsstandardize all error messages which are being thrown so that I know how to display them in my CLI. So I'm just kind
3:48:393 hours, 48 minutes, 39 secondsof making a structure that I want to work with right now.
3:48:463 hours, 48 minutes, 46 secondsSo that is if error is an instance of HTTP exception otherwise let's log the unhandled error and let's go ahead and return the following. All right.
3:48:593 hours, 48 minutes, 59 secondsNow, uh what I want to do is I want to define the following. Instead of returning app,
3:49:073 hours, 49 minutes, 7 secondsI'm going to do port 3000 fetch app.fetch and idle timeout
3:49:163 hours, 49 minutes, 16 secondsto this amount. The idle timeout is actually super important here. Let me go ahead and add a comment here. Idle
3:49:253 hours, 49 minutes, 25 secondstimeout must be high otherwise uh LLM tool calls might not complete. That's
3:49:343 hours, 49 minutes, 34 secondswhat happened in my initial build. The LLM was simply unable to complete any complex task because uh when it used GP
3:49:443 hours, 49 minutes, 44 secondsor anything else to like search through the files, it kept timing out and I couldn't figure out like what's the problem until uh I came across this. So you need idle timeout.
3:49:563 hours, 49 minutes, 56 secondsOkay. And now let's go ahead and define uh our initial route which will be called sessions.
3:50:053 hours, 50 minutes, 5 secondsSo I'm going to go ahead inside of source here and create our routes. And I will add sessions.ds.
3:50:153 hours, 50 minutes, 15 secondsIn here, I'm going to import hono from hono http exception zod validator
3:50:243 hours, 50 minutes, 24 secondszod itself. And then I'm going to use night code shared to import find supported chat model. And you can see
3:50:323 hours, 50 minutes, 32 secondsthat when I controlclick on it, I get redirected to my package. So this is uh properly linked through the workspace tag right here.
3:50:433 hours, 50 minutes, 43 secondsGreat. For now, we are not going to have any database just yet. So, let's define a mock message with ID, RO, content,
3:50:513 hours, 50 minutes, 51 secondsmode, model, status, parts, duration, created ID, and session ID. And let's go ahead and create a type for a mock
3:50:583 hours, 50 minutes, 58 secondssession as well with an ID, title, uh the path, user ID, created at and messages, which is an array of mock
3:51:063 hours, 51 minutes, 6 secondsmessages. So, later we're just going to replace this with real database.
3:51:113 hours, 51 minutes, 11 secondsLet's go ahead and create an in-memory uh sessions table I guess. Let's go
3:51:173 hours, 51 minutes, 17 secondsahead and create a primitive uh ID uh kind of assigner here. And now let's go
3:51:243 hours, 51 minutes, 24 secondsahead and create our sessions schema. So create session schema is going to be a zod object.
3:51:333 hours, 51 minutes, 33 secondsAnd what we are going to accept is the following. We're going to accept title.
3:51:383 hours, 51 minutes, 38 secondsWe're going to accept the path and then we're going to have the initial message and the initial message will be another
3:51:453 hours, 51 minutes, 45 secondsobject and that object will have the role
3:51:523 hours, 51 minutes, 52 secondscontent and mode and finally we're going to have model and we can do a cool thing
3:51:593 hours, 51 minutes, 59 secondswith zod which is a refined chain which can then call functions like this. So we
3:52:063 hours, 52 minutes, 6 secondsare basically going to break in runtime if the supported chat
3:52:143 hours, 52 minutes, 14 secondsmodel is not found. So if someone attempts to make a post request and attempts to kind of uh pass a model that
3:52:233 hours, 52 minutes, 23 secondswe are not supporting, we're not going to be we're not going to have our API fooled. Instead, we're going to return
3:52:303 hours, 52 minutes, 30 secondsback an error. Hey, we do not support that model. So that's a cool thing you can do with refine here. All right. And
3:52:383 hours, 52 minutes, 38 secondsthe initial message itself will actually be optional. So let's just chain that as well. Now let's go ahead and create a
3:52:463 hours, 52 minutes, 46 secondsvery simple create session validator which uses Z validator passes in the type which is JSON. Then
3:52:553 hours, 52 minutes, 55 secondsdefines the schema to use which is create session schema. And in the third argument is a call back with the result or uh with the result and the context.
3:53:063 hours, 53 minutes, 6 secondsSo if the result is not success meaning the create session schema has failed which can be either because this is not a passed as a string this is not passed
3:53:153 hours, 53 minutes, 15 secondsas a string or maybe the uh scenario I was talking about unsupported model was passed. So the model right now
3:53:233 hours, 53 minutes, 23 secondscan only be this one or this one or this one or this one. Right? That's what we are doing here. We are protecting our API from unwanted models.
3:53:333 hours, 53 minutes, 33 secondsSo this is the validator. And now that we have the validator and we are throwing properly structed errors if uh
3:53:403 hours, 53 minutes, 40 secondszod fails, we can go ahead and create some routes. Let's start with a very simple get route.
3:53:483 hours, 53 minutes, 48 secondsAnd in here, what I want to do on get is just load everything. So what I'm going
3:53:563 hours, 53 minutes, 56 secondsto do is I'm going to go over my sessions. So session sessions do map.
3:54:023 hours, 54 minutes, 2 secondsI'm going to get ID title created at and I'm just going to immediately return an object for every single session with the ID title and created at. So I'm
3:54:113 hours, 54 minutes, 11 secondsbasically going to use this sessions array right here.
3:54:163 hours, 54 minutes, 16 secondsAll right, we have that. Then uh let's go ahead and create another one right here.
3:54:253 hours, 54 minutes, 25 secondsThis one is basically used to get an individual ID. Oh, and I forgot to
3:54:313 hours, 54 minutes, 31 secondsreturn the result here. Return C.JSON result. There we go.
3:54:383 hours, 54 minutes, 38 secondsAnd when we want to get an individual session, the first thing I want to add is I just want to add these mocks so we
3:54:443 hours, 54 minutes, 44 secondscan then later easily test uh an error or an exception. Let me show you how that looks like if it's hard to read through the comments.
3:54:543 hours, 54 minutes, 54 secondsI'm going to collapse this so it's easier to see. So we are basically throwing a new
3:55:023 hours, 55 minutes, 2 secondsexception here. Mock error session loading failed. And in here we are simulating a loading of 5 seconds. So I'm going to comment both of them out so
3:55:113 hours, 55 minutes, 11 secondslater we can easily try them and see how our UI behaves. So when the user wants to load an individual session, we are
3:55:193 hours, 55 minutes, 19 secondshave to extract the id from the URL params and then for now we are just going to use sessions.find and let's
3:55:283 hours, 55 minutes, 28 secondsmatch the ID. So this is just all mock now because we don't have the database yet. I just want to create some working example
3:55:373 hours, 55 minutes, 37 secondsand then let's go ahead and do the following. If there is no session, let's return C.json JSON error session not
3:55:443 hours, 55 minutes, 44 secondsfound and back a 404 and let's go ahead and return the session.
3:55:523 hours, 55 minutes, 52 secondsNow let's go ahead and create this
3:55:593 hours, 55 minutes, 59 secondswhich is basically the end point to create a new session. Uh in here I'm going to copy this mock
3:56:083 hours, 56 minutes, 8 secondsso I can easily test if session creation is slow and how it looks like. Then from here I'm going to go ahead and extract
3:56:163 hours, 56 minutes, 16 secondsinitial message and then the rest of the data from C request.valid.
3:56:223 hours, 56 minutes, 22 secondsWhat this is basically doing is is not just reading your normal C request.json JSON, but instead is using a validated version of JSON through the validator.
3:56:353 hours, 56 minutes, 35 secondsThat's what's really cool about Hono. It has really, really nice developer experience for us.
3:56:423 hours, 56 minutes, 42 secondsSo, we now know that the initial message and the whatever model is passed here has to be one of the refined models we
3:56:493 hours, 56 minutes, 49 secondshave uh made a rule for here. So at this point we can very safely use whatever the initial message is and we don't have
3:56:563 hours, 56 minutes, 56 secondsto worry. So let's go ahead and mock uh ID increment here. Let's go ahead and mock the date creation and let's go
3:57:053 hours, 57 minutes, 5 secondsahead and assign our mock messages. If the user passed along the initial message in that case let's go ahead and
3:57:143 hours, 57 minutes, 14 secondspush that to the message array. Now inside of this push we have to define everything we need. So let's increment
3:57:223 hours, 57 minutes, 22 secondsthe ID once again. Let's go ahead and add ro content mode model and model.
3:57:313 hours, 57 minutes, 31 secondsLet's go ahead and add status as complete. And then let's go ahead and add
3:57:373 hours, 57 minutes, 37 secondsparts duration created at and session ID.
3:57:453 hours, 57 minutes, 45 secondsNow let's go ahead and create the actual mock session.
3:57:513 hours, 57 minutes, 51 secondsSo mock session has ID, title, path, user ID hardcoded to mock user, created app, and messages.
3:58:013 hours, 58 minutes, 1 secondAnd then let's just go ahead and push this new session here. And let's go ahead and return C.JSON session with the
3:58:093 hours, 58 minutes, 9 seconds2011 code. And let's export default app.
3:58:173 hours, 58 minutes, 17 secondsNow that we have our sessions API mostly mocked, but it will be an easy change
3:58:243 hours, 58 minutes, 24 secondslater on. Uh let me just check. Uh okay, this HTTP exception is unused because we
3:58:323 hours, 58 minutes, 32 secondscommented it out. Okay, so now uh that we have developed the sessions.dts, we have to go back instead
3:58:413 hours, 58 minutes, 41 secondsof source index.ts DS and in here let's do const routes app.oute
3:58:513 hours, 58 minutes, 51 secondsand then forward slash sessions and let's simply get the sessions.
3:58:593 hours, 58 minutes, 59 secondsWe can get the sessions from dot routes sessions just like that we have registered to our app all of
3:59:083 hours, 59 minutes, 8 secondsthese. So get this is basically registering as sessions this is sessions id and this is sessions post request and
3:59:173 hours, 59 minutes, 17 secondsnow that we have the routes here in order to use um end to end type safety what we can do is
3:59:253 hours, 59 minutes, 25 secondswe can define an app type which is a type of routes and then when you hover over you can see that we get an RPC a
3:59:323 hours, 59 minutes, 32 secondsfully type safe uh way of communicating with the hono API and we will be able to import this because we are in a monor
3:59:403 hours, 59 minutes, 40 secondsrepo. We will be able to import this uh through dev dependencies uh in our uh CLI package and then our fetch requests
3:59:493 hours, 59 minutes, 49 secondsare going to be that more that much more secure simply because we're using the app type. So we're going to know exactly what input something takes like the
3:59:583 hours, 59 minutes, 58 secondsparam has to be the ID what output looks like. So we know exactly what kind of error to show to the user. uh we
4:00:064 hours, 6 secondsbasically know everything through this super simple type of off that's another really cool uh hono feature and besides
4:00:144 hours, 14 secondsthis you can also use open API specifications great uh I think that already uh we can
4:00:214 hours, 21 secondstry this so if I go ahead into sessions you can see it's a completely empty array if I try sessions
4:00:294 hours, 29 secondsone two three four I get an error session not found uh perfect So, it's actually working. Really, really cool.
4:00:394 hours, 39 secondsNow, what I want to do uh is I want to uh
4:00:464 hours, 46 secondshow do I uh say this? I want to like connect it to our front end even though it's currently in a mock phase. Uh I
4:00:544 hours, 54 secondswant us to be able to at least try and create some sessions. So, when we visit sessions, we can at least see an array
4:01:014 hours, 1 minute, 1 secondof some sessions. So we can see how our server and our CLI package is connected and how we are both using the shared package here. Let's go ahead and start
4:01:104 hours, 1 minute, 10 secondsinside of CLI source and let's create a new folder called lib. And in here I'm going to create API client.ts.
4:01:204 hours, 1 minute, 20 secondsAnd in here I'm going to import uh HC from hono client. And then I'm going to import app type from night code server.
4:01:314 hours, 1 minute, 31 secondsAnd then I'm finally going to go ahead and export the API client, which is basically going to use the Hono client.
4:01:404 hours, 1 minute, 40 secondsWe're going to give it the type app type. And we have to pass in the API URL. And if we don't pass it, I'm just
4:01:484 hours, 1 minute, 48 secondsgoing to fall back to localhost 3000 because that's where we are currently uh hosting it on. Great. So now that we
4:01:554 hours, 1 minute, 55 secondshave that, let's just go ahead and ensure that we have these packages in our uh CLI here. So let's go inside of CLI package.json.
4:02:064 hours, 2 minutes, 6 secondsAnd let me see what the situation is. So the first thing I'm going to do is just
4:02:124 hours, 2 minutes, 12 secondsadd night shared in my dependencies here. Here it is. So night code shared.
4:02:224 hours, 2 minutes, 22 secondsuh then I'm specifically going to add in dev dependencies night code server. Now there is a reason
4:02:294 hours, 2 minutes, 29 secondsI'm adding this to dev dependencies and not dependencies. Both would work just fine. The only difference is when you
4:02:364 hours, 2 minutes, 36 secondsbuild it, right? So right now the only reason I need my server package added to
4:02:444 hours, 2 minutes, 44 secondsmy CLI package is because of the app type. So this can technically be avoided
4:02:514 hours, 2 minutes, 51 secondsduring build. So because of that to so we don't unnecessarily uh bundle entire hono even though hono
4:03:004 hours, 3 minutesis extremely lightweight uh you know why would we bundle our server into our CLI build if we don't have to. So I'm using
4:03:094 hours, 3 minutes, 9 secondsa kind of a trick I guess uh so that our CLI package only imports it as a dev
4:03:174 hours, 3 minutes, 17 secondsdependency. So during the build, it actually won't be bundled. That's why I'm adding server to dev dependencies.
4:03:264 hours, 3 minutes, 26 secondsOkay. Uh now let me see what else I have to do. Uh in my CLI, uh I'm going to go
4:03:344 hours, 3 minutes, 34 secondsahead. Uh let me see what do I need to add.
4:03:384 hours, 3 minutes, 38 secondsUh I have React React Router. I think I need Okay, I Let me just go inside of CLI.
4:03:484 hours, 3 minutes, 48 secondsbun add we're going to add zod and I'm also going to add hono simply
4:03:564 hours, 3 minutes, 56 secondsbecause uh I need hono client let me go ahead and check yes I need
4:04:034 hours, 4 minutes, 3 secondshono client so because of that we need hono uh installed in the CLI package so
4:04:114 hours, 4 minutes, 11 secondskind of ironic because I just said we don't want to bundle hono uh from a server uh But I think you get what I
4:04:184 hours, 4 minutes, 18 secondsmean. Uh it's just safer to not couple these things together if they don't have to be coupled, right? That was kind of my point. Hono is extremely lightweight.
4:04:284 hours, 4 minutes, 28 secondsEven if you bundled it, it wouldn't be a big deal. But you know, I think it's just better if we do it this way. So to
4:04:384 hours, 4 minutes, 38 secondsconclude, in your package JSON in dev dependencies, you should have night code server from workspace version. And in
4:04:454 hours, 4 minutes, 45 secondsyour dependencies, you should have night code shared from workspace. You should have hono and you should have zod added.
4:04:534 hours, 4 minutes, 53 secondsSpecifically talking about our CLI package. And I think that that is all we
4:05:024 hours, 5 minutes, 2 secondsneed right now. So let me go ahead and focus on developing some more libs here.
4:05:074 hours, 5 minutes, 7 secondsInstead of CLI lib, I'm going to go ahead and create http errors.ts.
4:05:144 hours, 5 minutes, 14 secondsLet me go ahead and add the error response type. And then I'm going to create a a useful function here which
4:05:224 hours, 5 minutes, 22 secondswill help us extract the error message every time we receive a response. And that's going to be a lot of times. So let's go ahead and add this in the try and catch method.
4:05:344 hours, 5 minutes, 34 secondsUh in the catch method, I'm simply going to add a comment to ignore invalid error payloads and fall back to the status text, which we're going to write in a second.
4:05:444 hours, 5 minutes, 44 secondsAnd in the try method, I am basically going to attempt to await response JSON.
4:05:504 hours, 5 minutes, 50 secondsAnd I'm going to cast it what I think it's going to be, an object with an error inside. And then I'm going to add an if clause.
4:05:574 hours, 5 minutes, 57 secondsAnd I'm going to check if it actually is data. And if it's a type of string and if data error is greater than one, in
4:06:064 hours, 6 minutes, 6 secondsthat case, it's safe and we can return it. We can use it as the error.
4:06:104 hours, 6 minutes, 10 secondsOtherwise, let's go ahead and try to use response.st status text. But if that fails as well, then I'm just going to
4:06:184 hours, 6 minutes, 18 secondshardcode it with request failed with status and then response. status. So, I'm purposely wrapping this in try and catch so that this await even if it
4:06:274 hours, 6 minutes, 27 secondsbreaks uh doesn't break the entire CLI, we're just going to fall back and say, "Hey, something happened." You know, we
4:06:354 hours, 6 minutes, 35 secondsdon't know why it failed, but we don't break the app.
4:06:404 hours, 6 minutes, 40 secondsAll right. Uh now, uh let's go ahead and see what we have to do now. So I want to
4:06:484 hours, 6 minutes, 48 secondsamend my new session. Now what do we need to happen right now when we do
4:06:564 hours, 6 minutes, 56 secondsthis? Whoops. Let me go ahead go back a bit. So bon rundev cli in the root. When
4:07:034 hours, 7 minutes, 3 secondsI do hello world, what I want to do is I want this screen, the new session screen. I want it to invoke a post
4:07:124 hours, 7 minutes, 12 secondsrequest and then use the router state of my message as the initial message and
4:07:194 hours, 7 minutes, 19 secondsthen it will create a new session in this array and then redirect me to sessions ID page. Okay, so let me go
4:07:274 hours, 7 minutes, 27 secondsahead and see where we have that in CLI source. We have screens, new sessions.
4:07:334 hours, 7 minutes, 33 secondsSo yeah, home I don't think it has to be amended at all because home is doing all it needs to do redirecting the user to
4:07:404 hours, 7 minutes, 40 secondssessions new and there are no post requests being fired here. So the only post requests that are going to happen are inside of the new session. So
4:07:494 hours, 7 minutes, 49 secondsbecause of that, let's go ahead and extend our imports from React here by adding use memo and use ref. Then I'm
4:07:564 hours, 7 minutes, 56 secondsgoing to go ahead and import zod. Then from night code shared, I'm going to import the default chat model ID, I'm
4:08:054 hours, 8 minutes, 5 secondsgoing to go ahead and remove bot message and I'm going to remove user message because we're no longer uh going to need
4:08:124 hours, 8 minutes, 12 secondsthat. And then uh let me go ahead and add some more imports here. So let's add use toast API API client and get error
4:08:224 hours, 8 minutes, 22 secondsmessage. Uh we created these two in this chapter and this one is I think from like first or second chapter.
4:08:294 hours, 8 minutes, 29 secondsHowever, you should have uh all of them.
4:08:334 hours, 8 minutes, 33 secondsNow, let's go ahead and create a new session state schema so we can properly validate this state right here because
4:08:424 hours, 8 minutes, 42 secondswe didn't do this initially because we didn't have zod. But now that we have it, we can have a bit more industry standard uh checks other than, you know,
4:08:504 hours, 8 minutes, 50 secondsrandom ifs and castings and just hope for the best. Let's go ahead and add the toast hook here. Let's go ahead and
4:08:574 hours, 8 minutes, 57 secondsdefine the has started ref so that we can cancel double requests if they happen because we have to do this from
4:09:054 hours, 9 minutes, 5 secondsuh use effect which is basically on mount. Uh let's go ahead and remove this state and let's replace it with a use
4:09:134 hours, 9 minutes, 13 secondsmemo so it's a bit more memorized and better quality because now instead of
4:09:204 hours, 9 minutes, 20 secondsblindly hoping for the best we are simply going to parse the location.state state against new session state schema.
4:09:284 hours, 9 minutes, 28 secondsAnd in here we define what we expect. We expect a message. So if the home screen sends message to this will simply fail
4:09:374 hours, 9 minutes, 37 secondsbecause safe pars will not allow it unless we change message to to here as well. So make sure you're passing message from home. Make sure you're
4:09:454 hours, 9 minutes, 45 secondsvalidating message in new session. Now that we have parsed, let's go ahead and simply check did
4:09:534 hours, 9 minutes, 53 secondsparsed return with a success or not. So return parse dosuccess parse the data otherwise return back null. And we have
4:10:024 hours, 10 minutes, 2 secondsto add a loc dependency array location.state. Great.
4:10:084 hours, 10 minutes, 8 secondsNow let's go ahead uh and do a simple check here. Let's add a guard. Basically
4:10:144 hours, 10 minutes, 14 secondsif we somehow got navigated here without state let's immediately uh go home. So
4:10:214 hours, 10 minutes, 21 secondsfor that we can use this use effect and let's just quickly check if there is no state let's just go ahead and return back home just like that.
4:10:324 hours, 10 minutes, 32 secondsUh and now let's go ahead and create the session on mount. So this screen
4:10:394 hours, 10 minutes, 39 secondsspecifically exists to do this. This is like an optimistic mutation you could say. So the user rather hangs because we
4:10:484 hours, 10 minutes, 48 secondshave two options. When user hits hello world, we can either make them wait on this screen. So user hits enter and they
4:10:554 hours, 10 minutes, 55 secondsjust have to wait here with like a loading indicator here. Or we can give them a feeling of it already streaming.
4:11:024 hours, 11 minutes, 2 secondsOkay. Well, a bad example now. Uh let me just quickly fix this. Okay. I have to close that. Basically, you get what I'm
4:11:094 hours, 11 minutes, 9 secondssaying. I'm picking the better option of the two.
4:11:144 hours, 11 minutes, 14 secondsSo let's create this session uh on mount. So again we need a use effect here.
4:11:244 hours, 11 minutes, 24 secondsAnd let's again check if there is no state or if has started or ref is true meaning we already did this because
4:11:344 hours, 11 minutes, 34 secondswe immediately set it to true. So if it already fires once it will not fire twice.
4:11:404 hours, 11 minutes, 40 secondsLet's go ahead and set another variable ignore to false. And then let's go ahead and create our create session function.
4:11:504 hours, 11 minutes, 50 secondsThe create session will be an asynchronous function and it's going to have a try and catch inside. So let me go ahead and expand both.
4:11:594 hours, 11 minutes, 59 secondsSo inside of try, what we're going to do is we are going to attempt to get the result using await API client. And
4:12:064 hours, 12 minutes, 6 secondswhat's cool about API client is that we can traverse through our HONO API using
4:12:124 hours, 12 minutes, 12 secondstype safe uh well SDK you could say. You can see I can call sessions and I can choose which request I need. For
4:12:214 hours, 12 minutes, 21 secondsexample, I need a post request here and then I can open options and I can select JSON. And in here you can see I have
4:12:284 hours, 12 minutes, 28 secondsautocomplete. I need the title. So what should the title be? How about we use the first 100 characters of the message.
4:12:354 hours, 12 minutes, 35 secondsthe user has sent. Now for the path, let's go ahead and pass process.cvd.
4:12:414 hours, 12 minutes, 41 secondsAnd for the initial message that we want with this session to be created is simply going to be the following. We're going to pass along the role to be user.
4:12:534 hours, 12 minutes, 53 secondsWe're going to pass along state to be message, mode to be build, and model to be the default chat model ID. So right
4:13:024 hours, 13 minutes, 2 secondsnow we have no way of configuring any of that. So, we're just going to leave it at that. So, once we have the uh
4:13:094 hours, 13 minutes, 9 secondsresponse, first things first, if we have ignore set to uh true for whatever reason, let's do an early return.
4:13:184 hours, 13 minutes, 18 secondsAnd then let's go ahead and check if for some reason uh response was not okay.
4:13:244 hours, 13 minutes, 24 secondsLet's immediately throw new error. And let's go ahead and parse it through our get error message which is simply going
4:13:314 hours, 13 minutes, 31 secondsto check uh various ways of making this a structured error. So after we do that
4:13:394 hours, 13 minutes, 39 secondswe can finally get the newly created session. You can see it's type safe and we see exactly how it's going to look
4:13:474 hours, 13 minutes, 47 secondslike. And after we have that, guess what we can do? We can navigate to sessions
4:13:554 hours, 13 minutes, 55 secondssession ID. So, let me go ahead and collapse this so it's easier to uh look at. So, we're using the navigate function and it will redirect to
4:14:034 hours, 14 minutes, 3 secondssessions session 1 2 3. We're going to use replace true and we're going to pass
4:14:104 hours, 14 minutes, 10 secondsthe uh session through router state once again. And in the error, let's go ahead
4:14:164 hours, 14 minutes, 16 secondsand catch that again. If ignore is present, let's return. Otherwise, let's go ahead and trigger a toast message,
4:14:244 hours, 14 minutes, 24 secondswhich will show a variant of error. And in here, it's going to simply show an
4:14:314 hours, 14 minutes, 31 secondserror fail to create session or if we can read from the message directly. And if [snorts] that happens to actually fail, we cannot leave the user on this
4:14:404 hours, 14 minutes, 40 secondsnew session screen. So, let's make sure that we navigate back to the homepage.
4:14:454 hours, 14 minutes, 45 secondsBrilliant. So now that we have uh create session function defined, we have to call it. So right here at the bottom,
4:14:534 hours, 14 minutes, 53 secondslet's simply call create session. And what's important is that we uh create the following. We have to do an unmount
4:15:024 hours, 15 minutes, 2 secondsin which we set ignore to true. So the reason we need this is because create session, let's say it takes 5 seconds
4:15:104 hours, 15 minutes, 10 secondsand in the meantime this component gets destroyed. uh we have to prevent anything from happening by adding ignore
4:15:184 hours, 15 minutes, 18 secondsset to true. So even if we get an error, let's just do an early return either in try or catch because otherwise you would
4:15:264 hours, 15 minutes, 26 secondsget uh invalid uh react usage. You could say like an antiattern. You need to cancel your requests during unmount.
4:15:354 hours, 15 minutes, 35 secondsAnd in the dependency array here, let's go ahead and let's add state and toast.
4:15:414 hours, 15 minutes, 41 secondsWe now no longer have to check for the message. We can just check if there is no state because if uh it's not properly parsed, it's going to be null.
4:15:494 hours, 15 minutes, 49 secondsAnd we can now remove the bot message and the error message and we can just show what the actual user sent. Uh
4:15:574 hours, 15 minutes, 57 secondsbrilliant. So this should actually work already right now. So my local host 3000
4:16:064 hours, 16 minutes, 6 secondsuh sessions, let me refresh. Oh, couldn't be reached. Oh yeah. So let's try this. If I do hello world now, you
4:16:144 hours, 16 minutes, 14 secondscan see I'm getting an error. Unable to connect. Is the computer able to access the URL? And if I go ahead and do bun rundev server now and it's running on
4:16:234 hours, 16 minutes, 23 secondslocalhost 3000 and I do hello world, you can see that now it's a completely different thing. The other thing I'm
4:16:304 hours, 16 minutes, 30 secondsnoticing is that my user message u is not being shown. So I'm not really sure
4:16:374 hours, 16 minutes, 37 secondswhat's happening here. Uh, I think I know what's happening here. I think it's actually all good. I think it just
4:16:444 hours, 16 minutes, 44 secondsredirected me to session ID screen and that screen is not fully developed. But you can see that localhost 3000 sessions now has its first session. Hello world.
4:16:564 hours, 16 minutes, 56 secondsReally, really cool. So, if I go ahead and end this and try again and in here I
4:17:034 hours, 17 minutes, 3 secondsdo what is up again. I'm going to get redirected here. And if I refresh, here it is. Another one. What is up? Really,
4:17:124 hours, 17 minutes, 12 secondsreally, really cool. So, let's go ahead and make the new uh not new, let's make
4:17:184 hours, 17 minutes, 18 secondsthe session ID screen make sense now as well because session ID now has to fetch the session by the ID. So, let's go inside of session.tsx.
4:17:304 hours, 17 minutes, 30 secondsYou can see yes, this is a completely empty session shell. So let's go ahead uh and make it actually fetch things.
4:17:394 hours, 17 minutes, 39 secondsSo besides the session shell, let's go ahead and add uh all of these from React. Let's add use params, use
4:17:474 hours, 17 minutes, 47 secondslocation, use navigate, Z from zod and infer response type from hono client.
4:17:554 hours, 17 minutes, 55 secondsThen in here let's add all three which is the user message bot message and
4:18:034 hours, 18 minutes, 3 secondsfinally uh the error message. Then let's go ahead and add the use toast API client and get error message. Perfect.
4:18:154 hours, 18 minutes, 15 secondsSo we need all of those. Now let's go ahead and create a type session data. we
4:18:224 hours, 18 minutes, 22 secondscan use info response type and then it'll go through type of API client sessions and then we get the id path and
4:18:324 hours, 18 minutes, 32 secondswe are specifically looking for the get request. So what is this super complicated thing? In the simplest uh
4:18:394 hours, 18 minutes, 39 secondsway possible, we need the type that our server routes session returns for
4:18:494 hours, 18 minutes, 49 secondswhere is it? Get id right. So we are creating the type so that we know
4:18:574 hours, 18 minutes, 57 secondsexactly what will be returned. Okay. So we are using infer response type for that. And then we are reading through API client sessions. We are specifically
4:19:064 hours, 19 minutes, 6 secondschoosing the session ID route and then specifically the get one the get request and in here you also have to specify
4:19:154 hours, 19 minutes, 15 secondswhich return code because it can have multiple variations right so it's a very uh specific way to get the type that you need.
4:19:264 hours, 19 minutes, 26 secondsNow let's go ahead and define a constant session location schema which is a ZOD object. The session is going to be a
4:19:354 hours, 19 minutes, 35 secondscustom ZOD rule. It's going to use the session data from above. And in here we are going to make sure that it's not
4:19:424 hours, 19 minutes, 42 secondsnull and that the type of the value is object and that it has the ID inside.
4:19:494 hours, 19 minutes, 49 secondsNow that we have that, let's go ahead and create a handy component called chat message. Now chat message will be used
4:19:574 hours, 19 minutes, 57 secondsto determine whether we should display the user message, bot message or the error message. For that our chat message
4:20:064 hours, 20 minutes, 6 secondsneeds to have proper types. So it will receive message and let's go ahead and create the type for this.
4:20:164 hours, 20 minutes, 16 secondsSo I'm going to go ahead and open this message type is going to use session
4:20:244 hours, 20 minutes, 24 secondsdata and then it's going to infer through messages and then simply to select like an individual type of this
4:20:324 hours, 20 minutes, 32 secondsarray you just type in number like that and then when you hover over message you can see that you see the exact type of the message that we need.
4:20:424 hours, 20 minutes, 42 secondsNow in here, let's go ahead and check for the role. So if message roll is user, we can go ahead and return the
4:20:514 hours, 20 minutes, 51 secondsuser message. Let me just go ahead and properly do this like this user message and pass along the message. Uh we don't
4:20:584 hours, 20 minutes, 58 secondsneed to do else if. We can just do this three times.
4:21:034 hours, 21 minutes, 3 secondsThe reason we can do it like this is because it will never be both user and something else. And we are using return
4:21:104 hours, 21 minutes, 10 secondswhich is uh which ends the else if chain. So we can do if if if [snorts] I just think it's like cleaner this way.
4:21:184 hours, 21 minutes, 18 secondsIf it's error let's go ahead and use error message. And then for the last one we don't even need an if clause. That's
4:21:264 hours, 21 minutes, 26 secondsjust going to be like the default state which will be a bot message which uses
4:21:324 hours, 21 minutes, 32 secondscontent prop and model. So let's go ahead and pass it message.
4:21:384 hours, 21 minutes, 38 secondsThere we go. So that is our handy chat message component. Now let's go ahead and properly develop this session here.
4:21:484 hours, 21 minutes, 48 secondsSo we are going to need the ID from the params location navigate and toast.
4:21:564 hours, 21 minutes, 56 secondsNow we have to go ahead and prefetch the value here using memo.
4:22:064 hours, 22 minutes, 6 secondsSo inside of here what we are going to do is the following. We are first going to check if we can safely parse the
4:22:144 hours, 22 minutes, 14 secondslocation state. If you forgot the location state is what we receive from new session.
4:22:234 hours, 22 minutes, 23 secondsSo when we create the session on mount from new session, what do we do? We redirect to sessions session ID and we
4:22:314 hours, 22 minutes, 31 secondspass along the newly created session from here.
4:22:354 hours, 22 minutes, 35 secondsSo the first thing we have to do here is that's what's we call prefetched,
4:22:424 hours, 22 minutes, 42 secondsright? Because there are two ways user can navigate to this page, the session page.
4:22:484 hours, 22 minutes, 48 secondsThe first one is if user opens up a session dialogue sessions dialogue and simply selects one of the older
4:22:554 hours, 22 minutes, 55 secondssessions. In that case we are not going to have this. Okay. But the other way is
4:23:034 hours, 23 minutes, 3 secondsthat the user receives a redirect from session from new session with the state.
4:23:104 hours, 23 minutes, 10 secondsTechnically we could make this simpler and not pass this at all and just load from the ID. We could technically do that, but why make the user wait twice?
4:23:224 hours, 23 minutes, 22 secondsYou know, we can prefetch. So, let's do it. So, this is all it is. We're just checking if we successfully parsed
4:23:304 hours, 23 minutes, 30 secondswhatever has been sent to us through location state. Basically, if parsed uh is a success, it means that the session
4:23:394 hours, 23 minutes, 39 secondsID screen was loaded through the new session redirect because it's passing along the session here.
4:23:474 hours, 23 minutes, 47 secondsAnd of course, very important, we need to pass this here.
4:23:534 hours, 23 minutes, 53 secondsGreat. So that is prefetched. And then we can go ahead and establish our session here and set session use state
4:24:014 hours, 24 minutes, 1 secondsession data and give it an initial value of prefetched. So yes, technically we could not have this at all and just make this null and then every single
4:24:104 hours, 24 minutes, 10 secondstime just uh fetch it here from the use effect, but that's making the user wait twice because technically we create it
4:24:194 hours, 24 minutes, 19 secondshere in the new session. This is technically fetching it. Why wouldn't we just pass it along and call that a
4:24:284 hours, 24 minutes, 28 secondsprefetch, right? That's what the prefetch is doing here. I hope that kind of cleared it up. Now we do the usual
4:24:354 hours, 24 minutes, 35 secondspath right the user loads this screen by simply selecting one of their older sessions. So in that case first thing we
4:24:444 hours, 24 minutes, 44 secondsdo is we check if this was already prefetched. If it is let's do an early return. So that's for the scenario
4:24:514 hours, 24 minutes, 51 secondsabove. Uh otherwise let's go ahead and reset the session by using set session null. Let's go ahead and do another
4:24:594 hours, 24 minutes, 59 secondsearly return if the ID is missing. Let's prepare for unmount by adding the ignore variable. And then let's start
4:25:064 hours, 25 minutes, 6 secondsdeveloping the fetch session uh asynchronous function.
4:25:124 hours, 25 minutes, 12 secondsAs usual, we're going to have our try and cache here. Let's go ahead and start with try. So we are going to use our API
4:25:194 hours, 25 minutes, 19 secondsclient sessions ID get. And inside of here we can use our type save configuration by passing along the
4:25:274 hours, 25 minutes, 27 secondsparam. Which param? The ID. If you try to for example pass ID2, you can see you
4:25:344 hours, 25 minutes, 34 secondsget an error here. Why? Well, because in our hono we specifically look for ID.
4:25:404 hours, 25 minutes, 40 secondsUnless you change this to ID2, you can see that now this is correct. But then you also have to change it here. You can see how cool this is, right? The moment
4:25:494 hours, 25 minutes, 49 secondsyou save it, the moment the entire app type uh resets.
4:25:544 hours, 25 minutes, 54 secondsThat is basically why I really really like working with Hono. It's lightweight, it's fast, and it's really cool to work with. Uh, now let's go
4:26:034 hours, 26 minutes, 3 secondsahead and handle the case if this component has unmounted. So do an early return. If the response here, I mean the
4:26:114 hours, 26 minutes, 11 secondsrequest has failed, meaning not okay, throw new error and go ahead and parse it through get error message which we developed.
4:26:204 hours, 26 minutes, 20 secondsOtherwise, we can go ahead and set session to the result of await rest.json.
4:26:284 hours, 26 minutes, 28 secondsIf you want to, you can make this into constants like fetched session or maybe
4:26:354 hours, 26 minutes, 35 secondsbetter resolved session like this or resolve. There we go. Like
4:26:454 hours, 26 minutes, 45 secondsthat. And in the error here, first things first, we check if the component has unmounted. If it did,
4:26:534 hours, 26 minutes, 53 secondslet's do an early return. Otherwise, let's go ahead and do a toast show variant error and then go ahead and
4:27:004 hours, 27 minutescheck what kind of message we can throw here. And if we do receive an error, let's navigate the user away from this screen back to the homepage by using navigate forward slash and replace true.
4:27:134 hours, 27 minutes, 13 secondsAnd once we have that, let's not forget that we have to call fetch session. And of course, we have to make sure that we are properly unmounting by doing this.
4:27:244 hours, 27 minutes, 24 secondsLet's not forget to pass along id prefetched toast and navigate.
4:27:314 hours, 27 minutes, 31 secondsNow let's go ahead and do the following.
4:27:334 hours, 27 minutes, 33 secondsIf there is no session yet, let's return an empty session shell with nothing to submit for and input disabled.
4:27:424 hours, 27 minutes, 42 secondsOtherwise, we're going to go ahead and uh still have a completely empty session shell, but this time it's not going to
4:27:514 hours, 27 minutes, 51 secondsbe loading or anything, and it's not going to be a self-closing tag. So, let me just change this.
4:28:004 hours, 28 minutesCool. It did it for me. And inside of here, I'm going to go ahead and iterate over each session message. And I'm going
4:28:094 hours, 28 minutes, 9 secondsto use my chat message component. So it's going to determine what component it should render. There we go. So
4:28:174 hours, 28 minutes, 17 secondsbasically now this session ID component has two ways of displaying data. Either if it's prefetched, if it's being
4:28:264 hours, 28 minutes, 26 secondsredirected through new session and then we have the new session fetched for us and passed along in the state or if we don't we just have the ID. In that case
4:28:354 hours, 28 minutes, 35 secondswe technically skip this part and just call the fetch session. So let's try if I do uh this is prefetched.
4:28:444 hours, 28 minutes, 44 secondsYou can see it immediately loads it. So it's a very fast experience. And if I refresh here we have another one. This
4:28:524 hours, 28 minutes, 52 secondsis prefetched. You might notice that it has been completely reset. Uh that is because it's just an in-memory uh store.
4:29:014 hours, 29 minutes, 1 secondIt's not a real database. So every time hot reload happens your database clears.
4:29:064 hours, 29 minutes, 6 secondsWe are not uh we don't have the real database just yet.
4:29:114 hours, 29 minutes, 11 secondsBrilliant. So really really cool. So hello world. You can see it works. So
4:29:184 hours, 29 minutes, 18 secondswhat should we try doing? I would recommend going inside of sessions.ts.
4:29:234 hours, 29 minutes, 23 secondsLet's go inside of our post request and let's try this. Let's try simulating
4:29:294 hours, 29 minutes, 29 secondsslow session creation. So if I do slow creation, you can see how that's going
4:29:364 hours, 29 minutes, 36 secondsto look like. For five seconds, it will display this. But the UX was changed immediately for the user. And you can
4:29:434 hours, 29 minutes, 43 secondssee it's almost seamless when it redirects to the session ID. Now let's go ahead and try the error as well.
4:29:534 hours, 29 minutes, 53 secondsSo let me go ahead and just close this bun rundev CLI. Hello world. Error and
4:30:004 hours, 30 minutesslow. So now it's waiting for five seconds in the new session screen and then it's going to error and it redirects me back to uh the homepage.
4:30:114 hours, 30 minutes, 11 secondsGreat. So good UX so far. Let's make sure to comment these out. And now I'm going to go ahead instead of get ID and in here I'm going to go ahead and make
4:30:194 hours, 30 minutes, 19 secondsit slow again. And I'm going to make it throw an error. And you will see how that's going to look like. So, oh
4:30:274 hours, 30 minutes, 27 secondsactually I don't think we can demonstrate that.
4:30:314 hours, 30 minutes, 31 secondsWell, let me show you. If I do hello world now, this will work just fine even though I specifically throw the error
4:30:404 hours, 30 minutes, 40 secondsand I specifically tell it to wait 5 seconds. That is because we have prefetched it. So to demonstrate, if I
4:30:484 hours, 30 minutes, 48 secondsgo inside of CLI screens session.tsx tsx. And if I turn off my prefetched
4:30:564 hours, 30 minutes, 56 secondshere, actually just make uh yeah, let me try. How do I make this
4:31:034 hours, 31 minutes, 3 secondsreturn null like a hack I guess? So I purposely not
4:31:104 hours, 31 minutes, 10 secondsmake it prefetched. Now if I do this, you can see that it's obviously broken, right? Something is not behaving as it
4:31:184 hours, 31 minutes, 18 secondsshould. Here it is. Session loading failed. So what happens is that it initially just loaded this which I guess
4:31:264 hours, 31 minutes, 26 secondswe have to do loading. I'm not sure why I'm not passing along that prop because technically that's what's happening.
4:31:344 hours, 31 minutes, 34 secondsHello world. Yeah, now it's kind of simulating the new session state in the session ID state. So we are basically
4:31:424 hours, 31 minutes, 42 secondshaving this kind of trampoline I guess you could call of new session creation.
4:31:474 hours, 31 minutes, 47 secondsBut it's all with the purpose of creating a high quality CLI uh terminal user experience because these are really
4:31:544 hours, 31 minutes, 54 secondshard to do. So let me go ahead and make sure that this one is loading because I think it should be loading. Uh and let
4:32:034 hours, 32 minutes, 3 secondsme remove the return null here. So that's what prefetched is for. And let me show you one last example. I'm going
4:32:104 hours, 32 minutes, 10 secondsto comment out this and I will just leave out this. And you can see that now remember how fast
4:32:174 hours, 32 minutes, 17 secondsthe initial creation was. Well, now uh oh uh well now it's still fast because
4:32:244 hours, 32 minutes, 24 secondsof the prefetch of course but if I do the thing again return null now it will behave differently. So hello world you
4:32:334 hours, 32 minutes, 33 secondscan see that now I have to wait five seconds again. So that's why we do the prefetch. So it doesn't have to go
4:32:404 hours, 32 minutes, 40 secondsthrough two API requests both the post request and then another get request using the ID from the params. Uh
4:32:504 hours, 32 minutes, 50 secondsbrilliant. So that is it for uh this step right here which is server and API client. And now what we have to do is we
4:32:594 hours, 32 minutes, 59 secondshave to add our database. We have to connect it to neon posgress and define the schema and replace all of the mock
4:33:064 hours, 33 minutes, 6 secondsthings uh with real database real persistent table.
4:33:124 hours, 33 minutes, 12 secondsLet's start by creating the actual database package. So I'm going to go ahead and create a new folder and I'm going to call it database. Then in here
4:33:214 hours, 33 minutes, 21 secondsI'm going to create a package.json and I'm going to go ahead and do the usual. I'm going to give it a name code
4:33:304 hours, 33 minutes, 30 secondsdatabase. I'm going to give it a type of module which we actually need for Prisma. I'm going to make it private.
4:33:394 hours, 33 minutes, 39 secondsAnd for the exports, I'm going to add two the index and also the enums separately.
4:33:464 hours, 33 minutes, 46 secondsI'm going to go ahead and add scripts database generate which is going to run bunx prisma generate. And I'm going to
4:33:544 hours, 33 minutes, 54 secondsleave it at that for now because we're going to add the packages in a moment.
4:33:594 hours, 33 minutes, 59 secondsSo now we have our database package here. Let's go ahead and set up Prisma.
4:34:084 hours, 34 minutes, 8 secondsSo we have a new project. Now let's go ahead and install the following dependencies. So we need to add Prisma
4:34:164 hours, 34 minutes, 16 secondsand types node as dev dependencies. So for that I'm going to go ahead inside of my packages database.
4:34:274 hours, 34 minutes, 27 secondsLet's add those. And once those are added, I'm going to add the other ones.
4:34:354 hours, 34 minutes, 35 secondsPrisma client, Prisma adapter, Postgress, and environment.
4:34:404 hours, 34 minutes, 40 secondsOnce we have that, let's go ahead and uh I think we Oh yeah, we need tsconfig,
4:34:464 hours, 34 minutes, 46 secondsbut we can just extend our uh base one tsconfig.json.
4:34:534 hours, 34 minutes, 53 secondsLet me just jump into server and just copy the contents of this and paste it.
4:34:594 hours, 34 minutes, 59 secondsI think pretty much everything that we need here. Module is ES module is preserved. Okay, I think it's completely
4:35:074 hours, 35 minutes, 7 secondsokay. I didn't I didn't modify anything regarding my DS config. So I don't think
4:35:164 hours, 35 minutes, 16 secondsthat we need to do anything special. I'm looking through my source code right now just to see if there's anything special
4:35:234 hours, 35 minutes, 23 secondsI did. I don't think there is but if something breaks um yeah we can easily just switch it. Okay. So let's leave this as is.
4:35:344 hours, 35 minutes, 34 secondsUh we already have type modules so that's fine. And now let's initialize Prisma ORM.
4:35:414 hours, 35 minutes, 41 secondsSo I'm going to go ahead. I'm not going to use the output command. I'm just going to run bonex bun prisma in it. So
4:35:494 hours, 35 minutes, 49 secondsmake sure you're running this within your database package. We already have the packages installed and initialized
4:35:564 hours, 35 minutes, 56 secondsPrisma uh in your project. Let's see did it do that correctly or not? because I
4:36:024 hours, 36 minutes, 2 secondsthink I'm pretty sure I want this to be within my source folder. But in here, I don't think it did it in the source
4:36:094 hours, 36 minutes, 9 secondsfolder. Yeah. Uh it did it uh here. But maybe that's okay.
4:36:194 hours, 36 minutes, 19 secondsYeah, actually it's it's okay. It's perfectly fine for it to work this way.
4:36:244 hours, 36 minutes, 24 secondsSo now what I want to do is I want to go inside of my Prisma config here and I just want to see if everything
4:36:334 hours, 36 minutes, 33 secondsworks. So we have define config, we have environment here, we have database URL here and what we should start doing now
4:36:434 hours, 36 minutes, 43 secondsis we should create a global.environment.example example and in here let's go ahead and add API
4:36:524 hours, 36 minutes, 52 secondsURL and database URL. Let's copy the environment example and let's go ahead and create just environment here and
4:37:024 hours, 37 minutes, 2 secondssave this file. And now let's grab our database URL by heading to Neon create an account and
4:37:094 hours, 37 minutes, 9 secondsthen go ahead and click new project. I'm going to call this night code development. And I'm going to leave everything as is.
4:37:174 hours, 37 minutes, 17 secondsAnd I'm going to hit create. And just like that, uh, in less than 30 milliseconds, uh, let's go ahead and get the connection string. So, I'm going to
4:37:264 hours, 37 minutes, 26 secondscopy the snippet just like that and paste it here. There we go. So, now uh, we have the database set up.
4:37:354 hours, 37 minutes, 35 secondsLet's go ahead and see what we have to do next here.
4:37:424 hours, 37 minutes, 42 secondsWe have this defined and now we would need the Prisma schema. So let's see database Prisma. We have schema.prisma
4:37:514 hours, 37 minutes, 51 secondshere. Uh this is already set to postress.
4:37:564 hours, 37 minutes, 56 secondsLet me check the config once more. Do I need anything special here? I don't think I do. I think this should work just the way it is.
4:38:074 hours, 38 minutes, 7 secondsEnvironment from Prisma config. Yeah, I think I think it will not be able to read the environment file that I have in
4:38:154 hours, 38 minutes, 15 secondsthe root of my project. Yeah, you can see it it wants to read the environment file here. Now, I'm not really sure
4:38:234 hours, 38 minutes, 23 secondswhat's the best practice with monor repos. Should you have environment in each package? I'm pretty sure that that sounds normal. That shouldn't sound too
4:38:304 hours, 38 minutes, 30 secondsodd, but I'm just going to keep all of them um in my root here. So I'm going to
4:38:374 hours, 38 minutes, 37 secondsremove that environment file from the database package and I'm just going to keep it and maintain everything here simply because my monor repo is very simple.
4:38:464 hours, 38 minutes, 46 secondsUh so what do we need to do? Let me go ahead and just create my schema prisma
4:38:534 hours, 38 minutes, 53 secondsbecause I want to try and push what I need and then we'll see if we're going to get any errors. So let me go ahead
4:39:004 hours, 39 minutesand create a role. A role of a message can be user assistant or error. Let me create an enum mode. The user can either
4:39:094 hours, 39 minutes, 9 secondsbe in build or plan mode. And let me go ahead and create an enum message status.
4:39:154 hours, 39 minutes, 15 secondsSo the user can either have a completed message or uninterrupted message. Same goes for uh the AI model. Then let's go
4:39:234 hours, 39 minutes, 23 secondsahead and create the session. The session is going to have an ID with a default CU ID, a required user ID, a
4:39:314 hours, 39 minutes, 31 secondsrequired title, optional path, some timestamps, and a relation to the message model which we don't yet have.
4:39:394 hours, 39 minutes, 39 secondsAnd we're going to create an index over user ID. We are not going to have a relation to the user because we are not going to have the user model. We're
4:39:464 hours, 39 minutes, 46 secondsgoing to use a third party out provider and then we're going to store just the user ID here.
4:39:534 hours, 39 minutes, 53 secondsNow let's go ahead and create the message. Here it is. So a message is going to have the ID session ID which is
4:40:024 hours, 40 minutes, 2 secondsbasically a relation to the session as we defined right here. Ro using our enum same for message status model content
4:40:104 hours, 40 minutes, 10 secondsparts which is basically uh JSON and these parts are going to be what we
4:40:184 hours, 40 minutes, 18 secondsdeveloped in shared here. When you see schemas this these are basically parts text delta reasoning delta tool call tool
4:40:274 hours, 40 minutes, 27 secondsresult done error that's what we're going to store in the database that's why we are using an ambiguous JSON so we
4:40:354 hours, 40 minutes, 35 secondsneed mode duration and uh what we define here is that when we decide to delete
4:40:444 hours, 40 minutes, 44 secondsuh a session we're also going to cascade and delete all messages belonging to that session session. So we are not going to have any orphaned messages. All
4:40:524 hours, 40 minutes, 52 secondsright. So that is our uh let me expand just in case you want to see how it looks like in one line. Here it is. So
4:41:004 hours, 41 minutesnow what we should do is we should generate and we should push to our database. So let's see if we can do that
4:41:084 hours, 41 minutes, 8 secondsor not. So I'm going to go uh make sure you are inside of your packages database and let me do banexprisma generate.
4:41:184 hours, 41 minutes, 18 secondsLet me try this first. And yeah, it's missing database URL. So again, two ways of fixing that. You can either maintain
4:41:264 hours, 41 minutes, 26 secondsanother environment file within your database, which I think is a normal practice, or we can go inside of the
4:41:334 hours, 41 minutes, 33 secondsconfig here. And what we can do here is well import
4:41:424 hours, 41 minutes, 42 secondsenvironment from dot environment and we can import path from path and
4:41:504 hours, 41 minutes, 50 secondsthen we can do environment.config and define the path and simply traverse
4:41:584 hours, 41 minutes, 58 secondsback to the top folder. So outside of here and aim at this environment file.
4:42:044 hours, 42 minutes, 4 secondsThat's what I'm doing in here. And I think that now I should be able let me try banx prisma generate. And just like
4:42:134 hours, 42 minutes, 13 secondsthat it's now working. So again two solutions you know either what I just did or if for whatever reason path is
4:42:204 hours, 42 minutes, 20 secondsnot working for you again Windows, Linux, Mac OS uh all of them work differently. you can just maintain
4:42:284 hours, 42 minutes, 28 secondsanother environment file in your database. Just make sure you know you don't accidentally forgot to upgrade it if you change something.
4:42:364 hours, 42 minutes, 36 secondsGreat. So, we have that now. And now we should be able to also push. So, if I go
4:42:434 hours, 42 minutes, 43 secondsinside of my neon database here and if I go inside of tables, I currently have uh
4:42:494 hours, 42 minutes, 49 secondsno tables in my public schema. But if I do BNX Prisma database push, I should be
4:42:574 hours, 42 minutes, 57 secondsable to push to this neon database. You can see it managed to read injected environment file. You can see it managed to do that and the database is now in
4:43:054 hours, 43 minutes, 5 secondssync. So if I refresh this, I should now see message and session. Brilliant. So
4:43:114 hours, 43 minutes, 11 secondsthat is properly set up. And um now well now that we have the schema and we have
4:43:204 hours, 43 minutes, 20 secondsthe config, let's go ahead inside of the database and let's create a new folder called source.
4:43:284 hours, 43 minutes, 28 secondsAnd let's go ahead and create client.ts.
4:43:354 hours, 43 minutes, 35 secondsIn here again I'm going to import environment config Prisma postgress adapter and
4:43:434 hours, 43 minutes, 43 secondsPrisma client in here it cannot find the module and I'm starting to think that this
4:43:514 hours, 43 minutes, 51 secondsmight be because of the TS config here could be I'm not sure
4:43:584 hours, 43 minutes, 58 secondshow about H Prisma client And
4:44:074 hours, 44 minutes, 7 secondslet me see what I'm doing incorrectly here. Oh, generated is loaded at the
4:44:144 hours, 44 minutes, 14 secondstop. So if I just go okay if I just go to back then it works. Okay, my apologies. So Prisma client works fine.
4:44:244 hours, 44 minutes, 24 secondsLet's get the database URL using process environment database URL. If it's missing, let's go ahead and throw the
4:44:314 hours, 44 minutes, 31 secondserror. And let's go ahead and create an adapter.
4:44:354 hours, 44 minutes, 35 secondsAnd finally, let's go ahead and export col database new Prisma client and the adapter.
4:44:424 hours, 44 minutes, 42 secondsAnd now let's go ahead and create enms.
4:44:514 hours, 44 minutes, 51 secondsAnd in here I want to reexport all the enmsiums that we need roll mode and message status. I'm going to explain why
4:45:004 hours, 45 minutesI'm doing this in a separate file in a second. So we now have a client. We now have an eniums. Let's go ahead and create one more index.ts.
4:45:104 hours, 45 minutes, 10 secondsAnd in here I'm simply going to go ahead and export database from client.ts.
4:45:164 hours, 45 minutes, 16 secondsAnd I'm going to export everything from generated Prismaclient.ts. So, let me check. Do I really need this?
4:45:224 hours, 45 minutes, 22 secondsI don't. But I think I do need it for this. Oh, I don't. Cool. Um, actually, I think the reason I'm adding TS is
4:45:304 hours, 45 minutes, 30 secondsbecause my builds were failing without it. So, I'm going to stay true to my source code and I'm going to import with the extension here.
4:45:404 hours, 45 minutes, 40 secondsUh, now if you remember in my package JSON for the database, I added two exports. So, one is just index and one
4:45:484 hours, 45 minutes, 48 secondsis for enums. uh the reason is very similar as to why I added nightcode server in dev dependencies of CLI. So
4:45:574 hours, 45 minutes, 57 secondsnow we will be able to uh specifically import night code database enums and I
4:46:064 hours, 46 minutes, 6 secondswon't have to inject an entire Prisma uh into the bundle because we need enumes uh both at runtime and for some
4:46:144 hours, 46 minutes, 14 secondsvalidation I think so because of that we cannot add it in dev dependencies we have to add it in dependencies and we're going to solve the tree shaking issue uh
4:46:244 hours, 46 minutes, 24 secondswith a separate export of enums Great. So we have that done.
4:46:334 hours, 46 minutes, 33 secondsSo let me see what we should be doing uh next. Now we should go inside of packages server package.json
4:46:424 hours, 46 minutes, 42 secondsand in dependencies here we should add night code database
4:46:484 hours, 46 minutes, 48 secondsworkspace like that. And let's also do
4:46:564 hours, 46 minutes, 56 secondsclear. Let's go inside of packages server bun add dot environment here as
4:47:034 hours, 47 minutes, 3 secondswell. So you should now have environment inside of your packages server because uh we need to read from that environment file again.
4:47:134 hours, 47 minutes, 13 secondsOkay.
4:47:154 hours, 47 minutes, 15 secondsNow let's go inside of packages server source routes sessions.ts
4:47:244 hours, 47 minutes, 24 secondsand in here I'm going to go ahead and import the database from night code database. So now I have the Prisma
4:47:324 hours, 47 minutes, 32 secondsclient here and I can finally get rid of the mock messages entirely. I can get rid of the mock session. I can get rid of this mock creation and everything.
4:47:434 hours, 47 minutes, 43 secondsI'm going to replace the ro here to be an enum and it's going to be using roll which we can uh import either from night
4:47:524 hours, 47 minutes, 52 secondscode database directly but since this are this is going to mess with the builds so let's rather do enums
4:48:014 hours, 48 minutes, 1 secondso roll like this and let's also add roll mode message status
4:48:084 hours, 48 minutes, 8 secondsso this is znium roll And for the mode, let's do cnume mode like that. Then
4:48:184 hours, 48 minutes, 18 secondslet's go ahead and change the get request. So the get request is no longer
4:48:254 hours, 48 minutes, 25 secondsgoing to be this. Instead, the get request is going to be an
4:48:324 hours, 48 minutes, 32 secondsasynchronous function which simply awaits database session find many order by latest created. And
4:48:404 hours, 48 minutes, 40 secondslet's just select ID title and created that. And then we can go ahead and simply return that back.
4:48:504 hours, 48 minutes, 50 secondsNow let's go ahead and oh let me comment this out.
4:48:564 hours, 48 minutes, 56 secondsSo in here we do need the ID param but we're not going to like filter through the sessions. Instead, we're going to go ahead and properly fetch using Prisma.
4:49:084 hours, 49 minutes, 8 secondsSo, we can you find a unique session using database session find unique where the ID matches and let's include all
4:49:154 hours, 49 minutes, 15 secondsmessages included in that session by uh newest creative.
4:49:234 hours, 49 minutes, 23 secondsGreat. If there is no session, let's throw an error. Perfect. And now let's go ahead and do this one, which is the post request. So in here we can delete
4:49:324 hours, 49 minutes, 32 secondsthis entire mock creation. [snorts] None of that is needed. Let's only keep the initial message and data extraction.
4:49:434 hours, 49 minutes, 43 secondsSo completely empty post request now.
4:49:464 hours, 49 minutes, 46 secondsAnd what we're going to do is we're going to initialize sessions create here.
4:49:554 hours, 49 minutes, 55 secondsWe're going to open data And in here, I'm just going to spread
4:50:034 hours, 50 minutes, 3 secondseverything data related. And I'm going to hardcode user ID to be mock user because we don't have AL yet. And then
4:50:114 hours, 50 minutes, 11 secondsI'm just going to spread this optional message if it exists. So, if it exists,
4:50:194 hours, 50 minutes, 19 secondsI'm going to go ahead and use their API, which allows me to communicate with the messages schema and call the create
4:50:284 hours, 50 minutes, 28 secondsmethod on them and pass along the initial message data and give it a status of complete. And then at the end,
4:50:364 hours, 50 minutes, 36 secondssince we are going to use this session as the prefetch for the session, we also need to include the messages.
4:50:434 hours, 50 minutes, 43 secondsAnd then at the end all we have to do is return C.JSON 2011.
4:50:514 hours, 50 minutes, 51 secondsBrilliant. So uh that is our sessions.ts fixed and I think that now
4:51:014 hours, 51 minutes, 1 secondeverything should be working as it was before. We don't have to change anything from the front end. I think so. Let me just go ahead and check now.
4:51:104 hours, 51 minutes, 10 secondsLet me go back here. back bun rundev C cli let's go ahead and do bunr rundev server
4:51:174 hours, 51 minutes, 17 secondsin the other one and let me try and do persisted message stored in the database
4:51:264 hours, 51 minutes, 26 secondsand let's see looks good on the front end side how about we refresh our neon database here messages and here is our
4:51:354 hours, 51 minutes, 35 secondsmessage status complete model claude opus persisted message stored in the database and the session creat created
4:51:424 hours, 51 minutes, 42 secondswith the mock user ID and the title similar to I mean identical to the um to
4:51:494 hours, 51 minutes, 49 secondsthe message. I even have my path passed along and the timestamps. Brilliant. So
4:51:554 hours, 51 minutes, 55 secondsvery very simple to replace our mocked uh solution with the real deal. Uh, one
4:52:034 hours, 52 minutes, 3 secondsthing I'm kind of not too satisfied about is like this environment file and how I have to have environment installed
4:52:114 hours, 52 minutes, 11 secondsin server and I have to kind of traverse in database and um also because I'm not
4:52:184 hours, 52 minutes, 18 secondssure if generated should be oh yeah see I have a git ignore inside of this package. I'm not really sure like what's
4:52:274 hours, 52 minutes, 27 secondsthe norm. Should I have like one git ignore and then let me just check.
4:52:354 hours, 52 minutes, 35 secondsShould I like uh copy the contents of this git ignore and then paste it like here?
4:52:444 hours, 52 minutes, 44 secondsLet me check. Prisma like should I do that?
4:52:514 hours, 52 minutes, 51 secondsI'm really not sure. And then if I delete this get ignore.
4:52:594 hours, 52 minutes, 59 secondsUh yeah, it doesn't work.
4:53:024 hours, 53 minutes, 2 secondsSo let me let me check. How do you properly do this? Well, I'm just going to revert it. I'm going to keep the g
4:53:114 hours, 53 minutes, 11 secondsignore in the database right here. And I'm going to leave it to be as is. I'm not going to keep this. Okay. So yes,
4:53:194 hours, 53 minutes, 19 secondsjust let the database have its own git ignore. Again, if you want it, you can maintain the environment file within the database. I might research a bit and if
4:53:284 hours, 53 minutes, 28 secondsI see that the norm is that usually each of these has its own environment file, then I'm going to stop doing the hard
4:53:354 hours, 53 minutes, 35 secondsjob of uh making all of these packages use environment to point to this environment file, which you can already do yourself. You can add dot environment
4:53:444 hours, 53 minutes, 44 secondsfile into the server and dot environment file into the database and make all of them point to the same database URL and
4:53:514 hours, 53 minutes, 51 secondsI think that it should work just as well. Great.
4:53:574 hours, 53 minutes, 57 secondsOkay. And I found uh how you can control where generated is created. If you go
4:54:044 hours, 54 minutes, 4 secondsinside of your Prisma schema at the top here, you can see the output.
4:54:104 hours, 54 minutes, 10 secondsSo if you want it to be inside of your source, you can change it to this.
4:54:144 hours, 54 minutes, 14 secondsAgain, I'm not sure which one is better, but this one seems to be what git ignore was looking at. So I'm just going to keep it in generated. And it makes sense
4:54:224 hours, 54 minutes, 22 secondsbecause everything Prisma related is outside of my source folder. So I'm just going to keep my source folder for the things I'm exporting. Uh great. I
4:54:304 hours, 54 minutes, 30 secondsbelieve we are finished with this chapter entirely now. So let me go ahead and commit it. So, chapter 4, server, shared package, and database.
4:54:414 hours, 54 minutes, 41 secondsOh, the one thing I want to do is just search for my HTTP exception
4:54:474 hours, 54 minutes, 47 secondsand go here. Actually, I want to go inside of sessions. DS. So, go inside of your server source routes sessions.ds.
4:54:564 hours, 54 minutes, 56 secondsAnd let's just comment this out because we're not using HTTP exception anywhere.
4:55:024 hours, 55 minutes, 2 secondsSo, let's shut this down. Let's go ahead and get checkout 04
4:55:104 hours, 55 minutes, 10 secondsand this will be server shared database.
4:55:174 hours, 55 minutes, 17 secondsGit add commit 04 server shared
4:55:254 hours, 55 minutes, 25 secondsand database packages and get push origin 04 server shared
4:55:344 hours, 55 minutes, 34 secondsdatabase. Now that that is pushed we can go ahead and create a pull request and then we can go ahead and review our changes.
4:55:454 hours, 55 minutes, 45 secondsLet's go through the review by code rabbit. So in here we have the release notes, some new features, some chores
4:55:524 hours, 55 minutes, 52 secondsthat we added, but more importantly we have a lot of comments to look at. So the first one is that the title slicing
4:56:004 hours, 56 minutescan be a bit problematic. Um I'm going to rule this as okay simply because this is a tutorial. So in production
4:56:084 hours, 56 minutes, 8 secondsinstances, I would actually recommend using AI to generate a nice uh text message depending on this message slice.
4:56:174 hours, 56 minutes, 17 secondsUh in here you can pause the screen to read the in-depth uh problem here. As you can see many characters uh and other
4:56:264 hours, 56 minutes, 26 secondsthings can apparently make posgress reject this because of invalid uh byte sequence for encoding in UTF8. So we
4:56:354 hours, 56 minutes, 35 secondsshould probably tighten this as you can see how they do it here. But I think for our use case this is just perfectly fine
4:56:434 hours, 56 minutes, 43 secondsas is. But definitely a good suggestion by code rabbit uh if it comes to production. In here it's warning us that
4:56:504 hours, 56 minutes, 50 secondsour session location schema is too loose and that it will crash on malformed state. So its proposed tider validation
4:56:584 hours, 56 minutes, 58 secondsis to also confirm that we have messages and that array of messages exists. But
4:57:064 hours, 57 minutes, 6 secondsas it says currently the only producer is new session which means that we own uh what we send in location.state. So we
4:57:144 hours, 57 minutes, 14 secondsare pretty safe but it's warning us about history entries, hot reloads or future call sites that can easily trip
4:57:224 hours, 57 minutes, 22 secondsthis. So with the current state, it's actually perfectly fine this way. But yeah, uh very good idea to tighten it if
4:57:294 hours, 57 minutes, 29 secondsyou end up having uh multiple call sites that redirect with session location schema. Even though uh the only reason
4:57:374 hours, 57 minutes, 37 secondswe even have location schema is because of the pre-fetching that we are doing. So the user doesn't have to wait twice.
4:57:434 hours, 57 minutes, 43 secondsSo very good comment, but since we own the only call location, I'm going to leave it as is.
4:57:494 hours, 57 minutes, 49 secondsUh in here this is very interesting and even marked as critical here uh toast is not stable across renders. We can add
4:57:574 hours, 57 minutes, 57 secondsuse memo to the context value in toast provider. So the toast dependency in the effect is problematic. Although the show function is memorized via use callback,
4:58:054 hours, 58 minutes, 5 secondsthe context value object itself is created fresh on every render of toast provider. This means that each call to use toast returns a different object
4:58:144 hours, 58 minutes, 14 secondsreference. When toast provider rerenders from any parent update, the session effect sees a new toast object, reruns,
4:58:224 hours, 58 minutes, 22 secondsaborts the inflight fetch via ignore true and triggers a new network request cascading requests while the compound is
4:58:304 hours, 58 minutes, 30 secondsmounted. So that is pretty serious and something I haven't noticed because I don't have a network inspect tab in my TUI. So let's go ahead and fix this.
4:58:384 hours, 58 minutes, 38 secondsLet's go inside of toast provider and let's memorize our value here because it's problematic that we're adding it to the dependency array which then sub does
4:58:474 hours, 58 minutes, 47 secondssubsequent network requests. So inside of my CLI package I'm going to go inside of providers toast and I'm going to go inside of index right here.
4:58:584 hours, 58 minutes, 58 secondsLet me go ahead and find the value. Here it is. Here is the value and I'm going to replace it by memorizing it.
4:59:094 hours, 59 minutes, 9 secondsLet me go ahead and import use memo from React. No errors. Looks like everything is still good. Just make sure you import
4:59:174 hours, 59 minutes, 17 secondsuse memo. Let me confirm that that's the one it is. And let me try
4:59:234 hours, 59 minutes, 23 secondsbond rundev cli works. Let me go ahead and do hello world.
4:59:324 hours, 59 minutes, 32 secondsThis seems to work just as fine. Perfect.
4:59:364 hours, 59 minutes, 36 secondsSo, that works. I'm going to Well, I'm not going to do anything yet just in case there are more of these. Uh, okay.
4:59:434 hours, 59 minutes, 43 secondsIn here, it's telling me to add more environment uh varants, but we don't need that because of our root get
4:59:504 hours, 59 minutes, 50 secondsignore. At least I think uh in here it does a a good uh comment as well. So,
4:59:584 hours, 59 minutes, 58 secondsuse deterministic environment loading instead of uh path dependent import.vironment environment config.
5:00:065 hours, 6 secondsSo on line one import.environment config resolves environment from the process working directory in this monor repo
5:00:145 hours, 14 secondsvarying uh path from different script invocation points. So bun run from packages server or packager CLI causes
5:00:225 hours, 22 secondsthis to fail to load the root environment triggering line 8 throw even when root environment actually exists.
5:00:305 hours, 30 secondsOkay, that sounds like something we should fix. So let's go ahead and do it.
5:00:355 hours, 35 secondsSo we are talking about database source client.ds. Let me go ahead and check that out. So
5:00:455 hours, 45 secondsdatabase source client DS. So I'm going to change this to be environment from environment.
5:00:575 hours, 57 secondsThen I'm going to go ahead and import path from path. And then I'm going to go ahead
5:01:055 hours, 1 minute, 5 secondsand do this and just remove the diff change here. Okay, I think this should work. Not sure how we can test this.
5:01:195 hours, 1 minute, 19 secondsAnd h why is it going so outside of here? Probably because it has to go outside of here to the source. That's one. Outside of here, that's two.
5:01:295 hours, 1 minute, 29 secondsOutside of here, that's three. and then environment. So, one, two, three. Okay, I think I get it. So, let me just I
5:01:375 hours, 1 minute, 37 secondsdon't know try bondev server.
5:01:425 hours, 1 minute, 42 secondsOh, here it is. Injected environment from environment multiple files. Okay.
5:01:485 hours, 1 minute, 48 secondsAnd then let me go ahead and do bun rundev cli here. Hello world. Testing if this works.
5:01:565 hours, 1 minute, 56 secondsLet's see. Looks like it works. Let me try and purposely break it. So if I pick environment two here and then run this again.
5:02:085 hours, 2 minutes, 8 secondsOkay, it says it loaded it. So if I try bondev cli
5:02:155 hours, 2 minutes, 15 secondshello world, it still works. Huh.
5:02:225 hours, 2 minutes, 22 secondsOkay. I don't think I fully understand this, but uh I feel like this is just more explicit than what we had. So, I'm
5:02:295 hours, 2 minutes, 29 secondsjust going to use it. It seems to not break our app. Seems to work just fine.
5:02:345 hours, 2 minutes, 34 secondsIf you're having problems, feel free to have multiple environment files, like one in your database, one in your CLI, one in your server, wherever it needs to
5:02:435 hours, 2 minutes, 43 secondsbe to make it work, and just have the database URL. Okay, [snorts] sure. Uh, I'm going to go ahead and do Okay. Again, I'm not sure if that's all we need. Uh, but this looks fine.
5:02:565 hours, 2 minutes, 56 secondsuh in here. Yeah, it's warning us that we should probably have some automatic setup hook to ensure
5:03:025 hours, 3 minutes, 2 secondsfresh environments can build and type check simply because this is get ignored. So it entirely depends on the
5:03:115 hours, 3 minutes, 11 secondsuser's machine if they run uh BNX Prisma generate. So if they don't run this, they're going to have stale data. I
5:03:215 hours, 3 minutes, 21 secondsthink this is more of a problem if you're working within a theme or something. So different people are going to have different problems but uh
5:03:285 hours, 3 minutes, 28 secondsourselves we are going to be aware that we have to run bonex prisma generate every time we update our schema and then this will subsequently update as well.
5:03:395 hours, 3 minutes, 39 secondsSo good comment definitely but for us it's okay in here it's telling us to remove database from root to from root export
5:03:485 hours, 3 minutes, 48 secondsto prevent unnecessary client DS evaluation. Reexporting database from the package root forces evaluation of client which throws on missing database
5:03:565 hours, 3 minutes, 56 secondsURL whenever anything is important from night code database even when only Prisma types or any are needed. This makes the root export fragile. Oh, that's interesting.
5:04:075 hours, 4 minutes, 7 secondsYeah, I like this.
5:04:115 hours, 4 minutes, 11 secondsI like this. Let's do it. So, remove database from root export. I'm going to go ahead and do that.
5:04:205 hours, 4 minutes, 20 secondsuh database source index. I'm going to remove that from the root export and I'm going to go inside of my package JSON
5:04:285 hours, 4 minutes, 28 secondsand I'm going to add client export specifically like this. And that changes
5:04:355 hours, 4 minutes, 35 secondsthings in my server file I believe. Let me check if that's true. So in my server source routes sessions I now have an
5:04:435 hours, 4 minutes, 43 secondserror here and I have to import database forward slashclient like this. I think that's the only instance I have. Let me go ahead and
5:04:525 hours, 4 minutes, 52 secondssearch for the database not in bunlock not in package json. Yes, that's the only instance just for good.
5:05:025 hours, 5 minutes, 2 secondsUh I'm going to check can I run the server? I can. Can I do vulner CLI? I can. Can I do hello world?
5:05:135 hours, 5 minutes, 13 secondsLooks like I can. Perfect.
5:05:175 hours, 5 minutes, 17 secondsSo, we resolved that. And here at the end, uh it's just telling us that we are missing user scoping. That's because we don't have out yet. So, we are mocking
5:05:265 hours, 5 minutes, 26 secondsusers or we are not even uh like filtering for user. We allow everyone to load everything. So, we can resolve that
5:05:335 hours, 5 minutes, 33 secondsourselves. Uh very good changes. So let's go ahead and get commit.
5:05:415 hours, 5 minutes, 41 secondsSo same message and I'm just going to append like fix at the end and I can then just do uh get push
5:05:495 hours, 5 minutes, 49 secondshas no upstream branch. That's interesting.
5:05:555 hours, 5 minutes, 55 secondsUm h let me try doing git push set upstream origin04
5:06:035 hours, 6 minutes, 3 secondsserver share database. See if that's going to fix it. Look like that fixes it. Let me see what command we actually
5:06:095 hours, 6 minutes, 9 secondsrun. So we run get push origin. I think I should have a flag git push-u
5:06:185 hours, 6 minutes, 18 secondsorigin and then that would set the upstream. Yes, that sounds I think that flag sounds like that should be it. So if you want to add
5:06:265 hours, 6 minutes, 26 secondssubsequent commits, you have to add set upstream origin here.
5:06:325 hours, 6 minutes, 32 secondsAnd that should re-trigger this And uh let me just confirm.
5:06:405 hours, 6 minutes, 40 secondsSo I have two commits. That looks good.
5:06:425 hours, 6 minutes, 42 secondsSo the first one is the initial one and the second one is the fix. And with that we have resolved. Uh let me see. I can
5:06:525 hours, 6 minutes, 52 secondsnow close this one because I don't need that. Uh this one already says outdated. Perfect.
5:07:015 hours, 7 minutes, 1 secondand everything else seems to be resolved. So, I'm just going to wait to see if this one gets resolved itself because we explicitly fixed that.
5:07:135 hours, 7 minutes, 13 secondsI'm just going to wait a second.
5:07:165 hours, 7 minutes, 16 secondsSo, since uh it wasn't resolving itself, I simply asked is this resolved in the latest commit and you can see that it confirmed that the latest commit fully
5:07:245 hours, 7 minutes, 24 secondsresolves this and file now uses deterministic approach. Perfect. And that automatically uh marked it
5:07:325 hours, 7 minutes, 32 secondsconfirmed as addressed by perfect. So all issues resolved. We are good to
5:07:385 hours, 7 minutes, 38 secondsmerge. Amazing job. Uh let's not delete the branch. So we have our history right
5:07:465 hours, 7 minutes, 46 secondshere. What we have to do is we have to go back here. Get checkout to the main branch and get pull origin main. So we are up to date with all of our changes.
5:07:585 hours, 7 minutes, 58 secondsBrilliant. Now, let's go ahead uh and end this chapter. Amazing, amazing job.
5:08:045 hours, 8 minutes, 4 secondsAnd see you in the next one. Now that we have a Hono server and the database, it's time to talk about monitoring.
Chapter 7: Sentry Monitoring
5:08:125 hours, 8 minutes, 12 secondsRight now, if something breaks on our server, we have no way of knowing that.
5:08:175 hours, 8 minutes, 17 secondsHere's an example. We have a user who uses our Hono server. Something happens like an internal server error. And we have no idea in which route it happened.
5:08:285 hours, 8 minutes, 28 secondsWe have no stack trace to reproduce it.
5:08:315 hours, 8 minutes, 31 secondsWe have no request context. And we have no idea how often it happens. We don't know if this was a oneoff event, if it
5:08:405 hours, 8 minutes, 40 secondsonly happened to one user or if it happened to a thousand users. This is problematic because we don't know what
5:08:485 hours, 8 minutes, 48 secondsto fix unless we experience this ourselves. And that isn't how you handle errors in production. Instead, what you
5:08:565 hours, 8 minutes, 56 secondsdo is you add some kind of monitoring like Sentry. With Sentry, you are one step ahead of every single error that
5:09:045 hours, 9 minutes, 4 secondshappens within your application because you don't have to wait for your users to report the errors or wait until you experience them yourselves. Sentry is
5:09:135 hours, 9 minutes, 13 secondsgoing to create a new issue for every single error that happens in your application. It's also going to create a
5:09:205 hours, 9 minutes, 20 secondsfull stack trace, allowing you to see which method, which route, how long did it take, and which status did it return.
5:09:285 hours, 9 minutes, 28 secondsUsing sentry logging, you can filter by method, path, status, duration, and many, many more things. You can also
5:09:365 hours, 9 minutes, 36 secondskeep track of frequency, how many times did an error happen, and how many users were affected. In short, you will know exactly what broke where and how often.
5:09:485 hours, 9 minutes, 48 secondsThis is an absolute must if you plan on having a production grade application.
5:09:535 hours, 9 minutes, 53 secondsThe way it works is extremely simple. So usually we have a request which goes into the route handler. An error happens
5:10:025 hours, 10 minutes, 2 secondsand we don't know about it. But by introducing sentry middleware for a hono, we put it in the first place
5:10:095 hours, 10 minutes, 9 secondsbefore anything else happens. So before any route handler execution is done, we add the sentry middleware. So if any
5:10:175 hours, 10 minutes, 17 secondsuncaught error happens, it is automatically going to throw it back inside of the sentry middleware. Meaning
5:10:255 hours, 10 minutes, 25 secondsthat we don't have to manually add try and catch methods everywhere. If something is truly uncaughth, it's now
5:10:325 hours, 10 minutes, 32 secondsbeing caught and immediately reported in the dashboard with a new issue created so that we know we have to fix it.
5:10:395 hours, 10 minutes, 39 secondsBesides that, Sentry also gives us an option to manually log things. For example, if we just want to log what
5:10:485 hours, 10 minutes, 48 secondshappened like a successful request, we can use their logger.info API. This is used for normal operations and they can be used for every request.
5:10:595 hours, 10 minutes, 59 secondsThis is useful because once you have successful states, it will be easier for you to notice an anomaly. So something
5:11:065 hours, 11 minutes, 6 secondsthat was usually successful is now failing or something that you expect could happen. So you have this instead
5:11:145 hours, 11 minutes, 14 secondsof try and catch for example in here you could use logger.warn warn API. And lastly, we have the example we spoke
5:11:225 hours, 11 minutes, 22 secondsabove. This is logger. This is if something breaks and you don't know about it. Basically, unhandled errors.
5:11:315 hours, 11 minutes, 31 secondsSo, we have option to manually log all kinds of things in our server. But you don't really have to worry about that
5:11:395 hours, 11 minutes, 39 secondsbecause the most important one, the unhandled error is captured immediately automatically with Sentry. Let's see how
5:11:475 hours, 11 minutes, 47 secondswe can add it to our Hono server using the link on the screen or simply entering the code code with Antonio.
5:11:545 hours, 11 minutes, 54 secondsWhen you sign up, you can get Century Team for free for 3 months as well as
5:12:025 hours, 12 minutes, 2 seconds150,000 errors included. So, go ahead and create a new account. Once you create a new organization, go ahead and
5:12:105 hours, 12 minutes, 10 secondscreate a new project. In here, choose Server as the platform. and you can see all of the amazing options it has. Down
5:12:185 hours, 12 minutes, 18 secondshere you can find Hono. So go ahead and select Hono. In here you can choose your alert frequency. That's right. Sentry is
5:12:275 hours, 12 minutes, 27 secondsgoing to alert you whenever some kind of internal or uncaught error happens. So this can be extremely useful if you want
5:12:345 hours, 12 minutes, 34 secondsto be on high alert and immediately start fixing when something breaks for your users. You can also turn it off if you don't like it.
5:12:445 hours, 12 minutes, 44 secondsAnd you can name your project whatever you want. So I'm going to go ahead and call this night code and I'm going to
5:12:515 hours, 12 minutes, 51 secondsput it in this default team. And then I'm going to go ahead and create the project. Now let's go ahead and configure the Hono SDK. You can see that error monitoring is already selected.
5:13:025 hours, 13 minutes, 2 secondsBut besides that you can add logs, application metrics, and tracing.
5:13:065 hours, 13 minutes, 6 secondsProfiling is currently only available for the Node.js runtime. Since we are using bun, I'm going to deselect that one. In here, I'm going to select bun.
5:13:175 hours, 13 minutes, 17 secondsAnd that gives me the exact installation and configuration steps that I need.
5:13:215 hours, 13 minutes, 21 secondsLet's go ahead and install these two packages inside of our server. So, I'm going to go inside of my packages and
5:13:285 hours, 13 minutes, 28 secondsthen I'm going to go inside of server and in here I'm going to do bun add. And I'm specifically going to add sentry hono and sentry bun. Once you've added
5:13:385 hours, 13 minutes, 38 secondsthem, let's go ahead and confirm that they have been added in the package JSON of my server package. Sentry bun and
5:13:455 hours, 13 minutes, 45 secondssentry hono. Now, let's go ahead and actually register the sentry middleware inside of our server. So, go inside of index.ts
5:13:535 hours, 13 minutes, 53 secondsand let's go ahead and import Sentry from Sentry Hono bun. Then, right after we initialize our app, let's go ahead and register the Sentry middleware.
5:14:055 hours, 14 minutes, 5 secondsThis configuration right here can be different depending on your selection of options up here. You can see that I, for
5:14:135 hours, 14 minutes, 13 secondsexample, have logs enabled because I've selected them right here.
5:14:185 hours, 14 minutes, 18 secondsAnd now let's go ahead and also modify our code to import this right below.
5:14:265 hours, 14 minutes, 26 secondsAnd then let's add this explicit test to debug Sentry.
5:14:315 hours, 14 minutes, 31 secondsSo, right after our middleware, I'm going to register an endpoint debugged sentry, which will use sentry logger
5:14:395 hours, 14 minutes, 39 secondsinfo, and we're going to use sentry metrics count. And then we're just going to go ahead and throw one random uncaugh error.
5:14:495 hours, 14 minutes, 49 secondsAll right, now that we have this, let's go ahead and actually run our app.
5:14:565 hours, 14 minutes, 56 secondsSo I'm going to do bun install here and then I'm going to go ahead and simply start my server. Now let's go ahead and
5:15:045 hours, 15 minutes, 4 secondsvisit localhost 3000 debug centry. So it's this exact API route and you should
5:15:125 hours, 15 minutes, 12 secondsget back error internal server error. So why are we getting our error structured
5:15:185 hours, 15 minutes, 18 secondslike this? Well, it is because we already have one middleware here on error which basically standardizes the
5:15:275 hours, 15 minutes, 27 secondsresponse output from that. But this doesn't actually capture our errors. It just standardizes the output. So they all return the exact same API structure.
5:15:405 hours, 15 minutes, 40 secondsSo make sure you hit this endpoint and get back an error. And now you should be ready to click take me to issues. And
5:15:495 hours, 15 minutes, 49 secondshere it is 47 seconds ago. You can see that now for every single error that happens within your API, you will be
5:15:585 hours, 15 minutes, 58 secondsaware. Not only will you be aware, you can see the exact URL where it happened.
5:16:055 hours, 16 minutes, 5 secondsYou can see the level of this issue. Is it an error? Is it an info? Or is it a warning? You can see the exact backend.
5:16:135 hours, 16 minutes, 13 secondsYou can see the exact machine where the server is hosted. You can see the highlights. You can see stack trace. You
5:16:205 hours, 16 minutes, 20 secondscan automatically create issues for that. And this is extremely useful. Right? So this is stack trace. Right?
5:16:275 hours, 16 minutes, 27 secondsNow it's extremely obvious because we purposely throw this error. But imagine how useful it would be to see this when you didn't expect an error to happen. So
5:16:365 hours, 16 minutes, 36 secondsthese kinds of stack traces are extremely extremely useful. So you can exactly understand where this was called
5:16:445 hours, 16 minutes, 44 secondsfrom and how did this error happen and then you can immediately go and fix it.
5:16:505 hours, 16 minutes, 50 secondsIn here you even have the breadcrumbs so you can see exactly how it started. The first thing we did is we visited the development server and then we hit the
5:16:585 hours, 16 minutes, 58 secondsfaulty endpoint. Now again all of this is very simple now but imagine as it grows more and more when we have all of
5:17:065 hours, 17 minutes, 6 secondsthese huge endpoints and our users start getting all kinds of errors how will we know what to fix well unless we experience those errors ourselves we
5:17:155 hours, 17 minutes, 15 secondswouldn't know but with Sentry we can keep track of absolutely everything that is happening every error on every single
5:17:255 hours, 17 minutes, 25 secondsuser for every single event and the best part of this all all we had to do was register the middleware. We didn't have
5:17:335 hours, 17 minutes, 33 secondsto do any special try catch here. So literally anything that gets thrown, whether that's from the database or if
5:17:415 hours, 17 minutes, 41 secondswe just had some kind of faulty query, whatever happens, we no longer have to worry about it being hidden from us, but
5:17:485 hours, 17 minutes, 48 secondsinstead it will be captured and immediately reported. From here, we can resolve it. We can assign someone from
5:17:565 hours, 17 minutes, 56 secondsour team. We can set the priority of this. We can even connect it to GitHub and automatically open a pull request.
5:18:045 hours, 18 minutes, 4 secondsSo many options you can do from here.
5:18:065 hours, 18 minutes, 6 secondsLet's see how else we can use Sentry specifically Sentry logs to improve our application. So I want to focus on this
5:18:155 hours, 18 minutes, 15 secondshandler that we have here on error. In here we obviously have some kind of HTTP exception meaning that this is actually
5:18:255 hours, 18 minutes, 25 secondsa handled error. So what should we do here? Well, let's visit the whiteboard.
5:18:315 hours, 18 minutes, 31 secondsThis would be an expected problem, right? So, this is something we would expect. So, the right thing to use here is logger.warn.
5:18:415 hours, 18 minutes, 41 secondsSo, let's go ahead and add that here.
5:18:435 hours, 18 minutes, 43 secondsHandled HTTP error. And in here, we can pass along the error status. We can pass along the error message with the
5:18:505 hours, 18 minutes, 50 secondsfallback, the C request path, the method, everything here under warn. So we don't have to console log. Every time
5:18:585 hours, 18 minutes, 58 secondswe want to console log, we can now do sentry log instead and then just throw this to the user. We actually don't have
5:19:075 hours, 19 minutes, 7 secondsto do anything here because it's going to be captured anyway. But if you want it to be explicit, you could remove this
5:19:155 hours, 19 minutes, 15 secondsconsole log entirely now and you could add sentry logger error with all of these issues here. But let's go ahead and visit our sessions.ts.
5:19:285 hours, 19 minutes, 28 secondsSo we can see some more useful ways of using Sentry. So I'm going to copy this Sentry import and I'm going to go inside of my routes sessions.ts.
5:19:395 hours, 19 minutes, 39 secondsThere are many useful places where we can use Sentry logging. Here for example in here we have the create sessions
5:19:475 hours, 19 minutes, 47 secondsschema and down here we have the create sessions validator. So [snorts] whenever this isn't successful, this is an
5:19:545 hours, 19 minutes, 54 secondsexpected error. So what we could do here is throw session creation validation fail. Now you might be wondering, but
5:20:025 hours, 20 minutes, 2 secondswhy would we even log this? Well, if it happens too often, you probably have some kind of UI that allows submitting
5:20:115 hours, 20 minutes, 11 secondsinvalid API body. That's why it's important for you to log these things because otherwise your users would just
5:20:195 hours, 20 minutes, 19 secondsbe getting 400 errors back and they I mean it could be that they are doing something wrong. But you also want to be
5:20:275 hours, 20 minutes, 27 secondsaware of that. Perhaps you have some kind of bad user experience implemented and by seeing an increase in these logs
5:20:345 hours, 20 minutes, 34 secondshappening in the create session validator you can go ahead and improve your application. So you don't have to think about this only for uncaught
5:20:435 hours, 20 minutes, 43 secondserrors. You can also think about this for improving user experience. Let's take a look at this. This is a
5:20:505 hours, 20 minutes, 50 secondssuccessful request, right? Nothing wrong is really happening here. Well, what we can do is we can add sentry logger and
5:20:595 hours, 20 minutes, 59 secondswe can go ahead and display how many sessions we have successfully loaded.
5:21:055 hours, 21 minutes, 5 secondsAgain, not too useful at first, but useful for you if you start noticing an anomaly here, right? If you start
5:21:135 hours, 21 minutes, 13 secondsnoticing that all of your uh listed sessions count becomes zero all of a sudden, you probably have some kind of
5:21:225 hours, 21 minutes, 22 secondsdatabase bug. Perhaps the database is down or something is corrupted, right?
5:21:265 hours, 21 minutes, 26 secondsThere are many many ways where logs can help you. Let's take a look at this ID once again. So if there is no session, this would be a warn error, right?
5:21:385 hours, 21 minutes, 38 secondsBecause it is technically expected. We are throwing this error back. But it's also useful for us to keep track of this. So this is session not found. And
5:21:475 hours, 21 minutes, 47 secondsI don't think we have to track anything other than session ID. Later when we have a user ID, we can add that as well, right?
5:21:575 hours, 21 minutes, 57 secondsExcept mock user, you will replace it with the actual user ID. So you can then track and filter by that user perhaps
5:22:045 hours, 22 minutes, 4 secondsonly that user has some kind of problem and then you can notice is that user in some organization is that user premium
5:22:125 hours, 22 minutes, 12 secondsis that user on a free tier as much context as possible for you to deduct why some errors are happening for your
5:22:205 hours, 22 minutes, 20 secondsusers because sure this is a very simple error session wasn't found but how is this user able to access an invalid ID
5:22:285 hours, 22 minutes, 28 secondsin the first place that is your job to figure out and that is where Sentry can help you. So once again, Sentry isn't just for errors. Sentry is also for
5:22:385 hours, 22 minutes, 38 secondsimproving user experience through various logs whether they are successful or if they are not successful. So
5:22:465 hours, 22 minutes, 46 secondsoutside of this error, we can go ahead and log a successful session, right? And you can also load the message count if
5:22:535 hours, 22 minutes, 53 secondsyou want or you can just mark this session ID as successfully loaded. There are many many ways you can do this
5:23:025 hours, 23 minutes, 2 secondsright. You can also down here mark successful s sessions right every time you successfully create a session go
5:23:115 hours, 23 minutes, 11 secondsahead and log them like this session ID title right you don't have to log the
5:23:185 hours, 23 minutes, 18 secondspath so just session ID and title all of this is very very useful information and just by adding these few changes you
5:23:265 hours, 23 minutes, 26 secondswill start to see uh useful things here so if I go inside of my logs here Now,
5:23:325 hours, 23 minutes, 32 secondslet's wait a second and uh then we're going to start seeing all of this information which we just logged. So,
5:23:395 hours, 23 minutes, 39 secondsgive it a few moments to load. What I'm trying right now is localhost 3000 and then sessions and then uh 1 2 3.
5:23:485 hours, 23 minutes, 48 secondsBasically, this is the URL I just visited, right? Something I know is going to fail, a random session ID. And
5:23:565 hours, 23 minutes, 56 secondsyou can see on the return side, everything looks perfectly fine. But you can see that something is happening in
5:24:035 hours, 24 minutes, 3 secondsthe logs here. So in my logs I can see a normal listed sessions log but I can
5:24:105 hours, 24 minutes, 10 secondsalso see that user triggered the test error. So okay this is the test error.
5:24:155 hours, 24 minutes, 15 secondsThis isn't uh as useful of course but this is your dashboard where you will keep track of all the logs happening uh
5:24:245 hours, 24 minutes, 24 secondson your application. For example, here is session not found. So you can see it's
5:24:305 hours, 24 minutes, 30 secondsnot exactly a a critical mistake, but you can see the exact session ID which
5:24:375 hours, 24 minutes, 37 secondswas attempted to be loaded and which user loaded it. This is already useful information because if you start seeing
5:24:455 hours, 24 minutes, 45 secondsan uptick in these sessions here, you can then deduct oh okay so this user somehow has some stale information in
5:24:535 hours, 24 minutes, 53 secondstheir UI. How is that happening? And then just think about it later when you improve this. You could also log which
5:25:015 hours, 25 minutes, 1 secondversion of the CLI application they are using and then you will have that information displayed here as well. So
5:25:095 hours, 25 minutes, 9 secondsthat is how you handle monitoring and errors for production grade applications and I can guarantee you that cloud code
5:25:165 hours, 25 minutes, 16 secondsopen codecs all have this kind of thing added. So they are actively monitoring anything that happens when they try to
5:25:235 hours, 25 minutes, 23 secondsload a session that was deleted, when they successfully delete a session, when they successfully load sessions, all of
5:25:305 hours, 25 minutes, 30 secondsthat is uh logged and you should be doing that as well. In case you were not
5:25:365 hours, 25 minutes, 36 secondssuccessful in enabling logs or error monitoring for whatever reason, you don't have to worry about not being able to complete the rest of this tutorial.
5:25:465 hours, 25 minutes, 46 secondsSo this is simply a bonus chapter that I wanted to show you which will greatly
5:25:525 hours, 25 minutes, 52 secondsimprove the production grade quality of your application. If you choose to use
5:25:595 hours, 25 minutes, 59 secondsthis, feel free to commit this changes and merge them into main. But if you don't want to use them, feel free to
5:26:065 hours, 26 minutes, 6 secondsdiscard all of the changes and simply go to the next chapter. Amazing job and see you in the next lesson. In this chapter,
Chapter 8: AI Chat Streaming
5:26:145 hours, 26 minutes, 14 secondswe're going to implement AI chat streaming. Basically, a way for our LLM to finally talk back to us in our
5:26:225 hours, 26 minutes, 22 secondsterminal. The way we are going to achieve this is by using the following flow. Our CLI client, our terminal, is
5:26:295 hours, 26 minutes, 29 secondsgoing to make a post request to a new API route we're going to develop called chat. That chat route is going to use
5:26:365 hours, 26 minutes, 36 secondsVersel's AI SDK, which allows us to use any provider we want. So, it's completely provider agnostic. I'm going
5:26:445 hours, 26 minutes, 44 secondsto showcase Anthropic and Open AI, but you can use any of their available providers, and there are a lot of them.
5:26:525 hours, 26 minutes, 52 secondsAnd yes, there are completely free ones like Google or Grock. And we're going to then persist the output to the database
5:27:005 hours, 27 minuteswhile simultaneously using server sent events to stream back to our terminal what is happening. And if you're worried
5:27:095 hours, 27 minutes, 9 secondsabout hearing the word Verscell in Verscell AIS SDK, uh let me go ahead and explain what that is. So AIS SDK is not
5:27:185 hours, 27 minutes, 18 secondsa uh Versel lockin. A lot of times I met I recommend people I recommend to people to use this tool and they are afraid of
5:27:275 hours, 27 minutes, 27 secondssome kind of lock in. Uh that is not what this is. This is an open-source tool by Versel that allows you to
5:27:355 hours, 27 minutes, 35 secondsbasically have provider agnostic model agnostic toolkit and it's perfect for an app like ours where we want to support
5:27:445 hours, 27 minutes, 44 secondsthousands of providers if needed. It's basically the same as Tanstack AI or Pyantic AI. Basically, it's model
5:27:525 hours, 27 minutes, 52 secondsagnostic and it supports virtually every model and provider. It's kind of the same idea with all of these packages.
5:27:585 hours, 27 minutes, 58 secondsand AI SDK is by far the most popular one and that's why we're going to be using it. I'm going to be using version
5:28:055 hours, 28 minutes, 5 secondssix and we're mostly going to focus on their streaming functionality. So what is streaming? Well, this right here. So
5:28:135 hours, 28 minutes, 13 secondsyou don't have to wait for the entire output. Instead, it will immediately start writing something back. So this will help us a lot because they have
5:28:225 hours, 28 minutes, 22 secondsthis stream text function. And then we're going to combine that with Hono's streaming helper so that we can uh well
5:28:305 hours, 28 minutes, 30 secondsadd that streaming event to our Hono server. We are then going to implement
5:28:385 hours, 28 minutes, 38 secondssomething called use chat hook which will be able to parse the results of the stream. Now, usually if you were working
5:28:465 hours, 28 minutes, 46 secondson the web, you wouldn't have to implement this yourself for a very simple reason that Versel's AI SDK actually has use chat for that specific
5:28:565 hours, 28 minutes, 56 secondspurpose. The problem is it uses some API that isn't available within Open TUI. So that's why at least that's to my
5:29:045 hours, 29 minutes, 4 secondsknowledge and my testing. I could be wrong but still it's like an extremely good practice to learn how to build your own use chat which is able to parse
5:29:135 hours, 29 minutes, 13 secondsthese stream events like text delta reasoning delta tool call tool result done and error and then we're going to
5:29:205 hours, 29 minutes, 20 secondswrap it up by implementing stream interruption. Basically in the middle of streaming we will allow the user to press escape and then we are going to
5:29:285 hours, 29 minutes, 28 secondscapture that event on the front end and we're going to persist the interrupted message on the back end. uh basically a very nice user experience by the end of
5:29:375 hours, 29 minutes, 37 secondsthis chapter. Let me show you exactly how that looks like. You will be able to send hello world and you will get back a
5:29:455 hours, 29 minutes, 45 secondsresponse from AI any second now. And if you do something like write me a longer
5:29:525 hours, 29 minutes, 52 secondsmessage and let's wait for its response. You can see that I can interrupt it like that.
5:29:595 hours, 29 minutes, 59 secondsThat is what we are going to achieve. So let's go ahead and do it. I'm going to
5:30:055 hours, 30 minutes, 5 secondsstart by adding some packages to my server package. So let's go inside of
5:30:135 hours, 30 minutes, 13 secondspackages server. And I'm going to do bun add AI SDK forward slashanthropic
5:30:235 hours, 30 minutes, 23 secondsAI-SDKward slop AI and finally the AI package
5:30:305 hours, 30 minutes, 30 secondsitself. So these three packages have just been added. You can even see the exact versions that I am using. Let me
5:30:385 hours, 30 minutes, 38 secondsgo ahead and confirm that they are here in package. JSON. Here they are.
5:30:425 hours, 30 minutes, 42 secondsPerfect. Now that we have that, we have to go ahead and set up a util for our
5:30:485 hours, 30 minutes, 48 secondsmodels. Let's go ahead inside of server here. Inside of source, I'm going to go ahead and create a new folder called
5:30:565 hours, 30 minutes, 56 secondslib. And in here, I'm going to create models.ds. DS.
5:31:015 hours, 31 minutes, 1 secondLet's go ahead and start by adding the imports of our newest two packages. And then let's go ahead and import all of the helpers we developed using uh night
5:31:105 hours, 31 minutes, 10 secondscode shared. Then let's go ahead and import a type language model from our AI package. In here, I'm going to define
5:31:195 hours, 31 minutes, 19 secondsthe anthropic model ID. Let me expand this anthropic model ID which is going to use our supported chat model type and
5:31:295 hours, 31 minutes, 29 secondsit's going to specify the provider being anthropic and then it's going to look for ID and that is going to uh filter it
5:31:365 hours, 31 minutes, 36 secondsto only the model ids that we have defined that we are supporting. So a really cool TypeScript way of making
5:31:445 hours, 31 minutes, 44 secondsthis only these three models. And if we ever want to expand that, we can go inside of our shared package here inside of the models and we can just extend it.
5:31:545 hours, 31 minutes, 54 secondsSo let's go ahead and for example add another set version. Let me duplicate it. Let's call this 47.
5:32:025 hours, 32 minutes, 2 secondsI can save it. And immediately here you can see it's added as a supported version. Let me remove it now. And you can see how it filters by the provider
5:32:115 hours, 32 minutes, 11 secondsanthropic. So it doesn't even mention these ones because that's provider open AI. And the same way we can do open AI
5:32:195 hours, 32 minutes, 19 secondsmodel ID by searching for the provider open AAI and focusing on the ID of the models. Let's go ahead and create a type
5:32:265 hours, 32 minutes, 26 secondsfor the resolved model which is going to use the types we imported above.
5:32:315 hours, 32 minutes, 31 secondsAnd now let's go ahead and create a little function assert unsupported provider. Inside of
5:32:385 hours, 32 minutes, 38 secondshere we are simply uh going to create a little helper that throws the error for this. And you're going to see why we need it simply because it's going to be
5:32:465 hours, 32 minutes, 46 secondsso common to do and we want to do it inside of a closure like this. Now let's go ahead and create a function to
5:32:545 hours, 32 minutes, 54 secondsresolve an anthropic model. So resolve anthropic model accepts model ID and it returns a type of resolved model and
5:33:025 hours, 33 minutes, 2 secondsit's simply going to return an object which is a model which calls anthropic from up here and passes along the model
5:33:105 hours, 33 minutes, 10 secondsID. And you can see how there are no errors here because anthropic messages model ID is supported or should I say
5:33:195 hours, 33 minutes, 19 secondsmatches what we have defined here. Now that I think of it, perhaps we could find a way to like use anthropic
5:33:265 hours, 33 minutes, 26 secondsmessages messages model ID type from AI SDK and maybe somehow combine it with
5:33:335 hours, 33 minutes, 33 secondsour shared package so that we don't exactly uh blindly write these IDs,
5:33:405 hours, 33 minutes, 40 secondsright? For example, we could always do a cast check, but I'm going to keep that for later. But I'm pretty certain that if you add something wildly incorrect.
5:33:525 hours, 33 minutes, 52 secondsLet me see. H it doesn't show an error here even though this is obviously incorrect. Perhaps it's not able to type
5:34:005 hours, 34 minutescheck like that. Let's just continue with our development then. So this is to resolve the enthropic model. Now I'm
5:34:075 hours, 34 minutes, 7 secondsgoing to create one to resolve open AI model. Uh the reason these are identical and I didn't unify it in one function is
5:34:155 hours, 34 minutes, 15 secondssimply because later when you add more and more providers and models uh they can start to verify with their config files and this is kind of more explicit.
5:34:255 hours, 34 minutes, 25 secondsSo that's why I'm separating it even though it's almost identical code. Now let's go ahead and create a function that will help us resolve the supported chat model.
5:34:375 hours, 34 minutes, 37 secondsSo I'm going to go ahead and first grab the provider from the model prop and then depending on the provider I'm going
5:34:445 hours, 34 minutes, 44 secondsto use a switch case to choose if it's entropic we're going to use the function we developed above for entropic for open
5:34:515 hours, 34 minutes, 51 secondsAI this and default is simply going to be assert unsupported provider throw an error like that
5:34:595 hours, 34 minutes, 59 secondslet's go ahead and add another helper function here is supported chat model using the model ID we're going to check if model ID is in supported chat model
5:35:085 hours, 35 minutes, 8 secondsID and we're then we're going to return find supported chat model and verify that the function doesn't return null.
5:35:165 hours, 35 minutes, 16 secondsPerfect.
5:35:195 hours, 35 minutes, 19 secondsAnd by the end let's add resolve chat model function. Resolve chat model also accepts a model ID and returns a
5:35:275 hours, 35 minutes, 27 secondsresolved model. It uses the same function as above to find the model. If there isn't one, we throw an error.
5:35:345 hours, 35 minutes, 34 secondsOtherwise, let's resolve supported chat model.
5:35:385 hours, 35 minutes, 38 secondsPerfect. So, that is the helper that we need. Now, let's go ahead and develop
5:35:445 hours, 35 minutes, 44 secondsthe chat route. We now have all the helpers here. So, how about we go inside
5:35:525 hours, 35 minutes, 52 secondsof server? Let's go inside of routes and not new folder. Let's go ahead and create chat.ts.
5:36:005 hours, 36 minutesAnd in here, let's go ahead and add some imports. So, we're going to start with everything we need from Hono. Then,
5:36:075 hours, 36 minutes, 7 secondslet's go ahead and add ZOD. Then, let's go ahead and add our new package AI and use it for streaming. Let's import the
5:36:165 hours, 36 minutes, 16 secondsdatabase. Remember, we now have to use forward/client here. That was the change that we did because of our code rabbit
5:36:235 hours, 36 minutes, 23 secondsuh requests. And now, let's import the enums separately. And let's import type chat chat stream event from night code
5:36:325 hours, 36 minutes, 32 secondsshared and from our new package I mean new lib models some functions like is supported chat model and resolve chat
5:36:405 hours, 36 minutes, 40 secondsmodel. In here I'm going to define a submit schema that is going to help us verify uh whether the user can actually
5:36:485 hours, 36 minutes, 48 secondssubmit this into the chat. So it requests the content to be string, the mode to be one of the two modes that we
5:36:555 hours, 36 minutes, 55 secondshave which is plan or build and finally the model to be a supported chat model.
5:37:025 hours, 37 minutes, 2 secondsSo the user cannot fool our API and using the submit schema we can build the submit validator using the Z validator
5:37:105 hours, 37 minutes, 10 secondsspecifically validating the JSON field of the post API request using the submit schema above. And if it's incorrect, we
5:37:185 hours, 37 minutes, 18 secondsare going to standardize the error like this.
5:37:215 hours, 37 minutes, 21 secondsNow that we have that, let's go ahead and create a little util that is going to help us build the conversation history. The conversation history is
5:37:305 hours, 37 minutes, 30 secondsimportant so that for example where I showed you this, if I go ahead and do
5:37:365 hours, 37 minutes, 36 secondswhat were my last two messages, it will understand what my last two
5:37:435 hours, 37 minutes, 43 secondsmessages were because of that uh database context. There we go. See, hello world, write me a longer message.
5:37:515 hours, 37 minutes, 51 secondsSo that's why we need a function to help us build conversation history. But we want only specific messages to be passed
5:38:005 hours, 38 minuteshere. So let's go ahead and add a prop inside of build conversation history. So inside of here, we're going to add messages.
5:38:105 hours, 38 minutes, 10 secondsAnd we're going to define the type as this. So messages is basically going to be an array of an object which has a
5:38:185 hours, 38 minutes, 18 secondsrole which can be user assistant and error and content and status which is message status.
5:38:255 hours, 38 minutes, 25 secondsNow, in here, let's go ahead and run a flat map over our messages.
5:38:345 hours, 38 minutes, 34 secondsWhoops. Okay. Instead of the flat map, let's go ahead and do the following. If the role is error, return an empty
5:38:425 hours, 38 minutes, 42 secondsarray. If the role is assistant and the content length is empty, return an empty
5:38:505 hours, 38 minutes, 50 secondsarray. And finally return an array and check if the role is user then map it as
5:38:595 hours, 38 minutes, 59 secondsuser and cast as const here for type safety where we're going to need this function in the future and if it's assistant then cast it as assistant and
5:39:085 hours, 39 minutes, 8 secondspass along the content. So let me go ahead and separate this like that. Great. So that
5:39:175 hours, 39 minutes, 17 secondsis our function to build conversation history. It basically strips error messages and empty messages from the
5:39:235 hours, 39 minutes, 23 secondsconversation. So, uh the token usage is lighter.
5:39:285 hours, 39 minutes, 28 secondsGreat. Now that we have that, let's go ahead and develop a type stream params that's going to accept session ID model
5:39:375 hours, 39 minutes, 37 secondshistory with a role who can be either user or assistant and content which is a string and it's going to be an array of
5:39:445 hours, 39 minutes, 44 secondsthose. So basically what we helped build right here, we're going to have mode and we're going to have an abboard controller in case of interruption.
5:39:545 hours, 39 minutes, 54 secondsAnd now we're going to go ahead and create a function to stream AI response.
5:40:025 hours, 40 minutes, 2 secondsIn the parameters of this function, we are going to accept stream with parameters parameters type of stream
5:40:105 hours, 40 minutes, 10 secondsserver send events and then the first one and then uh sorry the second one and then the first one. This is kind of an
5:40:185 hours, 40 minutes, 18 secondsugly type but it's a way to get this uh perhaps there is a way to extract
5:40:255 hours, 40 minutes, 25 secondsthat from hono directly but I don't think I was able to do it. Maybe we can do it, but I I'd rather leave it like
5:40:325 hours, 40 minutes, 32 secondsthis and then check if we can change it later. And the params are simply going to be stream params. Now, in here, I'm
5:40:405 hours, 40 minutes, 40 secondsgoing to go ahead and extract the session ID, model, history, mode, and aboard controller. And I'm going to
5:40:475 hours, 40 minutes, 47 secondsdefine the start time of the streaming so I can calculate uh when it's going to end.
5:40:545 hours, 40 minutes, 54 secondsThen let's go ahead and let's add a resolved model using the resolve chat model. And in here let's go ahead and define the full text.
5:41:055 hours, 41 minutes, 5 secondsNow let's go ahead and open a try and catch method here.
5:41:145 hours, 41 minutes, 14 secondsIn the try method, we're going to go ahead and generate the result using AI stream text from our AI package. We're
5:41:215 hours, 41 minutes, 21 secondsgoing to pass along the resolved model, the history of the messages and the abort signal so that we can cancel it if needed.
5:41:315 hours, 41 minutes, 31 secondsNow that we have the result from AI stream text, we have to iterate over every possible tool call that happens uh
5:41:405 hours, 41 minutes, 40 secondssorry every possible type of event that happens. So for each part of the result full stream let's go ahead and capture
5:41:495 hours, 41 minutes, 49 secondsit. For example, let's first do an early break if stream is aborted. And then for
5:41:565 hours, 41 minutes, 56 secondsexample, if we have a part which is text delta, let's simply append that text to the full text constant we defined above.
5:42:105 hours, 42 minutes, 10 secondsThen let's go ahead and define this event which we are going to use chat stream event type for. I'm not sure if
5:42:175 hours, 42 minutes, 17 secondsyou remember, but this comes from our shared package. And in here, we basically defined all of these tool
5:42:265 hours, 42 minutes, 26 secondscalling arguments using a discriminated union. So, if it's text delta, we expect a text. If it's reasoning, we expect a
5:42:345 hours, 42 minutes, 34 secondstext. If it's tool call, we expect tool call ID, tool name, and some arguments.
5:42:405 hours, 42 minutes, 40 secondsIf it's tool result, we expect result and tool call ID, etc. So that is what we developed I think in in a few
5:42:475 hours, 42 minutes, 47 secondschapters before and now we are using it here to specify using the results of the AI stream text function how we want to
5:42:575 hours, 42 minutes, 57 secondsstore each part that happens and now that we have the event we have to use Hono's
5:43:045 hours, 43 minutes, 4 secondswrite sE and simply send back the event which is text delta and then data JSON stringify event.
5:43:185 hours, 43 minutes, 18 secondsNow let's go ahead and check if part type is error. Let's throw back that error.
5:43:265 hours, 43 minutes, 26 secondsThen let's go ahead and check the following.
5:43:315 hours, 43 minutes, 31 secondsIf stream happens to be aborted or if a board controller signal is aborted, let's do an early return.
5:43:385 hours, 43 minutes, 38 secondsOtherwise, let's go ahead and calculate how long this took. So we're going to use date now minus the start time that
5:43:465 hours, 43 minutes, 46 secondswe defined up here. And that's how we know when the streaming has finished.
5:43:505 hours, 43 minutes, 50 secondsAnd once we know that we can go ahead and write the assistant message back to the database.
5:43:565 hours, 43 minutes, 56 secondsSo in here let's go ahead and pass along the following data. Session ID ro assistant status message status.complete
5:44:055 hours, 44 minutes, 5 secondscomplete model content using the full text which we are appending through the streaming events mode which is plan or
5:44:145 hours, 44 minutes, 14 secondsbuild and finally the duration and we are just going to pritify it so it's easier to work with later. So the reason
5:44:225 hours, 44 minutes, 22 secondsthis is over complicated at the moment or should I say seems over complicated is because we're only using the text
5:44:295 hours, 44 minutes, 29 secondsdelta but later we're going to have uh all of these I think I closed the tag but basically we're going to have a
5:44:375 hours, 44 minutes, 37 secondsbunch of different ones like done tool call tool result and we have to stream them in a different way so and we also
5:44:465 hours, 44 minutes, 46 secondshave to group them to display them properly on the terminal so that's why we are preparing in advance by doing this. And now we can finally
5:44:555 hours, 44 minutes, 55 secondsstore the result in the assistant message. And what we should do then is we should fire a done event with a
5:45:045 hours, 45 minutes, 4 secondsmessage that was created and the duration in milliseconds.
5:45:075 hours, 45 minutes, 7 secondsAnd let's go ahead and stream that back to the terminal. Event is done and data JSON stringify done event. Now in the
5:45:175 hours, 45 minutes, 17 secondscatch here, let's go ahead and grab the error. [snorts] And what we are going to do again is check if an abort controller
5:45:265 hours, 45 minutes, 26 secondshas been aborted. Let's go ahead and attempt to extract the error message by checking the instance of the error. And
5:45:345 hours, 45 minutes, 34 secondsonce we have that, we also have to persist this into the database. So the user has complete history of the session. So we are going to create a
5:45:435 hours, 45 minutes, 43 secondsmessage roll error status. Message status is complete meaning it's no longer streaming. So it's finished but
5:45:505 hours, 45 minutes, 50 secondsit's errored. The model that happened, the content of the message, the mode, basically everything. So the user knows exactly in which session the error has
5:45:585 hours, 45 minutes, 58 secondshappened and has complete history. So we are treating both events exactly the same. Right? The only thing we don't keep track of here is how long it took.
5:46:085 hours, 46 minutes, 8 secondsAnd now that we have that created in the database, we can go ahead and create an error event and we can stream back the
5:46:175 hours, 46 minutes, 17 secondserror event. And this is the function that we're going to extend going forward for any subsequent uh streaming parts
5:46:245 hours, 46 minutes, 24 secondsthat we need. Now let's go ahead and use this function. So let's define a new hono app. And the first thing I want to
5:46:335 hours, 46 minutes, 33 secondsbuild is the actual uh chat session ID route.
5:46:425 hours, 46 minutes, 42 secondsSo we call this just session ID because this will be registered under chat in the server index.ts.
5:46:535 hours, 46 minutes, 53 secondsSo in here we're going to have uh chat and then we're going to pass chat here.
5:46:585 hours, 46 minutes, 58 secondsSo that's why you don't have to write chat session ID here. You can just do session ID. So the first thing we're
5:47:065 hours, 47 minutes, 6 secondsgoing to do here is we're going to extract the param session ID. Then we're going to use Prisma OM to find this
5:47:135 hours, 47 minutes, 13 secondsunique session by its ID and we're going to include all the messages in that session. If the session wasn't found,
5:47:215 hours, 47 minutes, 21 secondswe're going to go ahead and do an early return with a 404.
5:47:265 hours, 47 minutes, 26 secondsOtherwise, let's go ahead and attempt to uh deconstruct Whoops. And attemp attempt to deconstruct the data that was
5:47:365 hours, 47 minutes, 36 secondspassed. And again, we're using this pattern of using validated JSON, which means that data is a completely valid content mode and model that we can use.
5:47:465 hours, 47 minutes, 46 secondsWhy is that? Because of the submit validator. So we are passing along the submit validator which we defined above
5:47:535 hours, 47 minutes, 53 secondshere which uses the submit schema which requires content to be string mode to be one of the two types and model to be one of the supported chat model ids.
5:48:065 hours, 48 minutes, 6 secondsSo we can count on this data being fully correct because if it isn't this part has already thrown an error back to the user.
5:48:155 hours, 48 minutes, 15 secondsAnd now what we can do is we can store that message immediately in the database. Right? So this is basically a user sending a new message here. So let's store that in the database.
5:48:255 hours, 48 minutes, 25 secondsSession ID ro user status message status.complete model data.mod content
5:48:315 hours, 48 minutes, 31 secondsdata.content and mode data do mode. Now once we have that we have to start streaming back the answer to the user's
5:48:405 hours, 48 minutes, 40 secondsmessage. So we have to rebuild the history. So, we're going to build our uh we're going to use our function build
5:48:485 hours, 48 minutes, 48 secondsconversation history. And inside of the messages array, we're going to open a new array. We're going to load all of
5:48:565 hours, 48 minutes, 56 secondsthe messages from the session that we have loaded here. If you want to, you
5:49:025 hours, 49 minutes, 2 secondscan, you know, to do maybe limit to last 10 five messages simply. If in
5:49:105 hours, 49 minutes, 10 secondsproduction this becomes too heavy, you would probably do something like that.
5:49:145 hours, 49 minutes, 14 secondsUh and then you append a new message which is basically what we just stored
5:49:215 hours, 49 minutes, 21 secondsin the database and that's how AI knows okay I have the entire context and I have your newest message. Now we have to
5:49:295 hours, 49 minutes, 29 secondsprepare the abort controller here in case something gets cancelled and let's simply return
5:49:375 hours, 49 minutes, 37 secondsstream server sent event. In the first argument we have to pass along the context and then in the second argument
5:49:455 hours, 49 minutes, 45 secondswe are writing a function. So this is going to be an asynchronous function and inside of here
5:49:545 hours, 49 minutes, 54 secondswe are going to start by capturing the onabort event of the stream and calling abort controller.abort.
5:50:035 hours, 50 minutes, 3 secondsOtherwise let's go ahead and simply stream the AI response. In here we pass along the stream and then we pass along
5:50:115 hours, 50 minutes, 11 secondssession ID, model history, mode and aboard controller. Basically that is this function which we have developed which is going to look at each part of
5:50:205 hours, 50 minutes, 20 secondsthe stream. It's going to call ourselves AI stream event here and carefully emit every type of event that we need which
5:50:285 hours, 50 minutes, 28 secondsincludes the text delta the error the finished event or done event and the
5:50:345 hours, 50 minutes, 34 secondserror event. So we are now using that in here stream server send events and we don't have to write the entire function here. We can just reuse it here.
5:50:455 hours, 50 minutes, 45 secondsOkay. And then let's go ahead and add a third call back here which is in case of an error.
5:50:535 hours, 50 minutes, 53 secondsSo in case the error happens, let's try and deconstruct the message using its instance.
5:51:005 hours, 51 minutesAnd what do we do? Well, we just go ahead and create another error event and
5:51:065 hours, 51 minutes, 6 secondswe simply emit that event back. So this is for something completely uncaught unrelated to stream AI response because
5:51:155 hours, 51 minutes, 15 secondsin here we have our own catch function which does that but you never know uh this can break in many other ways. So
5:51:245 hours, 51 minutes, 24 secondslet's just make sure that we are properly communicating back with the user what happened right something broke.
5:51:315 hours, 51 minutes, 31 secondsAll right, let's export default app here and then let's go ahead and uh map this
5:51:405 hours, 51 minutes, 40 secondsfunction in our server source index.ds.
5:51:465 hours, 51 minutes, 46 secondsSo in here I'm going to go ahead and chain another route chat
5:51:545 hours, 51 minutes, 54 secondsand I'm going to add chat. And then we just have to add import chat from routes chat just like that. Let's go back
5:52:035 hours, 52 minutes, 3 secondsinside of our chat routes now. So what we implemented here is for the first time the user sends a message, right?
5:52:135 hours, 52 minutes, 13 secondsBut there is another route that we have to develop which is basically to resume something. So I'm going to go ahead and do that uh at the end here.
5:52:235 hours, 52 minutes, 23 secondsActually let let me do it at the top.
5:52:265 hours, 52 minutes, 26 secondsSo another post request and in here we're going to add another session ID resume.
5:52:385 hours, 52 minutes, 38 secondsThere will be no validator here because there is nothing for the user to pass along here. Instead what we're going to
5:52:455 hours, 52 minutes, 45 secondsdo is we're going to grab the session ID. We're going to find the unique session
5:52:525 hours, 52 minutes, 52 secondsand load all of its messages. We are then going to return early if session wasn't found. We are specifically going to look for the last message.
5:53:035 hours, 53 minutes, 3 secondsThen let's go ahead and check the following use case. If there is no last message or if the last message role is
5:53:105 hours, 53 minutes, 10 secondsnot from the user, that means that there is nothing to resume. The resume endpoint only works if the last message
5:53:205 hours, 53 minutes, 20 secondsis something like this assistance message. But that's not the only criteria. Of course, we're also going to check if the last message uh message
5:53:295 hours, 53 minutes, 29 secondsstatus is not complete. So in case there is no last message and in case the last
5:53:365 hours, 53 minutes, 36 secondsmessage uh role is not user, it means whatever happened is finished, right?
5:53:425 hours, 53 minutes, 42 secondsAnd now we have to be careful. We can't just allow the user to resume something.
5:53:475 hours, 53 minutes, 47 secondsWe have to check again if this is even supported. So let's go ahead and do another check. If not supported chat
5:53:555 hours, 53 minutes, 55 secondsmodel, then pick at the last message and choose the model. In that case, we have to throw the error. Uh this session uses
5:54:035 hours, 54 minutes, 3 secondsan an unsupported model. Perhaps this is a session from the last year and we deprecated that model. So we have to be
5:54:105 hours, 54 minutes, 10 secondscareful. And then again here we have to reconstruct our history using build conversation history. We have to add the
5:54:185 hours, 54 minutes, 18 secondsabboard controller. And then we do what we usually did do what we did before. I mean we stream sec event. So let's go
5:54:265 hours, 54 minutes, 26 secondsahead and write an asynchronous function here.
5:54:315 hours, 54 minutes, 31 secondsAnd in here we are first things first going to handle the abboard from happening. Uh and in here we do stream not context. Sorry.
5:54:425 hours, 54 minutes, 42 secondsThen let's go ahead and use our stream AI response once again. This is why we wrote it like that because we can now
5:54:505 hours, 54 minutes, 50 secondsuse it multiple times both in our initial chat and in our resume chat function.
5:54:575 hours, 54 minutes, 57 secondsAnd this resume chat is actually going to be crucial for us to have. Even if you want that feature or not because of the optimistic mutation that we are
5:55:055 hours, 55 minutes, 5 secondsdoing when we send the new message, this is actually going to be used quite intensively. So you need the resume method here. Uh okay. So after we stream
5:55:135 hours, 55 minutes, 13 secondsback the continue response, right? like the resume. Let's go ahead and just handle the error once again because again something can go wrong, right?
5:55:245 hours, 55 minutes, 24 secondsMaybe network connection is bad or our database failed or something. Uh so we have to handle the errors as well.
5:55:315 hours, 55 minutes, 31 secondsBasically the exact same line we have below this one, right? It's the third argument
5:55:405 hours, 55 minutes, 40 secondsof our stream sec. This is the first one. This is the second argument. And this is the third argument that we just
5:55:485 hours, 55 minutes, 48 secondsadded which handles sending back the error event to the terminal in case something fails unrelated to stream AI
5:55:555 hours, 55 minutes, 55 secondsresponse because again stream AI response handles its own try catch. So it will catch any errors and it will
5:56:025 hours, 56 minutes, 2 secondssend that and uh persist that in the database. So yeah, the only difference is that the errors happened in here are
5:56:095 hours, 56 minutes, 9 secondsnot going to be persisted in the database which is okay because they are mostly like temporary errors anyway.
5:56:165 hours, 56 minutes, 16 secondsUh brilliant. So that is uh everything we need for our API route which marks uh
5:56:235 hours, 56 minutes, 23 secondsthis part as complete this entire thing in fact. And now uh we have to implement
5:56:325 hours, 56 minutes, 32 secondsthe use chat hook which will be able to parse this entire API endpoint on the
5:56:405 hours, 56 minutes, 40 secondsfront end or should I say in the terminal so it can actually uh stream what happened.
5:56:475 hours, 56 minutes, 47 secondsLet's start by adding some packages that we're going to need to develop the use chat hook. So we're going to have to add
5:56:555 hours, 56 minutes, 55 secondspackages inside of CLI here. So let me go here CLI.
5:57:025 hours, 57 minutes, 2 secondsMake sure you are in here. Let's add event source parser so it's easier for
5:57:095 hours, 57 minutes, 9 secondsus to parse these events on the front end. Another helper util pretty milliseconds and let's just keep it at that.
5:57:195 hours, 57 minutes, 19 secondsSo those two packages and you can see the versions that I'm using.
5:57:245 hours, 57 minutes, 24 secondsNow, inside of here, you should see those two, but let's add another one
5:57:315 hours, 57 minutes, 31 secondsbesides night code shared. Let's add night code database.
5:57:375 hours, 57 minutes, 37 secondsAnd oops, one thing I want to do is I want to go back to my root and just run bun install just to make sure everything
5:57:465 hours, 57 minutes, 46 secondsis linked properly. It looks like it is great. So now that we have that,
5:57:535 hours, 57 minutes, 53 secondslet's go ahead and let's build use chat hook.
5:57:575 hours, 57 minutes, 57 secondsSo inside of packages CLI source, let's create a new folder called hooks.
5:58:045 hours, 58 minutes, 4 secondsAnd inside of here, let's add use chat.ds.
5:58:105 hours, 58 minutes, 10 secondsLet's import everything we need from React.
5:58:145 hours, 58 minutes, 14 secondsLet's import event source parser stream from our new util. 30 milliseconds from
5:58:215 hours, 58 minutes, 21 secondsour new package client response type from Hono client.
5:58:285 hours, 58 minutes, 28 secondsOur API client which is an RPC communicator with our Hono server. Our util to uh properly parse error messages
5:58:365 hours, 58 minutes, 36 secondson the CLI. Let's go ahead and grab an enum from our night code database package. And let's go ahead and add chat
5:58:455 hours, 58 minutes, 45 secondsstream event schema and type supported chat model ID from night code shared.
5:58:515 hours, 58 minutes, 51 secondsNow let's go ahead and define some further types which we're going to need. Client message part type text string.
5:58:595 hours, 58 minutes, 59 secondsAnd now let's go ahead and create a discriminated union message type. So the first thing it can be is the following
5:59:095 hours, 59 minutes, 9 secondswhich is a role user content string mode mode and model a supported chat model.
5:59:155 hours, 59 minutes, 15 secondsSo that's if the user is sending a message. Then we have a second scenario if the assistant is sending a message.
5:59:245 hours, 59 minutes, 24 secondsSo let me go ahead and be consistent and just collapse all of these so they're easier to look at and consume and so you can see the differences more clearly.
5:59:345 hours, 59 minutes, 34 secondsSo we have user in here we have assistant and in here you can see we have parts and we also have duration
5:59:425 hours, 59 minutes, 42 secondsbecause this is streamed back to us and then we're going to have the last one
5:59:485 hours, 59 minutes, 48 secondswhich is the error if something goes wrong.
5:59:535 hours, 59 minutes, 53 secondsNow let's go ahead and do another discriminated union for the streaming state type. So streaming state can
6:00:006 hourseither be idle or it can be in the middle of streaming. So for that status is going to be streaming parts are going
6:00:096 hours, 9 secondsto be a type of client message part which is an array. And finally we're going to have mode and model like we usually do. All right. So we just define
6:00:186 hours, 18 secondsuh those two discriminated unions. Now let's go ahead and define the type for an active stream which has a request ID
6:00:286 hours, 28 secondsa controller which is aboard controller mode model which is supported channel uh chat model ID and parts client message
6:00:366 hours, 36 secondspart. Now let's go ahead and define submit params which are user text mode and model. Let's go ahead and create
6:00:446 hours, 44 secondsrunstream params which is mode model and the request which has the controller.
6:00:516 hours, 51 secondsAnd now let's go ahead and export function use chat the actual hook.
6:00:596 hours, 59 secondsSo the params of use chat are going to be session ID and besides session ID, we're also going
6:01:076 hours, 1 minute, 7 secondsto have the initial messages which is just an array of our messages type.
6:01:136 hours, 1 minute, 13 secondsLet's go ahead and store them in a state. Let's go ahead and keep track of the streaming state which we're going to
6:01:226 hours, 1 minute, 22 secondskeep off uh we're going to keep track of this in an object like this. So use state for streaming is going to be an object with a status property inside.
6:01:336 hours, 1 minute, 33 secondsAnd also I mean it's it's a discriminated union.
6:01:376 hours, 1 minute, 37 secondsIf it the status is idle it's just status. But if we change this to streaming we're also going to have to keep track of the parts which are being
6:01:456 hours, 1 minute, 45 secondsemitted. mode which is build or plan and the model that is writing back to us. So that's why we needed that discriminated
6:01:536 hours, 1 minute, 53 secondsunion. Now let's go ahead and define a ref active stream ref.
6:01:596 hours, 1 minute, 59 secondsThen let's go ahead and create a callback to update the messages as they appear. So I'm going to go ahead and try
6:02:076 hours, 2 minutes, 7 secondsand collapse this a bit. I'm not sure uh how it's easier for you to look at it.
6:02:136 hours, 2 minutes, 13 secondsThere we go. So update messages is a use call back which accepts the updator which is another function which simply returns an array of messages and in here
6:02:236 hours, 2 minutes, 23 secondswe call set messages with the current value and we pass it through the call back call updator which we are going to assign later.
6:02:326 hours, 2 minutes, 32 secondsNow let's go ahead and create another function here is active request which again uh is a use callback with a
6:02:406 hours, 2 minutes, 40 secondsrequest ID and it will simply use our active stream ref to see if that is a currently active request so that we
6:02:466 hours, 2 minutes, 46 secondsdon't do any duplicate requests. Now let's go ahead and create a callback to emit parts.
6:02:546 hours, 2 minutes, 54 secondsLet's start with a function and let's not forget the dependency array.
6:03:016 hours, 3 minutes, 1 secondSo the emit parts needs to take in some params. The first one will be request ID
6:03:086 hours, 3 minutes, 8 secondsand the second one is going to be parts coming from the server.
6:03:136 hours, 3 minutes, 13 secondsSo what it's going to do here is first it's going to check if the request ID is already active. So uh if it is not
6:03:206 hours, 3 minutes, 20 secondsactive, let's go ahead and do an early return. Now let's go ahead and create a snapshot from our parts. Let's go ahead and set the active stream to the ref.
6:03:346 hours, 3 minutes, 34 secondsMy apologies, we are not setting it here. We are extracting it. And if it doesn't exist, we do an early return.
6:03:416 hours, 3 minutes, 41 secondsAnd then we set the active stream parts to our parts which we've created a snapshot of here. And now we can go
6:03:506 hours, 3 minutes, 50 secondsahead and change the streaming state to streaming. And because of that, we also have to pass along these three otherwise
6:03:576 hours, 3 minutes, 57 secondsit's an error. So we need snapshot parts. We are doing a snapshot. So we don't pass mutable objects here. So that's why we are doing a shallow copy
6:04:066 hours, 4 minutes, 6 secondsmode active stream mode model active stream dot model. And very important, let's go ahead and add is active request to the dependency array.
6:04:176 hours, 4 minutes, 17 secondsNow let's go ahead and add another use callback which is used to clear the stream. So clear stream use call back
6:04:246 hours, 4 minutes, 24 secondsaccepts a request ID again checks if it is not active request. Let's do an early return and then simply resets the active
6:04:326 hours, 4 minutes, 32 secondsstream ref and sets the streaming back to idle. And don't forget the dependency array. So it's just like a reset button.
6:04:416 hours, 4 minutes, 41 secondsAnd now let's go ahead and develop the actual handle stream callback.
6:04:466 hours, 4 minutes, 46 secondsLet's go ahead and prepare dependency array. And let's start with the arguments here. And let's go ahead and make this asynchronous.
6:04:576 hours, 4 minutes, 57 secondsSo it's going to accept a response, which is a client response of type unknown. And then the active stream as the second argument.
6:05:096 hours, 5 minutes, 9 secondsAgain, let's go ahead and check if we are attempting to modify a request which is not currently active. So let's do an early return if it's not active. Now
6:05:176 hours, 5 minutes, 17 secondslet's go ahead and check for the scenario if the fetch response is not okay because in that case we have to
6:05:256 hours, 5 minutes, 25 secondsread and extract the error message from the response and then we have to update the messages
6:05:346 hours, 5 minutes, 34 secondsand we have to spread the existing messages and simply append the last message at the end giving it a mock id a
6:05:416 hours, 5 minutes, 41 secondsro of error and content message. So this is like an optimistic update instead of refetching all messages when an error
6:05:486 hours, 5 minutes, 48 secondshappens. And what's important here is an early return. All right.
6:05:546 hours, 5 minutes, 54 secondsNow let's go ahead and do the other scenario which is if everything is okay.
6:05:596 hours, 5 minutes, 59 secondsSo in that case we have to prepare the parts that are happening. Now let's prepare the stream. So from response we're going to go ahead and try to access the body.
6:06:106 hours, 6 minutes, 10 secondsThen let's go ahead and do pipe through.
6:06:136 hours, 6 minutes, 13 secondsAnd let's do new text decoder stream.
6:06:196 hours, 6 minutes, 19 secondsAnd let's go ahead and add an exclamation point here. So we always expect the body at this point because we do an early return if there is an error.
6:06:286 hours, 6 minutes, 28 secondsLet's make sure to execute the text decoder stream. And then we have to pipe through once again using the new event
6:06:366 hours, 6 minutes, 36 secondssource parser stream which we have added the package for. And this will heavily
6:06:436 hours, 6 minutes, 43 secondsuh make it easier for us to iterate through the stream response. So let's do a for loop here. So for await const and
6:06:536 hours, 6 minutes, 53 secondsthen we extract through the stream part data of each stream. Again, let's do a
6:07:016 hours, 7 minutes, 1 secondcheck here. If it's not active request of the active stream request ID, let's do an early return. Otherwise, let's add
6:07:076 hours, 7 minutes, 7 secondsan empty variable event. And then let's open a try and catch here. Try catch.
6:07:156 hours, 7 minutes, 15 secondsIn the try event, we're going to simply assign to the event chat stream event schema.parse
6:07:236 hours, 7 minutes, 23 secondsJSON.parse data. So we are basically just going to make sure that whatever we received is exactly what we expect. Text
6:07:326 hours, 7 minutes, 32 secondsdelta, reasoning delta, tool call, tool result or done or error.
6:07:396 hours, 7 minutes, 39 secondsAnd in case of an error here, let's go ahead and get our message using
6:07:466 hours, 7 minutes, 46 secondsits instance. And then again, let's do an optimistic update of the messages.
6:07:506 hours, 7 minutes, 50 secondsHere we spread all existing messages and we append the last one with a fake ID, a row of error and the content of what
6:07:586 hours, 7 minutes, 58 secondshappened. What's important here is to break.
6:08:036 hours, 8 minutes, 3 secondsAll right, now that we have that, let's go ahead and decide how we are going to
6:08:106 hours, 8 minutes, 10 secondsdisplay each stream type back to our terminal. For example, if we have a case
6:08:186 hours, 8 minutes, 18 secondsof text delta, what should we do? Well, let's go ahead and group them together.
6:08:256 hours, 8 minutes, 25 secondsSo, we're going to get uh the last variable here using the uh last part of
6:08:326 hours, 8 minutes, 32 secondsall parts that we receive. And we're going to check if that last part exists and it's a type of text. Let's simply go
6:08:416 hours, 8 minutes, 41 secondsahead and append it. else. If that's not the case, I'm just going to go ahead and push it to the parts like that.
6:08:526 hours, 8 minutes, 52 secondsThen let's go ahead and let's call emit parts active stream request ID and pass along the parts.
6:09:036 hours, 9 minutes, 3 secondsAnd this is where we are going to add additional cases for any tooling or things like that. Let's go ahead and add our done request here.
6:09:136 hours, 9 minutes, 13 secondsAnd of course, we need a break here, otherwise it's going to fall through in the done request. Let's go ahead and
6:09:226 hours, 9 minutes, 22 secondsdo protection here if it's not an active stream. And then let's go ahead and again attempt to construct full text
6:09:296 hours, 9 minutes, 29 secondsusing the parts. So we're going to filter to only get text parts using the part.ype.
6:09:376 hours, 9 minutes, 37 secondsThen we're going to map again and simply return the text value of each part. And then we're going to join it all together. And that's how we get a single
6:09:466 hours, 9 minutes, 46 secondsuh string value here and not an array of strings. And now we have to go ahead and
6:09:536 hours, 9 minutes, 53 secondsupdate the messages with that full text here. So we call update messages. We preserve the previous messages and we
6:10:016 hours, 10 minutes, 1 secondinject the latest message which is coming back from the assistant. So we have to preserve event message ID role
6:10:086 hours, 10 minutes, 8 secondshardcoded to assistant content is the full text we just constructed here mode is active stream do mode model active
6:10:166 hours, 10 minutes, 16 secondsstream.mmodel and then we use the pretty milliseconds function and you can see how that looks like you can pass along the time stamp and it will return a
6:10:256 hours, 10 minutes, 25 secondshuman readable string just so we don't have to develop that function as well and we do a shallow copy of the parts here so we don't accidentally mutate it
6:10:346 hours, 10 minutes, 34 secondsand after we update the messages. Let's make sure that we break.
6:10:386 hours, 10 minutes, 38 secondsAnd now let's go ahead and do the last case, which is very simple, the error case. I just did it incorrectly.
6:10:476 hours, 10 minutes, 47 secondsSo here, in case an error happens, we're just going to update the messages optimistically like we did a few times
6:10:546 hours, 10 minutes, 54 secondsbefore with the fake ID, roll off error, event message, and a break.
6:11:006 hours, 11 minutesUh, great. So we have that resolved and now we have to make sure our dependency
6:11:076 hours, 11 minutes, 7 secondsarray here has all of the proper functions update messages, emit parts and is active request.
6:11:166 hours, 11 minutes, 16 secondsNow we have to go ahead and develop another function called run stream. So let's go ahead and develop that.
6:11:276 hours, 11 minutes, 27 secondsFirst things first, uh let's go ahead and make sure it's an asynchronous function and let's add the parameters it's going to need. So it's actually
6:11:346 hours, 11 minutes, 34 secondsgoing to be uh one parameter, but we are immediately going to destruct it.
6:11:416 hours, 11 minutes, 41 secondsWhoops. Like this. We're going to have mode, model, and request all coming from a single parameter here. And it's going to be a type of run stream params.
6:11:546 hours, 11 minutes, 54 secondsNow let's go ahead in here and let's get our controller first.
6:12:006 hours, 12 minutesNow let's go ahead and define the active stream object.
6:12:056 hours, 12 minutes, 5 secondsIt's a type of active stream. We pass along the request ID controller mode and an array of parts.
6:12:136 hours, 12 minutes, 13 secondsThen let's go ahead and assign that active stream to the ref. And let's go ahead and change the status of the
6:12:216 hours, 12 minutes, 21 secondsstreaming to streaming. But let's just go ahead and make it empty for now. So empty parts, default mode, and default model. And now let's go ahead and open a try and catch block here.
6:12:356 hours, 12 minutes, 35 secondsAnd in the try method, all we have to do is we have to get the response and pass along the controller in the request. And
6:12:446 hours, 12 minutes, 44 secondsonce we get the response, we can simply pass it along through handle stream function which we have developed up
6:12:526 hours, 12 minutes, 52 secondshere. So it's automatically going to construct the stream events, update the messages, update the streaming state,
6:13:006 hours, 13 minuteseverything else it needs in case the error happens. Let's just go ahead and check what kind of error has happened.
6:13:076 hours, 13 minutes, 7 secondsBecause if it is an abort error, we can just do an early return. we don't have to display the error to the user because
6:13:146 hours, 13 minutes, 14 secondswe purposely did this. Then let's go ahead and do some protection. If it's not active request, let's do an early
6:13:216 hours, 13 minutes, 21 secondsreturn. And now let's go ahead and extract what was the error if it wasn't abort error using its instance. And then
6:13:296 hours, 13 minutes, 29 secondswe do another optimistic update using update messages where we preserve the previous message and just simply append
6:13:366 hours, 13 minutes, 36 secondsa fake error message at the end. And let's add a finally clause here where we clear the stream at the end. So it's no
6:13:446 hours, 13 minutes, 44 secondslonger active and it's no longer connected. And let's not forget to add uh all of the
6:13:546 hours, 13 minutes, 54 secondsdependency array items we need which are clear stream, handle stream, is active request and update messages.
6:14:016 hours, 14 minutes, 1 secondNow let's go ahead and build a simpler function which is the resume function. And so yes, we need to handle all of those
6:14:086 hours, 14 minutes, 8 secondscases that we just developed on the back end here.
6:14:136 hours, 14 minutes, 13 secondsSo this is a huge function but that is because we are trying to replicate AI
6:14:196 hours, 14 minutes, 19 secondsSDK's use chat uh which has all of those features. Yes, it can resume uh it can
6:14:276 hours, 14 minutes, 27 secondscapture events like on finish on error on data. We are kind of doing that for
6:14:346 hours, 14 minutes, 34 secondsuh our scenario. So we have handle stream, we have clear stream and we're going to return all of those functions from this hook. So the user can then
6:14:436 hours, 14 minutes, 43 secondsjust easily uh call run stream for example or call resume whatever the user
6:14:506 hours, 14 minutes, 50 secondsneeds depending on what's going on at the moment.
6:14:556 hours, 14 minutes, 55 secondsSo this will be an asynchronous function and again just a single uh parameter here which we are immediately going to
6:15:026 hours, 15 minutes, 2 secondsdeconstruct. So we're going to get mode and model from the submit params but we're going to omit user text so we
6:15:096 hours, 15 minutes, 9 secondsdon't get the error here because uh this is technically submitting it but we are
6:15:166 hours, 15 minutes, 16 secondsnot allowing the user to add any new text. The user can technically trigger the submit method by rejoining a session which was interrupted.
6:15:266 hours, 15 minutes, 26 secondsSo we can reuse the submit part because technically it is a submission. Uh but we are going to extract the user text
6:15:346 hours, 15 minutes, 34 secondsbecause user is not passing any new text. And in here we just have to call our runstream function again
6:15:416 hours, 15 minutes, 41 secondsand we have to pass along the mode. We have to pass along the model and then we have to pass along the request and this
6:15:496 hours, 15 minutes, 49 secondswill be asynchronous function which has the controller and it's simply going to call our API client
6:15:586 hours, 15 minutes, 58 secondschat session id dot resume which is a post request and in here we have to define the param.
6:16:116 hours, 16 minutes, 11 secondsLet's go ahead and make sure that is session ID not sessions
6:16:196 hours, 16 minutes, 19 secondssession that's why we are getting the error here and then we also have to pass along in it
6:16:276 hours, 16 minutes, 27 secondssignal controller dots signal because user should be able to interrupt the resume method just as easily.
6:16:356 hours, 16 minutes, 35 secondsUh okay, we have that.
6:16:386 hours, 16 minutes, 38 secondsUh let me just see. So that is a resume here. Oh yeah, let's go ahead and just do a return here like this.
6:16:506 hours, 16 minutes, 50 secondsGreat.
6:16:526 hours, 16 minutes, 52 secondsSo that is it for run stream and then we just have to add the dependency arrays here. Runstream and session id.
6:17:036 hours, 17 minutes, 3 secondsNow uh there are a couple of more functions we have to develop. Since we just developed the resume, let's go
6:17:106 hours, 17 minutes, 10 secondsahead and invent a logic to auto resume when conversation ends with a user
6:17:176 hours, 17 minutes, 17 secondsmessage that has no reply. So if this use chat hook is loaded with that scenario, we're going to trigger the resume method from above. So has out a resumed ref will be false by default.
6:17:286 hours, 17 minutes, 28 secondsAnd then the only way we can resume automatically is by using use effect here.
6:17:336 hours, 17 minutes, 33 secondsSo first things first, let's check if we uh have started the auto resume.
6:17:426 hours, 17 minutes, 42 secondsIf we have, we can do an early return.
6:17:446 hours, 17 minutes, 44 secondsOtherwise, let's go ahead and grab that last message to see what we have to return. So just like we do on the back end, we're going to do some check here.
6:17:536 hours, 17 minutes, 53 secondsIf there is no last message, and if the last message isn't from the user, it means there is nothing to resume. So we are not even going to attempt to do the resume.
6:18:036 hours, 18 minutes, 3 secondsBut if we manage to pass this if block, let's go ahead and initiate into the ref that we have started the resuming process and let's go ahead and trigger
6:18:126 hours, 18 minutes, 12 secondsour resume method which we have developed from above. So pass along the mode and model from the last message that we found that we have to resume.
6:18:226 hours, 18 minutes, 22 secondsAnd let's go ahead and pass in the dependency array here which we mustn't forget initial messages and resume.
6:18:316 hours, 18 minutes, 31 secondsNow let's go ahead and develop uh second to last function which is the submit
6:18:376 hours, 18 minutes, 37 secondsfunction. Another important one I did this incorrectly I believe.
6:18:476 hours, 18 minutes, 47 secondsSo our submit method is going to be asynchronous.
6:18:536 hours, 18 minutes, 53 secondsAnd it's going to have a single parameter which we are going to deconstruct. So user text mode and model
6:19:006 hours, 19 minuteswhich are submit params. And we are going to construct the user message with a message type. We are going to
6:19:086 hours, 19 minutes, 8 secondsprepare it with a random ID role of user content user text mode and model. And we're going to go ahead and do an
6:19:166 hours, 19 minutes, 16 secondsoptimistic update here to update the messages with that user message. So we are not refetching the messages just because we submitted the new one. We are
6:19:246 hours, 19 minutes, 24 secondsgoing to manually append it. That's why we are mocking the user ID here. And now let's go ahead and call the run stream
6:19:316 hours, 19 minutes, 31 secondsmethod which is going to do the following.
6:19:376 hours, 19 minutes, 37 secondsIt's going to call chat session ID. It's going to persist to the database and it's going to start streaming back.
6:19:446 hours, 19 minutes, 44 secondsSo we need mode, we need model, and finally we need the request. Since we've already done it once, let's do it
6:19:526 hours, 19 minutes, 52 secondsagain. So request, it's an asynchronous function which has access to the controller.
6:19:586 hours, 19 minutes, 58 secondsAnd in here, let's return API client chat
6:20:056 hours, 20 minutes, 5 secondssession ID, not resume, but immediately post because this is the chat ID route.
6:20:136 hours, 20 minutes, 13 secondsAnd then in here we have to pass along the first argument which are the params and the JSON. So pass along the param
6:20:226 hours, 20 minutes, 22 secondswhich is session ID and pass along the JSON which expects content which is user text mode and model. And then we have to
6:20:306 hours, 20 minutes, 30 secondspass the other argument which is the controller signal. So we can abort this early on if it needs aborting.
6:20:386 hours, 20 minutes, 38 secondsOkay.
6:20:406 hours, 20 minutes, 40 secondsAnd let's not forget to add it to the dependency array run stream session ID and update
6:20:506 hours, 20 minutes, 50 secondsmessages. Now let's go ahead and develop the last one finally uh which is abort function. The abort
6:20:596 hours, 20 minutes, 59 secondsfunction will not take any arguments and it's just going to attempt to find the the active stream using the ref. Do an
6:21:086 hours, 21 minutes, 8 secondsearly return if it if it is unable to find it. Reset it to null. Reset
6:21:146 hours, 21 minutes, 14 secondsstreaming to idle and go ahead and call the abort
6:21:206 hours, 21 minutes, 20 secondsfrom here. Brilliant. And now from here we can finally go ahead and return the messages, the streaming, the submit and the abort.
6:21:326 hours, 21 minutes, 32 secondsNow that we have the ability to stream back messages, we have to adapt our bot message component to that. So let's go
6:21:396 hours, 21 minutes, 39 secondsinside of messages and let's go inside of bot message. We're going to have to extend uh the content it receives, which is no longer going to be content at all.
6:21:506 hours, 21 minutes, 50 secondsIt's actually going to be parts of a message and we can import the client message part from our hooks
6:21:596 hours, 21 minutes, 59 secondsuse chat. Then let's go ahead and add mode from night code database enumes. Make
6:22:086 hours, 22 minutes, 8 secondssure you add forward/niums for tree shaking so when you build it doesn't bundle it together.
6:22:146 hours, 22 minutes, 14 secondsAnd now we also have duration how long a message took. And we also have streaming as a boolean.
6:22:246 hours, 22 minutes, 24 secondsSo let's go ahead and modify those props here as well. So parts model mode duration and streaming which we're going to hardcode I mean uh default to false.
6:22:356 hours, 22 minutes, 35 secondsNow let's go ahead and build or reconstruct the text that needs to be rendered back. So that's simply
6:22:446 hours, 22 minutes, 44 secondsgoing to look through the parts that we have. It's going to filter by text. It's going to map all text and it's going to join it in all into one string. And then
6:22:526 hours, 22 minutes, 52 secondswe can replace the context here with text.
6:22:566 hours, 22 minutes, 56 secondsNow we have to go ahead and improve this.
6:23:006 hours, 23 minutesUh so what this is actually going to do
6:23:076 hours, 23 minutes, 7 secondsis it's going to change the color depending on the mode. Right?
6:23:136 hours, 23 minutes, 13 secondsSo if the mode uh let me just see mode uh oh do I have to import it as enum
6:23:246 hours, 23 minutes, 24 secondsh let me check import type oh I don't want to import it as type so don't import it
6:23:326 hours, 23 minutes, 32 secondsas type just import it from eniums but not as type all right so yeah if mode is plan we use colors plan mode from our
6:23:406 hours, 23 minutes, 40 secondstheme otherwise we use colors primary if you ended up not implementing the theme.
6:23:456 hours, 23 minutes, 45 secondsUm, here's what's plan mode is and here's what's primary is. So, you can just hardcode those hex colors. And in
6:23:526 hours, 23 minutes, 52 secondshere we have the same bullet point dot uni code that we had before. Uh, okay.
6:24:026 hours, 24 minutes, 2 secondsAnd now, uh, for the model, uh, it's going to be a little bit different. So, let's remove the model. And instead, let's go ahead and open a box with flex
6:24:106 hours, 24 minutes, 10 secondsand gap. And now let's go ahead and decide whether we should display plan or build
6:24:186 hours, 24 minutes, 18 secondshere. So if it's plan, display plan otherwise display build.
6:24:236 hours, 24 minutes, 23 secondsThen let's go ahead and create a little separator.
6:24:286 hours, 24 minutes, 28 secondsAnd we have to import text attributes from open to a core uses colors dim separator. If you don't have that, it's this color.
6:24:396 hours, 24 minutes, 39 secondsAnd in here you can use a normal chevron. Uh yeah, this one like GT if you can't find the arrow ones.
6:24:536 hours, 24 minutes, 53 secondsThen let's go ahead and render the model that was used after that. And only if we actually get the duration.
6:25:036 hours, 25 minutes, 3 secondsLet's go ahead and render a fragment.
6:25:066 hours, 25 minutes, 6 secondsAnd then let's go ahead and com uh copy this. So it's kind of like breadcrumbs.
6:25:146 hours, 25 minutes, 14 secondsAnd finally render the duration.
6:25:186 hours, 25 minutes, 18 secondsAll right. So those are the changes needed in bot message. And now let's go ahead and go inside of screens and let's
6:25:296 hours, 25 minutes, 29 secondsfind session.dsx because this one uh will now need modification. So it works with the new
6:25:376 hours, 25 minutes, 37 secondsuh implementation right because you can see content is no longer accepted here.
6:25:426 hours, 25 minutes, 42 secondsSo first things first let's go ahead and import pretty milliseconds from pretty milliseconds.
6:25:506 hours, 25 minutes, 50 secondsThen uh let's go ahead and import from night code shared default chat model ID and type supported
6:25:596 hours, 25 minutes, 59 secondschat model ID. Then let's go ahead and import use chat from hooks. Use chat.
6:26:066 hours, 26 minutes, 6 secondsAnd finally let's import types message and client message part from hooks use chat.
6:26:146 hours, 26 minutes, 14 secondsSo now what we have to develop is a function to map database messages before we display them here. So let's go ahead
6:26:226 hours, 26 minutes, 22 secondsand develop that here. Map database messages accepts messages from the session.
6:26:316 hours, 26 minutes, 31 secondsLet's go ahead and return map database messages.
6:26:396 hours, 26 minutes, 39 secondsAnd for each message, we're going to see what we have to return. For example, if a message is a type of error, let's go ahead and return an object with ID, ro of error, and a simple content inside.
6:26:516 hours, 26 minutes, 51 secondsNow let's go ahead and do if the role is user return ro user m content mode and
6:27:006 hours, 27 minutesmodel. And finally we have a scenario if it's the assistant message that's being
6:27:066 hours, 27 minutes, 6 secondsreturned. So in this case uh we do pretty similar thing. We pass along the ID, the role of assistant, the content,
6:27:146 hours, 27 minutes, 14 secondsthe model and the mode. But there are also other things we can do here which are now very important which are parts
6:27:236 hours, 27 minutes, 23 secondsand we also have optional duration. So let's go ahead and do optional duration here. So if duration is not null in that
6:27:316 hours, 27 minutes, 31 secondscase open an object and pass along the duration to be pretty milliseconds and do this calculation otherwise an empty array.
6:27:406 hours, 27 minutes, 40 secondsGreat. Now let's go inside of chat message here uh and let's see all of the
6:27:476 hours, 27 minutes, 47 secondschanges that we have to do. So if message ro is user render user message.
6:27:526 hours, 27 minutes, 52 secondsIf message ro is error render error message. And for the bot message we now have to modify all of the props. So let's go ahead and do that.
6:28:036 hours, 28 minutes, 3 secondsThere we go. We're going to see what the error is about.
6:28:106 hours, 28 minutes, 10 secondsLet me just fix this first and let's fix the indentation here. Uh so let's see uh
6:28:206 hours, 28 minutes, 20 secondswhat is currently happening. So let's modify the chat message here to not use session data messages because this at this point is no longer uh that's why we
6:28:296 hours, 28 minutes, 29 secondsdid the function above to remap from session data messages into a digestible model that we can use to render here. So this is no longer that type actually.
6:28:406 hours, 28 minutes, 40 secondsIt's now using the message type. Uh which I think I somehow made even worse.
6:28:476 hours, 28 minutes, 47 secondsOh, because this now needs to be error.
6:28:506 hours, 28 minutes, 50 secondsMy apologies. Lowerase user error.
6:28:566 hours, 28 minutes, 56 secondsYeah, we have to change the uh the role here because it can be either error or assistant because that's
6:29:036 hours, 29 minutes, 3 secondswhat we map it map it as here. If you change this to uppercase user, you could continue using it. So just make sure that it's all in sync.
6:29:136 hours, 29 minutes, 13 secondsGreat. So we now have that. And now we have to develop another function called session chat
6:29:256 hours, 29 minutes, 25 secondswhich accepts the session and that session is a type of session data.
6:29:346 hours, 29 minutes, 34 secondsLet's go ahead and grab the initial messages using map database messages.
6:29:416 hours, 29 minutes, 41 secondsThen let's go ahead and add our use chat function. Pass along the session ID and the initial messages. And we can extract the messages, the streaming, submit, and
6:29:506 hours, 29 minutes, 50 secondsabort. Let's go ahead and stop any pending replies if user leaves the session. So we manually call the abort first.
6:29:596 hours, 29 minutes, 59 secondsAnd now we can simply reuse a bunch of components that we already have here. So let's go ahead and render the session
6:30:066 hours, 30 minutes, 6 secondsshell. But instead of making it uh useless as this example where it's actually not uh submitting anything or
6:30:146 hours, 30 minutes, 14 secondsdoing anything, we are going to go ahead and make it do something on submit. So on submit it
6:30:226 hours, 30 minutes, 22 secondswill receive the user text and it's going to call the submit method from use chat. pass along the user text, hardcode the model mode to build because we
6:30:296 hours, 30 minutes, 29 secondscurrently cannot modify it and hardcode the model to the default chat model. And then let's go ahead and make sure that it displays the loading state if it is in the streaming status.
6:30:416 hours, 30 minutes, 41 secondsAnd then very simply inside it will render messages and display our chat message component from above. And the
6:30:496 hours, 30 minutes, 49 secondsonly exception is going to be if it's currently streaming. If it's currently streaming and streaming parts have begun
6:30:566 hours, 30 minutes, 56 secondsmeaning they are greater than zero in that case we can render the bot message and pass along the parts the model the mode and the streaming and then when the
6:31:046 hours, 31 minutes, 4 secondsstreaming completes this message gets hidden but at that point it will already become persistent in the database and
6:31:116 hours, 31 minutes, 11 secondsupdated optimistically. So it will be rendered in that component anyway. So it's a very seamless user experience.
6:31:196 hours, 31 minutes, 19 secondsGreat. And now we can drastically simplify our session here down here. Uh we no longer have to uh do
6:31:296 hours, 31 minutes, 29 secondsthis at all. We can just do a oneline return actually.
6:31:366 hours, 31 minutes, 36 secondssession chat pass along the key so we can easily uh destroy the component if the session ID
6:31:456 hours, 31 minutes, 45 secondschanges and pass along the session object just like that. All right, now that we
6:31:536 hours, 31 minutes, 53 secondshave that done, the only thing we have to do is add our API keys. Uh so I'm
6:32:026 hours, 32 minutes, 2 secondsgoing to show you in the environment example. So you will now need to obtain either anthropic key or uh you can
6:32:126 hours, 32 minutes, 12 secondsobtain uh open AI API key. If you don't know uh which one you need for your
6:32:226 hours, 32 minutes, 22 secondsprovider using the AI SDK, you actually go let me go to the how do I go to the
6:32:316 hours, 32 minutes, 31 secondsroot page? basically find providers and models and in here find the one you're using. So if you're using Google for
6:32:396 hours, 32 minutes, 39 secondsexample because it has a free API you can go ahead and find the documentation here and you can see what it's going to search for. So you need to add Google
6:32:486 hours, 32 minutes, 48 secondsgenerative AI API key here if you're using Google models for example just make sure that in your models.dts DS in
6:32:556 hours, 32 minutes, 55 secondsthe shared package down here you replace the default chat model to one of the Google models you have added here for
6:33:026 hours, 33 minutes, 2 secondsexample I have the entropic key so I'm going to go ahead and use uh the anthropic key
6:33:106 hours, 33 minutes, 10 secondsuh so let me go ahead inside of environment and let me add my anthropic key here you can obtain them from the
6:33:176 hours, 33 minutes, 17 secondsofficial uh anthropic website or openAI website and once you add the key Here we
6:33:256 hours, 33 minutes, 25 secondsshould be in business. Let's go ahead and do uh first of all let me close the finished example
6:33:326 hours, 33 minutes, 32 secondsand let me close the finished example server.
6:33:386 hours, 33 minutes, 38 secondsSo night code bun rundev server. Let's check if that works. Works bundev cli
6:33:476 hours, 33 minutes, 47 secondsand the moment of truth. Hello. How are you? And let's see if we connected everything correctly. It is loading. It
6:33:566 hours, 33 minutes, 56 secondsis loading. And we [clears throat] have streaming. It took 4 seconds to stream this. Let's do an interruption test.
6:34:046 hours, 34 minutes, 4 secondsWrite me a long message for example. And let's see what that's going to happen.
6:34:106 hours, 34 minutes, 10 secondsAnd if I press escape, uh, if I press escape, nothing is happening. Uh, yes, because we didn't implement the
6:34:176 hours, 34 minutes, 17 secondsinterruption just yet. We're going to do that next. And it is uh not as complicated as any of this. You don't
6:34:246 hours, 34 minutes, 24 secondshave to worry. Uh but yeah, we can now stream. Amazing amazing job.
6:34:326 hours, 34 minutes, 32 secondsIn order to implement the last step which is stream interruption, we have to
6:34:396 hours, 34 minutes, 39 secondsgo ahead and go back inside of our chat router and we have to add the
6:34:466 hours, 34 minutes, 46 secondsfunctionality to actually interrupt something. So, we have a lot of things in place like abort controllers, but we
6:34:546 hours, 34 minutes, 54 secondsdon't really have the ability to interrupt and persist an interrupted message, which is maybe even more important. So, let's go back inside of
6:35:036 hours, 35 minutes, 3 secondsthe server source routes chat. DS and let's go ahead and find where we start about here. Build conversation history.
6:35:156 hours, 35 minutes, 15 secondsWhat I want to do is I want to have an in-memory uh active resume session ID set here. The reason I'm going to do
6:35:236 hours, 35 minutes, 23 secondsthis is because uh it is technically possible for use effect to fire twice
6:35:326 hours, 35 minutes, 32 secondsand then it's going to persist the same uh resumed session twice. And by keeping
6:35:396 hours, 35 minutes, 39 secondstrack of inmemory here, we can prevent that on a very primitive level, but it drastically improves the experience and
6:35:466 hours, 35 minutes, 46 secondsreduces the amount of bugs that could happen.
6:35:506 hours, 35 minutes, 50 secondsSo uh after the build conversation history function, let's go ahead another function here called get resumable user
6:35:586 hours, 35 minutes, 58 secondsmessage. Now the messages prop is basically an array of objects. Let me go ahead and collapse this.
6:36:116 hours, 36 minutes, 11 secondsAnd the messages can have ro model and mode. We're going to have go ahead and
6:36:186 hours, 36 minutes, 18 secondsget the last message. And we are simply looking for a last message that exists and the last message whose role isn't
6:36:266 hours, 36 minutes, 26 secondsuser. So like a handy little util. So we don't have to write this function every single time.
6:36:326 hours, 36 minutes, 32 secondsNow, uh, let's go ahead and scroll down here until we find, uh, full text. And I
6:36:406 hours, 36 minutes, 40 secondswant to add a function called, uh, persist interrupted message and make sure it's an asynchronous function. The
6:36:476 hours, 36 minutes, 47 secondsfirst thing we're going to do is we're going to check if the full text length is zero. In that case, there is nothing to resume. Otherwise, we have to uh I
6:36:576 hours, 36 minutes, 57 secondsmean nothing to resume. There's nothing to persist. So what we have to do now is we have to capture a message that was
6:37:056 hours, 37 minutes, 5 secondsinterrupted and we are going to calculate how long it took to generate whatever it generated and then we have
6:37:136 hours, 37 minutes, 13 secondsto store it into the database right even though it was interrupted.
6:37:196 hours, 37 minutes, 19 secondsSo let's go ahead and pass in the session ID ro assistant but let's keep track that it was interrupted. pass
6:37:266 hours, 37 minutes, 26 secondsalong the model, the content, full text, mode, and the duration. So the the identical thing that we do if it's a
6:37:336 hours, 37 minutes, 33 secondssuccessful one, which is this one, but instead of message status complete, we do message status interrupted so we can display the proper UI for it and so that
6:37:426 hours, 37 minutes, 42 secondswe can uh know if we have to resume it later. Okay. Uh and the only thing we
6:37:506 hours, 37 minutes, 50 secondsdon't do if the text is empty, we don't store it, right? the user interrupted at a point where not a single letter was written. So we don't have to store that
6:37:586 hours, 37 minutes, 58 secondsinto the database. Right? And now let's go ahead and find our try.
6:38:056 hours, 38 minutes, 5 secondsScroll down until we find stream aborted here. And we're going to go ahead and now extend it by also calling persist
6:38:146 hours, 38 minutes, 14 secondsinterrupted message. So if stream is aborted or abort controller has been called, we can persist the interrupted message like that. Now, let's go ahead
6:38:236 hours, 38 minutes, 23 secondsdown here until we find catch and do the same thing before a return. Great.
6:38:306 hours, 38 minutes, 30 secondsNow, uh let's go ahead and scroll further down uh in the resume method here.
6:38:406 hours, 38 minutes, 40 secondsAnd in here, let's go ahead and rename uh this last message into resumable message like that.
6:38:546 hours, 38 minutes, 54 secondsAnd instead of calling session uh session messages like this what I told you before we can now simply call our
6:39:036 hours, 39 minutes, 3 secondsfunction get resum resumable user message which technically does that but returns null if it's not correct and
6:39:116 hours, 39 minutes, 11 secondsthen let's go ahead and simply we don't have to check for the user we don't have to check anything we can just check if there is no resumable message throw the
6:39:196 hours, 39 minutes, 19 secondserror otherwise let's go ahead and check the supported uh model from resumable message domodel.
6:39:286 hours, 39 minutes, 28 secondsMake sure you don't accidentally use mode and again update this to be resumable message dot model.
6:39:396 hours, 39 minutes, 39 secondsDown here uh we now have to add another if clause.
6:39:456 hours, 39 minutes, 45 secondsSo after we check for supported chat model, we also have to check what I told you in the beginning which is the
6:39:526 hours, 39 minutes, 52 secondsin-memory uh map in which we track if there is an active resume in progress.
6:39:586 hours, 39 minutes, 58 secondsSo if active resume session ids has a session id let's return the error session already has an active resume
6:40:076 hours, 40 minutes, 7 secondsbecause the use effect fires active resumes. So if it fires twice which can happen uh we are going to be protected
6:40:156 hours, 40 minutes, 15 secondsfrom that. So that's the map which we developed initially. So just after you do a check if the resumed message has a
6:40:236 hours, 40 minutes, 23 secondsproper chat model also do a check if active resume session already has this session ID. It means that we are already
6:40:316 hours, 40 minutes, 31 secondsstreaming in progress. So we don't want that to happen twice.
6:40:376 hours, 40 minutes, 37 secondsAnd if it successfully passes this if check, it means that there wasn't any resume in progress and we can successfully add that resume to in
6:40:456 hours, 40 minutes, 45 secondsprogress. So the next time uh it knows exactly what to happen. Now let's go ahead and wrap our return try streams
6:40:546 hours, 40 minutes, 54 secondsinside of try and catch. Let me just find the last one here. Here it is.
6:41:006 hours, 41 minutesCatch. There we go. Let me go ahead and properly uh indent it here.
6:41:086 hours, 41 minutes, 8 secondsUh and let's see everything we need to change. So stream is okay.
6:41:166 hours, 41 minutes, 16 secondsUh and now what I'm going to do here is I'm going to open try
6:41:226 hours, 41 minutes, 22 secondsand catch here as well. So try catch like that.
6:41:306 hours, 41 minutes, 30 secondsLet's replace last message with resumable message.
6:41:356 hours, 41 minutes, 35 secondsAnd in the finally, actually, yeah, this isn't going to be catch. It's going to be finally.
6:41:426 hours, 41 minutes, 42 secondsLet's go ahead and delete that from our in-memory map. So, basically, this resume has ended in here. Let's see what we have to do.
6:41:546 hours, 41 minutes, 54 secondswe have to delete for the session ID from here as well even if it errors.
6:42:036 hours, 42 minutes, 3 secondsUh the message extraction looks fine.
6:42:066 hours, 42 minutes, 6 secondsThe error event looks fine and we stream sec back. I think all of that is perfectly fine. And let's go ahead and
6:42:146 hours, 42 minutes, 14 secondsjust do catch error here. And in case the error happens, let's also
6:42:216 hours, 42 minutes, 21 secondsmake sure that our in-memory map knows that this session has uh successfully resumed or ended the resume.
6:42:316 hours, 42 minutes, 31 secondsNow that we have updated our uh chat API route, we now have to update our use chat hook. So it supports the same. So,
6:42:406 hours, 42 minutes, 40 secondsI'm going to go inside of CLI source hooks use chat and I'm going to go ahead
6:42:466 hours, 42 minutes, 46 secondsand find my type message. And in here, we have to extend it
6:42:546 hours, 42 minutes, 54 secondsthe last part, the assistant part, sorry. So, not the last part, the assistant part with an optional interrupted boolean part.
6:43:046 hours, 43 minutes, 4 secondsAnd then let's go ahead and find active stream type. And let's do the same thing here. interrupted captured boolean.
6:43:136 hours, 43 minutes, 13 secondsNow let's go ahead and let's see what we have here. Uh submit params. Let's go inside of use chat.
6:43:236 hours, 43 minutes, 23 secondsWe have emit parts here. Uh yeah, let's go ahead and do it here.
6:43:316 hours, 43 minutes, 31 secondsSo I'm going to go ahead and develop a new function called capture interrupted message.
6:43:386 hours, 43 minutes, 38 secondsLet's go ahead and prepare this callback.
6:43:436 hours, 43 minutes, 43 secondsAnd in its parameters, it's going to have a single one, active
6:43:526 hours, 43 minutes, 52 secondsstream, which is a type of active stream. The first thing we're going to do is we are going to check if active
6:44:016 hours, 44 minutes, 1 secondstream has interrupted captured or if active stream parts are zero. And let me just Yeah. Whoops.
6:44:146 hours, 44 minutes, 14 secondsI messed this up. I don't like doing returns like this. I like to explicitly open the clause.
6:44:236 hours, 44 minutes, 23 secondsAnd then I'm just gonna collapse this.
6:44:256 hours, 44 minutes, 25 secondsThere we go. Basically, so if the active stream is already being captured or if active stream parts are zero, let's go ahead and do an early return.
6:44:376 hours, 44 minutes, 37 secondsNow, let's go ahead and set it to true, meaning that it wasn't the first scenario, but now it will be.
6:44:456 hours, 44 minutes, 45 secondsLet's go ahead and shallow copy the parts. Let's generate the full text by
6:44:526 hours, 44 minutes, 52 secondsfiltering the types of text, mapping them together, and then joining. And let's then go ahead and do an optimistic
6:45:006 hours, 45 minutesupdate using update messages, preserving the previous messages and appending the new one with the role of assistant and
6:45:076 hours, 45 minutes, 7 secondssimply uh marking it as interrupted. So we are storing it just as we would uh if the message was successful. I think we have an example somewhere down here.
6:45:176 hours, 45 minutes, 17 secondsHere it is. So this is like a successful message but in this case it was interrupted. So uh we store it in the same way. Here it is. This is what we
6:45:266 hours, 45 minutes, 26 secondsjust added. The only thing we don't do here is we don't do duration.
6:45:326 hours, 45 minutes, 32 secondsNow let's go ahead and uh find let me see where this is
6:45:416 hours, 45 minutes, 41 secondsdown here. We have active stream which seems to be erroring property interrupted captured is missing. So yes,
6:45:506 hours, 45 minutes, 50 secondsinside of here we have to add interrupted captured and set it to false initially.
6:45:586 hours, 45 minutes, 58 secondsGreat. Uh we have that. And now after we do this,
6:46:046 hours, 46 minutes, 4 secondslet's go ahead and add one more call back here.
6:46:136 hours, 46 minutes, 13 secondsAnd in this callback, we are going to add the ability to stop an active stream. It's going to take a single prop capture partial, which is a boolean.
6:46:246 hours, 46 minutes, 24 secondsIt will first attempt to find an active stream. If there is no active stream, let's go ahead and return. If capture
6:46:326 hours, 46 minutes, 32 secondspartial has been set to true, we're going to call capture interrupted message function, which is going to uh
6:46:396 hours, 46 minutes, 39 secondsthen add it to our optimistic update state.
6:46:466 hours, 46 minutes, 46 secondsAnd then let's go ahead and set the active stream back to null because we just interrupted this one. Let's set the streaming state to idle. And let's go
6:46:566 hours, 46 minutes, 56 secondsahead and call active stream controller abort. And let's pass along the capture interrupted message in the dependency array.
6:47:056 hours, 47 minutes, 5 secondsAnd just a few more things we have to do. Let's go ahead and find the submit method. Now here it is the submit method. Uh and in here before we define the user message.
6:47:196 hours, 47 minutes, 19 secondsLet's go ahead and make sure that we show partial answer before sending the next message. So just set the stop
6:47:286 hours, 47 minutes, 28 secondsactive stream and set it to true. So we persist the message that we just submitted. And now we also have to add this to the dependency array here.
6:47:416 hours, 47 minutes, 41 secondsGreat. Now let's go inside of the abort here. And we're going to have to modify uh this a bit. Actually it's it's much
6:47:506 hours, 47 minutes, 50 secondssimpler now. Uh okay. It's easier if I just clear everything here. So, we're going to start by calling stop active
6:47:596 hours, 47 minutes, 59 secondsstream like that and simply add that to the dependency
6:48:066 hours, 48 minutes, 6 secondsarray. And then we need one more function which is super simple interrupt function which stops the active stream
6:48:136 hours, 48 minutes, 13 secondsbut set sets this to true. Basically, we are distinguishing between wanting to persist a interrupted message or not
6:48:216 hours, 48 minutes, 21 secondspersisting an interrupted message. And let's go ahead and make sure we export the new interrupt.
6:48:296 hours, 48 minutes, 29 secondsGreat. So, those are all the changes that we need to do uh with use chat.
6:48:356 hours, 48 minutes, 35 secondsNow, uh let's go ahead and go inside of our session shell. So inside of packages CLI source
6:48:446 hours, 48 minutes, 44 secondscomponents uh let me find the session shell component we are simply going to extend it by expecting interruptible.
6:48:556 hours, 48 minutes, 55 secondsBasically this will um this will decide whether we are going to show an
6:49:026 hours, 49 minutes, 2 secondsindicator to the user that user is able to interrupt something. So let's go ahead and find the loading spinner here
6:49:106 hours, 49 minutes, 10 secondsand let's extend this by not just displaying the spinner but displaying a fragment with both spinner and if
6:49:176 hours, 49 minutes, 17 secondsinterruptible a text escape to interrupt so the user knows that they can do that.
6:49:246 hours, 49 minutes, 24 secondsOkay. Uh now let's go back inside of the bot message
6:49:306 hours, 49 minutes, 30 secondsand in here we have to maintain the UI if this was interrupted. So, let's add interrupted.
6:49:396 hours, 49 minutes, 39 secondsLet's go ahead and add interrupted here and make it false by default.
6:49:476 hours, 49 minutes, 47 secondsAnd let's see what we should do now here. Um
6:49:576 hours, 49 minutes, 57 secondsso besides maintaining uh the color of this little bullet point for plan mode or build mode uh we also have to
6:50:066 hours, 50 minutes, 6 secondsmaintain it now if it's been interrupted.
6:50:096 hours, 50 minutes, 9 secondsSo we're going to go ahead and do do it the following way.
6:50:156 hours, 50 minutes, 15 secondsWe're going to render a text. It's going to have attributes and if it's been interrupted we're going to use text attributes dim. Otherwise, set it to
6:50:226 hours, 50 minutes, 22 secondszero. And the foreground is also going to check if it's been interrupted. Then it's going to fall back to undefined.
6:50:286 hours, 50 minutes, 28 secondsOtherwise, it's going to check if the mode is plan and then use colors plan mode. Otherwise, fall back to colors primary. So, basically a combination of
6:50:366 hours, 50 minutes, 36 secondswhat we had before. Uh, now inside of here where we have the mode plan build, we have to kind of do a similar thing.
6:50:506 hours, 50 minutes, 50 secondsSo it's exactly the same in here, but what's different is that we add attributes and make it dimmed if it was
6:50:576 hours, 50 minutes, 57 secondsinterrupted. So basically just working on some indicators so the user knows this was interrupted. Now down here
6:51:046 hours, 51 minutes, 4 secondslet's go ahead and extend this not only for duration but if duration happened uh
6:51:116 hours, 51 minutes, 11 secondsif duration exists if it's greater than zero and if it's been interrupted in that case uh so if if any of those two
6:51:186 hours, 51 minutes, 18 secondsare true then let's go ahead and open this and then what we're going to do is we're going to decide what to show. So
6:51:286 hours, 51 minutes, 28 secondsif it's been interrupted, we're going to show the text interrupted. Otherwise, we're going to render the duration.
6:51:356 hours, 51 minutes, 35 secondsAnd I believe there is just one more file that we have to modify before we are done.
6:51:426 hours, 51 minutes, 42 secondsAnd that is the session itself. So CLI source screens session.
6:51:496 hours, 51 minutes, 49 secondsSo let's go ahead and just import use keyboard from open toy react.
6:51:556 hours, 51 minutes, 55 secondsThen let's go ahead and import message status from night code database enums and let's go ahead and import use
6:52:046 hours, 52 minutes, 4 secondskeyboard layer so that we can uh properly decide who owns the keyboard.
6:52:106 hours, 52 minutes, 10 secondsSo let's go ahead and find the map database messages function here and I believe somewhere here uh we are missing the interrupted state.
6:52:236 hours, 52 minutes, 23 secondsSo it's going to be interrupted if message status is message status interrupted. So we have to maintain that in the UI view as well. Let's go ahead
6:52:326 hours, 52 minutes, 32 secondsand find chat message here and let's go ahead and find uh bot message and let's go ahead and keep track of the
6:52:416 hours, 52 minutes, 41 secondsinterrupted state as well. Now let's actually implement the hotkey which will cancel the message while it's streaming.
6:52:526 hours, 52 minutes, 52 secondsSo, uh, I'm going to go ahead and add is top layer from use keyboard layer. I'm
6:52:586 hours, 52 minutes, 58 secondsgoing to go ahead and extract interrupt from use chat which we just
6:53:056 hours, 53 minutes, 5 secondsadded. And then after my use effect here, I am going to go ahead and let the user cancel a reply even before the first stream chunk arrives.
6:53:176 hours, 53 minutes, 17 secondsSo use keyboard looks for escape. Checks if top layer is base. So if you don't have any models or command dialogues. So
6:53:246 hours, 53 minutes, 24 secondsonly if it's at the the base layer and hits escape then we are going to call interrupt. But also only if it's
6:53:336 hours, 53 minutes, 33 secondsstreaming otherwise we have nothing to interrupt.
6:53:366 hours, 53 minutes, 36 secondsUh perfect. And then at the bottom here, besides loading in the session shell, let's also keep track
6:53:456 hours, 53 minutes, 45 secondsif the session shell itself is interruptible by passing along the streaming status. And I believe those are all the changes that we have to do.
6:53:556 hours, 53 minutes, 55 secondsLet's go ahead. Moment of truth. Write me a long message.
6:54:026 hours, 54 minutes, 2 secondsAnd then when it's once it starts, I'm going to hit escape.
6:54:076 hours, 54 minutes, 7 secondsAnd just like that, we are able to interrupt it. Uh, and let me go ahead and do what were we talking about.
6:54:166 hours, 54 minutes, 16 secondsLet's see if it has any persistence. Again, this will depend on the model.
6:54:226 hours, 54 minutes, 22 secondsUh, and you can see it understands. You asked me to write a long message. I had just begun writing before you followed
6:54:296 hours, 54 minutes, 29 secondsup with this question. Perfect. So, the interruption works. Uh the messages are being persisted in the database and uh
6:54:396 hours, 54 minutes, 39 secondsuh yeah it works. Uh you can see the UI is grayed out. You can see how it looks when it's complete. Brilliant. Truly
6:54:486 hours, 54 minutes, 48 secondsamazing work. Really really really amazing work. Um I believe we it looks like we have some unused variables here.
6:54:576 hours, 54 minutes, 57 secondsI'll see what's up with that. Uh but we've done uh so so much work here.
6:55:036 hours, 55 minutes, 3 secondsUh there's just one more thing I want to do now. Uh, I want to go inside of my
6:55:136 hours, 55 minutes, 13 secondswhere is sorry inside of my server source package JSON and in here I want
6:55:206 hours, 55 minutes, 20 secondsto add a build script so that we can start having proper CI/CD which is going to be super simple don't worry uh so
6:55:286 hours, 55 minutes, 28 secondsthat we can start getting close to production instance rather than just a development instance.
6:55:356 hours, 55 minutes, 35 secondsSo the build script is going to look like this. Bun build source index.ts out
6:55:436 hours, 55 minutes, 43 secondsdeer dist target bun. But we also need a post install script because we're using Prisma. So let's add post install bun run. Let's change directory to database.
6:55:566 hours, 55 minutes, 56 secondsSo it's going to find the directory database and call database generate. Uh though I think do we have that? we do
6:56:056 hours, 56 minutes, 5 secondsdatabase generate. So just make sure you have that script in here. Great. And uh that is all we need right now. So let's leave it at that.
6:56:166 hours, 56 minutes, 16 secondsAnd let's go ahead and get checkout B05.
6:56:226 hours, 56 minutes, 22 secondsThis is AI chat streaming. Okay.
6:56:296 hours, 56 minutes, 29 secondsGit add commit05 AI chat streaming get push U origin 05
6:56:386 hours, 56 minutes, 38 secondsAI chat streaming. Brilliant. Let's go ahead and open a pull request now and let's review it.
6:56:526 hours, 56 minutes, 52 secondsHere we have the summary. We added streaming chat responses with real-time messages, ability to interrupt in
6:56:596 hours, 56 minutes, 59 secondsprogress, support multiple providers, enhanced messages display showing model mode generation, duration, and
6:57:066 hours, 57 minutes, 6 secondsinterruption status, and we added API configuration for anthropic and open AI providers. Uh, and we only have two
6:57:146 hours, 57 minutes, 14 secondscomments, which is great considering the amount of work we did, meaning not a lot of bugs were introduced. Uh in here uh
6:57:226 hours, 57 minutes, 22 secondswe have a minor issue again a missing dependency in use call back. I should probably add update messages here. But
6:57:306 hours, 57 minutes, 30 secondsthe good news is that update messages is pretty stable. It has empty dependency array. But still I don't like the fact
6:57:376 hours, 57 minutes, 37 secondsthat uh we have a missing one. So let's go instead of use chat. Uh let's go ahead and find interrupted message.
6:57:486 hours, 57 minutes, 48 secondsCapture interrupted message.
6:57:506 hours, 57 minutes, 50 secondsAnd let's simply add updated messages to the dependency array here.
6:57:586 hours, 57 minutes, 58 secondsLet me see if that's the fix. It is. And in here, uh, it says not to use non-null assertion on the response body. Um,
6:58:086 hours, 58 minutes, 8 secondswhich is typically safe after checking response.
6:58:116 hours, 58 minutes, 11 secondsSo yeah, that's kind of why we are doing it. So I'm just going to leave it as is.
6:58:166 hours, 58 minutes, 16 secondsYeah, I mean if you we could technically do this, but it's okay for for our use case. It's completely okay. So, I'm just
6:58:246 hours, 58 minutes, 24 secondsgoing to go ahead and commit a fix for the updated messages here. So, get add get commit
6:58:326 hours, 58 minutes, 32 secondsuh incorrect. So, this is 05 AI what's the name of the chapter? AI
6:58:396 hours, 58 minutes, 39 secondschat streaming fix get push. And this time I can just do get push because I had a d- u flag.
6:58:516 hours, 58 minutes, 51 secondsOtherwise you have to set upstream to push. Uh if you have the error it will tell you exactly what you have to do or you can look at the previous chapter
6:58:586 hours, 58 minutes, 58 secondswhere I had the error with git push and how I resolved it. Uh great and that will definitely fix our issue. So let's
6:59:066 hours, 59 minutes, 6 secondsgo ahead and merge the pull request and let's go ahead and do one important thing. So, we currently don't have CI/CD
6:59:146 hours, 59 minutes, 14 secondsin place. Let's go ahead and head to Railway and let's add our current
6:59:216 hours, 59 minutes, 21 secondsproject uh inside of here using the link on the screen. By the way, you can get $20 in free credits. So, let's just go
6:59:286 hours, 59 minutes, 28 secondsahead and open a new app, GitHub repository. And I'm going to go ahead and select night code here. And it will
6:59:366 hours, 59 minutes, 36 secondsimmediately recognize that it's a monor repo and it's going to add all of them here. So, what I suggest is that we go inside of the server one and we focus on
6:59:446 hours, 59 minutes, 44 secondsthe variables. Let's click on uh raw editor here and let's copy everything that's inside
6:59:526 hours, 59 minutes, 52 secondsof environment. So, I'm just going to copy all of that and paste it here. Uh except the API URL. Technically, API URL
7:00:017 hours, 1 secondcan be replaced with whatever is the production instance. But I'm not sure API URL is even used anywhere in the
7:00:077 hours, 7 secondsserver. So I think if I search in the server package, yeah, it's not used here. So it doesn't matter. We can leave
7:00:157 hours, 15 secondsit anyway. So make sure you add uh those. Uh and technically you don't need CLI here. You don't need database here.
7:00:267 hours, 26 secondsBoth are going to fail. But let's just go ahead and hit deploy so you can see how that happens. Basically, we added a
7:00:347 hours, 34 secondsbuild script for Night Code server, but our Night Code CLI is not properly aligned to be built and our Night Code
7:00:437 hours, 43 secondsdatabase isn't even intended to be built, right? So, it's completely normal for these two to fail, but this one uh
7:00:517 hours, 51 secondsis what we want to succeed. uh you don't need to do this to complete the project but if you are planning on going to
7:00:597 hours, 59 secondsproduction you will need your app hosted somewhere and what I want you to show is how easy it is to do it with railway uh
7:01:077 hours, 1 minute, 7 secondsand how easy it is to actually add CI/CD with railway as well. So while this is
7:01:157 hours, 1 minute, 15 secondsbuilding here, let me go inside of project settings. Let me go inside of environments here. And one cool thing
7:01:237 hours, 1 minute, 23 secondsyou can do is you can enable PR environments. And once you do that and select the production as the base environment, it will automatically
7:01:327 hours, 1 minute, 32 secondscreate a preview every time you open a pool request. So we're going to see that active in the next one. Just make sure you select production as the base
7:01:417 hours, 1 minute, 41 secondsenvironment. Cool. So let's go back to our architecture. This failed as expected but we are focusing on the night code server here now.
7:01:537 hours, 1 minute, 53 secondsAnd there we go. Deployment has been successful. Meaning our scripts are all working. And now what we have to do is
7:02:007 hours, 2 minuteswe have to go inside of settings networking and we have to click generate domain. Uh
7:02:077 hours, 2 minutes, 7 secondslet's see it automatically found port 3000. So, if you didn't have the generate a domain button, you probably
7:02:167 hours, 2 minutes, 16 secondshad to enter the port. So, the port is 30,000. And then you can copy this and you can go ahead and try adding it. And
7:02:237 hours, 2 minutes, 23 secondsyou will see 404 not found. But if you try and go to forward slash sessions for example, uh or which one is it? Is it API sessions?
7:02:357 hours, 2 minutes, 35 secondsLet me go ahead and and find a route that works.
7:02:407 hours, 2 minutes, 40 secondsYeah, it was sessions. It just didn't load the first time. And you can see that now in production, we can see all
7:02:477 hours, 2 minutes, 47 secondsof our routes. Uh my apologies, all of our sessions. So, we have successfully deployed our server on railway now. And
7:02:567 hours, 2 minutes, 56 secondsyou can actually get rid of these other services like CLI. This can come in handy later. For example, you can
7:03:037 hours, 3 minutes, 3 secondsconnect this with uh homebrew or something and then it will automatically uh create a binary for your CLI app.
7:03:137 hours, 3 minutes, 13 secondsBut for now, it's just taking up space.
7:03:167 hours, 3 minutes, 16 secondsSo, I'm going to remove uh CLI and database from here. I'm going to type in this to confirm. And that will just
7:03:247 hours, 3 minutes, 24 secondsdelete those two because we only need the server one anyway. Beautiful. So, it was that easy to do. And from now on any
7:03:327 hours, 3 minutes, 32 secondssubsequent pull requests that we open are automatically going to be generated in its own instance uh using the
7:03:407 hours, 3 minutes, 40 secondsenvironment keys from the production instance that we have added here. So you will be able to test every single time
7:03:477 hours, 3 minutes, 47 secondsif it's working or not. Brilliant. So that marks the end of this chapter. We have a working interruption, working
7:03:547 hours, 3 minutes, 54 secondsstreaming. Uh we even have the build script and we added CI/CD. So many things we did in this chapter. Amazing, amazing job and see you in the next one.
7:04:067 hours, 4 minutes, 6 secondsOne thing we forgot to do is switch back to our main branch
7:04:127 hours, 4 minutes, 12 secondsand get pull origin main. So this way we are completely synchronized with our
7:04:197 hours, 4 minutes, 19 secondsmain branch. In this chapter, we're going to add session management and prompt configuration to our project. In
Chapter 9: Session Management
7:04:277 hours, 4 minutes, 27 secondsstep one, we're going to implement session management by creating a session dialogue which is going to use our
7:04:347 hours, 4 minutes, 34 secondsexisting dialogue search list component which is filterable and navigation is working through both keyboard and your
7:04:427 hours, 4 minutes, 42 secondscursor and that component is going to call our existing API sessions route. So
7:04:497 hours, 4 minutes, 49 secondswe are not going to have to implement anything on the back end. This will be quite a simple implementation. And once the user selects one of the existing
7:04:587 hours, 4 minutes, 58 secondssessions, we are simply going to navigate to that session. We're going to add a package called date FNS. So we can
7:05:067 hours, 5 minutes, 6 secondsuh nicely format timestamps for each of the sessions. And we are going to enable a command called new to simply uh
7:05:157 hours, 5 minutes, 15 secondsredirect back to the homepage. That's going to be step one. And step two is going to be prompt config. We're going to implement a prompt config provider
7:05:247 hours, 5 minutes, 24 secondswhich is going to maintain mode and model that the user chooses. Mode can either be build or plan and it can be
7:05:337 hours, 5 minutes, 33 secondsswitched using the tab key or by using the agents dialogue. Model can be whatever you yourself define as a
7:05:417 hours, 5 minutes, 41 secondssupported model. We used Oppus, Sonnet, GPT models, but you can of course add Google models, Grock models, whatever
7:05:487 hours, 5 minutes, 48 secondsyou prefer and they can be uh changed using the models dialogue. Both model and mode will be wired up to the status
7:05:577 hours, 5 minutes, 57 secondsbar so that they show the relevant information. Now, I'm going to show you exactly how that looks like. So, this is what we're going to have by the end of
7:06:047 hours, 6 minutes, 4 secondsthis chapter. Using the tab key, you can switch the mode and if you manually type in agents, you will be able to switch
7:06:117 hours, 6 minutes, 11 secondsthat as well. And for the models, you will be able to change them here.
7:06:197 hours, 6 minutes, 19 secondsLet's go ahead and implement that.
7:06:227 hours, 6 minutes, 22 secondsThe first thing we are going to do is we're going to go inside of our CLI package. So, make sure you are inside and we're going to add date FNS.
7:06:327 hours, 6 minutes, 32 secondsThis is the version that I'm using. And I'm just going to confirm that I did this correctly by looking at my code
7:06:397 hours, 6 minutes, 39 secondshere. And as you can see inside of my packages CLI package JSON, I have date FNS added to my dependencies. Great. Now
7:06:487 hours, 6 minutes, 48 secondswe're going to go ahead and implement the dialogue component that we need. So uh this is going to be called sessions
7:06:577 hours, 6 minutes, 57 secondsdialogue. Let's go inside of packages CLI source components dialogues. In here, I'm going to add sessions dialogue.tsx.
7:07:087 hours, 7 minutes, 8 secondsLet's go ahead and add uh all the imports that we're going to need. So use callback, use effect and use state from
7:07:167 hours, 7 minutes, 16 secondsReact text attributes from open 2E core format from our newly installed package.
7:07:217 hours, 7 minutes, 21 secondsUse navigate from React router and then from the providers we're going to need use dialogue from dialogue providers.
7:07:277 hours, 7 minutes, 27 secondsUse toast from toast provider API client from our library, get error message from our library and dialogue search list from our dialogue search list component.
7:07:387 hours, 7 minutes, 38 secondsLet's go ahead and create a type for the session here. ID, title, and created at.
7:07:437 hours, 7 minutes, 43 secondsAnd let's go ahead and export this content here.
7:07:487 hours, 7 minutes, 48 secondsSo, I'm going to go ahead now and create a state to maintain my sessions that I load. The reason I'm uh typing the type
7:07:577 hours, 7 minutes, 57 secondshere manually uh instead of infering it uh is because it's a specific type. As you can see in my routes here, when we
7:08:057 hours, 8 minutes, 5 secondsdo get, we only select ID, title, and created at. Uh, so this is like a quick way of doing it. If you want to, you
7:08:127 hours, 8 minutes, 12 secondscould use uh infer I think I we do this in CLI. Yeah, you could technically do
7:08:207 hours, 8 minutes, 20 secondsthis infer response type for example. You could do that. I just want to show you.
7:08:307 hours, 8 minutes, 30 secondsYou could import this Uh API client sessions ID get and huh is that really it?
7:08:437 hours, 8 minutes, 43 secondsOh yeah, not that one. not get by ID just get
7:08:527 hours, 8 minutes, 52 secondsand then you will have to specify I think like a number and then that would be session.
7:09:027 hours, 9 minutes, 2 secondsSo yeah technically you could do this as well. This is like strictly uh strictly inferring that. And let me just check in here. We import this from hono client.
7:09:147 hours, 9 minutes, 14 secondsIn here we imported from hono. I guess it's better if we use hono client. I think three shaking works uh better that
7:09:217 hours, 9 minutes, 21 secondsway. But yeah, basically whatever one you prefer. If you want to infer it, which is technically more correct, we
7:09:287 hours, 9 minutes, 28 secondscould do that. And then the state is exactly the same as if it would be if we manually typed it.
7:09:367 hours, 9 minutes, 36 secondsThen let's go ahead and add uh loading.
7:09:417 hours, 9 minutes, 41 secondsAnd then let's go ahead and add the ability to close the dialogue. And finally, let's add two more, the
7:09:487 hours, 9 minutes, 48 secondsnavigate and show for toast. Now we have to open up the use effect, which we're going to use to fetch all of our
7:09:577 hours, 9 minutes, 57 secondssessions. So inside of this use effect first things first let's go ahead and maintain the ignore constant I mean let which we can use in case of an unmount.
7:10:087 hours, 10 minutes, 8 secondsSo when it unmounts it's going to turn it to true and then we can break the uh API call early if that happens.
7:10:187 hours, 10 minutes, 18 secondsSo let's develop the asynchronous fetch sessions function.
7:10:257 hours, 10 minutes, 25 secondsis going to have a try and catch method.
7:10:287 hours, 10 minutes, 28 secondsIn the try method, we're going to use the API client to call sessions.get, which is exactly what we are inferring here.
7:10:377 hours, 10 minutes, 37 secondsAnd if the response is not okay, we're going to go ahead and throw an error and standardize it. Otherwise, if it is
7:10:457 hours, 10 minutes, 45 secondsokay, let's go ahead and destructure the data. And if not ignore, let's go ahead and assign that data to the state and
7:10:547 hours, 10 minutes, 54 secondsset the loading back to false. So we have to be careful to not do any set states if we have already unmounted as
7:11:027 hours, 11 minutes, 2 secondsthat is going to cause an error in React. Let's go ahead and handle the error now. So again, it only makes sense
7:11:107 hours, 11 minutes, 10 secondsto do this if not ignored. And what we're going to do is just go ahead and show a variant of error and a message
7:11:177 hours, 11 minutes, 17 secondsand close the dialogue. And we must not forget to actually fetch sessions like this. In the
7:11:267 hours, 11 minutes, 26 secondsdependency array, we're going to go ahead and put close and show. Because of that is why we destructured it. Because
7:11:347 hours, 11 minutes, 34 secondsusually we do dialogue and then we do dialogue.close. But since we have to put it in the dependency array, we destructured it. And just like that, we
7:11:437 hours, 11 minutes, 43 secondscan fetch our sessions. Let's go ahead and create a handle select function which is going to close the dialogue and
7:11:507 hours, 11 minutes, 50 secondsnavigate to sessions session ID. It's going to navigate here because we defined that route instead of CLI
7:11:587 hours, 11 minutes, 58 secondssource. Uh I think it's index right here. Here it is. Sessions ID. So make sure you don't misspell that. Great.
7:12:077 hours, 12 minutes, 7 secondsLet's go ahead and add a very primitive loading state which will simply in dim text say loading sessions.
7:12:167 hours, 12 minutes, 16 secondsAnd finally, let's go ahead and render our dialogue search list.
7:12:237 hours, 12 minutes, 23 secondsOur dialogue search list is going to have the following attributes.
7:12:317 hours, 12 minutes, 31 secondsWe're going to add items. We're going to add on select. We're going to add a filter function to query by the title of
7:12:397 hours, 12 minutes, 39 secondseach session. And then we're going to add the uh render item function which is going to render a fragment. And within
7:12:487 hours, 12 minutes, 48 secondsthat fragment, we're going to render the session title. If it is selected, it's going to be black. Otherwise, it's going
7:12:557 hours, 12 minutes, 55 secondsto be white. We are then going to make a purpose uh a purposeful purposeful empty box which simply used for spacing. And
7:13:047 hours, 13 minutes, 4 secondsthen we're going to uh render the timestamp when that session was created again with dynamic selection of the
7:13:147 hours, 13 minutes, 14 secondsforeground color and some attributes here. And we are using date FNS format to uh format this date.
7:13:227 hours, 13 minutes, 22 secondsAnd we need three more attributes here.
7:13:267 hours, 13 minutes, 26 secondsGet key so we know which is the unique key of our data. Placeholder and empty text. And it's actually a self-closing tag. So we can remove everything else.
7:13:387 hours, 13 minutes, 38 secondsAnd that is it. That is our entire dialogue. Not that difficult to implement. Now let's go ahead inside of
7:13:467 hours, 13 minutes, 46 secondsthe dialogues index. DSX. And let's go ahead and do a barrel export here.
7:13:517 hours, 13 minutes, 51 secondsSessions dialogue content sessions dialogue. Like that. Now that
7:14:007 hours, 14 minuteswe have that, we can go ahead inside of our source components command menu commands.tsx.
7:14:107 hours, 14 minutes, 10 secondsWe can copy the action from our theme action. And we can find our sessions.
7:14:157 hours, 14 minutes, 15 secondsAnd let's replace this action. And let's go ahead and change the title here to be sessions. And let's use sessions
7:14:257 hours, 14 minutes, 25 secondsdialogue content which we can now import from the same place as theme dialogue content. And just with those two changes
7:14:337 hours, 14 minutes, 33 secondsif I run bundde dev server and bun rundev cli
7:14:417 hours, 14 minutes, 41 secondslet me go to the root and if I run models my apologies sessions I should be able to load all of my
7:14:507 hours, 14 minutes, 50 secondssessions. Let me go ahead and try and pick one and let's see what happens here. Uh you can see that it auto
7:14:577 hours, 14 minutes, 57 secondsresumed. That could be because uh it's one of the older ones that we have. Let me try one of the newer ones like write
7:15:057 hours, 15 minutes, 5 secondsme a long message. You can see that we exactly have all of my uh interrupted messages and when I asked it what were
7:15:147 hours, 15 minutes, 14 secondswe talking about to prove that it had the context. So we are successfully proving once again our previous branch
7:15:217 hours, 15 minutes, 21 secondsis working correctly. And if you try any of your older ones, it will most likely uh automatically start to respond
7:15:307 hours, 15 minutes, 30 secondssomething simply because it assumes it's waiting for an answer. That's our autores functionality. So before we had
7:15:387 hours, 15 minutes, 38 secondsthe streaming functionality, we just store the user messages in the database.
7:15:427 hours, 15 minutes, 42 secondsSo if we revisit those sessions, they're going to automatically start streaming back to us. So just like that, we
7:15:497 hours, 15 minutes, 49 secondsfinished uh step one. Let's just not forget to add the new uh command here.
7:15:577 hours, 15 minutes, 57 secondsSo in order to do that uh we actually have to do the following. We have to go
7:16:047 hours, 16 minutes, 4 secondsinside of command types here. And besides exit toast and dialogue, we need
7:16:117 hours, 16 minutes, 11 secondsnavigate which is a function which accepts a string and returns a void.
7:16:217 hours, 16 minutes, 21 secondsAnd once we have that, we can go back inside of the commands find new and inside of this action, let's simply do
7:16:297 hours, 16 minutes, 29 secondscontext.n. [snorts] And let's go ahead and navigate to the root like that. Uh we are not done just
7:16:387 hours, 16 minutes, 38 secondsyet because we have to go inside of the input bar right here and we have to
7:16:467 hours, 16 minutes, 46 secondsprovide navigate here. The problem is we don't yet have navigate. So let's make
7:16:527 hours, 16 minutes, 52 secondssure we first add the proper import. Use navigate from react router like that.
7:17:007 hours, 17 minutesAnd then let's go ahead and let's just render it somewhere
7:17:087 hours, 17 minutes, 8 secondsjust like that. And let's not forget to add it to our dependency array. So renderer toast dialogue
7:17:167 hours, 17 minutes, 16 secondswe are talking about handle command function where we just added navigate and let's add navigate to the dependency array.
7:17:267 hours, 17 minutes, 26 secondsAnd just like that that should be completely finished. So if I now go into one of my sessions here. Perfect. And if I type new, back to home screen.
7:17:377 hours, 17 minutes, 37 secondsBeautiful. That is step one finished. And now we have to go to step two.
7:17:447 hours, 17 minutes, 44 secondsIn order to implement the prompt config, we have to create the provider. So let's go inside of CLI source providers. And
7:17:537 hours, 17 minutes, 53 secondsin here, let's go ahead and create a new folder, which we are going to call prompt config.
7:18:017 hours, 18 minutes, 1 secondInside of the prompt config, let's go ahead and create an index.tsx.
7:18:067 hours, 18 minutes, 6 secondsI'm going to go ahead and add all of the imports that we are going to use. That's going to be uh create context
7:18:147 hours, 18 minutes, 14 secondsuse context use state use callback react node type default chat model ID and the type supported chat model ID from night
7:18:227 hours, 18 minutes, 22 secondscode shared and finally mode from night code database enumes let's go ahead and define the type for this provider so
7:18:307 hours, 18 minutes, 30 secondswhat's the value of it will maintain the current mode the option to toggle a mode the option to set the mode it will
7:18:387 hours, 18 minutes, 38 secondsmaintain the model which is a type of supported chat model ID and it will have a function to set the model. Now let's go ahead and create this context.
7:18:487 hours, 18 minutes, 48 secondsThen let's go ahead and create the use prompt config hook which is going to take care of uh making sure that this
7:18:577 hours, 18 minutes, 57 secondshook is called within a prompt config provider and it needs to return the value. Very important. And now let's go
7:19:057 hours, 19 minutes, 5 secondsahead and define the type for the actual provider which is just the children.
7:19:107 hours, 19 minutes, 10 secondsWe've done this a couple of times already. They all follow the same practices here. And in here we're going
7:19:177 hours, 19 minutes, 17 secondsto m maintain two states. First one is mode. Second one is model. The the default mode is going to be build and
7:19:247 hours, 19 minutes, 24 secondsthe default model will be whatever we have defined in our shared package which for me is claude oppus 46. You can commandclick here and change it to one
7:19:337 hours, 19 minutes, 33 secondsof the other supported model ids. Once we have those states, let's go ahead and create a memorized toggle mode function.
7:19:437 hours, 19 minutes, 43 secondsSo if the existing mode is build, the toggle will switch to plan and vice versa.
7:19:497 hours, 19 minutes, 49 secondsAnd finally, let's go ahead and return our prompt config context provider and
7:19:577 hours, 19 minutes, 57 secondspass along the value which has mode toggle mode set mode model and set model
7:20:057 hours, 20 minutes, 5 secondsand encapsulates the children. Great. So that is our provider. Now we have to go
7:20:147 hours, 20 minutes, 14 secondsinside of index. Uh actually not inside of index inside of layouts root layout
7:20:217 hours, 20 minutes, 21 secondsand in here uh around theme the root let's add prompt config provider
7:20:307 hours, 20 minutes, 30 secondsthe order does matter so make sure that you do it in the correct place so prompt
7:20:377 hours, 20 minutes, 37 secondsconfig provider great now let's go ahead and modify our status bar so that it is connected uh to that instead of being hardcoded.
7:20:497 hours, 20 minutes, 49 secondsSo this is the status bar. Currently it's hardcoded. So now let's connect it to that config provider. So inside of CLI source components, let's go ahead
7:20:577 hours, 20 minutes, 57 secondsand find our status bar component. And in here I'm going to import
7:21:057 hours, 21 minutes, 5 secondsuse prompt config and I'm going to extract mode and model from it. Then I'm going to remove the hard-coded build
7:21:137 hours, 21 minutes, 13 secondstext here and instead I'm going to render the following and we have to import mode from night code database
7:21:217 hours, 21 minutes, 21 secondsenums. So foreground will be different depending on the current mode. So either plan mode or primary and the text will
7:21:297 hours, 21 minutes, 29 secondsbe different depending on the mode either plan or build. And last thing let's go ahead and change the hardcoded text here to render the current model.
7:21:397 hours, 21 minutes, 39 secondsJust like that, we can save and right now out on the start, nothing will really be different. It's still going to
7:21:467 hours, 21 minutes, 46 secondslook exactly the same. But go inside of prompt config here and let's go ahead and change the default. How about I
7:21:547 hours, 21 minutes, 54 secondschange this to plan mode? And how about I purposely do test one two three. Even though it's going to throw an error, you will see that that's exactly what gets
7:22:037 hours, 22 minutes, 3 secondsrendered in the status bar. So, we have successfully wired those two together.
7:22:087 hours, 22 minutes, 8 secondsMake sure you revert your changes and save. Perfect. So that is a status bar taken care of.
7:22:157 hours, 22 minutes, 15 secondsSo what I want to do next here uh is the toggle functionality. So for that let's go inside of the input bar.
7:22:267 hours, 22 minutes, 26 secondsAnd I'm going to go ahead and add the following imports here. I'm going to add use prompt config. Uh I'm going to add
7:22:367 hours, 22 minutes, 36 secondsmode from night code database enions and from my open to react I'm just going to
7:22:447 hours, 22 minutes, 44 secondsextend it to also have use keyboard alongside use renderer. So use keyboard use prompt config and mode are the new
7:22:517 hours, 22 minutes, 51 secondsimports that we have added. Uh now let's go ahead and use our new use prompt config hook and let's extract mode toggle mode set mode and set model.
7:23:047 hours, 23 minutes, 4 secondsNow let's go ahead and find our handle command function. And let's extend the command context by passing along the
7:23:137 hours, 23 minutes, 13 secondsmode set mode and set model. And let's go ahead and also
7:23:217 hours, 23 minutes, 21 secondsum add all of those here. Mode set mode set model like that. And let's go ahead and create the toggle function.
7:23:327 hours, 23 minutes, 32 secondsWe can do that. Uh let's see where should we render that. How about here?
7:23:377 hours, 23 minutes, 37 secondsUh before this use effect. It really doesn't matter because this is also somewhat of a use effect which actually
7:23:457 hours, 23 minutes, 45 secondsjust adds the event listeners. So add this use keyboard which uh returns early if disabled returns early if top layer
7:23:547 hours, 23 minutes, 54 secondsis not base and only if key name is tab calls toggle mode from use prompt
7:24:027 hours, 24 minutes, 2 secondsconfig. And just by adding this you will be able to toggle uh hit tab and you can see this changes. You can see a bug here. This is not changing the color.
7:24:147 hours, 24 minutes, 14 secondsLet's go ahead and resolve that. So scrolling down here you can see we have hardcoded it to colors. primary and we
7:24:227 hours, 24 minutes, 22 secondscan very easily fix that by checking if the mode is build then use primary otherwise use plan mode.
7:24:307 hours, 24 minutes, 30 secondsLet's try it again. There we go. It's fixed now. Now, uh let's go ahead and
7:24:377 hours, 24 minutes, 37 secondsadd the proper types to our command context. So for that we have to go
7:24:457 hours, 24 minutes, 45 secondsinside of packages CLI source components command menu types and after navigate
7:24:527 hours, 24 minutes, 52 secondslet's add our mode from database enumes and our supported chat model ID from
7:25:027 hours, 25 minutes, 2 secondsnight code shared and just like that if you visit input bar again you should have no errors in your code because now
7:25:097 hours, 25 minutes, 9 secondsall of those that we have added are supported and even expected.
7:25:157 hours, 25 minutes, 15 secondsGreat. So now what we have to do is we have to build the models dialogue and the agents dialogue. Let's start with
7:25:237 hours, 25 minutes, 23 secondsthe agents dialogue first. So I'm going to go inside of dialogues and I'm going to copy my theme dialogue and paste it.
7:25:307 hours, 25 minutes, 30 secondsAnd I'm going to rename it to agents dialogue. Let's go inside of the agents dialogue.
7:25:387 hours, 25 minutes, 38 secondsAnd let's go ahead and rename it. So agents dialogue content. Let's go ahead and
7:25:467 hours, 25 minutes, 46 secondscreate a type agents dialogue content props. Let's import mode from night code
7:25:537 hours, 25 minutes, 53 secondsdatabase enums. And let's not import the let me see. Yeah, let's not import it as a type. Let's import it like this.
7:26:037 hours, 26 minutes, 3 secondsLet's go ahead and create a little helper get mode label. So if it's plan render plan otherwise render build and
7:26:127 hours, 26 minutes, 12 secondslet's go ahead and add some props here current mode and on select mode
7:26:237 hours, 26 minutes, 23 secondsinside of the actual uh dialogue here. Yeah, I I picked a bit of a complex component. Okay, let's
7:26:327 hours, 26 minutes, 32 secondssimplify it. So we have dialogue. That's good. Uh we don't need theme, we don't need this, we don't need this, we don't
7:26:407 hours, 26 minutes, 40 secondsneed the use effect, we just need handle select. And inside of handle select, we're going to maintain one thing and
7:26:487 hours, 26 minutes, 48 secondsthat is the next mode that we are passing. And what's happening on select is very simple. On select mode,
7:26:567 hours, 26 minutes, 56 secondssomething's very broken here. Let me check. Okay, we choose on select mode into that next mode and we pass along
7:27:047 hours, 27 minutes, 4 secondsthe on select mode into the dev dependencies and we don't need handle highlight at all. So this is a much simpler component than what we had.
7:27:157 hours, 27 minutes, 15 secondsLet's remove the use theme. Let's remove use effect and use ref from react. Let's remove the type theme.
7:27:227 hours, 27 minutes, 22 secondsAll that's left is to fix the rendering in the dialogue search list. So items are going to be available modes
7:27:327 hours, 27 minutes, 32 secondsand we are going to create available modes ourselves. So it's just going to be an array of mode build and mode plan like this.
7:27:437 hours, 27 minutes, 43 secondsSo let's have that on highlight isn't going to be anything.
7:27:497 hours, 27 minutes, 49 secondsUh filter function will be get mode label. Oops. Let's do get mode
7:27:587 hours, 27 minutes, 58 secondslabel and then pass along item and let's use item like this. So that's
7:28:067 hours, 28 minutes, 6 secondshow we're going to do it. Get mode label basically either plan or build lowerase
7:28:127 hours, 28 minutes, 12 secondsit and see if the user's query includes uh that title.
7:28:187 hours, 28 minutes, 18 secondsThe render item will also be much simpler.
7:28:247 hours, 28 minutes, 24 secondsSo, it's just going to be text with a different foreground depending on if it's currently selected or not. We're
7:28:317 hours, 28 minutes, 31 secondsgoing to render a bullet point if the item matches the current mode and we're going to render its label. For the get
7:28:397 hours, 28 minutes, 39 secondskey, there isn't any property other than the name itself. So, we just return that. And let's go ahead and change the
7:28:477 hours, 28 minutes, 47 secondsplaceholder and the empty text search modes. No matching modes. You can also
7:28:547 hours, 28 minutes, 54 secondsdo search agents, no matching agents because they are technically like agents, right? Let's remove the theme
7:29:017 hours, 29 minutes, 1 secondentirely. Uh, and once we have this, now let's go ahead and register it in the index here.
7:29:097 hours, 29 minutes, 9 secondsSo, from our agents dialogue, agents dialogue content like that.
7:29:207 hours, 29 minutes, 20 secondsAnd let's go ahead and go inside of our command menu. commands.dsx.
7:29:277 hours, 29 minutes, 27 secondsUh I'm going to add agents here.
7:29:347 hours, 29 minutes, 34 secondsLet me add a trailing comma here. And I'm going to let me find and let me copy sessions.
7:29:437 hours, 29 minutes, 43 secondsLet me find agents. And let me replace the action here. And in here it will be select agent.
7:29:537 hours, 29 minutes, 53 secondsAnd we are simply going to render agents dialogue content. Oops. And let's go ahead and pass in the current mode.
7:30:037 hours, 30 minutes, 3 secondscontext do mode and on select mode context set mode like that.
7:30:157 hours, 30 minutes, 15 secondsAnd now even if you do agents you can switch it through there.
7:30:227 hours, 30 minutes, 22 secondsNow let's go ahead and do the same for models.
7:30:277 hours, 30 minutes, 27 secondsUh so I'm going to go ahead and close everything here
7:30:337 hours, 30 minutes, 33 secondsand I'm going to copy my agents dialogue and I'm going to
7:30:407 hours, 30 minutes, 40 secondsrename it to be my models dialogue like that.
7:30:457 hours, 30 minutes, 45 secondsAnd in here, let's go ahead and change the type here to be models, which is going to use the supported chat model
7:30:547 hours, 30 minutes, 54 secondsID. So models and on select model. Let's remove the available modes constant. We don't do not need it. Let's remove the
7:31:037 hours, 31 minutes, 3 secondsget model label helper. We don't need that either. Let's rename the function to modus dialogue content. Let's rename the props to modus dialog content props.
7:31:127 hours, 31 minutes, 12 secondsLet's change this to be the current models and on select model like that.
7:31:207 hours, 31 minutes, 20 secondsAnd let's go ahead and change the handle select here to accept model ID which is a type of
7:31:287 hours, 31 minutes, 28 secondssupported chat model ID. Call the on select model and then close the dialogue.
7:31:337 hours, 31 minutes, 33 secondsUh items are very simply going to be models.
7:31:377 hours, 31 minutes, 37 secondsfilter function is going to filter by model ID.
7:31:447 hours, 31 minutes, 44 secondsSo see if users query matches the model ID. Render item will be even simpler.
7:31:517 hours, 31 minutes, 51 secondsWe're not going to maintain which is the currently selected one. We're just going to render all of them like this. So model ID is selected. As simple as that.
7:32:027 hours, 32 minutes, 2 secondsuh get key can technically stay the same, but if you want to be more descriptive, you can call that model ID.
7:32:097 hours, 32 minutes, 9 secondsAnd then we're going to have the placeholder and the empty text here.
7:32:157 hours, 32 minutes, 15 secondsGreat. Uh now that we have that, we also have to register that in the index. So let me just uh copy this modus dialog content from modus dialogue. Perfect.
7:32:277 hours, 32 minutes, 27 secondsUh, and all that's left, I believe, is to map that in the command menu commands here. So, let me go ahead and copy the
7:32:367 hours, 32 minutes, 36 secondsaction of my agents. Go inside of models and replace this action here.
7:32:427 hours, 32 minutes, 42 secondsSo, let's go ahead and see what we have to change. The title here will be select
7:32:497 hours, 32 minutes, 49 secondsmodel and the children are going to render models dialogue
7:32:557 hours, 32 minutes, 55 secondscontent and we're going to import supported chat models from night code shared and we added modus dialogue
7:33:057 hours, 33 minutes, 5 secondscontent from dialogues. So these are the existing available models. And on select model we are calling context set model.
7:33:157 hours, 33 minutes, 15 secondsAll right.
7:33:177 hours, 33 minutes, 17 secondsAnd now if you go ahead and search for a model you can see that it is selected. If I hit tab that gets selected.
7:33:267 hours, 33 minutes, 26 secondsBrilliant. So we now have a way to call uh different models. So, for example, if
7:33:327 hours, 33 minutes, 32 secondsyou try and uh do hello world here, I think this might even fail now. Uh oh,
7:33:417 hours, 33 minutes, 41 secondsyeah, it's still calling claude opus because this isn't really connected. Uh, and let me see.
7:33:507 hours, 33 minutes, 50 secondsI think that there is uh one more thing that we have to do here. I'm not sure if I planned on doing this later or not,
7:33:597 hours, 33 minutes, 59 secondsbut let me just check. First, let me check all of the changes I did. Import mode. Okay.
7:34:077 hours, 34 minutes, 7 secondsUh, I'm thinking about session shell component. Let me find it. Components.
7:34:157 hours, 34 minutes, 15 secondsSession shell. Uh, in here I have this spinner. And the spinner
7:34:247 hours, 34 minutes, 24 secondsuses the uses a fixed color. Uh I'm pretty sure I have to modify this.
7:34:347 hours, 34 minutes, 34 secondsSo what I'm going to do is I'm going to import mode from night code database
7:34:407 hours, 34 minutes, 40 secondsenums. I'm going to give this spinner props which accept an optional mode. I'm
7:34:487 hours, 34 minutes, 48 secondsgoing to go ahead and mark this mode as default of build and I'm going to change the active color depending on the mode.
7:34:577 hours, 34 minutes, 57 secondsSo if it's plan, it's going to use plan mode otherwise it's going to use primary and then I'm going to switch the active color uh to be that. Now the only thing
7:35:077 hours, 35 minutes, 7 secondsthat I have to check is that inside of session shell here I somehow passed the mode option and let me just check how can I do that.
7:35:207 hours, 35 minutes, 20 secondsI think the simplest way is to just call the use prompt config
7:35:297 hours, 35 minutes, 29 secondslike this. just use prompt config from providers prompt config.
7:35:377 hours, 35 minutes, 37 secondsAnd now if I go ahead and switch to plan mode and do hello world. Yeah, you can see how uh this now changes to that
7:35:467 hours, 35 minutes, 46 secondscolor as well. So everything is kind of in sync. Uh obviously what's not in sync in is this because in the back end it's
7:35:537 hours, 35 minutes, 53 secondsnot yet yet persisted uh to use that plan mode. Uh okay. So I'm quite happy
7:36:007 hours, 36 minuteswith how this turned out. Uh one thing I'm not too too happy about is how in agents dialogue more specifically maybe
7:36:097 hours, 36 minutes, 9 secondsin commands how we have to pass the current mode and the on select mode through the context
7:36:167 hours, 36 minutes, 16 secondsrather than directly doing it inside of the agents dialog content. But I think the reason I did this is because if you
7:36:247 hours, 36 minutes, 24 secondsimport use prompt config here, I think it will break because it somehow gets rendered outside of the composition it's
7:36:347 hours, 36 minutes, 34 secondssupposed to be in. And what I mean by that is this. The dialogue provider, as you can see, is rendered before prompt
7:36:447 hours, 36 minutes, 44 secondsconfig provider. So if you attempt to import use provider here, it's going to
7:36:517 hours, 36 minutes, 51 secondsbreak. But I think that if you change the order like wrap this above, it introduces even more problems. So if you
7:36:597 hours, 36 minutes, 59 secondswere wondering like why did I uh pass all of those actions through the command context, it's because of that.
7:37:087 hours, 37 minutes, 8 secondsAll right, great great work. Let's go ahead and commit those changes.
7:37:147 hours, 37 minutes, 14 secondsSo chapter six session management configuration get checkout-b
7:37:227 hours, 37 minutes, 22 seconds06 session management and config
7:37:297 hours, 37 minutes, 29 secondsget addit commit 06 session and config get push- origin 06 session management and config.
7:37:437 hours, 37 minutes, 43 secondsBrilliant. Let's go ahead and compare and pull request. And what's going to happen now since we've added railway in
7:37:517 hours, 37 minutes, 51 secondsthe previous uh chapter is that besides code rabbit, we are also going to have uh our CI/CD happening on railway.
7:38:037 hours, 38 minutes, 3 secondsYou can check that by going inside of railway inside of your settings and environments. And in here you can see we
7:38:107 hours, 38 minutes, 10 secondshave a PR environment specifically for 06 session management and config now and it's being built.
7:38:207 hours, 38 minutes, 20 secondsAnd here we have the summary by code rabbit. We can now press tab to toggle between build and plane mode. Plan mode
7:38:287 hours, 38 minutes, 28 secondsagent and model selection dialogues are accessible via command menu. Sessions management dialogue with search functionality is available. Status bar
7:38:367 hours, 38 minutes, 36 secondsnow dynamically displays the current mode and selected model. We enhanced UI with mode aware visual indicators and spinner color reflects the current mode
7:38:447 hours, 38 minutes, 44 secondsbuild or plan. As you can see uh railway has also deployed night code server. If
7:38:517 hours, 38 minutes, 51 secondsyours hasn't, go ahead and change from your production environment to night code and you will see a deploy button and you can just hit deploy and then you
7:39:007 hours, 39 minuteswill have this indicator right here which is really cool that for every pull request you can confirm that night server service is up and running and wasn't affected and it's still working.
7:39:117 hours, 39 minutes, 11 secondsWe have one comment here uh and it's telling me that the list contains modes but the placeholder states agents. Yeah,
7:39:207 hours, 39 minutes, 20 secondstechnically they are agents in a way. Basically, whether you put modes or agents, same thing. It doesn't
7:39:287 hours, 39 minutes, 28 secondsreally matter. So, I'm going to resolve this conversation and I'm going to merge this pull request and I'm not going to delete any branches
7:39:367 hours, 39 minutes, 36 secondsso I can keep track of all of my progress here. All I'm going to do is get checkout main get pool origin main
7:39:467 hours, 39 minutes, 46 secondsand that's going to ensure that I have synchronized all of my changes and that I'm on my main branch. Brilliant. That
7:39:537 hours, 39 minutes, 53 secondswraps up chapter 6. Amazing job and see you in the next chapter.
Chapter 10: Tool Calling
7:39:597 hours, 39 minutes, 59 secondsIn this chapter, we're going to add tool calling to our project. We're going to achieve this in two steps. In step one,
7:40:067 hours, 40 minutes, 6 secondswe're going to modify our current way of streaming text, which is basically just a flat text. And we're going to modify
7:40:157 hours, 40 minutes, 15 secondsit into ordered message parts. These parts can be reasoning, tool calls, or the classic text that we have right now.
7:40:257 hours, 40 minutes, 25 secondsReasoning will look like this. It's basically going to display thinking with a dimmed border. And then it's going to
7:40:317 hours, 40 minutes, 31 secondsdisplay the thinking that the model is doing. Tool call will display the name of the tool and any arguments that it
7:40:407 hours, 40 minutes, 40 secondsreceived such as the path it wants to read. It will also display the status if it's currently calling it or if it has
7:40:467 hours, 40 minutes, 46 secondsfinished calling the tool. Then in step two, we're going to turn on the mode in
7:40:547 hours, 40 minutes, 54 secondsthe back end. So if the user selects plan mode we are going to limit for read file list grap and globe basically read
7:41:037 hours, 41 minutes, 3 secondsonly tools and if the user selects build mode we are going to enable write file edit file bash basically all of these
7:41:127 hours, 41 minutes, 12 secondsplus uh all the right functions which means we're also going to build our system prompt and we're also going to
7:41:197 hours, 41 minutes, 19 secondswork in the uh agentic loop uh function which you're going to see all about in a moment. So, let me show you what you're
7:41:277 hours, 41 minutes, 27 secondsgoing to have at the end of chapter 7, which is basically the most important part uh because this is what enables our
7:41:367 hours, 41 minutes, 36 secondsharness into becoming more than just a text streaming service. So in this
7:41:437 hours, 41 minutes, 43 secondsfinished chapter, if you go ahead and do something like uh a switch to plan mode and ask it what is this project about?
7:41:517 hours, 41 minutes, 51 secondsUh it will be able to uh call various tools, display its thinking and it will
7:42:007 hours, 42 minutesgive you the output uh based on what it reads from all of the files and
7:42:077 hours, 42 minutes, 7 secondseverything in here. There we go. You can see it gives me back the result. And of course, we will still be able to
7:42:147 hours, 42 minutes, 14 secondsinterrupt that and everything else. So that is the plan. Let's go ahead and implement it.
7:42:227 hours, 42 minutes, 22 secondsLet's go ahead and start by modifying our chat API route. So we're going to go inside of packages server source routes chat.ts.
7:42:327 hours, 42 minutes, 32 secondsIn here, we are going to go ahead and import Prisma type from our database. So let's go ahead and just add that. And
7:42:417 hours, 42 minutes, 41 secondsthen we are going to go ahead and extend our shared package imports. Right now we are only importing type chat stream
7:42:497 hours, 42 minutes, 49 secondsevent. So now let's go ahead and also extract message part. Let's extract tool
7:42:587 hours, 42 minutes, 58 secondsarguments schema and message parts schema which we have prepared before.
7:43:087 hours, 43 minutes, 8 secondsNow let's go ahead and modify our function called stream AI response.
7:43:157 hours, 43 minutes, 15 secondsCurrently this is optimized to only uh stream text. Now we are going to modify that. So let's go ahead and add parts
7:43:247 hours, 43 minutes, 24 secondswhich is basically an array of message parts which can be reasoning tool call or text. This is something we have
7:43:317 hours, 43 minutes, 31 secondsdefined in our shared package in the schemas here with this zod functionality.
7:43:387 hours, 43 minutes, 38 secondsNow that we have the parts, we can get rid of the full text for now and let's instead go directly inside of the
7:43:467 hours, 43 minutes, 46 secondspersist interrupted message. Let's go ahead and remove uh this clause and let's go ahead and simply generate full
7:43:557 hours, 43 minutes, 55 secondstext by filtering for text only instances of all of the parts that we have. Map them and join them all into a
7:44:057 hours, 44 minutes, 5 secondssingle string. We've done something similar before. So this is how we decide okay this is all the text that we have.
7:44:147 hours, 44 minutes, 14 secondsAnd then instead of doing the check outside, we're going to do the check in here. So if that text we just created is empty or in general, if all of the
7:44:237 hours, 44 minutes, 23 secondsmessage parts are empty, let's just go ahead and do an early return. I like to explicitly open the brackets like this.
7:44:317 hours, 44 minutes, 31 secondsWhat we have to do now is we have to validate uh our parts. So I'm not just going to blindly uh return all the parts
7:44:407 hours, 44 minutes, 40 secondsthat we are getting. I want to make sure that they are correct. So validated parts will be a type of Prisma input JSON value. And the reason we are using
7:44:497 hours, 44 minutes, 49 secondsinput JSON value is because of our schema Prisma. When you look at our message, we store parts in a JSON object
7:44:597 hours, 44 minutes, 59 secondssimply because they can be two various for us. I I meant to say they can vary a lot. So that's why I we are making use
7:45:087 hours, 45 minutes, 8 secondsof posgress JSON field because it's kind of dynamic. So we are just using it here. So we have the exact value that
7:45:167 hours, 45 minutes, 16 secondsour database expects. And basically what we assign here is again we check if it's greater than zero. And then we parse them through our message parts schema.
7:45:287 hours, 45 minutes, 28 secondsBasically a discriminated union which checks if the part that we received has a type of reasoning. It has to have
7:45:357 hours, 45 minutes, 35 secondstext. If the part we received has tool call, it needs to have ID, name, arguments and result. And the same for
7:45:437 hours, 45 minutes, 43 secondstext. So we are basically using ZOD to quickly validate that whoever calls this function persist interrupted messages uh
7:45:527 hours, 45 minutes, 52 secondshas completely valid streaming types that we can work with because we have to be careful about what we can store in
7:45:597 hours, 45 minutes, 59 secondsour database. And now we can just go ahead and add those parts JSON to our database. And since we defined it as an
7:46:067 hours, 46 minutes, 6 secondsinput JSON array, we don't have to worry.
7:46:107 hours, 46 minutes, 10 secondsGreat. Now, let's go ahead uh down here until we find uh messages history abort
7:46:207 hours, 46 minutes, 20 secondssignal. And inside of AI stream text, let's go ahead and pass along the provider options, which is going to call
7:46:277 hours, 46 minutes, 27 secondsresolve the model.provider options.
7:46:317 hours, 46 minutes, 31 secondsWe are going to fix uh this type error in a second. Let's just make sure we don't forget to add this.
7:46:387 hours, 46 minutes, 38 secondsAll right. Now, inside of this for uh for loop, let's go ahead and add another
7:46:467 hours, 46 minutes, 46 secondsif clause after this break check. And that will be if part type is reasoning delta. That means we are currently streaming back what the LLM is thinking.
7:46:597 hours, 46 minutes, 59 secondsSo let's go ahead and get that last part that we have and let's confirm that that last type exists and that it is
7:47:087 hours, 47 minutes, 8 secondsreasoning. And if it is, let's go ahead and append last.ext to part.ext. I mean vice versa. Let's
7:47:167 hours, 47 minutes, 16 secondsappend part do.ext to last.ext.
7:47:227 hours, 47 minutes, 22 secondsIn the else here, let's go ahead and do parts dotpush type reasoning text part.ext.
7:47:317 hours, 47 minutes, 31 secondsAnd then let's go ahead and generate the event we are going to stream back. So this is the event type reasoning delta.
7:47:417 hours, 47 minutes, 41 secondsAnd given that we have this discriminated union, we know okay if it's reasoning delta, we need to provide the text or what the LLM is thinking and
7:47:507 hours, 47 minutes, 50 secondsthat's what we are going to emit right here. So let's go ahead now and await
7:47:567 hours, 47 minutes, 56 secondsstream write s and pass along reasoning delta and stringify the data event.
7:48:057 hours, 48 minutes, 5 secondsGreat. So that is resolved for any thinking. And now we have to modify the text delta. So what I'm going to do is I'm going to remove the full text.
7:48:197 hours, 48 minutes, 19 secondsAnd I'm going to go ahead and get the last as I did before. And then I'm going to do the same thing I did above here.
7:48:297 hours, 48 minutes, 29 secondsI'm checking if last exists. If last is type of text. And then I'm appending part.ext text to last.ext
7:48:387 hours, 48 minutes, 38 secondselse we are going to push into parts uh type text part.ext.
7:48:467 hours, 48 minutes, 46 secondsSo basically either add more content to what's currently streaming or start a
7:48:537 hours, 48 minutes, 53 secondsnew part right uh I feel like I didn't explain this properly. This is basically
7:48:597 hours, 48 minutes, 59 secondsgrouping it right. So if the previous reasoning was already happening, right?
7:49:047 hours, 49 minutes, 4 secondsIf the if the last part of the streaming was reasoning, we are just going to append new text to it because it is
7:49:137 hours, 49 minutes, 13 secondsstill reasoning, right? So we don't have to display an entirely new section uh in
7:49:207 hours, 49 minutes, 20 secondsthe terminal saying thinking, thinking, thinking, thinking. We can just show thinking once and then just append new
7:49:287 hours, 49 minutes, 28 secondslines one beneath another. That's why we are checking. Hey, is the last part still reasoning? If it is, we can just
7:49:367 hours, 49 minutes, 36 secondsappend the text. But if it isn't, then we have to push a new part, right? We have to like stream back something new.
7:49:447 hours, 49 minutes, 44 secondsThat's what uh this logic is doing. I feel like I just uh went through that without explaining it. My apologies. So,
7:49:517 hours, 49 minutes, 51 secondssame thing here. If we know that it's currently rendering text, we are not going to create any new sections. we're
7:49:587 hours, 49 minutes, 58 secondsjust going to keep appending that existing text. But if the last part was reasoning, well, in that case, we have
7:50:067 hours, 50 minutes, 6 secondsto push a whole new part and a whole new variant. That's what that is doing. Uh,
7:50:137 hours, 50 minutes, 13 secondsokay. So, that is text delta. Now, let's go ahead and add uh tool call here. So, what happens if we hit a uh tool call?
7:50:257 hours, 50 minutes, 25 secondsThe first thing we are going to do is making sure that the arguments can be validated. So partinput
7:50:327 hours, 50 minutes, 32 secondscan we validate that against our tool call argument schema which is a very broad uh definition object but at least
7:50:417 hours, 50 minutes, 41 secondswe can parse something so we know it it's not something completely random that will break the app immediately. And
7:50:497 hours, 50 minutes, 49 secondslet's go ahead and push that part. So type tool call ID part tool call ID name part tool name and the arguments.
7:50:587 hours, 50 minutes, 58 secondsAnd since it's tool call, we know that that's everything we need here.
7:51:037 hours, 51 minutes, 3 secondsNow that we have that, let's go ahead and construct the event that we are going to stream back. Here we have it.
7:51:117 hours, 51 minutes, 11 secondsAnd let's go ahead and actually stream it. So stream write S SSE event tool call and stringify id event under data.
7:51:207 hours, 51 minutes, 20 secondsMake sure you didn't misspell any of the tools here. But even if you do, you will get an error because of our extreme type
7:51:287 hours, 51 minutes, 28 secondssafety that we are following here to make it easier for us to code. So that is tool call and now we have to handle
7:51:367 hours, 51 minutes, 36 secondstool results. Basically we have to modify the streaming uh in a sense that
7:51:427 hours, 51 minutes, 42 secondsit started calling a tool and then it finished calling a tool. So we have to update that indicator. So let's go ahead
7:51:507 hours, 51 minutes, 50 secondsand define the result string to check if type of part.output
7:51:577 hours, 51 minutes, 57 secondsis a string. If it is use part.output otherwise stringify whatever is passed
7:52:047 hours, 52 minutes, 4 secondsin part do.output. So this depends on the provider and on the LLM model that we are using. So we are basically now
7:52:147 hours, 52 minutes, 14 secondscreating some functions and some checks to make whatever our LLM is returning
7:52:207 hours, 52 minutes, 20 secondswithin the tool result into text because they can return objects. They can return uh a bunch of things. So we are checking
7:52:287 hours, 52 minutes, 28 secondsis it just a normal string? If it is let's go ahead and just output it. If it's not let's stringify it into something readable.
7:52:367 hours, 52 minutes, 36 secondsAnd now uh we have to go and find an existing tool part which we started
7:52:457 hours, 52 minutes, 45 secondsstreaming here and appended to our parts.push. We have to find it by id and
7:52:527 hours, 52 minutes, 52 secondswe have to update by giving it uh let me show you by giving it the result. You can see how right now there is no
7:53:007 hours, 53 minutesresult. Why? Because at this point we are just initiating the tool call. So in the tool result what we have to do is we
7:53:097 hours, 53 minutes, 9 secondshave to find tool call part using parts.find.
7:53:137 hours, 53 minutes, 13 secondsUh in here I'm doing kind of an ugly type script but it does help uh with the strictness here. And essentially within
7:53:227 hours, 53 minutes, 22 secondsparts we are looking for a part. Let me show you how this looks without TypeScript. So you can see that it's not
7:53:307 hours, 53 minutes, 30 secondssuch a complicated function actually right? It's just this but if you define this then it will be
7:53:397 hours, 53 minutes, 39 secondsvery strict onto what P can be and then this will have more sense. So we are looking for p part type which is tool
7:53:487 hours, 53 minutes, 48 secondscall and part id matches the current part tool result tool call id because
7:53:567 hours, 53 minutes, 56 secondsthe tool call ID is going to be identical to this one which started the tool call event and is now calling the
7:54:037 hours, 54 minutes, 3 secondstool result event. So now that we grab that uh TC part, let's go ahead and
7:54:107 hours, 54 minutes, 10 secondsappend the TC part dot result to our result string.
7:54:207 hours, 54 minutes, 20 secondsAnd now let's go ahead and construct an event tool result with the result string. And
7:54:287 hours, 54 minutes, 28 secondslet's go ahead and write SSE event tool result and stringify back the data. Great.
7:54:377 hours, 54 minutes, 37 secondsUh so we now have that. Let's go ahead all the way down here until we find uh a lapsed in milliseconds.
7:54:467 hours, 54 minutes, 46 secondsAnd let's go ahead and add another full text string here by querying over all
7:54:557 hours, 54 minutes, 55 secondsthe parts and only filtering those that are actual text. Let's go ahead and do
7:55:017 hours, 55 minutes, 1 secondanother validated parts here. Uh so we are again using Prisma input JSON
7:55:097 hours, 55 minutes, 9 secondsvalue. We are checking if parts.length is greater than zero. If it is, we are running it against our zod message part
7:55:177 hours, 55 minutes, 17 secondsschema validation. And otherwise, we are marking them as undefined.
7:55:227 hours, 55 minutes, 22 secondsAnd then once we have validated parts, we can go ahead and pass it in the database create. So parts
7:55:317 hours, 55 minutes, 31 secondsvalidated parts. You've probably noticed that this is almost identical to what we've done uh before. Let me try and
7:55:407 hours, 55 minutes, 40 secondsfind where we are doing that. I think somewhere uh somewhere up here basically because
7:55:487 hours, 55 minutes, 48 secondswe need to handle the interrupted message part. Yeah, we did it in in here. It's the same thing that we did here. But this is for the persist
7:55:577 hours, 55 minutes, 57 secondsinterrupted message. So if user presses escape we are going to trigger this function and then that has to again
7:56:067 hours, 56 minutes, 6 secondscapture all of the text and separately capture all of the parts that have
7:56:127 hours, 56 minutes, 12 secondshappened right and then store that into message which is interrupted with parts and with content full text. That's one
7:56:217 hours, 56 minutes, 21 secondsscenario. And then all the way down here we have to do the same thing with validated parts and full text for the
7:56:307 hours, 56 minutes, 30 secondsnormal uh assistant message complete status. And if this is confusing you,
7:56:367 hours, 56 minutes, 36 secondsit's perfectly fine because it's a very very complex function because we have to kind of modify it. Usually this would be
7:56:457 hours, 56 minutes, 45 secondsmuch simpler if we were on the web but because we are within open tui uh uh we have to reimplement the use chat hook
7:56:547 hours, 56 minutes, 54 secondswhich means that we have to modify the return events like this manually but it's an extremely good practice to kind of see the inner workings of uh those great SDK tools like AI SDK.
7:57:087 hours, 57 minutes, 8 secondsGreat. So that is it for our API. We can now display tool calling and we can now display uh thinking. So what I want to
7:57:177 hours, 57 minutes, 17 secondsdo now is I want to resolve uh this error that we have right here. Resolve the model.provider
7:57:257 hours, 57 minutes, 25 secondsoptions. The reason we have added provider options is because you have to specify uh or should I say enable if a
7:57:337 hours, 57 minutes, 33 secondsmodel should be thinking or not. So without this the models will never uh start reasoning. So let's go ahead and
7:57:427 hours, 57 minutes, 42 secondsresolve uh that. So I'm going to go ahead inside of my uh server
7:57:497 hours, 57 minutes, 49 secondssource libmodels.ds and I'm going to go ahead and import
7:57:577 hours, 57 minutes, 57 secondstype provider options from AISDK provided uh provider utils. Let's find
7:58:057 hours, 58 minutes, 5 secondsthe resolved model. And after model ID, let's go ahead and add optional provider options. And then I'm going to go ahead and do the following.
7:58:177 hours, 58 minutes, 17 secondsI'm going to create an object anthropic provider options, which is
7:58:247 hours, 58 minutes, 24 secondsgoing to be a partial of object anthropic mode ID. So supported ones combined with the provider options.
7:58:347 hours, 58 minutes, 34 secondsSo inside of this object, I'm going to go ahead and specify my first ID that I want to modify, claude oppus 46.
7:58:457 hours, 58 minutes, 45 secondsAnd I'm going to go ahead and choose what provider options I'm modifying. So my AI SDK tooling can tell me if
7:58:537 hours, 58 minutes, 53 secondssomething I'm trying to add here is wrong. So, I'm going to add thinking here.
7:59:007 hours, 59 minutesI'm going to enable it. And I'm going to set the budget tokens to be 10,000. And
7:59:077 hours, 59 minutes, 7 secondsthen I'm going to go ahead and do the same for Claude Sonnet 46.
7:59:177 hours, 59 minutes, 17 secondsLet me just see if this is properly indented or not. This is incorrectly indented because I have to end this here
7:59:257 hours, 59 minutes, 25 secondsand then I have an extra one here like this. So claw opus 46 clots onet
7:59:337 hours, 59 minutes, 33 secondssix. Okay, pause the screen and uh double check that you have correct indentations and everything here. So for
7:59:427 hours, 59 minutes, 42 secondsnow I'm just going to do it for these models. uh if you're using different models, let me show you and kind of try and give you a guide on what to do here.
7:59:527 hours, 59 minutes, 52 secondsSo you have to specify it for one of the models you have added in your shared package source models.dts in this array
8:00:008 hoursright here. So if you added some Gemini model or Google model uh you have to research whether it supports thinking
8:00:098 hours, 9 secondsand if it does support thinking in here you are not going to use entropic model ID uh instead you will have I don't know
8:00:188 hours, 18 secondsmaybe a third one like Gemini model ID and provider will be Gemini or Google
8:00:268 hours, 26 secondsmaybe something like that then you will create your own Gemini anthropic Click my apologies Gemini provider options and
8:00:358 hours, 35 secondsmodify this type to be uh Gemini and in here you will map the model that you are
8:00:428 hours, 42 secondsusing write Google or Gemini whatever is the provider and then you will enable thinking and what I would highly highly
8:00:498 hours, 49 secondshighly suggest is having Versel AI SDK open so that you can actively look at uh
8:00:588 hours, 58 secondsthe provider. So for example, uh Google generative AI
8:01:058 hours, 1 minute, 5 secondsuh Google generative AI provider and in here you will be able to uh I'm pretty
8:01:128 hours, 1 minute, 12 secondssure find uh the provider options and how they work. So in here let me try and
8:01:208 hours, 1 minute, 20 secondsfind if we have it's you can see there are some thinking options. So thinking
8:01:278 hours, 1 minute, 27 secondsbudget yeah you can see anthropic specifies thinking like this but Google generates uh Google specifies it in
8:01:358 hours, 1 minute, 35 secondsanother way for example let's let me find uh open AI and how they specify thinking so if I scroll
8:01:448 hours, 1 minute, 44 secondsdown here let me try and find uh so provider options open AI so that's what we are
8:01:528 hours, 1 minute, 52 secondsdoing here this is the the provider options And then you have to specify anthropic or open AI or something like that inside.
8:02:038 hours, 2 minutes, 3 secondsBut let me try and find the okay in here. It's reasoning effort,
8:02:118 hours, 2 minutes, 11 secondsright? I think uh I'm going to try and enable it for open AI simply so you uh
8:02:198 hours, 2 minutes, 19 secondsso you can see the changes that need to be done. uh reasoning output
8:02:268 hours, 2 minutes, 26 secondssee open AI reasoning summary detailed right so let me go ahead and finish what I wanted to do with enthropic here and I
8:02:358 hours, 2 minutes, 35 secondswould suggest you do it as well regardless if you use entropic or not simply so you have this finished uh go ahead
8:02:438 hours, 2 minutes, 43 secondsand find uh resolve anthropic model and in here add provider options and pass
8:02:508 hours, 2 minutes, 50 secondsalong anthropic provider options model ID like that. And by adding this, if you go
8:02:598 hours, 2 minutes, 59 secondsback inside of your server routes chat.ds, you will see that provider options are no longer a problem. Now,
8:03:098 hours, 3 minutes, 9 secondsuh, great. So, we now have that finished here. So for example,
8:03:168 hours, 3 minutes, 16 secondsif I want to copy this and paste it here, I would do something like open AI provider options.
8:03:268 hours, 3 minutes, 26 secondsI would use open AI model ID, which gives me an error here. Perfect. So I
8:03:338 hours, 3 minutes, 33 secondsmodify this to GPT 5.4 for example. I don't know if the other ones support thinking, so I'm not going to enable it.
8:03:418 hours, 3 minutes, 41 secondsI have to change this to open AI and I'm pretty sure that this is incorrect provider options here. So I think it could be reasoning summary that I need.
8:03:568 hours, 3 minutes, 56 secondsI'm not sure about budget tokens.
8:04:008 hours, 4 minutesSo I would add something like this open AI provider options and then I would find resolve open AI model provider
8:04:088 hours, 4 minutes, 8 secondsoptions and then again I'd choose model ID here and everything works just fine. So
8:04:178 hours, 4 minutes, 17 secondsthat's how you would do it for another provider. Uh I haven't tested if it works with OpenAI. I only I mostly use
8:04:258 hours, 4 minutes, 25 secondsum I mostly use uh clawed models but we'll see it will be a good exercise for
8:04:328 hours, 4 minutes, 32 secondsus to try. Great. So we now have that uh and now uh we have to do the equivalent
8:04:398 hours, 4 minutes, 39 secondsof what we did in chat route into use chat hook.
8:04:458 hours, 4 minutes, 45 secondsSo let's go inside of use chat and let's go ahead and find client
8:04:528 hours, 4 minutes, 52 secondsmessage part. And what I'm going to do now is I'm going to add another type called client tool call part. Type is
8:05:018 hours, 5 minutes, 1 secondtool call. It has ID, name, arguments, optional result, and a status of calling or done. Again, this is something that
8:05:098 hours, 5 minutes, 9 secondsyou can probably infer from Hono. A lot of things here can be inferred from hono. Perhaps it might be a good idea.
8:05:168 hours, 5 minutes, 16 secondsWe are writing too many custom types except maybe these run stream params, submit params. Those are uh our custom
8:05:258 hours, 5 minutes, 25 secondsones. But okay, it's message client tool call part and client message part could probably
8:05:338 hours, 5 minutes, 33 secondsbe inferred either from our shared package or from um from Prisma or from
8:05:418 hours, 5 minutes, 41 secondsHono. We'll see. I'll see at the end if this is something we can improve.
8:05:468 hours, 5 minutes, 46 secondsSo now that we have that, let's go ahead and also modify the uh client message
8:05:538 hours, 5 minutes, 53 secondspart to be a discriminated union. So client message part can either be type
8:06:008 hours, 6 minutesreasoning with text string or client tool call part or type text with text.
8:06:098 hours, 6 minutes, 9 secondsNow, let's go ahead and find use chat hook right here. Let's find our switch case.
8:06:208 hours, 6 minutes, 20 secondsHere it is. So, switche event.t type and let's go ahead and add our reasoning
8:06:268 hours, 6 minutes, 26 secondsdelta so we can stream back uh when that happens. So uh reasoning delta
8:06:348 hours, 6 minutes, 34 secondshas to look at the last part and just like on back end we have to confirm that the last part is reasoning. If it is
8:06:438 hours, 6 minutes, 43 secondslet's just append text to that last part. Uh otherwise if it's not let's go ahead and push an entirely new part. And
8:06:528 hours, 6 minutes, 52 secondsthen we have to emit those parts and break.
8:06:588 hours, 6 minutes, 58 secondsAnd now let's go ahead and add some other cases. So uh let me see where do we add? Well, it doesn't really matter
8:07:078 hours, 7 minutes, 7 secondswhere we add them really. Uh let me go ahead and add case tool call.
8:07:148 hours, 7 minutes, 14 secondsUh this one is simpler because tool calls uh are all individual. They don't like continuously
8:07:238 hours, 7 minutes, 23 secondshappen. So we can just go ahead and push a tool call and we can emit immediately
8:07:298 hours, 7 minutes, 29 secondsand break. And for tool result we once again have to look and have to find for the tool ID that was previously called.
8:07:428 hours, 7 minutes, 42 secondsSo again we have to find the tool call by searching through the parts. And again this is a very simple function
8:07:508 hours, 7 minutes, 50 secondswith a okay with a complicated type or maybe not so much but basically looking
8:07:578 hours, 7 minutes, 57 secondsif part is tool call and if part ID is equivalent to event tool call ID and if we are able to find that part we can go
8:08:068 hours, 8 minutes, 6 secondsahead and append the result and change the status to done and let's go [clears throat] ahead and emit parts and
8:08:158 hours, 8 minutes, 15 secondsbreak. So essentially what we were just doing on the back end we are now doing on the front end. Uh great. So we now
8:08:238 hours, 8 minutes, 23 secondshave that and what we have to do now is we have to modify our bot message component to be able to handle uh
8:08:308 hours, 8 minutes, 30 secondsdisplaying that because uh there is currently no way for it to do that. If you take a look at messages bot message,
8:08:388 hours, 8 minutes, 38 secondsit has no way of rendering any thinking or parts. It can just render text.
8:08:458 hours, 8 minutes, 45 secondsThat's all it can do because what we do here is we filter through just text. So
8:08:528 hours, 8 minutes, 52 secondswhat I'm going to do here is I'm going to add empty border. Make sure you have it. Then I'm going to go ahead and add
8:08:598 hours, 8 minutes, 59 secondsfrom use chat my new type client tool call part. Then I'm going to go ahead
8:09:068 hours, 9 minutes, 6 secondsand create a fun little util to format a tool name.
8:09:168 hours, 9 minutes, 16 secondsUh this can be done in like a billion ways. I found a regex that does it. And when I say found, I mean I asked AI to
8:09:258 hours, 9 minutes, 25 secondsgenerate it for me. Uh basically it's a it's it's a casing it's a case converter, right? So if the tool is
8:09:348 hours, 9 minutes, 34 secondssomething like read file, it will return back read file. If it's something like
8:09:418 hours, 9 minutes, 41 secondsgrap, it will return back grap. If it is create file, it will return create file.
8:09:508 hours, 9 minutes, 50 secondsThat's what this ragex does. You can pause the screen to copy it or just ask AI to generate this exactly.
8:09:598 hours, 9 minutes, 59 secondsNow let's go ahead and create a function to format tool arguments.
8:10:048 hours, 10 minutes, 4 secondsIt accepts client tool call part returns a string and it maps over the each value of the arguments and it returns them
8:10:148 hours, 10 minutes, 14 secondsinto a string. So you can exactly see what file a tool is working on. Let's go
8:10:228 hours, 10 minutes, 22 secondsahead and create a type. Part group type is client message part type. So reasoning tool call or text and parts are client message part and then array.
8:10:348 hours, 10 minutes, 34 secondsUh great. Now what we have to do is we have to create a function that will group consecutive parts.
8:10:428 hours, 10 minutes, 42 secondsUh this is a little bit not so functional as much as cosmetic simply because if you group consecutive parts
8:10:508 hours, 10 minutes, 50 secondstogether they look much better than if you constantly have like uh thinking uh
8:10:578 hours, 10 minutes, 57 secondsthen you have another spacer thinking another spacer thinking basically it just doesn't look as good. So let's go
8:11:048 hours, 11 minutes, 4 secondsahead and just group consecutive parts together. So if we have three parts and all three are thinking, let's display it
8:11:138 hours, 11 minutes, 13 secondsin one container rather than each of them being its own container. For that, we're going to use a simple for loop
8:11:228 hours, 11 minutes, 22 secondsover all the parts that we have. Let's get the current part that we are iterating over. Let's go ahead and find the last group that we know of. And
8:11:308 hours, 11 minutes, 30 secondslet's check if the last group type is equivalent to the current P part we are iterating over type. If it is, let's simply push it to that group.
8:11:428 hours, 11 minutes, 42 secondsOtherwise, if it's not, let's go ahead and define the key for the new group.
8:11:488 hours, 11 minutes, 48 secondsSo, if part type is tool call, then make it group tool call part ID. Otherwise,
8:11:548 hours, 11 minutes, 54 secondsgroup part type and just the index. And then finally, let's just go ahead and
8:12:018 hours, 12 minutes, 1 secondpush that new group with type part type parts an array and then a single part
8:12:078 hours, 12 minutes, 7 secondsinside and a key. And finally, return groups.
8:12:148 hours, 12 minutes, 14 secondsGreat. Now that we have that function, let's go ahead and modify how we actually render uh messages inside of
8:12:238 hours, 12 minutes, 23 secondsthe bot message here. Uh so what I know I can do is I can now get rid of this.
8:12:308 hours, 12 minutes, 30 secondsWe are no longer filtering by text only.
8:12:358 hours, 12 minutes, 35 secondsAnd what I'm going to do now uh is the following. So let me just see.
8:12:438 hours, 12 minutes, 43 secondsOkay. uh we can remove this part. I'm pretty certain that we can. And let's
8:12:508 hours, 12 minutes, 50 secondsinstead iterate over grouped consecutive parts. So for
8:13:008 hours, 13 minuteseach group that we receive, let's go ahead and create a container like this.
8:13:098 hours, 13 minutes, 9 secondsLet me go ahead and properly close it.
8:13:128 hours, 13 minutes, 12 secondsSo each group will have its own box with a group key, its own padding and full
8:13:188 hours, 13 minutes, 18 secondswidth. And then for each part of that group, we can iterate further.
8:13:268 hours, 13 minutes, 26 secondsFor example, in this part, let's go ahead and check if part type is
8:13:338 hours, 13 minutes, 33 secondsreasoning. Let's go ahead and return the UI for displaying reasoning. Uh, that's
8:13:418 hours, 13 minutes, 41 secondsgoing to be a box. I'm going to show you exactly what the code is in a second.
8:13:488 hours, 13 minutes, 48 secondsHere it is. Key reasoning border left border colors thinking border custom
8:13:568 hours, 13 minutes, 56 secondsborder characters. We are doing the little empty border trick. This is purely cosmetic. You don't have to do it if you don't have this character. Uh,
8:14:048 hours, 14 minutes, 4 secondsbut we I think we reused it somewhere already. You can just do it without this. It will work just as fine. It's just cosmetics. We give it full width and padding inside.
8:14:158 hours, 14 minutes, 15 secondsAnd then inside of here, we render the text. We give it the attributes of dim.
8:14:208 hours, 14 minutes, 20 secondsAnd we give it foreground colors thinking thinking. And we render the text. Great. Now let's go ahead and do
8:14:298 hours, 14 minutes, 29 secondsanother if parts.ype type is equal to tool call not parts individual part dot
8:14:388 hours, 14 minutes, 38 secondstype. So if it's tool call let's go ahead and learn how to display that. So
8:14:448 hours, 14 minutes, 44 secondsagain we're going to do a box. So let me go ahead and close the box and let me close the return. Let me show you the
8:14:538 hours, 14 minutes, 53 secondsattributes. So they are almost identical if not the same. Uh we are again using thinking border here. Again the little
8:15:028 hours, 15 minutes, 2 secondstrick padding is two. I think it's identical. The only difference is the key.
8:15:098 hours, 15 minutes, 9 secondsAnd inside of this box we are once again going to render text. We are going to
8:15:168 hours, 15 minutes, 16 secondsrender uh the formatted tool name. So if we again if we receive something like
8:15:258 hours, 15 minutes, 25 secondsread file we're going to render it as read file and we are going to format the tool
8:15:348 hours, 15 minutes, 34 secondsarguments immediately after and then if the status is calling we're going to add three dots otherwise we're not going to
8:15:418 hours, 15 minutes, 41 secondsadd anything to indicate that it's finished. Okay.
8:15:468 hours, 15 minutes, 46 secondsAnd let's go ahead and add the last type
8:15:528 hours, 15 minutes, 52 secondswhich is text. And in here we do the simple
8:15:598 hours, 15 minutes, 59 secondsreturn. And finally uh let me see I have some mistake.
8:16:068 hours, 16 minutes, 6 secondsUh well the last one will be return null. But obviously I'm having something here. Do I am I missing an extra here?
8:16:148 hours, 16 minutes, 14 secondsOkay. So, I had an extra parenthesis and I was missing a curly bracket.
8:16:238 hours, 16 minutes, 23 secondsJust make sure that you didn't do Yeah, you need to close this. You need to close this. You need to close this. And you need to close this.
8:16:328 hours, 16 minutes, 32 secondsSo, yes, this is how it should look like at the end.
8:16:368 hours, 16 minutes, 36 secondsUh, great. So I think that this should be enough for us to see some thinking
8:16:458 hours, 16 minutes, 45 secondsbecause we don't have any tool calls yet. So if I go ahead and run bondev
8:16:528 hours, 16 minutes, 52 secondsserver now and if I do I'm going to test on oppus and I will do hello how are you?
8:17:018 hours, 17 minutes, 1 secondI think I should see some thinking displayed here. Let's see in a second if
8:17:088 hours, 17 minutes, 8 secondsthis is correct or not. Uh it is still creating this in the database. Perhaps I have some network issue because it is
8:17:178 hours, 17 minutes, 17 secondstaking a while. So let's see if this will work or not.
8:17:238 hours, 17 minutes, 23 secondsAnd there we go. You can see we now have thinking. The user said hello world. A simple greeting. I'll respond in a
8:17:328 hours, 17 minutes, 32 secondsfriendly way. Brilliant. Uh, so I'm not sure if we implemented the ability to switch models, but can I try with this?
8:17:408 hours, 17 minutes, 40 secondsHello world again.
8:17:438 hours, 17 minutes, 43 secondsUm, I'm not sure if this will it still triggers claw opus 46. Okay, I think that's what we're going to do next.
8:17:508 hours, 17 minutes, 50 secondsWe're going to add the ability to switch models, but you can see that now we have thinking and we can see exactly what AI
8:17:578 hours, 17 minutes, 57 secondsthinks at the moment. Uh, brilliant. So that is step one finished and now we are on to step two.
8:18:098 hours, 18 minutes, 9 secondsLet's go ahead and create the general system prompt. We're going to do that inside of packages server source. And in
8:18:178 hours, 18 minutes, 17 secondshere I'm going to create system dashprompt. DS.
8:18:248 hours, 18 minutes, 24 secondsLet's go ahead and start by importing the mode type from database enums. Let's go ahead and create the system prompt
8:18:328 hours, 18 minutes, 32 secondsparams which can accept the path and the mode. And then let's go ahead and export a function
8:18:408 hours, 18 minutes, 40 secondscalled build system prompt. It will accept the path the mode and it has to
8:18:478 hours, 18 minutes, 47 secondsreturn a string. Let's go ahead and define the parts array. And let's go ahead and start with the very first
8:18:558 hours, 18 minutes, 55 secondspart. So your best bet is to either pause the screen and uh read through and copy or
8:19:048 hours, 19 minutes, 4 secondssimply go inside of the source code or the free assets and copy um
8:19:118 hours, 19 minutes, 11 secondsor ask AI to you know build it for you because it is relatively you know simple.
8:19:188 hours, 19 minutes, 18 secondsNow let's go ahead and check if we have path passed. If we do, we can show we can tell llm what is the user's current
8:19:258 hours, 19 minutes, 25 secondsdirectory. And now let's go ahead and do an if clause. So if mode is plan, we
8:19:328 hours, 19 minutes, 32 secondshave to tell the AI it's in plan mode like this. You are in planning mode.
8:19:388 hours, 19 minutes, 38 secondsYour job is to analyze, research, and propose solutions, but not make changes.
8:19:438 hours, 19 minutes, 43 secondsUse your available tools to explore the codebase. Present your analysis in a clear plan of action. explain trade-offs and ask for clarification when needed.
8:19:528 hours, 19 minutes, 52 secondsElse if we are not in tool calling mode, we are in build mode which means that we can make changes. So let's go ahead and explain AI that you are in build mode.
8:20:028 hours, 20 minutes, 2 secondsYour job is to implement changes directly. Read and understand relevant code before making changes. Use write file to create new files. Edit file for
8:20:108 hours, 20 minutes, 10 secondstargeted modifications. Use bash to run commands, tests, builds, git operations.
8:20:148 hours, 20 minutes, 14 secondsAfter making changes, verify the work when possible. All right.
8:20:218 hours, 20 minutes, 21 secondsAnd now let's go ahead and append to the system prompt what tools are available.
8:20:308 hours, 20 minutes, 30 secondsSo this is what we're going to pass here.
8:20:378 hours, 20 minutes, 37 secondsYou have these tools available. Read file list directory globe and grap.
8:20:438 hours, 20 minutes, 43 secondsFor the rules be decisive. Use glob to find what's relevant. Never reread files you already read. Batch your tool calls.
8:20:528 hours, 20 minutes, 52 secondsCall multiple tools in parallel when possible. Read file fi five files at once, not one at a time. So just some general guidelines here. All right.
8:21:028 hours, 21 minutes, 2 secondsAnd then let's go ahead and do a similar thing for build mode.
8:21:118 hours, 21 minutes, 11 secondsSo this is it. If we have CWD and the mode is build, let's go ahead uh and
8:21:188 hours, 21 minutes, 18 secondsshow it exactly which tools are available. Read file, write file, edit file, list directory, glob, grab and
8:21:268 hours, 21 minutes, 26 secondsbash. Rules, be decisive, never reread files, batch your tool calls, and basically the same thing uh but with the
8:21:348 hours, 21 minutes, 34 secondsaddition of all the new tools it has access to. Let me just indent these.
8:21:408 hours, 21 minutes, 40 secondsBrilliant. And what we have to do now is make sure to join all of those parts. So
8:21:478 hours, 21 minutes, 47 secondsthe end result is just a big string. So we are basically modifying the system prompt depending on if we have the directory the user is in and if we have
8:21:568 hours, 21 minutes, 56 secondsa specified I mean what mode we have specified.
8:22:008 hours, 22 minutesGreat. So that is the system prompt. Now let's go ahead and start building some tools. So, we're going to go inside of source and we're going to create tools.
8:22:138 hours, 22 minutes, 13 secondsAnd in here, let's go ahead and create a new file. Let's start with the bash
8:22:208 hours, 22 minutes, 20 secondstool. So, we're going to be using tool from AI and we're going to be using Z from zod. I'm going to specify some
8:22:298 hours, 22 minutes, 29 secondsdefaults, max output and default timeout. And let's go ahead and create a function which passes along the current
8:22:368 hours, 22 minutes, 36 secondsdirectory we are in. And let's go ahead and return the tool and the tools
8:22:428 hours, 22 minutes, 42 secondsconfiguration. You can find the API for the tool using Verscella's AI SDK. Uh so
8:22:508 hours, 22 minutes, 50 secondsnot providers. If we scroll down, we should find
8:22:578 hours, 22 minutes, 57 secondshow do I uh close all providers and just focus on
8:23:048 hours, 23 minutes, 4 secondsthe tools. Here are the tools and in here you can basically find how they are written. Weather tool description, get
8:23:128 hours, 23 minutes, 12 secondsthe weather in a location, input schema, uh what we need from the user and then the execution. In here you would for
8:23:208 hours, 23 minutes, 20 secondsexample call an API or something like that with the argument. So in our case the weather tool is the bash tool. The
8:23:288 hours, 23 minutes, 28 secondsargument is the users directory and the location is the ability to read files
8:23:348 hours, 23 minutes, 34 secondsright something like that. So let's go ahead and write this one together. Description.
8:23:428 hours, 23 minutes, 42 secondsThen let's go ahead and add the input schema.
8:23:488 hours, 23 minutes, 48 secondsAfter that, let's go ahead and write the execute method which is asynchronous has command
8:23:568 hours, 23 minutes, 56 secondsand timeout. Let's go ahead and open the try and catch method.
8:24:058 hours, 24 minutes, 5 secondsInside of try, let's go ahead and use bun to spawn some processes.
8:24:128 hours, 24 minutes, 12 secondsLet's go ahead and set the timer.
8:24:168 hours, 24 minutes, 16 secondsLet's go ahead and get some of the responses
8:24:238 hours, 24 minutes, 23 secondsand let's just build the entire thing uh to the end here. I would suggest uh
8:24:308 hours, 24 minutes, 30 secondslooking through my source code when you build these tool calls. They can mostly be improved by using other AI tools and
8:24:378 hours, 24 minutes, 37 secondsI would highly recommend doing so and make sure you capture the error. And that's for example uh one of the tools
8:24:468 hours, 24 minutes, 46 secondswe are going to have. Let's go ahead and do another tool. So I'm going to copy this and paste it. I'm going to call this edit file.
8:24:588 hours, 24 minutes, 58 secondsLet's go inside of edit file here. Let's go ahead and update our imports. Resolve relative from path. Read file write file
8:25:068 hours, 25 minutes, 6 secondsfrom FS promises tool from AI. Z from zod. And we no longer need these constants. Let's go ahead and change
8:25:148 hours, 25 minutes, 14 secondsthis to be create edit file tool. Then let's go ahead and modify the tool configuration here. So take a look at
8:25:228 hours, 25 minutes, 22 secondsthe new description I have added and take a look at the new input schema that I have added for here which means that
8:25:308 hours, 25 minutes, 30 secondsthe execute function is also going to be modified. So I'm going to go ahead and replace this with path old string and
8:25:378 hours, 25 minutes, 37 secondsnew string. Uh, and now in here we're also going to go ahead and write the new uh, execute function. So I'm going to go
8:25:468 hours, 25 minutes, 46 secondsahead and clear everything I have inside.
8:25:508 hours, 25 minutes, 50 secondsSo the execute function will start by resolving the current path. And if the whatever was resolved does not start
8:25:588 hours, 25 minutes, 58 secondswith what we have passed as the argument, it means that the path is outside of the project directory and we are not going to allow the LLM to do
8:26:058 hours, 26 minutes, 5 secondsanything with that file. regarding file editing. So just some safety here. Now
8:26:128 hours, 26 minutes, 12 secondslet's go ahead and attempt to read the file that we are trying to edit. Let's find the occurrences. If there are no
8:26:208 hours, 26 minutes, 20 secondsoccurrences, let's go ahead and throw an error. If the occurrences are greater than one, it means we found too many of
8:26:288 hours, 26 minutes, 28 secondsthem. So we need more context. Perhaps another tool call to specify which file we are we need. Other than that, we have
8:26:368 hours, 26 minutes, 36 secondsupdated the file by replacing the context. So, let's go ahead and write that file and let's return the success.
8:26:448 hours, 26 minutes, 44 secondsAnd in the catch method, let's go ahead and grab the error here.
8:26:498 hours, 26 minutes, 49 secondsAnd let's go ahead and return the following. Great. Another tool finished.
8:26:568 hours, 26 minutes, 56 secondsLet's go ahead and continue by building the globe tool. Uh I'm going to go ahead and copy bash again. And I'm going to rename it to globe.
8:27:078 hours, 27 minutes, 7 secondsSo for the globe tool, let's go ahead and change some patterns again resolve relative tool Z max results.
8:27:178 hours, 27 minutes, 17 secondsLet's go ahead and change this to be create globe tool. Then let's go ahead and modify all of the parameters here.
8:27:268 hours, 27 minutes, 26 secondsSo take a look at the new description.
8:27:288 hours, 27 minutes, 28 secondsTake a look at the new input schema which I have added here.
8:27:328 hours, 27 minutes, 32 secondsNow let's go ahead and change the execute method. So the execute method is going to be working with pattern and
8:27:408 hours, 27 minutes, 40 secondswith path. Let's go ahead and start by resolving things first.
8:27:478 hours, 27 minutes, 47 secondsSo check if we are outside of the current directory. Then inside of try method.
8:27:568 hours, 27 minutes, 56 secondsLet me go ahead and try to clean everything inside of the try method quickly. So inside of the try method, let's go ahead and get
8:28:068 hours, 28 minutes, 6 secondsuh bun. Globe running.
8:28:128 hours, 28 minutes, 12 secondsThen let's go ahead and run uh an await here for match of glob scan.
8:28:258 hours, 28 minutes, 25 secondsLet's go ahead and skip node modules for example. This is where you would, you know, improve the tool even further.
8:28:338 hours, 28 minutes, 33 secondsLet's go ahead and make sure we don't go over the maximum amount of results.
8:28:388 hours, 28 minutes, 38 secondsReturn paths relative to the project root.
8:28:448 hours, 28 minutes, 44 secondsThat's all for the loop. And now inside of here, let's just run files.
8:28:518 hours, 28 minutes, 51 secondsAnd let's go ahead and return. There are many opportunities for improvement over these tools. This is just to give you the basic idea of how they work, of
8:29:008 hours, 29 minutescourse. Uh, beautiful. That is our globe tool. Let's go ahead and copy globe, paste it. Let's go ahead and add grap tool.
8:29:108 hours, 29 minutes, 10 secondsSo, our grap tool will once again have a constant, but it's going to be max matches. Uh, the imports are all going
8:29:198 hours, 29 minutes, 19 secondsto be the same. The function name will be different. Create grab tool. And let's go ahead and modify the description and the input schema.
8:29:328 hours, 29 minutes, 32 secondsSo take a look at the new description and the new input schema.
8:29:388 hours, 29 minutes, 38 secondsNow let's go ahead and extend this with include and keep the pattern and the path. The
8:29:458 hours, 29 minutes, 45 secondsfirst check stays the same. And then inside of try and catch here, let's go ahead and do something different. So I'm going to clean up the try method.
8:29:568 hours, 29 minutes, 56 secondsI'm going to start by defining the arguments.
8:30:008 hours, 30 minutesI'm then going to go ahead and add the special case if we have include.
8:30:068 hours, 30 minutes, 6 secondsLet's go ahead and spawn a bun process. Let's go ahead and read the output.
8:30:158 hours, 30 minutes, 15 secondsLet's go ahead and await process exited.
8:30:208 hours, 30 minutes, 20 secondsNow, let's go ahead and just do some edge cases here.
8:30:268 hours, 30 minutes, 26 secondsSo, I've added these two if clauses.
8:30:318 hours, 30 minutes, 31 secondsNow, let's go ahead and prepare some lines. We're going to print and some matches. And we are going to append them
8:30:398 hours, 30 minutes, 39 secondsby running a for loop over all of the lines.
8:30:458 hours, 30 minutes, 45 secondsLet's go ahead and wrap up the for loop by spec specifying the format that we want.
8:30:558 hours, 30 minutes, 55 secondsSo whenever we grab something, we are going to display it in the following format so that the user can see what the tool is currently doing.
8:31:078 hours, 31 minutes, 7 secondsAll right. And then in here, let's go ahead and return the matches.
8:31:138 hours, 31 minutes, 13 secondsAnd let's leave the error as is.
8:31:178 hours, 31 minutes, 17 secondsUh, great. So, now let's go ahead and add uh three more tools. I'm going to
8:31:258 hours, 31 minutes, 25 secondsspeed up this process a bit. So, I'm going to go ahead and go inside of
8:31:348 hours, 31 minutes, 34 secondsthis create write file. DS.
8:31:398 hours, 31 minutes, 39 secondsI'm going to go ahead and add all of the imports.
8:31:438 hours, 31 minutes, 43 secondsThen I'm going to go ahead and add the function once again.
8:31:508 hours, 31 minutes, 50 secondsAnd I'm going to return the tool instance.
8:31:578 hours, 31 minutes, 57 secondsAnd then we're going to go ahead and I'm just going to write the entire execute.
8:32:038 hours, 32 minutes, 3 secondsAnd then I'm going to slowly go over it just so we speed up this process here.
8:32:088 hours, 32 minutes, 8 secondsSo this is the description, the input schema and here is the execute function. So again we start by resolving the path.
8:32:168 hours, 32 minutes, 16 secondsWe go ahead and attempt to write the file very simply.
8:32:218 hours, 32 minutes, 21 secondsWe even do new directories if needed. Uh I really chose the shortest one to speed up. Yeah, this one is not even that
8:32:308 hours, 32 minutes, 30 secondscomplicated. And the error catching is exactly the same.
8:32:348 hours, 32 minutes, 34 secondsUh great that is a write file. Now let's go ahead and do read file.ts.
8:32:448 hours, 32 minutes, 44 secondsSo again I'm going to go ahead and add imports. So these are the imports which
8:32:518 hours, 32 minutes, 51 secondswe are going to need. I'm going to add a constant maximum file size. I'm going to rename this to create read file tool.
8:32:598 hours, 32 minutes, 59 secondsI'm going to replace the description and the input schema. So, take a look at the new description here and the new input
8:33:078 hours, 33 minutes, 7 secondsschema, which means that we only have access to the path here because this is a read uh file tool. And again, I'm just
8:33:158 hours, 33 minutes, 15 secondsgoing to replace the entire execute method so you can see how it looks like now.
8:33:258 hours, 33 minutes, 25 secondsOkay. So take a look at the description in the input schema and this is the new execute method. So we have path we
8:33:348 hours, 33 minutes, 34 secondsresolve the current path and in here we are checking if the path is outside of the project directory. To make this
8:33:438 hours, 33 minutes, 43 secondseasier to read for you I'm going to go ahead and just collapse the if clause like this so you can see
8:33:528 hours, 33 minutes, 52 secondswhat is the actual condition here. So we return an error here if it's trying to read outside of the path directory. Then
8:34:008 hours, 34 minuteswe do the classic to ensure we are still within it. And then inside of here we attempt to read file with some
8:34:078 hours, 34 minutes, 7 secondslimitations uh regarding the maximum file size. And we throw errors in the exact same way. So again I recommend
8:34:158 hours, 34 minutes, 15 secondsjust using my assets file or my source code to get access to what I have written here. But of course you can just
8:34:238 hours, 34 minutes, 23 secondspause the screen if you want to write it yourself. All right.
8:34:298 hours, 34 minutes, 29 secondsUh and there is one more uh tool left and since we've already written like I
8:34:368 hours, 34 minutes, 36 secondsdon't know how many of them I'm just going to one shot this one. Uh so this one is called list directory.ts
8:34:478 hours, 34 minutes, 47 secondsand I'm just going to paste the entire thing inside and we're going to go over it. So these are the imports. This is the function name, the function
8:34:548 hours, 34 minutes, 54 secondsdescription, the input schema. And now we get to the execute part. So again we are working with path only. We check
8:35:018 hours, 35 minutes, 1 secondthat we are within the current directory. We open the try and catch block in here. We do whatever we have to do to list uh directories here.
8:35:148 hours, 35 minutes, 14 secondsWe sort the directory and we return the path, the entries and results. The error stays the same.
8:35:258 hours, 35 minutes, 25 secondsAnd let's go ahead and save read file.
8:35:298 hours, 35 minutes, 29 secondsBeautiful. Uh, now that we have all of those files, let's go ahead inside of tools and let's create index.ts.
8:35:418 hours, 35 minutes, 41 secondsNow, in here, we're going to add all of the imports that we need. And then I'm going to go ahead and export function
8:35:498 hours, 35 minutes, 49 secondscreate tools. I'm going to specify read only tools, which are read file, list,
8:35:568 hours, 35 minutes, 56 secondsdirectory, grap, and globe. I'm going to go ahead and specify if mode is planned to only return those.
8:36:058 hours, 36 minutes, 5 secondsand otherwise I'm going to extend the readonly tools with write file edit file and bash.
8:36:138 hours, 36 minutes, 13 secondsNow that we have all the tools in place, let's go back inside of our server routes chat.ds.
8:36:218 hours, 36 minutes, 21 secondsI'm going to go ahead and expand my imports for AI with step count is. And
8:36:298 hours, 36 minutes, 29 secondsI'm going to go ahead and import my new function called create tools.
8:36:378 hours, 36 minutes, 37 secondsAnd I'm going to import my new function build system prompt. I'm going to go
8:36:448 hours, 36 minutes, 44 secondsahead and find stream params here and I'm going to extend it by adding the current directory like this.
8:36:548 hours, 36 minutes, 54 secondsUh I am then going to go ahead and find where we structure that and make sure that we extract the current directory.
8:37:018 hours, 37 minutes, 1 secondNow here uh and then what I'm going to do is I'm going to define the tools by checking if
8:37:098 hours, 37 minutes, 9 secondswe have current directory then go ahead and create the tools by passing along the current directory otherwise undefined.
8:37:178 hours, 37 minutes, 17 secondsThen I'm going to go down to where we actually call the AI stream text. And in here I'm going to extend it by passing along the system prompt.
8:37:298 hours, 37 minutes, 29 secondsThen I'm going to pass along the tools.
8:37:328 hours, 37 minutes, 32 secondsAnd finally I'm going to go ahead and define a stop when and then if we have tools I'm going to increase the step
8:37:408 hours, 37 minutes, 40 secondscount. I think that the default step count is 20. So in here we kind of more than double it. So it provides for a better user experience. So yes, if after
8:37:498 hours, 37 minutes, 49 seconds50 steps the LLM still can't reach the result, it will most likely fail. In my
8:37:578 hours, 37 minutes, 57 secondsexperience, this is more than enough for almost everything I needed to do. But you can of course play around with it.
8:38:048 hours, 38 minutes, 4 secondsAll right. Uh now let's go ahead and search for stream AI response because we have an error here.
8:38:158 hours, 38 minutes, 15 secondssimply because we have to pass the current directory. Now here as well and
8:38:228 hours, 38 minutes, 22 secondsthere is another stream AI response that we have. So you can just search through it at this point because you will have errors in your
8:38:308 hours, 38 minutes, 30 secondscode. So just add it. And there is one more or maybe there isn't. Yeah, that's it.
8:38:418 hours, 38 minutes, 41 secondsSorry, that's it.
8:38:448 hours, 38 minutes, 44 secondsAll right. So those are all of the changes we need to do in our API route.
8:38:488 hours, 38 minutes, 48 secondsUh so now the next thing we should be doing uh is going inside of our session.tsx.
8:38:598 hours, 38 minutes, 59 secondsActually let me see uh no let's go inside of new session first. Let's go inside of new session first. So screens
8:39:078 hours, 39 minutes, 7 secondsnew session. And in here we can now remove the import for the default chat ID. We no longer need to hardcode it and
8:39:168 hours, 39 minutes, 16 secondswe can just import mode from night code database enums. And then inside inside the new session state schema we can just
8:39:258 hours, 39 minutes, 25 secondsgo ahead and append mode and enum over mode and model which is zstring.
8:39:338 hours, 39 minutes, 33 secondsAnd then we can go ahead and find where we specify the initial message. And we can remove the hard-coded mode and model
8:39:418 hours, 39 minutes, 41 secondsand make both of them dynamic. So they read directly from the state that is uh currently set.
8:39:508 hours, 39 minutes, 50 secondsUh great. And we also have to go down to our rendering and we should add
8:40:008 hours, 40 minutesmode to our user message which we don't yet have but we're going to add any second now. So let's while we are in the screens let's also visit home here.
8:40:138 hours, 40 minutes, 13 secondsLet's go ahead and add use prompt config and text attributes.
8:40:198 hours, 40 minutes, 19 secondsAnd from here we can also extend the handle submit to include the mode and the model. And we can get the mode and
8:40:288 hours, 40 minutes, 28 secondsthe model from use prompt config like that. And let's make sure to just add this to the dependency array.
8:40:408 hours, 40 minutes, 40 secondsLet's go ahead and find uh this box right here. Let's add flex
8:40:468 hours, 40 minutes, 46 secondsdirection column and gap one. And then after the input bar, let's go ahead and
8:40:548 hours, 40 minutes, 54 secondsadd this box which simply indicates to the user that they can press tab to
8:41:008 hours, 41 minutesswitch between the agents. So in here we are purposely sending this over state.
8:41:078 hours, 41 minutes, 7 secondsSo we extracted in the new session over state rather than using the prompt config here simply because this is supposed to be a snapshot of what the
8:41:158 hours, 41 minutes, 15 secondsuser just submitted. So that's why we are not calling use prompt config hook here. Okay.
8:41:228 hours, 41 minutes, 22 secondsUh now let's go ahead instead of the user message.
8:41:278 hours, 41 minutes, 27 secondsSo that's going to be components messages. Let's find the user message here. Let's go ahead and extract mode.
8:41:378 hours, 41 minutes, 37 secondsAnd let's go ahead and import mode. Whoops. Like that.
8:41:448 hours, 41 minutes, 44 secondsAnd let's go ahead and modify the border color here so it matches exactly the mode that the message was sent at at the
8:41:538 hours, 41 minutes, 53 secondstime. So if it was sent in plan mode, keep the border in plan mode color.
8:41:598 hours, 41 minutes, 59 secondsOtherwise, keep it primary. And now you can see that new session error has completely gone away because it accepts mode.
8:42:088 hours, 42 minutes, 8 secondsUh great. So now let's go ahead and go inside of screens session.tsx.
8:42:158 hours, 42 minutes, 15 secondsAnd now we have some errors we have to resolve here. Let's find our night code shared import. And we can now remove the default chat model ID. And let's instead import message parts schema.
8:42:288 hours, 42 minutes, 28 secondsLet's go ahead and import use prompt config from providers prompt config.
8:42:368 hours, 42 minutes, 36 secondsAnd then let's go ahead and go inside of our map database messages here. And in here when
8:42:458 hours, 42 minutes, 45 secondswe return the assistant message, let's go ahead and properly uh send the parts
8:42:528 hours, 42 minutes, 52 secondshere. So parsed parts. And then let's go ahead and iterate over the parts like this.
8:43:038 hours, 43 minutes, 3 secondsAnd then we no longer have to pass along these primitive parts. We can just pass along the proper parts like this.
8:43:158 hours, 43 minutes, 15 secondsThen let's go down here in the chat message. And in the chat message, we have to pass along uh the mode to the user message.
8:43:298 hours, 43 minutes, 29 secondsAnd then we have to go down to our session chat component. And in here, let's go ahead and add use prompt config and extract mode and model.
8:43:418 hours, 43 minutes, 41 secondsAnd let's modify the onsubmit method here to be a bit more intelligent one
8:43:488 hours, 43 minutes, 48 secondscan say by passing submit with user text mode and model from the prompt config.
8:43:578 hours, 43 minutes, 57 secondsUh great. So, what was super important here is that you actually modify this inside of the map database messages
8:44:058 hours, 44 minutes, 5 secondsbecause it's basically now serializing the database messages that we fetch and
8:44:118 hours, 44 minutes, 11 secondsuh making them readable for our well component.
8:44:178 hours, 44 minutes, 17 secondsSo, at this point, you should be able to do full tool calling.
8:44:238 hours, 44 minutes, 23 secondsLet's go ahead and check it out. Let's see if this works. So I'm simply going to start by switching to plan mode and I will ask what mode are you in? Let's
8:44:328 hours, 44 minutes, 32 secondsjust try something super simple like that. Uh you can see that it knows that it is in plan mode. It knows which which
8:44:418 hours, 44 minutes, 41 secondsfiles it can use and it knows what it cannot do and my message is persisted to be written in the plan mode. You can see
8:44:498 hours, 44 minutes, 49 secondsthat this is also purple. If I change this to build and ask how about now
8:44:568 hours, 44 minutes, 56 secondslet's see if it will receive info that it is in the new mode. I am in build mode. Uh perfect. You can see the LLM is
8:45:068 hours, 45 minutes, 6 secondsnot exactly super smart. Uh it cannot distinguish between the fact that it actually was in plan mode before. So I'm
8:45:148 hours, 45 minutes, 14 secondsgoing to switch to plan mode just for safety and I'm going to ask what is this project about?
8:45:218 hours, 45 minutes, 21 secondsAnd let's see if we are going to see any tool calling happening. And here it is.
8:45:268 hours, 45 minutes, 26 secondsList directory, read file, read file, list directory, packages, CLI, server,
8:45:328 hours, 45 minutes, 32 secondsdatabase, shared. It's going very deep into our files here. And you can see this is the thing I was talking about.
8:45:408 hours, 45 minutes, 40 secondsYou can see how all of the tool calls are grouped together. Uh, and that's what the cosmetic part was about. And
8:45:478 hours, 45 minutes, 47 secondsnow it tells you what night code is is a CLI based AI coding assistant similar to tools like cursor either or cloud code.
8:45:558 hours, 45 minutes, 55 secondsSo we succeeded into cloning cloud code because we made anthropic model think that this is similar. Uh brilliant. I'm very very very happy with the result.
8:46:068 hours, 46 minutes, 6 secondsAnd let's try a fun one. Uh, I'm going to switch to build mode and I'm going to tell it uh something like um
8:46:158 hours, 46 minutes, 15 secondscreate a food.js file in my uh root folder put hello world console log
8:46:258 hours, 46 minutes, 25 secondsinside. So let's go ahead and make it do something relatively simple just to check if right file is working. So I can
8:46:338 hours, 46 minutes, 33 secondsalready see that I have another file added here. Let me close everything.
8:46:378 hours, 46 minutes, 37 secondsfu.js. [snorts] It's right here. Hello world. Beautiful.
8:46:458 hours, 46 minutes, 45 secondsAnd what I want to test now is the ability to switch models. So, can I switch to haiku? And let me do hello
8:46:528 hours, 46 minutes, 52 secondsworld. This one should be significantly faster. And it is. It's much faster. And you can see it's clawed haiku. Let me
8:47:008 hours, 47 minutestry and switch to GPT54 Hello World again. And let's see. uh open API key is missing. That is
8:47:098 hours, 47 minutes, 9 secondscertainly correct. Let me go ahead and let me add my open API key.
8:47:168 hours, 47 minutes, 16 secondsSo I just added my open uh AI API key and I think I have to restart my
8:47:248 hours, 47 minutes, 24 secondsserver now because I don't think environment files are handled in hot reload. Let me try hello world again. I
8:47:328 hours, 47 minutes, 32 secondshave to check if I did the reasoning correctly. Uh I don't know if this is supposed to behave like that. Let me try
8:47:398 hours, 47 minutes, 39 secondswith the completely blank one. Uh what is this project about?
8:47:458 hours, 47 minutes, 45 secondsI know so little about open AI models that I don't even know if I'm doing this correctly. It's using the read the tools
8:47:538 hours, 47 minutes, 53 secondswhich is great. That's great news. Uh I'm not sure I'm seeing it thinking though, but it's definitely working. we
8:48:018 hours, 48 minutes, 1 secondare able to you know uh switch models and it's working but I'm just not able to see it thinking uh which tells me
8:48:108 hours, 48 minutes, 10 secondsmost likely that there is a problem inside of our models.ts DS in server here open AI provider options.
8:48:228 hours, 48 minutes, 22 secondsYou know what would be an interesting idea to tell it to look at that file. Let me
8:48:298 hours, 48 minutes, 29 secondstry this. Uh he cannot seem to showcase
8:48:368 hours, 48 minutes, 36 secondsopen AI models thinking in my app. Can you look at
8:48:448 hours, 48 minutes, 44 secondspackages server source lib models and look at open AI provider options?
8:48:548 hours, 48 minutes, 54 secondsThe same solution is working for anthropic.
8:49:018 hours, 49 minutes, 1 secondIs my or are my provider options for open AI incorrect?
8:49:138 hours, 49 minutes, 13 secondsWe are of course going to add a file matching system later, but for now let's just see if this works or not. This will be very interesting. And this is what
8:49:228 hours, 49 minutes, 22 secondssuper fun about this project. We are technically finished with it now. Uh and um
8:49:298 hours, 49 minutes, 29 secondsand we can use it to improve our app. So let's see what's what's going on. Uh check the exact version. Okay.
8:49:408 hours, 49 minutes, 40 secondsWhat's what am I supposed to do? Open air reasoning summary detailed.
8:49:498 hours, 49 minutes, 49 secondsOkay. I'm probably going to do this off screen. Uh, you can maybe play around with this, but yeah, it tells me that it
8:49:568 hours, 49 minutes, 56 secondslooks incorrect for the entropic. It's correct. It's plausible.
8:50:068 hours, 50 minutes, 6 secondsYeah, I'm not really sure which one should I use or not. Never mind. Okay, I
8:50:148 hours, 50 minutes, 14 secondscan't spend too much time on this. I have to end the chapter. But it's super interesting how you can use the project you have just created to help you finish the project you have just created.
8:50:238 hours, 50 minutes, 23 secondsBrilliant, brilliant work. Uh so that marks step two as complete. So chapter 7 tool calling. Let's go ahead and do get
8:50:328 hours, 50 minutes, 32 secondscheckout-b07 tool calling. Get addit commit 07 tool calling.
8:50:438 hours, 50 minutes, 43 secondsget push- origin 07 tool calling.
8:50:498 hours, 50 minutes, 49 secondsAnd that will allow us to open a new pull request and review our changes.
8:50:588 hours, 50 minutes, 58 secondsAnd here we have the summary. We now display AI reasoning and thought process in chat messages. We also added tool
8:51:068 hours, 51 minutes, 6 secondsexecution support, bash commands, file read, write and edit, file search, directory listing. We have plan and
8:51:138 hours, 51 minutes, 13 secondsbuild modes with mode specific tool availability. Plan mode is reen only dynamic system prompts that adapt to
8:51:208 hours, 51 minutes, 20 secondsworking directory and selected mode and some improvements.
8:51:258 hours, 51 minutes, 25 secondsAs you can see, we have a successful uh railway deployment, which is always uh great to con to confirm.
8:51:338 hours, 51 minutes, 33 secondsUh and in here we actually have a lot of comments. Most of them are uh about the system prompt specifically whenever we
8:51:428 hours, 51 minutes, 42 secondsuse the current directory simply because uh the way we are protecting uh our
8:51:498 hours, 51 minutes, 49 secondstools from not going outside of the path guard is not strong enough. I think a interesting way to fix this would be to
8:51:578 hours, 51 minutes, 57 secondsuse the tool we just created to fix itself. I think that will be a very interesting challenge. So for now all of
8:52:058 hours, 52 minutes, 5 secondsthese comments are the same. Basically this resolve starts with it's not uh strong to guarantee that workspace will
8:52:148 hours, 52 minutes, 14 secondsnot escape. That isn't to say this will break our app but yeah it could be unsafe if LLM goes arry and just you
8:52:248 hours, 52 minutes, 24 secondsknow goes over various files on your computer and deletes them, creates them or anything like that.
8:52:318 hours, 52 minutes, 31 secondsSo there is definitely room for improvement with our tool calling. And now that we have this tool that we
8:52:388 hours, 52 minutes, 38 secondscreated, perhaps we can create some cool tools and improvements ourselves. Let's go ahead and merge this pull request.
8:52:458 hours, 52 minutes, 45 secondsOnce again, I'm not going to delete my branch. So I have all of the history here. And then I'm simply going to go
8:52:528 hours, 52 minutes, 52 secondsahead and get checkout main. Get pull origin main. So, all of my changes are
8:52:598 hours, 52 minutes, 59 secondshere. Beautiful. Uh, amazing, amazing job. And see you in the next chapter.
Chapter 11: Completing The User Experience
8:53:068 hours, 53 minutes, 6 secondsIn this chapter, we're going to complete the user experience by adding file mentions and authentication. We're going to implement file mentions by listening
8:53:148 hours, 53 minutes, 14 secondsfor an add sign, which then calls the find active mention, which is going to parse the query token. Once we parse the
8:53:218 hours, 53 minutes, 21 secondstoken, we're going to pass it along to a new function, get mentioned candidates, which will read the directory we are in, filter and sort the results. We will
8:53:318 hours, 53 minutes, 31 secondseither display a direct match or a recursive fallback with maximum of 32 candidates skipping the node modules.
8:53:408 hours, 53 minutes, 40 secondsAnd we're going to display those candidates inside of a new component called file mention menu, which will have an overlay with the scroll box.
8:53:488 hours, 53 minutes, 48 secondsOnce the user selects one of the options and presses enter, depending on if it's a path, we're going to insert it or if
8:53:578 hours, 53 minutes, 57 secondsit's a directory, we're going to traverse further. We're also going to implement a new keyboard layer called mention, which will allow us to press
8:54:058 hours, 54 minutes, 5 secondsescape to dismiss the file mention menu and arrows to navigate up and down. Very similar to what we did with the command
8:54:128 hours, 54 minutes, 12 secondsmenu. And for our authentication, we're going to go ahead and implement a new command called login. Then we're going
8:54:218 hours, 54 minutes, 21 secondsto go ahead and use clerk's outflow and open the browser to allow the user to create an account, sign in, and allow
8:54:298 hours, 54 minutes, 29 secondspermissions for our CLI app to use clerk.
8:54:338 hours, 54 minutes, 33 secondsWe're going to use something called proof key for code exchange which allows us to build secure oath flows for public
8:54:408 hours, 54 minutes, 40 secondsclients like mobile and browserbased apps or in our case a terminal app. Once the user is authorized, we're going to
8:54:498 hours, 54 minutes, 49 secondsredirect to a local callback server which we are going to host on bun.serf on a random port. That server will
8:54:568 hours, 54 minutes, 56 secondsreceive a code which we are going to exchange for an access token and we are going to write it to a config file like this one. We are going to build this
8:55:058 hours, 55 minutes, 5 secondsfile with owner only permissions. So in case there's any malware, it's not going to be able to steal it that easily. Once
8:55:128 hours, 55 minutes, 12 secondswe have that token stored, our API client is going to add it to bearer header and then we're going to implement
8:55:198 hours, 55 minutes, 19 secondsa new middleware with hono called require out which will use clerk's SDK to verify the JSON web token we just
8:55:278 hours, 55 minutes, 27 secondsstored. If we receive back a user ID, we are going to finally have user scoped sessions and messages and everything
8:55:348 hours, 55 minutes, 34 secondselse. Otherwise, we're going to return back 401 unauthorized. And finally log out command is going to clear the out
8:55:428 hours, 55 minutes, 42 secondstoken that we have stored. Let me show you all of this in action. So first of all file mentions for example what is
8:55:508 hours, 55 minutes, 50 secondsthe content of this file. And in here I can go inside of packages. I can go ahead and manually type in further. I
8:55:598 hours, 55 minutes, 59 secondscan go ahead and select and basically I keep selecting and I keep seeing the menu until I either press space or until
8:56:078 hours, 56 minutes, 7 secondsI select something and take a look at something. If I go ahead and press enter, I'm getting an error. I am unauthorized which means I have to run
8:56:168 hours, 56 minutes, 16 secondslogin and in here you can see we don't have to build the login screen or anything. Uh all of this is handled by
8:56:258 hours, 56 minutes, 25 secondsclerk. the social login, the register screen, the sign-in screen, and finally the permission screen to allow night
8:56:328 hours, 56 minutes, 32 secondscode to use all of this information from the uh OOT scopes that we have selected.
8:56:378 hours, 56 minutes, 37 secondsAnd once you select allow, you will see that you are signed in. And you can go ahead and try again. Hello world. What is enums
8:56:468 hours, 56 minutes, 46 secondsfile used for? And you will now be able to create user ID scoped sessions. And
8:56:558 hours, 56 minutes, 55 secondsyou will also, as you can see, be able to tag exact files and get output uh
8:57:018 hours, 57 minutes, 1 secondabout that specific selection. So that is the goal of this chapter. Let's go ahead and implement it together.
8:57:128 hours, 57 minutes, 12 secondsLet's get started and let's implement the file mention functionality. For that, we have to revisit our input bar component. Let's go ahead and add a few
8:57:208 hours, 57 minutes, 20 secondsmore imports. At the top I'm going to add read directory is absolute relative and resolve from node path. Then I'm
8:57:298 hours, 57 minutes, 29 secondsgoing to go ahead and add use state to my react import. And I'm also going to
8:57:378 hours, 57 minutes, 37 secondsadd one type ref object from react.
8:57:438 hours, 57 minutes, 43 secondsThen I'm also going to add text attributes from open toy core. And
8:57:518 hours, 57 minutes, 51 secondsI'm going to extend my open to record type imports by also having scroll box
8:57:578 hours, 57 minutes, 57 secondsrenderable like that. Now let's go ahead and add constants needed to develop our
8:58:058 hours, 58 minutes, 5 secondstraversing functions. So maximum visible mentions current directory maximum fallback mention candidates mention
8:58:128 hours, 58 minutes, 12 secondsquery character and recursive mention ignore directories in which you can put whatever directories you want to ignore when traversing. Let's go ahead and
8:58:208 hours, 58 minutes, 20 secondsdefine some types. We are going to need a mention match and a mention candidate.
8:58:278 hours, 58 minutes, 27 secondsNow let's go ahead and develop a function is within current directory.
8:58:328 hours, 58 minutes, 32 secondsThis will help us safeguard the searches and traversing so we don't go outside of the current users directory.
8:58:408 hours, 58 minutes, 40 secondsNow let's go ahead and develop a function is mention query character. So we don't have to do the reg x text text
8:58:478 hours, 58 minutes, 47 secondstest every time. We can just call this function instead.
8:58:518 hours, 58 minutes, 51 secondsNow let's go ahead and develop the find active mention function which takes in the text and the cursor offset. Let's start with defining the safe offset.
8:59:038 hours, 59 minutes, 3 secondsLet's go ahead and do a while loop over the start. Let's go ahead and do the same over the end but in the opposite
8:59:118 hours, 59 minutes, 11 secondsdirection. This is to ensure that the user is indeed trying to mention a file and not typing like an email or trying
8:59:208 hours, 59 minutes, 20 secondsto add an ad sign like this. So just making sure of any edge cases and covering them. Let's go ahead and add token relative cursor and mention start.
8:59:348 hours, 59 minutes, 34 secondsLet's go ahead and do an early return of mention uh if mention start is negative.
8:59:408 hours, 59 minutes, 40 secondsSo again another edge case we are covering here. Let's do the same for the previous character here.
8:59:488 hours, 59 minutes, 48 secondsLet's go ahead and check mention end and see if we should increase it like that. And finally let's do one more edge
8:59:568 hours, 59 minutes, 56 secondscase check to see if we should do an early return. Otherwise we are safe to pass along the start of dimension end of
9:00:059 hours, 5 secondsdimension and the actual query that the user has typed. So in here in this function we have a bunch of uh like edge cases and early returns simply because
9:00:139 hours, 13 secondswe want to ensure that the user is indeed trying to uh let's say tag a file and not doing anything else. So that's
9:00:229 hours, 22 secondswhy the function looks big. Technically it could be just like this. Uh in here
9:00:279 hours, 27 secondswe are calculating the actual um mention right so from the start of the query to
9:00:359 hours, 35 secondsthe end of the query. uh and we are returning it in this specification like we defined right here in the mention
9:00:449 hours, 44 secondsmatch. All right. Now let's go ahead and develop a function called get mention
9:00:509 hours, 50 secondscandidates which returns a promise of a mention candidate. Let's normalize the query and
9:00:599 hours, 59 secondslet's do an empty array return if it starts with a trailing slash. Actually, that's not a trailing slash. That's a slash in the beginning. So, let's return
9:01:079 hours, 1 minute, 7 secondsan empty array for that case. Otherwise, let's define if we have a trailing slash at the end. So, we know that we have to
9:01:159 hours, 1 minute, 15 secondsload more files after that because it's obviously a folder. So, let's go ahead and get the last slash index.
9:01:259 hours, 1 minute, 25 secondsNow, let's go ahead and get the directory part.
9:01:299 hours, 1 minute, 29 secondsAfter that, let's go ahead and get the name prefix.
9:01:369 hours, 1 minute, 36 secondsAnd then let's go ahead and get the absolute directory.
9:01:429 hours, 1 minute, 42 secondsNow let's check if the absolute directory is not within current directory and do an early return if that's the case. And
9:01:519 hours, 1 minute, 51 secondsnow let's open a try and catch because we're going to use some node async
9:01:589 hours, 1 minute, 58 secondsfunctions here. In the catch, we can already just return an empty array as in nothing found.
9:02:049 hours, 2 minutes, 4 secondsFor the try one, let's go ahead and add uh three constants here. The entries, the lowercase prefix, and the option to
9:02:129 hours, 2 minutes, 12 secondsshow hidden entries if we uh have a dot in our name prefix at the start. So now
9:02:199 hours, 2 minutes, 19 secondswe have to first develop the direct matches.
9:02:249 hours, 2 minutes, 24 secondsSo the direct matches are going to be uh the exact files that we have found that
9:02:329 hours, 2 minutes, 32 secondsmatch that user can select and then later we're going to have to implement recursive fallback so that folders are shown as well. So for the direct matches we have to filter them.
9:02:469 hours, 2 minutes, 46 secondsFirst we filter by hidden entries and if the name doesn't start with a dot and then we filter by checking the lower lowercase prefix.
9:02:579 hours, 2 minutes, 57 secondsOnce we did that, let's go ahead and sort.
9:03:019 hours, 3 minutes, 1 secondSo we sort files first and directory last.
9:03:069 hours, 3 minutes, 6 secondsAnd then let's go ahead and map. And depending on if it's directory or not, we go ahead and return that exact uh label in path and kind here.
9:03:199 hours, 3 minutes, 19 secondsNow let's go ahead and check if we can return the direct matches by checking if they are greater than zero and some other edge cases here.
9:03:299 hours, 3 minutes, 29 secondsAnd now we have to do the same but for fallback matches. So let's define an array here. And now we're going to
9:03:379 hours, 3 minutes, 37 secondsdevelop a recursive function called visit which will be able to call itself until it reaches the end of a folder. So it's going to take in two arguments absolute directory and directory part.
9:03:509 hours, 3 minutes, 50 secondsWe're going to start by grabbing the entries from the absolute directory. And then for each entry that we find let's
9:03:589 hours, 3 minutes, 58 secondsgo ahead and traverse through it. So first things first we go ahead and do some early continues here.
9:04:079 hours, 4 minutes, 7 secondsSo in here we check if it's directory and if it is supposed to be ignored. So we do an early ignore here like node
9:04:159 hours, 4 minutes, 15 secondsmodules otherwise we go ahead and we extract the path and the kind of the entry.
9:04:279 hours, 4 minutes, 27 secondsSo let me go ahead and show you how this one is supposed to look like so you can easily copy it.
9:04:329 hours, 4 minutes, 32 secondsNow let's go ahead and check if the entry name starts with the prefix. If it does, we are going to push it to
9:04:419 hours, 4 minutes, 41 secondsfallback matches and we are going to immediately limit if it has reached 32 which is the limit we have set up. Now
9:04:509 hours, 4 minutes, 50 secondswe have to check if the entry is directory and if it is we have to visit
9:04:579 hours, 4 minutes, 57 secondsit again. So essentially we are recursively calling the visit function itself until it reaches the end or in
9:05:069 hours, 5 minutes, 6 secondsother words until it reaches 32 candidates. So that's how we are going to uh find all of the other ones.
9:05:159 hours, 5 minutes, 15 secondsWhen I say all of the other ones I mean all matches which are not direct matches. And now we have to call the visit function for the first time with the current directory. And then the
9:05:249 hours, 5 minutes, 24 secondsvisit function itself can call any subsequent directories that it needs to call. And what we have to do at the end
9:05:329 hours, 5 minutes, 32 secondsis return fallback matches because we can uh we are awaiting them which means that we can return after this line. And
9:05:409 hours, 5 minutes, 40 secondsfallback matches will be an array in which we can then sort our paths. And in the catch just do a return like this.
9:05:499 hours, 5 minutes, 49 secondsGreat. So now that we have this, we have to develop the file mention component.
9:05:569 hours, 5 minutes, 56 secondsSo let's go ahead and add the props for the file mention. Then let's go ahead and develop the file mention menu component. In here, we're going to
9:06:059 hours, 6 minutes, 5 secondsassign the colors and we're going to assign the visible height to know when to trigger an overflow. Let's do an
9:06:139 hours, 6 minutes, 13 secondsearly return. If we detect that the count bitates are zero, so we can immediately show to the user that there's nothing to be seen here.
9:06:239 hours, 6 minutes, 23 secondsAnd let's go ahead and return a scroll box.
9:06:289 hours, 6 minutes, 28 secondsSo let me add the close tag for the scroll box here. And within the scroll box, all that we're going to do is we're going to map over our candidates.
9:06:399 hours, 6 minutes, 39 secondsSo let's keep track of the candidate that is currently selected. So the user knows what they are highlighting and what will be selected if they press
9:06:479 hours, 6 minutes, 47 secondsenter. And in the return here we are going to go ahead and render a box with
9:06:549 hours, 6 minutes, 54 secondsa key some flex and padding the background color which changes if the user selects I mean hover over the
9:07:019 hours, 7 minutes, 1 secondcurrent option on mouse down which uh triggers the on select and on mouse sorry on mouse move and on mouse down
9:07:099 hours, 7 minutes, 9 secondswhich will actually execute uh that path. And within the box, we're going to have one container for the candidate
9:07:189 hours, 7 minutes, 18 secondspath, which again is going to be different depending on if selected or not. And then next to it, we're going to have another box, which will simply
9:07:269 hours, 7 minutes, 26 secondsindicate if this is a folder or a file with again different foreground color if selected or not. So we show uh a
9:07:359 hours, 7 minutes, 35 secondscontrast. Great. So just as we've seen in the initial demo. Brilliant. So that
9:07:429 hours, 7 minutes, 42 secondsis actually it for the file mention menu and these functions above. But what we have to do now is we have to implement
9:07:499 hours, 7 minutes, 49 secondsall of the keyboard layer logic and basically all of the uh user experience that comes in with hovering with your
9:07:579 hours, 7 minutes, 57 secondscursor and your keyboard up and down. So basically the same thing we had to do for the command menu. So this is where it gets a little bit complicated but
9:08:069 hours, 8 minutes, 6 secondsit's all worth it for a good user experience. Let me go ahead and add some new refs here inside of the input bar.
9:08:139 hours, 8 minutes, 13 secondsActive mention ref and mention scroll ref.
9:08:179 hours, 8 minutes, 17 secondsThen I'm going to go ahead and find the keyboard layer and I'm going to add push and pop to it. Then I'm going to go
9:08:269 hours, 8 minutes, 26 secondsahead and I'm just going to add some new states here.
9:08:319 hours, 8 minutes, 31 secondsactive mention a mention candidates and mention selected index null empty array and zero as the initial values
9:08:409 hours, 8 minutes, 40 secondsthen I'm going to go ahead and define a constant of which tracks whether we should show the mention menu or not so
9:08:499 hours, 8 minutes, 49 secondssimilar to how we have show command menu I'm going to keep track if I should show the mention menu by checking if I have
9:08:569 hours, 8 minutes, 56 secondsan active mention now uh let's go ahead head and develop a
9:09:029 hours, 9 minutes, 2 secondsfunction called close mention menu. So I'm just going to go ahead and put it here.
9:09:099 hours, 9 minutes, 9 secondsIt's going to reset the mention ref set the state to null. Reset this to an array and it's going to remove mention
9:09:169 hours, 9 minutes, 16 secondsfrom the keyboard array uh array and we have to add pop to the dependency array here. Now let's go ahead and develop a syncment mention menu component.
9:09:309 hours, 9 minutes, 30 secondsSo syncment mention menu accepts a text and a cursor offset. And in here we're going to call our functions above to
9:09:389 hours, 9 minutes, 38 secondsfind an active mention. We're going to go ahead and add previous mention and we're going to detect whether a mention
9:09:469 hours, 9 minutes, 46 secondshas changed or not because syncment mention menu can be called from various places. Let me just indent this properly.
9:09:549 hours, 9 minutes, 54 secondsUh uh let me just check am I doing this correctly? I think I am. Okay. So we have the next mention, we have the
9:10:039 hours, 10 minutes, 3 secondsprevious mention and with those two we can detect whether a mention was actually changed or not because if it's not changed uh in that case we can just
9:10:119 hours, 10 minutes, 11 secondsclose the mention menu like this or we can do an early return.
9:10:209 hours, 10 minutes, 20 secondsNow let's go ahead and set the active mention ref to the next mention. Let's go ahead and set the state set active
9:10:279 hours, 10 minutes, 27 secondsmention to the next mention. And let's go ahead and push it to the keyboard layer. And finally, if the mention
9:10:359 hours, 10 minutes, 35 secondsitself has changed, we also have to reset the selected index to that new mention at the top. And we have to uh
9:10:439 hours, 10 minutes, 43 secondsscroll to the top as well. So basically what this means is uh are there any new mentions? Did the user type in anything
9:10:519 hours, 10 minutes, 51 secondsnew? So that we have to basically synchronize the mention menu. So we are basically checking is there anything
9:10:589 hours, 10 minutes, 58 secondsnew? If it is let's go ahead and push those changes now. Great. So in the dependency array make sure you have
9:11:059 hours, 11 minutes, 5 secondsclose menu and make sure uh that you have push here. Let me just check is this properly indented or not.
9:11:159 hours, 11 minutes, 15 secondsIf I do it like this. Yeah, I think I have to like indent all of this one back. It doesn't matter for
9:11:229 hours, 11 minutes, 22 secondsfunctionality. I just like my indents to be correct. Uh, okay. So, we now have
9:11:299 hours, 11 minutes, 29 secondsthat. And now let's go ahead and find
9:11:349 hours, 11 minutes, 34 secondshandle text area content change. So make sure that this function is below your
9:11:439 hours, 11 minutes, 43 secondssync mention menu because now every time text area content changes.
9:11:489 hours, 11 minutes, 48 secondsWe also have to pass along uh we also have to execute that function syncment mention menu and we can extract the text
9:11:579 hours, 11 minutes, 57 secondsfrom text area plain text and we now have to populate this dependency array
9:12:039 hours, 12 minutes, 3 secondshere with handle content change which we should have had before and sync mention menu.
9:12:129 hours, 12 minutes, 12 secondsBrilliant. So uh we now have that. So handle text area content change. That looks good. Uh now let's go ahead and
9:12:219 hours, 12 minutes, 21 secondsimplement a new method called handlement mention execute. So I'm going to do that right below handle text area content change.
9:12:329 hours, 12 minutes, 32 secondsAll right. Dependency array like this. Let me fix the indentation.
9:12:409 hours, 12 minutes, 40 secondsAnd here we are. So handle mention execute. In here we are going to basically define what happens when the
9:12:489 hours, 12 minutes, 48 secondsuser decides to execute a mention. So they've selected it and they've pressed enter. What happens for that? We need
9:12:559 hours, 12 minutes, 55 secondsthe text area. We need the mention ref and we need the candidate from the mention candidates and if any of those
9:13:049 hours, 13 minutes, 4 secondsare missing we cannot proceed with this function. So now let's go ahead and check what kind of insertion this is. So
9:13:119 hours, 13 minutes, 11 secondsif it's directory we are inserting the entire path otherwise we are stringifying the path and using that we
9:13:199 hours, 13 minutes, 19 secondscan also generate the new text inside of template literal where we insert text area uh text area plain text and then at
9:13:279 hours, 13 minutes, 27 secondsthe end of the at sign we go ahead and insert whatever we got from the insertion
9:13:359 hours, 13 minutes, 35 secondsand we now have to replace that here and we have to move the cursor to the end of that insertion. And then we have
9:13:449 hours, 13 minutes, 44 secondsthe sync mention menu. And depending if this is a path or a file, it will trigger the visit function recursively again and display even more directories.
9:13:559 hours, 13 minutes, 55 secondsSo that's why we have to sync mention menu. And let's make sure to add uh mention candidates in the syncment mention menu to the dependency array.
9:14:069 hours, 14 minutes, 6 secondsAll right. Uh now let's go ahead and implement another function called handle text area cursor change which gets the
9:14:149 hours, 14 minutes, 14 secondstext area and simply calls the syncment mention menu. That's it. So like an easy way to sync mention menu every time something changes.
9:14:259 hours, 14 minutes, 25 secondsNow let's go ahead and find our use effect.
9:14:299 hours, 14 minutes, 29 secondsHere it is. So wire up the text area submit handlers so it always reads the state. So find this use effect. right
9:14:369 hours, 14 minutes, 36 secondshere. Uh, and let's see what we have to add here. So, we have onsubmit ref.t
9:14:449 hours, 14 minutes, 44 secondscurrent. So, this isn't properly indented. That's why it was confusing me or not. Uh, wait, let me check. Oh, no.
9:14:529 hours, 14 minutes, 52 secondsWe have to do it in the onsubmit ref. My apologies. Okay. So, after we do this return, before we trigger handle submit
9:14:599 hours, 14 minutes, 59 secondsin here, we should check if we have a mention menu. And if we do, we should find the active candidate. And if the active candidate was found, we should
9:15:079 hours, 15 minutes, 7 secondstrigger handlement mention execute and then do an early return. Basically, if the user hits enter, but we have a
9:15:159 hours, 15 minutes, 15 secondsselected candidate, we have to run the handlemention execute function and not the handle submit function. So that's a crucial difference. All right.
9:15:269 hours, 15 minutes, 26 secondsNow uh let's go ahead and uh let me see how many use effect use effects do we have here. Okay, so we have this one.
9:15:389 hours, 15 minutes, 38 secondsUh but do we have any other one? Use effect register the base layer.
9:15:489 hours, 15 minutes, 48 secondsLet's implement another use effect here because we're going to need it to keep the file picker in sync with the current
9:15:559 hours, 15 minutes, 55 secondsmention token. So, let's go ahead and open uh the use effect.
9:16:029 hours, 16 minutes, 2 secondsAnd inside of here, what I'm first going to do is do an early return if there is no active mention. And then I'm going to reset my array. Then I'm going to go
9:16:109 hours, 16 minutes, 10 secondsahead and add a cancelellable ignore here. So I can cancel in case uh an unmount happens. Now we have to define
9:16:199 hours, 16 minutes, 19 secondsan asynchronous function called load candidates. And for that we are going to treat our get mentioned candidates
9:16:279 hours, 16 minutes, 27 secondssimilar to how we would a fetch uh API endpoint, right? Just get us the new next candidates.
9:16:359 hours, 16 minutes, 35 secondsNow we have to before we set any states we have to do an early return. And now if that has passed we can successfully
9:16:449 hours, 16 minutes, 44 secondsset mention candidates. And we can go ahead and set the uh mention selected
9:16:509 hours, 16 minutes, 50 secondsindex. And now we have to actually call load candidates. And we mustn't forget
9:16:579 hours, 16 minutes, 57 secondsto unmount at the end. And let's go ahead and pass the active mention in the dependency array. So that is our new use effect which keeps that in sync.
9:17:119 hours, 17 minutes, 11 secondsNow let's go ahead and register the base layer responder so that we can start controlling uh this file mention menu
9:17:189 hours, 17 minutes, 18 secondswith uh our arrow keys and everything else. So um I'm going to go ahead and see what we already have here. So we
9:17:269 hours, 17 minutes, 26 secondshave a set responder to base. We have text area. Uh everything here actually looks good. But we now need to create a
9:17:369 hours, 17 minutes, 36 secondscompletely new use keyboard here. So let me go ahead and add it. And perhaps let me check if I have any existing ones
9:17:449 hours, 17 minutes, 44 secondswhich I should have right. So let me see. Uh I have this one is top layer
9:17:509 hours, 17 minutes, 50 secondsbase return and I have this one. So just two of them. All right.
9:17:569 hours, 17 minutes, 56 secondsSo in this new one I'm going to go ahead and check if we are disabled and do an early return. Then I'm going to check if
9:18:039 hours, 18 minutes, 3 secondsshow mention menu is not shown and if top layer is not mentioned in that case I'm going to return. Then I'm going to handle the escape scenario. So if the
9:18:139 hours, 18 minutes, 13 secondsuser presses escape I'm going to close the mention menu. Then I'm going to do an else if
9:18:209 hours, 18 minutes, 20 secondswhich is basically what if user presses the up button. If the user presses the up button, we're going to prevent the default. And then we are going to go ahead and set mention selected index.
9:18:339 hours, 18 minutes, 33 secondsWe're going to look through the current index and we're going to calculate which is the next index and scroll to it.
9:18:399 hours, 18 minutes, 39 secondsAnd uh that is actually it for this if clause. Let me see if my indentation is correct.
9:18:489 hours, 18 minutes, 48 secondsUh that's weird.
9:18:529 hours, 18 minutes, 52 secondsOkay. Oh, that's what's weird. Got it. Uh, that is for the up direction. Now we have to do
9:19:019 hours, 19 minutes, 1 secondthe same for down direction. So what happens if we go down? We start with the key prevent default once again. And then
9:19:119 hours, 19 minutes, 11 secondswe go ahead and calculate our index once again. But we have to do it in an opposite direction of course. So first
9:19:199 hours, 19 minutes, 19 secondsthings first, let's see if we can just return zero if there are no mentioned candidates. Otherwise, let's go ahead
9:19:269 hours, 19 minutes, 26 secondsand calculate the next index. Then let's go ahead and get the scroll box.
9:19:339 hours, 19 minutes, 33 secondsIf we are able to get the scroll box, let's go ahead and calculate where we
9:19:399 hours, 19 minutes, 39 secondsshould scroll to. And finally, let's go ahead and return next index. Great.
9:19:489 hours, 19 minutes, 48 secondsSo now what we should do is we should render our new uh file mention menu. So just like we do show command menu. Let's
9:19:569 hours, 19 minutes, 56 secondssee where that ends. Right here we are going to make sure that show command menu is not open and show mention menu
9:20:059 hours, 20 minutes, 5 secondsis open instead. We're going to render a box in which we want to display our file
9:20:129 hours, 20 minutes, 12 secondsmention menu. So this is the box and in here we are going to go ahead and render the actual file mention menu.
9:20:249 hours, 20 minutes, 24 secondsLet's go ahead and insert the file mention menu inside. And then let's go ahead and modify our is disabled by also checking for is top layer like this.
9:20:399 hours, 20 minutes, 39 secondsLet's go ahead and check it here. So packages server source tools bash. What is this
9:20:489 hours, 20 minutes, 48 secondsfunction? Let's switch to plan mode. And if it works, I mean it already works. The rest is on LLM. And
9:20:569 hours, 20 minutes, 56 secondsyou can see how the LLM will now precisely only read uh that file.
9:21:019 hours, 21 minutes, 1 secondBrilliant. So that marks the end of step one. And now we go on to the step two which is clerk out.
9:21:109 hours, 21 minutes, 10 secondsUsing the link on the screen, you can create a completely free clerk account and you're going to get 50,000 monthly
9:21:209 hours, 21 minutes, 20 secondsrecurring users for free. That isn't 50,000 signups. Those are actual users
9:21:279 hours, 21 minutes, 27 secondswhich sign up again and again. So your free tier is not going to be used up by
9:21:339 hours, 21 minutes, 33 secondspeople who drop off after one day. So you have more than enough resources to
9:21:409 hours, 21 minutes, 40 secondshandle an application like this. And that includes B2B authentication all out which we're going to do now.
9:21:499 hours, 21 minutes, 49 secondsLet's go ahead and check it out. So after you create an account using the link on the screen, we have to create a new application. I'm going to go ahead
9:21:579 hours, 21 minutes, 57 secondsand call this night code. Uh I'm going to add an indicator too simply because I have one already so I don't want to get
9:22:039 hours, 22 minutes, 3 secondsit confused. You can add as many of these as you want. All of them will work just fine. I'm going to keep it sing uh
9:22:129 hours, 22 minutes, 12 secondssimple with Google for now. Let's go ahead and create an application. And now what I want to do is I want to go inside
9:22:209 hours, 22 minutes, 20 secondsof configure and I want to go down until we hit uh developers and in here find
9:22:279 hours, 22 minutes, 27 secondsoalf applications. Go ahead and click add oalf application. I'm going to call it night code and for your scopes make
9:22:369 hours, 22 minutes, 36 secondssure you have email profile open ID and offline access. and
9:22:439 hours, 22 minutes, 43 secondsmake sure it is set to public because we're going to be using proof key for exchange flow. So let's go ahead and
9:22:519 hours, 22 minutes, 51 secondsclick add. Now go ahead and copy the client secret as you're not going to see it again.
9:23:009 hours, 23 minutesAnd now that you have that secret, let's go ahead and immediately add it to our environment file. So I'm going to go
9:23:089 hours, 23 minutes, 8 secondsinside of environment here and I'm going to add clerk OAL
9:23:159 hours, 23 minutes, 15 secondsclient secret like this. Beneath it, I'm going to add
9:23:219 hours, 23 minutes, 21 secondsO client ID. So I'm ready for what's next. And that is to copy the client ID
9:23:319 hours, 23 minutes, 31 secondsfrom here. In case you forgot the client secret, you can always regenerate, but keep in mind that that's going to break uh any existing apps.
9:23:409 hours, 23 minutes, 40 secondsAll right. So we now have clerk oath client secret clerk oath client ID. Uh what I'm going to do is I'm also going
9:23:479 hours, 23 minutes, 47 secondsto add them to my environment file here simply. So we have documentation about what's needed. And I'm just going to
9:23:569 hours, 23 minutes, 56 secondsseparate. So this is my these are my AI keys. This is my database URL. This is a generic API URL just so I have some
9:24:059 hours, 24 minutes, 5 secondsseparation here. And I'm going to do the same here. All right.
9:24:129 hours, 24 minutes, 12 secondsNow, let's go ahead and add the rest of the configuration that we need. So, one more key that we're going to need is JWT
9:24:219 hours, 24 minutes, 21 secondssecret, JSON web token secret. And this is something that you generate. But for the sake of simplicity, I would recommend just using some string. So, it
9:24:309 hours, 24 minutes, 30 secondsneeds to be something. It cannot be empty. uh but for now you can just you know either use something to generate it
9:24:379 hours, 24 minutes, 37 secondsor simply use something like JWT secret. Besides that we are also going to need to get our clerk front end API.
9:24:489 hours, 24 minutes, 48 secondsSo let's go ahead and copy that from here. So that we have a bunch of URLs here. You can find your front end API
9:24:569 hours, 24 minutes, 56 secondsURL uh on various ways actually. But yeah, for now let's just go ahead and use the simplest one. So developers uh
9:25:069 hours, 25 minutes, 6 secondslet me see where where was I? Oh applications. Okay, so in here let's just copy the entire link for now.
9:25:169 hours, 25 minutes, 16 secondsLet's paste it and let's just remove everything besides accounts.dev.
9:25:249 hours, 25 minutes, 24 secondsSo basically this is your clerk front end API.
9:25:309 hours, 25 minutes, 30 secondsAnd now we're going to need to prepare two more things. Clerk secret key and
9:25:369 hours, 25 minutes, 36 secondsclerk publishable key. You can find that on the overview screen if you haven't connected yet.
9:25:469 hours, 25 minutes, 46 secondsSo let's go ahead and it it's automatically selecting next.js JS but we are actually I think closer to using
9:25:559 hours, 25 minutes, 55 secondsexpress here and then you will see the type of keys that we need without the next public prefix. So you can copy both of them actually and just add them here.
9:26:049 hours, 26 minutes, 4 secondsSo clerk publishable key and clerk secret key and in your environment example just make sure that you add all
9:26:119 hours, 26 minutes, 11 secondsof these so that you know what you have to add if you were ever to reinitialize this application.
9:26:219 hours, 26 minutes, 21 secondsGreat. And you can leave JVT secret as JVT secret just to indicate that this is something that you have to define yourself. It's not something that you
9:26:309 hours, 26 minutes, 30 secondsget from any dashboard. Uh brilliant. So now that we have that ready,
9:26:379 hours, 26 minutes, 37 secondsuh let's go ahead and build some utils that are going to help us with the Oout login.
9:26:459 hours, 26 minutes, 45 secondsSo in the backend package, we're going to need to add one thing. Let's go inside of packages server
9:26:539 hours, 26 minutes, 53 secondsand let's do bun add at clerk forward slashbackend. So that's the one we are going to need.
9:27:029 hours, 27 minutes, 2 secondsAnd in the CLI bun open. So just open. Uh, open is a
9:27:109 hours, 27 minutes, 10 secondspackage that we're going to use to Oops, I triggered something.
9:27:169 hours, 27 minutes, 16 secondsOpen is a package that we are going to use to safely uh crossplatform open
9:27:239 hours, 27 minutes, 23 secondsbrowsers through a terminal. Otherwise, we would have to implement our own solution.
9:27:309 hours, 27 minutes, 30 secondsSo, let's start by implementing the out lib in the CLI package inside of packages CLI.
9:27:389 hours, 27 minutes, 38 secondsuh source we have lib and now let's create alt ds inside of that file let's
9:27:469 hours, 27 minutes, 46 secondsgo ahead and add the imports that we need let's define the type for out data
9:27:569 hours, 27 minutes, 56 secondsthen let's go ahead and define the al deer and out file so I'm going to store this inside of night code and the file
9:28:059 hours, 28 minutes, 5 secondsname will be aljson So very very similar to my uh where do I
9:28:119 hours, 28 minutes, 11 secondsstore my theme theme index theme uh let me see yes config deer night code
9:28:199 hours, 28 minutes, 19 secondsreferences JSON so in the same place night code but aljson so the first thing we're going to do is
9:28:279 hours, 28 minutes, 27 secondscreate a function called uh get al and it's going to either return the al data or it's going to return null.
9:28:389 hours, 28 minutes, 38 secondsIn the try method, we're going to try and read a file using UTF8 uh encoding and then we're going to
9:28:469 hours, 28 minutes, 46 secondsparse the data as out data. We're going to return a parsed token if it's a type
9:28:539 hours, 28 minutes, 53 secondsof string. Otherwise, we're going to return null. And if there are any errors with reading the actual file, we're going to return null. Uh once again now
9:29:019 hours, 29 minutes, 1 secondlet's create the equivalent function for saving something in the database. So save out and the first thing we have to
9:29:099 hours, 29 minutes, 9 secondscheck if is the out directory exists and then we are going to create an owner
9:29:169 hours, 29 minutes, 16 secondsonly permission so other users on the machine can't read tokens which is just a basic safety precaution here. So this
9:29:249 hours, 29 minutes, 24 secondsis the mode that we're using to create that file uh that directory. And then inside of that directory, we use the
9:29:319 hours, 29 minutes, 31 secondsexact same mode uh to write the file in it. And finally, let's go ahead and create a clear out function which
9:29:399 hours, 29 minutes, 39 secondsbasically just unlinks the file or an empty catch because this just means the file doesn't exist.
9:29:489 hours, 29 minutes, 48 secondsNow let's implement our o util. So again inside of lib create a new file oalf.ds.
9:29:569 hours, 29 minutes, 56 secondsThis is where we are actually going to have uh all of that logic happening right. So o flow which opens the browser
9:30:049 hours, 30 minutes, 4 secondslocal callback server exchange code and finally calling the save out file. So we
9:30:119 hours, 30 minutes, 11 secondsare going to start by importing open from open which we've just installed.
9:30:169 hours, 30 minutes, 16 secondssave out from dot slash out a login timeout in milliseconds. Then we're
9:30:239 hours, 30 minutes, 23 secondsgoing to define the Oout state. We're going to add a helper function to base 64 URL. Then we're going to create a
9:30:329 hours, 30 minutes, 32 secondsfunction that's going to create the challenge for PCE and it's going to accept a verifier and
9:30:399 hours, 30 minutes, 39 secondsit's going to use crypto to create a proper challenge.
9:30:459 hours, 30 minutes, 45 secondsNow let's go ahead and create a helper function to encode state.
9:30:539 hours, 30 minutes, 53 secondsNow let's go ahead and create a function to decode state. So let's go ahead and first throw
9:31:019 hours, 31 minutes, 1 secondan early error if it's invalid and otherwise we can go ahead and parse it.
9:31:089 hours, 31 minutes, 8 secondsNow, let's go ahead and grab a helper to get an error message from an error. And
9:31:159 hours, 31 minutes, 15 secondsnow, let's import the actual perform login function. So, in here, we're going to need to set up three things. First,
9:31:239 hours, 31 minutes, 23 secondsthe clerk front end API, client ID, and API URL. So, double check that all three
9:31:329 hours, 31 minutes, 32 secondsexist here. What I recommend doing is literally copying things. For example, I'm going to copy clerk front end API
9:31:419 hours, 31 minutes, 41 secondsand paste it here. I'm going to copy clerk oath client ID, find it, and paste it here just to double check that there
9:31:489 hours, 31 minutes, 48 secondsare no misspellings because misspellings are often subtle and you don't realize uh what's wrong.
9:31:559 hours, 31 minutes, 55 secondsGreat. And in case any of those are missing, we're going to throw an equivalent error. Let's go ahead and set
9:32:049 hours, 32 minutes, 4 secondsthe nons variable. Let's go ahead and create a code verifier.
9:32:109 hours, 32 minutes, 10 secondsLet's go ahead and set up the code challenge.
9:32:139 hours, 32 minutes, 13 secondsLet's go ahead and set the settled variable to be false. And now let's go ahead and return a promise with some expected types.
9:32:239 hours, 32 minutes, 23 secondsAnd let me just fix this. There we go.
9:32:289 hours, 32 minutes, 28 secondsAnd what we're going to do in here is we're going to start that bun server so that we can accept the token from a
9:32:359 hours, 32 minutes, 35 secondssuccessful Oout login. We're going to use port zero which is going to randomize the port. And then we're going to go ahead and call a fetch function.
9:32:489 hours, 32 minutes, 48 secondsAnd inside of the fetch function, we are going to set up the URL.
9:32:549 hours, 32 minutes, 54 secondsThen we're going to check if the URL path name is not call back and then we're going to return back not found. So
9:33:039 hours, 33 minutes, 3 secondsthis bun server is exclusively listening to call back nothing else. That's its
9:33:099 hours, 33 minutes, 9 secondsonly purpose. Okay. Uh and now let's go
9:33:159 hours, 33 minutes, 15 secondsahead and extract the error if any error exists from the search params.
9:33:239 hours, 33 minutes, 23 secondsIf the error exists, we have to handle it. So let's go ahead and generate or should I say extract the message from
9:33:309 hours, 33 minutes, 30 secondsthese search params. Set the settle to true because we are done with this request. Reject the promise and set the
9:33:409 hours, 33 minutes, 40 secondstime out and then stop the server. So we give it a little buffer and return new response authentication failed with an appropriate status.
9:33:509 hours, 33 minutes, 50 secondsIf we succeed without an error, we can extract code and state from the params.
9:33:589 hours, 33 minutes, 58 secondsNow in case there is no code or state, that means we are in another invalid state. So we can call settled true once
9:34:079 hours, 34 minutes, 7 secondsagain. We can reject. We can set timeout and stop the server and return an early request.
9:34:159 hours, 34 minutes, 15 secondsBut if that's not the case, let's go ahead and actually verify. So we are going to open try
9:34:239 hours, 34 minutes, 23 secondsand catch and we are going to
9:34:329 hours, 34 minutes, 32 secondsestablish the payload by decoding the state.
9:34:359 hours, 34 minutes, 35 secondsAnd if payload nons isn't equivalent to our crypto random UYU ID, we're going to throw a new error state mismatch.
9:34:489 hours, 34 minutes, 48 secondsLet's go ahead and grab the error here.
9:34:529 hours, 34 minutes, 52 secondsAnd in case anything errors, we once again set the settled to true. We reject, we stop the server, and we return back invalid state.
9:35:039 hours, 35 minutes, 3 secondsWhat we have to do now is we have to exchange the authorization code for clerk token. So, open another try and
9:35:119 hours, 35 minutes, 11 secondscatch inside of this one. Let's go ahead and
9:35:199 hours, 35 minutes, 19 secondsset up the redirect URL using our API URL/out/
9:35:259 hours, 35 minutes, 25 secondscallback. And we can get the token response by awaiting
9:35:329 hours, 35 minutes, 32 secondsa fetch request to clerk's front end API O token. And then we have to pass along some options.
9:35:419 hours, 35 minutes, 41 secondsSo how do I know it's going to be OL token here?
9:35:459 hours, 35 minutes, 45 secondsYou can double check that your clerk's front end API is this. And then you can go inside of clerk. And if you go back
9:35:549 hours, 35 minutes, 54 secondsinside of developers oath applications night code and in here
9:36:039 hours, 36 minutes, 3 secondsyou should find all the variations. So here is O token
9:36:119 hours, 36 minutes, 11 secondsand that is exactly what we have constructed here oath token.
9:36:179 hours, 36 minutes, 17 secondsNow we have to specify what kind of fetch request this is. So the method is
9:36:249 hours, 36 minutes, 24 secondspost headers our content type application x www form URL encoded
9:36:339 hours, 36 minutes, 33 secondsand then we have to pass the body that we are sending to the token request. So
9:36:399 hours, 36 minutes, 39 secondsuse new URL search params then pass along the grant type to be authorization code. pass along the code.
9:36:529 hours, 36 minutes, 52 secondsPass along the redirect URL and finally pass along the client ID and
9:37:019 hours, 37 minutes, 1 secondcode verifier. Be mindful of the states.
9:37:069 hours, 37 minutes, 6 secondsGreat. And if the token response is not okay, we then have to await token
9:37:159 hours, 37 minutes, 15 secondsresponse.ext text. So we get the details of the error or we fall back.
9:37:229 hours, 37 minutes, 22 secondsNow let's go ahead and extract the token data if await was successful. So we can
9:37:299 hours, 37 minutes, 29 secondsawait token response JSON and we can cast cast it as the object we we expect.
9:37:359 hours, 37 minutes, 35 secondsAnd at this point everything is going well. So we can set settled to true and we can save out and pass along token
9:37:439 hours, 37 minutes, 43 secondsdata.ac access token. We can resolve the promise with the exact same object and we can stop the server after a timeout.
9:37:539 hours, 37 minutes, 53 secondsAnd finally, we can return new response authenticated. You can close this tab.
9:37:589 hours, 37 minutes, 58 secondsBut in case any error has happened, we do our usual. We again set the settled to true. We reject the promise. We
9:38:079 hours, 38 minutes, 7 secondsattempt to deconstruct the error message. Then we go ahead and stop the server.
9:38:149 hours, 38 minutes, 14 secondsAnd finally, we return a response.
9:38:189 hours, 38 minutes, 18 secondsAuthentication has failed. And once you do a return for every scenario, all of your errors should go away.
9:38:279 hours, 38 minutes, 27 secondsGreat.
9:38:289 hours, 38 minutes, 28 secondsSo now let's go ahead and make sure that this is finished.
9:38:369 hours, 38 minutes, 36 secondsuh and we now have to build a state with port and nons. So let's go ahead and extract port.
9:38:459 hours, 38 minutes, 45 secondsLet's go ahead and check if port is by chance incorrect.
9:38:499 hours, 38 minutes, 49 secondsAnd if it is, we're going to stop the server. We're going to reject and we're going to return.
9:38:579 hours, 38 minutes, 57 secondsNow let's go ahead and define the state and the redirect URL like here. And now let's construct the
9:39:069 hours, 39 minutes, 6 secondsauthorize URL. So clerk front end API o authorize. Again something that you can double check here. O authorize.
9:39:179 hours, 39 minutes, 17 secondsAnd now we have to set the search params for all of our types. So I'm just going to add all of them here and then you can pause the screen and see what they are.
9:39:289 hours, 39 minutes, 28 secondsSo, response type, client ID, redirect, scope, open ID, email, and profile, state, prompt, code challenge, code
9:39:379 hours, 39 minutes, 37 secondschallenge method. There we go. And then let's go ahead and add void open
9:39:449 hours, 39 minutes, 44 secondsauthorize URL to string. And finally, let's go ahead and add set timeout here using login timeout in milliseconds.
9:39:549 hours, 39 minutes, 54 secondsAnd if it wasn't settled within that timeout, we are going to set the settled to true, stop the server and reject that
9:40:019 hours, 40 minutes, 1 secondthe entire thing has timed out. We can no longer log in. Brilliant. So that is the most complicated part of uh this
9:40:109 hours, 40 minutes, 10 secondsimplementation the O uh and the exchange of the codes that we
9:40:169 hours, 40 minutes, 16 secondsneed to perform. So what we can do now is we have to modify our API client. Let
9:40:249 hours, 40 minutes, 24 secondsme go ahead and show you. So inside of packages uh CLI source lib API client, we now
9:40:349 hours, 40 minutes, 34 secondshave to import clear out and get out and we now have to modify the entire API client here.
9:40:469 hours, 40 minutes, 46 secondsSo what I'm going to do is I'm going to add a third I mean a second argument here and open an object like that and
9:40:549 hours, 40 minutes, 54 secondsthen I'm going to add my own fetch here and that's going to be an asynchronous function which will accept an input
9:41:019 hours, 41 minutes, 1 secondwhich is going to be parameters and inside of parameters
9:41:099 hours, 41 minutes, 9 secondswe are going to add type of fetch then we're going to get the first item from There in the second, it's going to
9:41:189 hours, 41 minutes, 18 secondsbe an optional init parameter again using parameters type of fetch and then the second one like that.
9:41:309 hours, 41 minutes, 30 secondsAnd that's going to be an arrow function.
9:41:359 hours, 41 minutes, 35 secondsAnd inside of that arrow function, we are going to initialize the headers. We are going to get the out.
9:41:449 hours, 41 minutes, 44 secondsAnd if out exists, we are going to set the authorization out token.
9:41:539 hours, 41 minutes, 53 secondsAnd then we're going to go ahead and get a response from whatever the user
9:42:009 hours, 42 minutesintended to call. And in case the response is 401, we are always going to
9:42:079 hours, 42 minutes, 7 secondsclear our out token because it means it has become invalid. And finally, let's return response. So we can make this
9:42:169 hours, 42 minutes, 16 secondsinput more readable by collapsing the parameters here. So you can see how it looks like. Great. So now every single
9:42:259 hours, 42 minutes, 25 secondsAPI client is passing along our out whether it has one or if it hasn't. So far nothing will really change simply
9:42:349 hours, 42 minutes, 34 secondsbecause we we are not with changing our API at this point. So let's go ahead and go inside of packages. Let's go inside
9:42:429 hours, 42 minutes, 42 secondsof CLI source components. Let's go inside of a command menu and in commands and at the top here I'm going to add
9:42:519 hours, 42 minutes, 51 secondsperform login and I'm going to add clear out. I'm going to find the login method and I'm going to change this action and make it asynchronous.
9:43:029 hours, 43 minutes, 2 secondsI'm going to leave the toast as is and then I'm going to go ahead and open a
9:43:079 hours, 43 minutes, 7 secondstry and catch at uh method inside of try
9:43:149 hours, 43 minutes, 14 secondsI'm going to perform login and after it awaits I'm going to successfully show that it's been logged in.
9:43:259 hours, 43 minutes, 25 secondsNow in case any error happens regardless timeout or user denies permission we're going to try and show that error message to the user.
9:43:379 hours, 43 minutes, 37 secondsSo let's get the error message and then we're just going to go ahead and show that to the user in a error variant. Now let's go ahead and find the log out.
9:43:489 hours, 43 minutes, 48 secondsAnd this one will be even simpler. So just clear out. As simple as that. So let's go ahead and try it out.
9:44:009 hours, 44 minutesSo go ahead and do let's go to the root first.
9:44:069 hours, 44 minutes, 6 secondsbun rundev cli and you should now have a log out which you will simply clear the file nothing should happen here and you
9:44:149 hours, 44 minutes, 14 secondsshould have login which should open the browser now I'm going to show you the error that
9:44:239 hours, 44 minutes, 23 secondsI got so the request is missing a required parameter includes an invalid parameter value includes a parameter
9:44:309 hours, 44 minutes, 30 secondsmore than once or is otherwise malformed the redirect URI parameter does not match any of the all outs pre-register
9:44:389 hours, 44 minutes, 38 secondsredirect URLs. So what are we doing wrong? Well, we forgot to add our call back URL which I defined here.
9:44:489 hours, 44 minutes, 48 secondsOh, actually I didn't. Oh yeah. So we we forgot to define our call back URL. So let's go ahead go inside of our oath
9:44:589 hours, 44 minutes, 58 secondshere and let's ensure that we support HTTP localhost
9:45:059 hours, 45 minutes, 5 seconds3000 o call back and click add URI and click save. So HTTP is the protocol 3000 is the port.
9:45:179 hours, 45 minutes, 17 secondsLet's go ahead and try once more.
9:45:229 hours, 45 minutes, 22 secondsAnd this time it appears to be successful. So I'm going to go ahead and log in.
9:45:289 hours, 45 minutes, 28 secondsAnd after I've logged in, you can see uh Night Code wants to access Night Code 2 on behalf of whoever you logged in with.
9:45:379 hours, 45 minutes, 37 secondsMake sure that you trust this. And let's go ahead and hit allow. Uh and looks like I'm redirected to a 404 not found.
9:45:459 hours, 45 minutes, 45 secondsSo let me check uh if I forgot to do something here. It should it should have
9:45:529 hours, 45 minutes, 52 secondsredirected me to not not found but instead to an out call back which says successfully logged in.
9:46:039 hours, 46 minutes, 3 secondsSo uh I think I might have started uh the demonstration too early. I'm pretty sure we are missing some things.
9:46:149 hours, 46 minutes, 14 secondsSo we are missing the entire O call back server. This entire thing doesn't exist.
9:46:209 hours, 46 minutes, 20 secondsMy deepest apologies for that. Uh for some reason I thought we were ready to try. Let's go inside of packages server
9:46:299 hours, 46 minutes, 29 secondssource. Let's go inside of lip and let's create our al utils here. So we are going to need create clerk client. Let's
9:46:399 hours, 46 minutes, 39 secondsgo ahead and do some checks in case our environment variables are missing. And once we know they aren't, we can create
9:46:469 hours, 46 minutes, 46 secondsthe clerk client. And then we can go ahead and create a function authenticate
9:46:549 hours, 46 minutes, 54 secondsoath request. In here, we can grab the request state by using clerk client
9:47:019 hours, 47 minutes, 1 secondauthenticate request and accept an oath token. In case it isn't authenticated, we return null. Otherwise, we go ahead
9:47:109 hours, 47 minutes, 10 secondsand get the out property and then we check if the out property is valid. So, if the type is not O token or if it
9:47:189 hours, 47 minutes, 18 secondsdoesn't include user ID, let's return null. Otherwise, let's go ahead and return the proper user ID.
9:47:279 hours, 47 minutes, 27 secondsNow, let's create the callback uh route.
9:47:309 hours, 47 minutes, 30 secondsSo, inside of routes here, I'm going to create ALF. DS instead of routes I'm going to import hono and then I'm simply
9:47:409 hours, 47 minutes, 40 secondsgoing to create one single route that we need the callback route. In here I'm going to extract
9:47:489 hours, 47 minutes, 48 secondscode state and error from the query. I'm going to get the error description if I
9:47:559 hours, 47 minutes, 55 secondshave one. If the error is present, I'm going to do an early return here with the error description.
9:48:049 hours, 48 minutes, 4 secondsIf I'm missing code or state. Oh, let me fix the indentation here. If I'm missing code or state, I'm missing something.
9:48:139 hours, 48 minutes, 13 secondsYou can see login finally timed out. Uh, now let's go ahead and open try and catch.
9:48:239 hours, 48 minutes, 23 secondsInside of try method, let's go ahead and get our encoded from state.
9:48:309 hours, 48 minutes, 30 secondsIf encoded is missing, let's throw invalid state.
9:48:379 hours, 48 minutes, 37 secondsLet's go ahead and get the payload parsed. From the payload, we can deconstruct the port where our temporary
9:48:459 hours, 48 minutes, 45 secondsserver is serving through bun. If that port is incorrect, let's throw. And now we have to construct the redirect URL
9:48:549 hours, 48 minutes, 54 secondsusing localhost port call back and pass along the code encode it. Pass along the state and code it.
9:49:049 hours, 49 minutes, 4 secondsAnd then let's go ahead and redirect the user to that redirect URL. And in the cache method, let's go ahead and return
9:49:129 hours, 49 minutes, 12 secondsinvalid authentication state. And finally, let's export default app. So don't confuse this localhost port with
9:49:219 hours, 49 minutes, 21 secondsour server. Okay, this is where OL is going to redirect after we log in. This
9:49:289 hours, 49 minutes, 28 secondsis the callback and then the call back is going to redirect us to
9:49:369 hours, 49 minutes, 36 secondsthis not sorry oath.ts to this bun server that we are running right. So we get the port and then we
9:49:459 hours, 49 minutes, 45 secondsconstruct it for the O request before we go ahead and do the O token and before we open the browser and everything,
9:49:539 hours, 49 minutes, 53 secondsright? uh we send all of that through the URL and then when the O returns that
9:50:029 hours, 50 minutes, 2 secondsback to us um here we can deconstruct the port and then we
9:50:089 hours, 50 minutes, 8 secondscan redirect to that temporarily open uh local host and then we do a proper
9:50:169 hours, 50 minutes, 16 secondsexchange. So it's it's a little bit complicated flow but uh that is actually the same standard that you see in open
9:50:239 hours, 50 minutes, 23 secondscode uh that you see codeex doing. Uh alternative is enter an API key but it's kind of boring. I thought this is a much
9:50:319 hours, 50 minutes, 31 secondsmore interesting thing to do to allow browser login which somehow automatically tells your CLI yeah he's
9:50:399 hours, 50 minutes, 39 secondslogged in. You can only achieve that by using callbacks through Ooutflow which then redirect to a bun serve that's been initiated through the CLI app itself.
9:50:499 hours, 50 minutes, 49 secondsThat's kind of the only way you can do it. The alternative is device flow but that's a whole other story. But
9:50:569 hours, 50 minutes, 56 secondsbasically you need to have an app uh running a small server running not to be confused with our Hono server. So just a
9:51:049 hours, 51 minutes, 4 secondssmall bun server running initialized through the CLI CLI package and because
9:51:119 hours, 51 minutes, 11 secondsthen this server is basically waiting for the code and the state to tell us that everything is okay right so that's
9:51:199 hours, 51 minutes, 19 secondsthe only way it can immediately immediately save the token and it can immediately tell the user hey you you have successfully logged in from this
9:51:279 hours, 51 minutes, 27 secondsentire other application because we're we are now making two applications communicate your terminal app and your uh browser. So that's why it's complicated.
9:51:379 hours, 51 minutes, 37 secondsUh great. So we now have that. Now that we have our API route, uh we should
9:51:449 hours, 51 minutes, 44 secondsprobably register it. So let's go inside of index.ds. I'm going to go ahead and import ALF.
9:51:549 hours, 51 minutes, 54 secondsAnd let's go ahead and let me chain all of these.
9:52:039 hours, 52 minutes, 3 secondsThere we go. Let me just do proper indentation. So now we have AL. Perfect.
9:52:109 hours, 52 minutes, 10 secondsUh and I think that at this point we can probably try it again. So let me go
9:52:179 hours, 52 minutes, 17 secondsahead and try it with forward slash login which opens the browser and after I click allow there we go authenticated.
9:52:309 hours, 52 minutes, 30 secondsYou can close this tab and I missed it but there was a success message here that popped up. If you are have it side to side uh you are probably seeing it.
9:52:399 hours, 52 minutes, 39 secondsUh beautiful. So that worked but we have a problem. Uh, if I hit log out, nothing really changes. I can still load all of
9:52:479 hours, 52 minutes, 47 secondsmy sessions. Uh, I can still uh send new files, everything, right? So, that isn't how it should be. If the user is logged
9:52:569 hours, 52 minutes, 56 secondsout, they shouldn't be able to do anything. So, let's go ahead inside of
9:53:039 hours, 53 minutes, 3 secondsserver source, let's create a new folder, middleware.
9:53:089 hours, 53 minutes, 8 secondsAnd inside of middleware, let's create require al.ds.
9:53:149 hours, 53 minutes, 14 secondsInside of here, we have to import create middleware from hono factory and authenticate oout request. Let's create
9:53:229 hours, 53 minutes, 22 secondsa type authenticated environment which gives the user ID variable to every context. Now let's go ahead and create
9:53:309 hours, 53 minutes, 30 secondsthe actual middleware which returns back the authenticated environment. So we go a synchronous
9:53:389 hours, 53 minutes, 38 secondsfunction with context and next. We go ahead and open a try method.
9:53:489 hours, 53 minutes, 48 secondsIn the try method, we attempt to authenticate OOT request using C.est.
9:53:579 hours, 53 minutes, 57 secondsIf there is no out, we throw back an error. Otherwise, we are simply going to set the user ID variable to the context.
9:54:059 hours, 54 minutes, 5 secondsSo every subsequent request will have it and we proceed with the next middleware in line.
9:54:139 hours, 54 minutes, 13 secondsAnd in the catch we simply throw. And now that we have the middleware, let's
9:54:219 hours, 54 minutes, 21 secondsgo ahead and assign it where it needs to be. So I'm going to go inside of my index.ds
9:54:289 hours, 54 minutes, 28 secondsand I'm going to import require out. And let's go ahead now above the routes here
9:54:389 hours, 54 minutes, 38 secondsand let's just make sure that every route from session and every route from chat uses require al. So just by doing
9:54:459 hours, 54 minutes, 45 secondsthis if I do hello world I now have an error and I'm not sure if you yeah this
9:54:539 hours, 54 minutes, 53 secondsall of our errors are caught. So we're not seeing any. Uh if you try to load sessions you have an error. anything you
9:55:009 hours, 55 minutestry to do you get an error except of course looking at the models and looking at the agents. So now to make it
9:55:099 hours, 55 minutes, 9 secondsactually work we have to go back inside of our routes here for example uh let's
9:55:169 hours, 55 minutes, 16 secondsgo inside of our sessions and we now have to add type safety for the user ID thing. So find the new hono
9:55:269 hours, 55 minutes, 26 secondsand simply extend it with authenticated environment from the middleware. So we have user ID because that's what we set
9:55:339 hours, 55 minutes, 33 secondsuser ID. That's where we store it if it exists.
9:55:379 hours, 55 minutes, 37 secondsSo what you can now do is everywhere you need to query by the user you can extract the user. So we are no longer
9:55:459 hours, 55 minutes, 45 secondsloading all sessions only those uh which in which this user belongs to.
9:55:529 hours, 55 minutes, 52 secondsAnd now let's go ahead and find the individual get ID one.
9:55:599 hours, 55 minutes, 59 secondsAnd let's also include user ID, a composite index.
9:56:059 hours, 56 minutes, 5 secondsNow let's go ahead and do it in the O request down here as well.
9:56:129 hours, 56 minutes, 12 secondsSo we get the user ID and we no longer use mock user. Instead, we simply use user ID or shorthand operator like this.
9:56:219 hours, 56 minutes, 21 secondsAnd if I search for mock, there are only comments. Perfect. So now sessions can
9:56:289 hours, 56 minutes, 28 secondsonly be created and loaded by a specific user.
9:56:329 hours, 56 minutes, 32 secondsSo let's go ahead and check it out. If I do hello world, nothing works. But if I go through the outflow,
9:56:409 hours, 56 minutes, 40 secondsyou can see I'm now signed in. I did it in my other monitor. And I do hello world. This should be my first session
9:56:489 hours, 56 minutes, 48 secondstied to this account. And as you can see, this time I'm not getting any error. So there we go. And now if I go
9:56:589 hours, 56 minutes, 58 secondsahead and go through my sessions, you can see that I can only see one session here, which is the first session that I did in this account because every other
9:57:079 hours, 57 minutes, 7 secondssession has the mock user as the user ID. So technically uh only if we ever
9:57:149 hours, 57 minutes, 14 secondscreate a user with that ID will be able to read all of those previous sessions. Beautiful uh amazing amazing job.
9:57:249 hours, 57 minutes, 24 secondsNow I just want to wrap it up by adding user ID to a few more places. So let me just copy this definition. Let me go
9:57:329 hours, 57 minutes, 32 secondsinside of chat.ds and in here we create messages. So let's go ahead and add that here.
9:57:419 hours, 57 minutes, 41 secondsLet's import this like that. And for example, if we want to resume a session, we're going to make sure that the
9:57:509 hours, 57 minutes, 50 secondssession whose we are resuming matches the currently logged in uh user ID.
9:57:569 hours, 57 minutes, 56 secondsAnd let's go ahead and do the same thing in initial session ID here
9:58:039 hours, 58 minutes, 3 secondslike that. And let's extend it right here. So nothing much should really
9:58:109 hours, 58 minutes, 10 secondschange at the moment. If I go ahead and type uh can Oh, let me try. Can I type?
9:58:209 hours, 58 minutes, 20 secondsYou can see that it works perfectly fine. But it it worked before as well, but technically someone could abuse the
9:58:279 hours, 58 minutes, 27 secondsAPI. Now they can't. They have to be logged in here as well. Uh beautiful. I
9:58:339 hours, 58 minutes, 33 secondsbelieve that marks uh everything that we intended to do. So that is step two. Let's go ahead and review the changes.
9:58:429 hours, 58 minutes, 42 secondsSo chapter 8 completing the user experience.
9:58:469 hours, 58 minutes, 46 secondsLet me go ahead and get checkout B08 user experience.
9:58:519 hours, 58 minutes, 51 secondsGit addit 08 user experience.
9:58:589 hours, 58 minutes, 58 secondsGet push- origin 08 user experience. And by pushing the branch, we should be able
9:59:079 hours, 59 minutes, 7 secondsto open a new pull request and we should be able to review all the changes.
9:59:149 hours, 59 minutes, 14 secondsLet's go through the notes from code rabbit. So our CLI now supports oout login and logout with browserbased
9:59:219 hours, 59 minutes, 21 secondsauthentication flow which is exactly what we wanted to achieve. We added file and folder mentioned suggestion in the CLI input bar using the add symbol with
9:59:309 hours, 59 minutes, 30 secondskeyboard navigation and selection. All session and chat endpoints now require user authentication. We also have a
9:59:389 hours, 59 minutes, 38 secondssuccessful railway deployment here. Uh we can go ahead and check it out here.
9:59:449 hours, 59 minutes, 44 secondsPerfect. So we know everything is running smoothly. And the cool thing about railway is that it knows how to
9:59:519 hours, 59 minutes, 51 secondswatch for a specific package in your monor repo. You can see these are the watch paths. So even when I create a
9:59:589 hours, 59 minutes, 58 secondspull request which didn't include server, it's not going to rebuild it. So only if it reads the watch path and detects it, that's when it's going to
10:00:0710 hours, 7 secondsrebuild it. Brilliant. And we have some comments from code rabbit. So this is the some lint order warning of the
10:00:1510 hours, 15 secondsenvironment keys. I don't really know anything about that. Feel free to reorder. Uh, of course, a weak JSON web token secret, but we are aware of that.
10:00:2610 hours, 26 secondsIn here, it's giving us a tip that recursive fallback search is too eager for PE per keystroke updates. So, this
10:00:3310 hours, 33 secondsline runs on every mention query change and that can walk the project three recursively and there's until there is
10:00:4010 hours, 40 secondsno direct root match. The ignore flag only prevents stale writes. It does not cancel file system traversal. So typing
10:00:4610 hours, 46 secondscan lag on large repos. Okay. So if you are interested, this is the solution. A
10:00:5410 hours, 54 secondstiny debounce and avoid fallback for tiny prefixes. Really cool actually because yes uh as you try this in a
10:01:0210 hours, 1 minute, 2 secondsbigger repo, it could lead to lag depending on what machine your users are on. So pretty good advice from Code
10:01:1010 hours, 1 minute, 10 secondsRabbit. Feel free to implement this if you uh feel like doing that. Uh in here
10:01:1710 hours, 1 minute, 17 secondsagain a very good advice validate token response shape before accessing access token. That's what I was thinking of
10:01:2510 hours, 1 minute, 25 secondsimmediately when I did a cast here. We could definitely use zod validation like a zod schema and then make sure we have
10:01:3310 hours, 1 minute, 33 secondsparsed data correctly. So again uh great comment by code rabbit here in here.
10:01:4010 hours, 1 minute, 40 secondsgave me a critical issue but it was incorrect. Uh so it told me that if I use middleware this way it won't cover
10:01:4810 hours, 1 minute, 48 secondssessions but it absolutely does. I tested it myself and in the guide of Hono you can see the example is here. So
10:01:5610 hours, 1 minute, 56 secondsnow it's cool because it knows uh this from now on.
10:02:0110 hours, 2 minutes, 1 secondBrilliant. Uh and in here it's also telling us to harden the port validation before redirecting. So again uh we
10:02:1010 hours, 2 minutes, 10 secondsshould probably just ensure that port I mean we already do some hardening here. I guess we can do it even more. Yes.
10:02:1910 hours, 2 minutes, 19 secondsOkay. There's a range that has to be supported. Got it. Again uh a very good suggestion by code rabbit. If you want to feel free to uh improve that as well.
10:02:3010 hours, 2 minutes, 30 secondsBrilliant. So I'm going to go ahead and merge this pull request. I'm not going to delete the branch.
10:02:3610 hours, 2 minutes, 36 secondsInstead, I'm going to go ahead check out to my main GR branch and then gitpool origin main. So, everything is
10:02:4510 hours, 2 minutes, 45 secondsup to date. Brilliant. That marks the end of this chapter, which means we should now have eight branches here.
10:02:5310 hours, 2 minutes, 53 secondsBrilliant. Amazing. Amazing job.
Chapter 12: Usage Based Billing
10:02:5710 hours, 2 minutes, 57 secondsIn this lesson, we're going to implement billing. We're going to do that by introducing the upgrade command and the usage command. The upgrade command is going to open the checkout screen in the
10:03:0510 hours, 3 minutes, 5 secondsuser's browser and user will let them know how many tokens they have left.
10:03:0910 hours, 3 minutes, 9 secondsWe're going to achieve that by using Polar SDK. We're going to implement a new middleware on the server called require credits balance which is going
10:03:1610 hours, 3 minutes, 16 secondsto allow the request if the user has enough credits and deny it if they don't. We're going to use this to guard API endpoints like sessions, chat ID,
10:03:2510 hours, 3 minutes, 25 secondsand chat ID resume. Whenever AI streaming is finished, we're going to extract total usage tokens and we're going to develop a calculate credits for
10:03:3310 hours, 3 minutes, 33 secondsusage function which will extract input and output tokens and multiply them by our pricing multiplier. For that, we're going to use inest AI usage function
10:03:4110 hours, 3 minutes, 41 secondswhich will use Polar's unit economics layer to calculate how much to bill this user. We're going to do this for completed messages but also for
10:03:5010 hours, 3 minutes, 50 secondsinterrupted messages. Whenever our API uh endpoint has been hit and whenever we occur any costs, we are going to
10:03:5710 hours, 3 minutes, 57 secondscalculate how much we should bill the user for that same action. Making our app profitable and monetizable. Let's start by creating an organization with
10:04:0610 hours, 4 minutes, 6 secondsPolar. Head to the link on the screen or just polar.sh and create a new organization which will look something
10:04:1310 hours, 4 minutes, 13 secondslike this. It doesn't really matter what you enter here because once you actually create your first organization, you're
10:04:2110 hours, 4 minutes, 21 secondsgoing to click here and you're going to click go to sandbox. And once you are in sandbox, you're going to have to do it all over again. So in here, I'm going to
10:04:2910 hours, 4 minutes, 29 secondscreate a new organization and I'm going to call it night code tutorial. You can select any payment currency you want and just make sure to agree to Polar's terms.
10:04:3810 hours, 4 minutes, 38 secondsUsing it in here in this sandbox allows you and gives you the freedom to try whatever you want without fear of doing something live. You can see the big
10:04:4710 hours, 4 minutes, 47 secondsbanner here. The changes you make here don't affect your live account. Payments are not processed. So now that we have this dashboard, let's go ahead and set
10:04:5510 hours, 4 minutes, 55 secondsup everything we need to do. Let's start by creating a new meter. So we're going to go inside of products meters and let's go ahead and click the plus button
10:05:0310 hours, 5 minutes, 3 secondshere. Let's give it a name of night code credits. And let's go ahead and create our first filter. The filter condition
10:05:1010 hours, 5 minutes, 10 secondsgroup is going to look for name equals and then we're going to type night code underscore usage and press enter. And
10:05:1810 hours, 5 minutes, 18 secondsthat's going to select it like this. And for the aggregation, select sum over property name credits. Both night code
10:05:2610 hours, 5 minutes, 26 secondsusage and credits are important to be named exactly like this. And then we can just leave this to be scholar. Later we
10:05:3510 hours, 5 minutes, 35 secondsmight actually change it to something else but for now let's leave it like this and make sure that you have this very simple night code credits meter.
10:05:4310 hours, 5 minutes, 43 secondsNow that we have our meter let's create a benefit. So again click on the plus button and let's call this 1,000 credits and let's go ahead and select meter
10:05:5110 hours, 5 minutes, 51 secondscredits as the type. Select a meter night code credits and give the user a,000 credits or a,000 credited units
10:06:0010 hours, 6 minutesdepending on your choice. you can roll over unused credits into the next cycle. I'm not going to do that for simplicity.
10:06:0710 hours, 6 minutes, 7 secondsSo, let's just hit create. And just like that, we now have our benefit which uses the meter which we have just created.
10:06:1310 hours, 6 minutes, 13 secondsFinally, let's create a product. So, click on products once more, new product. Go ahead and give it a name of,000 credits. Make sure it is a
10:06:2110 hours, 6 minutes, 21 secondsone-time purchase. Select whatever currency you prefer and then select a price. I'm going to set it to be $20.
10:06:2910 hours, 6 minutes, 29 secondsAnd for $20 of fixed price, you're going to get a,000 credits using our meter like that. If you scroll down, you can
10:06:3710 hours, 6 minutes, 37 secondsfind metadata, which we don't need to populate ourselves. We can do this programmatically. For the customer portal, select private. So, this is only
10:06:4510 hours, 6 minutes, 45 secondspurchasable via a direct checkout link, which is generated using the API. And in here, you can customize by adding an image and description, which I'm going
10:06:5310 hours, 6 minutes, 53 secondsto skip for simplicity. And just like that, we have our first product which uses the benefit which uses the meter.
10:06:5910 hours, 6 minutes, 59 secondsNow let's go ahead and prepare the environment variables which we're going to need to extract from polar and add to our example and environment. So I'm
10:07:0710 hours, 7 minutes, 7 secondsgoing to start with environment.example here. We're going to need to set polar access token polar product ID polar
10:07:1410 hours, 7 minutes, 14 secondsserver which we can already hardcode to sandbox here just like we did for JVT secret for example and polar credits meter ID. So let's go ahead and add
10:07:2310 hours, 7 minutes, 23 secondsthese and let's immediately copy them and then add them to our real environment file. So I am adding these to my environment in the root folder.
10:07:3310 hours, 7 minutes, 33 secondsAll right. So let's first obtain the polar access token. For that we can go inside of settings here. Scroll down
10:07:4010 hours, 7 minutes, 40 secondsuntil you find developers and hit create token. I'm going to go ahead and call this night code development. I'm going to set the expiration to no expiration.
10:07:4910 hours, 7 minutes, 49 secondsAnd since this is sandboxed and just for development, I'm going to select all of the scopes and down here I'm going to hit create token. Then I'm going to copy
10:07:5710 hours, 7 minutes, 57 secondsthis token here and I'm going to paste it in the environment file. Now let's obtain the product ID. So I'm going to go inside of my products here and I'm
10:08:0610 hours, 8 minutes, 6 secondsgoing to click copy product ID and I'm going to paste that here too. We can leave the polar server to be sandbox. Now let's obtain the credits meter ID.
10:08:1410 hours, 8 minutes, 14 secondsThis one is a little bit tricky because usually uh this is intended to be
10:08:2110 hours, 8 minutes, 21 secondsidentified using the filter condition group and the name night code usage. You can see that it doesn't really give you
10:08:2810 hours, 8 minutes, 28 secondsan option to copy the ID, but you can copy the ID from the URL. If you take a look up here, you will have products and
10:08:3610 hours, 8 minutes, 36 secondsthen meters and then an ID here after the slash. So just copy it here from above and paste it here like that. Even
10:08:4610 hours, 8 minutes, 46 secondsif you end up not managing finding the meter ID, you can still uh finish this by using night code usage filter to find
10:08:5510 hours, 8 minutes, 55 secondsyour meter. Great. So now we have everything we need in regards to the environment file. Now let's go ahead and
10:09:0210 hours, 9 minutes, 2 secondsinstall the polar package into our server. So go inside of packages server and in here let's do bun add polar sh
10:09:1110 hours, 9 minutes, 11 secondsSDK. So just like this let's go ahead and confirm it's been added into the correct place. So inside of server I have package JSON and in here I have
10:09:2010 hours, 9 minutes, 20 secondspolar sh SDK. Now let's create all of the helpers which we're going to need to implement this billing functionality. So I'm going to go inside of packages
10:09:2810 hours, 9 minutes, 28 secondsinside of server source. And here inside of lib I'm going to start with polar.ds.
10:09:3510 hours, 9 minutes, 35 secondsI'm going to go ahead and import polar from polar sh SDK. I'm going to create a type for polar server union. I'm going
10:09:4310 hours, 9 minutes, 43 secondsto create a helper function which will help us check if the environment variable exists or not. I'm going to add get polar access token function. Then
10:09:5110 hours, 9 minutes, 51 secondsI'm going to add get polar product ID and finally get polar credits meter ID.
10:09:5710 hours, 9 minutes, 57 secondsSo these functions are used to check if we have the proper environment files set in our project. Then let's go ahead and
10:10:0410 hours, 10 minutes, 4 secondscreate a function get polar server which returns a polar server. So in here we have to obtain the polar server
10:10:1310 hours, 10 minutes, 13 secondsenvironment variable which if not set will simply fall back to sandbox.
10:10:2010 hours, 10 minutes, 20 secondsSo that's technically in line with all of these other ones that we have but with a fallback. Great. Now let's go
10:10:2710 hours, 10 minutes, 27 secondsahead and actually initialize the new polar like this and give it the access token and server from our helper functions. Let's go ahead and create a
10:10:3610 hours, 10 minutes, 36 secondsfunction has status code so we can properly parse the errors. Let's go ahead and create the create checkout URL
10:10:4410 hours, 10 minutes, 44 secondsparams function sorry type and then let's actually create a function create checkout URL which uses those uh params
10:10:5210 hours, 10 minutes, 52 secondstype here accepts the customer external ID and request URL and simply uses polar checkouts create selects specific
10:11:0110 hours, 11 minutes, 1 secondproducts so the one we have in our environment variable and in the success URL redirects to billing success and
10:11:0910 hours, 11 minutes, 9 secondspasses along the request URL. It maps the external customer ID and adds metadata which you can or don't have to
10:11:1710 hours, 11 minutes, 17 secondshave. It's just useful useful for logging.
10:11:2210 hours, 11 minutes, 22 secondsNow let's go ahead and create a similar function but for invoking the customer portal URL. So this one very similar
10:11:2910 hours, 11 minutes, 29 secondsinstead of polar checkout we do polar customer sessions and we again extract it. uh I mean we scope it using the external customer ID.
10:11:3910 hours, 11 minutes, 39 secondsNow let's go ahead and develop a function for getting the available credits balance.
10:11:4710 hours, 11 minutes, 47 secondsSo we're going to open a try and catch function in here. Let me show you what we're going to do. So inside of try we're going to get customer state. We're
10:11:5410 hours, 11 minutes, 54 secondsgoing to get matching meters by finding by meter ID and using get polar meter id. If we cannot find it, we're going to throw expected exactly one matching
10:12:0310 hours, 12 minutes, 3 secondspolar credits meter. And then from that credits meter, we're going to get it and extract the balance. And in the catch, we're going to check the has status code
10:12:1110 hours, 12 minutes, 11 secondswith the error. And if the status code is 404, we return back a negative. And we throw the error otherwise.
10:12:1910 hours, 12 minutes, 19 secondsNow, let's go ahead and develop a function inest AI usage params.
10:12:2610 hours, 12 minutes, 26 secondsAnd let's make this function here use it. So, ingest AI usage will accept external customer ID, event ID, and
10:12:3410 hours, 12 minutes, 34 secondscredits. And it's going to use the ingest AI usage params. If it doesn't have credits, it's going to return.
10:12:4010 hours, 12 minutes, 40 secondsOtherwise, let's use polar events ingest. And this is important. It needs to call nightcode usage because that is
10:12:4810 hours, 12 minutes, 48 secondsexactly what we've set in this meter, remember. So, open your meter and check that it has night code usage. Okay? It
10:12:5610 hours, 12 minutes, 56 secondsneeds to match exactly. And the metadata credits need to match exactly. It cannot be misspelled misspelled, right? It
10:13:0410 hours, 13 minutes, 4 secondsneeds to be credits because we aggregate over credits. So these two strings are extremely important. All right.
10:13:1310 hours, 13 minutes, 13 secondsSo that is our our polar.ts file. And now let's go ahead and create some other ones. Now let's create
10:13:2110 hours, 13 minutes, 21 secondsanother helper here in the lib folder in our server lib folder called credits.ts.
10:13:2710 hours, 13 minutes, 27 secondsTS let's go ahead and add the imports that we need. So from night code shared we need supported chat models find supported chat model and type model
10:13:3510 hours, 13 minutes, 35 secondspricing and we need to import type language model usage from the AI package. Then let's go ahead and import a type calculate credits for usage
10:13:4310 hours, 13 minutes, 43 secondsparams. Let's create billable usage type and let's create a type token counts.
10:13:5210 hours, 13 minutes, 52 secondsNext, let's go ahead and define the following tokens per million. So, this is the reasoning behind this night code
10:14:0210 hours, 14 minutes, 2 secondscharges in internal credits. Instead of exposing provider pricing, we currently peg one credit to 1 cent so credits stay
10:14:0910 hours, 14 minutes, 9 secondseasy to reason about like cents while still being granular enough. So, for small AI usage, change this constant if
10:14:1610 hours, 14 minutes, 16 secondsproduct if product wants a finer unit like 0.01 or a coarser one. So let's go ahead and define here US dollar per
10:14:2410 hours, 14 minutes, 24 secondscredit. So this is why I mentioned earlier that maybe we could change the unit here because at the time when I developed this, this actually wasn't an
10:14:3310 hours, 14 minutes, 33 secondsoption. But you can see that this controls how prices are formatted for display. For example, selecting token shows prices as $20 per 1 million tokens instead of a raw per token amount.
10:14:4410 hours, 14 minutes, 44 secondsSo, I'm not sure if this will change anything mathematically for us or if it's just for display
10:14:5310 hours, 14 minutes, 53 secondsbecause it technically could be useful for us to use it as a token. I mean, it's not that difficult to just create a new meter later and test it out. But for
10:15:0210 hours, 15 minutes, 2 secondsnow, I want to stay true to how I did it the first time. All right. So, once we have that, let's go ahead and develop a function called get token counts. So get
10:15:1110 hours, 15 minutes, 11 secondstoken counts will accept the usage and return token counts. From usage we can extract input tokens and output tokens throw an error if any of those is not
10:15:1910 hours, 15 minutes, 19 secondsdefined and then just return them. So more like a parser. Right now let's go ahead and develop a function called get
10:15:2610 hours, 15 minutes, 26 secondsmodel pricing. Get model pricing will accept the provider and the model and return model pricing. We're going to find the supported chat model. If there
10:15:3410 hours, 15 minutes, 34 secondsis no model or if there's no provider, we're going to throw that this is unsupported. And same thing if it can't find something else. And basically once
10:15:4210 hours, 15 minutes, 42 secondswe 100% ensure that we support this provider and if we support this model only then go ahead and return its pricing which we define for each model in here.
10:15:5510 hours, 15 minutes, 55 secondsNow let's go ahead and create a simple function estimate cost in US dollars which accepts input tokens and output tokens and returns this calculation.
10:16:0610 hours, 16 minutes, 6 secondsNow let's go ahead and create a convert US dollars to credits function which accepts estimated cost in US dollars and it returns back into credits.
10:16:1910 hours, 16 minutes, 19 secondsAnd finally let's go ahead and return calculate credits for usage function.
10:16:2610 hours, 16 minutes, 26 secondsThis function will accept provider model and usage. It will get token counts pricing for the model estimated cost in US dollars and credits and finally return the credits.
10:16:3610 hours, 16 minutes, 36 secondsAnd that is all we need for the credits.ts helper function. Now let's go ahead and create our middleware. So inside of server source, let's go inside
10:16:4510 hours, 16 minutes, 45 secondsof middleware and let's create a new file called require credits balance.dts.
10:16:5110 hours, 16 minutes, 51 secondsNow inside of here, I'm going to add create middleware the type authenticated environment from our nearby middleware and get available credits balance from
10:16:5910 hours, 16 minutes, 59 secondsour new lib polar. Now let's go ahead and prepare our new middleware here which is called require credits balance.
10:17:0810 hours, 17 minutes, 8 secondsLet's go ahead and make sure that we inject authenticated environment here.
10:17:1310 hours, 17 minutes, 13 secondsSo this context actually has an authenticated environment which holds the user ID because we are going to need it here. Let's go ahead and open a
10:17:2210 hours, 17 minutes, 22 secondssimple try and catch block here. And inside of try, first things first, we extract the user ID, which we can do in
10:17:3010 hours, 17 minutes, 30 secondsa type- safe manner. You can see when when I hover over user ID, it tells me it's a string. If I misspell it, it throws an error because of this. Now
10:17:3910 hours, 17 minutes, 39 secondsthat we have the user ID, we can use it to extract their credit balance. So, I'm going to go ahead and add a little comment here. So, this is a simple
10:17:4810 hours, 17 minutes, 48 secondslaunch time gate. Only start new work when the customer still has credits left. it does not reserve the full eventual cost of the request. So low
10:17:5610 hours, 17 minutes, 56 secondsvolume apps may tolerate small overspend on edge cases just for your information here. Let's go ahead and simply throw back an error if credits balance is less
10:18:0410 hours, 18 minutes, 4 secondsor equal than zero. Otherwise, let's simply go to the next middleware or in our case API route. And if anything else
10:18:1210 hours, 18 minutes, 12 secondsfails, if we are unable to establish how many credits the user has left, we have to throw again. We cannot let them spend
10:18:1810 hours, 18 minutes, 18 secondsour co and occur costs on our side just because we cannot verify how much they have left. Great. So now we have a middleware and we are ready to start
10:18:2610 hours, 18 minutes, 26 secondsmaking API modifications. Let's go ahead and create a new route inside of the server source routes. I'm going to go ahead and create billing.ts.
10:18:3710 hours, 18 minutes, 37 secondsInside of the new route billing, import hono. Import authenticated environment from require out. create checkout URL and create customer portal URL from lib
10:18:4610 hours, 18 minutes, 46 secondsportal. In here, let's define a new hono app, but make sure to inject authenticated environment inside of it.
10:18:5210 hours, 18 minutes, 52 secondsAnd in here, let's go ahead and chain a post request checkout, which is an asynchronous one, which is able to extract the user ID from the context and
10:19:0110 hours, 19 minutes, 1 secondsimply return a weight create checkout URL and scope it with via customer external ID to the user ID and request URL to simply be C request URL.
10:19:1310 hours, 19 minutes, 13 secondsThen let's go ahead and chain portal.
10:19:1610 hours, 19 minutes, 16 secondsOnce again, let me remove the semicolon here. So post portal will do a very similar thing but instead of checkout it will generate the customer portal URL.
10:19:2810 hours, 19 minutes, 28 secondsGreat. And finally let's create one hard-coded endpoint success to which all of these endpoints redirect back to. So
10:19:3710 hours, 19 minutes, 37 secondsthey simply show the user success. You can now close this tab and return to night code. And let's not forget to
10:19:4410 hours, 19 minutes, 44 secondsexport default of this app or should I say of this blink. Now let's go ahead and register our new billing route by
10:19:5110 hours, 19 minutes, 51 secondsgoing inside of server source and let's go inside of index.ts.
10:19:5610 hours, 19 minutes, 56 secondsI'm going to go ahead and import billing from routes billing and then I'm going to register these routes. So I'm going
10:20:0310 hours, 20 minutes, 3 secondsto go ahead let's see I'm going to first register the middleware here. So billing checkout will require AL and billing
10:20:1310 hours, 20 minutes, 13 secondsportal both of them are going to require AL. And then let's actually register the route here. So it doesn't matter where
10:20:1910 hours, 20 minutes, 19 secondsyou do it. Route billing. All right. So billing check out and technically. Okay.
10:20:2510 hours, 20 minutes, 25 secondsSo we are purposely not protecting the entire thing because there is one here which we want always to be uh available
10:20:3210 hours, 20 minutes, 32 secondswith AL added here. Okay. So that's why we are explicitly protecting these two.
10:20:3710 hours, 20 minutes, 37 secondsNow let's go ahead and let's adapt our existing route in the server called chat.ts DS and let's make it work with
10:20:4610 hours, 20 minutes, 46 secondsour new billing system. So for that I'm going to go ahead and add require credits balance calculate credits for
10:20:5310 hours, 20 minutes, 53 secondsusage and ingest AI usage. Also make sure you have the authenticated environment which we seem to have from the previous chapters. Besides this,
10:21:0210 hours, 21 minutes, 2 secondslet's also import type language model usage from AI. Now let's go ahead and
10:21:0910 hours, 21 minutes, 9 secondsfind the stream params down here. And besides session ID, let's extend it with user ID. Let's also go ahead and create
10:21:1810 hours, 21 minutes, 18 secondsa brand new type here before this function stream AI response called ingest usage for message params. Now that we have the user ID, we can
10:21:2710 hours, 21 minutes, 27 secondsactually extract it here in this function.
10:21:3010 hours, 21 minutes, 30 secondsAnd let's go ahead and create a new variable here right after the resolved model called completed usage and give it a type of language model usage or null.
10:21:4110 hours, 21 minutes, 41 secondsAnd by default, it's going to be null.
10:21:4410 hours, 21 minutes, 44 secondsThen go ahead and find this await database message create. And instead of await, let's do return. Scroll down to
10:21:5410 hours, 21 minutes, 54 secondswhere it's finished. And in between the try block and that function here, we're going to go ahead and develop a new
10:22:0110 hours, 22 minutes, 1 secondfunction called ingest usage for message.
10:22:0710 hours, 22 minutes, 7 secondsIt will accept message ID and status using our params from above. First things first, if there is no completed
10:22:1510 hours, 22 minutes, 15 secondsusage, let's do an early return. Now, let's go ahead and open another try and catch block here. Inside of try, we are
10:22:2410 hours, 22 minutes, 24 secondsgoing to generate billable usage using calculate credits for usage. Pass along the provider model and usage. Then let's go ahead and do await ingest AI usage.
10:22:3710 hours, 22 minutes, 37 secondsExternal customer ID is very important.
10:22:4010 hours, 22 minutes, 40 secondsEvent ID not so much but useful for logging and credits are extremely important inside of the catch which will receive an error here.
10:22:5010 hours, 22 minutes, 50 secondsLet's go ahead and simply do a console error. So it's useful for us to see if something goes wrong and why. Great. Now
10:22:5910 hours, 22 minutes, 59 secondslet's go ahead and add one more function after this one still before we enter the try block called persist interrupted
10:23:0810 hours, 23 minutes, 8 secondsmessage and usage. So if we get an interrupted message let's go ahead and await persist interrupted message and let's await inest usage for message with a status of interrupted.
10:23:2010 hours, 23 minutes, 20 secondsNow let's go inside of the try block here. Let's go ahead and find provider options. And in here we're going to
10:23:2710 hours, 23 minutes, 27 secondscapture the onfinish event. Once we get the onfinish event, assign the completed usage which we have defined above here.
10:23:3410 hours, 23 minutes, 34 secondsLet me go ahead and find it. Here it is.
10:23:3710 hours, 23 minutes, 37 secondsAnd set it to be let's see event total usage. Now let's scroll down until we
10:23:4510 hours, 23 minutes, 45 secondsfind stream dot aborted right here. Or if aborted controller signal aborted.
10:23:5310 hours, 23 minutes, 53 secondsAnd let's go ahead and call a different function instead of this one. Persist interrupted message and usage. Okay.
10:24:0210 hours, 24 minutes, 2 secondsNow let's go ahead and go to the end here right before the done event. And in
10:24:1010 hours, 24 minutes, 10 secondshere we're going to await inest usage for message with the message ID from the assistant and status complete.
10:24:1910 hours, 24 minutes, 19 secondsLet's go inside of the catch error here.
10:24:2110 hours, 24 minutes, 21 secondsHere we are. And let's find if abort controller signal aborted. Let's replace this function again with our new one.
10:24:2810 hours, 24 minutes, 28 secondsPersist interrupted message and usage like that. Now let's go ahead and scroll down for the resume method. We have
10:24:3710 hours, 24 minutes, 37 secondsauthenticated environment here. So that is great. Let's see what else do we have to do here. So we already have the user ID and we make sure that sessions are
10:24:4510 hours, 24 minutes, 45 secondsloaded by user ID. But let's see if everything is truly finished here. So, I'm going to scroll down until I find
10:24:5210 hours, 24 minutes, 52 secondsstream AI response. And we can see an error here. So, after session ID, make sure that you add user ID here. There we
10:24:5910 hours, 24 minutes, 59 secondsgo. We had that error. Now, let's scroll down until we find the post session ID here. And so, whenever we want to submit
10:25:0810 hours, 25 minutes, 8 secondssomething to a specific sess uh to a specific session ID, we're going to use our new require credits balance middleware. So, let's make sure we use
10:25:1710 hours, 25 minutes, 17 secondsthat. And in here we already do this but just double check that you are finding the session that belongs to this user.
10:25:2510 hours, 25 minutes, 25 secondsBrilliant. And down here we should have one more error. Again with stream AI response go ahead and simply add the
10:25:3210 hours, 25 minutes, 32 secondsuser ID. Brilliant. Uh so that is it for chat.ts route and we can now go ahead and
10:25:4010 hours, 25 minutes, 40 secondsimplement the link in other places. Now let's go ahead and quickly visit our sessions.ts DS route and let's go ahead
10:25:4710 hours, 25 minutes, 47 secondsand import a new package which we've just created require credits balance middleware and let's also get rid of
10:25:5610 hours, 25 minutes, 56 secondsthis night code shared find supported chat model and instead let's go ahead
10:26:0310 hours, 26 minutes, 3 secondsand use is supported chat model which we can extract from dot dolib models. So
10:26:1010 hours, 26 minutes, 10 secondsissup supported chat model a simpler function here. Okay, let's make sure we have these two. Now, let's go ahead and
10:26:1810 hours, 26 minutes, 18 secondsfind this and let's make it simpler by replacing this entire thing and just adding is supported chat model in the
10:26:2610 hours, 26 minutes, 26 secondsrefine. And then down here, not in the get but in the post method here to allow the user to create new sessions. They
10:26:3510 hours, 26 minutes, 35 secondsneed to have some balance. So, let's make sure we add this middleware here.
10:26:4010 hours, 26 minutes, 40 secondsBrilliant. Those are all the changes we need to do in the sessions. DS. Now, let's head to our CLI package. Inside of
10:26:4810 hours, 26 minutes, 48 secondshere, let's go inside of lib and let's create a new file upgrade.
10:26:5310 hours, 26 minutes, 53 secondsDS. In here, let's import open API client and get error message. Then, let's go ahead and create a new function
10:27:0010 hours, 27 minuteshere, open upgrade checkout. In here, we're going to communicate with our new billing endpoint using Hono RPC. So,
10:27:0810 hours, 27 minutes, 8 secondsbilling checkout post endpoint. We're going to check if the response is okay.
10:27:1210 hours, 27 minutes, 12 secondsAnd if it is, we're going to use our crossplatform open package to open the user's browser with the return URL,
10:27:2010 hours, 27 minutes, 20 secondswhich will be the checkout screen, and throw a new error if anything else happens. And then we're going to create a pretty much identical function, but
10:27:2810 hours, 27 minutes, 28 secondsfor the billing portal, which targets API client billing portal post request.
10:27:3510 hours, 27 minutes, 35 secondsGreat. So this is the only lib which we're going to have at the client. Now let's go ahead and actually wire this
10:27:4210 hours, 27 minutes, 42 secondsinto our command prompt. I mean our command popover. So for this we are going to go inside of CLI inside of
10:27:5010 hours, 27 minutes, 50 secondssource. Let's go inside of components command menu and let's find commands.tsx.
10:27:5610 hours, 27 minutes, 56 secondsIn here let's import open billing portal and open upgrade checkout. Let's first find the upgrade command which we should
10:28:0410 hours, 28 minutes, 4 secondsalready have here. So, upgrade buy more credits, which right now doesn't really do much. Let's make sure the function is
10:28:1110 hours, 28 minutes, 11 secondsasynchronous. And let's leave this toast message as is. And let's go ahead and open a try and catch function here. So,
10:28:1810 hours, 28 minutes, 18 secondsinside of the try function, we're going to await open upgrade checkout. And after we successfully await it, we're going to trigger toast show success
10:28:2710 hours, 28 minutes, 27 secondscheckout open in browser. Otherwise, if we catch an error, we're going to obtain to parse the error message, and we're going to show an error toast with the
10:28:3610 hours, 28 minutes, 36 secondserror message. So, that is for the upgrade one. Now, let's go ahead and find the usage one, which we should also
10:28:4310 hours, 28 minutes, 43 secondshave. And this one will be pretty much identical. So, make sure it's an asynchronous function. You can leave the existing toast message as is. And then
10:28:5110 hours, 28 minutes, 51 secondsin here, we're going to add another try and catch method. We're going to attempt to open the billing portal this time with a toast of success. If it
10:29:0010 hours, 29 minutessuccessfully awaits and if we catch any error, it will simply toast with an error. Great. Now, I'm pretty confident
10:29:0810 hours, 29 minutes, 8 secondsthat we have everything we need to test this out. So, make sure that you are in your root repository. So, change
10:29:1510 hours, 29 minutes, 15 secondsdirectory. If you are inside of server, make sure you are at the root. And in here, let's go ahead and start our server. And then in the other one, let's
10:29:2410 hours, 29 minutes, 24 secondsgo ahead and let's start our CLI. So, first things first, I'm going to make sure that I am logged in because if I
10:29:3110 hours, 29 minutes, 31 secondstry with hello world now, you can see I'm getting an error because I am unauthorized. So, I have to log in
10:29:3810 hours, 29 minutes, 38 secondsfirst. Once I successfully log in and allow all the permissions, I should be able to send a message. So, I just want
10:29:4610 hours, 29 minutes, 46 secondsto confirm that. But you can see that now I have a different error. So, try sending a message. Even if you're logged in, you should get no credits remaining.
10:29:5410 hours, 29 minutes, 54 secondsSo that is exactly what our middleware is protecting us from. So let's hit upgrade, which should redirect us to
10:30:0110 hours, 30 minutes, 1 secondthis, a checkout screen. In here, I'm going to enter a dummy test card, an expiration that's in the future, any
10:30:0910 hours, 30 minutes, 9 secondscard holder name, any country at all. So I'm going to choose Croatia here. And you can see that for $20, I'm going to
10:30:1710 hours, 30 minutes, 17 secondsget a,000 credits. I don't think email matters. Let's go ahead and hit pay now. Okay, so it does matter.
10:30:2610 hours, 30 minutes, 26 secondsSo, type in whichever email you want here.
10:30:3010 hours, 30 minutes, 30 secondsLet's go ahead and pay. And this should then redirect us to a success screen.
10:30:3810 hours, 30 minutes, 38 secondsLet's give it a moment to finish. And yeah, make sure that you are in the sandbox mode, of course. All right, I'm going to pause and Okay, here we are.
10:30:4710 hours, 30 minutes, 47 secondsDone. You can close this tab and return to night code. Brilliant. So, at this point, I should also be able to open
10:30:5410 hours, 30 minutes, 54 secondsusage. And in this usage here, I can see my benefits. So, I can see that I have a,000 credits here. And what's more
10:31:0110 hours, 31 minutes, 1 seconduseful is the actual usage tab, which tells me how much I have left. But more importantly, does this work? So, let's
10:31:0810 hours, 31 minutes, 8 secondsgo ahead and try hello world. And I can see that I no longer have any errors, which means that this is successfully
10:31:1710 hours, 31 minutes, 17 secondsworking. Now, keep in mind that these credits aren't going to be immediately updated. So, give it a minute. This is
10:31:2410 hours, 31 minutes, 24 secondsasynchronous, right? Because we're not exactly querying this ourselves. This is their page, so it depends on how often they refresh this. But you can see after
10:31:3310 hours, 31 minutes, 33 secondsa few refreshes, I now have uh 998 instead of a,000. So two credits were spent using our ingestion calculation
10:31:4210 hours, 31 minutes, 42 secondshere. Amazing. So we have successfully implemented billing in our project.
10:31:4810 hours, 31 minutes, 48 secondsAmazing. Amazing job. So let's go ahead and create a new branch and commit these changes. So I'm going to do get checkout-b09
10:31:5810 hours, 31 minutes, 58 secondsbilling. I'm going to do git add git commit- m09 billing and git push- origin 09 billing.
10:32:0910 hours, 32 minutes, 9 secondsThat should push the branch in here. I should be able to open a new pull request at this point, base it to main,
10:32:1610 hours, 32 minutes, 16 secondsand create a new pull request. And let's go ahead and review our changes. Now, let's go ahead and review our pull request. So, here's the summary. We
10:32:2410 hours, 32 minutes, 24 secondsadded new upgrade and usage commands in the CLI to access the billing portal and checkout flows. We implemented credit based billing system that tracks AI
10:32:3210 hours, 32 minutes, 32 secondstoken usage and converts to credits. We added credit balance requirement for chat sessions to prevent overuse.
10:32:3910 hours, 32 minutes, 39 secondsGreat. In here we have our railway deployment and something I remembered is that we probably have to upgrade the
10:32:4710 hours, 32 minutes, 47 secondsenvironment variables. So we can do this in two ways. inside of environment here, we can simply copy these ones that we
10:32:5510 hours, 32 minutes, 55 secondsneed here. So, let's go ahead and take a look at our current environment variables. But keep in mind that you're right now in the preview environment.
10:33:0310 hours, 33 minutes, 3 secondsSo, I actually wouldn't recommend doing it here unless you really want this preview to work as expected. I would
10:33:1110 hours, 33 minutes, 11 secondsrecommend just doing it in production instead. So, switch to production mode here. Open this, open variables, and
10:33:1810 hours, 33 minutes, 18 secondsopen the raw editor here. So let's take a look a little bit. We have API URL, we have database URL, and we have enthropic
10:33:2610 hours, 33 minutes, 26 secondsAPI key. So immediately here I can see that we are missing the open API key. So I'm going to add that. So you don't have
10:33:3410 hours, 33 minutes, 34 secondsto do this, right? But I'm making sure that we have all the environment variables that we need. Polar is entirely developed on the server. So I
10:33:4210 hours, 33 minutes, 42 secondsknow that it needs to have all of the polar ones.
10:33:4610 hours, 33 minutes, 46 secondsNow, from my clerk ones, I'm actually not entirely sure. But here's the thing.
10:33:5310 hours, 33 minutes, 53 secondsUh, we don't really lose anything by adding them. So, I'm going to add all of them as well, including the JVT secret.
10:33:5910 hours, 33 minutes, 59 secondsAnd then I'm just going to hit upgrade variables. And then I'm going to redeploy. Great. Now, let's go back to
10:34:0610 hours, 34 minutes, 6 secondsuh our all request here. And let's see a comment that we have. validate token counts as finite non- negative integers.
10:34:1710 hours, 34 minutes, 17 secondsLine 34 currently only checks for missing values. If token values are not a number infinity or negative, credit
10:34:2610 hours, 34 minutes, 26 secondscalculation can become invalid and produce bad billing output. So instead of our credits.ts,
10:34:3410 hours, 34 minutes, 34 secondslet's quickly review that. So it's so instead of if input tokens here, let's quickly check where is that function
10:34:4210 hours, 34 minutes, 42 secondsexactly in here. So get token counts. Okay. And how does it suggest we do that?
10:34:5110 hours, 34 minutes, 51 secondsOkay, I'm guessing that yeah, that could be an improvement. So if you want to, you don't have to, but if you want to, you
10:34:5910 hours, 34 minutes, 59 secondscan add uh this changes or maybe even simpler if you have code rabbit, you can probably just tell it to do that
10:35:0610 hours, 35 minutes, 6 secondscommitable suggestion. You can see for you it's going to do it. It's going to add an if here and throw an error. So we
10:35:1410 hours, 35 minutes, 14 secondscould just update this like this. Commit changes. Suggestion applied. And then it
10:35:2110 hours, 35 minutes, 21 secondsshould re-review the code. You can see that this is now resolved. Uh, great.
10:35:2610 hours, 35 minutes, 26 secondsSo, I'm just going to pause the video and wait for my deployment and everything to finish just to confirm that nothing else was broken with this
10:35:3310 hours, 35 minutes, 33 secondsmerge. All right, I can see everything is successful. So, I'm going to go ahead and merge my pull request here. There we go. I'm not going to delete the branch
10:35:4110 hours, 35 minutes, 41 secondsso I have a clean history here. And just like that, we are now up to date. So, let's go ahead and go back to our main
10:35:4810 hours, 35 minutes, 48 secondsGR branch and get origin main. So we pull that new merge back here just like that. What I always like to check, you
10:35:5710 hours, 35 minutes, 57 secondscan see how now I have that change applied from code rabbit here. So I can see that this all uh works well still. I like to go inside of here, open the
10:36:0610 hours, 36 minutes, 6 secondsgraph, and I just like to confirm that everything's okay. So you can see that in here I have 09 billing. In here I have that commit from code rabbit. You
10:36:1410 hours, 36 minutes, 14 secondscan see it he was the author. And in here I have merge pull request number nine. Brilliant. So, I believe that
10:36:2310 hours, 36 minutes, 23 secondsmarks the end of this chapter. Amazing, amazing job and see you in the next one.
Chapter 13: Client-Side Tool Execution
10:36:2710 hours, 36 minutes, 27 secondsThis lesson is going to be very different in comparison to all other lessons we've had. Primarily because we are not going to be implementing any new
10:36:3510 hours, 36 minutes, 35 secondsfeature, but instead we're going to rewrite our chat logic. You're probably asking why are we doing this now at the
10:36:4210 hours, 36 minutes, 42 secondsend of this project? Well, that is because I realized by reviewing the code that we have a critical mistake that
10:36:5010 hours, 36 minutes, 50 secondsmakes this entire project useless. And I'm not kidding when I say that. Let me go ahead and explain what I mean. The
10:37:0010 hours, 37 minutesbiggest problem is that right now our tool execution is entirely run on the server. And you might be thinking, why
10:37:0810 hours, 37 minutes, 8 secondsis that a problem? Well, let's go ahead and demonstrate the current state of our app and then let's change our API URL to
10:37:1810 hours, 37 minutes, 18 secondstarget our deployed server instead of our local server. So what happens right
10:37:2410 hours, 37 minutes, 24 secondsnow in one terminal we do bondev server which is running on localhost 3000.
10:37:3210 hours, 37 minutes, 32 secondsThen in another terminal we do bunr rundev cli.
10:37:3610 hours, 37 minutes, 36 secondsNotice how both of these commands are being run from the same repository, night code. Now I'm going to go ahead
10:37:4310 hours, 37 minutes, 43 secondsand just do the usual login here. I'm going to continue. I'm going to select my account
10:37:5210 hours, 37 minutes, 52 secondsand after I allow I'm going to get redirected back here and I am authenticated. So if I switch to plan mode and if I do something like what is this project about?
10:38:0210 hours, 38 minutes, 2 secondseverything will work as expected and that is why I didn't notice until now that we have a huge huge problem in this
10:38:1210 hours, 38 minutes, 12 secondsproject. The reason this is able to read all of these files and perform all of
10:38:1810 hours, 38 minutes, 18 secondsthese tools is purely accidental because bunr rundev server is also run from the
10:38:2610 hours, 38 minutes, 26 secondssame repository as bunr rundev cli making it seem like our CLI is executing
10:38:3310 hours, 38 minutes, 33 secondsthese tools but it isn't in fact we can ask our AI exactly that where is tool
10:38:4110 hours, 38 minutes, 41 secondsexecution happening happening in this project and you will see that it's going to do whatever it needs to do but
10:38:4910 hours, 38 minutes, 49 secondseventually it's going to conclude that all tool execution is happening on the server. This is a huge problem for us
10:38:5910 hours, 38 minutes, 59 secondsbecause the goal of this project is for the server to be entirely separated. The server needs to be hosted somewhere else
10:39:0810 hours, 39 minutes, 8 secondsand the CLI should be invoked inside of the user's machine, right? That is the whole idea of this app. Let's take a look at the output here.
10:39:1810 hours, 39 minutes, 18 secondsSo, I'm going to scroll up a bit to see if there's anything useful. Here is the analysis. All tool execution happens on
10:39:2610 hours, 39 minutes, 26 secondsthe server. The CLI is purely a display layer for tool activity. So the tool definitions are actually made on the
10:39:3510 hours, 39 minutes, 35 secondsserver. Each tool is made using Verscell's AI SDK. Cool. Tool assembly is made on the server. Create tool
10:39:4410 hours, 39 minutes, 44 secondsfunction is on the server. Tool invocation is where inside of chat.ts again on the server. And I completely
10:39:5210 hours, 39 minutes, 52 secondsmissed this. I I'm not sure how I even did this. uh when I attempt to build the system prompt, I actually send the
10:40:0010 hours, 40 minutesdirectory on the server and this whole time I was convinced that all this is normal because it worked right but it
10:40:0710 hours, 40 minutes, 7 secondsworked on accident. I'm going to demonstrate now by asking something else here. What happens if we decide to host
10:40:1610 hours, 40 minutes, 16 secondsthe server on something like railway or versel and then attempt to run the
10:40:2510 hours, 40 minutes, 25 secondsCLI in a specific directory on my machine. So just to conclude this critical issue that we
10:40:3410 hours, 40 minutes, 34 secondshave, let's see what it's going to answer. This is a critical architectural issue. So this is definitely broken. Let
10:40:4410 hours, 40 minutes, 44 secondsme prove that to you. Here it is. It would be completely broken. If we host this server and run the CLI locally,
10:40:5110 hours, 40 minutes, 51 secondstool execution would operate on the remote servers file system, not our local machine.
10:40:5810 hours, 40 minutes, 58 secondsSo the only reason this works right now is because bond rundev server is tested locally from the directory where we are
10:41:0610 hours, 41 minutes, 6 secondsdeveloping this tool here. That is why I am dedicating this chapter to refactoring to further demonstrate this problem. This is what I'm going to do.
10:41:1710 hours, 41 minutes, 17 secondsI'm going to find my night code server deployment. I'm going to go ahead and copy the URL here and I'm going to go
10:41:2410 hours, 41 minutes, 24 secondsahead and find what environment variable is responsible for communicating with the server. So I'm going to go inside of my CLI package lib API client. In here I
10:41:3410 hours, 41 minutes, 34 secondscan see its API URL. So let's go inside of environment and let's change the API URL to be this. And let's remove the trailing slash. So exactly like this.
10:41:4610 hours, 41 minutes, 46 secondsNow I'm going to go ahead and go inside of my clerk. Find your O application and
10:41:5410 hours, 41 minutes, 54 secondsgo inside of redirect URLs. Then once again copy this and append out call back
10:42:0210 hours, 42 minutes, 2 secondshere. and let's hit add URL and hit save. Okay, now that that's been saved,
10:42:1010 hours, 42 minutes, 10 secondslet's go ahead and close this. And I'm going to shut down my server because in production, we wouldn't need to have the server running, right? This is supposed
10:42:1810 hours, 42 minutes, 18 secondsto be a production app. So, let's go ahead and do bunr rundev CLI. We would have to perform login again because we
10:42:2510 hours, 42 minutes, 25 secondsnow have an entirely different uh API URL. So if you've configured this correctly, you should see successful clerk here. If it doesn't work, if you
10:42:3410 hours, 42 minutes, 34 secondsget some kind of redirect URI is missing, it means that this wasn't properly saved or maybe you have a typo in out call back. So just make sure it's
10:42:4210 hours, 42 minutes, 42 secondsthis. Okay. And click allow here. So I'm successfully authenticated. Great. So that works. But what if I try to do what
10:42:5010 hours, 42 minutes, 50 secondsis this project about? Let's see what happens now. My server is not running locally anymore. So apparently it's
10:42:5710 hours, 42 minutes, 57 secondsreading something. Oh, but what happens now? It appears the directory and then the full path to my directory doesn't
10:43:0410 hours, 43 minutes, 4 secondsexist or it's empty. This could mean that the project hasn't been initialized, the path is incorrect, or the project was recently deleted or
10:43:1210 hours, 43 minutes, 12 secondsmoved. It has completely no idea what project am I talking about. So if we were to actually deploy this server,
10:43:2110 hours, 43 minutes, 21 secondswhich we are, and then build this CLI as a distributable app and let people download it, whoever tries to run the
10:43:2810 hours, 43 minutes, 28 secondsapp would get the same response but with their path here because we just send the path to the server. So I completely
10:43:3710 hours, 43 minutes, 37 secondsmessed up this logic because it worked because both server and the CLI were being initialized and run locally in the
10:43:4610 hours, 43 minutes, 46 secondssame directory. So by testing that I did everything worked fine but I made a critical critical mistake. So just to
10:43:5410 hours, 43 minutes, 54 secondsshow you how you can revert this go ahead and change this back to localhost 3000.
10:44:0010 hours, 44 minutesShut down bundev cli. Go ahead and now run the server again.
10:44:0810 hours, 44 minutes, 8 secondsGo ahead and run CLI again. And once again you will have to login now because you have a whole new server now. So you
10:44:1610 hours, 44 minutes, 16 secondscan leave inside of clerk here both your local host and the uh actual deployment
10:44:2310 hours, 44 minutes, 23 secondsURL and once you log in here and you allow the permissions and try again what
10:44:3010 hours, 44 minutes, 30 secondsis this project about it will all work so I guess this is fine if this is local
10:44:3710 hours, 44 minutes, 37 secondsonly project but that isn't fun right that isn't what we intended to build that is why I'm making this chapter by
10:44:4610 hours, 44 minutes, 46 secondsrewriting the entire chat. But I don't want to scare you too much. The end result is mostly going to be net negative when it comes to writing code.
10:44:5610 hours, 44 minutes, 56 secondsMeaning that we're going to remove more code in this lesson that we are going to add because along this mistake that I've
10:45:0310 hours, 45 minutes, 3 secondsmade, I also made sure to research the entire project and find all other mistakes or complications that I've
10:45:1110 hours, 45 minutes, 11 secondsimplemented which I can simplify. So remember how we implemented our own use
10:45:1910 hours, 45 minutes, 19 secondschat and in here we do tool calling tool result text delta all of that same thing
10:45:2710 hours, 45 minutes, 27 secondsin chat.ts TS route we stream the response and we carefully um stream every single reasoning delta and all of
10:45:3510 hours, 45 minutes, 35 secondsthese things that is because I thought that it wasn't safe to use use chat instead of open tui but turns out we can
10:45:4310 hours, 45 minutes, 43 secondsactually use this which means we can simplify the entire codebase that much you you will not believe how much
10:45:5010 hours, 45 minutes, 50 secondssimpler all of this is going to be and by doing that we can officially call this project finished. I simply couldn't
10:45:5810 hours, 45 minutes, 58 secondsleave you with a broken project. So that is why I researched all of the things we can simplify and make better so that you can proudly show this project and share it with other people. Let's get started.
10:46:0910 hours, 46 minutes, 9 secondsLet's go ahead and first add some new packages and remove some packages we are no longer going to use. So I'm going to
10:46:1610 hours, 46 minutes, 16 secondsgo ahead inside of my packages inside of CLI. And in here I'm going to add AI SDK
10:46:2410 hours, 46 minutes, 24 secondsReact and I'm going to add AI. So these two packages right here. Then I'm going
10:46:3110 hours, 46 minutes, 31 secondsto go ahead and remove event source parser and night code
10:46:3910 hours, 46 minutes, 39 secondsdatabase. So I'm no longer going to need these two. And then let's go inside of our shared package. So inside of shared
10:46:4810 hours, 46 minutes, 48 secondsand inside of here, let's do bun add AI once more. So let's take a look at the
10:46:5510 hours, 46 minutes, 55 secondsstate of our changes now. So inside of here, you should have changes to your CLI in form of addition for AI SDK,
10:47:0410 hours, 47 minutes, 4 secondsReact and AI and removal of event source parser and night code database. And in your shared you should just have AI like
10:47:1310 hours, 47 minutes, 13 secondsthis. And once you've done that, go ahead back to your root project and just run bun install so it all synchronizes.
10:47:2210 hours, 47 minutes, 22 secondsNext, let's go ahead and modify our schema because that's also going to be one simplification which we're going to be doing instead of maintaining the
10:47:3010 hours, 47 minutes, 30 secondsentire message model. Here's what we can do instead. We can get rid of it entirely. And then inside of session
10:47:3810 hours, 47 minutes, 38 secondshere, we can simply think of messages as a JSON field. This way, they're going to be elastic and they can adapt to whatever result we return from AI SDK.
10:47:5110 hours, 47 minutes, 51 secondsAll right, so let's go over all of the fields here. ID, user ID, title, and we can get rid of the uh path here.
10:47:5910 hours, 47 minutes, 59 secondsActually, there is absolutely no reason sessions should know what path it is. So we just have ID, user ID, title, created
10:48:0610 hours, 48 minutes, 6 secondsat, updated at, and we have the messages, which is a JSON with the default of an empty array in quotes, and
10:48:1310 hours, 48 minutes, 13 secondsan index for the user ID. Once we have that, let's go ahead inside of packages and inside of database here, and let's
10:48:2310 hours, 48 minutes, 23 secondsrun bunx Prisma uh migrate reset. Uh my apologies, that's not the syntax.
10:48:3010 hours, 48 minutes, 30 secondsBanex Prisma migrate reset like this. So we want to remove all data because we just made a breaking change here. So
10:48:3810 hours, 48 minutes, 38 secondslet's get rid of all of our data. This is of course development only. You should never do this in production. In production you should do proper migration. Once you deleted all your
10:48:4710 hours, 48 minutes, 47 secondsdata, you can run bonex prisma generate and then banexprisma database push.
10:48:5610 hours, 48 minutes, 56 secondsSo let's wait a second for all of this to synchronize with our remote database. And once it is, let's do bonex Prisma.
10:49:0610 hours, 49 minutes, 6 secondsLet me see is it studio? It is. So after you have studio here, you should see only the session table here with ID
10:49:1410 hours, 49 minutes, 14 secondscreated at messages, title, updated, and user ID. Those are the only things you should be seeing. Besides the messages
10:49:2210 hours, 49 minutes, 22 secondstable, we can now also get rid of all of the unused enmsiums here. So you should
10:49:2910 hours, 49 minutes, 29 secondsjust have model session like this. Let's go ahead and run the commands one more
10:49:3610 hours, 49 minutes, 36 secondstime just in case even though most likely the generate is the only one that matters here. But let's go ahead and
10:49:4410 hours, 49 minutes, 44 secondsjust in case do a database push just to confirm that we can successfully synchronize our Prisma schema with the remote database even after we removed
10:49:5210 hours, 49 minutes, 52 secondsthe eniums and Prisma database studio just to confirm. My apologies it is just studio just to confirm this command
10:50:0110 hours, 50 minutes, 1 secondstill works. Perfect. So nothing is broken. Now let's go ahead and go inside of packages inside of database source
10:50:0910 hours, 50 minutes, 9 secondsand in here finds. You can see that the entire file has errors. So you can just go ahead and move that to trash. Let's
10:50:1710 hours, 50 minutes, 17 secondsgo ahead inside of the index here to make sure there's no errors, no errors in the client. And we can just go inside of the package JSON here and we can find
10:50:2510 hours, 50 minutes, 25 secondsthe eniums and we can get rid of this like this. Now we need to develop the
10:50:3310 hours, 50 minutes, 33 secondsreplacement for the enions. So let's go ahead inside of shared inside of source and inside of here find schemas.ts.
10:50:4310 hours, 50 minutes, 43 secondsNow schemas already has some content but we are going to have to modify some of it. So let's see what it currently has.
10:50:5110 hours, 50 minutes, 51 secondsAll of this message part schemas honestly tool call schemas all of this will go away. None of this is really needed. The schemas will become an
10:50:5910 hours, 50 minutes, 59 secondsentirely new thing. So go ahead and add zod and tool from AI. Define the mode
10:51:0610 hours, 51 minutes, 6 secondshere. Let's go ahead and define mode schema. Let's derive the mode type from that.
10:51:1310 hours, 51 minutes, 13 secondsAnd now in here we're going to maintain tool input schemas. So we are going to do this in a shared package rather than
10:51:2110 hours, 51 minutes, 21 secondson the server so that we can both have the schema for the server but do the actual execution on the CLI. So it needs
10:51:2910 hours, 51 minutes, 29 secondsto be used by both. That's why shared is the perfect uh place for it. So for each tool, we're going to go ahead and just
10:51:3610 hours, 51 minutes, 36 secondsadd a quick pattern. Sorry, a quick path like this. And description.
10:51:4310 hours, 51 minutes, 43 secondsSome are going to have a pattern like this. So be mindful of that. So I'm just going to paste each. You can pause the screen and then see what's written
10:51:5210 hours, 51 minutes, 52 secondsinside. Now let's do write file. Now, let's go ahead and do edit file. And
10:52:0010 hours, 52 minuteslet's go ahead and do bash. I'm going to go ahead and zoom out just a bit in case it's easier for you to see this way. And
10:52:0710 hours, 52 minutes, 7 secondsI'm going to scroll so you can double check that you've added all of them.
10:52:1210 hours, 52 minutes, 12 secondsMake sure you have read file, list, directory, glob, grap, write file, edit file, and bash. Those are all the tool
10:52:2010 hours, 52 minutes, 20 secondsschemas that we need. Great. Let's go ahead and add as const to the end of this object. Then let's go ahead and
10:52:2910 hours, 52 minutes, 29 secondsdefine a new object read only tool contracts. Inside of here I'm going to define a read file.
10:52:4010 hours, 52 minutes, 40 secondsThen after read file I'm going to add list directory.
10:52:4610 hours, 52 minutes, 46 secondsThen I'm going to add glob. And then I'm going to add GP.
10:52:5310 hours, 52 minutes, 53 secondsSo let's go ahead and add as const to this as well. Make sure that you have GP
10:53:0010 hours, 53 minutesglobe list directory and read file instead of a read only tool contracts.
10:53:0610 hours, 53 minutes, 6 secondsSo we're simply keeping uh an object here which we in which we are going to keep a list of read only tools. So these are basically non-destructive tools.
10:53:1710 hours, 53 minutes, 17 secondsOkay. So inside of here we have various kinds. We have read file, list directory, but we also have write file,
10:53:2510 hours, 53 minutes, 25 secondsedit file. Right? But in here we kind of duplicate that. But it's also useful to explicitly maintain them like this.
10:53:3410 hours, 53 minutes, 34 secondsSo now let's go ahead and export the following build tool contracts. Inside of here I'm
10:53:4210 hours, 53 minutes, 42 secondsgoing to spread read only contracts. And then I'm going to add a write file. I'm
10:53:4910 hours, 53 minutes, 49 secondsgoing to add an edit file. And finally, I'm going to add bash. And let's add as
10:53:5810 hours, 53 minutes, 58 secondsa const here as well. Then let's go ahead and export type tool contracts.
10:54:0510 hours, 54 minutes, 5 secondsAnd finally, let's export a function get tool contracts scoped to the mode. So if
10:54:1310 hours, 54 minutes, 13 secondsmode is plan we can simply return read only contracts. Otherwise let's return
10:54:1910 hours, 54 minutes, 19 secondsbuild tool contracts. So this is a very handy schema file which has read only
10:54:2610 hours, 54 minutes, 26 secondsbuild and all other tools schemas we might need. So make sure you have all of them here. Notice how none of these are
10:54:3510 hours, 54 minutes, 35 secondsdescribing or doing the actual execution here. So we are just describing the schemas right now. Now let's modify the
10:54:4210 hours, 54 minutes, 42 secondssystem prompt. For that we're going to go inside of packages server source. Let's go ahead and choose system prompt.
10:54:5110 hours, 54 minutes, 51 secondsDS and let's go ahead and replace this with mode type import from night code shared.
10:55:0010 hours, 55 minutesAnd let's go ahead and replace the mode with mode type. And let's remove the path here entirely. Let's quickly fix
10:55:0810 hours, 55 minutes, 8 secondswhat this problem is here. Night code shared. Ah, yes. So, what happened here?
10:55:1410 hours, 55 minutes, 14 secondsLet's for a second go back inside of here. Let me show you where I am. So, inside of my shared, we just developed the schemas file, but I completely
10:55:2210 hours, 55 minutes, 22 secondsforgot to modify my index, my export of the shared package. So, this is where we just wrote all of those tool contracts
10:55:3110 hours, 55 minutes, 31 secondsand schemas. Now, let's go inside of index.ts, DS which is just next to it here. And in here we're going to have to modify our U export or return structure.
10:55:4410 hours, 55 minutes, 44 secondsSo what has to be modified? Well, pretty much everything from the schemas file because everything was modified. So we
10:55:5110 hours, 55 minutes, 51 secondsnow have mode, we have mode schema, tool input schemas, get tool contracts, type
10:56:0010 hours, 56 minutestool contracts, and we have type mode type. So all of
10:56:0710 hours, 56 minutes, 7 secondsthis should be exported from shared index.ts.
10:56:1410 hours, 56 minutes, 14 secondsWhile we are here, we can also take a peek at package JSON and just confirm we have the AI package here. though I believe we added this at the beginning.
10:56:2210 hours, 56 minutes, 22 secondsSo what we can do now once we have the proper export here in the index in the shared we can go back inside of system prompt which we started fixing. So
10:56:3110 hours, 56 minutes, 31 secondsinside of server source system prompt you can see how we no longer have the error for importing this. So we can assign that to be the type of mode and
10:56:3810 hours, 56 minutes, 38 secondsinside of build system prompt what I want to do is I want to get rid of the path entirely. So I only have a singular
10:56:4710 hours, 56 minutes, 47 secondsmode here. Okay. So, how are we going to modify uh what we have here? Well, very simply, we're just going to remove it.
10:56:5510 hours, 56 minutes, 55 secondsWe are not going to let the system prompt be aware of anything regarding the path, right? So, let's get rid of
10:57:0310 hours, 57 minutes, 3 secondsthat. Let's scroll down here. And we can again just leave if mode plan. As simple as that. And down here, if mode build,
10:57:1210 hours, 57 minutes, 12 secondsthat's it. Nothing else here needs changing. So now our system prompt has a very very clean build. Now let's go
10:57:2010 hours, 57 minutes, 20 secondsahead and delete all of the tools on the server. So if you go inside of your packages server source, all these tools
10:57:2810 hours, 57 minutes, 28 secondshere handle execution logic. You can see how they're actually looking through the file system. But as we deducted, all of
10:57:3810 hours, 57 minutes, 38 secondsthis is unfortunately problematic and completely wrong because it's reading the file system on the server where it
10:57:4510 hours, 57 minutes, 45 secondsshould be reading the file system wherever the CLI package is running. So we can just highlight the tools folder
10:57:5310 hours, 57 minutes, 53 secondsand we can delete it entirely. So you can see that you should have all of these files deleted. All right, now that
10:58:0010 hours, 58 minuteswe have that, let's add some code for a change. Now that we deleted all of the tools from the server, let's go ahead and build the actual execution logic
10:58:0910 hours, 58 minutes, 9 secondsinside of the CLI. So inside of CLI source, inside of lib here, I'm going to go ahead and create local tools.ts.
10:58:2010 hours, 58 minutes, 20 secondsSo we explicitly know what this is.
10:58:2210 hours, 58 minutes, 22 secondsLet's go ahead and add some imports. So all of this from fs promises, all of these from path and all of these from
10:58:2910 hours, 58 minutes, 29 secondsour night code shared which has now been modified and it's ready to go. Let's add all of these constants here. And let's
10:58:3710 hours, 58 minutes, 37 secondsfirst create a simple function called resolve inside path. So this is
10:58:4510 hours, 58 minutes, 45 secondskind of a guardrail to ensure that whatever the user is trying to search for by using agent tools is inside of the path that we want it to be.
10:58:5510 hours, 58 minutes, 55 secondsNow let's go ahead and add a simple truncate helper function here. And then let's go ahead and create a factory of
10:59:0410 hours, 59 minutes, 4 secondstool execution. So a function called execute local tool which accepts a tool name, input and mode. First things
10:59:1310 hours, 59 minutes, 13 secondsfirst, we're going to go ahead and check whether we are in plan mode. So we know we have to forbid certain tools. So if
10:59:2210 hours, 59 minutes, 22 secondsmode is equal to plan mode and if not read file list directory globe or grap.
10:59:3010 hours, 59 minutes, 30 secondsSo if it is not any of these we have to throw an error. Whatever tool you are requesting is not available in plan
10:59:3710 hours, 59 minutes, 37 secondsmode. So this is the guardrail. So that in plan mode only read file list directory globe and grap can be used.
10:59:4610 hours, 59 minutes, 46 secondsNow let's go ahead and open a switch case based on the tool name and let's start with a case of read file. So if
10:59:5610 hours, 59 minutes, 56 secondsit's read file make sure to read the actual file call our resolve inside path
11:00:0311 hours, 3 secondshere and then simply use the API to read file and return back the content. Now
11:00:1011 hours, 10 secondslet's go ahead and develop a more complex one which is list directory. So another case here I'm going to show you
11:00:2011 hours, 20 secondsthe entire thing. Here it is list directory. Once again we get the path we resolve the path inside of our guardrails and then in here you can see
11:00:2911 hours, 29 secondsthat we are reading inside of directory but we skip node modules explicitly here and we return back the results. That's the case for list directory.
11:00:4011 hours, 40 secondsNow let's go ahead and develop our globe tool. So once again I'm going to show
11:00:4611 hours, 46 secondsyou the entire thing. Here it is our globe tool.
11:00:5211 hours, 52 secondsAfter the globe tool, let's go ahead and return our grap tool. So I'm going to develop the grap tool in phases because
11:01:0011 hours, 1 minuteit's a bit longer and I want you to see the entire code. Feel free to use AI assistance for this. It is surprisingly good at this type of things. So let's go
11:01:0911 hours, 1 minute, 9 secondsahead and add this. Let's go ahead and establish some arguments here. Then let's go ahead and
11:01:1711 hours, 1 minute, 17 secondspush those arguments. Let's go ahead and spawn the actual process here.
11:01:2311 hours, 1 minute, 23 secondsSo this part then let's go ahead and handle return messages or errors.
11:01:3311 hours, 1 minute, 33 secondsLet's go ahead and define constants for lines, matches, and a truncated let here.
11:01:4111 hours, 1 minute, 41 secondsLet's go ahead and parse over all the lines using a for loop. So after truncated false, go ahead and add this for loop right here.
11:01:5311 hours, 1 minute, 53 secondsAnd then let's go ahead and return all of the matches.
11:01:5911 hours, 1 minute, 59 secondsAnd if truncated, let's go ahead and include that in the metadata here along with the length of the total matches.
11:02:0711 hours, 2 minutes, 7 secondsThen let's go ahead and develop the case for write file.
11:02:1311 hours, 2 minutes, 13 secondsAfter write file, let's go ahead and develop the case for edit file.
11:02:2011 hours, 2 minutes, 20 secondsAfter that, let's develop the last one which is bash. Let me go ahead and slowly show you the entire thing here.
11:02:2911 hours, 2 minutes, 29 secondsSo this is bash. I can zoom out just a bit so it fits on the screen. This is our bash tool. Feel free to pause the screen if you want to type it out.
11:02:4011 hours, 2 minutes, 40 secondsThen let's go ahead and add a default case which is simply to throw unknown tool. Great. So we have now replicated
11:02:4911 hours, 2 minutes, 49 secondsall of the execution logic inside of the CLI package. so it can safely be executed here and not on the server. Now
11:02:5611 hours, 2 minutes, 56 secondsit's time to develop the refactoring of our chat.ts route. Unfortunately, the diff is so big
11:03:0511 hours, 3 minutes, 5 secondsthat it simply makes sense to start all over. But the good news is that the end result is going to be drastically
11:03:1311 hours, 3 minutes, 13 secondssimpler than what we have now and also much shorter. So let's go ahead and delete the entire thing and let's start
11:03:2011 hours, 3 minutes, 20 secondswith the imports. So we add hono validator and zod. Then from the AI
11:03:2611 hours, 3 minutes, 26 secondspackage, let's add all of these. Then let's go ahead and add our database. And let's go ahead and add the type Prisma.
11:03:3611 hours, 3 minutes, 36 secondsI'm going to see what the error here is.
11:03:3811 hours, 3 minutes, 38 secondsI think we don't import database. I think we import client, but we're going to see in a second. So let's go ahead and get get tool contracts mode schema
11:03:4711 hours, 3 minutes, 47 secondstype mode type and type tool contracts all from night code shared. Then let's
11:03:5511 hours, 3 minutes, 55 secondsgo ahead and import build system prompt from our newly refactored system prompt. Let's go ahead
11:04:0211 hours, 4 minutes, 2 secondsand add some middleares here. So this one is for authentication. This one is for sufficient balance or billing. Let's import calculate credits for usage.
11:04:1411 hours, 4 minutes, 14 secondsLet's import our ingest AI usage from polar. And finally, let's import is supported chat model and resolve chat
11:04:2211 hours, 4 minutes, 22 secondsmodel from lib models. Now, let me go ahead and resolve what we have in the database here. So, perhaps I need to do
11:04:3111 hours, 4 minutes, 31 secondsbun run database sorry bonex prisma generate.
11:04:3911 hours, 4 minutes, 39 secondsSo it's not database. Let me see how how are we importing this usually.
11:04:5211 hours, 4 minutes, 52 secondsLet me quickly check inside of sessions. Oh, database client. My apologies.
11:05:0211 hours, 5 minutes, 2 secondsAll good. All right. And yes, we have some errors in the sessions, but we're going to fix that. So yes, my my bad about the night code database import. We
11:05:1011 hours, 5 minutes, 10 secondsneed to do it with another forward slashclient here. So we explicitly request the client and then we get the database. All right. So now let's go ahead and continue developing this.
11:05:2111 hours, 5 minutes, 21 secondsWe're going to add a type chat message.
11:05:2511 hours, 5 minutes, 25 secondsIn here we're going to maintain the mode for each message, the model, the duration, and the usage. Let's go ahead
11:05:3211 hours, 5 minutes, 32 secondsand develop a type from that by constructing it by using UI message from AI. In here, we can then append the
11:05:4111 hours, 5 minutes, 41 secondsmetadata that we intend to ex extend the existing um UI message with and some tools here for tool contracts which
11:05:5111 hours, 5 minutes, 51 secondswe've defined. Now let's go ahead and develop the submit schema using zod
11:05:5811 hours, 5 minutes, 58 secondswhich accepts the ID and accepts the messages. Messages are an array of a custom object with a type of night code
11:06:0611 hours, 6 minutes, 6 secondsUI message and it's a minimum of one otherwise the validate UI messages will break. In here
11:06:1411 hours, 6 minutes, 14 secondswe maintain the mode and down here we maintain the model.
11:06:2111 hours, 6 minutes, 21 secondsNow let's go ahead and define the submit validator using ZV validator. Let's go ahead and develop a helper function has
11:06:2911 hours, 6 minutes, 29 secondspending tool calls. In here we have to skip all pending or dynamic tool calls because that is otherwise going to hang
11:06:3811 hours, 6 minutes, 38 secondsforever on the CLI. This is easier to understand if we first wrote it
11:06:4511 hours, 6 minutes, 45 secondsincorrectly and then had to fix it. But since I want to focus in this lesson on
11:06:5211 hours, 6 minutes, 52 secondsjust bringing you the working version of the code, you're just going to have to trust me that we have to skip certain
11:06:5911 hours, 6 minutes, 59 secondstools or certain deltas like output available, output error, dynamic tool uh simply because it's not going to work
11:07:0711 hours, 7 minutes, 7 secondsbecause things kind of change now that we execute tools on the client instead of the server. So we have to purposely
11:07:1511 hours, 7 minutes, 15 secondsskip some because uh as I said it will infinitely hang on the client and not a
11:07:2211 hours, 7 minutes, 22 secondssingle tool would ever be able to be executed. That's why we need this function right here.
11:07:2811 hours, 7 minutes, 28 secondsNow let's go ahead and develop the actual router here using Hono and pass along the authenticated environment here. And let's go ahead and start with
11:07:3711 hours, 7 minutes, 37 secondsa simple post request. So I'm going to go ahead and open the post request. And in here, I'm going to establish
11:07:4711 hours, 7 minutes, 47 secondsthe slash route, which will essentially be the chat route. For the middleware, we're going to use require credits balance and submit validator.
11:07:5611 hours, 7 minutes, 56 secondsAnd then let's go ahead and add an asynchronous function here.
11:08:0311 hours, 8 minutes, 3 secondsInside of the asynchronous function, let's go ahead and extract the user ID as well as all the body parameters from
11:08:1011 hours, 8 minutes, 10 secondsthe validated JSON because we are using ZV validator from HONO. Then let's go ahead and load the actual session scoped
11:08:2011 hours, 8 minutes, 20 secondsto the ID and the user ID. And if we can't find any session, we have to throw an error meaning that we can't do uh any
11:08:2811 hours, 8 minutes, 28 secondsAI generation because the session hasn't been found. In order to calculate the duration of the messages for the UI
11:08:3711 hours, 8 minutes, 37 secondsdisplay, we have to start a timer like this. Then let's go ahead and invoke all
11:08:4411 hours, 8 minutes, 44 secondsthe tools like this. Let's go ahead and obtain a resolved model. Let's go ahead
11:08:5211 hours, 8 minutes, 52 secondsand obtain previous messages or an empty array if we can't find any. Let's go
11:08:5911 hours, 8 minutes, 59 secondsahead and add a copy of them in merged messages here so we don't mutate them directly. Now let's go ahead and go over
11:09:0711 hours, 9 minutes, 7 secondseach message inside of our messages here.
11:09:1311 hours, 9 minutes, 13 secondsAnd let's go ahead and create incoming message which should satisfy night code UI message.
11:09:2411 hours, 9 minutes, 24 secondsThen let's go ahead and find the existing message index using merged messages. And let's go ahead and decide
11:09:3211 hours, 9 minutes, 32 secondswhere to assign it. So if existing messages index is minus one, we have to push it in the array. Otherwise, we have
11:09:4011 hours, 9 minutes, 40 secondsto put it in place of the existing message index.
11:09:4411 hours, 9 minutes, 44 secondsOutside of this for loop here, let's go ahead then and define next
11:09:5211 hours, 9 minutes, 52 secondsmessages using await validate UI messages function from AI and assign the night code UI message type here.
11:10:0111 hours, 10 minutes, 1 secondHere we are. And alongside messages, also add the tools. So this can properly be validated with the tools it had at
11:10:0911 hours, 10 minutes, 9 secondsthe time. Now let's go ahead and load all of the model messages.
11:10:1411 hours, 10 minutes, 14 secondsAnd let's go ahead and define a constant which will change later. Completed usage.
11:10:2011 hours, 10 minutes, 20 secondsNow let's go ahead and define the result.
11:10:2511 hours, 10 minutes, 25 secondsThe result uses a stream text API from AI SDK passes along the model from our our resolved model API. The system using
11:10:3411 hours, 10 minutes, 34 secondsbuild system prompt and the mode messages from model messages and the tools. But the cool thing is the tools
11:10:4111 hours, 10 minutes, 41 secondsis only calling the tool contracts meaning that there is no execution being done here. So we still need to have tools on the server but they shouldn't
11:10:5011 hours, 10 minutes, 50 secondsbe executing anything. We have the provider options here and we have an unfinish event to calculate the completed usage. Great. Now let's go
11:10:5911 hours, 10 minutes, 59 secondsahead and instead of developing our own event source parser, what we can simply do is return AI SDKs one which will be
11:11:0711 hours, 11 minutes, 7 secondscompatible with the use chat hook. So first things first, let's add original messages here. Now let's go ahead and
11:11:1511 hours, 11 minutes, 15 secondsadd or should I say construct message metadata. We need this because I still
11:11:2211 hours, 11 minutes, 22 secondswant to maintain the UI look and feel of our messages. So I have to construct the metadata as it was. Okay. So if part
11:11:3111 hours, 11 minutes, 31 secondstype is start return mode and model. If part type isn't finish returned
11:11:3811 hours, 11 minutes, 38 secondsundefined. And for all other instances return mode model duration milliseconds which is calculated with date now minus
11:11:4711 hours, 11 minutes, 47 secondsstart time. And if we have completed usage go ahead and add that as well. Now let's go ahead and decide what happens
11:11:5711 hours, 11 minutes, 57 secondson an async on finish event here. So in here first things first if it's aborted let's go ahead and do an early return.
11:12:0611 hours, 12 minutes, 6 secondsThen if it has pending tool calls. So this is why we had to do that function.
11:12:1211 hours, 12 minutes, 12 secondsSo if it has any of those tools let's go ahead and do an early return so it doesn't hang forever. After we solve
11:12:1911 hours, 12 minutes, 19 secondsthose two cases, let's go ahead and update the database session by updating the messages.
11:12:2611 hours, 12 minutes, 26 secondsThen let's go ahead and do an early return if there is no completed usage.
11:12:3211 hours, 12 minutes, 32 secondsBut if there is completed usage, let's go ahead and open a try and catch block and let's attempt to ingest the billable
11:12:3811 hours, 12 minutes, 38 secondsusage. So we can now use our calculate credits for usage using resolved model provider model ID and completed usage
11:12:4711 hours, 12 minutes, 47 secondsand finally get the billable usage. And then what we can do is we can await inest AI usage from our polar lib for this user ID for this amount of credits.
11:12:5911 hours, 12 minutes, 59 secondsAnd if we get an error in this process, it means we were unable to build a user.
11:13:0411 hours, 13 minutes, 4 secondsSo we're just going to log that for us for now like this.
11:13:0811 hours, 13 minutes, 8 secondsAnd finally, let's go ahead and add the last line of code here, which is on error for which we want to simply parse
11:13:1611 hours, 13 minutes, 16 secondsthe error and return it. And last but not least, let's not forget to export the app. There it is. That is the last line. So this is our new rebuilt chat.
11:13:2811 hours, 13 minutes, 28 secondsDS route. If you compare it to what we had before, which we can actually do using a git diff here, you will notice that it is drastically simpler. Take a
11:13:3611 hours, 13 minutes, 36 secondslook at how much file was deleted in comparison to how much it was added. So we are pretty much done already here.
11:13:4311 hours, 13 minutes, 43 secondsTake a look at all this file which was deleted.
11:13:4711 hours, 13 minutes, 47 secondsAll of this is now handled via AI SDK instead of having to maintain our own version. So I think this was a much much
11:13:5511 hours, 13 minutes, 55 secondsbetter solution. Now let's go ahead and fix our sessions route which will be much simpler than this. Go inside of sessions here and let's start by fixing
11:14:0411 hours, 14 minutes, 4 secondsthe imports here. So we are we can completely remove the ro mode and message status from here and we can also
11:14:1211 hours, 14 minutes, 12 secondsremove is supported chat model. So we only have authenticated environment require credits balance z validator zod
11:14:2211 hours, 14 minutes, 22 secondsdatabase and hono. These are the only things we should have. So inside of the
11:14:2911 hours, 14 minutes, 29 secondscreate session schema we can pretty much delete everything but the title. That's the only thing that matters here. And
11:14:3711 hours, 14 minutes, 37 secondsthen down here when we actually uh load the let's see. So this one is perfectly fine. I think that this individual one
11:14:4611 hours, 14 minutes, 46 secondsis a bit problematic. Here it is. So when we load the individual session, we now no longer need to include anything.
11:14:5111 hours, 14 minutes, 51 secondsIt's included by default because it's now a JSON field here. Okay. And then what we should do here in the post
11:14:5911 hours, 14 minutes, 59 secondsmethod, we should let's see we have this initial message here.
11:15:0411 hours, 15 minutes, 4 secondsWe don't need any of that. I think we can now just get rid of this. And let's see user ID. Yeah, we can just do data
11:15:1411 hours, 15 minutes, 14 secondshere like that. And we don't need to do this entire thing. And we don't need to add any include. So as simple as this.
11:15:2311 hours, 15 minutes, 23 secondsLet's take a look again. So just data session data user ID here. We can leave this. It's useful for mocking. And you
11:15:3311 hours, 15 minutes, 33 secondsbasically shouldn't have any errors in your code. So a much much simpler version of sessions now. Brilliant. Now that we have a brand new chat.ts and
11:15:4111 hours, 15 minutes, 41 secondssessions.ds, it's time for us to rebuild our use chat hook. Take a look at how
11:15:4811 hours, 15 minutes, 48 secondsmassive this hook is because it needed to handle all of the things that chat.TS was previously returning. So it was a
11:15:5711 hours, 15 minutes, 57 secondsvery complicated hook. Let's go ahead and delete it entirely and let's build a much more simpler and elegant solution
11:16:0411 hours, 16 minutes, 4 secondsfor it. So, we're going to import use memo and use chat and we're going to alias it as use AI chat from AI SDK
11:16:1211 hours, 16 minutes, 12 secondsReact. Then, let's go ahead and add all of these imports from the AI package.
11:16:1711 hours, 16 minutes, 17 secondsLet's go ahead and add all of these imports from our new night code shared.
11:16:2111 hours, 16 minutes, 21 secondsAnd finally, API client get out and execute local tool. So we are finally going to be doing this on the client
11:16:2911 hours, 16 minutes, 29 secondshere. Let's go ahead and export the type chat message with mode model duration in milliseconds and usage. Let's go ahead and develop the type for chat tools.
11:16:4111 hours, 16 minutes, 41 secondsThen let's go ahead and export the type for the message. And finally let's export our use chat function here. It
11:16:5011 hours, 16 minutes, 50 secondswill accept session ID and initial messages. First thing we need to do is we need to define a transport which will
11:16:5711 hours, 16 minutes, 57 secondsbe passed to the use chat hook. Well, not this use chat but this use chat from AI SDK react. So inside of this use memo, let's go ahead and open it.
11:17:1211 hours, 17 minutes, 12 secondsAnd in here, let's go ahead and immediately return new default chat transport and pass along the message
11:17:2111 hours, 17 minutes, 21 secondstype. Inside of this default chat transport, we have to define which API endpoint we are going to target. So we
11:17:2911 hours, 17 minutes, 29 secondscan use API client chat and request the URL from that and then go ahead and parse it to string. This is essentially
11:17:3611 hours, 17 minutes, 36 secondsgoing to target this chat.ts route which we have been refactoring.
11:17:4211 hours, 17 minutes, 42 secondsSo since this is even though we used API client here we only use it to get the URL this default chat transport has its
11:17:5011 hours, 17 minutes, 50 secondsown fetch function here which means we have to add the headers to make sure it has the out. So that's why we need to do it separately here. We need to get out
11:17:5911 hours, 17 minutes, 59 secondsif it's available. We have to add the bearer token otherwise just pass along new headers. Let's go ahead and further prepare the send messages request.
11:18:1011 hours, 18 minutes, 10 secondsextract the messages prop from here.
11:18:1211 hours, 18 minutes, 12 secondsLet's go ahead and start by getting the last message. If there is no message, let's go ahead and throw no message to
11:18:2111 hours, 18 minutes, 21 secondssend. Then let's go ahead and obtain the metadata from the message using an optional chain
11:18:2911 hours, 18 minutes, 29 secondsmethod. Then let's go ahead and define the previous message.
11:18:3411 hours, 18 minutes, 34 secondsAnd finally, let's construct the request messages by using the message ro. So if message ro is assistant and if pre
11:18:4211 hours, 18 minutes, 42 secondsprevious message ro is user, let's go ahead and make sure we have the proper order here.
11:18:4911 hours, 18 minutes, 49 secondsAnd let me indent this. Okay.
11:18:5211 hours, 18 minutes, 52 secondsAnd finally, let's go ahead and do a return here body with ID, messages, mode, and model
11:19:0211 hours, 19 minutes, 2 secondslike this. And in the dependency array of this use memo, we need to add a session ID. So it is updated for every
11:19:1011 hours, 19 minutes, 10 secondsnew session. And now let's go ahead and actually use use AI chat. So instead of
11:19:1711 hours, 19 minutes, 17 secondshaving to develop all of those deltas and checking for all of those different things, we can now just use uh use AI
11:19:2511 hours, 19 minutes, 25 secondschat. And in here we can pass along a session ID which kind of serves as a key. So it's going to reset every time the session ID changes. This session ID
11:19:3311 hours, 19 minutes, 33 secondscould be whatever messages basically the initial messages transport which is essentially the fetch client. And then
11:19:4311 hours, 19 minutes, 43 secondshere's where the magic happens on tool call. This is where we decide that we are going to execute the tools. First
11:19:5011 hours, 19 minutes, 50 secondsthing we have to do is we have to extract what mode are we in which we're going to use by getting the last message mode. And then we're going to go ahead
11:19:5911 hours, 19 minutes, 59 secondsand call void execute local tool. From the tool call, we're going to pass along the tool name, tool input, and finally
11:20:0711 hours, 20 minutes, 7 secondsthe mode. And then let's [snorts] go ahead and chain a dot then here. And I
11:20:1411 hours, 20 minutes, 14 secondsam purposely using dot then instead of awaiting because if you await on tool call, it can lead to hangs. Okay? So
11:20:2411 hours, 20 minutes, 24 secondsmake sure you use then and then use chat add tool output and this information here so we can properly display it in
11:20:3111 hours, 20 minutes, 31 secondsour UI. And the same way we handle dot then let's handle catch in case any
11:20:3911 hours, 20 minutes, 39 secondserror happens. And then let's go ahead down here and add one more property send automatically when last assistant
11:20:4711 hours, 20 minutes, 47 secondsmessage is complete with tool calls from AI. So a handy helper here. And guess what? That's it. That's the entire hook.
11:20:5611 hours, 20 minutes, 56 secondsAll we have to do is return the information now. So let's go ahead and return the simple ones first. Messages,
11:21:0311 hours, 21 minutes, 3 secondsstatus, and error. Then let's go ahead and develop the submit method. So the submit method has params which are user
11:21:1111 hours, 21 minutes, 11 secondstext, mode, and model. And it immediately returns chat send message.
11:21:1611 hours, 21 minutes, 16 secondsSo be careful here. Some of you might want to wrap this inside of parenthesis like this, which is fine, but then you have to remember to do an explicit
11:21:2411 hours, 21 minutes, 24 secondsreturn here. I actually prefer this. I always like opening the brackets and explicitly saying return because then I understand what this is. So when you
11:21:3111 hours, 21 minutes, 31 secondshover over submit, this is how it should look like. That's how you know you did it correctly. It should basically immediately be the send message which is
11:21:3911 hours, 21 minutes, 39 secondsright here. Okay, now that we have that ready, let's go ahead and add two more things
11:21:4811 hours, 21 minutes, 48 secondswhich are abort and interrupt. So this looks useless, but it's because I'm adapting this so our existing code works
11:21:5611 hours, 21 minutes, 56 secondsas much as possible. I don't want to do a huge refactor. Okay, so that's why I'm purposely doing this. So it's kind of a backwards compatibility that I'm adding
11:22:0411 hours, 22 minutes, 4 secondshere. And that is it. That is our entire refactor of use chat hook. Let me show you the drastic difference. So the red
11:22:1211 hours, 22 minutes, 12 secondslines are what we removed and the green lines are what we added. Take a look at this. How many lines of code were
11:22:2011 hours, 22 minutes, 20 secondsremoved for a more elegant solution because we discovered that we can actually use use chat. So you might be wondering was all of this a waste of
11:22:2911 hours, 22 minutes, 29 secondstime? Well, not really. Rarely do people embark on building their own version of AI SDK which is essentially what we did.
11:22:3711 hours, 22 minutes, 37 secondsBut eventually we came to a conclusion that it's better if we used AI SDK in the first place. Well, we learned that
11:22:4411 hours, 22 minutes, 44 secondsand we're fixing it right now. Let's continue fixing some broken types. Now, so back inside of packages CLI source components command menu and types.ts.
11:22:5611 hours, 22 minutes, 56 secondsYou can see we have some errors. So we can now remove supported chat model ID
11:23:0411 hours, 23 minutes, 4 secondsand we can remove mode and we can import both from night code shared like this.
11:23:1111 hours, 23 minutes, 11 secondsLet's go ahead and switch mode for mode type here and here. And just like that we fixed our command menu types. Now
11:23:2011 hours, 23 minutes, 20 secondslet's go inside of our dialogues here and let's go inside of agents dialogue.
11:23:2511 hours, 23 minutes, 25 secondsSo similar thing here instead of database engines let's go night code shared and we need to import mode yes
11:23:3411 hours, 23 minutes, 34 secondsbut we also need to import the mode type. So let's go ahead and set available modes to be this current mode
11:23:4111 hours, 23 minutes, 41 secondsto be mode type on select mode param to use mode type and the label to use mode type and down here once again mode type.
11:23:5311 hours, 23 minutes, 53 secondsSo those are some of the things that we need to do. Let's go ahead and continue by going inside of the components here
11:23:5911 hours, 23 minutes, 59 secondsand let's find input bar. If you scroll at the top here, you will once again find the import for database enums. Just
11:24:0911 hours, 24 minutes, 9 secondschange it to shared in here. You don't need to change anything else. You can see that it's all working just fine.
11:24:1611 hours, 24 minutes, 16 secondsGreat. So that is those three completed.
11:24:2011 hours, 24 minutes, 20 secondsUh let's go ahead and see what else we can do. We should also have messages user message. So once again let's go
11:24:2911 hours, 24 minutes, 29 secondsahead and replace database enions with shared and let's go ahead and add type mode type. And let's replace this with
11:24:3811 hours, 24 minutes, 38 secondsmode type. Another easy win here. Let's go ahead and do some other changes. So
11:24:4611 hours, 24 minutes, 46 secondswe have spinner right here which will once again uh rely on shared and we need to add
11:24:5611 hours, 24 minutes, 56 secondstype mode type here. So let's just add it like that. There we go. Then let's go inside of status bar which is the same.
11:25:0711 hours, 25 minutes, 7 secondsSo we need to import from shared but in here we don't need to import the mode type. So it is actually uh somewhat simpler.
11:25:1611 hours, 25 minutes, 16 secondsNow let's go ahead again in the CLI source. Let's go inside of providers this time. Prompt config index.ts.
11:25:2611 hours, 25 minutes, 26 secondsSo I'm going to go here first and I'm going to change this to be shared. Oh, since we already have one shared, let's
11:25:3311 hours, 25 minutes, 33 secondsgo ahead and reuse it then. So we have default chat model ID. We have uh type supported chat model ID. I'm going to
11:25:4211 hours, 25 minutes, 42 secondsadd the actual mode. I'm going to add the type mode type and let's see what else am I going to
11:25:5011 hours, 25 minutes, 50 secondsdo. Okay, so we need to import this before the other types and we need to add a comma here.
11:25:5711 hours, 25 minutes, 57 secondsLet me just see. So default chat model ID mode type supported chat model ID type mode type.
11:26:0611 hours, 26 minutes, 6 secondsOkay, I think those are all we need. And now in the context value, change this to be mode type. this to be mode type. Down
11:26:1311 hours, 26 minutes, 13 secondshere, find the prompt config provider and find the use state and change this to be mode type as well. I think that is the entire thing fixed here. All right.
11:26:2511 hours, 26 minutes, 25 secondsNow, let's go ahead inside of packages CLI source. Uh I think this
11:26:3411 hours, 26 minutes, 34 secondsis in screens here. Let's go inside of a new session. Yes, we should have an error here as well. So once again go
11:26:4011 hours, 26 minutes, 40 secondsahead and import from shared and this time we're going to need to add mode
11:26:4711 hours, 26 minutes, 47 secondsschema. Okay. So instead of using the enum here let's use the actual mode
11:26:5411 hours, 26 minutes, 54 secondsschema since we have it now. And then we have to scroll all the way down to create session here. And in here we can
11:27:0211 hours, 27 minutes, 2 secondsget rid of the path and the initial message. So we only care about the title because that's how we modified the sessions endpoint for if you remember.
11:27:1011 hours, 27 minutes, 10 secondsAnd let's go ahead and quickly revisit our navigate here. So sessions session ID is good. Replace true is good. And let's go ahead and open the state here.
11:27:2111 hours, 27 minutes, 21 secondsSo we have session but we should also have the initial prompt and set it to be the state like this.
11:27:3011 hours, 27 minutes, 30 secondsLet me just confirm that. So this is the state that we are talking about. Okay.
11:27:3611 hours, 27 minutes, 36 secondsSo that is another one fixed.
11:27:4011 hours, 27 minutes, 40 secondsAnd now we have some bigger things to do. But before we go on to those bigger ones, let's go ahead and do one more
11:27:4811 hours, 27 minutes, 48 secondsthing that I know we're going to have to do inside of messages. Let's go inside of uh actually no, my apologies. Inside
11:27:5811 hours, 27 minutes, 58 secondsof session shell, this is the one that we need. So in here, let's find the scroll box. This one where it
11:28:0711 hours, 28 minutes, 7 secondsencapsulates the children and go ahead and remove this gap simply because what we're going to do next is we're going to modify the messages which are a bit more
11:28:1511 hours, 28 minutes, 15 secondscomplex. Perfect. So we knocked out a lot of easy wins and now we have to do some tiny bit more complex refactoring
11:28:2411 hours, 28 minutes, 24 secondsfor the messages, but nothing scarier than the chat route or the use chat. So don't worry, let's go ahead and refactor
11:28:3011 hours, 28 minutes, 30 secondsour sessions screen. So in inside of CLI screens session dsx. You can see we have
11:28:3811 hours, 28 minutes, 38 secondsa lot of things we have to fix. So let's start by adding use ref to the react here. Then let's remove milliseconds from here as we no longer need that.
11:28:4911 hours, 28 minutes, 49 secondsThen from night code shared let's go ahead and remove message parts schema
11:28:5611 hours, 28 minutes, 56 secondsbecause it no longer exists there and instead let's go ahead and import type mode type from there. So we have mode
11:29:0411 hours, 29 minutes, 4 secondstype and we have the supported chat uh model ID. All right. Then let's go ahead
11:29:1411 hours, 29 minutes, 14 secondsdown here from the use chat hook and we can remove the unused client message part now because it's much simpler this
11:29:2311 hours, 29 minutes, 23 secondstime. Uh for the eniums we can delete this entirely. We no longer need that.
11:29:2811 hours, 29 minutes, 28 secondsAnd I think that that's all we have to do.
11:29:3311 hours, 29 minutes, 33 secondsLet me just see. Type message from use chat. It's all here. Okay. a lot of imports so I don't want to get lost but
11:29:4111 hours, 29 minutes, 41 secondsI'm pretty confident that we now have everything that we need. Now let's go ahead down here and let's find session
11:29:4811 hours, 29 minutes, 48 secondslocation schema and let's add the initial prompt. So it's going to be optional object with a message mode and
11:29:5611 hours, 29 minutes, 56 secondsmodel using these custom types which we have imported above. We can delete the entire map database messages function.
11:30:0511 hours, 30 minutes, 5 secondsWe don't need it anymore. So we can now directly go inside of chat message here and let's go ahead and start fixing some
11:30:1311 hours, 30 minutes, 13 secondsthings. Okay. So the first thing I want to do here inside of message roll user
11:30:2111 hours, 30 minutes, 21 secondslet's go ahead and extract the text part using message.parts filter for all types which are which are
11:30:2811 hours, 30 minutes, 28 secondstext and then simply map all their text values and then join that array. And once you have that text, you can go
11:30:3511 hours, 30 minutes, 35 secondsahead and pass that as the value of message. Now for the mode, we have to use the metadata. Okay, so we have to go
11:30:4411 hours, 30 minutes, 44 secondsto message metadata mode or fallback to build if we truly don't have uh anything
11:30:5111 hours, 30 minutes, 51 secondselse to display. Great. Now, uh, about the error, I'm pretty confident we don't
11:31:0011 hours, 31 minutesneed it, but I'm not entirely sure. Let me just, um, quickly check that is
11:31:0811 hours, 31 minutes, 8 secondscorrect. Yeah, we do not need the error handled here at all. We can go ahead immediately and fix the bot message
11:31:1611 hours, 31 minutes, 16 secondshere. So, parts are okay, but the model should once again be coming from the metadata. So message metadata model or
11:31:2511 hours, 31 minutes, 25 secondsunknown. Same thing for the mode metadata mode. And guess what? Same
11:31:3311 hours, 31 minutes, 33 secondsthing for the duration. One thing we're going to delete immediately here is going to be this interrupted prop. So
11:31:4211 hours, 31 minutes, 42 secondswe're going to get rid of that. Uh you can ignore the type error here for now because we are later going to refactor the bot message as well. So it doesn't
11:31:5011 hours, 31 minutes, 50 secondsreally matter that much. All right. Now, let's go inside of session chat and let's see what's different here. So,
11:31:5611 hours, 31 minutes, 56 secondsbesides having session, we now also have initial prompt. Let's go ahead and add a
11:32:0311 hours, 32 minutes, 3 secondsquick type for that. So, here is the definition for what is the session. And beneath it, let's add an optional
11:32:1211 hours, 32 minutes, 12 secondsinitial prompt with a message mode and model. Great. Now in here we have
11:32:1911 hours, 32 minutes, 19 secondsinitial messages but we have to no longer use map database messages.
11:32:2411 hours, 32 minutes, 24 secondsInstead we can just use session messages as unknown as an array of messages.
11:32:3011 hours, 32 minutes, 30 secondsOkay. And now in here this is where we use our new use chat hook. So let me just collapse this so it's easier for me
11:32:3811 hours, 32 minutes, 38 secondsto look at it. Session ID and initial messages. And we no longer have streaming but we do have status. So we can add that instead. We should have
11:32:4711 hours, 32 minutes, 47 secondssubmit. We have abort. We have interrupt. All of that looks good.
11:32:5211 hours, 32 minutes, 52 secondsBasically streaming was removed. Now right here we need to add has submitted initial prompt ref. And we have to set
11:33:0111 hours, 33 minutes, 1 secondthis to false. Okay. Uh so now let's go ahead and add uh let's go ahead and fix
11:33:0811 hours, 33 minutes, 8 secondsthis use effect. So what we have to do is we have to return as in when unmounted and simply do void abort.
11:33:1611 hours, 33 minutes, 16 secondsRemember we have to adhere by these rules because this abort is essentially message.stop from the use AI chat from
11:33:2411 hours, 33 minutes, 24 secondsAI SDK. Okay. So that's why we have to invoke it like this because it's their rules now not ours anymore. Okay. So
11:33:3311 hours, 33 minutes, 33 secondslet's see what's going on with the use keyboard here. So if key name is escape and is top layer is base. So now instead
11:33:4011 hours, 33 minutes, 40 secondsof streaming we are simply going to have the status streaming and the logic stays the same. So you can see we are
11:33:4811 hours, 33 minutes, 48 secondsadjusting for the API. We could essentially also do abort here but we mapped it under interrupt even though it's the same thing just so we don't
11:33:5511 hours, 33 minutes, 55 secondshave to uh refactor too many things. All right. Now, we have to add one use effect that didn't exist before, which
11:34:0211 hours, 34 minutes, 2 secondswe're going to use to uh submit the message whenever this screen loads because remember we have that cool thing that once you submit from the homepage,
11:34:1011 hours, 34 minutes, 10 secondsit kind of immediately shows you the loading screen. So, you don't have to wait on the home screen as you are blocked. So, because of that, we need
11:34:1711 hours, 34 minutes, 17 secondsthis use effect right here. So, this one, make sure you add initial prompt and submit in the dependency array. do an early return if there is no initial
11:34:2511 hours, 34 minutes, 25 secondsprompt or if you have already submitted the initial prompt and then immediately set that to true so it doesn't happen twice and then invoke submit using void
11:34:3411 hours, 34 minutes, 34 secondspass along the user text mode and model that's going to automatically submit the user's message which was navigated here through the initial prompt okay now
11:34:4311 hours, 34 minutes, 43 secondslet's go ahead and take a look at the session shell here so on submit looks fine user text which is text mode and
11:34:5211 hours, 34 minutes, 52 secondsmodel Uh but for the loading we do have to modify it. So it's going to be using
11:34:5911 hours, 34 minutes, 59 secondsstatus. And for interruptible once again it's going to be using status.
11:35:0511 hours, 35 minutes, 5 secondsFor mapping over messages it's going to be the same for chat message but once again uh it will be different for bot message. In fact we are not going to
11:35:1411 hours, 35 minutes, 14 secondsrender bot message here at all for this streaming case. We can just get rid of it. Instead what we can do here is we
11:35:2211 hours, 35 minutes, 22 secondscan render the error message like this if we have an error. Okay. Now down here we have our oh let me see looks like
11:35:3111 hours, 35 minutes, 31 secondserror is missing. How did I uh miss that? Oh yes we can get the error from our new hook. So in here in use chat go
11:35:4011 hours, 35 minutes, 40 secondsahead and extract error from here and that should fix the error rendering.
11:35:4511 hours, 35 minutes, 45 secondsOkay let's go inside of the session here now.
11:35:4911 hours, 35 minutes, 49 secondsSo some slight modifications are needed here but nothing too heavy. So instead
11:35:5611 hours, 35 minutes, 56 secondsof session in here it should no longer be parsed data session. So you can
11:36:0311 hours, 36 minutes, 3 secondsremove session here. Okay. And then inside of prefetched here what we're going to do
11:36:1111 hours, 36 minutes, 11 secondsis we're going to add question mark session or fallback to null.
11:36:1711 hours, 36 minutes, 17 secondsOkay. And then inside of the use effect here we are going to go ahead and do question mark session return. So we are
11:36:2611 hours, 36 minutes, 26 secondsexplicitly looking for session because data now has the initial prompt as well.
11:36:3011 hours, 36 minutes, 30 secondsSo now we have to go down here to where we render the session chat and alongside session
11:36:3811 hours, 36 minutes, 38 secondswe also need to pass the initial prompt and let's make that be prefetched question mark initial prompt like this.
11:36:4811 hours, 36 minutes, 48 secondsAnd to make this easier to look at, we can collapse these like that.
11:36:5611 hours, 36 minutes, 56 secondsAnd let's go ahead and do this.
11:37:0311 hours, 37 minutes, 3 secondsThere we go. Session chat key session and initial prompt. Great. So I believe that this is everything that we need to
11:37:1211 hours, 37 minutes, 12 secondsdo uh in this refactor. So now let's go ahead and refactor the last component and then we're ready to try all of this
11:37:1911 hours, 37 minutes, 19 secondsout and that last component is this bot message. You can see that we have an error here. So that's where we are going to fix it. Let's go ahead and refactor
11:37:2711 hours, 37 minutes, 27 secondsour CLI source components messages bot message which also has some errors here.
11:37:3411 hours, 37 minutes, 34 secondsSo we're going to start by changing the database enions into shared and then we
11:37:4011 hours, 37 minutes, 40 secondscan export the proper type from here mode type and we can modify the mode to
11:37:4711 hours, 37 minutes, 47 secondsuse the mode type from our hooks use chat. We can delete both of these types and we can simply import the type
11:37:5511 hours, 37 minutes, 55 secondsmessage. Okay. Now let's see what else do we need to have here. So I'm going to go ahead and import
11:38:0311 hours, 38 minutes, 3 secondspretty millisecond package which we removed from the other component. So we can purposely put it here. Uh and I think we don't need anything else. Okay.
11:38:1511 hours, 38 minutes, 15 secondsNow let's go ahead and develop the types that we need here. So we are going to create client message part like this.
11:38:2211 hours, 38 minutes, 22 secondsMessage parts and then a number. tool part is simply going to extract from the client message part for specific tools
11:38:2911 hours, 38 minutes, 29 secondslike this tool part that makes our props here correct now. So let's see we have parts which is client message part. We
11:38:3711 hours, 38 minutes, 37 secondshave model which is string mode was now fixed and we have to change from duration to duration milliseconds like this and let's change it into a number.
11:38:4811 hours, 38 minutes, 48 secondsStreaming can be a boolean and we can remove the interrupted prop. Okay. And just by doing this, I'm pretty confident
11:38:5511 hours, 38 minutes, 55 secondsthat if you go inside of our previous change, which was the session, you should no longer have any errors in the bot message because we now added
11:39:0311 hours, 39 minutes, 3 secondsduration milliseconds here. Okay, so that is props fixed. The format tool name function is correct. So we don't
11:39:1111 hours, 39 minutes, 11 secondshave to do anything here. But this one format tool arguments
11:39:1911 hours, 39 minutes, 19 secondsis a little bit different. And before we can develop it, we need to add a function is tool part which accepts the client message part and it returns a
11:39:2811 hours, 39 minutes, 28 secondspart which has to be a tool part. So it has to start with tool or it has to be dynamic tool. All right. And once we
11:39:3511 hours, 39 minutes, 35 secondshave that we can go ahead and fix our format tool argument here. So let's
11:39:4211 hours, 39 minutes, 42 secondsremove this function and let's rebuild it like this. Format tool arguments.
11:39:4811 hours, 39 minutes, 48 secondsAnd once we have that, let's go ahead and see what we have to do in group
11:39:5511 hours, 39 minutes, 55 secondsconsecutive parts here. All right. So here is the problem. Part type is tool
11:40:0111 hours, 40 minutes, 1 secondcall. Okay. So instead of doing this, we can simply call our new function is tool
11:40:1011 hours, 40 minutes, 10 secondspart and pass along the part. Okay. And instead of part ID, we can now use the
11:40:1811 hours, 40 minutes, 18 secondsnew API part tool call ID. All right, I believe all of this should now be fine.
11:40:2511 hours, 40 minutes, 25 secondsGroup type index part type part part.
11:40:2811 hours, 40 minutes, 28 secondsAll of this looks fine to me now. Uh now let's go ahead inside of the bot message and let's see which props do we need,
11:40:3611 hours, 40 minutes, 36 secondswhich props do we not need. parts we need model we need mode we need uh duration has now changed to duration in milliseconds and we can remove
11:40:4511 hours, 40 minutes, 45 secondsinterrupted entirely okay so now let's go ahead inside of this group
11:40:5211 hours, 40 minutes, 52 secondsconsecutive parts and let's see okay so we have a box group key padding
11:41:0111 hours, 41 minutes, 1 secondis equal to one uh so I want to remove this padding Okay.
11:41:0911 hours, 41 minutes, 9 secondsAnd what I want to do is I want to go inside of this inner.
11:41:1511 hours, 41 minutes, 15 secondsLet me just see. It's a bit confusing to look at this. Okay. Uh this is what I want to do. So I want to remove padding
11:41:2311 hours, 41 minutes, 23 secondsY and I want to add dynamic padding. So I have to extract the index from this map here. Okay. Padding top. If index is zero meaning if it's first then no
11:41:3211 hours, 41 minutes, 32 secondspadding top otherwise padding of one. So only subsequent messages have spacing but the first message shouldn't have any
11:41:3911 hours, 41 minutes, 39 secondsspacing at all. So down here we should pretty quickly find the error which is instead of using our new uh is tool part
11:41:4811 hours, 41 minutes, 48 secondswe're doing this. So let's simply do is tool part and once again instead of part ID we should do tool call ID.
11:41:5811 hours, 41 minutes, 58 seconds[snorts] All right. So, let me just confirm that's all we need to do. I'm pretty sure it is. Okay. So, now let's see uh what's wrong inside of this text
11:42:0811 hours, 42 minutes, 8 secondshere. So, format tool name. Uh okay.
11:42:1311 hours, 42 minutes, 13 secondsLet's see. Uh we should probably construct tool name first. So, let's do that in here. If is tool part.
11:42:2411 hours, 42 minutes, 24 secondsLet's go ahead and develop this tool name. So if part type is dynamic tool, you can extract part tool name from it.
11:42:3111 hours, 42 minutes, 31 secondsOtherwise, let's go ahead and remove tool dash from the part type. And then we're going to be left with whatever is
11:42:3911 hours, 42 minutes, 39 secondsthe name. And that's what we're going to get here. Tool name. Okay. And then we should be able to just pass along
11:42:4811 hours, 42 minutes, 48 secondstool name in here. Okay. So I don't want to change anything else. But for the
11:42:5511 hours, 42 minutes, 55 secondsoutput here, we need to make it a little bit different. So it's not going to be status. It's going to be part.state.
11:43:0111 hours, 43 minutes, 1 secondAnd we're going to do if not output available. You can see how we have type safety now. Okay. So if not output
11:43:0911 hours, 43 minutes, 9 secondsavailable, we're not done yet. And if partstate is not
11:43:1811 hours, 43 minutes, 18 secondsoutput error, then we're going to display three dots. Otherwise, we're going to display uh empty string. Okay.
11:43:2911 hours, 43 minutes, 29 secondsAnd then we're not done yet. Below that, we have to handle the error. Okay.
11:43:3811 hours, 43 minutes, 38 secondsSo, let's see. Do we have anything important here? I don't think so. But perhaps here. Uh yes, looks like here we
11:43:4711 hours, 43 minutes, 47 secondsdo. Okay. So, first things first, instead of padding bottom, let's do padding top and set it to one here.
11:43:5911 hours, 43 minutes, 59 secondsUh, let's see. Okay. Well, actually, we can just do padding Y. I think that might be smarter.
11:44:0711 hours, 44 minutes, 7 secondsOkay. So, box direction flex roll.
11:44:1311 hours, 44 minutes, 13 secondsSo, okay. What is wrong here?
11:44:1811 hours, 44 minutes, 18 secondsMhm. Oh, so this is for the interrupted one. Okay. So, I think it's easier to just delete this text element entirely.
11:44:2811 hours, 44 minutes, 28 secondsAnd then let's just go ahead and display whatever we need to display for the plan instead of doing the interrupted thing.
11:44:3711 hours, 44 minutes, 37 secondsOkay. Then let me go inside of this box here.
11:44:4211 hours, 44 minutes, 42 secondsSo text. So it's deciding for plan or build.
11:44:4811 hours, 44 minutes, 48 secondsOkay. Attributes. I don't think we need any attributes here. Let me just see.
11:44:5911 hours, 44 minutes, 59 secondsYeah, let's let's remove the attributes for now.
11:45:0411 hours, 45 minutes, 4 secondsYeah, because this is for interrupted, so we don't need that. Okay. Then we have this separator here.
11:45:1111 hours, 45 minutes, 11 secondsColors separator. I think that's fine.
11:45:1411 hours, 45 minutes, 14 secondsThen once again we have this logic for duration or interrupted. So what we can just do is we can check duration in
11:45:2111 hours, 45 minutes, 21 secondsmilliseconds and instead of checking for interrupted we can just check if not null. So if it's not null in that case
11:45:3011 hours, 45 minutes, 30 secondslet's just go ahead and render the duration. I think this should work just fine. Sorry for being so slow here but a
11:45:3811 hours, 45 minutes, 38 secondslot of things already exist. I have to look at my fix and I have to think at the same time.
11:45:4511 hours, 45 minutes, 45 secondsUh duration millisecond. Uh duration millisecond. This should work. But I'm
11:45:5211 hours, 45 minutes, 52 secondsdoing something wrong obviously. So let me check what it is. Oh, probably because I put an identical here. Yes. So
11:46:0011 hours, 46 minutesI shouldn't use identical. Okay. H but I think this might be it. I think we've
11:46:0811 hours, 46 minutes, 8 secondsdone all of the changes. I think that we are ready to try now. All right, for the
11:46:1511 hours, 46 minutes, 15 secondsmoment of truth, let's go ahead and try 32 files changed. Let's see if we fixed our big problem. All right, let's get
11:46:2211 hours, 46 minutes, 22 secondsstarted. So, first things first, I want to go uh inside of my packages and specifically inside of
11:46:3011 hours, 46 minutes, 30 secondsmy database and I just want to have my studio open. Okay, so it's going to be open right here. It's very small but
11:46:3811 hours, 46 minutes, 38 secondsit's mostly just so I see if I get any sessions here. So I currently have no sessions. Okay.
11:46:4611 hours, 46 minutes, 46 secondsUh I don't think I have to migrate anything. Okay. I'm going to do bun rundev server in this one. So far so
11:46:5311 hours, 46 minutes, 53 secondsgood. Okay. Then let's do bun rundev cli here. All right. So far so good. Let me go ahead and perform a login here.
11:47:0411 hours, 47 minutes, 4 secondsSo I'm not sure where this is opening. Okay, continue.
11:47:0911 hours, 47 minutes, 9 secondsLet me go ahead and allow my permissions. Okay, and I think I'm good. I think I'm able to log in now.
11:47:1711 hours, 47 minutes, 17 secondsOkay, let's try what is this project about. Let's see if we get any errors or
11:47:2511 hours, 47 minutes, 25 secondsnot. Let me explore the project structure to understand what the project is about. And are we seeing tool calls?
11:47:3211 hours, 47 minutes, 32 secondsEverything looks good. The rendering looks good. The grouping looks good. The duration in milliseconds seems to be working. Though, uh, it's displaying the
11:47:4011 hours, 47 minutes, 40 secondsmilliseconds directly. I wish it displayed it only once it's finished.
11:47:4411 hours, 47 minutes, 44 secondsKind of like an indicator that it's been done, but okay, for now. Okay. I mean, we should be able to figure out how to
11:47:5311 hours, 47 minutes, 53 secondsfix it. But yeah, let's wait for a second and see if this is now working.
11:47:5911 hours, 47 minutes, 59 secondsThis is plan mode for now. Great. So plan mode seems to work fine. Let's switch to build mode. If you want, you
11:48:0811 hours, 48 minutes, 8 secondscan also switch to a different model just for fun. And I'm going to tell it create a new file food.js with some content inside.
11:48:1711 hours, 48 minutes, 17 secondsSo let's see. It switched to build mode.
11:48:2011 hours, 48 minutes, 20 secondsAnd it is using GPT 5.4. It says created Fu.js with sample content. Let's see if
11:48:2811 hours, 48 minutes, 28 secondsthat's true. FU.js JS and sample content inside. Beautiful. So, I've purposely switched to a different mode and to a
11:48:3711 hours, 48 minutes, 37 secondsdifferent uh agent inside of the same session to confirm that is still working. So, let's go inside of new.
11:48:4211 hours, 48 minutes, 42 secondsLet's go inside of sessions and let's select this and just confirm that we can actually load a session from history.
11:48:4911 hours, 48 minutes, 49 secondsThat works as well. Brilliant. So, I can now take some time to look at my database here just to see how this looks. So it's going to be slightly
11:48:5611 hours, 48 minutes, 56 secondsdifferent because we now only have the sessions table and you can see that messages is now a JSON object here. It's very fluid which was simply an easier
11:49:0511 hours, 49 minutes, 5 secondsrefactor for us to do. Uh you can still use the messages table if you feel more comfortable with that. I will completely understand if you do that but I hope you
11:49:1311 hours, 49 minutes, 13 secondsunderstand why I chose to do the simpler version now simply so we can bring this refactor to an end and so you have a working project. I do see some logs in the server here.
11:49:2311 hours, 49 minutes, 23 secondsOkay, warning logging. Okay, this is unrelated.
11:49:3011 hours, 49 minutes, 30 secondsOkay, so it's warning me that I have some incompatible reasoning parts, but it's not breaking the app. It's just a
11:49:3711 hours, 49 minutes, 37 secondswarning. I mean, just a warning. It's good that we have it here, but that's purposely why I uh changed a different
11:49:4511 hours, 49 minutes, 45 secondsmodel and a different uh mode. Looks like we can still use it but AI SDK is warning us that some context could be lost but I am okay with that if it
11:49:5411 hours, 49 minutes, 54 secondsworks. If the context is persisted and if we can achieve what we wanted to achieve which is tool calling I am perfectly comfortable with that. So the
11:50:0211 hours, 50 minutes, 2 secondsonly thing that is tricky right now is the following. So uh write me a long message. So let's go ahead and switch to
11:50:1011 hours, 50 minutes, 10 secondsplan mode and tell it to do that. And if I press escape you can see I no longer have that interrupted state. And if I go back to new and if I go into session,
11:50:1811 hours, 50 minutes, 18 secondsyou will see that that last one won't be persisted. So that is the only thing we lost. Uh unfortunately it is a bit out
11:50:2611 hours, 50 minutes, 26 secondsof scope for this refactor because it does include some complicated logic. I would invite you to try and challenge yourself to implement that using AI.
11:50:3311 hours, 50 minutes, 33 secondsFeel free to do that. Uh I mean we are building a coding agent so obviously you now know how they work from inside out.
11:50:3911 hours, 50 minutes, 39 secondsSo you will be able to use them that much more effectively. But for the moment of truth, we actually have to try what we did in the beginning, which is
11:50:4711 hours, 50 minutes, 47 secondsattempting to use uh another version of the server. But we have to deploy it first. So let's do that. And then we'll test if it works. So let's go ahead and
11:50:5611 hours, 50 minutes, 56 secondsdo this. So I'm going to go back to the root and I'm going to do get checkout-b this is 10 client side tool execution. I
11:51:0411 hours, 51 minutes, 4 secondsthink that is the appropriate name for this chapter. Or migration to AI SDK would be another good one. Let's go
11:51:1211 hours, 51 minutes, 12 secondsahead and add all of the changes here. M 10 client side tool execution.
11:51:2011 hours, 51 minutes, 20 secondsGit push dash u origin 10 like that. There we go. So it should
11:51:2811 hours, 51 minutes, 28 secondsnow pop up here any second. Uh since this was a huge refactor, I think we're going to get like a billion comments from code rabbit. So you can just add
11:51:3511 hours, 51 minutes, 35 secondscode rabbit paused because I don't want to see the review right now. I mostly want to see if it works first. Okay. So,
11:51:4411 hours, 51 minutes, 44 secondsI'm going to go ahead and do merge pull request anyway. Let's just confirm the merge and we can fix it later if something doesn't work. Do not delete
11:51:5211 hours, 51 minutes, 52 secondsthe branch. I mean, if you care about that, you can see I maintain all of the changes here. So, you have branch 10.
11:51:5711 hours, 51 minutes, 57 secondsAnd now that this has been merged, what's happening here is that production is being rebuilt. So, since we didn't
11:52:0411 hours, 52 minutes, 4 secondsadd any new environment files, I think everything should be perfectly fine. One thing that I removed from here is the
11:52:1111 hours, 52 minutes, 11 secondsAPI URL. Even though I think it absolutely doesn't matter if you have that in the server. So don't worry if you don't see it here. I removed it
11:52:2011 hours, 52 minutes, 20 secondsbecause it's only used in the client, but it won't hurt the server. If it does, you can remove it and redeploy, but I highly doubt it would. Okay, so I'm going to wait until this finishes.
11:52:2911 hours, 52 minutes, 29 secondsAll right, so this is now deployed. So I'm going to click here. Okay, not found. All of this looks good. We already have this added here. So I don't
11:52:3811 hours, 52 minutes, 38 secondsthink we really need to do much. Uh what's important is that this is at the newest version so that it's merged and
11:52:4511 hours, 52 minutes, 45 secondslet's try it out now. So we shouldn't need to run our server now. The only thing we would need to do is modify our
11:52:5311 hours, 52 minutes, 53 secondsAPI URL. Just remove the trailing slash like this. And then let's see bun rundev CLI only. That's the only thing we need.
11:53:0311 hours, 53 minutes, 3 secondsSo I'm going to log in again because we are at an entirely new backend now, right? So let me log in here. So we get
11:53:1011 hours, 53 minutes, 10 secondsa new token. Let's allow access. Great, successful login. Let's go ahead and try this out. So this time the CLI is
11:53:1811 hours, 53 minutes, 18 secondsrunning locally, but the server is hosted somewhere else. So this is the production case, right? What would happen now? What is this project about?
11:53:2711 hours, 53 minutes, 27 secondsSo I am running night code inside of my local machine. So let's see are is tool execution now happening on the client or
11:53:3511 hours, 53 minutes, 35 secondsis it happening still on the server? You can see by the amount of read files and list directories we have successfully
11:53:4211 hours, 53 minutes, 42 secondsfixed this extremely problematic uh architectural issue that we had which
11:53:4911 hours, 53 minutes, 49 secondsunfortunately didn't uh allow the this project to read anything other but the servers file system. But now we can thankfully execute tools on the client.
11:54:0211 hours, 54 minutes, 2 secondsMeaning wherever you run this CLI is the place where uh it's going to be reading
11:54:0811 hours, 54 minutes, 8 secondsthe files. So we fixed that huge architectural uh issue that I've added.
11:54:1411 hours, 54 minutes, 14 secondsMy apologies for that once again and congratulations on this huge refactor.
11:54:1911 hours, 54 minutes, 19 secondsNow let's go ahead and just do get checkout main and get pull origin main.
11:54:2411 hours, 54 minutes, 24 secondsSo all of these changes are synchronized and you aren't on that branch, but you are on the main branch with all of the
11:54:3211 hours, 54 minutes, 32 secondschanges. And remember, if you want to develop, you have to revert this back to localhost 3000. Otherwise, it's always going to use your production server. So
11:54:4011 hours, 54 minutes, 40 secondschoose which use case you want to be with at the moment. And for the end, I want to teach you how you can run night code in any repository on your machine.
Chapter 14: The End
11:54:5011 hours, 54 minutes, 50 secondsSo just like you can call open code for example and it opens anywhere. It would be cool if we could do the same for
11:54:5811 hours, 54 minutes, 58 secondsnight code. Well, we can do it. So first things first, make sure that you actually use your deployed API URL. So
11:55:0711 hours, 55 minutes, 7 secondsyou don't need to have the server running. Then let's go ahead and do bun add dot environment. So in the root of
11:55:1511 hours, 55 minutes, 15 secondsyour project, your package json here should now have environment.
11:55:2111 hours, 55 minutes, 21 secondsNext, let's go ahead inside of CLI.
11:55:2611 hours, 55 minutes, 26 secondsIgnore the bin and dist folders. So I have them because I was just testing things out, but you probably don't have
11:55:3311 hours, 55 minutes, 33 secondsthem. So feel free to ignore them. But go inside of package JSON of the CLI.
11:55:3911 hours, 55 minutes, 39 secondsAnd in here, first things first, let's go ahead and create the launcher using
11:55:4611 hours, 55 minutes, 46 secondsbin night code and then target this bin folder night code. Then let's go ahead
11:55:5311 hours, 55 minutes, 53 secondsand create the actual build script down here like this. So bun build source
11:55:5911 hours, 55 minutes, 59 secondsindex outdoor dist target bun. Okay, now that we have that, let's go ahead and
11:56:0711 hours, 56 minutes, 7 secondscreate a bin folder. And inside, let's create a launcher night code like this.
11:56:1511 hours, 56 minutes, 15 secondsAnd in here, let's go ahead and paste this. So, we have shebang here. We
11:56:2311 hours, 56 minutes, 23 secondsimport environment. And we simply inject the environment file inside of here. and
11:56:2911 hours, 56 minutes, 29 secondswe import the index dsx. So right here, this is the launcher. Okay, so it should
11:56:3811 hours, 56 minutes, 38 secondsbe exactly like this path here, bin night code. Usually you could do this directly from the script, but because of
11:56:4611 hours, 56 minutes, 46 secondsbun, it has its own banner. So this shebang breaks entirely. So we need to develop it as a launcher. And this disc
11:56:5411 hours, 56 minutes, 54 secondsis simply uh where the thing is going to be built. You probably don't have this yet, but you should have the bin now because we just created it. And then go
11:57:0211 hours, 57 minutes, 2 secondsinside of package JSON. So, back here and go ahead and add the following. Add
11:57:0811 hours, 57 minutes, 8 secondsa comma and then bun. Um, my apologies, build CLI. And then beneath it, go ahead
11:57:1611 hours, 57 minutes, 16 secondsand add link CLI. So, what build CLI in the root package JSON is going to do is
11:57:2311 hours, 57 minutes, 23 secondsit's going to filter for night code. So make sure that instead of CLI package JSON, it's actually the name of the
11:57:3111 hours, 57 minutes, 31 secondspackage because that one is going to find it and run its build script. Okay.
11:57:3711 hours, 57 minutes, 37 secondsSo make sure that this is called build and this M code CLI and link CLI is going to run this
11:57:4511 hours, 57 minutes, 45 secondscommand which I just described. It's going to change directory inside of CLI and run bun link. So let's go ahead and
11:57:5311 hours, 57 minutes, 53 secondstry this out now. So in the root here bun run link C cli there we go everything seems to be successful let's
11:58:0111 hours, 58 minutes, 1 secondtry night code here and there we go but let's make it more fun and let's switch to some other project so this is
11:58:0911 hours, 58 minutes, 9 secondsresonance this is my open source 11 labs alternative my previous project and what happens if I run night code here let's
11:58:1711 hours, 58 minutes, 17 secondsswitch to plan mode and let's ask it what is this project about and let's see if it will be able to run
11:58:2511 hours, 58 minutes, 25 secondsindependently. So I don't have my server running. Uh it's it's deployed on railway. And here it is. Resonance open-source alternative to 11 labs.
11:58:3611 hours, 58 minutes, 36 secondsBeautiful. So we officially came to the end of this tutorial. So what could be the next steps for you? Well, obviously
11:58:4311 hours, 58 minutes, 43 secondsthere is a lot of polishing that could be done. For starters, you could commit this and deploy it. Of course, what I
11:58:5111 hours, 58 minutes, 51 secondswould recommend doing is challenging yourself and using maybe AI to adapt
11:58:5711 hours, 58 minutes, 57 secondsthis by adding a whole new script which will allow you to distribute this using GitHub releases to your users. I think
11:59:0611 hours, 59 minutes, 6 secondsthat would be a fun challenge and you're practically halfway there. The other part is just a script which allows you
11:59:1311 hours, 59 minutes, 13 secondsto install something using uh another shell script. So feel free to give yourself a challenge to do that. You now
11:59:2211 hours, 59 minutes, 22 secondshave night code available in your machine and you can use it just like you can clot code, open code or anything else. Congratulations on finishing your
11:59:3011 hours, 59 minutes, 30 secondsvery own coding agent and thank you so much for watching. See you in the next tutorial.

Sync to video time
