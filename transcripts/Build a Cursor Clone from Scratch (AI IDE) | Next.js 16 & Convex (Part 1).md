https://www.youtube.com/watch?v=Xf9rHPNBMyQ&t=20081s



Build a Cursor Clone from Scratch (AI IDE) | Next.js 16 & Convex
Code With Antonio
Code With Antonio
419k subscribers

Join


3.6k


Share

Ask

Save

103,355 views  5 Jan 2026
🎥 PART 2:    • Build and Deploy an AI Coding Agent | Curs...  

Try Clerk: https://cwa.run/clerk
Try Firecrawl: https://cwa.run/firecrawl
Try Convex: https://cwa.run/convex
Try Inngest: https://cwa.run/inngest
Try Sentry: https://cwa.run/sentry
Try CodeRabbit: https://cwa.run/coderabbit

💻 FREE Source Code: https://cwa.run/polaris
🎨 FREE Assets: https://cwa.run/polaris-assets

In this tutorial, we're building Polaris, a complete AI-powered code editor from scratch. You'll learn how to create a professional IDE with a CodeMirror 6 editor featuring syntax highlighting, code folding, and a minimap, integrate AI-powered code suggestions and quick edit functionality using Claude, handle background job execution for AI agents with multi-tool capabilities, and build a full SaaS business layer with authentication and GitHub OAuth. We'll also cover error tracking with LLM monitoring, in-browser code execution with WebContainer and live preview, and complete GitHub integration for importing and exporting repositories.

Key features:
🤖 AI code suggestions & quick edit
🧠 AI agent with file manipulation tools
📚 Live docs scraping with Firecrawl
✏️ CodeMirror 6 editor with minimap
▶️ In-browser execution with WebContainers
🐙 GitHub import & export
⚡ Background jobs with Inngest
🗄️ Real-time sync with Convex
🔐 Clerk authentication & billing
🐛 Sentry error tracking + LLM monitoring
🐰 CodeRabbit PR reviews
🌐 Next.js 16 + TypeScript

Timestamps
00:00 Intro
04:53 01 Project Setup
32:33 02 Authentication
53:31 03 Database Setup
1:52:15 04 Background Jobs
2:25:55 05 Firecrawl AI
2:50:46 06 Error Tracking
3:24:16 07 Projects
4:26:14 08 IDE Layout
5:23:36 09 File Explorer
7:14:06 10 Code Editor State
8:59:58 11 AI Features
10:40:45 12 Conversation System
11:55:48 End of Part 1
Ask
Get answers, explore topics and more

Ask questions

--------------------------------------------------
In this video


Chapters

Transcript
Search transcript
Search transcript

Chapter 1: Intro
0:000 secondsAI editors like Cursor have changed how developers write code. But have you ever wondered what's actually happening
0:088 secondsbehind the scenes? In this tutorial, we're building Polaris, a complete AI powered IDE from scratch, Ghost Text
0:1717 secondsSuggestions, an AI agent that can create and modify your files, live preview running entirely in the browser, and
0:2626 secondsfull GitHub integration. This is how modern AI coding tools actually work.
0:3333 secondsLet's start with project creation. Open the new project dialogue. Describe what you want to build in plain English and
0:4141 secondswatch the AI generate your entire project structure in real time. Files, folders, components, all stored in the
0:4949 secondsConvex database and available instantly thanks to Convex's sync engine. No refresh, no polling. True realtime
0:5858 secondsreactivity. And here's the magic. Your app is already running. No local setup, no terminal commands. Web containers
1:061 minute, 6 secondsgive us a full NodeJS environment right in the browser. You can see install logs, developer server output, and your
1:151 minute, 15 secondslive app all in one place. The editor is built on code mirror 6 with full syntax highlighting, code folding, and a mini
1:251 minute, 25 secondsmap. But here's where it gets interesting. As you type, AI suggestions appear as ghost text. Just hit tab to
1:331 minute, 33 secondsaccept. It's contextaware, analyzing the code around your cursor to give you relevant completions. Now watch this.
1:411 minute, 41 secondsSelect any code, open quickedit, and paste a URL. Firecrol scrapes that page and feeds it directly to the AI.
1:511 minute, 51 secondsdocumentation for a library that launched last week, a GitHub readme, API references, anything on the web
1:581 minute, 58 secondsinstantly becomes context. The AI isn't limited to what it was trained on anymore. That's the power of Fire Crawl.
2:062 minutes, 6 secondsFor bigger changes, open the chat sidebar, ask it to add a feature, and watch it work. You'll see the thinking
2:132 minutes, 13 secondsindicator. Then the AI starts calling tools, creating files, modifying code, building out your request step by step.
2:232 minutes, 23 secondsIngest handles the background processing, managing the AI agent execution, retries if something fails,
2:312 minutes, 31 secondsand keeps everything reliable. GitHub integration is built in. You can import any repository. We use clerk's oalf to
2:402 minutes, 40 secondssecurely access your GitHub token. And when you're ready to ship, you can export directly to a new repository.
2:482 minutes, 48 secondsIngest runs these as background jobs, so large repositories import smoothly without blocking your UI. For
2:552 minutes, 55 secondsauthentication and payments, Clerk handles it all. Signup flows, OOTH providers, and now billing, free tier,
3:043 minutes, 4 secondspro plans, all managed in one place. In production, you need visibility. Sentry gives us error tracking and session
3:133 minutes, 13 secondsreplace to catch and debug issues. They also have a new AI monitoring feature.
3:203 minutes, 20 secondsEvery LLM call is logged with model token counts and cost per request.
3:263 minutes, 26 secondsUseful for keeping an eye on your AI spend. Throughout this tutorial, we're using Code Rabbit for AI powered pull
3:353 minutes, 35 secondsrequest reviews. Each chapter of our tutorial is a branch and each feature is a pull request. You'll learn the
3:433 minutes, 43 secondscomplete Git workflow alongside building this product. Let's go over the full text stack. Nex.js and TypeScript for
3:513 minutes, 51 secondsthe foundation. Convex for our database and realtime sync. Clerk for authentication and billing. Ingest
3:593 minutes, 59 secondspowering our AI agent and background jobs. Code mirror 6 for the editor. Web containers for in browser code
4:084 minutes, 8 secondsexecution, firecrol for URL scraping, Sentry for error tracking and AI monitoring, and Code Rabbit for our GitHub pull request review workflow.
4:204 minutes, 20 secondsThis isn't just a coding tutorial. This is a complete playbook for building AI powered developer tools. And now without
4:294 minutes, 29 secondsfurther ado, let's get started. Before we dive in, using the link on the screen, you can get 3 months of Sentry
4:384 minutes, 38 secondsteam completely for free. We'll be using their AI monitoring to track all our LLM
4:454 minutes, 45 secondscalls throughout this build. If that sounds useful for your project, feel free to grab the deal. And now, let's
Chapter 2: 01 Project Setup
4:534 minutes, 53 secondsbuild. In this chapter, we're going to learn how to set up the project. We're going to initialize Nex.js JS with
5:005 minutesTypeScript. Install and configure Shatsen components. Add a theme provider and configure the fonts and global CSS variables.
5:105 minutes, 10 secondsLet's start by initializing Nex.js.
5:135 minutes, 13 secondsHere on the right side, I have my code editor Visual Studio Code. And here on the left side, I have opened Nex.js
5:205 minutes, 20 secondsdocumentation page, which you can visit by using the link on the screen. Click on get started. Click on the installation tab and scroll down to find
5:295 minutes, 29 secondsthe system requirements. It's very important that you make sure that you meet these requirements. Otherwise, you will have problems running NextJS.
5:385 minutes, 38 secondsSo, the minimum node version is 20.9 and the supported operating systems are Mac OS, Windows, and Linux.
5:465 minutes, 46 secondsIf you don't know your Node version, go inside of your terminal and run node-v.
5:525 minutes, 52 secondsIf you get an error, it's time to install node. If you have a version lower than 20.9, it's time to upgrade.
6:006 minutesEither way, make sure you do that and then run this command again and make sure you have a higher version this time
6:066 minutes, 6 secondsand no errors. While you are here, also check for npx and npm. The version here
6:146 minutes, 14 secondsisn't as important because different operating systems have different versions. So, you don't need to have the same version as me. And I don't really
6:226 minutes, 22 secondsknow what version is the most upto-date either. Just make sure you don't have errors for any of these three commands.
6:316 minutes, 31 secondsNow, let's go ahead and let's install.
6:336 minutes, 33 secondsMake sure you select npm since that's going to be our package manager. And I'm just going to prepare the command. I'm not going to run it just yet. So, as you
6:416 minutes, 41 secondscan see, that's why I told you to test for npx because we are using it right this moment. So, I'm going to
6:486 minutes, 48 secondsspecifically choose a version 16.1.1 instead of just using the latest. And if
6:546 minutes, 54 secondsyou haven't noticed, that is actually my latest version. So, why am I telling you to use that? Well, the reason I'm
7:027 minutes, 2 secondstelling you to do that is so you don't have a hard time following this tutorial. Depending on when you found this video, that can be a month from
7:107 minutes, 10 secondsnow, 6 months from now, maybe even a year from now. And during that time period, a lot of breaking changes could
7:187 minutes, 18 secondshave arrived in the newest version of NextJS.
7:227 minutes, 22 secondsThat isn't to say that you shouldn't upgrade. You should upgrade, but I recommend doing that after you finish
7:297 minutes, 29 secondsthe tutorial. This way, you will not have any trouble following along the way, and you will be able to give
7:367 minutes, 36 secondsyourself a challenge to finish your on your own after you complete the tutorial. So, it's not a bad thing that
7:457 minutes, 45 secondsbreaking changes arrive in Nex.js. Uh, a lot of times Nex.js takes care of backwards compatibility and if that's
7:537 minutes, 53 secondsnot possible, they offer migration scripts. So, that's perfectly fine and you should be up to date in case of any
8:018 minutes, 1 secondsecurity issues or things like that. But just to make it easier for you to follow along and not encounter any breaking
8:088 minutes, 8 secondschanges and avoid any frustrations, I recommend using the exact same version as me. So we are on the same page and we
8:178 minutes, 17 secondshave the exact same code. So let's go ahead and run this command and let's give our project a name. I'm going to choose Polaris.
8:248 minutes, 24 secondsI'm going to use the arrow keys and select customize settings. I will select yes for typescript slint for the
8:338 minutes, 33 secondsllinter. I will leave it as no for react compiler, yes for tailwind. Make sure
8:408 minutes, 40 secondsyou select yes for source directory, yes for app router, and select no for
8:478 minutes, 47 secondscustomizing the import alias and give it a minute to install.
8:528 minutes, 52 secondsOnce it's finished, you're going to see a success message like this. So what you have to do now is first change the
9:009 minutesdirectory of your terminal into your newest project and then do the same thing in your code editor.
9:089 minutes, 8 secondsSo I'm going to go ahead and open folder and I'm going to select the one we just installed Polaris.
9:169 minutes, 16 secondsSo now let's go ahead and let's review the file structure package JSON and things like that.
9:239 minutes, 23 secondsAs you can see, this newest Visual Studio Code's AI feature is a little bit buggy, which is ironic considering that
9:309 minutes, 30 secondsin this tutorial, we're building our own code editor, which will not be buggy.
9:369 minutes, 36 secondsSo, let's go ahead and take a look at the folder structure. Since we selected yes for the source folder, we can obviously see the source folder here.
9:479 minutes, 47 secondsAnd inside of that, we have an app folder because we selected yes for the app router. It is very important that you have the exact same file structure
9:549 minutes, 54 secondsas me. And let's go ahead and confirm the package JSON. Since I initialized the command with npx uh create next app
10:0410 minutes, 4 seconds16.1.1 that is the exact next version that I have in my dependencies and you should have too. And besides that, React 19.2.3
10:1410 minutes, 14 seconds2.3 is I believe pinned to this version as well because of this option we selected. So you should probably have
10:2310 minutes, 23 secondsthe exact same dependencies as me for the dev dependencies. They are probably the same as well. Great. Now let's go
10:3110 minutes, 31 secondsahead and let's run the project to see what's on our screen.
10:3710 minutes, 37 secondsSo open localhost 3000. I'm going to zoom out. And here we have the default
10:4310 minutes, 43 secondslanding page. So I believe that depending on whether you use light or dark mode, this can change as you can
10:5210 minutes, 52 secondssee. So if you have a light background, that's perfectly fine. So how do you modify this file? Well, very simply go inside of source app page.tsx.
11:0411 minutes, 4 secondsThe only thing that's important to know for now is that page is a reserved file name. So you cannot name it whatever you
11:1111 minutes, 11 secondswant. It needs to be page. And second important thing is that whatever you write here. So let's do a simple
11:1811 minutes, 18 secondscomponent right const page. This doesn't matter I mean the name of the component. It can be called whatever you want.
11:2711 minutes, 27 secondsSo if you do something like this, it obviously won't work. it will throw an error. Even if you do this, it also
11:3711 minutes, 37 secondswon't work. It needs to be a default export and then it will work. So for
11:4511 minutes, 45 secondsnow, that's the only important thing for you to know. Page is a reserved file name and export default is the required
11:5411 minutes, 54 secondsway of exporting within page.dsx.
12:0012 minutesGreat. So now let's go ahead and test if Tailwind is working. So I'm going to give this text red 500 and it changes to
12:0912 minutes, 9 secondsred. Perfect. Make sure you save the file and then it will change. A lot of people forgot to save the file and then
12:1612 minutes, 16 secondsthey think the Tailwind is not configured. It is. You just have to save the file. Great. Now you have probably
12:2312 minutes, 23 secondsnoticed that I have this little red color indicator and that I also have these autocompletes which actually are
12:3212 minutes, 32 secondscompletely valid Tailwind classes. And when I hover over I can see the underlying CSS.
12:3812 minutes, 38 secondsIf you want the same thing I highly highly recommend installing Tailwind CSS in extension.
12:4712 minutes, 47 secondsThere we go. Tailwind CSS IntelliSense.
12:5012 minutes, 50 secondsI recommend this at the start of all of my tutorials. It is an amazing extension which will help you understand Tailwind much better and make fewer mistakes.
13:0113 minutes, 1 secondGreat. So now that we have this, let's go ahead and do the second thing.
13:0513 minutes, 5 secondsInstall and configure Chats UI components. So for now, you can shut down your app and let's head to ui.shhatsen.com.
13:1613 minutes, 16 secondsYou can use the link on the screen to visit their landing page. Let's go ahead and click on the menu documentation.
13:2513 minutes, 25 secondsAnd by default, they select the installation tab, but you can find it here as well. Pick your framework. For
13:3213 minutes, 32 secondsus, that's next.js. Select npm and npx chats latest. Don't run the command just yet.
13:4013 minutes, 40 secondsWhat I'm going to do first is I'm going to use d- version to check what is the latest version. So for me it is 3.6.2.
13:5013 minutes, 50 secondsSo that's why I will be telling you to use that version.
13:5413 minutes, 54 secondsAgain you can upgrade later when you finish the project. But in order to avoid any headaches and to avoid having
14:0314 minutes, 3 secondsdifferent components, different props, I recommend using the exact same version as me, 3.6.2.
14:1014 minutes, 10 secondsSo, make sure you are running this command within your project. You should have some kind of indicator that you're within the Polaris folder and run npx
14:1814 minutes, 18 secondschaten 3.6.2 in it. This will automatically recognize the framework as well as the tailwind.
14:2614 minutes, 26 secondsAnd then go ahead and just select the base color. I will be using neutral and give it a second to install. There we
14:3314 minutes, 33 secondsgo. So, right now, not much should change besides the folder structure. I suppose we have a couple of new files.
14:4214 minutes, 42 secondsOne of them is components.json, which is basically just a config file of the things we selected a moment ago,
14:5014 minutes, 50 secondsright? For example, uh our base color, we selected neutral. Uh we didn't select this, but it automatically found that,
14:5914 minutes, 59 secondsright? So that's what this file is about. You will never have to modify it yourself really. And inside of source,
15:0515 minutes, 5 secondswe now have a lib folder with utils.d DS inside. This is doesn't seem like a very descriptive function, but it will
15:1315 minutes, 13 secondsactually be one of the most used functions in this project. It will be used to safely merge or create
15:2015 minutes, 20 secondsconditional Tailwind classes, which seems like a simple task, but if you're not careful and don't understand how Tailwind functions, you can accidentally
15:2915 minutes, 29 secondsoverride yourself or create something you didn't intend to do. This simple util right here makes sure that never
15:3615 minutes, 36 secondshappens. and it has a very nice developer experience on top of all that.
15:4115 minutes, 41 secondsThat's all you have to know for now. We don't have to do anything about it. So now let's go ahead and let's add some components. Right? Because we just added
15:5015 minutes, 50 secondschaten. We can see that the definition of it on their page is the foundation for your design system. But we are not
15:5715 minutes, 57 secondsseeing any components. So let's add all of them.
16:0216 minutes, 2 secondsSo npxhatzen 3.6.2 to add d-all and this will add every single component
16:0916 minutes, 9 secondsfrom shatzen to your project and when it's finished you're going to see a message like this basically an
16:1716 minutes, 17 secondsoutput of all the components that were installed besides that chaten command also modified our globals css file which
16:2616 minutes, 26 secondswe're going to take a peek at right now but let's first take a look at all of these files what are these files Well,
16:3516 minutes, 35 secondsShhatzen works differently from other component libraries primarily because it isn't a component library. It's a
16:4216 minutes, 42 secondscollection of beautifully designed components that you can use to create your own component library. So, what do
16:4916 minutes, 49 secondsthey mean by that? Well, if you open source components UI, you will see all of those components which you can guess
16:5716 minutes, 57 secondswhat they are looking at their names, right? But what's cool is by clicking on any of those you can actually access and
17:0317 minutes, 3 secondsmodify their source code. So that is something you usually are not able to do. And that's what they mean by not a
17:1217 minutes, 12 secondscomponent library but a set of beautifully designed components, right?
17:1717 minutes, 17 secondsA composition of primitives that allow us to modify them and create our own design system, our own brand guidelines,
17:2617 minutes, 26 secondsright? They just give us highquality primitives. So we don't have to build them from scratch and on top of that they are very goodlooking from scratch.
17:3517 minutes, 35 secondsSo even if you don't modify them, they look very nice, but they are used to be they are intended to be modified, right?
17:4317 minutes, 43 secondsThat's why a lot of times people say all Shatsian projects look the same. That makes no sense. That's like saying all
17:5117 minutes, 51 secondsCSS projects look the same. Well, yeah, if you don't modify the CSS, right? So that's how Shatsen is supposed to be
17:5817 minutes, 58 secondsused. So let's try it out. Let's go inside of app folder page.tsx.
18:0418 minutes, 4 secondsLet's remove this class name here. And let's render a button from components UI button.
18:1318 minutes, 13 secondsAnd I'm going to add click me here. Make sure to save the file and do npm rundev.
18:2018 minutes, 20 secondsSo I'm going to go ahead inside of my local host. And the first thing you're going to notice is that your theme has
18:2718 minutes, 27 secondschanged. So regardless if you are on light or dark mode, the background is now in light mode. So that's perfectly normal. Don't worry.
18:3818 minutes, 38 secondsAnd here we have our button, which simply says click me. So what's cool about this is that this button, for example, has variants.
18:4818 minutes, 48 secondsLet's select a variant destructive and save. And what happens is it changes the color red. And what you can do is you
18:5618 minutes, 56 secondscan commandclick inside of the button or find it inside of source components UI button and scroll up to find the button variants.
19:0619 minutes, 6 secondsAnd inside of this variant object, go ahead and write your own. For example, purple and give it a background of
19:1419 minutes, 14 secondspurple 500 and text of white. And make sure to put a comma at the end. Then save the file. Go back to page. Change the variant here to purple.
19:2419 minutes, 24 secondsAnd guess what? You just modified the source code of the button and added your very own variant. That is what they mean
19:3219 minutes, 32 secondsby customizable, right? Usually when you use a component library, you don't even see the code of the button. You just
19:3919 minutes, 39 secondsimport it and the source code is in node modules, but you are not intended to look at it, nor are you intended to
19:4719 minutes, 47 secondsmodify it. That's the difference. And this is actually a very good way to learn about how to create highquality components. You can always take a peek
19:5619 minutes, 56 secondsfrom the pros. So from now I'm going to remove this purple variant and just revert it back to how it was. Great.
20:0420 minutes, 4 secondsSo one thing that's bothering me now is that my project is in light mode and most code editors are in dark mode by
20:1420 minutes, 14 secondsdefault. Case in point right here, right? So, how do we hardcode our project to dark mode? Well, if you take
20:2320 minutes, 23 secondsa look at Shatenne and inside of its documentation here, you can find something called dark mode. So, let's take a look. Let's click on dark mode
20:3120 minutes, 31 secondsand let's click on next.js. Even if you can't find this documentation, don't worry. It's very simple to do. You can just follow my steps. So, first things first, let's install Next Themes.
20:4420 minutes, 44 secondsSo I'm going to go ahead and do npm install next themes and I'm going to show you the exact version that I have
20:5220 minutes, 52 secondsinstalled in my project even though I don't think it really matters. This is not really a breaking thing. So my version is 0.4.6.
21:0221 minutes, 2 secondsSo if you want to use the exact same you can. 0.4.6.
21:0921 minutes, 9 secondsGreat. Once you have next themes installed, you can create your own component. So let's go inside of source
21:1821 minutes, 18 secondscomponents new file theme-provider.tsx.
21:2421 minutes, 24 secondsThe reason I didn't put it inside of the UI folder is because I want to keep that reserved for chats and components.
21:3121 minutes, 31 secondsBasically components I didn't create.
21:3321 minutes, 33 secondsThis way, it's easier for me to keep track of things I have to take care of versus things I only have to, I don't
21:4121 minutes, 41 secondsknow, upgrade, right? Kind of a mental separation, at least for me. So, open the theme provider here, and we're just
21:5021 minutes, 50 secondsgoing to copy this code. Again, don't worry if you can't find it. I'm going to pause the screen so you can copy. We add
21:5821 minutes, 58 secondsthe use client directive which turns this into a client component because by default uh components are server
22:0422 minutes, 4 secondscomponents in app router and we import react. We use our new import next themes
22:1222 minutes, 12 secondsand we export a component called theme provider which very simply pro um propagates the props and renders the
22:2022 minutes, 20 secondschildren as its well children. Great. So once you have the theme provider, let's
22:2822 minutes, 28 secondsgo ahead and go inside of source app folder and find layout. So same rule as in page. Layout is a reserved file name.
22:3922 minutes, 39 secondsAnd inside of it, you will find a couple of weird things. This random export of
22:4622 minutes, 46 secondsmetadata and then this random export of root layout. So this can be thought of
22:5422 minutes, 54 secondsthe same as the default export that is required in page right we need at least one default export and that's what kind
23:0123 minutes, 1 secondof registers the layout or registers the page that's how filebased routing works.
23:1023 minutes, 10 secondsSo basically for now just go inside of this root layout and go inside of HTML
23:1623 minutes, 16 secondsbody and simply add theme provider from components theme provider. Make sure you're using the one you just created.
23:2623 minutes, 26 secondsSo theme provider from components theme provider. When it comes to imports, I like to have a specific sorting
23:3323 minutes, 33 secondsorganization. I like to keep the npm ones at the top followed by aliased ones and then these ones at the bottom. You
23:4223 minutes, 42 secondsdon't have to follow me, but I really like it this way.
23:4723 minutes, 47 secondsAnd once you do this, I think just by adding this, you might actually get some errors. There we go. Yes, you can see
23:5423 minutes, 54 secondsthat we have some errors here. That's perfectly fine. And in fact, the next step here tells you how to fix that. we
24:0224 minutes, 2 secondshave to add suppress hydration warning prop to the HTML tag. So I'm just going to add that here. There we go. And now
24:1124 minutes, 11 secondswhat I want to do is I want to change this theme provider to default to dark
24:1724 minutes, 17 secondsmode. So attribute will be class, default theme will be dark. I'm going to
24:2624 minutes, 26 secondschoose enable system and disable transition on change.
24:3124 minutes, 31 secondsAnd now when you refresh your app, you will see we have switched back to dark mode. So even if I change this to light
24:4124 minutes, 41 secondsmode, you can see that my browser has changed to light mode. the app stays in dark mode which is exactly what we
24:4724 minutes, 47 secondswanted to achieve because most idees are in dark mode by default. Of course
24:5624 minutes, 56 secondslater on you can add light mode that's why I did it using the theme provider and not directly by modifying the global
25:0525 minutes, 5 secondsCSS in a way that just removes the light mode. So if you ever want to develop light mode later on, you will be able to do that and you will be able to change
25:1325 minutes, 13 secondsthis to light. But for now, let's do it in dark mode.
25:2125 minutes, 21 secondsNow, while we are inside of this layout file, I also want to modify the font.
25:2725 minutes, 27 secondsSo, we're going to have two fonts. One will be our Sans and one will be our mono. So instead of uh gist or gase suns
25:3625 minutes, 36 secondsI'm not sure how to pronounce it I'm going to be using inter we can import that from next font google
25:4525 minutes, 45 secondsand instead of ge mono I'm going to do IBM plex mono so change this to plex mono let's change
25:5525 minutes, 55 secondsthe variable of both of them this one to be font enter and this one to be font plex mono
26:0426 minutes, 4 secondsAnd besides the subsets, the mono one also needs the weight. So make sure to add these.
26:1226 minutes, 12 secondsNow let's go ahead and add the inter variable and plex mono variable.
26:2126 minutes, 21 secondsSo if you have a good eye, you might have noticed the change. If not, perfectly fine. We don't really have a lot of content right now to display
26:2826 minutes, 28 secondsthese new fonts. But uh why not do it while we are already here. But there is one slight problem. Uh this font didn't
26:3626 minutes, 36 secondseven load actually. And that is because if you take a look at globals.css instead of source app, you will find
26:4326 minutes, 43 secondsthat font sans has defaulted to font sans whereas we have changed it to font
26:5226 minutes, 52 secondsenter. So only when you save this and refresh will it actually modify. But that's not how we're going to change
27:0027 minutesthis global CSS. Instead I have prepared a link which you can see on the screen
27:0727 minutes, 7 secondsand using that link you can access Polaris assets GitHub repository. And in here you can find my globals.css.
27:1727 minutes, 17 secondsSo you can see that here at the bottom I have even added some very specific CSS which we are going to need later. I will
27:2427 minutes, 24 secondstry my best to uh remind myself about this and explain why I have added this but I don't think it makes sense to you
27:3227 minutes, 32 secondsknow do this any other way than to copy and paste. It's not a lot of learning material to write each line of globals
27:4027 minutes, 40 secondsCSS. I basically just changed the way and look until I liked how it looked. So that's why I'm telling you to copy it,
27:4827 minutes, 48 secondsright? I'm not trying to uh teach you anything less. So just go ahead and remove your existing globals.css and paste the new one inside.
28:0028 minutesAnd what this will do is it will create a slight modification. As you can see, we are no longer using that uh black
28:0828 minutes, 8 secondsbackground. Instead, we are using this lighter one. And this will actually look very well once we have all the elements
28:1728 minutes, 17 secondsof the IDE like the code editor and the file explorer and all the other things.
28:2428 minutes, 24 secondsGreat. So, what I want to do now is I want to push this changes to a GitHub repository so that we can start tracking
28:3228 minutes, 32 secondseach of our features and chapters in a branch.
28:3828 minutes, 38 secondsSo, in order to add this project to a new GitHub repository, we first have to create one. Make sure you have a GitHub
28:4528 minutes, 45 secondsaccount. And once you do, click on the plus button and click on uh new repository right here. One thing I'm
28:5428 minutes, 54 secondsgoing to change that you don't have to change is the owner. So, I'm using my organization code with Antonio. You don't have to change this. It really
29:0229 minutes, 2 secondsdoesn't matter. So, I'm going to go ahead and call this Polaris.
29:0729 minutes, 7 secondsAnd for now, I'm going to keep this private. And I don't recommend adding any of these because we have all of them right here. So just create a repository.
29:1729 minutes, 17 secondsGreat. So now we have two options here.
29:2029 minutes, 20 secondsCreate a new repository or push an existing repository. This is our case.
29:2529 minutes, 25 secondsWe already have a repository. It's just local. So we are going to use these three commands right here. So let's copy these three commands right here.
29:3629 minutes, 36 secondsLet's go ahead and shut down our app. And let's do the following.
29:4229 minutes, 42 secondsInside of here, do get add get commit.
29:4729 minutes, 47 secondsAnd let's go ahead and call this 01. And I'm going to call this setup, right? The
29:5529 minutes, 55 secondssame as we called it here. So, let me just be specific. Project setup.
30:0330 minutes, 3 secondsAnd then once we've done that, you will also see a change here. So of course you can use the visual editor here or you
30:1030 minutes, 10 secondscan use the command line. Uh I kind of prefer the command line, but a lot of you find it easier to use this. That's also perfectly fine. But for this first
30:2030 minutes, 20 secondsattempt, I recommend doing the same thing I'm doing. So I did get add and then a dot which basically staged all of
30:2730 minutes, 27 secondsmy changes which was as you can see 62 new files because we added a lot of new components and then I committed with a
30:3630 minutes, 36 secondsmessage all of those staged files and then what I'm going to do is I'm going to paste those three commands which we
30:4430 minutes, 44 secondshave copied from here. Git remote, git branch and git push.
30:5130 minutes, 51 secondsGo ahead and enter that.
30:5430 minutes, 54 secondsAnd there we go. You can go back here and refresh. And you now have your newest project right here ready. What
31:0331 minutes, 3 secondsthis will allow us to do is use a branches. So then in the next chapter when we commit that, we're going to push
31:1131 minutes, 11 secondsthat to a separate branch. And then you will have a very nice overview of all of your changes and all of your progress.
31:1731 minutes, 17 secondsAnd if you ever wonder what was your state in uh in I don't know chapter five, you will simply find chapter five
31:2431 minutes, 24 secondshere and you will able to go back to that state of the project if you want to learn in that specific way. I think it's a very useful thing to do because you also learn the proper git workflow.
31:3531 minutes, 35 secondsGreat. So one thing uh which you can always do is you can use this synchronize changes and then you can
31:4331 minutes, 43 secondsclick okay. What this will do is this will basically push and pull from your remote branch. What is a remote branch?
31:5231 minutes, 52 secondsThis right what is on the internet on GitHub is remote and what's on your laptop on your machine is local. And
32:0132 minutes, 1 secondthis is a button which synchronizes the remote one with the local one. Great. So amazing amazing job for the first
32:0832 minutes, 8 secondschapter. You did all of this. You initialized Nex.js JS with TypeScript.
32:1432 minutes, 14 secondsYou initialized Chaten and all of its components. You added a theme provider and changed the default to dark mode.
32:2132 minutes, 21 secondsAnd finally configured fonts and global CSS variables. And on top of all of that, you've set up a new GitHub
32:2832 minutes, 28 secondsrepository. Amazing job. And see you in the next chapter.
Chapter 3: 02 Authentication
32:3332 minutes, 33 secondsIn this chapter, we're going to add authentication to our project. We're going to set up Clerk account and SDK.
32:4132 minutes, 41 secondsconfigure authentication provider and middleware, create signin and signup flows, and then test it all out by building authenticated and
32:4932 minutes, 49 secondsunauthenticated views. No need to have your app running at the moment because we're going to visit Clerk's page using the link you can see on the screen. Go
32:5832 minutes, 58 secondsahead and create an account and visit the dashboard. In the dashboard, you will have a list of your previous projects or a button to create your very
33:0733 minutes, 7 secondsfirst application, which is what we are going to do. Let's click on create application. I'm going to give my application a name, Polaris. And for the
33:1633 minutes, 16 secondssign-in options, make sure you have email turned on. This is because clerk billing needs this sign-in option to
33:2433 minutes, 24 secondswork. As for the other providers, it really doesn't matter. You can add as many of them as you prefer, but one that is very important to enable is GitHub.
33:3433 minutes, 34 secondsThis is because GitHub O token will allow us to later import users repositories even private ones as well
33:4133 minutes, 41 secondsas create new repositories on their behalf which is a crucial feature of our editor. So for simplicity sake I'm just
33:5033 minutes, 50 secondsgoing to enable GitHub. You can of course add as many of them as you want later but make sure you have email and GitHub as those are the important ones.
34:0134 minutes, 1 secondand let's click create application.
34:0434 minutes, 4 secondsNow let's go ahead and let's run the following terminal command so that we can install clerk.
34:1134 minutes, 11 secondsI'm going to go ahead and paste this and then I'm going to show you what version was installed.
34:1834 minutes, 18 secondsThere we go. Let's go ahead and check the package JSON so you can see exactly what package I have you been using.
34:2734 minutes, 27 secondsThere we go. Clerk 6.36.5.
34:3134 minutes, 31 secondsSo for those of you who want to use the exact same version, you can install it like this. Great.
34:4034 minutes, 40 secondsNow let's go ahead and follow the instructions. So we've just added the package and now we have to set up clerk
34:4734 minutes, 47 secondsAPI keys. Add these keys to your environment file. Let's go ahead and copy these and let's create our
34:5534 minutes, 55 secondsenvironment file. So in the root of our app right here, I'm going to create a new file dot environment. Here it is.
35:0335 minutes, 3 secondsAnd I'm just going to paste this here.
35:0535 minutes, 5 secondsSo we now have next public clerk publishable key and clerk secret key. It goes without saying that you shouldn't share this with anyone. Since I'm making
35:1335 minutes, 13 secondsa tutorial, I'm sharing them, but obviously I will remove them later. I like to add comments to my environment
35:2135 minutes, 21 secondsso I know exactly what keys refer to which service.
35:2535 minutes, 25 secondsGreat. Step two finished. Let's see what else we have to do. We now have to create what was previously called a
35:3335 minutes, 33 secondsmiddleware. You can see they even have a note about that here. So if you're using Nex.js lower than 15, name of your file
35:4035 minutes, 40 secondsis middleware. So since we're using next 16, we are using a new name proxy, which is honestly a good thing they've changed
35:4835 minutes, 48 secondsbecause middleware was just confusing people because it doesn't actually work as a normal middleware. So depending on whether you have the source folder or
35:5635 minutes, 56 secondsnot, your middleware file actually goes in a different place. Uh let me see if they actually tell you that here. They
36:0336 minutes, 3 secondsdo. So you either create one at the root of your project or inside the source directory if you're using that. Since we
36:1036 minutes, 10 secondsdo, let's go inside of source. Create a new file middleware.ts. My apologies. All have it proxy. DS.
36:1936 minutes, 19 secondsEven though middleware would still work, it will throw a deprecation warning in the terminal.
36:2536 minutes, 25 secondsSo let's go ahead and copy this code from here and paste it inside of here.
36:3136 minutes, 31 secondsSo it kind of makes no sense for us to write this. That's why we are copying and pasting. If you want to, you can pause the screen and then write it on
36:3936 minutes, 39 secondsyour own, but it's just a big uh rugx rule which covers a bunch of things.
36:4636 minutes, 46 secondsGreat. And now let's go ahead and let's add a clerk provider. So you can see they are instructing us to add some code to the layout file which we are already
36:5436 minutes, 54 secondsfamiliar with at this point. So let's revisit it. Source app folder layout.dsx.
37:0137 minutes, 1 secondAnd in here let's go ahead and well let's import all of these. So clerk provider signin button sign up button
37:0937 minutes, 9 secondssigned in signed out as well as the user button. I'm just going to add all of them here. There we go. No errors because we have all the packages
37:1737 minutes, 17 secondsinstalled. Great. So, let's see what else do we have to do. We have to wrap our entire app with a clerk provider.
37:2537 minutes, 25 secondsSo, I'm going to go ahead and do that right here. And let me indent the rest.
37:3337 minutes, 33 secondsAnd now I'm going to go ahead and go inside of the theme provider and I will create a signed out view. And inside of
37:4137 minutes, 41 secondssigned out, I will add a sign in button, which will be a self-closing tab. So all users who are signed out are going to see a button to sign in.
37:5337 minutes, 53 secondsAnd let's add sign up button here as well. Let me go ahead and move this here.
38:0238 minutes, 2 secondsObviously, if you want to, you can just copy it from here. But I'm writing, you know, along just so we kind of learn how to compose clerk components.
38:1338 minutes, 13 secondsAnd no need to do the whole class name thing. I think they're just trying to demonstrate how you can modify the look
38:2038 minutes, 20 secondsof the sign up button. So in here, I'm just going to give it a background rose 500 and the text of white. So we have eight points, maybe some padding rounded and u I don't know. That's it.
38:3438 minutes, 34 secondsAnd for the signed in view, let's just render a user button which
38:4138 minutes, 41 secondswill allow us to well sign out. Uh, great. Yeah. And we can we can kind of keep all of that within a header. So, it's kind of like a nbar.
38:5238 minutes, 52 secondsThere we go.
38:5838 minutes, 58 secondsLet's go ahead and do npm rundev. And we should be able to access our app at localhost 3000. And I think at this point it should already be working.
39:0839 minutes, 8 secondsYeah, there we go. So I'm zoomed in a lot, but basically you can see that above my click me button, which is inside of my
39:1639 minutes, 16 secondspage.tsx, I now have a sign in and sign up buttons. both of them will actually do
39:2339 minutes, 23 secondsthe same thing right now because I have no accounts. So, as you can see, we are redirected to another page with our
39:3039 minutes, 30 secondssignin box. And in here, I can use GitHub to create an account. So, I'm going to go ahead and do that. Let me authorize clerk.
39:3939 minutes, 39 secondsAnd I will be redirected back to my local host app. There we go. And you can see that now right here, I have my
39:4739 minutes, 47 secondsaccount. And when you click on this button right here, you can click manage account and you can see a bunch of info about your account. We are going to
39:5539 minutes, 55 secondsexplore this later, especially when it comes to billing. The only reason I'm not clicking it right now is because it's going to show my email address. Uh
40:0340 minutes, 3 secondsbut feel free to explore the manage account settings. And you can also sign out from here as well. And that will lead you back to the unauthorized state.
40:1240 minutes, 12 secondsPerfect. So this is how easy it was to add authentication using clerk. Obviously, it goes even more than this.
40:2140 minutes, 21 secondsUh, but it doesn't make sense to explore this any further before we add convex, which will be our database provider, our
40:2940 minutes, 29 secondssync engine, our real-time database, basically our backend. And once we add that, we're going to have to incorporate
40:3840 minutes, 38 secondsthat with Clerk. So I want to wait until we do that so that we can in a smarter
40:4540 minutes, 45 secondsway create components that will combine both and work nicely together rather than building something now and then
40:5340 minutes, 53 secondshaving to change it all together. But it goes without saying uh you can control how your user sees when they are signed
41:0241 minutes, 2 secondsin and when they are signed out in many different ways and one of them is by using composition components like signed
41:1041 minutes, 10 secondsin or signed out but obviously you will be able to do that also using the middleware or what's called proxy now
41:1841 minutes, 18 secondsright uh what I suggest you do is you follow the guide and there we go okay so my email is shown here now which is what
41:2641 minutes, 26 secondsI was trying to avoid but okay not a problem u what I would suggest you do now after you do this is visit the
41:3541 minutes, 35 secondsdocumentation in fact we're going to do it together so I can show you a bit how all of that looks like so you can click on any of these actually and they will
41:4341 minutes, 43 secondslead you to the documentation for example add security and in here you'll be redirected to NexJS SDK here and you
41:5141 minutes, 51 secondscan read all about this right but if you want to get familiar here with their components. For example, uh you can do
41:5841 minutes, 58 secondsthat as well. Uh let's go ahead and scroll a bit up. We have user management here,
42:0742 minutes, 7 secondsUI components. There we go. So, we have the clerk provider, which is what we've just added, right? And in here, we can see all the props that clerk provider
42:1442 minutes, 14 secondshas. And for example, one of the props that we are going to use is going to be
42:2142 minutes, 21 secondsuh the theme. So that's something you can figure out if you go through the props, right? So let's actually try it out. Let's go inside of layout here.
42:3342 minutes, 33 secondsMy apologies. It's not called the theme.
42:3542 minutes, 35 secondsIt's called appearance, right? So appearance prop and go ahead and add a base theme here.
42:4242 minutes, 42 secondsActually, let's call let's do theme as base theme is deprecated. And [snorts] in here we can use the dark theme. Keep
42:5042 minutes, 50 secondsin mind that now we have to install that. So, let's go ahead and do that.
42:5442 minutes, 54 secondsSo, we're going to have to add a small package here.
42:5842 minutes, 58 secondsMPM install clerk/ themes.
43:0343 minutes, 3 secondsAs always, I'm going to go ahead inside of my package.json clerk themes 2.4.46.
43:1043 minutes, 10 secondsSo, if you want to, you can use that specific version like this.
43:1543 minutes, 15 secondsNow that we have clerk themes, we can import dark from that package.
43:2343 minutes, 23 secondsLet's do dark from at clerk themes. There we go.
43:3243 minutes, 32 secondsAnd now the clerk provider will match all of its UI components according to
43:3943 minutes, 39 secondsthe theme we have given it which is exactly what we want because we have kind of defaulted our app to dark
43:4643 minutes, 46 secondsmode if you remember. And now you can see how it opens in dark mode. So basically that's the kind of thing you can learn if you go through their
43:5443 minutes, 54 secondsdocumentation and figure out all the things that they have. Here it is appearance which accepts the theme and then you will get to the themes here and
44:0344 minutes, 3 secondsthis is what we just did. We added clerk themes right. So obviously I've been using clerk for a lot for a long time.
44:0944 minutes, 9 secondsSo I do all of this you know at the top of my mind but uh this is how I learned that right? I went through the documentation and I learned how clerk
44:1844 minutes, 18 secondsworks. We're going to go back to this documentation later whenever we need to explain something. I think it's a very very well-ritten documentation. That's
44:2544 minutes, 25 secondswhy I'm pushing it so much for you to visit it because uh it's a shame if you don't do it. Usually documentations are
44:3244 minutes, 32 secondsnot very you know easy to read but clerks is very very well done and I would recommend that you do that. You
44:3944 minutes, 39 secondsknow just kind of get familiar what is clerk middleware? How does it work with the app router? What is this out helper?
44:4644 minutes, 46 secondsRight? How does that work? And you will actually find some useful examples about how you can authenticate your page and maybe you can even play around with it.
44:5444 minutes, 54 secondsUh we will explore most of this simply by building the project anyway. But if you want to do it on your own, I highly
45:0145 minutes, 1 secondrecommend that. That's always a good way to learn something. Uh excellent. Other than that, uh I believe we did what we
45:0945 minutes, 9 secondswanted in this chapter. So we have set up clerk account and SDK. We have configured the authentication provider
45:1745 minutes, 17 secondsand the middleware. We've created signin and signup flows. And we also build authenticated and unauthenticated views
45:2445 minutes, 24 secondsusing their composition components. So in the next chapter, we're going to join this with convex to make it even more powerful. So for now, let's go ahead and
45:3345 minutes, 33 secondsdo what we usually do and that is commit this and create a new branch.
45:3845 minutes, 38 secondsSo I'm just going to go ahead and close everything here. As you can see, I have four files changed. package JSON
45:4645 minutes, 46 secondspackage lock proxy file and layout where I added all of the clerk stuff. So I'm going to go ahead and do get add dot
45:5545 minutes, 55 secondswhich will add all of them. You can see four files have been staged. Then I'm going to do get commit
46:0246 minutes, 2 secondslike this. And now what I'm going to do is going to be a slight change. I'm going to create a new branch. So, get
46:1046 minutes, 10 secondscheckout-b and I'm going to call this 02 authentication.
46:1646 minutes, 16 secondsAnd you can see I have a message now switched to a new branch. Right. And now that I'm here, I'm going to do get push u origin 02 authentication.
46:2746 minutes, 27 secondsWhoops. It is not with a slash. It is just origin and then the name of the branch which in our case is 02 authentication.
46:3746 minutes, 37 secondsThere we go.
46:3946 minutes, 39 secondsAnd you will see that the same thing is happening here in the visual editor. So down here you can see I am on 02 authentication.
46:4746 minutes, 47 secondsSo now let's go ahead and go to our GitHub and you will now see that once we pushed this new branch we have this
46:5546 minutes, 55 secondsprompt 02 authentication had recent pushes 26 seconds ago. In case you are not getting this notification, you can
47:0447 minutes, 4 secondsalways manually go instead of pull requests here and create it. But just confirm that you actually have that new
47:1147 minutes, 11 secondsbranch here because we just push that branch to remote. So it should be visible right here. So I'm going to go ahead and this time just created
47:1947 minutes, 19 secondsmanually. I'm going to go instead of pull request and I will click new pull request. So base is main and we are comparing that to our new branch. There
47:2847 minutes, 28 secondswe go. So we only have one commit here which I have conveniently named exactly the same as our branch. So we know that's the one. So I'm going to go ahead
47:3647 minutes, 36 secondsand click create pull request and then I'm just going to create the pull request. And now we are going to review our changes.
47:4647 minutes, 46 secondsAs you can see my pull request has been reviewed by something called code rabbit which probably isn't the case for you.
47:5547 minutes, 55 secondsAnd that's perfectly fine. That's because I'm using Code Rabbit to review my pull requests automatically the
48:0248 minutes, 2 secondsmoment they are created and you will be able to do exactly the same. So I'm going to explain all about it in a
48:1048 minutes, 10 secondssecond, but for now let's just actually go over what happened in this pull request. So the first thing that happened is Code Rabbit provided me with
48:1848 minutes, 18 secondsa summary of this pull request. New features, we integrated user authentication system with sign in and sign up functionality. We added user
48:2748 minutes, 27 secondsaccount menu for authenticated users and finally we enabled security across the application with authentication middleware. So that is the highlevel
48:3648 minutes, 36 secondssummary which is always useful in itself. And then below it actually went file by file and found some what it
48:4448 minutes, 44 secondsthought was a bug. So in here it noticed that I have a file called proxy.t DS and it labeled this as a critical failure.
48:5448 minutes, 54 secondsIt said incorrect file name for Nex.js middleware. And I know what you're thinking. It's not exactly a great first
49:0249 minutes, 2 secondsimpression for an AI review tool to not have the most upto-date information, but give Code Rabbit a
49:0949 minutes, 9 secondsbenefit of the doubt, especially with what I'm about to show you next. So in the last few projects, code rapid has found multiple crit real critical
49:1949 minutes, 19 secondssecurity issues in my code. I think it is in general a good idea that between you and me, we have a third person, AI,
49:2849 minutes, 28 secondswhomever reviewing the code because as much as I think my code is okay, sometimes things slip. And if this
49:3549 minutes, 35 secondswasn't the case, if proxy truly was a misnamed file, it would have been a critical failure and middleware would
49:4349 minutes, 43 secondsnot have worked at all. So, it is actually impressive that code rabbit wrote this comment. But here's what's even more impressive. I actually
49:5149 minutes, 51 secondsresponded that middleware has been renamed to proxy in next 16 and I've provided with the documentation and you
49:5949 minutes, 59 secondscan see the response. The usual, you are absolutely correct. I know we are all tired of hearing that. It apologized for
50:0650 minutes, 6 secondsthe incorrect review comment and thanked me for the clarification. It even gave me some tips on how I should be exporting a function called proxy if I want to write some custom logic here.
50:1850 minutes, 18 secondsAnd here's the cool part. I can see learnings added. So from now on I have successfully taught Code Rabbit
50:2650 minutes, 26 secondssomething new. And this is where you can actually see what a high quality tool this is. Even though this encounter
50:3650 minutes, 36 secondsmight have seemed a bit annoying with its lack of uh the most up-to-date knowledge, we all know that AI is really
50:4450 minutes, 44 secondsstruggling with that. The fact that you can feed it new information makes it really, really good because this probably won't happen again now. And I
50:5450 minutes, 54 secondsthink this will stay true across my entire account. I think that the next time I start a project, this won't happen again because it now has this
51:0251 minutes, 2 secondslearning. So I think this is super cool example. Even though it looked like a big failure, it is actually really
51:0951 minutes, 9 secondsreally cool and I promise the more complex our pull requests get, the more useful code rabbit will be. Using the
51:1851 minutes, 18 secondslink on the screen, you can add the same thing to your GitHub account. And with a literal two-click install, you can add
51:2751 minutes, 27 secondsit to all of your pull requests. They have a super generous free tier. It costs you nothing to add this. It would
51:3551 minutes, 35 secondsmean the world to me if you would use the link you can see on the screen to create an account.
51:4051 minutes, 40 secondsSo, since this was a super simple pull request, we actually don't have too many things to do besides merge it. So, I'm going to go ahead and just merge this.
51:4951 minutes, 49 secondsI'm not going to change anything. And I'm not going to delete my branch. This way, whenever I want, I can just go
51:5651 minutes, 56 secondsahead and switch back to 02 authentication. And then I can see uh well, what I was doing back then. What
52:0452 minutes, 4 secondswe have to do now is we have to go back to our main branch here. And then we
52:1352 minutes, 13 secondshave to uh my apologies. We have to pull from origin main. So get pull origin
52:2052 minutes, 20 secondsmain. There we go. So you can see that I was ahead but now I am on the same branch. Uh great. My apologies. This
52:2852 minutes, 28 secondssyntax keeps confusing me. So it is get pool origin and then space uh main.
52:3352 minutes, 33 secondsPerfect. So what this means is that now I have completely synchronized my local main branch with my remote uh main
52:4152 minutes, 41 secondsbranch and we can confirm that with the visual editor here as well by clicking on the graph here. So we have this initial commit from create next app. We
52:4952 minutes, 49 secondsthen have our first commit which was in our first chapter project setup. And then you can see that we have uh
52:5552 minutes, 55 secondsbranched out into this 02 authentication branch. And then we merged that back into our main branch here. So you should have the exact same graph here.
53:0753 minutes, 7 secondsExcellent. I believe that marks the end of this chapter. So going on, this is how we're going to end all of our chapters with a branch so we can always
53:1553 minutes, 15 secondseasily come back to it and so that we get an actual uh code review uh of our changes which will come in very handy
53:2353 minutes, 23 secondswhen we start doing some uh security things. Amazing amazing job and see you in the next chapter.
Chapter 4: 03 Database Setup
53:3253 minutes, 32 secondsIn this chapter, we're going to set up our database. This will include setting up a new Convex account and a new project, installing a Convex SDK as well
53:4053 minutes, 40 secondsas the CLI tools, creating a table and testing out some CRUD operations on it, and finally configuring the Convex provider together with Clerk
53:4953 minutes, 49 secondsauthentication which we developed in the previous chapter. So, for now, no need to have your app running at the moment.
53:5653 minutes, 56 secondsIn fact, we're going to visit the Convex website. So, using the link on the screen, you can get to this page that I
54:0254 minutes, 2 secondssee right here. So why are we using convex for this application? Well, primarily one of the biggest problems
54:1154 minutes, 11 secondsthat I had was how do I bring a native file explorer feeling to a browser
54:1854 minutes, 18 secondscloud-based IDE because we are not writing files to any file system, right?
54:2454 minutes, 24 secondsWe are writing them to a database. So we are either going to store text content or binary content depending on what type of file it is. So, how do we make that
54:3354 minutes, 33 secondsfeel native? How do we make it feel so that the user is using an app even though this is a browser web
54:4154 minutes, 41 secondsapplication? In short, with Convex, our app will update in real time automatically. There will be no
54:4954 minutes, 49 secondswebsockets to set up, no polling, no cache invalidation headaches. It just works. And you will especially see this magic when we build the file explorer.
55:0055 minutesBut honestly, you will see it everywhere else as well. So this is why I've prepared the finished app so you can actually see what I'm talking about.
55:0955 minutes, 9 secondsThis is the finished result and I have purposely opened it in two different browsers. So I'm going to go ahead and just quickly create a new file something
55:1855 minutes, 18 secondslike test.tsx and you can see immediately it was created here and here right. So if I go
55:2555 minutes, 25 secondsahead and rename that to something, you can see that immediately it's been reflected elsewhere. That's the power of
55:3455 minutes, 34 secondsconvex. Same thing happens if I create a new folder. For example, uh app folder, right? My apologies. This was a file. So
55:4255 minutes, 42 secondsif I create an app folder, you can see immediately all the things are reflected here. If I go inside of here and create a new file, let's call this uh container.jsx.
55:5355 minutes, 53 secondsimmediately reflected. So this is byproduct of using Convex. It's amazing sync engine that makes every app feel
56:0256 minutes, 2 secondsnative. And this is reflected even further uh besides the file explorer.
56:0756 minutes, 7 secondsTake a look at the title of this project. Right? So I'm using some random unique slug generator. So I'm going to rename this to my project immediately renamed in the other side as well.
56:1856 minutes, 18 secondsThat's what I'm talking about. That is the power of Convex. So, let's get started and let's create an account. And
56:2656 minutes, 26 secondson the dashboard inside, you're going to see a list of your projects or an empty screen if you have none. So, I'm going to go ahead and create a new project.
56:3456 minutes, 34 secondsI'm going to call this Polaris and I will click create.
56:3956 minutes, 39 secondsOnce you've created your project, you don't really have to do anything here, but you can leave this tab open. Now, let's go ahead and go to Convex
56:4856 minutes, 48 secondsdocumentation here. So we can actually follow a simple getting started guide.
56:5356 minutes, 53 secondsSo in here you actually have quick starts next.js. So since we already have the project, we are not going to run this command. Instead, we're just going
57:0157 minutes, 1 secondto go inside of our app and run npm install convex. And then I'm going to show you the exact version of convex I will be using through this tutorial. So
57:0957 minutes, 9 secondsmake sure you are inside of your project here and run npm install convex. And I'm going to go ahead and prepare package
57:1757 minutes, 17 secondsJSON here. So you can see exactly what version has been added. So 1.31.2.
57:2557 minutes, 25 secondsFor those of you who want to use the same version as me, you can install it like this.
57:3057 minutes, 30 secondsOnce you have convex inside, let's see what the next steps are. So now we have to set up a convex dev deployment
57:3757 minutes, 37 secondsrunning npx convex dev. This will prompt you to log in with GitHub, create a project, and save your production and
57:4457 minutes, 44 secondsdeployment URLs. It will also create a new convex folder for you to write your backend API functions in. The dev command will then continue running to
57:5357 minutes, 53 secondssync your functions with your dev deployment in the cloud. So let's go ahead and run this command right here.
58:0058 minutesSo depending on if you've run this before or if it's your first time running it, you are probably getting a login link. Clicking on that login link
58:0858 minutes, 8 secondswill lead you to the login screen and then you just have to login with your account and then it will basically be able to either create a new project in
58:1758 minutes, 17 secondsyour account or you can choose an existing project and in here you should be able to see Polaris. So I'm purposely
58:2458 minutes, 24 secondsdoing it this way so you know that you you did it correctly right we created a new project called Polaris here and you
58:3058 minutes, 30 secondscan now select it here. There we go. And as you can see now uh something that will happen besides
58:3858 minutes, 38 secondsjust the connection is we have a new folder and we have some new things in our environment here. So let me go ahead and close everything here. Open Polaris
58:4758 minutes, 47 secondsand here we have the convex folder. So right now you can ignore the generated folder. Uh the underscore here kind of
58:5458 minutes, 54 secondsrepresents that it's not meant to be modified and we will never modify it. It will automatically be modified once we add things to our schema or our
59:0259 minutes, 2 secondsfunctions. Right? This is kind of like Prisma's generated folder. Uh, another thing you will notice is that we now have environment.local.
59:1059 minutes, 10 secondsSo, what I suggest actually is move this to one environment. Um,
59:1759 minutes, 17 secondsI'm going to see if maybe we should keep it in local or environment. For now, I'm just going to move all of them here like this. And I'm just going to change this to be convex.
59:2859 minutes, 28 secondsAnd if you want you can leave these comments so you know what your team is and what your project's name is like this. So you should have convex deployment and next public convex URL.
59:3859 minutes, 38 secondsAnd for now let's just remove environment.local.
59:4259 minutes, 42 secondsAnd I will test this out in just one simple way. I'm going to do npx convex dev again. And if this continuously
59:5059 minutes, 50 secondscreates the environment.local file then I will just move it to that. Looks like every time we run npx convex dev, it will create a dot environment.local.
1:00:001 hourSo instead of moving convex to environment, let's move clerk to environment.local. I think that might be
1:00:071 hour, 7 secondsa better solution. So move clerk here and let's go ahead and change this to convex and then remove dot environment.
1:00:181 hour, 18 secondsSorry for going around, but I just wanted to figure out which was the one that gets created all the time. In your
1:00:241 hour, 24 secondsnew environment. You should now have the same content that you had before for clerk with the addition of new convex
1:00:321 hour, 32 secondsvariables. And this time when you do npx convex dev, I believe there should be no changes to your environment.
1:00:411 hour, 41 secondsThere we go. So nothing new, nothing gets overridden. You don't have to worry. Perfect. Once we have that ready,
1:00:471 hour, 47 secondslet's see what we have to do next. So, we now have to create a sample data for our database. So, I'm just going to copy
1:00:551 hour, 55 secondsthis and then I'm just going to create that file. Uh, make sure you do this in the root of your app. So, outside of any
1:01:021 hour, 1 minute, 2 secondsfolders here, create a new file, sample data.json L.
1:01:091 hour, 1 minute, 9 secondsMake sure to put the letter L at the end. And let's just paste. So just a simple three list, three item list like this.
1:01:211 hour, 1 minute, 21 secondsNow let's go ahead and let's run this command. npx convex import table tasks sample data.jsonl.
1:01:291 hour, 1 minute, 29 secondsMake sure you are running it in the root of your project so that it can actually find sample data.jsonl.
1:01:371 hour, 1 minute, 37 secondsAll right, as you can see, we have a success message. Added three documents to table tasks. And before I go any further, if you failed at this command
1:01:451 hour, 1 minute, 45 secondsfor any reason, don't worry. This is just to test out how convex works. So if you're using uh a specific operating system where this doesn't work as
1:01:541 hour, 1 minute, 54 secondsintended, it's okay. Uh we will create normal data and schema later on. But I just wanted to populate it with
1:02:011 hour, 2 minutes, 1 secondsomething as in the tutorial. And immediately if you go back to this screen, your database, you will now see a table called tasks. And inside of here
1:02:101 hour, 2 minutes, 10 secondsyou will see is completed field as well as the text field as well as their creation time. And this is your database
1:02:191 hour, 2 minutes, 19 secondsnow. So let's see what are the next steps here. Let's expose a database query. So let's find a way to fetch from
1:02:261 hour, 2 minutes, 26 secondsthis database and display that data in our app. So we're going to go ahead and do the following. Inside of our convex folder, I'm going to go ahead and create a new file called tasks.
1:02:361 hour, 2 minutes, 36 secondsuh ts and let's paste this here. So import query from dot /generated
1:02:441 hour, 2 minutes, 44 secondsforward slashs server which is basically this right here. We are exporting a constant called get and we are using the
1:02:521 hour, 2 minutes, 52 secondsquery. The query accepts the following parameters. an arguments which is empty for now and a handler which is an
1:02:591 hour, 2 minutes, 59 secondsasynchronous function which has access to the context and then the context itself has access to the database uh abstraction which we can in this kind of
1:03:081 hour, 3 minutes, 8 secondsquery builder tool well query and collect items from which table tasks and what's cool is that it should give you
1:03:181 hour, 3 minutes, 18 secondsuh errors if something is wrong uh we just need to make sure we have convex npx convex dev running.
1:03:281 hour, 3 minutes, 28 secondsLet's just ensure that we have that and I believe that then uh my apologies it will not give you uh errors here.
1:03:401 hour, 3 minutes, 40 secondsSo in order to test this out we have to make sure that we have npx convex dev running. So just make sure you have this
1:03:481 hour, 3 minutes, 48 secondsrunning and then you will get a simple message of uploading functions to convex and then convex functions are ready and [snorts] you can actually test whether
1:03:551 hour, 3 minutes, 55 secondsthis works or not already. You can go back here and go inside of your functions here and you will find a new
1:04:021 hour, 4 minutes, 2 secondsfunction tasks get. You can click on run function here since there are no arguments to be passed. You can see that the output was a simple fetch of all of
1:04:111 hour, 4 minutes, 11 secondsour functions. So if you were to purposely mess it up by querying the wrong table here
1:04:191 hour, 4 minutes, 19 secondsand then let's try and run this again run function. You will see this time we have no output at all. Right? Uh I
1:04:281 hour, 4 minutes, 28 secondsbelieve that later on this will actually throw an error right here in the editor.
1:04:321 hour, 4 minutes, 32 secondsBut in order to do that we need to have an actual schema. Since we don't have a schema it doesn't really know what's true or not. Right? How does it even
1:04:401 hour, 4 minutes, 40 secondsknow that tasks exists? Well, it doesn't. We know that because we created them using a JSONL file. So, if you're
1:04:481 hour, 4 minutes, 48 secondsworried about that, don't be because later we are going to have a proper schema which will give us some type safety in that aspect.
1:04:571 hour, 4 minutes, 57 secondsGreat. So, now instead of testing this function through Convex's dashboard, how about we actually test it through our
1:05:041 hour, 5 minutes, 4 secondsapp? In order to do that, we first need to create a Convex client provider. So, I'm going to go ahead and do that. I'm
1:05:111 hour, 5 minutes, 11 secondsgoing to create inside of my source components convex-client-provider.tsx
1:05:211 hour, 5 minutes, 21 secondslike that. And I'm just going to copy the content inside and then show you what it is. So we have use client to
1:05:281 hour, 5 minutes, 28 secondsmake this a client component. We are importing convex provider and convex react client from convex forward/react and react node from react. We initialize
1:05:371 hour, 5 minutes, 37 secondsa new convex singleton using new convex react client and we pass in process.environment next public convex url and this is the important part. So
1:05:461 hour, 5 minutes, 46 secondsdouble check that inside of your environment.local local you actually have next public's convex URL
1:05:541 hour, 5 minutes, 54 secondsand then we export function convex client provider which is a very simple function which simply returns the convex
1:06:001 hour, 6 minutesprovider element passes the client prop and renders the children inside
1:06:091 hour, 6 minutes, 9 secondsnow that we have our convex client provider ready let's add it to our layout which I believe is outlined as the next step there we go so make sure
1:06:181 hour, 6 minutes, 18 secondsyou save this file and let's go inside of source app folder layout and in here I'm going to go ahead and the same way
1:06:261 hour, 6 minutes, 26 secondswe imported the theme provider let's import convex client provider and make sure you do that from add components
1:06:331 hour, 6 minutes, 33 secondsconvex client provider so don't use any npm import you're using your file that you've just created and then go ahead
1:06:421 hour, 6 minutes, 42 secondsand render this convex client provider let's see around the children so I'm going to go ahead and do this inside of the theme provider like this.
1:06:571 hour, 6 minutes, 57 secondsThere we go. And all the way to here.
1:07:041 hour, 7 minutes, 4 secondsPerfect. Now that that is ready, let's just go ahead and make sure our app is running. So I suggest that you have both
1:07:111 hour, 7 minutes, 11 secondsof these running. npx convex dev and npm rundev. Imagine this as your front end and this as your back end. So now I'm
1:07:201 hour, 7 minutes, 20 secondsgoing to go ahead and go to localhost 3000 and I'm just going to confirm that nothing crashes and everything seems to work perfect. And now that we have this
1:07:281 hour, 7 minutes, 28 secondsprovider set up, we can actually use the hooks. So I'm going to go ahead and do the following. I will go inside of
1:07:341 hour, 7 minutes, 34 secondssource app page.tsx and I'm going to change this to be a client component. I'm doing this so I can use hooks within this page.
1:07:461 hour, 7 minutes, 46 secondsAnd I'm going to go ahead and I will call tasks using use query from convex react. And then I will import API from
1:07:541 hour, 7 minutes, 54 secondsdot dot dot doconvex generated API. This will give me access to type safe functions that I've developed.
1:08:021 hour, 8 minutes, 2 secondsAnd then what I will be able to do is iterate over them. So tasks question mark dot map and in here I will have an
1:08:101 hour, 8 minutes, 10 secondsindividual task and then I will be able to return a div like this
1:08:181 hour, 8 minutes, 18 secondsgive each div a key task id and let's go actually it is underscore
1:08:261 hour, 8 minutes, 26 secondsID my apologies. So why does it why didn't it throw an error here again?
1:08:321 hour, 8 minutes, 32 secondsBecause we don't have the schema. So it had no way of knowing if maybe ID was some property that we had right because
1:08:401 hour, 8 minutes, 40 secondswe could have easily added a property called ID here. So because of that it's not throwing any errors. As I said later
1:08:471 hour, 8 minutes, 47 secondswhen we add a real schema it will throw errors for undefined fields or tables that don't exist.
1:08:561 hour, 8 minutes, 56 secondsSo now let's go ahead and simply render task dot uh you can see there's no auto completion either so I have to manually
1:09:051 hour, 9 minutes, 5 secondsadd text and let's go ahead and do is completed task is completed
1:09:131 hour, 9 minutes, 13 secondsmake sure you don't misspell this because as I said no type safety at the moment because we don't have a schema file
1:09:201 hour, 9 minutes, 20 secondsand just for fun I'm going to make this class name border rounded padding to flex flex column. And I will
1:09:301 hour, 9 minutes, 30 secondsgo ahead and give this flex flex column gap two. So they appear one beneath the other. There we go. And let's give all
1:09:391 hour, 9 minutes, 39 secondsof this a padding of four. So you can see that now.
1:09:441 hour, 9 minutes, 44 secondsAnd let's just go ahead and wrap this inside of template literal.
1:09:511 hour, 9 minutes, 51 secondsUh let me just see. There we go.
1:09:581 hour, 9 minutes, 58 secondsSo you can see the actual output. So is completed true? Is completed true? Is completed false. So [snorts] let's actually try something out. I'm
1:10:061 hour, 10 minutes, 6 secondsgoing to open a split view here. You don't have to do that. Uh this is a new feature. So I'm learning it. Add tab to new split view. And I will choose this.
1:10:161 hour, 10 minutes, 16 secondsOkay. So I have my app right here. And I'm going to go ahead inside of my uh data here.
1:10:241 hour, 10 minutes, 24 secondsAnd I will find one is completed which is false. So integrate convex is currently in state of false. And watch
1:10:321 hour, 10 minutes, 32 secondswhat happens when I directly modify this in the database to true. It is immediately reflected in my app. That is the native field I keep talking about.
1:10:421 hour, 10 minutes, 42 secondsRight? When you are using a real-time database which needs to have and it does have a very very good sync engine. This
1:10:511 hour, 10 minutes, 51 secondsbecomes a completely different experience, right? And when we buil we are building something like a cloud-based IDE, we need to have that
1:11:001 hour, 11 minutesfeeling. No one wants to work in something that feels like a secondhand experience as opposed to uh you know a
1:11:071 hour, 11 minutes, 7 secondsnormal CL normal normal IDE on your machine. So that's why we are choosing convex for this. And same goes if you change this to false, right?
1:11:181 hour, 11 minutes, 18 secondsImmediately reflected here. Perfect. And that's actually it for the quick start here. So what I want to do now is I just
1:11:271 hour, 11 minutes, 27 secondswant to create a schema and then I want to connect all of this with convex with with clerk. So I'm going to go ahead and
1:11:351 hour, 11 minutes, 35 secondsclose this for now. And this time instead of having tasks, let's go ahead and go inside of our convex right here.
1:11:421 hour, 11 minutes, 42 secondsAnd let's create a schema.ts.
1:11:471 hour, 11 minutes, 47 secondsSo inside of here I'm going to import define schema from convex server.
1:11:531 hour, 11 minutes, 53 secondsI'm going to import v from convex values and I'm also going to import define table from convex server. I will export default define schema here.
1:12:071 hour, 12 minutes, 7 secondsI will create new projects table using define table and I will give each project a name and I'm also going to
1:12:161 hour, 12 minutes, 16 secondsgive it something fun. Uh for example, let's do owner ID and let's do import status.
1:12:291 hour, 12 minutes, 29 secondsV dot optional V dot union
1:12:341 hour, 12 minutes, 34 secondsV dot literal importing completed
1:12:411 hour, 12 minutes, 41 secondsand failed. So I'm purposely trying to do something a bit more complex than just a normal string so that you can see how you would for example create an enum
1:12:491 hour, 12 minutes, 49 secondsright. So each of our projects will be able to have an import status which is completely optional because users can
1:12:561 hour, 12 minutes, 56 secondseither create new projects from scratch or they will be able to import them from GitHub. In case they are importing we're
1:13:031 hour, 13 minutes, 3 secondsgoing to be using these set of enumes to let the user know what is the status of the import. Is it currently importing?
1:13:101 hour, 13 minutes, 10 secondsHas it completed or has it failed? And once you save this what I want to do is I want to add an index. My apologies not
1:13:171 hour, 13 minutes, 17 secondssave this. So I'm going to add an index here by owner. So by adding the field owner ID, I will be
1:13:261 hour, 13 minutes, 26 secondsable to query the projects much faster by owner ID. So every time I need to
1:13:331 hour, 13 minutes, 33 secondsload all projects by a certain user, I will be able to do that in that manner.
1:13:401 hour, 13 minutes, 40 secondsSo now that you save this file, it needs to be named schema. It needs to have a default export here. Uh you should see
1:13:491 hour, 13 minutes, 49 secondsthis. You should see that it has added table indexes. You should see that there was probably some error here because we
1:13:561 hour, 13 minutes, 56 secondstried to basically this is this keeps trying to synchronize your code with convex cloud. So if you are in the middle of uh writing it, it might be
1:14:041 hour, 14 minutes, 4 secondsinvalid. So that's why the errors are happening. But if the last message you see is a success, that means everything
1:14:111 hour, 14 minutes, 11 secondsis working. If you want to, you can also restart the entire thing and that will automatically try again. And this time
1:14:191 hour, 14 minutes, 19 secondsthere shouldn't be any errors whatsoever.
1:14:221 hour, 14 minutes, 22 secondsAnd now if you go ahead inside of your uh convex. So let me just go ahead and go to my project here. And if I go inside of my uh let me see is it data?
1:14:341 hour, 14 minutes, 34 secondsYes, inside of my data here you can see that I now have projects in here. And if I open tables, you can see I still have
1:14:421 hour, 14 minutes, 42 secondsmy previous ones tasks, but it says this table is not defined in your schema, right? So, it's keeping them separate.
1:14:531 hour, 14 minutes, 53 secondsAnd you can actually always take a look at your schema right here.
1:14:581 hour, 14 minutes, 58 secondsSo, you can see what it's doing. It's constantly synchronizing the code you have written locally to the cloud right here. That's also one of the very very
1:15:071 hour, 15 minutes, 7 secondscool features of Convex. And if you learn to use this dashboard, your life is going to be so much easier because you will actually learn to see, you
1:15:151 hour, 15 minutes, 15 secondsknow, how much of your functions are hitting the cache, how much are they failing, uh, you will be able to create
1:15:221 hour, 15 minutes, 22 secondslog streams, all of those things. Uh, and there are so many more things Convex can do, but for this chapter, we're just going to focus on what it does best,
1:15:311 hour, 15 minutes, 31 secondswhich is real time database, but you can orchestrate agents with it. You can create schedules, a bunch of bunch of things here. And we will also be using
1:15:401 hour, 15 minutes, 40 secondsit as our file upload system for binary files when we need that function. So now that we have projects here, you can see
1:15:471 hour, 15 minutes, 47 secondsthat you can add them by passing in the name, the owner ID, which are the required fields. So how about we go
1:15:541 hour, 15 minutes, 54 secondsahead and try and do that. So instead of convex, we can actually now remove tasks. And you can see this is what I
1:16:021 hour, 16 minutes, 2 secondswas talking about. Now we have an error here because the only table it knows about from our schema is projects. So
1:16:101 hour, 16 minutes, 10 secondsit's very confused about the fact that we are querying tasks and maybe even in page here we now get type errors because
1:16:191 hour, 16 minutes, 19 secondsit doesn't know what this task schema is supposed to look like. So that's what I was telling you that is going to happen.
1:16:251 hour, 16 minutes, 25 secondsSo yes, you can now remove tasks from here and instead in the convex go ahead and create projects. DS and let's go
1:16:331 hour, 16 minutes, 33 secondsahead and export const create. And inside of here, what we're going to do is we're going to create a mutation like
1:16:421 hour, 16 minutes, 42 secondsthis with arguments. And inside of here, we're just going to accept a name.
1:16:491 hour, 16 minutes, 49 secondsAnd let's go ahead and import V from convex values.
1:17:001 hour, 17 minutesAnd then let's add a handler which is an asynchronous function. We can access context from here.
1:17:101 hour, 17 minutes, 10 secondsAnd what we're going to do is very simply await convex dot database dotinsert into project table context.
1:17:221 hour, 17 minutes, 22 secondsMy apologies arguments are separated like this.
1:17:271 hour, 17 minutes, 27 secondsSo let's just pass in the name to be arguments and owner id which is also required
1:17:361 hour, 17 minutes, 36 secondsand this is arguments.name. So for now yeah just hardcode owner ID to 1 to3. We are doing this on purpose because later we are going to connect this with clerk.
1:17:451 hour, 17 minutes, 45 secondsSo we will able actually be able to extract the user's ID here. And let's export const get which is our query.
1:17:531 hour, 17 minutes, 53 secondsarguments will be empty. Handler will be an asynchronous function and I'll just await context database.
1:18:021 hour, 18 minutes, 2 secondsWhoops. So let's just get context.
1:18:071 hour, 18 minutes, 7 secondsWe have to import query the same place we imported mutation from. And then we will get convex.database.get
1:18:161 hour, 18 minutes, 16 secondsget projects table and then just uh collect
1:18:241 hour, 18 minutes, 24 secondsmy apologies it is not get it is a query the get accepts an ID get is for a
1:18:311 hour, 18 minutes, 31 secondssingle one but yeah we can just call this get for now uh and let's save it like that and let's make sure that the
1:18:381 hour, 18 minutes, 38 secondslast message you see here are that convex functions are ready and now let's go back inside of the page here and instead of tasks this will now be projects api.p projects.get.
1:18:491 hour, 18 minutes, 49 secondsWe are going to iterate over projects and we are going to use the project name. So we're going to be using project
1:18:561 hour, 18 minutes, 56 secondsand this time if you try uh you should be able to see uh the keys. Let me just see what's going on here.
1:19:051 hour, 19 minutes, 5 secondsUh that's because we're not returning this. There we go.
1:19:151 hour, 19 minutes, 15 secondsAnd now if you try there we go you can see type safety which I was talking about. So in here you can now do name
1:19:221 hour, 19 minutes, 22 secondsand you can also do owner id project dot owner id and you can render
1:19:301 hour, 19 minutes, 30 secondsthis in a normal way now because it's no longer a type of boolean.
1:19:361 hour, 19 minutes, 36 secondsSo right now I don't think anything will appear here. So what we can do is we can create a simple mutation. So I will do
1:19:441 hour, 19 minutes, 44 secondsconst create project use mutation which we can import from convex react and pass in API. projects
1:19:541 hour, 19 minutes, 54 secondsyou guessed it create. And then above this I'm going to add a button which we can import from components UI button.
1:20:051 hour, 20 minutes, 5 secondsAnd I'm going to add a label. Add new on click.
1:20:121 hour, 20 minutes, 12 secondsCreate project. Let's just make sure we do it like this.
1:20:191 hour, 20 minutes, 19 secondsSo create project and pass in the name.
1:20:221 hour, 20 minutes, 22 secondsAnd let's call this new project like this. And when you click
1:20:291 hour, 20 minutes, 29 secondsadd new, there we go. It immediately creates it with a name new project with the owner ID. So if I change this to new
1:20:361 hour, 20 minutes, 36 secondsproject 1 to three and click again there we go. So you can see how we don't have to do any invalidation. We don't have to do any polling. The sync engine does its
1:20:451 hour, 20 minutes, 45 secondsmagic. That is the magic of this use query right here. So, how do I get the currently logged in user, which I am
1:20:531 hour, 20 minutes, 53 secondsright now, inside of this owner ID? And more so, in fact, how do I throw an error when the user is logged out?
1:21:021 hour, 21 minutes, 2 secondsBecause it's easy to protect the UI. But what's important is to protect our data access layer because that way even if
1:21:101 hour, 21 minutes, 10 secondssomehow someone bypasses our uh proxy or middleware, which has been known to happen, right? people have found
1:21:191 hour, 21 minutes, 19 secondsvulnerabilities in the proxy. Which was previously called middleware. Uh people who still protected their API routes
1:21:271 hour, 21 minutes, 27 secondsindividually or in this case API functions were completely okay, right?
1:21:331 hour, 21 minutes, 33 secondsSo that's what we're going to learn how to do. Let's go ahead and learn how to connect clerk with convex.
1:21:401 hour, 21 minutes, 40 secondsYou can actually find this exact guide on their documentation page. So let's actually go through it so we learn how to find it together. I think it's always
1:21:481 hour, 21 minutes, 48 secondsgood to learn how to use the documentation. So they offer a bunch of authentication providers. The one we are using is Clerk. So I'm going to find it
1:21:571 hour, 21 minutes, 57 secondshere in the sidebar. And then I'm going to find the next JS example. So we already created an account with clerk.
1:22:051 hour, 22 minutes, 5 secondsAnd what we have to do now is we have to create a JVT template. So this is very important. Let's go ahead and head to dashboard.clarker.com.
1:22:141 hour, 22 minutes, 14 secondsYou can use the link on the screen of course and let's go to our new Polaris app. In here you should have only one
1:22:221 hour, 22 minutes, 22 secondsuser or more if you added more users and you know about it. And now let's go ahead through here and let's go inside of sessions and click on JVT templates.
1:22:321 hour, 22 minutes, 32 secondsIn here click add new template for the template field. You can actually select convex out of the box. You don't have to
1:22:411 hour, 22 minutes, 41 secondschange anything here and you especially shouldn't modify the name. So just click save as it is. There we go. You should now have a new template convex.
1:22:521 hour, 22 minutes, 52 secondsAnd now in here it says to copy and save the issue URL somewhere secure. So let's go ahead and do that. We have the issuer right here. And I'm going to copy it.
1:23:031 hour, 23 minutes, 3 secondsAnd now I'm going to go ahead and store it inside of my environment file. I believe that's where we need to add it.
1:23:121 hour, 23 minutes, 12 secondsSo let me just go ahead and check.
1:23:161 hour, 23 minutes, 16 secondsSo environment.local I'm going to add one more field to the clerk section and this will be called
1:23:241 hour, 23 minutes, 24 secondsclerk_jvt_issuer domain.
1:23:311 hour, 23 minutes, 31 secondsAnd let's just paste it here.
1:23:351 hour, 23 minutes, 35 secondsThere we go. Now that we have added this, here's an important thing you have to do.
1:23:411 hour, 23 minutes, 41 secondsYou also need to synchronize your Convex Cloud environment variables. So, I'm going to go inside of my settings right here and click on environment variables.
1:23:531 hour, 23 minutes, 53 secondsAnd I'm just going to go ahead and you don't have to add the next public's convex URL or convex deployment. But if you want to, you can just copy your
1:24:011 hour, 24 minutes, 1 secondentire environment.local file and just paste things here. So, I really don't think you need convex deployment here or
1:24:091 hour, 24 minutes, 9 secondsnext public convex. So, I'm going to remove those. I'm just going to keep next public's clerk, next public clerk, clerk secret key, and clerk JVT issuer
1:24:171 hour, 24 minutes, 17 secondsdomain. You most likely don't need this one either. This is specifically used for front end, but still uh we can paste our entire environment file here. And
1:24:261 hour, 24 minutes, 26 secondslet's just save all of these. So, this is important because the cloud doesn't have access to our local environment
1:24:341 hour, 24 minutes, 34 secondsfiles, right? Uh that is not synchronized because obviously those are our private keys. it would be a bad idea to synchronize those. So that's why we
1:24:431 hour, 24 minutes, 43 secondshave to do it this way. So just make sure that in your project polaris in convex environment variables you have added clerk JVT issue domain, clerk
1:24:501 hour, 24 minutes, 50 secondssecret key and next public clerk publishable key. Great. And now you will
1:24:571 hour, 24 minutes, 57 secondsbe able to learn how to uh let me just scroll down. There we go.
1:25:031 hour, 25 minutes, 3 secondsNext.js. So we created the template. Uh yes. And now we have to go ahead and do the following. We have to go inside of
1:25:111 hour, 25 minutes, 11 secondsconvex and inside of here we have to create out.config.ts and let's go ahead and let's import out
1:25:211 hour, 25 minutes, 21 secondsconfig from convex server. Let's export default
1:25:281 hour, 25 minutes, 28 secondsproviders. Open an array. Open an object.
1:25:321 hour, 25 minutes, 32 secondsAdd a domain to be process.environment environment and then clerk JVT issuer domain
1:25:401 hour, 25 minutes, 40 secondsand then application ID set it to be convex. We're going to go over these values and why those values
1:25:471 hour, 25 minutes, 47 secondsspecifically in a second and let's add satisfies out config.
1:25:541 hour, 25 minutes, 54 secondsAll right, let's go ahead and see the first thing is ID needs to be capitalized. There we go.
1:26:001 hour, 26 minutesSo why convex exactly in the application ID? The reason is because our template name is convex. That's why I told you
1:26:091 hour, 26 minutes, 9 secondsnot to modify that because it needs to be the same. And the second thing is clerk JVD issue domain. Double check
1:26:161 hour, 26 minutes, 16 secondsthat you have called it exactly the same here. So clerk JVT is domain. Copy it from here and then paste it here. It
1:26:241 hour, 26 minutes, 24 secondsshould match exactly. And then double check once more that you have named it correctly here. Clerk JVT issue domain.
1:26:331 hour, 26 minutes, 33 secondsAll right. Now that you have that, double check that again the last messages you see here are that convex functions are ready. It's completely
1:26:421 hour, 26 minutes, 42 secondsokay to have an error here. That's because it tried to synchronize when we were writing this code. So obviously it broke. We already have clerk next.js, so
1:26:511 hour, 26 minutes, 51 secondsno need to do that. We already have this. And we even have the middleware now. What we have to do now is we have to configure convex provider with clerk.
1:27:001 hour, 27 minutesSo this is what I suggest that we do. At this point we are having a lot of providers. So let's go ahead and do the following. Let's go inside of source
1:27:081 hour, 27 minutes, 8 secondscomponents and let's create a new file called provider providers.tsx.
1:27:151 hour, 27 minutes, 15 secondsAnd in here I'm going to mark this as use client. And I'm going to go ahead and I will import
1:27:231 hour, 27 minutes, 23 secondsclerk provider and use out from add clerk nextjs.
1:27:321 hour, 27 minutes, 32 secondsI'm going to import convex provider with clerk
1:27:391 hour, 27 minutes, 39 secondsfrom convex forward slashreact clerk and I'm going to establish convex here
1:27:461 hour, 27 minutes, 46 secondsusing new convex react client process environment next public convex url
1:27:581 hour, 27 minutes, 58 secondsand let me just see yes we also need to import convex React client from convex react. So we are basically kind of modifying this convex client provider.
1:28:101 hour, 28 minutes, 10 secondsAnd you know now that I think of it maybe we don't need to create a whole new providers again.
1:28:181 hour, 28 minutes, 18 secondsMaybe it is enough for this to actually let me just check.
1:28:241 hour, 28 minutes, 24 secondsOkay, you know what? Let's create the providers because it it's going to be easier to maintain things this way, right? So we're just basically creating
1:28:311 hour, 28 minutes, 31 secondsthe same thing. You can copy from here and paste it here to ensure that you've used the correct environment variables here. And then what we're going to do is
1:28:391 hour, 28 minutes, 39 secondsexport const providers children
1:28:471 hour, 28 minutes, 47 secondsreact node.
1:28:521 hour, 28 minutes, 52 secondsThere we go. And then I'm going to return clerk provider here.
1:28:581 hour, 28 minutes, 58 secondsAnd then in here I'm going to return convex provider with clerk. And I'm going to give it client of convex
1:29:061 hour, 29 minutes, 6 secondsand use out of use out.
1:29:111 hour, 29 minutes, 11 secondsAnd inside of here I'm going to render the children like this.
1:29:201 hour, 29 minutes, 20 secondsAnd now that we have this, let's go ahead and wrap our app with it.
1:29:271 hour, 29 minutes, 27 secondsSo I'm going to go inside of source app folder layout. I'm going to remove the clerk provider from here.
1:29:361 hour, 29 minutes, 36 secondsAnd from here and for now I'm going to remove the entire header here. So I just have the convex client provider. I'm
1:29:441 hour, 29 minutes, 44 secondsgoing to remove all the imports from clerk to clear things up. And then I'm going to import my providers and providers here.
1:29:581 hour, 29 minutes, 58 secondsAnd let's just add providers like this.
1:30:011 hour, 30 minutes, 1 secondSo, so far not much should change. More importantly, our app should still be working just fine. You should still be able to load your elements here. You
1:30:101 hour, 30 minutes, 10 secondsshould be able to create new ones. So, nothing much has changed, right? We created the providers and we just
1:30:171 hour, 30 minutes, 17 secondschanged from let's go ahead and go to convex-client provider. So we changed from using the convex provider to using
1:30:251 hour, 30 minutes, 25 secondsconvex provider with clerk. That's basically the biggest change and we just combine them in one. So we don't have to
1:30:321 hour, 30 minutes, 32 secondsmanually do that. At this point you can delete convex client provider entirely.
1:30:381 hour, 30 minutes, 38 secondsAnd you can even add the theme provider to here. So let's do that. Let's add the
1:30:451 hour, 30 minutes, 45 secondstheme provider like this.
1:30:501 hour, 30 minutes, 50 secondsAnd I'm going to import theme provider from dot /the provider. So the local one. And then you can remove the theme
1:30:581 hour, 30 minutes, 58 secondsprovider from here. This way our layout isn't polluted with a bunch of imports and a bunch of providers. So we just have a nice sleek providers right here.
1:31:101 hour, 31 minutes, 10 secondsGreat.
1:31:111 hour, 31 minutes, 11 secondsSo now what we have to do is we have to learn how to actually access convex uh
1:31:191 hour, 31 minutes, 19 secondshow to actually access clerk's authentication within convex because sure this is still just UI. We haven't really done anything yet. So let's go
1:31:281 hour, 31 minutes, 28 secondsinside of convex and let's go inside of projects.dts.
1:31:321 hour, 31 minutes, 32 secondsAnd now in here I'm going to go ahead and attempt to extract my current user.
1:31:391 hour, 31 minutes, 39 secondsAnd the way I can do that is by doing the following. I can call context.out
1:31:481 hour, 31 minutes, 48 secondsget user identity. And this needs to be awaited.
1:31:531 hour, 31 minutes, 53 secondsAnd then what I'm going to do is that if there is no identity in the first place, I'm going to go ahead and throw new error unauthorized.
1:32:041 hour, 32 minutes, 4 secondsYou shouldn't be able to visit this, right?
1:32:071 hour, 32 minutes, 7 secondsAnd okay. uh that seems to be throwing an error now simply because we haven't established a proper uh composition of
1:32:161 hour, 32 minutes, 16 seconds[snorts] inside of layout here. You need to wrap your app inside of authenticated from convex react like this.
1:32:281 hour, 32 minutes, 28 secondsAnd we need to oops not here my apologies inside of providers.
1:32:351 hour, 32 minutes, 35 secondsSo let's just quickly do that.
1:32:401 hour, 32 minutes, 40 secondswrap your children in authenticated which you can import from convex forward/react.
1:32:471 hour, 32 minutes, 47 secondsAnd now when you do this uh you shouldn't be getting an error here. So let's go ahead and do the following.
1:32:541 hour, 32 minutes, 54 secondsNow in here let's do the same thing.
1:32:561 hour, 32 minutes, 56 secondsconst identity await context.alfout al get user
1:33:021 hour, 33 minutes, 2 secondsidentity and owner ID will now be identity dot subject and let's go ahead and do if
1:33:111 hour, 33 minutes, 11 secondsthere is no identity throw new error unauthorized.
1:33:191 hour, 33 minutes, 19 secondsThere we go. And in here let's actually just return an empty array if there is no identity present. Great.
1:33:281 hour, 33 minutes, 28 secondsSo now I'm just going to go ahead and go back in here.
1:33:361 hour, 33 minutes, 36 secondsLet's go inside of source app. My apologies components providers and let's add unauthenticated view
1:33:461 hour, 33 minutes, 46 secondsfrom convex react. So you can see I have imported authenticated convex react client and unauthenticated all from one place.
1:33:581 hour, 33 minutes, 58 secondsAnd in here I'm just going to say not authenticated.
1:34:051 hour, 34 minutes, 5 secondsAnd then in here I'm going to add out loading from the same place convex react. And I'm going to say out loading.
1:34:171 hour, 34 minutes, 17 secondsSo what we actually want to happen here is to have a sign in button and a sign up button from clerk.js.
1:34:281 hour, 34 minutes, 28 secondsSo now I'm going going to go ahead and sign in here the way I usually do with GitHub.
1:34:341 hour, 34 minutes, 34 secondsI'm pretty sure you will get logged out too during this process. And there we go. You can see what happened. We now had out loading and now we have this
1:34:431 hour, 34 minutes, 43 secondsright. So let's go ahead and just try and uh let's
1:34:511 hour, 34 minutes, 51 secondstry and do the following now. So I will move children outside of any out thing and I will
1:34:591 hour, 34 minutes, 59 secondscomment out authenticated right. So now I can load and see this even if I am um
1:35:081 hour, 35 minutes, 8 secondslogged out. So okay, let's reenable this and let's just render user button inside
1:35:161 hour, 35 minutes, 16 secondsagain. You can import this from K next.js.
1:35:191 hour, 35 minutes, 19 secondsSo I should be able to log out myself now. And you can see that now since I am
1:35:251 hour, 35 minutes, 25 secondsnot logged in, I cannot see any projects. That is because of this. If we
1:35:321 hour, 35 minutes, 32 secondsare not able to detect an identity here, we throw an empty array. So if I comment this out
1:35:401 hour, 35 minutes, 40 secondsand refresh, I can now again fetch the projects.
1:35:461 hour, 35 minutes, 46 secondsBut that shouldn't happen. This should be the normal behavior, right? So that's why we have added this. If there is no
1:35:531 hour, 35 minutes, 53 secondsidentity present, we just return an empty array. But what's more impressive is this the mutation. I'm logged out and
1:36:021 hour, 36 minutes, 2 secondsif I click add new I'm getting an error unauthorized right but if I sign in with
1:36:101 hour, 36 minutes, 10 secondsGitHub this time take a look at what will happen I will be able to a load my
1:36:181 hour, 36 minutes, 18 secondsproject and b click add new and this time it has populated the exact user ID
1:36:261 hour, 36 minutes, 26 secondsthat I have and one thing I've just noticed that I forgot to tell you uh right now you can't select anything in
1:36:341 hour, 36 minutes, 34 secondsyour app if you try to. That's because in chapter one we copied and pasted my globals.css.
1:36:401 hour, 36 minutes, 40 secondsSo inside of your source app globals.css. If that's bothering you, just remove select none. And now you
1:36:471 hour, 36 minutes, 47 secondsshould be able to select things. Let me refresh and see.
1:36:541 hour, 36 minutes, 54 secondsUh that should have fixed it. Perhaps you just need to I mean we just need to restart the app.
1:37:021 hour, 37 minutes, 2 secondsLet's go ahead and do rmrf.next to clear out the cache and then run the app again.
1:37:091 hour, 37 minutes, 9 secondsThere we go. You can now select things.
1:37:111 hour, 37 minutes, 11 secondsSo in case you notice that it's because of this select none on the body. Later this will be useful to get that real
1:37:201 hour, 37 minutes, 20 secondseditor feeling and to disallow user from selecting things they shouldn't be selecting. But for now, it actually might be useful. So, no need to add
1:37:291 hour, 37 minutes, 29 secondsthat. I'm going to add a to-do to-do add select none later.
1:37:391 hour, 37 minutes, 39 secondsAnd let me end the comment here. There we go.
1:37:441 hour, 37 minutes, 44 secondsSo, that's what's happening now. We have successfully connected Clerk to our back end. And here's what we can do even
1:37:511 hour, 37 minutes, 51 secondsmore. We can actually now learn to use that index of ours. So let's do context.database.query.t
1:38:001 hour, 38 minutesprojects and let's do now with index by owner. And by owner accepts a query. And
1:38:071 hour, 38 minutes, 7 secondsin inside of here we can do query equals for a field of owner ID to be matching identity dots subject.
1:38:171 hour, 38 minutes, 17 secondsSo let me go ahead and expand this.
1:38:221 hour, 38 minutes, 22 secondsuh like this and this. There we go. So we are now
1:38:291 hour, 38 minutes, 29 secondsquerying for all projects from the loggedin user. You can see how now I can
1:38:361 hour, 38 minutes, 36 secondsonly see projects which have my owner ID. That is because in my data here in my projects, all of my previous ones
1:38:441 hour, 38 minutes, 44 secondshave this hard-coded one, two, three owner ID, which means that this user shouldn't be allowed to see those. So, our authentication is working correctly.
1:38:551 hour, 38 minutes, 55 secondsThis is what I wanted us to achieve. My apologies for a few hiccups here and there. It's kind of hard to, you know, demonstrate this with so little data in
1:39:041 hour, 39 minutes, 4 secondsour project, but I think we did a pretty good job with explaining how we successfully connected clerk with
1:39:101 hour, 39 minutes, 10 secondsconvex. This will basically be the most important way of building our back end.
1:39:161 hour, 39 minutes, 16 secondsSo, it's important that we establish this that early on. Amazing. So, I
1:39:221 hour, 39 minutes, 22 secondsbelieve that actually um did most of the hard work regarding this. I think um I
1:39:311 hour, 39 minutes, 31 secondsjust want to check the providers to see if there's something more we can add here. I think for now, yeah, I would recommend still rendering the children
1:39:391 hour, 39 minutes, 39 secondsonly in the authenticated state simply because we're really this is the kind of app
1:39:481 hour, 39 minutes, 48 secondsthat shouldn't even allow the user to not be authenticated. Right? This is a
1:39:551 hour, 39 minutes, 55 secondscloud-based IDE. The only thing that unauthenticated users should see in this kind of app is the landing page and the
1:40:031 hour, 40 minutes, 3 secondslogin screen. That's it. Everything else is authenticated, right? The list to see your projects authenticated. The file
1:40:111 hour, 40 minutes, 11 secondsexplorer authenticated, the actual code authenticated, right? So, because of that, we're just going to render the
1:40:171 hour, 40 minutes, 17 secondsentire project within the authenticated composition right here. So to wrap that up, I actually want to create a few
1:40:261 hour, 40 minutes, 26 secondscomponents here just to make our app feel nicer and to kind of start building our features folder. So this will be our
1:40:361 hour, 40 minutes, 36 secondsfolder structure. I'm going to use the features and I will create an out feature here and each of my feature will
1:40:431 hour, 40 minutes, 43 secondshave a component. So let's add the components here and let's create unauthenticated view.tsx.
1:40:541 hour, 40 minutes, 54 secondsSo now I'm going to go ahead and import an icon from lucid react. I'm going to import a component called item from our
1:41:031 hour, 41 minutes, 3 secondscomponents UI item which we have added through chats UI. So this has been added in the first chapter.
1:41:111 hour, 41 minutes, 11 secondsAnd then I'm going to export const unauthenticated view.
1:41:181 hour, 41 minutes, 18 secondsThis will not accept any props. It's going to be purely a presentational component. And we're going to start by creating a container.
1:41:271 hour, 41 minutes, 27 secondsThis container will have flex items center justify center height of screen and bg of background. Then an inner
1:41:361 hour, 41 minutes, 36 secondscontainer which will limit to how wide this can be. So we give it full width but we limit it to maximum width of
1:41:431 hour, 41 minutes, 43 secondslarge which is 512 pixels and we give it a background of muted. And then we're going to do a composition using those
1:41:521 hour, 41 minutes, 52 secondselements above. So we're using the item component with a variant of outline.
1:41:561 hour, 41 minutes, 56 secondsInside we render the item media with a variant of icon and we render the icon inside and then inside of that we start
1:42:041 hour, 42 minutes, 4 secondsrendering the item content. Each item content should have an item title. So we add unauthorized access here. And below
1:42:121 hour, 42 minutes, 12 secondsthat we add item description. You're not authorized to access this resource.
1:42:171 hour, 42 minutes, 17 secondsBeautiful. Let's go ahead and go back inside of the providers here. And in the unauthenticated state, let's add unauthenticated view.
1:42:271 hour, 42 minutes, 27 secondsWe can do that by importing from features out components. So I'm going to move this above the theme provider like that. And let's remove the import for
1:42:361 hour, 42 minutes, 36 secondsthese two. So now if you go ahead and if you actually log out, you should see this unauthorized access.
1:42:451 hour, 42 minutes, 45 secondsYou are not authorized to access this resource. Great. Now let's go ahead and while we're here, let's create besides
1:42:531 hour, 42 minutes, 53 secondsunauthenticated view, let's create an outloading view. So this will be even simpler. So components
1:43:011 hour, 43 minutes, 1 secondoutloading view.dsx DSX and we're just going to import spinner from components UI spinner. We're going
1:43:101 hour, 43 minutes, 10 secondsto export outloading view component and we're very simply going to return a div with flex items center justify
1:43:191 hour, 43 minutes, 19 secondscenter height of screen bg background and inside a spinner with size six and text ring. The spinner again is just a
1:43:281 hour, 43 minutes, 28 secondsvery simple chaten UI component. You can find it in source components UI spinner.
1:43:331 hour, 43 minutes, 33 secondsAnd you can see it's practically just a loader icon which animates. Great. Now let's go ahead and render that here. So
1:43:401 hour, 43 minutes, 40 secondsoutloading view which you can import from features out components out loading view. And you can
1:43:481 hour, 43 minutes, 48 secondsalready see how this happens right. It's loading and then it shows unauthorized access. Now if you want to you can
1:43:561 hour, 43 minutes, 56 secondsextend uh this unauthenticated view with I believe it's called um item action
1:44:041 hour, 44 minutes, 4 seconds[clears throat]
1:44:081 hour, 44 minutes, 8 secondsand maybe in here let me just check how uh we add this. So yeah inside of item
1:44:151 hour, 44 minutes, 15 secondsactions I think you can add sign in button from clerk next.js JS and inside you can import a button which should say
1:44:231 hour, 44 minutes, 23 secondssign in and I think you can also style this to give it a variant of outline and
1:44:301 hour, 44 minutes, 30 secondsa size of small. So you should have signin button imported from clerk next.js and button from components UI
1:44:381 hour, 44 minutes, 38 secondsbutton and this should redirect you to the login page. So that is one solution
1:44:451 hour, 44 minutes, 45 secondsyou can have. Another solution is to automatically redirect the user.
1:44:511 hour, 44 minutes, 51 secondsSo for example, inside of s my apologies. Yes, instead of source proxy.ts,
1:44:571 hour, 44 minutes, 57 secondswe can modify the proxy to only allow certain routes. So for now, I'm going to
1:45:061 hour, 45 minutes, 6 secondsdo const is public route create route matcher from clerk next.js server. And
1:45:151 hour, 45 minutes, 15 secondsI'm only going to allow for example forward slap API slingingest and then everything after that because that's one of the scenarios which we want to allow.
1:45:271 hour, 45 minutes, 27 secondsRight? You don't even know what this is yet. We are going to learn that in the next chapter. But for everything else I want to redirect the user away. And then
1:45:361 hour, 45 minutes, 36 secondswhat I can do here is first of all move this above the default export and then
1:45:431 hour, 45 minutes, 43 secondsopen the clerk middleware asynchronous I get access to out and request
1:45:501 hour, 45 minutes, 50 secondsand if not is public route. So if this current request is not a public route I will trigger out.protect protect method.
1:45:581 hour, 45 minutes, 58 secondsAnd what this will do is it will automatically redirect your user whenever they try to access this app if
1:46:061 hour, 46 minutes, 6 secondsthey're logged out. If you prefer that solution, you can use that solution. If you don't, you don't have to. So, whatever you like best, I just want to show you multiple ways of doing things.
1:46:171 hour, 46 minutes, 17 secondsBoth are completely valid. Uh they are basically just different user experience. They don't offer different layers of protection. If you like it
1:46:261 hour, 46 minutes, 26 secondsthis way, that's completely fine. Just keep in mind you will probably want to couple this with some kind of landing page so that users shouldn't even get to
1:46:331 hour, 46 minutes, 33 secondsthis page unless they are redirected from your landing page. And if they do, they will be greeted with a screen like this. You're not authorized to access
1:46:421 hour, 46 minutes, 42 secondsthis resource. So if you want to skip that altogether, you can implement what I did and just automatically redirect them. Or if you want if you like this
1:46:491 hour, 46 minutes, 49 secondsexplicit action of sign in, then you can keep it like this. Great. I think we
1:46:561 hour, 46 minutes, 56 secondsimplemented a lot and it's time to end this chapter. Amazing job. So, let's go ahead and commit all of this. Let's see.
1:47:041 hour, 47 minutes, 4 secondsOur chapter is three database setup. So, I'm just going to shut everything down.
1:47:101 hour, 47 minutes, 10 secondsI will get add get commit chapter 3 database setup. And then I'm going to get checkout-b
1:47:181 hour, 47 minutes, 18 seconds03 database setup. get push origin03 database setup.
1:47:281 hour, 47 minutes, 28 secondsLet's wait a second. There we go. Then let's go ahead and open our new app.
1:47:371 hour, 47 minutes, 37 secondsAnd in here we can open a new pull request. So this time I'm going to click here compare and pull request. And as always we're going to review this code.
1:47:461 hour, 47 minutes, 46 secondsSo let's just create a pull request. And if you've added code rabbit as I did in the previous chapter, you will now get
1:47:531 hour, 47 minutes, 53 secondsan automatic PR review. So let's see what it has to say about our current code.
1:48:001 hour, 48 minutesLet's have a look at the summary by code rabbit. New features create and manage projects with automatic persistence and
1:48:081 hour, 48 minutes, 8 secondsownership tracking. Enhanced authentication flow with dedicated sign-in interface, loading indicators, and access control notifications.
1:48:171 hour, 48 minutes, 17 secondsWe updated the global styling which is referring to the fact that we removed select none and we added backend service integration dependency referring the
1:48:261 hour, 48 minutes, 26 secondsconvex and in here it noticed some issues. So in here it is warning us that we shouldn't use non-null assertion on
1:48:331 hour, 48 minutes, 33 secondsenvironment variables and risk runtime failure and while this is true this type of environment variable allows our app
1:48:431 hour, 48 minutes, 43 secondsto run in the first place. So if we don't have this set up, the app will not even work. So this isn't something that
1:48:511 hour, 48 minutes, 51 secondswill maybe fire sometime so that we have to add an if clause check here. It will literally crash the app. So one way or
1:49:001 hour, 49 minutesanother, we're going to see it fail. So it's not like this will go, you know, hidden from us. So that's the only
1:49:091 hour, 49 minutes, 9 secondsreason it's okay to do it like this here. But yes, usually whenever you work with runtime uh variables, you should do
1:49:181 hour, 49 minutes, 18 secondsan if check if it actually exists and then throw an error. So it prevents the app from running. But this will do the
1:49:251 hour, 49 minutes, 25 secondssame thing either way. So that's why we are okay. In here we are missing a semicolon. So it even notices simple
1:49:331 hour, 49 minutes, 33 secondsthings like this. You probably have a semicolon. You've probably noticed I don't have prettier turned on or any kind of uh format on save. The reason I
1:49:421 hour, 49 minutes, 42 secondsdon't have that is so that you can see every single line of code that I change in my tutorials, right? So I don't want any formatterers to mess with some code
1:49:511 hour, 49 minutes, 51 secondsoutside of the screen recording view. Uh so for you this probably didn't happen.
1:49:561 hour, 49 minutes, 56 secondsIf you have format on save and prettier and slint, you probably have semicolon here. Not a big issue. In here it says
1:50:051 hour, 50 minutes, 5 secondsthat we have a schema mismatch with the projects table. So you can see how well it understands our project. It read the
1:50:131 hour, 50 minutes, 13 secondsschema table and it sees that this sample data does not match that at all.
1:50:201 hour, 50 minutes, 20 secondsAnd in fact this reminded me to remove that file which is exactly what it suggested. And in here it noticed some
1:50:281 hour, 50 minutes, 28 secondsunused imports. another thing for us to resolve in the next chapter. And another
1:50:341 hour, 50 minutes, 34 secondsthing uh we shouldn't hardcode values here, right? We should do something if we do, we should have something
1:50:411 hour, 50 minutes, 41 secondsmeaningful like untitled project, but it noticed that this appears to be a testing or debugging code. So perfectly
1:50:501 hour, 50 minutes, 50 secondsfine for us at the moment. And same advice here to not use nonnull assertion
1:50:571 hour, 50 minutes, 57 secondsoperator. But as I said, if we actually do forget to add this variable, the project won't even start. So this kind
1:51:061 hour, 51 minutes, 6 secondsof that kind of acts like a runtime error in itself. Very good review. Let's go ahead and merge this pull request and
1:51:131 hour, 51 minutes, 13 secondswe are going to fix those issues in the next chapter. Amazing. So we already have three branches here. Actually, yeah, three of them including the main.
1:51:231 hour, 51 minutes, 23 secondsAnd now once we've done that, we should go back here, check out back to the main branch and
1:51:301 hour, 51 minutes, 30 secondsget pull origin main so that we pull those remote changes. There we go. And
1:51:371 hour, 51 minutes, 37 secondsin order to confirm everything is okay, double check you are on your main branch right here. And inside of your graph
1:51:451 hour, 51 minutes, 45 secondscontrol, you can see that the same behavior happens. We checked out to a new branch for 03 and then we merged it
1:51:521 hour, 51 minutes, 52 secondsback to main. Amazing. So, let's go ahead and recap. Uh, we have set up
1:52:001 hour, 52 minutesConvex account in a new project, installed Convex SDK and CLI tools, created table and tested out CRUD operations, and finally configured
1:52:091 hour, 52 minutes, 9 secondsConvex provider with clerk authentication. Amazing job and see you in the next chapter.
Chapter 5: 04 Background Jobs
1:52:151 hour, 52 minutes, 15 secondsIn this chapter, we're going to add background jobs to our project. We're going to start by setting up AI SDK, which will allow us to create some
1:52:241 hour, 52 minutes, 24 secondslongunning tasks, such as querying an AI and getting a response back. Then, we're going to call that AI model through a
1:52:321 hour, 52 minutes, 32 secondsnormal API route, which will serve as our quote unquote blocking example. Then we're going to do the exact same thing,
1:52:411 hour, 52 minutes, 41 secondsbut this time by running it through an ingest background job. And then we're going to compare blocking versus non-blocking.
1:52:491 hour, 52 minutes, 49 secondsSo let's start by adding AIS SDK to our project. I'm going to be using AIS SDK
1:52:561 hour, 52 minutes, 56 secondsversion 6. So in my case, I can go ahead and use at latest because this will be
1:53:031 hour, 53 minutes, 3 secondsversion six and I'm going to immediately show you that. So inside of my package.json, if I search for AI, you can see that my version is 6.0.3.
1:53:141 hour, 53 minutes, 14 secondsIf you want to use the same version as me, you can do this. Though I don't think that these minor versions matter too much. I think that the version six
1:53:231 hour, 53 minutes, 23 secondsis the most important one because between version four, five, and six, there are quite some breaking changes in how you use it. So that's why I'm making
1:53:321 hour, 53 minutes, 32 secondsyou aware of the version that I'm using at the time of making this tutorial. So now let's go ahead and click on documentation here and let's click on
1:53:401 hour, 53 minutes, 40 secondsproviders and models. So this is your choice. You can choose whatever provider you want. I would highly highly highly
1:53:491 hour, 53 minutes, 49 secondssuggest using anthropic providers. They they are by far the best when it comes to agentic coding and you will
1:53:571 hour, 53 minutes, 57 secondsdefinitely feel that in building an app like this which will have to kind of loop itself into tool calling until it
1:54:061 hour, 54 minutes, 6 secondsreaches a certain result and a lot of these other providers and models are not as good as entropic when it comes to
1:54:151 hour, 54 minutes, 15 secondsthat. Same goes for their UI and their generative coding models, right? They are just really really good. So I'm
1:54:231 hour, 54 minutes, 23 secondsgoing to show you two examples. I'm going to show you how to set up AI SDK Google because it's completely free and I'm going to show you how to set up Anthropic because that's what I will be
1:54:311 hour, 54 minutes, 31 secondsusing going through. If you're wondering about the total costs for Enthropic to finish this project, it's going to be
1:54:381 hour, 54 minutes, 38 secondsaround $5 to $10. So nothing too much, but I completely understand if for some of you that is not obtainable for
1:54:451 hour, 54 minutes, 45 secondswhatever reason. So I'm going to start with Google simply because it's free. So let's start with Google generative AI provider. Let's click on npm and let's
1:54:541 hour, 54 minutes, 54 secondsinstall it. Again I'm going to use the latest version simply so I know that
1:55:011 hour, 55 minutes, 1 secondwhatever version gets installed here is compatible with my AI latest version. So
1:55:081 hour, 55 minutes, 8 secondsif I search for AI SDK Google it's 3.0.1. So if you want to, you can do this.
1:55:191 hour, 55 minutes, 19 secondsNow that we have that, we have to go ahead and create a very simple API route that will call this. So I'm going to go
1:55:261 hour, 55 minutes, 26 secondsahead and create an API folder within my app folder here. And then I'm going to
1:55:331 hour, 55 minutes, 33 secondscreate a demo folder and inside of that blocking and inside of the blocking
1:55:401 hour, 55 minutes, 40 secondsfolder route. DS. What we have achieved with this folder structure is the
1:55:481 hour, 55 minutes, 48 secondsfollowing API route. So localhost 3000 API demo blocking.
1:55:551 hour, 55 minutes, 55 secondsAnd if you call a post request to this route right here, we're going to trigger Google's Gemini provider to create something, right? To generate some text.
1:56:081 hour, 56 minutes, 8 secondsSo let's go ahead and export asynchronous function post like this
1:56:161 hour, 56 minutes, 16 secondsand now we have registered this as a post route right so it will return something from here so inside of response right here what I want to do is
1:56:251 hour, 56 minutes, 25 secondsI want to add this so I'm just going to copy it here
1:56:321 hour, 56 minutes, 32 secondsso we can import generate text from AI I package which we've just installed
1:56:411 hour, 56 minutes, 41 secondsand we can import Google from at AI SDK
1:56:491 hour, 56 minutes, 49 secondsGoogle like this and then we can return next response.json you can import or you can just do
1:56:581 hour, 56 minutes, 58 secondsresponse.json and pass in the response like this. So
1:57:051 hour, 57 minutes, 5 secondsthis is how you would implement a normal Gemini call. The problem is we don't have an API key. So this will fail now.
1:57:131 hour, 57 minutes, 13 secondsSo using the link on the screen, you can visit Google AI studio. And in here we can create one free uh API key. So I'm
1:57:201 hour, 57 minutes, 20 secondsgoing to name this Polaris Dev. And let me show you how you can easily create a new project. So Polaris dev create a
1:57:291 hour, 57 minutes, 29 secondsproject. And once that project has been created, you can go ahead and select it.
1:57:351 hour, 57 minutes, 35 secondsThere we go. It is automatically selected. I will call this Polaris-dev. I'm going to click create key.
1:57:431 hour, 57 minutes, 43 secondsAnd [snorts] once we create this key, I'm going to copy it here.
1:57:471 hour, 57 minutes, 47 secondsAnd I think I can add it here. So API key uh or here.
1:57:581 hour, 57 minutes, 58 secondsLet me go ahead and research a bit about how I can directly add. Usually you can do it through the environment variable, but I want to show you how you can
1:58:051 hour, 58 minutes, 5 secondsexactly do it from here. All right. So I think that the way you need to do this is by using create Google generative AI
1:58:141 hour, 58 minutes, 14 secondsand then defining your own Google like this API key and then add it here. So let me
1:58:231 hour, 58 minutes, 23 secondscopy this again and let's add that right here.
1:58:281 hour, 58 minutes, 28 secondsAnd then we're going to use Google like this. You can of course add this to your dot environment. I'm going to show you how you can do that in a moment. But
1:58:351 hour, 58 minutes, 35 secondslet's try it directly uh with this. So uh let's go ahead and try this out. And I'm going to create a very simple UI so
1:58:431 hour, 58 minutes, 43 secondswe can test this. So instead of the app folder, I'm going to create a demo folder and then page.tsx inside. What this will do is this will
1:58:521 hour, 58 minutes, 52 secondscreate a page that we can access on the localhost 3000 slashdemo. So let's start by adding use client here. So we can do
1:59:001 hour, 59 minutessome interactivity. Export default function demo page.
1:59:081 hour, 59 minutes, 8 secondsLet's go ahead and let's return a div.
1:59:111 hour, 59 minutes, 11 secondsLet's give this div a class name. Let's do padding uh let's do bigger padding 8
1:59:201 hour, 59 minutes, 20 secondsspace x4 and let's call button from components UI button and let's give it a label of
1:59:291 hour, 59 minutes, 29 secondsblocking and then let's go ahead and implement a very simple handle blocking asynchronous function
1:59:381 hour, 59 minutes, 38 secondswhich await fetch API demo blocking with a post method. So this is the exact API route which we have created. You can see the cascading here. API demo blocking.
1:59:491 hour, 59 minutes, 49 secondsAPI demo blocking. As long as it starts with the app folder and goes into the API, you've done it correctly. And then let's just go ahead and give this an
1:59:581 hour, 59 minutes, 58 secondsclick here and paste it. Right. There we go.
2:00:052 hours, 5 secondsSo I'm going to go ahead and try it now.
2:00:072 hours, 7 secondsAnd let's just make sure we are running npm rundev.
2:00:122 hours, 12 secondsAnd here's the thing. So I actually tried doing this chapter a few times already. And every time I tried my
2:00:202 hours, 20 secondsGoogle provider failed. So that's why I told you if possible use something other than a Google provider. It's just not
2:00:282 hours, 28 secondsreliable in its current state. I'm going to try one more time. We're going to see maybe this will be the successful one.
2:00:342 hours, 34 secondsUh let's see. It's doing something. I'm not sure if it's failing or not. As you can see, it is definitely hitting that forward slashdemo.
2:00:452 hours, 45 secondsAnd there we go. This time we managed to do it. And here it is. Here's a delicious and hearty vegetarian lasagna
2:00:532 hours, 53 secondsrecipe. So basically we just had an API call do a vegetarian lasagna recipe for four
2:01:022 hours, 1 minute, 2 secondspeople using Gemini 2.5 flesh and a free API key. Yeah. So for some reason uh many times I've tried this. It just
2:01:112 hours, 1 minute, 11 secondsdidn't work for me. I don't know why it keeps saying random errors. Uh like my quotota was uh finished even though I
2:01:202 hours, 1 minute, 20 secondsonly have one uh request to Gemini in a whole month.
2:01:262 hours, 1 minute, 26 secondsSo I am not sure how that happened. Then it kept saying that my API key was invalid. So I don't really know. And let me show you how you can add it to your
2:01:342 hours, 1 minute, 34 secondsenvironment file. So if you don't want to use it like this, all of that is actually documented here. So you can see that when you scroll down here,
2:01:442 hours, 1 minute, 44 secondsyou can store it inside of Google generative AI API key. So inside of your environment.local, add a hashtag AI, add it here.
2:01:562 hours, 1 minute, 56 secondsAnd then you can just add it like this. There we go.
2:02:052 hours, 2 minutes, 5 secondsAnd then you no longer have to really do this. You should then be able to just import Google and use it directly without having to define it.
2:02:142 hours, 2 minutes, 14 secondsLet's try if it still works. Maybe the problem is in that environment file. Yeah, looks like it works now. Great.
2:02:232 hours, 2 minutes, 23 secondsSo, you can see that uh our first example is now working. Great.
2:02:302 hours, 2 minutes, 30 secondsNow, what we have to do is slightly modify our page.tsx the sx into showing that blocking state because so far we've
2:02:382 hours, 2 minutes, 38 secondsonly seen it in the network but I don't think we visually understand what's actually happening. So because of that I'm just going to implement a super
2:02:462 hours, 2 minutes, 46 secondssimple use state here which will keep track of loading.
2:02:522 hours, 2 minutes, 52 secondsSo loading and set loading. Then I'm going to set loading to true when we start doing it and set it to false when we finish.
2:03:022 hours, 3 minutes, 2 secondsAnd I'm going to go ahead and make this button disabled while it's loading.
2:03:082 hours, 3 minutes, 8 secondsAnd if it's loading, I'm going to show loading. Otherwise, I will show blocking like this. So hopefully this will give
2:03:172 hours, 3 minutes, 17 secondsus a better understanding of what's going on right now. So when I click on blocking, you can see how it takes 1 2 3 4 5 6 7 Oops, I refreshed.
2:03:302 hours, 3 minutes, 30 secondsDo you see the point? The point is that when it comes to long running tasks like this, you cannot let your user wait for
2:03:392 hours, 3 minutes, 39 seconds10, 20, 30 seconds because late this is this is now a super simple AI query, but later it's going to be a super complicated one and it's going to last
2:03:462 hours, 3 minutes, 46 secondsfor maybe up to a minute, right? If we are cascading an entire application so you can't let your user hang like this,
2:03:542 hours, 3 minutes, 54 secondsespecially with the fact that they can accidentally refresh, they can go back and all of those things, right? this takes too much time and it's not the problem about it taking too much time.
2:04:032 hours, 4 minutes, 3 secondsis the problem that we are handling this through a normal blocking method.
2:04:082 hours, 4 minutes, 8 secondsWhereas what we should be doing is simply using an API route to trigger a background job and then immediately tell
2:04:162 hours, 4 minutes, 16 secondsto the user, hey, we triggered the background job. You are free to do whatever you want. We are going to alert you when it's finished. You can go out
2:04:252 hours, 4 minutes, 25 secondsand take a walk. You can shut down your laptop. Whatever you want to do, it's going to be ready when you come back.
2:04:312 hours, 4 minutes, 31 secondsThat is what we want to do. So let's go ahead and learn how to implement that using the link on the screen. You can
2:04:402 hours, 4 minutes, 40 secondsvisit ingest. And in here, let's go ahead and go through their documentation. One great thing about
2:04:472 hours, 4 minutes, 47 secondsingest is that they offer completely accountless setup. So you can just follow Nex.js quickart without ever
2:04:542 hours, 4 minutes, 54 secondscreating an account until it comes to deployment, of course. So for now, let's just follow Next.js GS app router solution here. First things first we're
2:05:022 hours, 5 minutes, 2 secondsgoing to do is we're going to install ingest. So for now I'm going to shut down the app and just do npm install inest and then I'm going to show you the exact version of ingest that I'm using
2:05:112 hours, 5 minutes, 11 secondssince this is an important package. So I'm going to go inside of package json search for ingest and let me give it a moment to install.
2:05:222 hours, 5 minutes, 22 secondsHere we go. So my inest version is 3.48.1.
2:05:272 hours, 5 minutes, 27 secondsSo if you wanted to you could have used this. Great.
2:05:312 hours, 5 minutes, 31 secondsThat is step one finished. Now what we have to do is we have to run the inest developer server which is basically a
2:05:392 hours, 5 minutes, 39 secondsfast in-memory version of ingest where you can quickly send and view events as function runs. So let's go ahead and
2:05:462 hours, 5 minutes, 46 secondscopy this and let's run it here. So npx- ignore scripts false ninja cli at latest
2:05:542 hours, 5 minutes, 54 secondsdev. It will be best to find this on your own so you don't have to uh read off my screen here. And it offers to
2:06:022 hours, 6 minutes, 2 secondsinstall a new package. So feel free to say yes here. And what this will do is it will spin up like a little local instance of ingest which you can visit on localhost 8288.
2:06:132 hours, 6 minutes, 13 secondsSo feel free to visit that. And in here you will basically find this inest dashboard. Right now there is nothing to
2:06:202 hours, 6 minutes, 20 secondsbe found. There are no applications which are connected and there are no functions. There are no runs, nothing. So that's what we're going to do next.
2:06:262 hours, 6 minutes, 26 secondsWe're going to connect inest to our project.
2:06:302 hours, 6 minutes, 30 secondsSo in order to do that, we need to create source inestclient.ts.
2:06:362 hours, 6 minutes, 36 secondsI'm going to go ahead inside of my code editor here. Source. And then I'm going to do ingest right here.
2:06:452 hours, 6 minutes, 45 secondsAnd client.ds.
2:06:472 hours, 6 minutes, 47 secondsThere we go. I'm going to paste this inside. So we are importing the ingest from ingest package and I'm going to call this Polaris.
2:06:562 hours, 6 minutes, 56 secondsThere we go.
2:06:582 hours, 6 minutes, 58 secondsOnce we have that, let's go ahead and register this in an API route because just by adding this, it's not enough.
2:07:062 hours, 7 minutes, 6 secondsAnd you also need to have your app running at the same time. And what you will see now is that this inest is
2:07:142 hours, 7 minutes, 14 secondstrying to hit a bunch of end points for ingest. So it's trying to figure out what our project is. It's trying in
2:07:222 hours, 7 minutes, 22 secondsNetlify functions, Redwood functions, a bunch of things. This is where we are going to register our and once it finds
2:07:302 hours, 7 minutes, 30 secondsthat that's the only endpoint it's going to hit. So let's go ahead and go inside of app folder, our API folder. Let's
2:07:392 hours, 7 minutes, 39 secondscreate a new folder inside called ingest like that. And then inside route.ts.
2:07:472 hours, 7 minutes, 47 secondsSo I'm going to go ahead and just copy the contents from here and paste them in here. We import serve from inest next.
2:07:562 hours, 7 minutes, 56 secondsAnd then we import from our inest client. The client you can use a shorthand operator alias for this like that.
2:08:072 hours, 8 minutes, 7 secondsSo this is basically going to source folder inest client. That's
2:08:142 hours, 8 minutes, 14 secondswhat this is. And in here we export get, post, and put. Save that. And now when you scroll down, you should see success
2:08:232 hours, 8 minutes, 23 secondsmessages here. It finally managed to find our app. And if you go inside of the ingest server here and go inside of
2:08:312 hours, 8 minutes, 31 secondsapps here, you can see it started to autodetect it. So it knows it's Nex.js.
2:08:372 hours, 8 minutes, 37 secondsBut we still haven't added any functions here. So it's still not exactly usable.
2:08:412 hours, 8 minutes, 41 secondsSo we now have to create our very first function. So that's what I'm going to do.
2:08:472 hours, 8 minutes, 47 secondsSo inside of our source inest, I will create functions.
2:08:582 hours, 8 minutes, 58 secondsDS and I will paste this here. So we are importing the ingest client and we are exporting a constant called hello world.
2:09:072 hours, 9 minutes, 7 secondsAnd inside of here, we are simply creating a function with an ID of hello world and an event of test forward/hello.world.
2:09:152 hours, 9 minutes, 15 secondsThis is what will be used to trigger the event. And we're going to demonstrate triggering in a moment. What this will do is it will sleep for 1 second and
2:09:242 hours, 9 minutes, 24 secondsthen it's going to return back a message. One way we can immediately test whether this works or not is by going
2:09:322 hours, 9 minutes, 32 secondsinside of the inest server. So let's go ahead and let's find our functions here.
2:09:412 hours, 9 minutes, 41 secondsAnd if it's not found, you could uh recsynchronize it by
2:09:482 hours, 9 minutes, 48 secondsrerunning this. So npx ignore scripts and maybe even npm rundev here to make sure everything works fine.
2:09:582 hours, 9 minutes, 58 secondsOh, that's not it. That's not all we have to do. My apologies. Yes, we now have to add that hello world function to
2:10:042 hours, 10 minutes, 4 secondsour uh route.ts. My apologies. So, let's go inside of app folder API inest
2:10:112 hours, 10 minutes, 11 secondsroute.ts and let's add hello world. There we go. From inest functions.
2:10:192 hours, 10 minutes, 19 secondsAnd now inside of your inest server, there we go. One function found. And when you click on functions, you can see it right
2:10:262 hours, 10 minutes, 26 secondshere. What you can do now is you can invoke it here. So, I'm going to go ahead and pass in email here
2:10:342 hours, 10 minutes, 34 secondsand I'm going to use business@codewithonia.com.
2:10:392 hours, 10 minutes, 39 secondsIt really doesn't matter. Let's just invoke a function. And what this is going to do is it's going to run a background job. So, what happened was
2:10:472 hours, 10 minutes, 47 secondspretty quick, so you don't really notice the effect of it, right? But it actually run a step called wait a moment in which
2:10:562 hours, 10 minutes, 56 secondsit waited for 1 second and then it simply returned a message hello and then
2:11:022 hours, 11 minutes, 2 secondsthe data it rece it received my email right so you can kind of already guess where we are going with this but now
2:11:112 hours, 11 minutes, 11 secondswe're going to kind of actualize it right so we're going to go ahead and go inside of ingest functions
2:11:192 hours, 11 minutes, 19 secondsds s and we're going to create a completely new one. Instead of hello world, let's do demo generate
2:11:292 hours, 11 minutes, 29 secondsand instead of this ID, it will be demo generate, this will be demo forward
2:11:362 hours, 11 minutes, 36 secondsslash generate like that. And then I'm going to go ahead and run this instead of await step.run
2:11:432 hours, 11 minutes, 43 secondsgenerate-ext like this.
2:11:472 hours, 11 minutes, 47 secondsLet's go ahead and call this asynchronous method and let's do await generate text which we can import from
2:11:542 hours, 11 minutes, 54 secondsAI. I'm going to call the Google model from AI SDK Gemini 2.5
2:12:032 hours, 12 minutes, 3 secondsflash or 2.0 Flash. Let me go ahead and see what did I use in my blogging example.
2:12:112 hours, 12 minutes, 11 secondsWell, I can just copy this actually.
2:12:172 hours, 12 minutes, 17 secondsSo, I'm just going to do this. There we go.
2:12:212 hours, 12 minutes, 21 secondsAnd in fact, I'm just going to return the output here. So, this way, I don't really need the event at all.
2:12:302 hours, 12 minutes, 30 secondsAnd let's try that out now. I just have to change inside of my source app API inest route.ts demo generate.
2:12:432 hours, 12 minutes, 43 secondsLet's refresh this and let's go back to our ingest server. Let's go inside of functions. Let's click invoke. The data really doesn't matter. It can be empty
2:12:512 hours, 12 minutes, 51 secondsand click invoke function. [snorts] And what you see now is the exact same thing happening. It's generating a haiku or
2:12:592 hours, 12 minutes, 59 secondsit's generating a lasagna recipe for four people but through a background job. And this is now nonblocking UI.
2:13:082 hours, 13 minutes, 8 secondsRight? So you can now see exactly what it did right here. There we go. This is a vegetarian lasagna. There we go. And
2:13:152 hours, 13 minutes, 15 secondsnow let's go ahead and plug that into our app right here. So you can see how differently it behaves. So I'm going to
2:13:232 hours, 13 minutes, 23 secondsgo inside of app folder API inside of demo. I'm going to copy the blocking folder and paste it here again.
2:13:322 hours, 13 minutes, 32 secondsAnd I'm going to rename it to unblocking or let's call it uh background like this.
2:13:412 hours, 13 minutes, 41 secondsIf you have this opened, this is just React cache which sometimes gets confused when you rename folders. You can just save that and close it and
2:13:492 hours, 13 minutes, 49 secondsclose the next folder. Let's go back inside of our background route here. And what I'm going to do inside of here is a
2:13:582 hours, 13 minutes, 58 secondslittle bit different. So instead of directly calling this, I'm just going to do awaiting injust from inestclient send
2:14:102 hours, 14 minutes, 10 secondsname demo forward slashgenerate with the data
2:14:172 hours, 14 minutes, 17 secondsof just an empty object and this will be status started and then let's remove and this is now
2:14:262 hours, 14 minutes, 26 secondsaccessible on this API route.
2:14:302 hours, 14 minutes, 30 secondsThere we go. Now that we have that, let's go ahead inside of our app folder demo page.tsx.
2:14:392 hours, 14 minutes, 39 secondsAnd in here, I'm now going to create a handle background function like this.
2:14:452 hours, 14 minutes, 45 secondsHandle background, which again will call set loading here, but it's going to call the background API route. And then I'm
2:14:542 hours, 14 minutes, 54 secondsgoing to duplicate this button right here.
2:14:582 hours, 14 minutes, 58 secondsAnd let's actually uh okay yeah this will be background and
2:15:052 hours, 15 minutes, 5 secondsthis will call handle background so let's look at the differences now let's repeat our knowledge right our
2:15:132 hours, 15 minutes, 13 secondsnormal API routes uh okay yeah this is not a good example so I'm just going to
2:15:202 hours, 15 minutes, 20 secondshave a very simple solution not the prettiest but it works
2:15:282 hours, 15 minutes, 28 secondshave them use different loading attributes. Okay, so when you use a normal blocking one,
2:15:352 hours, 15 minutes, 35 secondsyou can see how long it takes. This is how long your user is blocked, right?
2:15:412 hours, 15 minutes, 41 secondsYour user cannot do anything right now because we have blocked the entire UI and we are waiting until AI finishes
2:15:482 hours, 15 minutes, 48 secondsresponding and finally it responded and it unblocked the user. User can now do something with that output. Whereas with
2:15:562 hours, 15 minutes, 56 secondsa background job, you can see that immediately it finished and it just starts running the job in the
2:16:032 hours, 16 minutes, 3 secondsbackground. So it's still not done. It's still creating the recipe. But the user is free to initialize another one.
2:16:112 hours, 16 minutes, 11 secondsRight? There we go. I immediately have another one running or I can do, you know, three of them at once. All of them
2:16:182 hours, 16 minutes, 18 secondswill execute in their due time. This is the power of background jobs. And this is just scratching the surface because
2:16:252 hours, 16 minutes, 25 secondslater Inest will have something that they call their agent kit. And their
2:16:342 hours, 16 minutes, 34 secondsagent kit is honestly amazing. And we're going to use it to orchestrate AI agents into creating loops which will call
2:16:432 hours, 16 minutes, 43 secondstools. And that will basically create the agent that can create something. We are going to create an entire network of
2:16:522 hours, 16 minutes, 52 secondsagents which will be able to call each other, communicate with each other and in the end create an actual Nex.js
2:17:012 hours, 17 minutes, 1 secondproject or whatever user describes in the prompt as you saw in the demo.
2:17:072 hours, 17 minutes, 7 secondsRight? So that's the power of ingest and the power of background jobs. You can see how quickly this is finished as
2:17:142 hours, 17 minutes, 14 secondsopposed to this. Don't get me wrong, the speed is the same. It's just a matter of how you handle this process in blocking
2:17:232 hours, 17 minutes, 23 secondsversus non-blocking way. So that's the power of background jobs. That's what I wanted to to demonstrate, right? We are
2:17:312 hours, 17 minutes, 31 secondsnow comparing blocking versus non-blocking. Great. So uh as I said, I also told you I will show you how to set
2:17:402 hours, 17 minutes, 40 secondsup clawed SDK. So uh let me go ahead and go through that to end the chapter. Uh I
2:17:472 hours, 17 minutes, 47 secondswould recommend you know doing this even if you don't plan on using entropics simply because it is a much better model and it will unlock a lot of new
2:17:552 hours, 17 minutes, 55 secondspossibilities for you. In fact, Google Gemini actually had problems and complete unability to call tools in the past. I think that's changed now, right?
2:18:062 hours, 18 minutes, 6 secondsBut you can see just how advanced these anthropic models are and why I prefer them so much. So, I'm just going to go ahead and do let me just expand my terminals here.
2:18:192 hours, 18 minutes, 19 secondsnpm install AIS SDK Antropic. Then I'm going to show you the version.
2:18:292 hours, 18 minutes, 29 secondsSo, AI SDK Antropic 3.0.1. I believe all providers are on the same version.
2:18:362 hours, 18 minutes, 36 secondsGreat. And then you can see that inside of here they basically explain how you can do the exact same thing. And your
2:18:452 hours, 18 minutes, 45 secondsAPI key should be stored inside of anthropic API key. So I suggest you find this in the documentation so you don't just blindly trust me if they change it.
2:18:542 hours, 18 minutes, 54 secondsSo anthropic API key.
2:18:582 hours, 18 minutes, 58 secondsHow do you create uh an anthropic API key? Well, by using anthropic console.
2:19:032 hours, 19 minutes, 3 secondsYou can use the link on the screen. uh I added $5 to my account. Uh I think in entire like development of this project
2:19:112 hours, 19 minutes, 11 secondsand like extensive testing I spent a maximum of $15 and we won't be doing as much testing in
2:19:192 hours, 19 minutes, 19 secondsthis app. So I think you should be completely fine with with $5 to $10. But again, I completely understand if that's not possible for you. That's why I
2:19:272 hours, 19 minutes, 27 secondsshowed you first how to do it with a free API key. So I'm going to go ahead and call this Polaris dev. You can, of course, choose a proper workspace or
2:19:362 hours, 19 minutes, 36 secondswhatever, but I'm just going to use the default one. And there it is. API key. And I'm just going to paste it here.
2:19:442 hours, 19 minutes, 44 secondsThere we go. And then I'm going to go ahead back here. And I'm going to scroll down until I can find the basic generate
2:19:522 hours, 19 minutes, 52 secondstext. Here it is. So I'm just going to replace both my blocking and background generate
2:20:012 hours, 20 minutes, 1 secondtext to use the anthropic model now not from inest from anthropic.
2:20:122 hours, 20 minutes, 12 secondsThere we go.
2:20:152 hours, 20 minutes, 15 secondsAnd I'm going to copy this and [snorts] I'm going to go inside of my demo functions.dts.
2:20:252 hours, 20 minutes, 25 secondsThat's the file. And in here I'm just going to replace this generate text to use anthropic.
2:20:352 hours, 20 minutes, 35 secondsThere we go. So both my source inest functions.ts and my app folder API demo blocking route.ts are now modified to use claude.
2:20:452 hours, 20 minutes, 45 secondsHaiku and I have added my enthropic API key. So let's just give it a shot to see
2:20:522 hours, 20 minutes, 52 secondsif it's working or if something wrong is happening. So I think I'm seeing no
2:21:002 hours, 21 minuteserrors here. There we go. So both of this seems to be working just fine. Here it is.
2:21:062 hours, 21 minutes, 6 secondsLet's see. Here is a vegetarian lasagna recipe that serves four people. You can see the difference in their outputs. And in fact, I think somewhere here you should be able to see. There we go.
2:21:152 hours, 21 minutes, 15 secondsProvider metadata. So this one used Anthropic. Perfect. So it's that easy to actually change providers. Uh you can of
2:21:232 hours, 21 minutes, 23 secondscourse choose whatever provider you want. If you have an existing API key, you know, for OpenAI, you can definitely use that. That is also a great one. I just personally prefer Antropic.
2:21:322 hours, 21 minutes, 32 secondsWhenever I work with this kind of projects, Anthropic provides the best results. Uh I believe that's all we
2:21:392 hours, 21 minutes, 39 secondswanted to do for this chapter. So let's go ahead and let's merge these changes.
2:21:462 hours, 21 minutes, 46 secondsFirst things first, let's see all the changes that we actually have. So we confirm we are on the same page. So I have eight changes. Two of them are package lock and package JSON. Then I added some routes for a background demo.
2:21:582 hours, 21 minutes, 58 secondsFor a blocking demo, the route which uh registers inest page where we have the UI for our blocking and background,
2:22:072 hours, 22 minutes, 7 secondsright? client which is just an injust singleton and functions where we actually write the background jobs. So
2:22:162 hours, 22 minutes, 16 secondsI'm going to go ahead and shut down all of my apps for now and I will simply do get add dot get
2:22:242 hours, 22 minutes, 24 secondscommit. This will be 04 right background jobs. And then I'm going to do get
2:22:332 hours, 22 minutes, 33 secondscheckout B04 background jobs. And then get push
2:22:402 hours, 22 minutes, 40 secondsorigin 04 background jobs.
2:22:452 hours, 22 minutes, 45 secondsAnd then we're going to go ahead and review this pull request. Perfect.
2:22:522 hours, 22 minutes, 52 secondsYou can see how I have switched my branch even in the visual part here. Now let's open GitHub and open a pull request.
2:23:002 hours, 23 minutesSo as usual here on the top I have a new branch. So I'm going to go ahead and open it and create a pull request. And let's see code rabbit's summary.
2:23:122 hours, 23 minutes, 12 secondsLet's read the summary by code rabbit.
2:23:152 hours, 23 minutes, 15 secondsNew features. We added a new demo page with interactive examples comparing blocking and background operations. We
2:23:232 hours, 23 minutes, 23 secondsimplemented a synchronous API endpoint for immediate text generation requests, the blocking one. And we implemented an
2:23:302 hours, 23 minutes, 30 secondsasynchronous API endpoint for quering background tasks. We also added a backend infrastructure to process and
2:23:372 hours, 23 minutes, 37 secondsmanage cued operations inest. So let's take a look at the comments. Most of the comments are due to the fact that this
2:23:452 hours, 23 minutes, 45 secondsis just initial demo code. So we didn't handle errors. We didn't handle retries.
2:23:522 hours, 23 minutes, 52 secondsAbsolutely nothing. Right? You can see that we always returned here. Even though this can technically
2:24:002 hours, 24 minutesfail as long as you can aait something, it can fail. Right? So it's those kind of things that we should improve later on. But since most of these will
2:24:082 hours, 24 minutes, 8 secondsactually be deleted later, it doesn't matter. Right? Otherwise, obviously all very valid concerns here. Even the invalid comments, it noticed that too.
2:24:202 hours, 24 minutes, 20 secondsSame thing here. So, some improvements we should do, but this is just for demo.
2:24:242 hours, 24 minutes, 24 secondsYou can see by the name, right? Loading too. That's not the industry standard when it comes to naming. And yes, in here it actually warns us that this
2:24:332 hours, 24 minutes, 33 secondswouldn't work in production, which is true. There is a separate process of enabling injust in production. Luckily, Versell offers one-click setup for that.
2:24:432 hours, 24 minutes, 43 secondsSo, we will worry about that when the deployment step comes. Amazing. Other than that, let's go ahead and merge this pull request.
2:24:522 hours, 24 minutes, 52 secondsAs always, I'm not going to delete my branch. So, I have a clear history of all of my chapters. You can see that I can now go back to anything I want.
2:25:022 hours, 25 minutes, 2 secondsGreat. So, let's go back to my main branch and get pull origin main. So I have pulled those remote changes we just
2:25:112 hours, 25 minutes, 11 secondsmerged. And I always like to confirm that everything is fine by going inside
2:25:172 hours, 25 minutes, 17 secondsof here graph and just confirming that the same behavior is present. We checked out to-do 04 and then we merge that back
2:25:272 hours, 25 minutes, 27 secondsinto main. Amazing. So I believe that marks the end of this chapter. We've set up AI SDK, created a blocking API route,
2:25:362 hours, 25 minutes, 36 secondsand then we did the same thing with a cued background job. And finally, we compared blocking versus non-blocking
2:25:442 hours, 25 minutes, 44 secondsand its benefits. And I hope that I explained why we need background jobs, especially in apps like this. Amazing,
2:25:522 hours, 25 minutes, 52 secondsamazing job. And see you in the next chapter.
Chapter 6: 05 Firecrawl AI
2:25:562 hours, 25 minutes, 56 secondsIn this chapter, we're going to learn how to add firecroll AI to our project.
2:26:022 hours, 26 minutes, 2 secondsAnd why do we even need it? Well, AI models have something called a knowledge cutff. That means that from the moment
2:26:112 hours, 26 minutes, 11 secondstheir knowledge has been cut off or up to the point they have been trained, they probably don't know about anything
2:26:192 hours, 26 minutes, 19 secondshappening after that. That would include, for example, Nex.js 15, Nex.js
2:26:252 hours, 26 minutes, 25 secondsJS 16, React 19, the newest React use hook, or maybe the new file name for a
2:26:352 hours, 26 minutes, 35 secondsmiddleware inside of newest version of Nex.js. Those are all real problems when working with AI. So the goal of this
2:26:442 hours, 26 minutes, 44 secondschapter is to enable our AI models to improve their knowledge and go even
2:26:512 hours, 26 minutes, 51 secondsbeyond their cutoff date by giving them the ability to read anything on the web
2:26:582 hours, 26 minutes, 58 secondsusing fire crawl AI. In fact, we already encountered this pattern very early on.
2:27:062 hours, 27 minutes, 6 secondsSo I'm going to give you a quick reminder. In the very first pull request that we've created, we noticed this
2:27:132 hours, 27 minutes, 13 secondspattern happen, right? We had this comment by code rabbit which basically warned us, hey, you are using an invalid
2:27:212 hours, 27 minutes, 21 secondsfile name. It's not called proxy. It should be called middleware.ts.
2:27:262 hours, 27 minutes, 26 secondsAnd I have corrected it and said that's not true. Here's the URL to the newest documentation. And it agreed with me because the new name is indeed proxy.
2:27:372 hours, 27 minutes, 37 secondsYes. So this is a current issue of working with AI models. All of them have a knowledge cut off date. They can do
2:27:472 hours, 27 minutes, 47 secondstheir best to be up to date with various methods and this is one of them allowing users to teach them new things. So there
2:27:562 hours, 27 minutes, 56 secondsmust be some way this amazing tool code rabbit somehow read this URL. And while
2:28:032 hours, 28 minutes, 3 secondsI do not know exactly how they do it, I know how we are going to do it using firecrawl which will allow us to turn
2:28:122 hours, 28 minutes, 12 secondswebsites into LLM ready data. And in fact, I'm going to demonstrate exactly
2:28:192 hours, 28 minutes, 19 secondshow that works right here. This is the finished project, right? This is what you will have at the end of this tutorial. And let's see how that works.
2:28:292 hours, 28 minutes, 29 secondsSo I'm going to do the following. What is the current file name of the middleware file in
2:28:372 hours, 28 minutes, 37 secondsnextJS and let's see the answer that it gave
2:28:462 hours, 28 minutes, 46 secondsus. So first of all it told me this is not a Nex.js project. Yes, that is because this AI tool has access to my
2:28:542 hours, 28 minutes, 54 secondsentire app and this is indeed a Vit project, not a Nex.js one. But still it
2:29:012 hours, 29 minutes, 1 secondanswered and it gave me the wrong information. So it says in Nex.js projects the middleware file is typically named middleware.ds.
2:29:112 hours, 29 minutes, 11 secondsThat is incorrect. So what I'm going to do is I'm going to copy the URL which demonstrates the new proxy file right
2:29:202 hours, 29 minutes, 20 secondshere and I'm going to tell it that is incorrect. That is not correct. read this and tell me the new name.
2:29:312 hours, 29 minutes, 31 secondsSo let's see if it will be able to do that.
2:29:352 hours, 29 minutes, 35 secondsAnd here we have the answer. You are absolutely right. So the same as code rabbit, right? According to Nex.js
2:29:422 hours, 29 minutes, 42 secondsdocumentation, starting with Nex.js16, the middleware file has been renamed to middleware.t from middleware to proxy.
2:29:522 hours, 29 minutes, 52 secondsThe documentation states starting with Nex.js16 JS16 middleware is now called proxy to better reflect its purpose. So this is what we will be able to achieve.
2:30:032 hours, 30 minutes, 3 secondsBy default, you're not able to do this just like that. You need a tool like fire crawl to help you achieve this
2:30:112 hours, 30 minutes, 11 secondseffect. So that's what we're going to be focusing on. So using the link on the screen, go ahead and create an account with firecrawl.
2:30:222 hours, 30 minutes, 22 secondsOnce you get to the plan page, feel free to select their free plan. It will be more than enough for this project. And
2:30:292 hours, 30 minutes, 29 secondsin fact, you will get even more credits than you think. So, just go ahead and click get started on the free plan. It's more than enough. And then what I want
2:30:382 hours, 30 minutes, 38 secondsyou to do is go ahead and click on your account here. And let's go inside of our account settings right here. Actually, let's click on the settings here.
2:30:492 hours, 30 minutes, 49 secondsAnd let's go ahead and click on billing. And in here you will find apply coupon.
2:30:562 hours, 30 minutes, 56 secondsAnd in here go ahead and enter Antonio coupon. What this will give you is a,000
2:31:042 hours, 31 minutes, 4 secondsextra credits. So let's go ahead and just take a look at this. So successfully redeemed coupon for a,000
2:31:132 hours, 31 minutes, 13 secondscredits. So you have nothing to lose. Go ahead and enter the Antonio coupon here.
2:31:192 hours, 31 minutes, 19 secondsSo what do we have to do now? Well, I think the best way to use it is by actually opening the documentation as
2:31:272 hours, 31 minutes, 27 secondswell. So first things first, we have to establish the fire crawl singleton or
2:31:342 hours, 31 minutes, 34 secondsclient, however you want to call it. And for that we need an API key. So either copy the existing one or create the
2:31:412 hours, 31 minutes, 41 secondsfirst one. Let's go ahead and install firecrawl in our project. So, npm install at mandible slashfirecrol-js.
2:31:572 hours, 31 minutes, 57 secondsThere we go. Now that this has been installed, I'm going to go ahead inside of my source lib and I'm going to create a new file firecrawl.
2:32:122 hours, 32 minutes, 12 secondsAnd then inside of here, I'm going to import fire crawl from our newly installed package. And then I'm just
2:32:202 hours, 32 minutes, 20 secondsgoing to export const firecrol with an API key which reads from process.environment
2:32:272 hours, 32 minutes, 27 secondsfirecraw key. Now let's go inside of environment.local.
2:32:322 hours, 32 minutes, 32 secondsLet's add firecroll here and let's add that here. Let's copy this and let's paste it. There we go. So we
2:32:402 hours, 32 minutes, 40 secondssuccessfully created the fire crawl client. So what we have to do now to test this out is the following. I think
2:32:482 hours, 32 minutes, 48 secondsthe easiest way to do this is by modifying our ingest function here.
2:32:522 hours, 32 minutes, 52 secondsLet's go ahead and make this just a bit more advanced. So what we're going to do now is we're going to add more steps to
2:33:012 hours, 33 minutes, 1 secondthis background job. We're first of uh first of all going to allow the user to add their custom prompt into this and
2:33:092 hours, 33 minutes, 9 secondsthen we are going to use the that prompt to extract all URLs which user has
2:33:162 hours, 33 minutes, 16 secondspasted. So if user said hey read this URL we have to specifically extract that URL. Why do we need to extract it? Well
2:33:262 hours, 33 minutes, 26 secondsbecause that is how fire crawl API accepts data. So in their standard features here we have scrape. Make sure
2:33:342 hours, 33 minutes, 34 secondsyou select node because that's what we're going to be using. So this is the npm install package which we have created and we have this client set up.
2:33:412 hours, 33 minutes, 41 secondsAnd basically this is the function that we are going to call file.scrape and then we're going to enter the URL
2:33:492 hours, 33 minutes, 49 secondswhich we have extracted from the user's prompt and we are going to return a format that we want to add to our context. In our case, markdown will be
2:33:582 hours, 33 minutes, 58 secondsthe one that we need. But as you can see, you can do even more advanced things like scraping down to HTML and so
2:34:062 hours, 34 minutes, 6 secondsmuch more things you can do which we are going to go through later. But for now, let's focus on the most simple and easy
2:34:122 hours, 34 minutes, 12 secondsto understand feature here. So first things first, let's go ahead and modify
2:34:212 hours, 34 minutes, 21 secondsthis. Let's add event here. And then let's go ahead and extract from event prompt. We can get that from event.data.
2:34:332 hours, 34 minutes, 33 secondsAnd we are going to define the type of event dot data to very simply accept a prompt which is a type of string. There
2:34:422 hours, 34 minutes, 42 secondswe go. Now let's go ahead and extract the URLs using await step.run.
2:34:492 hours, 34 minutes, 49 secondsAnd let's call the step extract URLs. is going to be an asynchronous method.
2:34:562 hours, 34 minutes, 56 secondsSo this is now a separate step and what we need to define here is is URL reg x.
2:35:042 hours, 35 minutes, 4 secondsSo, I'm going to go ahead and write a forward slash https question mark colon
2:35:132 hours, 35 minutes, 13 secondsand let's add a backwards slash forward slash another backward slash and
2:35:202 hours, 35 minutes, 20 secondsthen another forward slash open square brackets. Then go ahead and add a carrot
2:35:292 hours, 35 minutes, 29 secondsinside. Another backwards slash s plus forward slashg or just Google URL regax or use AI.
2:35:432 hours, 35 minutes, 43 seconds[laughter] Okay, whatever you do, just make sure you have a regx that can scrape URLs. And what we're going to do
2:35:502 hours, 35 minutes, 50 secondsnow is just return prompt domatch URL regax
2:35:562 hours, 35 minutes, 56 secondsor fall back to an empty array. And this will then be basically an array of
2:36:022 hours, 36 minutes, 2 secondsstrings in the end. So that's what URLs is going to be.
2:36:082 hours, 36 minutes, 8 secondsNow that we have that, let's go ahead and define our scraped content. And we can do that by doing await step.un run
2:36:182 hours, 36 minutes, 18 secondsscrape dash URLs again an asynchronous method and what we're going to do is we're
2:36:262 hours, 36 minutes, 26 secondsgoing to get the results by doing await promise.all URLs dom. So we are iterating over every
2:36:352 hours, 36 minutes, 35 secondssingle array over every single URL which we have extracted. So let's go ahead and extract it like this. And let's simply
2:36:442 hours, 36 minutes, 44 secondsrun the following await firecrol which you can now import from lib firecrawl
2:36:512 hours, 36 minutes, 51 secondsdots scrape and simply pass in the URL as the first argument and then open an
2:36:582 hours, 36 minutes, 58 secondsobject formats and go ahead and add markdown as the option here. There we go.
2:37:082 hours, 37 minutes, 8 secondsAnd now from this result, let's just return result domarkdown or fall back to null in case we were not able to scrape.
2:37:172 hours, 37 minutes, 17 secondsThere we go. And now let's just return results.filter by boolean. What this will do is it will filter out any of those null basically unsuccessful ones.
2:37:292 hours, 37 minutes, 29 secondsAnd let's just join this with a page break. So use backwards slashn backwards slashn.
2:37:402 hours, 37 minutes, 40 secondsGreat. And now what we can do is we can structure the final prompt. So the final
2:37:462 hours, 37 minutes, 46 secondsprompt here will be scraped content if it's available. We're going to go
2:37:522 hours, 37 minutes, 52 secondsahead and do this context column break
2:38:002 hours, 38 minutesscraped content break another break and then the user's
2:38:082 hours, 38 minutes, 8 secondsquestion prompt otherwise just the prompt we weren't able to extract any URLs or maybe there
2:38:162 hours, 38 minutes, 16 secondswere no URLs to extract and then instead of the prompt being this the final prompt will be this. So what are we doing now?
2:38:272 hours, 38 minutes, 27 secondsWe now have uh three steps. The first step is to extract all URLs from the user's query. The second step is to
2:38:372 hours, 38 minutes, 37 secondsscrape those URLs using fire crawl in a markdown format. And then we simply combine that into the prompt leading us
2:38:462 hours, 38 minutes, 46 secondsto last and third step to actually generate a response using this new
2:38:542 hours, 38 minutes, 54 secondscontext. So you can do this with uh of course Google, you can do this with Antropic, you can do this with open AI
2:39:012 hours, 39 minutes, 1 seconddepending on what model you use. uh it might know more and it might know less depending on their cutoff knowledge
2:39:092 hours, 39 minutes, 9 secondsdate. So I am assuming by the name of this one that its cutoff date was 2024. I don't know maybe it is maybe it isn't.
2:39:192 hours, 39 minutes, 19 secondsSo let's go ahead and run our project now in here npm rundev and in another side
2:39:282 hours, 39 minutes, 28 secondsnpx ignore scripts false inest cli latest dev. I'm just going to expand so you can see how it looks like in one line.
2:39:382 hours, 39 minutes, 38 secondsAll right. Make sure you have all of these running. And in fact, you won't even need to see your uh app. You just
2:39:452 hours, 39 minutes, 45 secondsneed to see uh inest server because we can now actually pass data from here. So go inside of functions, find the demo
2:39:542 hours, 39 minutes, 54 secondsgenerate one, and click invoke. And inside of here, go ahead and add prompt.
2:39:592 hours, 39 minutes, 59 secondsAnd let's try something simple. What is 2 + 2 for example? And let's click invoke function. So right now we're just
2:40:062 hours, 40 minutes, 6 secondstesting if this works. And this was super fast. As you can see, we first attempted to extract URLs. And as you can see, no URL is found. We attempted to scrape URLs. None of them were found.
2:40:182 hours, 40 minutes, 18 secondsAnd finally, we just went ahead and there we go. This is the response. 2 + 2 is equal to 4. Very simple, right?
2:40:262 hours, 40 minutes, 26 secondsBasically, our prompt thingy works. So let's try this again. This time let's go ahead and pose it the same question.
2:40:352 hours, 40 minutes, 35 secondsWhat is the name of the middleware?
2:40:402 hours, 40 minutes, 40 secondsLet me just go ahead and use some other quotes file in nextJS.
2:40:482 hours, 40 minutes, 48 secondsSo if I am correct, this model shouldn't know that the newest name is proxy.
2:40:542 hours, 40 minutes, 54 secondsDepending on when you are watching this tutorial, maybe that's common knowledge in uh AIS. now but I think that right
2:41:012 hours, 41 minutes, 1 secondnow let's see generate text uh okay in nextJS there is no specific middleware file instead nextJS provides a
2:41:092 hours, 41 minutes, 9 secondsmiddleware feature that allows you to intercept uh okay basically yes this is it this is the middleware file I guess
2:41:172 hours, 41 minutes, 17 secondsit's just understood me in differently but there we go it has no information about the new proxy thing right so let's
2:41:272 hours, 41 minutes, 27 secondschange that let's go ahead And let me just prepare the proxy thing.
2:41:322 hours, 41 minutes, 32 secondsUh if you want to find it too, uh go inside of the documentation and just click on proxy here and then copy the
2:41:382 hours, 41 minutes, 38 secondsURL. So let's try now. Let's try again this time with file crawl. So and let's
2:41:452 hours, 41 minutes, 45 secondsgo ahead and give it here [snorts] are the docs and paste it.
2:41:522 hours, 41 minutes, 52 secondsLet's click invoke function. And this time as you can see extract URLs has success successfully extracted the URL.
2:42:012 hours, 42 minutes, 1 secondThen it scraped the URL. So you can see we have every single information about the page in markdown format now. And
2:42:102 hours, 42 minutes, 10 secondsthen let's see the output. According to the documentation, the file for the middleware functionality in Nex.js is now called proxy. So successfully we
2:42:202 hours, 42 minutes, 20 secondshave extended the context of our very limited and knowledge cutff model. So
2:42:272 hours, 42 minutes, 27 secondsClaude's haiku is actually well I'm not sure if the dumbest model is the correct term to use but it's it's supposed to be
2:42:352 hours, 42 minutes, 35 secondsused for very short tasks. So the fact that we were able to extend the knowledge of this very simple model
2:42:422 hours, 42 minutes, 42 secondsshows you how useful something like fire crawl is. And if you weren't impressed enough uh by its generous free tier,
2:42:512 hours, 42 minutes, 51 secondsamazing feature. Did you know it's also open source? That's right. You can actually contribute to fire crawl
2:42:582 hours, 42 minutes, 58 secondsyourself. But let's go ahead and see what other things a fire crawl can do.
2:43:042 hours, 43 minutes, 4 secondsSo we just did the very basic scrape function, right? I think it's self-explanatory what this does. It can
2:43:122 hours, 43 minutes, 12 secondsscrape, but it can do so much more than that. So if for a specific case perhaps our case when we need super fast
2:43:202 hours, 43 minutes, 20 secondsresponses within our code editor ghost suggestions we might use their faster scraping function. You can see they even
2:43:282 hours, 43 minutes, 28 secondsthought of that just make sure to always click on JavaScript or NodeJS so you can see uh the actual code that you will be
2:43:362 hours, 43 minutes, 36 secondsusing. They also offer batch scraping for multiple URLs. They offer JSON mode.
2:43:442 hours, 43 minutes, 44 secondsAnd this is a cool one. They offer tracking changes on websites. This one is actually super cool. I can already
2:43:522 hours, 43 minutes, 52 secondsthink of a SAS you could build around this. Your users could give you URLs of the websites they want to track. And you
2:44:012 hours, 44 minutes, 1 secondcould build a SAS with fire crawl, which basically alerts them every time there's a change or maybe you detect that there
2:44:082 hours, 44 minutes, 8 secondsis an AB test going on. perhaps something uh to see how competitors are doing. So you can see how many things
2:44:152 hours, 44 minutes, 15 secondsthey have besides this scrape thing, stealth mode, proxies, so many other things. And if that wasn't enough, you
2:44:232 hours, 44 minutes, 23 secondscan also search the web in general, right? So if you want to, you can extend
2:44:312 hours, 44 minutes, 31 secondsthis even further by not waiting for the user to give us the direct URL, but
2:44:412 hours, 44 minutes, 41 secondsinstead allowing the user to just search for anything they want like what is the most up-to-date Nex.js version and we
2:44:492 hours, 44 minutes, 49 secondswould use Firecrol's search of that term.
2:44:542 hours, 44 minutes, 54 secondsSo instead of fire crawl here we would search for latest Nex.js version and we would maybe limit to top three results
2:45:022 hours, 45 minutes, 2 secondsso we don't you know overload the context and what that would do is it would return three items like this with
2:45:102 hours, 45 minutes, 10 secondsrelevant information about where you can find that info. So if if that crossed your mind you know oh cool but we have
2:45:192 hours, 45 minutes, 19 secondsto know the exact URL. Uh well, not only that, you can literally tell it, hey,
2:45:252 hours, 45 minutes, 25 secondscan you search for Nex.js uh proxy, right? Are there any updates about that file? And it will genuinely find the results just like a Google search would.
2:45:362 hours, 45 minutes, 36 secondsAnd then you could extract the URLs from here instead and do the usual process.
2:45:422 hours, 45 minutes, 42 secondsSo, it is a very very advanced tool. If that's not enough, they also offer
2:45:492 hours, 45 minutes, 49 secondssomething called map. Map basically allows you to input a website and get
2:45:562 hours, 45 minutes, 56 secondsall the URLs on that website extremely fast. And I think there's like a billion things you can build with this. How far
2:46:042 hours, 46 minutes, 4 secondsthey've gone with this is absolutely amazing. And the fact they're open source means that they will only grow more. In fact, in here you can see their
2:46:132 hours, 46 minutes, 13 secondsGitHub almost 70,000 more than 70,000 stars and extremely active repository completely opensource.
2:46:232 hours, 46 minutes, 23 secondsSo I I highly recommend that you take a look at this. I am super impressed by everything you can do here. You can even
2:46:312 hours, 46 minutes, 31 secondsrun this locally and you can selfhost fire crawl. Did I mention that on top of
2:46:402 hours, 46 minutes, 40 secondseverything else they offer stepbystep self-hosting guides? So I hope I explained why we need this because in
2:46:492 hours, 46 minutes, 49 secondsthe very first chapter that we did when we encountered an AI model which was code rabbit. You saw how it was limited
2:46:582 hours, 46 minutes, 58 secondsby its cutoff knowledge date. And the one way we can improve that is by allowing it to read the web. and we just
2:47:072 hours, 47 minutes, 7 secondsadded that to our AI model using firecrol. Amazing amazing job. So what
2:47:152 hours, 47 minutes, 15 secondswe've done now is just get familiar with firecrol uh understand what it can do and we grab some free tokens. But what
2:47:232 hours, 47 minutes, 23 secondswe're going to do later is obviously we're going to plug fireroll in into various AI features that we're going to
2:47:302 hours, 47 minutes, 30 secondshave which I demonstrated at the beginning of this chapter. The agentic chat on the left side will have a step
2:47:392 hours, 47 minutes, 39 secondscalled extract URLs and scrape URLs and then we're going to have a quick edit where user will also be able to add
2:47:462 hours, 47 minutes, 46 secondstheir own URL and we are going to have the same thing happening there. So that's how we're going to be using a
2:47:532 hours, 47 minutes, 53 secondsfire crawl in our app. Amazing amazing job. So let's go ahead and merge this changes. So, Firecrol AI. I'm just going
2:48:022 hours, 48 minutes, 2 secondsto shut down my app. Let's go ahead and do get add get commit 04 Firecrol AI.
2:48:132 hours, 48 minutes, 13 secondsGet checkout-b 04 firecroll AI.
2:48:222 hours, 48 minutes, 22 secondsGet push origin 04 firecrolai.
2:48:292 hours, 48 minutes, 29 secondsPerfect. Now, let's go ahead onto our GitHub repository URL. Let's open a a
2:48:372 hours, 48 minutes, 37 secondspull request. And this time, we don't actually have to review it simply because this was just a demonstration of
2:48:462 hours, 48 minutes, 46 secondsfire crawl. And we are later going to add firecroll in its proper place in its proper functions. So, right now it's in a function called demo function. Right?
2:48:572 hours, 48 minutes, 57 secondsSo no need to review that right now since obviously this will later be added again in a proper function. So just for
2:49:062 hours, 49 minutes, 6 secondsbecause of that there is no need to go through the entire review process right now. We are going to have the same review later. So let's just go ahead and
2:49:152 hours, 49 minutes, 15 secondsimmediately merge 04 fire crawl AI. And now we can go ahead
2:49:212 hours, 49 minutes, 21 secondsand do git checkout main gitpool origin main.
2:49:272 hours, 49 minutes, 27 secondsLet's wait a second and let's confirm everything is good here. So we are on the main branch and inside of my source
2:49:362 hours, 49 minutes, 36 secondscontrol in the graph here I can see that I have uh oh is it 04 firecrol AI? Uh huh. Did I make a mistake in nuration?
2:49:492 hours, 49 minutes, 49 secondsOh, this is chapter five. Okay, my apologies. This is supposed to be chapter five. So, one mistake that I've
2:49:562 hours, 49 minutes, 56 secondsmade. My apologies. So, later when you look at the branches, you will see 04 background jobs and 04 firecroll AI.
2:50:042 hours, 50 minutes, 4 secondsThat is supposed to be uh 05. Okay, one mistake. It's not going to hurt anyone, but you know that this is supposed to be
2:50:132 hours, 50 minutes, 13 seconds05. Maybe you've noticed and corrected yourself. Either way, not a big deal. We
2:50:202 hours, 50 minutes, 20 secondsgo ahead and we continue going uh with this amazing project. So, we demonstrated outdated AI code patterns.
2:50:272 hours, 50 minutes, 27 secondsWe've set up Final Cru uh web scraping.
2:50:312 hours, 50 minutes, 31 secondsWe successfully extracted URLs from user prompts. And finally, using Filecrol's scrape function, we have enhanced prompts with live documentation.
2:50:412 hours, 50 minutes, 41 secondsAmazing, amazing job. And see you in the next chapter.
Chapter 7: 06 Error Tracking
2:50:462 hours, 50 minutes, 46 secondsIn this chapter, we're going to add production grade error tracking and observability to our app. Basically,
2:50:542 hours, 50 minutes, 54 secondswe're going to transform silent failures, which will happen all across the app, into some actionable insights,
2:51:012 hours, 51 minutes, 1 secondto something you can fix and something you are aware of when it happens. This chapter will aim to show you the
2:51:082 hours, 51 minutes, 8 secondsdifference between flying blind and having full observability in production.
2:51:142 hours, 51 minutes, 14 secondsSo, let's get started by demonstrating some types of errors that can happen within our app. Make sure you have npm rundev running and make sure you have your ingest CLI running as well.
2:51:272 hours, 51 minutes, 27 secondsSo, now I'm going to go ahead and make sure my app is active on the localhost 3000 slash demo. Basically, where we tested our blocking and background ones.
2:51:402 hours, 51 minutes, 40 secondsAnd now I'm going to prepare my NJS developer server here as well simply so I'm ready to observe what happens there
2:51:482 hours, 51 minutes, 48 secondsas well. I'm going to go inside of my app folder demo page.tsx.
2:51:552 hours, 51 minutes, 55 secondsAnd now I'm going to go ahead and prepare a scenario of when we have a client error. So what is a client error?
2:52:032 hours, 52 minutes, 3 secondsThat's something that happens well on the client. That would be right here right in some use client component. This
2:52:122 hours, 52 minutes, 12 secondscan be various reasons. It can be an invalid access in an object. It can be an invalid function, an invalid type,
2:52:192 hours, 52 minutes, 19 secondsmany things. But in our demo scenario, we can just do this handle client error. And let's just do throw new error.
2:52:282 hours, 52 minutes, 28 secondsClient error. Something went wrong in the browser. So that's the first scenario we need to have.
2:52:362 hours, 52 minutes, 36 secondsThen let's prepare a second scenario, an API error. So we are going to purposely fetch an API endpoint which will throw
2:52:452 hours, 52 minutes, 45 secondsback an error. And then we're going to have a third scenario
2:52:522 hours, 52 minutes, 52 secondsinest error. Basically this will successfully make a fetch request but the background job itself will throw an
2:53:012 hours, 53 minutes, 1 seconderror. So that will be interesting to observe. So let's go ahead and first test the client error. This is the one
2:53:102 hours, 53 minutes, 10 secondsthat should be uh very easy to do. So I'm just going to go ahead here and I will add a new button.
2:53:192 hours, 53 minutes, 19 secondsI'm going to give it an on click variant of destructive and I will add a label
2:53:272 hours, 53 minutes, 27 secondsclient error. So we should now see client error button right here. What happens when I click? Well, as you can
2:53:342 hours, 53 minutes, 34 secondssee, we have an error. That is very expected, right? But the problem is only the user and well, us now in development
2:53:432 hours, 53 minutes, 43 secondsmode are aware that something actually went wrong in the browser. We actually
2:53:502 hours, 53 minutes, 50 secondshave no idea what went wrong. We don't know what user was trying to do. And worst of all, we genuinely don't know
2:54:002 hours, 54 minutesthat a user got an error, which is unacceptable in production. We need to be aware of every single error that
2:54:082 hours, 54 minutes, 8 secondshappens in our app on the client side, on the server side, or in a background job. So now, let's go ahead and copy
2:54:172 hours, 54 minutes, 17 secondsthis and demonstrate a server error or an API error. So handle API error. In
2:54:252 hours, 54 minutes, 25 secondsorder to test this out, we have to create the demo error which is very simple. So inside of an API folder demo,
2:54:342 hours, 54 minutes, 34 secondslet's create a new folder called error and inside of there route.ts
2:54:422 hours, 54 minutes, 42 secondsand let's simply add an invalid post method. Just a simple error. Something went wrong on the server. So, I'm going
2:54:502 hours, 54 minutes, 50 secondsto go ahead and call this API error. So, even worse experience here. We we don't even see anything happen. That's because
2:54:582 hours, 54 minutes, 58 secondsthis is a server error. And we can only figure that out if we go inside of our server logs right here. API error.
2:55:062 hours, 55 minutes, 6 secondsSomething went wrong on the server. So, this is even harder to observe, right?
2:55:112 hours, 55 minutes, 11 secondsEven the user is not really aware of what just happened. And you can guess that the third one is even worse than
2:55:192 hours, 55 minutes, 19 secondsthat. So let's just go ahead and quickly prepare that. So I'm just going to copy this and I will call this inest error
2:55:272 hours, 55 minutes, 27 secondshandle inest error. And let's go ahead and just
2:55:332 hours, 55 minutes, 33 secondscreate a very simple route. So inside of this demo I will create a new folder and
2:55:422 hours, 55 minutes, 42 secondsI will call it inest- error I will create a new route.ts inside and I will paste the following.
2:55:542 hours, 55 minutes, 54 secondsI'm going to import inest client. I'm going to export an asynchronous post method and all I'm going to do is I'm
2:56:012 hours, 56 minutes, 1 secondgoing to trigger a background job with the name of demo forward slash error.
2:56:062 hours, 56 minutes, 6 secondsAnd then I'm going to send a what is a success status of well response.json just status started. Right? This is what
2:56:152 hours, 56 minutes, 15 secondsthis would be considered a successful API call. Right? So I'm going to go ahead and now create that background job.
2:56:272 hours, 56 minutes, 27 secondsSo let's quickly go inside of source functions.ts and just as we have demo generate. So
2:56:352 hours, 56 minutes, 35 secondsthe same thing right at the bottom here I'm going to add demo error in justest
2:56:422 hours, 56 minutes, 42 secondscreate function first argument is ID second argument is very important demo
2:56:482 hours, 56 minutes, 48 secondsforward slash error which should match exactly what we trigger inside of the
2:56:552 hours, 56 minutes, 55 secondsAPI demo inest error route and we only have one step which will run fail and it
2:57:032 hours, 57 minutes, 3 secondswill just throw an error background job failed. In order to make this function, we also need to go inside
2:57:102 hours, 57 minutes, 10 secondsof API inest route.ts and add a demo error from that very same file. So we
2:57:172 hours, 57 minutes, 17 secondsnow register it. So now let's go ahead and click on ingest error. So even less information happening on the client but
2:57:272 hours, 57 minutes, 27 secondson the actual ingest development server we can see that this step is struggling.
2:57:352 hours, 57 minutes, 35 secondsSo something is going on. This step is simply keeps failing. You can see that inest thankfully will attempt to retry
2:57:442 hours, 57 minutes, 44 secondsthis step over and over again with polling uh increasing each time so it doesn't spam or reach a rate limit if it
2:57:522 hours, 57 minutes, 52 secondswere a third-party service. But still we know that we hardcoded this to an error.
2:57:582 hours, 57 minutes, 58 secondsSo those are three serious scenarios of which we have absolutely no idea that they're happening. How do we improve
2:58:062 hours, 58 minutes, 6 secondsthat? One of the most popular tools for resolving this issue is Sentry. And using the link on the screen, you can
2:58:142 hours, 58 minutes, 14 secondsget Sentry team for free for 3 months as well as 150,000 errors completely for
2:58:232 hours, 58 minutes, 23 secondsfree. Let's go ahead and create an account and then let's create a project.
2:58:292 hours, 58 minutes, 29 secondsOnce you are in your dashboard, you will see a prompt to create a project. I'm going to select Nex.js JS as that is our
2:58:372 hours, 58 minutes, 37 secondsframework and I'm not going to modify the defaults at all. Let's just modify our project slack to be Polaris and click create project.
2:58:482 hours, 58 minutes, 48 secondsAnd then in here we are going to get an install script. So we can just copy this. I'm going to shut down all of my
2:58:572 hours, 58 minutes, 57 secondsterminals for now. We're going to get them up and running later. So this is the command npx centry vizard latest and
2:59:052 hours, 59 minutes, 5 secondsI'm going to use nex next.js with a SAS flag organization name. This is my organization name John Doe. Yours will
2:59:132 hours, 59 minutes, 13 secondsbe different and a project name. I chose Polaris. You chose whatever you entered or you just left it at default. It
2:59:212 hours, 59 minutes, 21 secondsdoesn't matter. Let's just go ahead and run this within our project here. So in here it's telling us that we have some
2:59:282 hours, 59 minutes, 28 secondsuncommitted or unttracked files in our repo. And that's basically a demonstration of all of these errors. Uh
2:59:352 hours, 59 minutes, 35 secondsso it's warning us that it might overwrite some files. But this is perfectly fine because these are demo
2:59:422 hours, 59 minutes, 42 secondsfiles anyway. So yes, we are going to continue anyway. Let's confirm that.
2:59:482 hours, 59 minutes, 48 secondsAfter this, it's going to open a browser and it's going to connect. So as you can see, we now have login complete. You can go back to your terminal and now it is
2:59:572 hours, 59 minutes, 57 secondsinstalling Sentry using npm and after this we're going to answer some questions. So for the first option if
3:00:043 hours, 4 secondsyou want to route Sentry requests in the browser through the Nex.js server to avoid ad blockers basically giving you a
3:00:123 hours, 12 secondsbetter overview of what's going on with your app you can select yes. Same thing for tracing. Same thing for session
3:00:193 hours, 19 secondsreplay which is honestly magic like reprodu reproduction of what happened.
3:00:243 hours, 24 secondsLogs will be very important. This will allow us to create a structured trace of what actually led up to the event.
3:00:333 hours, 33 secondsAnd if you want to well I would recommend yes uh select yes for this too which is basically an example error
3:00:423 hours, 42 secondspage. And you can select yes for using a CI/CD tool because that will give us the
3:00:493 hours, 49 secondssentry out token. So copy the sentry out token. Make sure you copy it in full and immediately store it in your
3:00:583 hours, 58 secondsenvironment. Just make sure you don't commit environment which should be the default behavior. So I'm going to add sentry and just paste. Let me go ahead
3:01:083 hours, 1 minute, 8 secondsand copy this code and paste it here. There we go. And we [snorts] can just say yes, continue.
3:01:173 hours, 1 minute, 17 secondsAnd I will select no for project scoped MCP server simply because we are not going to be doing any AI coding things
3:01:263 hours, 1 minute, 26 secondsin this project. Well, besides building an AI editor. Great. So, I'm going to go
3:01:333 hours, 1 minute, 33 secondsahead now and run npm rundev again. And the first thing I'm going to do is I'm
3:01:423 hours, 1 minute, 42 secondsgoing to visit the page that they have created for us. So, Sentry example page.
3:01:483 hours, 1 minute, 48 secondsYou can visit this page at localhost 3000. Sentry-ample-page.
3:01:553 hours, 1 minute, 55 secondsSo, I'm going to copy that and paste it here. And we should be able to visit Sentry's pre-made page here. Ignore the
3:02:033 hours, 2 minutes, 3 secondspurple around our button. That is because this page has some custom styles. It's just for demo. And in here
3:02:113 hours, 2 minutes, 11 secondsthey have prepared a sample error similar to how we have prepared it. But you can see a crucial difference. This
3:02:183 hours, 2 minutes, 18 secondstime the error was logged to Sentry. So now let's go ahead and let's click on
3:02:253 hours, 2 minutes, 25 secondsour issues right here. So 15 seconds ago you can see some errors happening. We
3:02:323 hours, 2 minutes, 32 secondscan see the sentry example API error as well as sentry example front end error.
3:02:403 hours, 2 minutes, 40 secondsSo from now on we can actually see why our errors are happening. And I want to show you something very impressive. So
3:02:483 hours, 2 minutes, 48 secondsI'm going to expand my screen here. Uh go inside of Sentry example front end error. I'm pretty sure this is where
3:02:553 hours, 2 minutes, 55 secondsit's happening. And look at this. This is called a session replay. This is
3:03:013 hours, 3 minutes, 1 secondsomehow rebuilding what the user was doing in your UI before the error
3:03:083 hours, 3 minutes, 8 secondsoccurred. So you can see this is representing you can see this right. It's representing this very screen. It's
3:03:183 hours, 3 minutes, 18 secondsobviously saving on resources or maybe things it doesn't have access to. But you can see we very clearly clicked on
3:03:263 hours, 3 minutes, 26 secondsthis button and that is what triggered the error. Right? So this would help you a lot if you had some unknown error or
3:03:353 hours, 3 minutes, 35 secondsif the user doesn't know or didn't explain how it happened. You would have almost like a camera of what the user
3:03:433 hours, 3 minutes, 43 secondswas doing at the time. And using their breadcrumbs you can go so much in depth.
3:03:503 hours, 3 minutes, 50 secondsLook at this about every single thing that happened here, right? This is an
3:03:563 hours, 3 minutes, 56 secondsideal way of actually fixing a bug. This is insane. But we're just scratching the
3:04:043 hours, 4 minutes, 4 secondssurface. So now I'm going to go to my demo page, right? And in here I'm going
3:04:113 hours, 4 minutes, 11 secondsto try calling the client error. So this is the problem we had first time, right?
3:04:173 hours, 4 minutes, 17 secondsUser gets an error. And let me just show you in case you're lost. We are on forward slashdemo because I know this is
3:04:253 hours, 4 minutes, 25 secondsvery small font. So that's why I'm showing you. So this time we should get an improvement over that. There we go.
3:04:333 hours, 4 minutes, 33 secondsAnother error successfully tracked.
3:04:363 hours, 4 minutes, 36 secondsClient error. Something went wrong in the browser which is exactly what we log in our code. So exactly what happened.
3:04:463 hours, 4 minutes, 46 secondsThis is the error that we just triggered. You can see the exact URL where it happens. Forward slashdemo. You
3:04:543 hours, 4 minutes, 54 secondscan see my Chrome version, my Mac OS version. A bunch of things right here.
3:05:003 hours, 5 minutesAnd as always, you can see the trace preview. You can see the breadcrumbs.
3:05:043 hours, 5 minutes, 4 secondsLet's go ahead and go even further. So now I'm going to try triggering the API error again. Right now we can only see
3:05:133 hours, 5 minutes, 13 secondsthat here, right? Something went wrong on the server. But let's give it a second. Let's maybe refresh. And it's now going to appear here. There we go.
3:05:233 hours, 5 minutes, 23 secondsAPI error. Something went wrong on the server. So, forward/ API demo error. You
3:05:303 hours, 5 minutes, 30 secondscan now see and observe every single error happening in your project. The
3:05:373 hours, 5 minutes, 37 secondsonly thing that I believe isn't added by default is the ingest error. And in fact, we also need to have our injust
3:05:463 hours, 5 minutes, 46 secondsdevelopment server running to test this out. I'm pretty sure that uh when I click on inest error right here, it is
3:05:543 hours, 5 minutes, 54 secondsgoing to fail. But I don't think this will observe it by default. Instead, there is something called a middleware
3:06:033 hours, 6 minutes, 3 secondswhich we can use to add sentry to. This is what I was talking about. So, inest has a sentry middleware. And this is the
3:06:113 hours, 6 minutes, 11 secondscool thing about using Sentry. 99% of the tools that we will be using have uh full Sentry support. So that is amazing.
3:06:213 hours, 6 minutes, 21 secondsThat's how good of a tool this is. So let's start by installing the Inest Middleware Sentry here. I'm just going
3:06:293 hours, 6 minutes, 29 secondsto go ahead and install that. So mpm installing inest middleware sentry. Uh this is the version at the time of me making this video. This is 0.1.3.
3:06:413 hours, 6 minutes, 41 secondsAnd now I'm going to go ahead and copy this import. And I will go inside of my Okay, I can remove this comment here.
3:06:513 hours, 6 minutes, 51 secondsLet me copy the import again. And I will go inside of my ingest client.ts and I will add the import. There we go. And
3:07:003 hours, 7 minutesthen I'm just going to add it to my middleares here. So currently I have no middleares at all. Basically, this will
3:07:093 hours, 7 minutes, 9 secondsnow intercept all of our background jobs and we will be able to see what's going on uh between them. You can see some
3:07:163 hours, 7 minutes, 16 secondsrules here. So, in case it's not working or something is uh erroring, it's probably a version mismatch. So, I would
3:07:253 hours, 7 minutes, 25 secondssuggest that you can basically just Google Sentry Middleware ingest and you can find this page right here. So let's
3:07:333 hours, 7 minutes, 33 secondsgo ahead now and I will just restart my npm rundev and my ingest server. I will refresh
3:07:423 hours, 7 minutes, 42 secondsboth of them. And I'm going to refresh my feed here in the Sentry project. And now I'm going to trigger that ingest
3:07:513 hours, 7 minutes, 51 secondserror once again. And let's see if something else is happening now in the feed here. So, I'm going to refresh the feed.
3:08:013 hours, 8 minutes, 1 secondAnd there we go. We can now track all the errors happening in our background
3:08:083 hours, 8 minutes, 8 secondsjobs too. And keep in mind this can be so many things, right? So, let's go ahead and take a look at something
3:08:163 hours, 8 minutes, 16 secondsinside of our app folder demo. Uh we had some block actually we can go directly inside of ingest functions. So, take a look at all the steps that are possible.
3:08:273 hours, 8 minutes, 27 secondsuh we can fail with URL extraction, right? Maybe the prompt isn't a string,
3:08:343 hours, 8 minutes, 34 secondsright? This step can fail and usually we wouldn't even know that it failed. We probably think that user cannot enter
3:08:423 hours, 8 minutes, 42 secondsanything other than a string. But now if that happens, we will be aware of that, right? We are going to know exactly what
3:08:503 hours, 8 minutes, 50 secondshappened. Look at this. I can see exactly where it appeared exactly in what step. So this is an extremely
3:08:583 hours, 8 minutes, 58 secondsextremely useful thing. Uh it can happen in some third-party providers like fire
3:09:053 hours, 9 minutes, 5 secondscrawl, right? What if that fails? We are now aware of all of those amazing
3:09:123 hours, 9 minutes, 12 secondsthings. That is the power of sentry. But we are not done yet. we can improve our
3:09:193 hours, 9 minutes, 19 secondsobservability and monitoring even further when building an app like ours.
3:09:263 hours, 9 minutes, 26 secondsIt is also crucial to know how much tokens we are spending that simply cannot go unnoticed and Sentry has a
3:09:343 hours, 9 minutes, 34 secondssolution for that as well. In fact, it has a solution for the very provider of AI we are using uh Versel AI SDK. So
3:09:443 hours, 9 minutes, 44 secondsfollowing this documentation, we're now going to enable that. So you will see exactly how well Sentry understands
3:09:523 hours, 9 minutes, 52 secondswhat's going on with our app with just a few uh line changes. So first things first, let's go inside of sentry.edge.config.
3:10:003 hours, 10 minutesSo I'm going to find sentry.edge right here, and I'm going to find my sentry.init.
3:10:073 hours, 10 minutes, 7 secondsSo here it is my DSN, my traces sample rate and my enable logs which is send to
3:10:153 hours, 10 minutes, 15 secondstrue. So at the bottom here I'm going to add integrations.
3:10:193 hours, 10 minutes, 19 secondsI'm going to open the array and I'm going to add sentry dot versel AI integration. So make sure you add this to your sentry.edge.config.ts.
3:10:323 hours, 10 minutes, 32 secondsRight at the bottom, this is where I'm going to add that. And now what we have to do is we have to find some places
3:10:403 hours, 10 minutes, 40 secondswhere we are actually calling generate text. So I already know I have one inside of my API demo uh blocking a
3:10:483 hours, 10 minutes, 48 secondsroute.ts example. Here it is. I have generate text right here. And then after I do the prompt, I'm going to add
3:10:573 hours, 10 minutes, 57 secondsexperimental telemetry. Keep in mind that what's called experimental can sometimes be deprecated. Right? You can
3:11:053 hours, 11 minutes, 5 secondssee that we already had a bunch of deprecated things. That usually means that the new name is what was after
3:11:143 hours, 11 minutes, 14 secondsexperimental, right? So you can see now it's active tools, but before it was experimental active tools. I'm just
3:11:213 hours, 11 minutes, 21 secondstelling you this in case telemetry gets deprecated. That probably means you can now just use telemetry. But both should
3:11:293 hours, 11 minutes, 29 secondsactually work. And let's do is enabled to true. record inputs to true and
3:11:363 hours, 11 minutes, 36 secondsrecord outputs to true. And I will copy this and then I'm going to go inside of
3:11:433 hours, 11 minutes, 43 secondsmy ingest background job. So let me go ahead and find my inest functions.ts
3:11:513 hours, 11 minutes, 51 secondsand in here I have another generate text. So I'm just going to add the experimental telemetry here. Then I'm
3:11:593 hours, 11 minutes, 59 secondsjust going to restart my app and I'm going to restart my ingest
3:12:063 hours, 12 minutes, 6 secondsdeveloper server. I'm going to stay on the demo page here and I'm going to go back to the issues here and I'm going to
3:12:153 hours, 12 minutes, 15 secondsgo ahead and just, you know, start using my blocking.
3:12:193 hours, 12 minutes, 19 secondsLet's just wait for it to finish. Yeah, this is the example of the blocking one and my background one. So basically we
3:12:263 hours, 12 minutes, 26 secondsjust triggered some generate texts and now we're going to see if we can uh find
3:12:343 hours, 12 minutes, 34 secondssome AI telemetry within our Sentry project and completely accidentally
3:12:423 hours, 12 minutes, 42 secondsSentry actually caught an error in my inest background job. That is because I completely forgot. But yes, this will
3:12:523 hours, 12 minutes, 52 secondsnow fail because remember we now have to pass data and we have to pass prompts inside. That is how our background job
3:13:013 hours, 13 minutes, 1 secondnow works because we accept a prompt to extract some URLs inside. So yours might have failed too. And I would be clueless
3:13:103 hours, 13 minutes, 10 secondsas of why it happened until I looked at the code. But this way I can see that it was caught by centuries. So it was so
3:13:203 hours, 13 minutes, 20 secondseasy to make a mistake on our end and now as you can see it was immediately caught here and just by seeing this line
3:13:283 hours, 13 minutes, 28 secondsI would immediately get reminded oh I forgot to pass the prompt right I I forgot that we modified that from the
3:13:363 hours, 13 minutes, 36 secondsprevious chapters but lucky for us the blocking one should still be working just fine right that is just a normal
3:13:423 hours, 13 minutes, 42 secondsgenerate text so now find the insights click on AI and click on agents. In
3:13:513 hours, 13 minutes, 51 secondshere, as you can see, I can see exactly which LLM calls I did as well as how many tokens those LLMs actually used.
3:14:023 hours, 14 minutes, 2 secondsAnd in here, I can click on the exact trace ID. So, this is the one API demo blocking. Let me go ahead and zoom in so
3:14:103 hours, 14 minutes, 10 secondsyou can see post request on API demo blocking. We called generate text and we
3:14:173 hours, 14 minutes, 17 secondsspent that many tokens. And then you can see some more information here. And you
3:14:243 hours, 14 minutes, 24 secondscan see exactly which prompt it was. And you can even see the exact response
3:14:303 hours, 14 minutes, 30 secondsright here. And all this information is available. So you can see that just by
3:14:363 hours, 14 minutes, 36 secondsenabling that one small integration, we now have full observability over our AI
3:14:433 hours, 14 minutes, 43 secondsagents, we can see exactly which ones are being called, which ones are failing, uh, and how many tokens they
3:14:523 hours, 14 minutes, 52 secondsare using, right? So all of this is so interconnected when you actually start to research Sentry and how it works. And
3:15:023 hours, 15 minutes, 2 secondsone last thing I want us to demonstrate here is sentry logs. So that is actually
3:15:113 hours, 15 minutes, 11 secondsalready enabled if I take a good look in my sentry. So enable logs is set to
3:15:183 hours, 15 minutes, 18 secondstrue. So just make sure you have it here as well. But what we can do is something a bit more fun. We can basically explain
3:15:273 hours, 15 minutes, 27 secondsto our trace logs what the user was trying to do by giving some logging
3:15:353 hours, 15 minutes, 35 secondsinformation whenever user clicks a function or whenever we trigger a background job. Uh even though it's very
3:15:423 hours, 15 minutes, 42 secondsclear from sentry itself what happened we can be more descriptive ourselves and do that. So, by using Century's new
3:15:513 hours, 15 minutes, 51 secondsfeature called logs, you can actually create structured information and give
3:15:573 hours, 15 minutes, 57 secondsyou a better understanding of why certain errors have happened. And they're actually super easy to set up.
3:16:053 hours, 16 minutes, 5 secondsIn fact, I believe they are already configured here. So, make sure that inside of your sentry config files, both
3:16:133 hours, 16 minutes, 13 secondsof them, right? Uh I think it's very important that both of them are identical actually. So yes, make sure
3:16:203 hours, 16 minutes, 20 secondsboth your um Sentry server and Sentry Edge have the same information in them.
3:16:273 hours, 16 minutes, 27 secondsBut this is the one we are focusing on now. Enable logs set to true. And this is what you can basically do now. Uh you
3:16:363 hours, 16 minutes, 36 secondscan create structured information whenever user is doing something. This is actually a standard practice in production. So if I go inside of my demo
3:16:443 hours, 16 minutes, 44 secondspage right here and let's focus on these three functions that I have handle client error, API error and ingest
3:16:513 hours, 16 minutes, 51 secondserror. I'm going to go ahead and for example use the sentry logger to log that information. So import all as
3:17:003 hours, 17 minutessentry from at century nextjs and then I can use the sentry logger and
3:17:083 hours, 17 minutes, 8 secondsfor example let's do info. We can of course do error, trace, debug, warn, whatever we want. Right? So for example,
3:17:163 hours, 17 minutes, 16 secondssentry logger info and in here I'm just going to say uh user attempting to click
3:17:243 hours, 17 minutes, 24 secondson client function and you can give it even more information. So since we are using a clerk what we can actually do is we can
3:17:343 hours, 17 minutes, 34 secondsget the user ID from use user id use my apologies use out
3:17:413 hours, 17 minutes, 41 secondsuse out is a function you can import from clerk uh clerk react or clerk
3:17:503 hours, 17 minutes, 50 secondsnexjs. I think both of them should work just fine.
3:17:553 hours, 17 minutes, 55 secondsAnd you can destructure the user ID from here like this. And then you can go ahead and just pass that along here.
3:18:043 hours, 18 minutes, 4 secondsRight? You can see they actually tell you that you can do it like this.
3:18:073 hours, 18 minutes, 7 secondsBasically structured information. So this user attempt to click this button and then you can track along if that
3:18:153 hours, 18 minutes, 15 secondsuser breaks something going forward and you can see that side by side. So uh I have added this to handle client error
3:18:233 hours, 18 minutes, 23 secondswhich is used in the client error button. So when I click here I'm expecting that to be logged. So let me
3:18:303 hours, 18 minutes, 30 secondsshow you where you can find logs. Go inside of explore and then go inside of
3:18:373 hours, 18 minutes, 37 secondslogs right here. And if you have a prompt here to enable it, you can go ahead and click enable logs at the top.
3:18:463 hours, 18 minutes, 46 secondsAnd after a few moments, you will see a new log here. User attempting to click on client function. And here is our
3:18:543 hours, 18 minutes, 54 secondsproperty user ID. And here's the best part. So these logs by itself are okay.
3:19:013 hours, 19 minutes, 1 secondBut this is where the magic happens. If you actually go and find the relevant error, which is something went wrong in the browser, and you scroll down, you
3:19:113 hours, 19 minutes, 11 secondscan actually see the related log. So you now have more information, right? What
3:19:193 hours, 19 minutes, 19 secondsuser this happened to and what were they doing? Well, user attempting to click on a client function. That is what was
3:19:273 hours, 19 minutes, 27 secondshappening. That is the power of structured logs. You can see that they are way more powerful than that.
3:19:333 hours, 19 minutes, 33 secondsActually, you can trace things when starting a database connection and tell exactly what database we are connecting
3:19:403 hours, 19 minutes, 40 secondsto. uh we can throw fatal ones if database connection pool is exhausted
3:19:463 hours, 19 minutes, 46 secondsand you can track exactly at what uh number of connections that has happened.
3:19:523 hours, 19 minutes, 52 secondsSo very very useful and you can of course automate it and then abstract it to a much more uh useful state than
3:20:013 hours, 20 minutes, 1 secondthat. But here's another cool thing that they can actually do. They have integrations and you can for example
3:20:083 hours, 20 minutes, 8 secondssend console log warn and error calls all as logs to Sentry. So I'm going to
3:20:153 hours, 20 minutes, 15 secondsgo ahead and do that and then whenever my app or one of my third party libraries throws these errors or logs or
3:20:233 hours, 20 minutes, 23 secondsyou know things like that uh you can you have to add that to integrations. So right here there we go. uh our app will
3:20:313 hours, 20 minutes, 31 secondsnow receive log warn and error ones. So I'm going to add that to both here so I have identical ones. And there we go.
3:20:393 hours, 20 minutes, 39 secondsRight, just like that, our logs will now be listening to various uh console
3:20:473 hours, 20 minutes, 47 secondstraces throughout our app. So that's what was happening here. Here you can see injust is throwing some console warns or errors and I can see that
3:20:563 hours, 20 minutes, 56 secondshappening in my logs and I can see that happening next to my errors. So you can do so so much with Sentry and I cannot
3:21:053 hours, 21 minutes, 5 secondsrecommend this product enough. This is the go-to product for error tracking. uh
3:21:123 hours, 21 minutes, 12 secondsand they have a super generous free tier and you will trust me you will get alerted for every single error that
3:21:203 hours, 21 minutes, 20 secondshappens which in production is you know invaluable how much helpful it is. Uh I
3:21:273 hours, 21 minutes, 27 secondsbelieve that I have shown you the power and uh you know we we now learn the difference you know between going in
3:21:353 hours, 21 minutes, 35 secondsblind and having some proper observability production grade observability. So let's take a look at
3:21:433 hours, 21 minutes, 43 secondsuh what we did. We've set up Sentry with Nex.js Wizard. We caught a background job failure with ingest. We figured out
3:21:503 hours, 21 minutes, 50 secondshow to monitor AI calls and talking usage. And we added structured logs for user interactions. And uh finally, we
3:21:583 hours, 21 minutes, 58 secondseven added uh user context like user ID for even better debugging. So let's go
3:22:053 hours, 22 minutes, 5 secondsahead and let's merge all of these changes. We will clean up uh our extra stuff later, but for now we can just do
3:22:123 hours, 22 minutes, 12 secondsget add and then a dot and then get commit. So I previously
3:22:203 hours, 22 minutes, 20 secondsmade a mistake. I have uh 04 twice. So I have to be careful. This is now chapter
3:22:273 hours, 22 minutes, 27 secondssix. So I'm going to call this error tracking. And then once I've created
3:22:333 hours, 22 minutes, 33 secondsthis commit, I will do get checkout-b0 error tracking.
3:22:413 hours, 22 minutes, 41 secondsThere we go. Get push u origin06 error tracking. And we can do a quick
3:22:503 hours, 22 minutes, 50 secondsjob of a merge here simply because there is not much to review when it comes to a wizard who added all of the files which
3:22:583 hours, 22 minutes, 58 secondswas npx sentry. Every other new file is a file that's going to be deleted.
3:23:043 hours, 23 minutes, 4 secondsMeaning uh for example, all of this was added by sentry. So no need to review that because we are not going to modify what they have added, right? Uh but
3:23:133 hours, 23 minutes, 13 secondsthese things like an inest error route and a registration of that. All of that will be removed. Obviously, these are all just demo examples. So because of that, it makes no sense to waste time.
3:23:253 hours, 23 minutes, 25 secondsLet's go ahead and merge this and let's get on to building new features. So, I'm going to go ahead and merge this pull
3:23:323 hours, 23 minutes, 32 secondsrequest. Make sure to not delete the branch. So, now I have twice the number 04, but we know that this is actually
3:23:413 hours, 23 minutes, 41 secondssupposed to be 05. Let's go ahead and get checkout back to the main branch and get pull origin main. So, we are up to
3:23:503 hours, 23 minutes, 50 secondsdate with our remote merged changes. And to wrap it all up now, I always love to
3:23:573 hours, 23 minutes, 57 secondsconfirm my graph here. Here it is. So yes, 04 appears twice, but you can see logically chronologically that is 05.
3:24:073 hours, 24 minutes, 7 secondsAmazing. I believe that marks the end of this chapter. Amazing. Amazing job and see you in the next one.
Chapter 8: 07 Projects
3:24:173 hours, 24 minutes, 17 secondsIn this chapter, we're going to build the projects page. This will include the Polaris branding, project creation and
3:24:263 hours, 24 minutes, 26 secondsget feature, the actual project list, and some keyboard shortcuts as well as a command pallet or dialogue. Basically, this is what it's going to look like.
3:24:383 hours, 24 minutes, 38 secondsSo, this is the finished project. This is what we are supposed to have at the end of this chapter. This is the Polaris
3:24:463 hours, 24 minutes, 46 secondsbranding that we are going to have. This is the new button. And the only thing we aren't going to do is we aren't going to
3:24:553 hours, 24 minutes, 55 secondsmake this open a prompt simply because we don't have any functionality as to where to send that prompt at the moment.
3:25:033 hours, 25 minutes, 3 secondsSo, we're just going to make this instantly create a new project and then we're going to modify it later. Same is
3:25:103 hours, 25 minutes, 10 secondsfor the import feature right here. But everything else we will be able to do including this command dialogue right
3:25:193 hours, 25 minutes, 19 secondshere and the shortcuts all of that will work at the end of this chapter. So let's get right into it. The first thing
3:25:283 hours, 25 minutes, 28 secondswe have to do is make sure our app is running. Uh we will not be needing any ingest or anything like that. So you can
3:25:353 hours, 25 minutes, 35 secondsjust have localhost 3000 running. And what I would like to do is just clean up our project first. Right. So let's go
3:25:423 hours, 25 minutes, 42 secondsinside of source app folder and in here let's remove the central example page as we're not going to need it. Uh and let's
3:25:503 hours, 25 minutes, 50 secondsremove the demo page too. We are not going to need that either. And inside of the API let's carefully go here. So let's remove demo. We don't need that.
3:26:003 hours, 26 minutesAnd let's remove century example API.
3:26:033 hours, 26 minutes, 3 secondsAnd inside of inest route we can leave it as is. we're going to clean up in just later when we actually start building uh some real background jobs.
3:26:133 hours, 26 minutes, 13 secondsSo for now, let's just head back to localhost 3000 where we have kind of started building the projects list, right? So what I want to do first is I
3:26:223 hours, 26 minutes, 22 secondswant to go inside of convex and I want to go inside of schema here. The reason I want to do that is because I want to add all of the features here simply. So
3:26:313 hours, 26 minutes, 31 secondsin case we are doing some UI changes depending on the field of the project in the database, we can do that and we
3:26:403 hours, 26 minutes, 40 secondsdon't have to fake it. Right? So I'm going to go ahead and add export status here.
3:26:483 hours, 26 minutes, 48 secondsGive it a v.optional like this.
3:26:533 hours, 26 minutes, 53 secondsAnd inside I'm just going to copy this v.un. Let's go ahead and add exporting.
3:27:013 hours, 27 minutes, 1 secondLet's go ahead and add completed.
3:27:043 hours, 27 minutes, 4 secondsLet's add failed. And let's add cancelled.
3:27:093 hours, 27 minutes, 9 secondsAnd let's also add export repo URL. This will also be optional. And if it is
3:27:163 hours, 27 minutes, 16 secondspassed, it has to be a string. So, the reason I'm adding this is because I'm pretty sure our UI will look different
3:27:243 hours, 27 minutes, 24 secondsif a project has this field. If it does, we're going to show a little GitHub icon to indicate to the user like, hey, uh,
3:27:333 hours, 27 minutes, 33 secondsthis was imported. Otherwise, it will show a globe icon to indicate it's kind of on the cloud, right? It's custom
3:27:403 hours, 27 minutes, 40 secondsmade. Uh, perhaps we won't need the export status for this exact chapter, but still, no worries. Uh it's
3:27:473 hours, 27 minutes, 47 secondscompletely fine if we add it. Now the import status is important. So make sure you have that. And let's also add
3:27:553 hours, 27 minutes, 55 secondsupdated ad field. So updated ad is a number like this. Great. So now let's go
3:28:033 hours, 28 minutes, 3 secondsahead and make sure we do npx convex dev simply so all of that is immediately
3:28:093 hours, 28 minutes, 9 secondssynchronized. And there we go. Okay. So this is actually all successful. The problem is that we have existing
3:28:173 hours, 28 minutes, 17 secondsuh projects, right? So, let's go inside of dashboard.convex.dev or you can use the link on the screen.
3:28:253 hours, 28 minutes, 25 secondsLet's go inside of Polaris here. Data projects and let's just delete all of them. All of them are outdated. And
3:28:343 hours, 28 minutes, 34 secondslet's do the same inside of tasks because we don't even have that anymore. So, we can get rid of tasks entirely.
3:28:403 hours, 28 minutes, 40 secondsLet me see. Uh there we go. You can delete the table from here. Perfect. So we are only left with projects. That
3:28:473 hours, 28 minutes, 47 secondsreminds me, we can also delete sample data.jsonl.
3:28:523 hours, 28 minutes, 52 secondsSo let's remove that. No need for that either. Perfect. Now let's go ahead inside of convex and let's go inside of
3:29:003 hours, 29 minutesprojects here. And now we're going to go ahead and just fix the current create method. So let's go ahead and see the
3:29:103 hours, 29 minutes, 10 secondsarguments here. Still we're just going to use the name. Nothing needed to change here. And then let's go ahead and
3:29:173 hours, 29 minutes, 17 secondsdo the following. So I'm going to do const project ID await context database insert into
3:29:253 hours, 29 minutes, 25 secondsproject table name arguments.name owner ID identity.
3:29:363 hours, 29 minutes, 36 secondsAnd updated at will very simply be a date.now instance. And let's return back project ID. All right.
3:29:463 hours, 29 minutes, 46 secondsAnd now I want to do one thing. We're going to use this a lot like in almost every single query and mutation. So
3:29:543 hours, 29 minutes, 54 secondslet's abstract it. So I'm going to go inside of convex here and I will create a new out. DS
3:30:013 hours, 30 minutes, 1 secondand I'm going to import mutation context from generated server and query context from generated server. And then I'm
3:30:113 hours, 30 minutes, 11 secondsgoing to export const verify out. I'm going to make this an asynchronous method. And for the context type, I will
3:30:193 hours, 30 minutes, 19 secondsuse either a query context or a mutation context. And then in here, we can go
3:30:263 hours, 30 minutes, 26 secondsahead and return the identity. There we go.
3:30:323 hours, 30 minutes, 32 secondsNow that we have verify out, we can call this instead. So in order to get identity, we can just await verify out and pass in the context.
3:30:433 hours, 30 minutes, 43 secondsSo you can import that from out. Since this is a mutation inside of ver verify out, this is the type we will use. So if
3:30:523 hours, 30 minutes, 52 secondsI didn't pass that, uh looks like it doesn't have an error because they could be identical. Yes, it uses the generic
3:30:593 hours, 30 minutes, 59 secondsmutation context. So maybe that covers the type for the other one. I don't know but I kind of want to use this. It works
3:31:073 hours, 31 minutes, 7 secondsfor me in the original source code. So I will teach you to do it here as well.
3:31:113 hours, 31 minutes, 11 secondsGreat. So this is our create method. And now let's go ahead and let's modify uh the get method here. We are going to
3:31:183 hours, 31 minutes, 18 secondsslightly modify it. So first things first, we get the identity by using verify out and passing in the context here.
3:31:263 hours, 31 minutes, 26 secondsAnd then let's go ahead and store the result of this inside of a query. And what we're going to do is we are going
3:31:343 hours, 31 minutes, 34 secondsto add an argument here which will be optional limit v dot optional and pass in the number here. So if we want to we can limit the number of results we get.
3:31:453 hours, 31 minutes, 45 secondsSo if arguments.limmit uh actually yeah it would be better to just not call items here at all. Uh
3:31:543 hours, 31 minutes, 54 secondsokay, let's call this get partial like this.
3:32:023 hours, 32 minutes, 2 secondsAnd since the name indicates that it's going to be partial, we can actually make the limit required because that makes more sense, right? If we have a
3:32:103 hours, 32 minutes, 10 secondsseparate query for making partial ones, let's go ahead and actually do that here. And then we can very simply uh instead of using collect we can use take
3:32:193 hours, 32 minutes, 19 secondsand just pass in the arguments limit. And I'm not sure I'm doing this correctly. There we go.
3:32:303 hours, 32 minutes, 30 secondsArguments.limmit. Perfect. And then in here, well, I think we can just return
3:32:383 hours, 32 minutes, 38 secondsit now. There we go. So that is get partial. And now let's just have a normal get which will well we can copy
3:32:473 hours, 32 minutes, 47 secondsit since it's going to be very very similar except it's not going to accept any arguments at all and instead of this it will just use collect and no need for
3:32:563 hours, 32 minutes, 56 secondsthis. Looks like await has no effect on this type of expression. I'm assuming that's the case here too. Looks like it's not. Okay.
3:33:063 hours, 33 minutes, 6 secondsYou can see that it tells me a weight has no effect on this type of expression. Hm.
3:33:123 hours, 33 minutes, 12 secondsOkay, I'm going to trust it. So, let's go ahead and have that in here. We got an error.
3:33:223 hours, 33 minutes, 22 secondsUse query projects.get.
3:33:263 hours, 33 minutes, 26 secondsSo, looks like something is incorrect here inside of the convex one. So, let me go ahead and do npx convex dev again
3:33:353 hours, 33 minutes, 35 secondsin hopes that that will resolve it because I don't see any at least I can't see any issues with the code. There we go. Convex functions ready. So, can I refresh this now?
3:33:463 hours, 33 minutes, 46 secondsOkay, I still cannot refresh it. How about we go and take a look what it actually is? So, source app folder page.dsx.
3:33:563 hours, 33 minutes, 56 secondsUh, let's see what is the problem.
3:33:583 hours, 33 minutes, 58 secondsProjects. Um, what is the problem? Map does not exist.
3:34:033 hours, 34 minutes, 3 secondsOkay. API projects.get H. Oh, I'm sure a lot of you have noticed this.
3:34:163 hours, 34 minutes, 16 secondsSorry about that. Uh, okay. If you didn't see what it was, I forgot to execute the collect method.
3:34:243 hours, 34 minutes, 24 secondsNow, it should work just fine. My apologies. Okay, so we now have the get method, we have the get partial, so we
3:34:323 hours, 34 minutes, 32 secondscan limit the amount of things we get and we have a proper create method.
3:34:373 hours, 34 minutes, 37 secondsPerfect. So let's go ahead and let's start with uh the creation of this. So I'm going to go ahead inside of source
3:34:463 hours, 34 minutes, 46 secondsfeatures and in here I will create projects like this. Instead of projects I will create UI. Uh my apologies, I'm
3:34:543 hours, 34 minutes, 54 secondsnot going to call it UI. I'm going to call it components. And inside I will create let's call this projects view.tsx
3:35:043 hours, 35 minutes, 4 secondslike this. Let's mark it as use client export con projects view. And let's return a div projects view.
3:35:143 hours, 35 minutes, 14 secondsJust like that. And then I'm going to go ahead inside of the app folder page. DSX
3:35:213 hours, 35 minutes, 21 secondsright here. I'm going to go ahead and call this home.
3:35:253 hours, 35 minutes, 25 secondsI will remove every logic inside all the logic.
3:35:303 hours, 35 minutes, 30 secondsRemove all of the imports. No need for it to be used client anymore. And I'm just going to return projects view. So that's going to be my only import here.
3:35:403 hours, 35 minutes, 40 secondsThere we go. So now I will no longer develop here inside of the app folder.
3:35:443 hours, 35 minutes, 44 secondsInstead I will just import projects view which is uh correctly put here in the projects folder. So I don't have to care
3:35:513 hours, 35 minutes, 51 secondsif you know this accidentally becomes part of the URL or something because that's how uh routing works inside of
3:35:583 hours, 35 minutes, 58 secondsthe app folder. I can safely develop things here in the structure that I want with the folder names that I prefer.
3:36:053 hours, 36 minutes, 5 secondsGreat. So we are inside of the projects view. Let's go ahead and let's start by actually building the layout. So I'm
3:36:143 hours, 36 minutes, 14 secondsgoing to give this a minimum height of screen so it always takes 100% of the view. I'm going to give it a background
3:36:213 hours, 36 minutes, 21 secondscolor of sidebar which is going to make it slightly darker.
3:36:263 hours, 36 minutes, 26 secondsI'm going to give it flex flex column items center justify center padding of
3:36:333 hours, 36 minutes, 33 secondssix and on medium padding of 16. Let's go ahead and open a new div inside. And
3:36:423 hours, 36 minutes, 42 secondsin this one we're going to limit how wide the content will go. So maximum width of this content will be small. We
3:36:493 hours, 36 minutes, 49 secondsuse MX out to equally push it from both sides. And we repeat the flex call. We
3:36:563 hours, 36 minutes, 56 secondsgive it a gap for items center. And let's go ahead and keep it at that. Now let's go ahead and let's add a new div.
3:37:063 hours, 37 minutes, 6 secondsSo I'm going to add some spaces so it's easier for you to follow. There we go.
3:37:113 hours, 37 minutes, 11 secondsanother div with a class name flex justify between gap 4 with full and items center inside and then let's go
3:37:203 hours, 37 minutes, 20 secondsahead and add another div again I'm going to add spaces there we go div flex items center gap do
3:37:303 hours, 37 minutes, 30 secondswith full and group forward slash logo so this is how it's supposed to be okay
3:37:373 hours, 37 minutes, 37 secondsinside of here we're going to have an image element And for now, let's go ahead and use if we have any image in
3:37:443 hours, 37 minutes, 44 secondsour public folder so we can add an image later so we don't concern ourselves with that. Looks like we have versell.svg.
3:37:513 hours, 37 minutes, 51 secondsCan I use that? There we go. Perfect.
3:37:543 hours, 37 minutes, 54 secondsAnd let me give this an alt of polaris which will be the name of our app. And let's give it this a class name size dash 32 pixels in square brackets. And
3:38:043 hours, 38 minutes, 4 secondsthe medium size 46 pixels in square brackets. There we go. So a very small
3:38:103 hours, 38 minutes, 10 secondsone and maybe I should zoom out actually so I see the browser mode here.
3:38:173 hours, 38 minutes, 17 secondsOkay. And then below the image or should I say next to it we are going to have a text polaris like this. And let's go
3:38:263 hours, 38 minutes, 26 secondsahead and add the poppins font. So I'm going to go ahead and define that const font will be poppins from next font
3:38:353 hours, 38 minutes, 35 secondsgoogle. subsets will be Latin and then we need to add the weight property. So it's going to be 400, 500, 600 and 700.
3:38:473 hours, 38 minutes, 47 secondsGreat. Now let's go ahead and let's prepare an import of if you remember very early in CN. This helps us uh make dynamic Tailwind classes.
3:38:583 hours, 38 minutes, 58 secondsSo we are using it for the first time now CN like this. And in the first argument of
3:39:073 hours, 39 minutes, 7 secondsthe CN, I'm just going to give it some default classes like text for Excel to make it larger on medium text 5 Excel
3:39:163 hours, 39 minutes, 16 secondsfont semibold text white even though that's already present. So no need to do that. And then I'm going to go ahead and add a comma
3:39:253 hours, 39 minutes, 25 secondshere. And I'm going to pass font.classname. And that's going to change the font.
3:39:313 hours, 39 minutes, 31 secondsPerfect. So now uh let's go ahead and let's go outside of this div. Outside of this div.
3:39:413 hours, 39 minutes, 41 secondsAnd in here let's go ahead and open a new one like this.
3:39:483 hours, 39 minutes, 48 secondsThis one will have a class name of flex flex call gap 4 and full width. And [snorts] then in here
3:39:573 hours, 39 minutes, 57 secondswe're going to create a grid. So class name grid grid columns 2 and gap 2. Let me just fix the indentation here. And
3:40:053 hours, 40 minutes, 5 secondsinside we're going to use our chaten buttons. So make sure you add an import for that. And I'm going to give this a
3:40:143 hours, 40 minutes, 14 secondscouple of things. So variant here will be outline.
3:40:193 hours, 40 minutes, 19 secondsOn click for now is just going to be an empty arrow function. Class name will be
3:40:253 hours, 40 minutes, 25 secondsfull height. items start justify start
3:40:303 hours, 40 minutes, 30 secondspadding of four bg of background border
3:40:393 hours, 40 minutes, 39 secondsflex flex column gap six and rounded none so
3:40:463 hours, 40 minutes, 46 secondswe make it sharp inside of here open up a div and inside a sparkle icon from lucid react so make sure you import
3:40:553 hours, 40 minutes, 55 secondsspark sparkle icon. And I'm just going to move it up here.
3:41:023 hours, 41 minutes, 2 secondsOkay, I'm going to fix this little issue I've created. The sparkle icon will have a class name of size four
3:41:113 hours, 41 minutes, 11 secondslike this. And the div encapsulating the sparkle icon will have a class name of
3:41:183 hours, 41 minutes, 18 secondsflex items center and justify between as well as a full width. Then below this,
3:41:253 hours, 41 minutes, 25 secondswe're going to add our shortcut UI. So KBD component, we have this from Shaten
3:41:323 hours, 41 minutes, 32 secondsUI. So KBD and let's go ahead and add a class name here. BG accent and border. Let's make sure it's closed.
3:41:433 hours, 41 minutes, 43 secondsAnd then [snorts] inside of here, we're simply going to say what our shortcut will be. So for me, it's going to be command J since I am on a Mac OS. Uh you
3:41:533 hours, 41 minutes, 53 secondscan also use you know control + J whatever you want right if you want this specific icon I would suggest just
3:42:003 hours, 42 minutesgoogling um command icon copy paste you know just find it on Google
3:42:083 hours, 42 minutes, 8 secondsokay and then outside of this div I'm just going to add a new div and the span which says new and I'm going to give it a class name of text small like this.
3:42:203 hours, 42 minutes, 20 secondsSo, let me go ahead and check it out.
3:42:233 hours, 42 minutes, 23 secondsThere we go. Looks nice. We now have this button right here. Perfect.
3:42:293 hours, 42 minutes, 29 secondsUh, let's go ahead and let's copy this button. So, the entire thing we can duplicate it below. There we go. Now I
3:42:383 hours, 42 minutes, 38 secondshave two of them. So, I'm going to work in the bottom one. The class will be exactly the same.
3:42:453 hours, 42 minutes, 45 secondsThe shortcut will be the letter I. Instead of new, it will say import.
3:42:543 hours, 42 minutes, 54 secondsAnd for the icon, we actually have to install React icons for this one. So, let's do that.
3:43:013 hours, 43 minutes, 1 secondnpm install react- icons simply because Lucid React doesn't really have a good uh GitHub icon. So, make sure you have
3:43:103 hours, 43 minutes, 10 secondsReact icons installed. And then let's go ahead and import fa GitHub from react-ons
3:43:183 hours, 43 minutes, 18 secondsFA. And then we can replace down here this one. Find import and find sparkle
3:43:263 hours, 43 minutes, 26 secondsicon and replace it with GitHub. There we go. We now have our new and our import buttons right here. Amazing. So
3:43:353 hours, 43 minutes, 35 secondsnow what we ought to build next is the project list. So where does the project list belong? Uh well, it actually belongs right outside of this div right
3:43:443 hours, 43 minutes, 44 secondshere after we close the button. So let's prepare it projects list like this.
3:43:503 hours, 43 minutes, 50 secondsNow let's go ahead and create it. So instead of components here, I'm going to create a new file project-list.tsx
3:43:593 hours, 43 minutes, 59 secondsand let's start creating that. So first things first, I'm going to add an interface projects list props which will
3:44:053 hours, 44 minutes, 5 secondshave one prop on view all function and then we can go ahead and create a proper export projects list on view all. Don't
3:44:143 hours, 44 minutes, 14 secondsworry I'm going to collapse this so you can see better. There we go. Very simple. So projects list is a component
3:44:223 hours, 44 minutes, 22 secondsin which we've destructured on view all and we gave it a type of project list props above. So make sure you have the structured the props here. This can also
3:44:303 hours, 44 minutes, 30 secondsbe written as props like this, but we have to structure it since it's going to be the only one here. All right. So, now
3:44:383 hours, 44 minutes, 38 secondsthat we have that, I'm going to go ahead and write return. I'm going to add a div here with a class name flex flex column and a gap of four like so.
3:44:523 hours, 44 minutes, 52 secondsAnd then uh let's go ahead and let's actually, you know, list our projects.
3:44:593 hours, 44 minutes, 59 secondsAnd before we do that, let's just render them. So projects list, make sure you import it. There we go. I'm going to
3:45:073 hours, 45 minutes, 7 secondsgive it an on view all to be an empty arrow function simply so we get rid of the type error. And now what I like to do is I like to abstract my hooks. So
3:45:173 hours, 45 minutes, 17 secondsI'm going to go inside of features projects and I will create a new folder called hooks like this.
3:45:233 hours, 45 minutes, 23 secondsAnd my hooks will have a file called use-p projects.ts.
3:45:303 hours, 45 minutes, 30 secondsAnd in here I'm going to import you know use query from convex react import
3:45:393 hours, 45 minutes, 39 secondsAPI from convex generated API and I will export con use projects here like this
3:45:473 hours, 45 minutes, 47 secondsand return use query API projects get like this and then I'm going to
3:45:553 hours, 45 minutes, 55 secondsimmediately duplicate this and I will call this use projects partial
3:46:013 hours, 46 minutes, 1 secondwith a limit which is a type of number get partial and in here we have to pass the limit
3:46:103 hours, 46 minutes, 10 secondsthere we go so a simple abstraction so I can now call this instead so let's do that let's go inside of projects list
3:46:183 hours, 46 minutes, 18 secondsright here and let's do that uh right here const projects use projects partial
3:46:273 hours, 46 minutes, 27 secondsfrom hooks use projects and pass in the number. So I'm going to do six actually.
3:46:333 hours, 46 minutes, 33 secondsSo six of my latest projects. And if projects is undefined, that means it is still loading. So I'm just going to
3:46:413 hours, 46 minutes, 41 secondsreturn a spinner component. You can import this from components UI spinner.
3:46:473 hours, 46 minutes, 47 secondsAnd I'm going to give it a class name size for text ring.
3:46:533 hours, 46 minutes, 53 secondsSo if you refresh for a brief second, you see the spinner. In fact, if I change this to true, you can see how it
3:47:023 hours, 47 minutes, 2 secondslooks like. Let me zoom in so they can actually see what we're developing.
3:47:063 hours, 47 minutes, 6 secondsThere we go. So yes, in convex, if the query result, any query result is
3:47:143 hours, 47 minutes, 14 secondsundefined, that means it's loading because it's either going to be an empty array or
3:47:213 hours, 47 minutes, 21 secondsnull if if we weren't able to find it, right? So if it's undefined that means it's loading and that is from the
3:47:283 hours, 47 minutes, 28 secondsdocumentation of convex right. So that's how you detect if something from convex is loading. Okay. Now inside of here let's go ahead and do something. So I'm
3:47:373 hours, 47 minutes, 37 secondsgoing to go ahead and do most recent projects and then I'm going to do rest from projects. So what did I do here?
3:47:463 hours, 47 minutes, 46 secondsWell, I will extract the most recent project I have worked on from the rest
3:47:533 hours, 47 minutes, 53 secondssimply because I'm going to have a separate card showing me uh like, hey, you can continue working on your most recent project. And then here are the
3:48:023 hours, 48 minutes, 2 secondsrest of the projects. So that's why I'm doing this for now. Let's just do the rest thing. So if rest.length length is
3:48:113 hours, 48 minutes, 11 secondslarger than zero meaning okay we do have the rest of the project in that case let's go ahead and start creating uh a
3:48:203 hours, 48 minutes, 20 secondslist for this so let's give this flex flex call and a gap of two then let's go
3:48:273 hours, 48 minutes, 27 secondsahead and create another div inside with flex items center and justify between and gap two then let's go ahead and
3:48:363 hours, 48 minutes, 36 secondscreate a label so basically a span element with text extra small and text muted foreground which simply says uh
3:48:453 hours, 48 minutes, 45 secondsrecent projects right uh okay so the reason we're not seeing that text but
3:48:523 hours, 48 minutes, 52 secondsindicate that this is actually empty so let me go ahead instead of use projects specifically get partial here let's see
3:49:023 hours, 49 minutes, 2 secondsuh can oh yes it is because we don't really have any projects here. So this
3:49:113 hours, 49 minutes, 11 secondsis what I would like to do right now. I would like to just just because it makes no sense, you know, to develop thing uh
3:49:173 hours, 49 minutes, 17 secondsa UI thing we don't see, right? So let's just quickly go back to the projects
3:49:253 hours, 49 minutes, 25 secondsview right here. Let's focus on that and let's prepare our hooks. Use projects.
3:49:333 hours, 49 minutes, 33 secondsAnd inside of here, let's go ahead and let's create export const use create
3:49:403 hours, 49 minutes, 40 secondsproject like so. Return use mutation from convex react API projects create like this.
3:49:533 hours, 49 minutes, 53 secondsThat's the only thing we're going to do now. So, let's go back inside of the projects view. And now I'm just going to
3:49:593 hours, 49 minutes, 59 secondsgo ahead and well I'm just going to add that hook here.
3:50:053 hours, 50 minutes, 5 secondsconst create project use projects use create project from dot dohooks use projects. Perfect.
3:50:183 hours, 50 minutes, 18 secondsSo now let's go ahead and find this uh new button. Right. And in here I'm going to go ahead and call create projects.
3:50:293 hours, 50 minutes, 29 secondsAnd for the name, so what should we use uh for the name? Well, what I the solution that I have found is to
3:50:383 hours, 50 minutes, 38 secondsbasically use a library uh which will allow us to create a unique slug. So
3:50:473 hours, 50 minutes, 47 secondslet's go ahead and do that. The package name is the following. So, unique names
3:50:553 hours, 50 minutes, 55 secondsgenerator. So, let's do npm install unique-names generator.
3:51:003 hours, 51 minutesThis one. Perfect. And let's go ahead and import everything we need from it.
3:51:063 hours, 51 minutes, 6 secondsSo, we will later, you know, move this somewhere else. But for now, it's just going to be here. So, let's import
3:51:143 hours, 51 minutes, 14 secondsadjectives, animals, colors, and unique names generator itself from the same named package. And then once we have
3:51:223 hours, 51 minutes, 22 secondsthat we are able to actually uh generate the name. So I'm going to go ahead and prepare that just above here in the on click function.
3:51:333 hours, 51 minutes, 33 secondsSo the project name will call the unique names generator function and instead of its object we're going to add
3:51:403 hours, 51 minutes, 40 secondsdictionaries. So we're going to use adjectives, animals and colors. I simply found that to be a nice combination. The
3:51:473 hours, 51 minutes, 47 secondsseparator is going to be a dash and we're going to use three words. This is kind of the standard in most of these types of projects you see these days. So
3:51:563 hours, 51 minutes, 56 secondsthere we go. Now when I click on new here, uh I'm not sure if it works or not.
3:52:023 hours, 52 minutes, 2 secondsLet's see here. It works. Do I have the fun name? I do. Shaky cannid teal. So if I click again here, there we go. It
3:52:123 hours, 52 minutes, 12 secondsworks. And you can see my owner ID is stored inside. And now I can even see the recent projects here. Perfect. Uh so make sure you have at least two created.
3:52:223 hours, 52 minutes, 22 secondsThat's why the recent projects were not showing. Remember inside of projects list we separate the most recent one
3:52:323 hours, 52 minutes, 32 secondsfrom the rest. So make sure you have at minimum two items inside.
3:52:383 hours, 52 minutes, 38 secondsSo maybe for simplicity sake we can just use projects for now. here
3:52:453 hours, 52 minutes, 45 secondsprojects that will be simpler I think great so now that we have the span recent
3:52:543 hours, 52 minutes, 54 secondsprojects let's go ahead and add a native HTML button with view all text here
3:53:033 hours, 53 minutes, 3 secondsand a KBD so import it again let me just move it
3:53:093 hours, 53 minutes, 9 secondsto its place here okay KBD And inside I'm just going to do well I'm just going
3:53:163 hours, 53 minutes, 16 secondsto write the shortcut which will be the letter K and the command. I'm going to give this a class name BG accent and the
3:53:243 hours, 53 minutes, 24 secondsborder. There we go. And for the button itself it will have a couple of class names. So let me go ahead and add them here so you can see it. Just a second.
3:53:373 hours, 53 minutes, 37 secondsflex items center gap 2 text muted foreground text extra small on hover text foreground and transition colors.
3:53:473 hours, 53 minutes, 47 secondsThere we go. So yeah, this is how it's going to look like. All right, now let's
3:53:543 hours, 53 minutes, 54 secondsgo ahead and let's actually render the items. So outside of this div add an
3:54:023 hours, 54 minutes, 2 secondsunordered list element ul and let's do projects do map
3:54:123 hours, 54 minutes, 12 secondsget the individual project here and I'm going to render project item here let's
3:54:203 hours, 54 minutes, 20 secondsgive the unordered list a class name flex flex column and for the project
3:54:283 hours, 54 minutes, 28 secondsitem itself Let's pass in a key of project ID and then data project. And now let's
3:54:363 hours, 54 minutes, 36 secondsgo ahead and let's actually create the project item. And we're going to do this in the very same com uh the very same
3:54:443 hours, 54 minutes, 44 secondsfile, right? So it's easier. So I'm going to do this below here. Or maybe we should do it above so we don't reference
3:54:533 hours, 54 minutes, 53 secondsit before it's created. project item will accept data and the data type will be a type of document.
3:55:033 hours, 55 minutes, 3 secondsUh we can import doc doc not from zod from
3:55:123 hours, 55 minutes, 12 secondsconvex. So let me go ahead and find convex generated uh data model. Is it doc?
3:55:243 hours, 55 minutes, 24 secondsI think it is doc and then we have to define from
3:55:323 hours, 55 minutes, 32 secondsprojects. Okay, I think I'm not uh importing this correctly.
3:55:393 hours, 55 minutes, 39 secondsThe doc is used but it's never read. I think I just have to finish the function. There we go. Yes.
3:55:473 hours, 55 minutes, 47 secondsSo, make sure that we are using the data here. We gave it a proper type.
3:55:523 hours, 55 minutes, 52 secondsAnd now I'm going to go ahead and use a link component from next link. So I'm going to give this an href of forward/
3:56:003 hours, 56 minutesprojects and then data ID like that. Let's go ahead and give the
3:56:083 hours, 56 minutes, 8 secondslink a class name. So I like to have my attributes one below another like so. So it is going to have a couple of class
3:56:153 hours, 56 minutes, 15 secondsnames as well. Let me go ahead and add them here.
3:56:193 hours, 56 minutes, 19 secondstext small text foreground with a 60% opacity font medium on hover text
3:56:263 hours, 56 minutes, 26 secondsforeground padding on the yaxis one flex items center justify between full width
3:56:343 hours, 56 minutes, 34 secondsand it's also going to be a group so now inside of here I'm going to open a div with a class name flex items center and
3:56:433 hours, 56 minutes, 43 secondsgap 2 let me fix my typo here and inside of Here we have to render the
3:56:503 hours, 56 minutes, 50 secondsicon of this project. So I will now use globe icon here as default and then I'm going to change it later. So make sure
3:56:573 hours, 56 minutes, 57 secondsyou just import uh Lucid React here, the globe icon.
3:57:043 hours, 57 minutes, 4 secondsSo that's the first thing we're going to have. And then I will add an arrow right icon again from Lucid React. Make sure
3:57:133 hours, 57 minutes, 13 secondsyou import that. So, outside of this div and then uh let me see if I
3:57:223 hours, 57 minutes, 22 secondsuh my apologies. No, not yet. We're not going to have this. Instead, let's just add a span. And in here, we would have to format uh the timestamp.
3:57:353 hours, 57 minutes, 35 secondsAnd for that, we're going to use date FNS. So, let's mpm install date FNS.
3:57:433 hours, 57 minutes, 43 secondsSo we have to now import format distance to now. And let's go
3:57:523 hours, 57 minutes, 52 secondsahead and create a little helper function here.
3:57:563 hours, 57 minutes, 56 secondsSo I'm just going to add that here at the top. Format timestamp will accept the time stamp which is a type of number
3:58:053 hours, 58 minutes, 5 secondsand it will return format distance to now like this. And inside it's going to pass
3:58:133 hours, 58 minutes, 13 secondsthe new date around that time stamp and then as the second argument options in which we add suffix to be true. Great.
3:58:233 hours, 58 minutes, 23 secondsNow that we have format timestamp inside of this span, let's go ahead and simply use it for project.
3:58:333 hours, 58 minutes, 33 secondsUh so it's called data. Okay.
3:58:363 hours, 58 minutes, 36 secondsData.updated at There we go.
3:58:413 hours, 58 minutes, 41 secondsNow let's go ahead and render the project item here.
3:58:453 hours, 58 minutes, 45 secondsUh project item cannot be used as a JSX probably because I never return anything here. So make sure to return something.
3:58:553 hours, 58 minutes, 55 secondsAnd there we go. So I can already see two of them here. Perfect. Uh now let's go ahead and just style this a bit. So what do we have to style?
3:59:083 hours, 59 minutes, 8 secondsUh first things first about this span here. Oh, we are missing another span which renders the data name.
3:59:193 hours, 59 minutes, 19 secondsThere we go. And let's give this a class name of truncate like so.
3:59:273 hours, 59 minutes, 27 secondsFor this span right here, it will have some larger class name
3:59:343 hours, 59 minutes, 34 secondstext extra small text muted foreground on group hover text foreground with 60% opacity and transition colors. All right.
3:59:463 hours, 59 minutes, 46 secondsUh so we have that and now let's go ahead and check it out. Let's see how it looks like. There we go. You can see how
3:59:553 hours, 59 minutes, 55 secondsI create a new one. Perfect. Uh so uh what should we do next? The new one is
4:00:024 hours, 2 secondsfinished here. Okay. So uh the globe is too big and the globe actually shouldn't be [clears throat] rendered like this.
4:00:104 hours, 10 secondsInstead uh we should develop a function called get project icon. And we're going
4:00:174 hours, 17 secondsto accept project as the prop.
4:00:224 hours, 22 secondsAnd if project import status is completed, we will return FA GitHub icon.
4:00:324 hours, 32 secondsSo make sure to import this from React icons FA. And let's also give it a class
4:00:404 hours, 40 secondsname size 3.5 and text muted foreground.
4:00:474 hours, 47 secondsAnd then let's go ahead and just do other options, right? So if import status is failed, let's import alert circle icon again from Lucid React.
4:01:014 hours, 1 minute, 1 secondThen let's go ahead and check if import status is importing
4:01:084 hours, 1 minute, 8 secondsand let's use the loader 2 icon. So all of them have the same class name except the last one which also has animate
4:01:154 hours, 1 minute, 15 secondsspin. So just make sure to add that. And then let's go ahead and add the default one. So outside of all if clauses, let's return the globe icon.
4:01:274 hours, 1 minute, 27 secondsYou can obviously turn this to a switch case if you prefer it that way. For some reason, I have an aversion towards uh
4:01:344 hours, 1 minute, 34 secondsswitch cases. I just don't like them, but you can of course use them if you prefer. And then replace the globe icon
4:01:404 hours, 1 minute, 40 secondswith get project icon and pass in uh data.
4:01:454 hours, 1 minute, 45 secondsAnd all of ours will have the globe icon, right? But if you want to play around, if you go to one of your
4:01:524 hours, 1 minute, 52 secondsprojects here, I don't know, uh, import status. If I say completed
4:01:594 hours, 1 minute, 59 secondsin quotes and save, you can see that one of them was changed to GitHub. If I
4:02:064 hours, 2 minutes, 6 secondschange another one to failed, you can see it shows an alert.
4:02:134 hours, 2 minutes, 13 secondsAnd if I change another one to importing, it's a spinner. So there we go. Those are all the instances that can happen.
4:02:224 hours, 2 minutes, 22 secondsGreat.
4:02:254 hours, 2 minutes, 25 secondsNow, let's go ahead and show the last project we worked on into a separate container simply so we have some better
4:02:324 hours, 2 minutes, 32 secondsuh user experience here. So I'm just going to copy this because it's identical as what we're going to build and it's going to be called a continue card like this.
4:02:434 hours, 2 minutes, 43 secondsSo it will have the exact same props here. And in order to make it immediately visible, let's go back inside of projects list here. And then
4:02:524 hours, 2 minutes, 52 secondslet's go ahead and do the thing with most recent and the rest. So now
4:03:004 hours, 3 minuteslet's use the rest.length and let's use rest.m map which will as
4:03:074 hours, 3 minutes, 7 secondsyou can see remove one. And then what we can do is just do continue card and pass in the project or let's do data most recent.
4:03:194 hours, 3 minutes, 19 secondsGreat. Now let's go ahead and develop the continue
4:03:244 hours, 3 minutes, 24 secondscard. Uh inside of here let's return a div with a class name flex flex call and
4:03:344 hours, 3 minutes, 34 secondsgap 2. Then inside of it, let's add a label span with a text last updated and text extra small text muted foreground.
4:03:484 hours, 3 minutes, 48 secondsUh, and that's it. Then let's add a button, but this time a button from components
4:03:574 hours, 3 minutes, 57 secondsUI button. There we go. And let's go ahead and give it a few props. So, it's
4:04:034 hours, 4 minutes, 3 secondsgoing to have a variant of outline. It's going to have an as child prop. And it's going to have the following class name.
4:04:134 hours, 4 minutes, 13 secondsHeight auto items start justify start padding for BG background border rounded
4:04:224 hours, 4 minutes, 22 secondsnone flex flex column and gap two. Then let's render a link.
4:04:304 hours, 4 minutes, 30 secondsLet's give this an href forward slash projects and then render the data underscore id here.
4:04:414 hours, 4 minutes, 41 secondsAnd the only class name the link will have is group.
4:04:474 hours, 4 minutes, 47 secondsThen let's go ahead and render a div inside with a flex items center justify between and with full class name.
4:04:594 hours, 4 minutes, 59 secondsThen let's go ahead and open a new div inside flex item center and gap 2. And
4:05:084 hours, 5 minutes, 8 secondsthen inside of here, we're going to render get project icon for that specific project we are continuing our work on.
4:05:204 hours, 5 minutes, 20 secondsAnd next to it, we're going to add a span with font medium and truncate class name to render the name.
4:05:304 hours, 5 minutes, 30 secondsAnd then outside of this div, let's render an arrow right icon from lucid
4:05:384 hours, 5 minutes, 38 secondsreact with a class name size 4 text muted foreground group hover translate x0.5 and transition transform. There we go.
4:05:504 hours, 5 minutes, 50 secondsLike this.
4:05:534 hours, 5 minutes, 53 secondsNow let's go ahead and render the format timestamp as well. outside of this div
4:06:024 hours, 6 minutes, 2 secondstext extra small text muted foreground and let's render the time stamp. There we go. So now this is our kind of last
4:06:124 hours, 6 minutes, 12 secondsworked on project. So we can access it easily here so we don't have to search it through here. Excellent. So this is
4:06:204 hours, 6 minutes, 20 secondsnow working pretty good. Uh, what I want to test is what happens when I have no projects.
4:06:294 hours, 6 minutes, 29 secondsUh-huh. That's what happens. So, let's go ahead and make sure that inside of projects list only if most recent
4:06:384 hours, 6 minutes, 38 secondsexists, we show that. Otherwise, we don't render anything. There we go. So, let's click new here.
4:06:464 hours, 6 minutes, 46 secondsAnd there we go. That's how it looks like. And now I want to show you something that we can do to uh improve our hook actually.
4:06:584 hours, 6 minutes, 58 secondsSo instead of use projects, if you find use create project, you can see there's kind of a slight delay
4:07:074 hours, 7 minutes, 7 secondshappening, right? And during that delay, we don't even block this. So what we can actually do is we can add a optimistic
4:07:164 hours, 7 minutes, 16 secondsmutation. So with optimistic uh update like this and let's just push a new
4:07:244 hours, 7 minutes, 24 secondsproject to the list sooner. So let's open the local store and the arguments and then let's go ahead and let's get all the existing projects.
4:07:384 hours, 7 minutes, 38 secondsSo existing projects using local store get query API projects get if existing
4:07:474 hours, 7 minutes, 47 secondsprojects is not undefined meaning they have loaded let's go ahead and kind of
4:07:524 hours, 7 minutes, 52 secondssimulate a new project so date now const
4:07:594 hours, 7 minutes, 59 secondsnew project will be an object underscore id will use crypto random
4:08:074 hours, 8 minutes, 7 secondsUyu ID and we are we have to cast that as the ID
4:08:154 hours, 8 minutes, 15 secondsfrom convex. So make sure you add this and let's also add doc here.
4:08:234 hours, 8 minutes, 23 secondsBesides ID we will have creation time which will use now name which will use
4:08:314 hours, 8 minutes, 31 secondsarguments.name name, owner ID which will be anonymous
4:08:374 hours, 8 minutes, 37 secondsupdated ad which will be now uh we could also use user ID
4:08:464 hours, 8 minutes, 46 secondsuse out from clerk nextjs and then we could pass user ID here.
4:08:554 hours, 8 minutes, 55 secondsI think that should work too. So you can import user uh use out here. So we don't pass anonymous.
4:09:034 hours, 9 minutes, 3 secondsAnd then what we have to do with this new project is call the local store and
4:09:094 hours, 9 minutes, 9 secondsset the query API projects get skip the arguments part and then inside of here
4:09:194 hours, 9 minutes, 19 secondslet's go ahead and add new project to the list of existing projects.
4:09:264 hours, 9 minutes, 26 secondsAnd let me just see what type problems do we have here.
4:09:324 hours, 9 minutes, 32 secondsSo we have date now and this can actually be fixed with a comment. Actually cannot call impure function.
4:09:414 hours, 9 minutes, 41 secondsLet's just go ahead and add slint disable react hooks purity. So that should get rid of that.
4:09:514 hours, 9 minutes, 51 secondsThis is what I've added. And now I'm trying to figure out uh ah I see.
4:09:594 hours, 9 minutes, 59 secondsSo let's just use anonymous it doesn't matter either way. This is
4:10:074 hours, 10 minutes, 7 secondsnot uh back end anyway. So now we have optimistic update and if I'm correct this should now appear instantly and I
4:10:164 hours, 10 minutes, 16 secondsthink it does. It's like significantly faster. Let me go ahead and delete all of them again so we can test it out.
4:10:234 hours, 10 minutes, 23 secondsSo now we don't even need like any loading state because it's instant like it's takuck. It's super fast. Great. So
4:10:314 hours, 10 minutes, 31 secondsyes, you can do optimistic updates with convex as well. So I believe there's one thing left to do here and that is to
4:10:394 hours, 10 minutes, 39 secondsimplement the view all and the actually it makes no sense to implement shortcuts because shortcuts will open dialogues.
4:10:474 hours, 10 minutes, 47 secondsSo the only one that makes sense is the view all one.
4:10:534 hours, 10 minutes, 53 secondsSo, we're going to in uh we're going to create a project command dialogue. So, inside of components,
4:11:014 hours, 11 minutes, 1 secondnew file projects command- dialogue.tsx.
4:11:074 hours, 11 minutes, 7 secondsLet's mark it as use client. And let's go ahead and import everything we are going to need. So, uh okay, we actually
4:11:164 hours, 11 minutes, 16 secondsdon't need use client because it's already within a client component. So use router f a github
4:11:244 hours, 11 minutes, 24 secondsthe following icons from lucid react alert circle icon globe icon loader to icon. Then we're going to need all of
4:11:324 hours, 11 minutes, 32 secondsthese from components UI command. So dialogue empty group input item and list. All of these come from chats and
4:11:414 hours, 11 minutes, 41 secondsUI. And last but not least use projects from hooks use projects.
4:11:484 hours, 11 minutes, 48 secondsThen let's create an interface project command dialogue props to accept a boolean called open and a function on
4:11:584 hours, 11 minutes, 58 secondsopen change which will be used to modify that boolean.
4:12:034 hours, 12 minutes, 3 secondsThen let's go ahead and export the following function projects command
4:12:104 hours, 12 minutes, 10 secondsdialogue using our projects command dialogue props and the structuring the props above. Perfect. Let's define the router here. Let's define projects.
4:12:234 hours, 12 minutes, 23 secondsLet's quickly define handle select method. So whenever we select one of the projects from this dialogue, we will get
4:12:314 hours, 12 minutes, 31 secondsproject ID from that selection. And we can use the router.push method to
4:12:384 hours, 12 minutes, 38 secondsredirect to projects project ID like that. And then let's call on open change
4:12:454 hours, 12 minutes, 45 secondsfalse. So we immediately close this dialogue. Great.
4:12:514 hours, 12 minutes, 51 secondsJust make sure you have imported use router from next navigation because in the previous versions it had another
4:12:584 hours, 12 minutes, 58 secondsone. So now I'm going to go inside of projects list. I'm going to find this
4:13:064 hours, 13 minutes, 6 secondsfunction get project icon and I'm going to copy it. So, the entire function
4:13:134 hours, 13 minutes, 13 secondsand I'm going to go ahead and let's see. I'm going to add it up here.
4:13:224 hours, 13 minutes, 22 secondsI will see if this ends up being identical. We can export it. But for now, we're just reusing it in two
4:13:294 hours, 13 minutes, 29 secondsplaces. Uh, and yeah, let's just do doc here. We have to import this from convex
4:13:374 hours, 13 minutes, 37 secondsgenerated data model. So, make sure you have this import, we now have get project icon. Perfect. And okay, the
4:13:454 hours, 13 minutes, 45 secondsonly difference is going to be the size of the icon. So, instead of 3.5,
4:13:524 hours, 13 minutes, 52 secondswe're going to use four. It's just a subtle difference, but it makes it look a little bit better for the dialogue.
4:13:594 hours, 13 minutes, 59 secondsRight. And now inside of here, let's return. And then let's go ahead and render the everything we need. Right? We
4:14:074 hours, 14 minutes, 7 secondsneed the command dialogue. The command dialogue should have open and unopen change which we can immediately pass
4:14:154 hours, 14 minutes, 15 secondsalong. Let's give it a title and description relevant to what they do.
4:14:214 hours, 14 minutes, 21 secondsSearch projects. Search and navigate to your project. Let's render a command input with a placeholder. Search
4:14:294 hours, 14 minutes, 29 secondsprojects. And then let's go ahead and render the command list. Let's go ahead
4:14:354 hours, 14 minutes, 35 secondsand define the empty state which will simply show the label no projects found.
4:14:434 hours, 14 minutes, 43 secondsThen let's go ahead and add a command group with a heading of projects. And then inside of here, let's iterate over
4:14:504 hours, 14 minutes, 50 secondsour projects with a question mark in case they are empty. And in here, we are going to render the command item.
4:14:594 hours, 14 minutes, 59 secondsUh, looks like I'm doing something incorrect here. Let me just figure out what There we go.
4:15:064 hours, 15 minutes, 6 secondsI was missing uh another parenthesis here, right? So I have to add it. So let's give the command item a key of
4:15:154 hours, 15 minutes, 15 secondsproject ID. Let's give it a value of project
4:15:214 hours, 15 minutes, 21 secondsname dash project ID. The reason we are doing this is because if you just use
4:15:284 hours, 15 minutes, 28 secondsyou need to use the project name because that is what will be highlighted when you search. So it's going to look for
4:15:354 hours, 15 minutes, 35 secondsvalue. The problem comes when you have projects with the same name and then all of them are highlighted. So that's why we kind of combine it with project ID.
4:15:464 hours, 15 minutes, 46 secondsSo they are kind of unique in their own way. And let's add on select to call our
4:15:544 hours, 15 minutes, 54 secondshandle select method and redirect to the project ID. Then let's go ahead and render the get project icon and finally the project name.
4:16:074 hours, 16 minutes, 7 secondsNow we have to go back to the projects view page and let's add a state.
4:16:164 hours, 16 minutes, 16 secondsCommand dialogue open. set command dialogue open control through use state.
4:16:234 hours, 16 minutes, 23 secondsI'm just going to move this to the top.
4:16:264 hours, 16 minutes, 26 secondsAnd now that we have this, we can go ahead and render it in the return. So I'm going to do that within this
4:16:344 hours, 16 minutes, 34 secondsfragment. So I'm going to encapsulate the entire content of the return inside of a fragment.
4:16:434 hours, 16 minutes, 43 secondsSo my order is semantically corre correct because the projects command
4:16:504 hours, 16 minutes, 50 secondsdialogue is above all of those other elements. Right? So make sure to import projects command dialogue which we have
4:16:594 hours, 16 minutes, 59 secondsjust developed here. Right? Make sure you have exported it correctly.
4:17:044 hours, 17 minutes, 4 secondsAnd I'm going to go ahead and give it open and on open change. There we go.
4:17:124 hours, 17 minutes, 12 secondsAnd now what we have to do is we have to pass the on view all option properly. So
4:17:204 hours, 17 minutes, 20 secondsfind project list and pass in the on view all to call set command dialogue open and set it to
4:17:294 hours, 17 minutes, 29 secondstrue. Now I just have to confirm that I'm using on view all within the projects list. Looks like I'm not. So
4:17:374 hours, 17 minutes, 37 secondsI'm just going to go ahead and find my uh recent projects here. And then here we go. This button right here will call on click on view all. Let's test it out.
4:17:494 hours, 17 minutes, 49 secondsSo I'm going to go ahead and click view all. And here we go. So let's search for cougar. There we go. Perfect. And
4:17:574 hours, 17 minutes, 57 secondsclicking on it will redirect me to a 404 because well we haven't developed that yet. So what's left to do now is just
4:18:054 hours, 18 minutes, 5 secondsadd a shortcut. So let's go inside of projects view back here and using use effect we can very simply achieve this
4:18:144 hours, 18 minutes, 14 secondseffect. So use effect make sure you have imported it from
4:18:204 hours, 18 minutes, 20 secondsreact same place as use state const handle key down
4:18:274 hours, 18 minutes, 27 secondsevent keyboard event if e do meta key or econt control key is
4:18:364 hours, 18 minutes, 36 secondsincluded and then if e key is equal to k e prevent default set command and
4:18:444 hours, 18 minutes, 44 secondsdialogue open to true. As simple as that. Let's add document add event listener
4:18:534 hours, 18 minutes, 53 secondson key down and passing the handle key down. And super important make sure to unmount it. So document remove event
4:19:024 hours, 19 minutes, 2 secondslistener on key down handle key down.
4:19:104 hours, 19 minutes, 10 secondsAnd uh let's move the state above the use effect like this so it can
4:19:164 hours, 19 minutes, 16 secondsproperly access it. So if you try pressing on the control key or the
4:19:244 hours, 19 minutes, 24 secondscommand key if you have Mac OS and hold the letter K at the same time you can see you can now open view all. Amazing.
4:19:354 hours, 19 minutes, 35 secondsAnd to end the chapter, I think the only interesting thing to do is add a real logo to our app. So I found the logo on
4:19:444 hours, 19 minutes, 44 secondsuntitled UI. And usually I also use logo Ipsum. So whichever of those you like,
4:19:534 hours, 19 minutes, 53 secondsgo ahead and just click copy, you know, and that will copy the SVG. I think it works very similarly here. There we go.
4:20:004 hours, 20 minutesYeah. So, Untitled UI and Logo Ipsum are my go-tos for finding logos. Or if you want the exact one that I have, uh,
4:20:084 hours, 20 minutes, 8 secondsusing the link on the screen, you can visit my assets, find logo. SVG, I'm going to copy raw file. And then I'm
4:20:184 hours, 20 minutes, 18 secondsjust going to go ahead inside of source, my apologies, inside of public, and I will create logo.svg.
4:20:284 hours, 20 minutes, 28 secondsUh, I will confirm this. open using standard editor and I will paste inside.
4:20:354 hours, 20 minutes, 35 secondsThere we go. That's how I do it. You can drag and drop if you want. There we go.
4:20:404 hours, 20 minutes, 40 secondsThis is the logo. So, let's go inside of page.tsx projects view and let's uh remove the
4:20:484 hours, 20 minutes, 48 secondsversel one and use our logo. SVG. And yeah, this is a warning that we should
4:20:544 hours, 20 minutes, 54 secondsuse next image instead of image. Um, if you want to, you can just uh turn that
4:21:014 hours, 21 minutes, 1 secondoff. Let me use uh for this line. No,
4:21:094 hours, 21 minutes, 9 secondsnot working. Okay. Yeah, it's just going to show like this. It's okay. It's just a warning. And that's it. I believe this
4:21:164 hours, 21 minutes, 16 secondsis exactly what we've envisioned. Um, obviously, we don't have the dialogues, but those will come. And uh yeah,
4:21:254 hours, 21 minutes, 25 secondseverything else works just uh as it should. Uh let me see. I think the only
4:21:324 hours, 21 minutes, 32 secondsthing we might want to improve could be inside of convex projects maybe
4:21:394 hours, 21 minutes, 39 secondsthe way maybe the order of fetching these. So we show the newest ones first.
4:21:464 hours, 21 minutes, 46 secondsLet me see.
4:21:494 hours, 21 minutes, 49 secondsYes, we can do that. So inget let's go ahead and do dot order descending
4:21:574 hours, 21 minutes, 57 secondsand in get partial let's do the same thing descending.
4:22:024 hours, 22 minutes, 2 secondsLet me refresh and that should reverse it now. Yes, because when you create the newest one that one should become the last the last updated one. There we go.
4:22:124 hours, 22 minutes, 12 secondsSo now they are constantly switching. You can see how fast this creation is.
4:22:154 hours, 22 minutes, 15 secondsThat's optimistic uh mutation. Amazing, amazing job. I'm super satisfied with how this went. So, let's go ahead and
4:22:244 hours, 22 minutes, 24 secondsreview all of these changes. There's a lot of them, right? So, I'm going to go ahead and do get add and then a dot get commit.
4:22:354 hours, 22 minutes, 35 secondsThis is chapter 7. So, 07 projects.
4:22:434 hours, 22 minutes, 43 secondsThere we go. and then get checkout-b07- projects.
4:22:504 hours, 22 minutes, 50 secondsI'm I keep checking if I'm correct with my names now uh because of that number I
4:22:554 hours, 22 minutes, 55 secondsmissed. So, git push origin07- projects.
4:23:024 hours, 23 minutes, 2 secondsThere we go. Perfect. So, we have officially pushed that branch. And now,
4:23:094 hours, 23 minutes, 9 secondslet's go ahead and review it. So I'm going to open a pull request and this time we can definitely let code rabbit review all of these changes we just did.
4:23:224 hours, 23 minutes, 22 secondsSo in this pull request we added projects interface with search functionality using the command
4:23:294 hours, 23 minutes, 29 secondsdialogue. We added project creation which now generates random project names automatically. Recent projects overview
4:23:374 hours, 23 minutes, 37 secondsdisplays the most updated projects. And we also have added the export status for tracking projects. If you remember, uh I
4:23:464 hours, 23 minutes, 46 secondsadded this because I thought we might use it for the UI. Looks like we only use the import status, but still uh it's
4:23:534 hours, 23 minutes, 53 secondsnot going to hurt. We removed the demo and the example pages and we added new dependencies. And looks like our code
4:24:004 hours, 24 minuteswas very good. No comments from code rabbit besides some nitpick comments which are also interesting. As you can
4:24:084 hours, 24 minutes, 8 secondssee exactly what we said. We could potentially extract get project icon to avoid duplication.
4:24:164 hours, 24 minutes, 16 secondsAnd in the projects view it is detecting that we are missing a keyboard shortcut which is very interesting because the only thing it knows is that one of them
4:24:254 hours, 24 minutes, 25 secondsis implemented right and it only knows that in the UI we show the other one.
4:24:314 hours, 24 minutes, 31 secondsvery very interesting but yeah we will add that later when we do uh again consider using the next JS image
4:24:384 hours, 24 minutes, 38 secondscomponent so same as the uh llinter uh we do have some buttons with no functionality like the import button we
4:24:464 hours, 24 minutes, 46 secondswill add that later in here we added slint disable for the date now so it
4:24:534 hours, 24 minutes, 53 secondssuggests explaining why we did that so you can see it even agrees with us it just wants us to explain
4:25:014 hours, 25 minutes, 1 secondWhy? Overall very very good. Yes, we can definitely you know validate the limit parameter but yes most of these are just
4:25:094 hours, 25 minutes, 9 secondsyou know nitpick comments but still very cool to have someone else take a look at the code before we merge simply so we know if we made any serious mistakes.
4:25:194 hours, 25 minutes, 19 secondsAmazing. So that is a branch07 project. Now, let's check out back to our main branch.
4:25:284 hours, 25 minutes, 28 secondsAnd let me go ahead and just try like this. There we go. Get check out. My apologies. Get pool origin main. This
4:25:374 hours, 25 minutes, 37 secondsshould now synchronize our local state with what we just merged. And as always, I like to confirm this by going inside
4:25:444 hours, 25 minutes, 44 secondsof my source control, opening the graph below, and here we have it. 07 projects detached into its own branch and then
4:25:534 hours, 25 minutes, 53 secondsmerged back to main. I believe that marks the end of this chapter. We built the landing page with Polaris branding.
4:26:014 hours, 26 minutes, 1 secondWe built the project creation and get feature, project list layout and finally keyboard shortcuts and the command
4:26:094 hours, 26 minutes, 9 secondsdialogue. Amazing amazing job and see you in the next chapter.
Chapter 9: 08 IDE Layout
4:26:144 hours, 26 minutes, 14 secondsIn this chapter, we're going to develop our IT layout. We're going to start by creating a dynamic project routing
4:26:224 hours, 26 minutes, 22 secondssystem. Then we're going to build resizable IDE split panes using a package called aotment. We're going to implement a navbar with project actions.
4:26:334 hours, 26 minutes, 33 secondsSet up editor and preview containers and add code preview tab switching functionality. So how is that going to
4:26:424 hours, 26 minutes, 42 secondslook like? Well, we have a finished example here. So this is the finished product. We don't have this yet. And
4:26:504 hours, 26 minutes, 50 secondswe're going to start developing some things here now. So, let me go ahead and show you what the first thing we're going to do is this navbar right here.
4:27:014 hours, 27 minutes, 1 secondOr at least we're going to prepare this navbar, right? So, that's what we're going to implement. And then we're going
4:27:084 hours, 27 minutes, 8 secondsto implement the basic split pane. This will be pain on the left side. And this will be the pane on the uh right side.
4:27:184 hours, 27 minutes, 18 secondsAnd besides that, we're going to implement the ability to switch between code and preview, but we're not actually
4:27:274 hours, 27 minutes, 27 secondsgoing to implement any of the contents inside. Right? So, let's go ahead and start building. Make sure you have your app running at npm rundev.
4:27:394 hours, 27 minutes, 39 secondsAnd what we've built last is this the landing page. And currently if we try to
4:27:464 hours, 27 minutes, 46 secondsgo to a project, we get a 404. So let's start with resolving that. And let's
4:27:534 hours, 27 minutes, 53 secondsalso get rid of our user button on every single screen. So I'm going to go ahead
4:28:004 hours, 28 minutesinside of source components providers. I will remove the user button from the authenticated state and I will remove it
4:28:074 hours, 28 minutes, 7 secondsfrom the imports. Speaking of unused imports, I believe there's one inside of app layout. At least I have it. So I'm
4:28:164 hours, 28 minutes, 16 secondsjust going to remove it. Great. So now we have a clean 404. Now let's fix it.
4:28:234 hours, 28 minutes, 23 secondsSo how do we do that? Well, let's take a look at our URL localhost 3000 projects. And here's the
4:28:324 hours, 28 minutes, 32 secondstricky part. We now have something dynamic. So far, we've only learned how
4:28:394 hours, 28 minutes, 39 secondsto create the URLs when we know exactly the words. But it's not difficult to make it dynamic either. So, we already
4:28:484 hours, 28 minutes, 48 secondsknow the first part. Inside of the app folder, create a folder called projects.
4:28:544 hours, 28 minutes, 54 secondsAnd now, what do we put inside? Well, it's actually very simple. open square brackets and then type the name of the
4:29:024 hours, 29 minutes, 2 secondsvariable where you want to store the param. In our case, that's going to be project ID with a capitalized letter I.
4:29:114 hours, 29 minutes, 11 secondsAnd then inside add a page.tsx.
4:29:154 hours, 29 minutes, 15 secondsAnd you will probably notice that you will now get a different error here.
4:29:194 hours, 29 minutes, 19 secondsThat's because this is a reserved file name. So it officially registered this route and we are hitting that route
4:29:264 hours, 29 minutes, 26 secondshere. But the problem is page is not exporting anything. So it's not really not found anymore. It's just incorrect.
4:29:354 hours, 29 minutes, 35 secondsThat's why we have to export something.
4:29:384 hours, 29 minutes, 38 secondsProject id page div. And let's prepare just a label which is supposed to show the project ID
4:29:474 hours, 29 minutes, 47 secondswhich we've entered. So how do we access this project ID now? Well, through
4:29:534 hours, 29 minutes, 53 secondsparams. So let's go ahead and prepare the params here and let's give it a type. A type of params is a promise.
4:30:054 hours, 30 minutes, 5 secondsAnd then inside what variable we expect?
4:30:094 hours, 30 minutes, 9 secondsWell, we expect project ID. So let's go ahead and add it here. And let's give it a type of string. And then let's go
4:30:184 hours, 30 minutes, 18 secondsahead and make this entire thing asynchronous like this.
4:30:244 hours, 30 minutes, 24 secondsAnd let's destructure project ID from await params. And let's
4:30:304 hours, 30 minutes, 30 secondsrender project ID. There we go. So now, no matter what you type in your URL,
4:30:374 hours, 30 minutes, 37 secondslike 1 2 3 4, you should still get the same result. See, it should be immediately reflected. The reason I
4:30:464 hours, 30 minutes, 46 secondsexplicitly mentioned with a capital letter I is because people often overlook this. If I rename this to
4:30:554 hours, 30 minutes, 55 secondssomething like this and update the imports, you don't have to do this. You can see it just causes a bunch of cache issues, right?
4:31:044 hours, 31 minutes, 4 secondsAnd if I refresh here, uh, looks like it's actually still working. That's interesting. I'm
4:31:114 hours, 31 minutes, 11 secondsinterested now because I wanted to teach you a lesson. But maybe I actually learned something new. So I'm purposely deleting next to get rid of the cache
4:31:214 hours, 31 minutes, 21 secondsbecause what I'm expecting here is that this shouldn't load and it doesn't. Okay, so it was just cache, right?
4:31:284 hours, 31 minutes, 28 secondsBasically, if you are not careful with how you name your folder, you also you will probably, you know, uh write the
4:31:374 hours, 31 minutes, 37 secondswrong variable here. That's what I was trying to tell you. That's why it's important to do that. So if you wanted to fix this, you would now have to use
4:31:454 hours, 31 minutes, 45 secondslowercase project ID. You can see that resolves it. But we don't want to use that. We want to use the proper camel case. So because of that, I'm going to
4:31:534 hours, 31 minutes, 53 secondsrename it once more. And then again, I'm going to have to update my imports here and most likely remove cache and run it again.
4:32:074 hours, 32 minutes, 7 secondsLet's restart and we should be good to go. There we go. Now let's go ahead and let's create the layout. So layout is
4:32:154 hours, 32 minutes, 15 secondsalso a reserved file name here. And the reason we're using layout is because layout will not rerender on every
4:32:224 hours, 32 minutes, 22 secondsproject ID change, but we are kind of going to need to have it to be uh static. It's kind of easier to explain
4:32:294 hours, 32 minutes, 29 secondsif we just start building it. So it's quite similar. Let's go ahead and do layout here.
4:32:394 hours, 32 minutes, 39 secondsAnd uh well for now let's just render the children because that's kind of the only important thing. We've never
4:32:484 hours, 32 minutes, 48 secondswritten a custom layout before. So I will stop to explain a bit. So the type will be react node and that's not where
4:32:554 hours, 32 minutes, 55 secondsI type this. My apologies. This is where I type that.
4:33:014 hours, 33 minutes, 1 secondAnd just by saving uh everything should work perfectly fine, right? So what's the purpose of a layout? Why did I just
4:33:094 hours, 33 minutes, 9 secondsdo this? First of all, it's a reserved file name. So make sure you didn't misspell it. Second of all, it's going to be used like this. Imagine this is a
4:33:174 hours, 33 minutes, 17 secondsnavbar. And [snorts] I know it doesn't seem like much yet, but if I create another thing here, for
4:33:244 hours, 33 minutes, 24 secondsexample, settings page, right? So imagine each project has a settings page. And if I add page inside, you don't have to do this. I'm just trying
4:33:324 hours, 33 minutes, 32 secondsto demonstrate. Settings page div. Whoops.
4:33:384 hours, 33 minutes, 38 secondsProject settings page. How do I access this now? So I go, you take a look at
4:33:444 hours, 33 minutes, 44 secondsthe URL. Projects 1 2 3 4/ That's how I access it. What are you
4:33:524 hours, 33 minutes, 52 secondsnoticing here? So this content has changed but the layout content hasn't
4:33:594 hours, 33 minutes, 59 secondschanged. Right? So I'm just being semantically correct when it comes to the things I want to put in my layout and the things I want to keep in the
4:34:074 hours, 34 minutes, 7 secondspage. The layouts are also less prone to rerendering making the app more optimized. For now we can get rid of the
4:34:154 hours, 34 minutes, 15 secondssettings one. We are not going to need it. I just wanted to explain to you in that way. So yes, let's go back to just
4:34:224 hours, 34 minutes, 22 secondsprojects and then 1 2 3 4. Great. Let's now focus on this layout.tsx.
4:34:304 hours, 34 minutes, 30 secondsAnd we can actually access the params here as well. And they are the exact same type. So let's add them. There we
4:34:394 hours, 34 minutes, 39 secondsgo. And let's make sure layout is asynchronous as well. And let's dstructure it.
4:34:484 hours, 34 minutes, 48 secondsAnd let's change our return to very simply be project ID layout which we don't yet have
4:34:564 hours, 34 minutes, 56 secondsand render children inside. Let me go ahead and add parentheses around this so
4:35:024 hours, 35 minutes, 2 secondsit's easier to look at. And the only thing we're going to pass as a prop will be the project ID. So when I save, we're
4:35:114 hours, 35 minutes, 11 secondsgoing to get an error because project ID layout doesn't exist. So let's go ahead and create it. Inside of source features
4:35:194 hours, 35 minutes, 19 secondsproject components, let's create project id layout.tsx.
4:35:264 hours, 35 minutes, 26 secondsI'm going to mark this as use client.
4:35:304 hours, 35 minutes, 30 secondsAnd then I'm going to export const project ID layout.
4:35:364 hours, 35 minutes, 36 secondsThe children uh the props I will expect uh whoops. The props I expect are children and the project ID.
4:35:464 hours, 35 minutes, 46 secondsChildren are a type of react react node and project ID is a type of string.
4:35:544 hours, 35 minutes, 54 secondsAnd then let's go ahead and return a div. And let's just render the children so we know it's working.
4:36:034 hours, 36 minutes, 3 secondsNow let's go ahead inside of app projects layout and let's import project ID layout from features projects
4:36:104 hours, 36 minutes, 10 secondscomponents project ID layout and since I can see my children it means everything is correct we can now focus exclusively
4:36:184 hours, 36 minutes, 18 secondson the project ID layout inside of the project ID layout we're going to go ahead and give this
4:36:264 hours, 36 minutes, 26 secondscontainer div a class name of full width height of screen flex and flex column
4:36:344 hours, 36 minutes, 34 secondsand then we're going to implement an actual navbar component and pass along the project ID.
4:36:424 hours, 36 minutes, 42 secondsLet's go ahead and let's implement the navbar component. So again inside of projects let's create a new file called
4:36:504 hours, 36 minutes, 50 secondsnavbar dsx and I'm going to import a type of ID
4:36:574 hours, 36 minutes, 57 secondsfrom convex generated data model. I will export const navbar.
4:37:054 hours, 37 minutes, 5 secondsI'm going to prepare the types here. So we expect the project ID and I'm going to do something different. I'm going to give it a type of ID projects. The
4:37:144 hours, 37 minutes, 14 secondsreason I'm doing this is so that I can easily pass it to convex queries. So in order to make this work, first of all,
4:37:224 hours, 37 minutes, 22 secondslet's make sure we return something. So hello navbar. Then let's go back to project ID layout. Let's import the
4:37:294 hours, 37 minutes, 29 secondsnavbar from dot /navbar and uh you can save and it will work. So we now have hello navbar here but the project ID is
4:37:384 hours, 37 minutes, 38 secondsincorrect. So we're just going to do the same thing here. Instead of project ID layout give this a type of ID projects.
4:37:464 hours, 37 minutes, 46 secondsID is also a string but we are just making sure that it's works as an identifier for convex.
4:37:544 hours, 37 minutes, 54 secondsGreat. So now that we have this project ID, uh let's go ahead and let's style this a bit. We are going to use project
4:38:024 hours, 38 minutes, 2 secondsID later. For now, let's give this a flex justify between items center gap X2
4:38:104 hours, 38 minutes, 10 secondspadding two background color of sidebar border bottom and border Border.
4:38:204 hours, 38 minutes, 20 secondsActually, we don't need that. We can just do border bottom. And then in here, let's create a div with a class name
4:38:294 hours, 38 minutes, 29 secondsflex items center and gap x2. Let's change the outer one to nav. Actually, I think that makes more sense. Right now,
4:38:374 hours, 38 minutes, 37 secondswhat we have to do is we have to import all the components from shhatsen navbar.
4:38:444 hours, 38 minutes, 44 secondsSo that's going to be breadcrumb. My apologies from shhatsen breadcrumb not navbar. So breadcrumb item link list
4:38:524 hours, 38 minutes, 52 secondspage and separator all from components UI breadcrumb.
4:38:584 hours, 38 minutes, 58 secondsAnd once we have that we're just going to create a composition to render the breadcrumb. So starting with the actual breadcrumb. Then inside we're going to add a breadcrumb item.
4:39:104 hours, 39 minutes, 10 secondsThen we're going to add a breadcrumb list with a class name and another property.
4:39:164 hours, 39 minutes, 16 secondsSo let me just go ahead and properly indent this. So we have a class name
4:39:224 hours, 39 minutes, 22 secondsflex items center gap 1.5 and group forward slash logo. Uh in fact we don't
4:39:294 hours, 39 minutes, 29 secondsneed group logo just this and an as child prop.
4:39:344 hours, 39 minutes, 34 secondsAnd inside of here we're going to render a button. Make sure you import button from components UI button. So it's shad
4:39:424 hours, 39 minutes, 42 secondscen button. The button will have a variant of ghost. It will have a class name of with fit with an exclamation
4:39:524 hours, 39 minutes, 52 secondsmark. This basically means important like override whatever other style it had. Same thing for padding and same
4:40:004 hours, 40 minutesthing for the height. And as child here as well. Then finally inside we're going
4:40:064 hours, 40 minutes, 6 secondsto import link from next link and give it an href to go to a well to the root
4:40:144 hours, 40 minutes, 14 secondspage. So just make sure you've imported link from next link.
4:40:204 hours, 40 minutes, 20 secondsGreat. So what will actually be displayed here? Well, an image. So let's import next image.
4:40:284 hours, 40 minutes, 28 secondsLet me show you what the import looks like. Just a second. There we go. Next image. and I will put it right next to link.
4:40:384 hours, 40 minutes, 38 secondsThe image will have an href, my apologies, a source of forward/logo.
4:40:434 hours, 40 minutes, 43 secondsWe are going to have an alt of logo, width of 20, and a height of 20 as well.
4:40:504 hours, 40 minutes, 50 secondsAnd then next to the image, we're going to have a span polaris.
4:40:554 hours, 40 minutes, 55 secondsLet's go ahead and give this a class name. And let's use the CN util library.
4:41:034 hours, 41 minutes, 3 secondsSo in the first argument here, we're going to put text small and font medium.
4:41:104 hours, 41 minutes, 10 secondsAnd then what I'm going to do is I'm going to go back to projects dash view component.
4:41:184 hours, 41 minutes, 18 secondsAnd in here I'm just going to copy the popins instance.
4:41:234 hours, 41 minutes, 23 secondsAnd then I'm going to go back inside of my navbar here. I'm going to paste this.
4:41:274 hours, 41 minutes, 27 secondsAnd I'm going to import Poppins from next font Google. And I'm just going to move it here at the top. So now we have the popins font again. So I can now add
4:41:374 hours, 41 minutes, 37 secondsa comma and then in the second argument of the CN util font.class name making this have the Poppins font. Great. So
4:41:474 hours, 41 minutes, 47 secondsthat's the first item and the uh now let's go ahead and add a breadcrumb separator and actually it's a self-closing tag.
4:42:004 hours, 42 minutesThe only class name we're going to give it is ml-0 and mr of one.
4:42:084 hours, 42 minutes, 8 secondsAnd then let's add a breadcrumb item again here.
4:42:154 hours, 42 minutes, 15 secondsSo what should we uh write here? Well, we should use the breadcrumb page.
4:42:224 hours, 42 minutes, 22 secondsThat's the one we should use. And inside of here for now let's just do demo project.
4:42:304 hours, 42 minutes, 30 secondsAnd for the class name let's give it text small cursor pointer
4:42:384 hours, 42 minutes, 38 secondshover text primary font medium maximum width of 40 and truncate.
4:42:464 hours, 42 minutes, 46 secondsLet me go ahead and zoom out so we can see how this looks like. So, looks like it's not taking
4:42:544 hours, 42 minutes, 54 seconds100% height. Uh, I apologize.
4:43:044 hours, 43 minutes, 4 secondsOkay, that works. Let me go back here.
4:43:084 hours, 43 minutes, 8 secondsYes, this this should definitely expand to 100% width. So, let me just go ahead and see why that is not happening.
4:43:204 hours, 43 minutes, 20 secondsOh, it is because I gave you an invalid composition. So, instead of breadcrumb, we should have breadcrumb list.
4:43:294 hours, 43 minutes, 29 secondsWe're not using that. So, let's go ahead and encapsulate both of our breadcrumb items within that list. And then let's indent everything together. There we go.
4:43:424 hours, 43 minutes, 42 secondsAnd I'm going to give this a class name of gap zero. All right. So let's take a
4:43:494 hours, 43 minutes, 49 secondslook now. This is our navbar. In here we can see we have what is what will be the
4:43:564 hours, 43 minutes, 56 secondstest the text of the currently loaded project. And in here we have a button to go back. Right. So our next step is to
4:44:044 hours, 44 minutes, 4 secondsactually load the name of the project that will be here. But before we do that we can actually do uh one easy thing. So
4:44:144 hours, 44 minutes, 14 secondslet's go at the bottom here and in here let's just add a class name flex items center and gap 2 and just
4:44:244 hours, 44 minutes, 24 secondsrender user button from clerk nextjs. So make sure you've imported user button from clerk next.js
4:44:334 hours, 44 minutes, 33 secondsand now you have a place to log out. So if you need to change your account you can just go ahead and log out from here.
4:44:404 hours, 44 minutes, 40 secondsGreat. So uh let's see uh what's next.
4:44:454 hours, 44 minutes, 45 secondsSo we can use the project ID to actually load the project. In order to do that, we have to go inside of convex projects.
4:44:544 hours, 44 minutes, 54 secondsDS and we have to develop get by ID. So I'm going to copy the existing get and I will rename it to get by ID.
4:45:064 hours, 45 minutes, 6 secondsThe arguments it's going to accept is ID which will be a type of vid projects.
4:45:134 hours, 45 minutes, 13 secondsSo now that we have the arguments, we also have to extract them here. And the first thing we're going to do is just
4:45:204 hours, 45 minutes, 20 secondsattempt to get the project using await context database get projects and then pass in arguments ID. That's the first
4:45:284 hours, 45 minutes, 28 secondsthing we're going to do. Then we're going to add an if check if the project is missing and we're going to throw new error here. project not found. That's
4:45:364 hours, 45 minutes, 36 secondsthe first check. The second check will confirm if project owner ID is not identical to the current identity.
4:45:484 hours, 45 minutes, 48 secondsMeaning we have to throw a new error unauthorized access to this project
4:45:554 hours, 45 minutes, 55 secondsbecause this user should not be looking at this project. If all uh of these cases pass, we can safely return the
4:46:044 hours, 46 minutes, 4 secondsproject. You might notice um that I'm not sure how well you know Convex, but they've undergone a change recently.
4:46:144 hours, 46 minutes, 14 secondsThis also works just fine because their ids are kind of special. You can
4:46:204 hours, 46 minutes, 20 secondssee you have to define that it's an ID of the projects. So in the past you just
4:46:284 hours, 46 minutes, 28 secondspassed arguments ID and it it immediately knew it has to load projects. They've done an update where you can be more explicit and it's super
4:46:374 hours, 46 minutes, 37 secondscool they made this backwards compatible. So both work but this is the new way. So you should be writing it like this. uh as far as I understand the
4:46:464 hours, 46 minutes, 46 secondsreason they're doing this is a to be more explicit and b to enable uh local running of convex because right now this
4:46:554 hours, 46 minutes, 55 secondsID thing is probably related to the cloud. So if you want to enable someone to run convex 100% locally uh they have
4:47:044 hours, 47 minutes, 4 secondsto fix that first. So they are working towards that and I kind of like this explicitness more. Great. So we have the
4:47:104 hours, 47 minutes, 10 secondsget by ID. Now let's go ahead inside of source features projects hooks use projects and inside of here let's
4:47:194 hours, 47 minutes, 19 secondsimplement a super simple hook use project. So make sure to not name it the
4:47:264 hours, 47 minutes, 26 secondssame. It's use project. It will accept one argument project ID which is a type of ID project. it will return use query
4:47:354 hours, 47 minutes, 35 secondsAPI. projects dot get by id with the argument id of project id. So this is the new route that we have just created.
4:47:454 hours, 47 minutes, 45 secondsRight? And we only accept that. So make sure you have this and click save.
4:47:514 hours, 47 minutes, 51 secondsGreat. Now let's go ahead and go back inside of the navbar.tsx
4:47:584 hours, 47 minutes, 58 secondsand let's load the project. And it should be fairly easy now that we have the hook. So project from use project
4:48:084 hours, 48 minutes, 8 secondsand pass in the project ID. Make sure to import use project from hooks. Use projects. There we go.
4:48:164 hours, 48 minutes, 16 secondsAnd we should probably mark navbar as use client. So let's do that. Use client.
4:48:244 hours, 48 minutes, 24 secondsThere we go. That will get rid of the error. Uh or not. Uh because that's not what the error is. The error is because
4:48:334 hours, 48 minutes, 33 secondswe added a new function but we didn't run or should I say aren't running actively npx convex dev. So make sure
4:48:414 hours, 48 minutes, 41 secondsyou have convex functions ready here and let's do one more refresh. There we go.
4:48:474 hours, 48 minutes, 47 secondsBut still we're not using this project anywhere. So now let's go ahead and scroll down to demo project breath
4:48:564 hours, 48 minutes, 56 secondscrumba page and do project question mark name or loading.
4:49:024 hours, 49 minutes, 2 secondsThere we go. You can see that for a brief second it's going to say loading and then it will change to the name. So
4:49:094 hours, 49 minutes, 9 secondstry with your project and you should see different name for every project.
4:49:164 hours, 49 minutes, 16 secondsExcellent. So now we have to add the ability to rename this and that will be a little bit more tricky but not too
4:49:244 hours, 49 minutes, 24 secondsdifficult don't worry. I want to start uh by actually building the rename mutation. So let's head back inside of
4:49:314 hours, 49 minutes, 31 secondsconvex projects. I'm going to copy get by ID because it's very similar.
4:49:394 hours, 49 minutes, 39 secondsI'm going to rename it to rename and it will accept a name and it will
4:49:474 hours, 49 minutes, 47 secondsaccept an ID and a new name which will be a type of string. There we go. First things first, we do the identity check.
4:49:554 hours, 49 minutes, 55 secondsWe fetch the project. We confirm it exists. We confirm we have access to it.
4:50:014 hours, 50 minutes, 1 secondAnd then what we do is well, we don't have to return anything. Let's just do await context database patch. And again,
4:50:084 hours, 50 minutes, 8 secondsyou can just pass arguments do ID, but I like this more. And this is the new way.
4:50:144 hours, 50 minutes, 14 secondsSo, get used to doing this. Let's pass in the new name. And let's move the updated ad to be date. Now, all right.
4:50:254 hours, 50 minutes, 25 secondsUh, so let's see. Yes. Why does it not exist? Because this isn't a query. This
4:50:324 hours, 50 minutes, 32 secondsis a mutation. So, make sure you change this. And we had it imported from here. Great. And now it should work just fine.
4:50:414 hours, 50 minutes, 41 secondsPerfect. Uh I believe it returns a project ID back. No, it doesn't. Okay.
4:50:484 hours, 50 minutes, 48 secondsNo need to return anything. So we now have the rename mutation. Perfect. Now let's add it to our hook.
4:50:564 hours, 50 minutes, 56 secondsUse projects. Here it is.
4:51:004 hours, 51 minutesSo I'm going to go ahead and uh I'm going to copy use create project because it's more similar to that than anything
4:51:084 hours, 51 minutes, 8 secondselse. So I now have copied the use create project and I'm going to change it. So the argument we're going to
4:51:164 hours, 51 minutes, 16 secondsaccept is project ID. The use mutation we're going to call is projects.reame.
4:51:234 hours, 51 minutes, 23 secondsAnd let's do optimistic update here as well. So instead of calling existing projects, we are going to change this to call an individual existing project.
4:51:364 hours, 51 minutes, 36 secondsRight? So let me just go ahead and see. I'm trying to make this easy to look at.
4:51:444 hours, 51 minutes, 44 secondsOkay. So get query API projects get pi ID which we previously developed and pass in the argument
4:51:534 hours, 51 minutes, 53 secondsID project ID. I think I can collapse this like so.
4:51:584 hours, 51 minutes, 58 secondsJust trying it trying to make it easier to read. Okay.
4:52:024 hours, 52 minutes, 2 secondsSo, now that we have the existing project, let's go ahead and check uh how we should actually update this. So, I'm just going to remove everything inside.
4:52:114 hours, 52 minutes, 11 secondsWe're going to check if we have the existing project meaning it is not undefined and if existing project is not null.
4:52:224 hours, 52 minutes, 22 secondsRight? Because undefined means loading and null means not found. Only then can
4:52:284 hours, 52 minutes, 28 secondswe call our local store set query API dot projects get by ID
4:52:384 hours, 52 minutes, 38 secondsid project ID. So we are going to find it in the uh local cache. And then we're just going to spread the existing
4:52:464 hours, 52 minutes, 46 secondsproject and change the name. And we can also change updated add to be data.now
4:52:544 hours, 52 minutes, 54 secondswhich isn't exactly correct because it's going to be different on the server but good enough.
4:53:014 hours, 53 minutes, 1 secondSo that's for uh updating the existing project. But we're still not done because now we have to push it to a list
4:53:084 hours, 53 minutes, 8 secondsof our existing projects. So for that I believe we can copy this from use create project.
4:53:194 hours, 53 minutes, 19 secondsYes, we can rename this to use rename project. So we get rid of the error. So after this first if block here, let's again fetch for the existing projects.
4:53:324 hours, 53 minutes, 32 secondsCheck if existing projects are not loading and then call local
4:53:404 hours, 53 minutes, 40 secondsstore set query API.get
4:53:484 hours, 53 minutes, 48 secondsskip the arguments go inside of existing projects existing projects. So be careful, right?
4:53:574 hours, 53 minutes, 57 secondsMap get the individual project and in here return
4:54:054 hours, 54 minutes, 5 secondsproject ID matches arguments ID. If it does
4:54:124 hours, 54 minutes, 12 secondsspread the project property, change the name to arguments.name and update it at to date.now.
4:54:224 hours, 54 minutes, 22 secondsOtherwise just return the plain project. There we go.
4:54:294 hours, 54 minutes, 29 secondsSo I believe that is it. That's what we have to develop here. So this will change both the query for get by ID and
4:54:394 hours, 54 minutes, 39 secondsalso it will update the project in all the places where we fetch projects. So a
4:54:454 hours, 54 minutes, 45 secondspowerful optimistic update. We now have use rename project. But what we have to
4:54:524 hours, 54 minutes, 52 secondsdevelop is the UI so that when the user clicks on this, it changes to an input.
4:55:004 hours, 55 minutesSo I'm going to go back inside of navbar.tsx and I'm going to start developing that.
4:55:074 hours, 55 minutes, 7 secondsSo first I'm going to add our new method rename project. Use rename project
4:55:164 hours, 55 minutes, 16 secondsand pass in the project ID. Make sure to import username project.
4:55:224 hours, 55 minutes, 22 secondsGreat. That's the first thing. Then let's prepare two states is renaming and name. And then just
4:55:314 hours, 55 minutes, 31 secondsimport use state from react. I'm going to move it here to the top.
4:55:404 hours, 55 minutes, 40 secondsOkay. So we should have rename project is renaming and name as well as its setters.
4:55:484 hours, 55 minutes, 48 secondsNow that we have that, let's go ahead and see what should we render when we are renaming and what should we render
4:55:564 hours, 55 minutes, 56 secondswhen we are not. So down here I'm going to find breadcrumb uh page and actually
4:56:044 hours, 56 minutes, 4 secondsI'm going to focus on the breadcrumb item. So if is renaming I will render a native input otherwise I'm going to render a breadcrumb page.
4:56:174 hours, 56 minutes, 17 secondsSo let's indent this. There we go.
4:56:214 hours, 56 minutes, 21 secondsAnd on the breadcrumb page, let's give it an on click handle start rename. And
4:56:284 hours, 56 minutes, 28 secondsnow let's go ahead and just develop this method real quick.
4:56:334 hours, 56 minutes, 33 secondsSo constant handle start rename will check if we don't have a project and
4:56:404 hours, 56 minutes, 40 secondsimmediately break. And then call set name with project.name. and set is
4:56:464 hours, 56 minutes, 46 secondsrenaming to true. So in case project hasn't loaded, we're just going to break the method. Otherwise, we're going to
4:56:544 hours, 56 minutes, 54 secondsset the local name to be project's name that we loaded and then we're just going to change set is renaming to true. What
4:57:034 hours, 57 minutes, 3 secondsthis will do is it will render the input. And inside of this input, let's see what we have to do. So I want to
4:57:094 hours, 57 minutes, 9 secondsauto focus on it. I want to give it a type of text value
4:57:164 hours, 57 minutes, 16 secondsof name on change.
4:57:224 hours, 57 minutes, 22 secondsLet's get the event and call set name event target value
4:57:294 hours, 57 minutes, 29 secondson focus event current target select
4:57:364 hours, 57 minutes, 36 secondson blur for now an empty arrow function on key down
4:57:434 hours, 57 minutes, 43 secondsan empty arrow function as well. And now let's focus on the class names here. So,
4:57:514 hours, 57 minutes, 51 secondswe're going to have text small, BG transparent, and text foreground.
4:57:584 hours, 57 minutes, 58 secondsThen, we're going to have outline none, focus ring one, focus ring inset,
4:58:074 hours, 58 minutes, 7 secondsand then the last view, focus ring, ring, font medium, maximum
4:58:144 hours, 58 minutes, 14 secondswidth of 40, and truncate. So feel free to pause the screen and confirm you have the entire class name here. And let's
4:58:224 hours, 58 minutes, 22 secondstest it out. So now when I click here, it turns into an input. But currently it doesn't really do much, right? We cannot
4:58:304 hours, 58 minutes, 30 secondssubmit, we cannot cancel. And when we refresh, we can very well see that it wasn't saved. So let's implement the functions we need to actually save this.
4:58:414 hours, 58 minutes, 41 secondsWe have only implemented handle start rename so far. So now let's do const handle submit.
4:58:504 hours, 58 minutes, 50 secondsThe first thing we're going to do is set is renaming to false. And then let's go ahead and trim the name. So name.trim.
4:59:024 hours, 59 minutes, 2 secondsIf this new trimmed name doesn't exist, meaning it's falsy, meaning it was just
4:59:084 hours, 59 minutes, 8 secondsa blank space which we don't uh accept as a name.
4:59:134 hours, 59 minutes, 13 secondsor if trimmed name is exactly the same as current project.name.
4:59:204 hours, 59 minutes, 20 secondsAnd to fix this, we can just check if there is no project return. There we go.
4:59:284 hours, 59 minutes, 28 secondsBreak the function as well. So, we're not going to waste resources uh updating to the same thing. Let's call rename
4:59:354 hours, 59 minutes, 35 secondsproject. Give it an ID of project ID and name of trimmed name.
4:59:434 hours, 59 minutes, 43 secondsGreat. And now let's go ahead and implement a super simple handle key down. So handle key down will accept an event which is a react keyboard event.
4:59:554 hours, 59 minutes, 55 secondsIf that key pressed is enter, we're going to call our previously created handle submit. Otherwise, if the key is
5:00:045 hours, 4 secondsescape, we are simply going to toggle off the renaming functionality.
5:00:105 hours, 10 secondsNow that we have both of them, let's go ahead and add them to on blur and on key down. So, right here.
5:00:195 hours, 19 secondsThere we go.
5:00:215 hours, 21 secondsSo, let's refresh for good luck. And let's change this to test and press enter. And you can see it's immediately
5:00:305 hours, 30 secondsuh optimistically updated, right? So, optimistic update immediately. You don't even feel that it's loading. And you can
5:00:395 hours, 39 secondssee it's reflected here as well. So definitely works. Amazing job. So that's that finished.
5:00:485 hours, 48 secondsThere is uh one more element left to develop here. Uh and that is the import status indicator.
5:00:585 hours, 58 secondsIn order to implement the status indicator, we first have to import all the components from tool tip. So tool
5:01:065 hours, 1 minute, 6 secondstip content and trigger. Then let's go down here and after the breadcrumb ends
5:01:135 hours, 1 minute, 13 secondsbut still inside of this div, let's go ahead and check if project dot import status is importing.
5:01:225 hours, 1 minute, 22 secondsIn that case, let's render a tool tip. Let's render tool tip trigger.
5:01:305 hours, 1 minute, 30 secondsLet's add as child prop and let's add a loader icon from Lucid React. So make sure you add this import.
5:01:415 hours, 1 minute, 41 secondsI'm going to move it here.
5:01:445 hours, 1 minute, 44 secondsThe loader icon will have a class name size four text muted foreground and animate spin.
5:01:565 hours, 1 minute, 56 secondsLet me just write the alternative here so I don't get that error even though I still have the error. Okay, so that's
5:02:045 hours, 2 minutes, 4 secondsthe tool tip trigger and the tool tip content will simply say importing. And now for the alternative.
5:02:135 hours, 2 minutes, 13 secondsLet's check if project question mark updated at exists even though it should
5:02:205 hours, 2 minutes, 20 secondsalways exist though. H it is set at undefined.
5:02:265 hours, 2 minutes, 26 secondsLet me check. Updated at is always a number. H. [clears throat] Okay. Yeah, we can we can do it like this. It's okay. Copy the tool tip.
5:02:385 hours, 2 minutes, 38 secondsPaste it inside. The trigger will be a little bit different. The trigger will be a cloud check icon from Lucid React.
5:02:505 hours, 2 minutes, 50 secondsThe class name will be identical besides I mean except animate spin like that.
5:02:575 hours, 2 minutes, 57 secondsAnd then the tool tip content will tell the user when was the last save. So
5:03:045 hours, 3 minutes, 4 secondssaved add this space format distance to now from date FNS. So make sure you
5:03:135 hours, 3 minutes, 13 secondsimport that. We installed this package in the previous chapter.
5:03:185 hours, 3 minutes, 18 secondsIn the first argument, pass in project updated at and in the second one add suffix to true.
5:03:265 hours, 3 minutes, 26 secondsSo let's check it out. Next to our name, you can see that it says saved 5 minutes ago. So if I update it, saved less than
5:03:365 hours, 3 minutes, 36 secondsa minute ago. Let's try and find some of my projects which are importing. Do I have any? I do not. So, I'm going to go
5:03:455 hours, 3 minutes, 45 secondsto dashboard conconvex.dev and I'm just going to purposely change one.
5:03:525 hours, 3 minutes, 52 secondsSo, here in my database, I'm going to find one project. Maybe this one, two, three, so it's easy to find. And I'm
5:04:005 hours, 4 minutesgoing to change its import status to importing.
5:04:055 hours, 4 minutes, 5 secondsSo, there we go. You can see how it's changed here. And when I click here, you can see it says importing. It's a little
5:04:135 hours, 4 minutes, 13 secondsbit twitchy, but okay. Let's leave it like this for now. That's it for the navbar. Our navbar is now finished. We
5:04:225 hours, 4 minutes, 22 secondscan now focus on the bottom half, which will basically have an allotment pane to
5:04:295 hours, 4 minutes, 29 secondsseparate the items. So, that's it for the navbar.
5:04:335 hours, 4 minutes, 33 secondsLet's go ahead. Uh, I guess the only thing that's kind of worrying me is this
5:04:405 hours, 4 minutes, 40 secondssyntax. It feels weird. I'm not sure it needs to be like this.
5:04:465 hours, 4 minutes, 46 secondsI think we can render it regardless.
5:04:525 hours, 4 minutes, 52 secondsAnd then in here do the thing. So uh if project
5:05:015 hours, 5 minutes, 1 secondquestion mark updated at then use format distance to now otherwise unknown.
5:05:095 hours, 5 minutes, 9 secondsI guess that's like an edge case.
5:05:125 hours, 5 minutes, 12 secondsWeird syntax but let me see if I can somehow make it easier for you to read.
5:05:205 hours, 5 minutes, 20 secondsOkay. And just move this here.
5:05:255 hours, 5 minutes, 25 secondsOkay. I guess you can recognize this, right? If we have project updated at, we format its distance. Otherwise, unknown.
5:05:325 hours, 5 minutes, 32 secondsWe have no idea when it was last updated because we don't have that data, which would be very weird because we always
5:05:385 hours, 5 minutes, 38 secondshave the updated ad property. Cool. Or how about loading?
5:05:465 hours, 5 minutes, 46 secondsYeah, how about we Okay, I'm I'm doing too much, but you can do whatever you want. This is an edge case that should almost never appear.
5:05:555 hours, 5 minutes, 55 secondsGreat. Now that we have that, let's focus back inside of our projects components
5:06:025 hours, 6 minutes, 2 secondsproject ID layout. What we have to do now is we have to install a package called allotment. So, npm install
5:06:125 hours, 6 minutes, 12 secondsallotment. And I'm going to show you what version I'm using.
5:06:165 hours, 6 minutes, 16 secondsSo, package json allotment. This is my version in case you want to use the same. And this is its npm page. So
5:06:245 hours, 6 minutes, 24 secondswhat's cool about a lotment is that it has an industry standard look and feel.
5:06:295 hours, 6 minutes, 29 secondsSo if you like VS Code's split view implementation, you are in luck because this component is derived from the same
5:06:375 hours, 6 minutes, 37 secondscodebase. And I actually like this more than I like Shaten's resizable component because uh those resizable components
5:06:465 hours, 6 minutes, 46 secondsfor some reason do proportional expansion on zoom and that just doesn't look or feel good. But this this feels
5:06:555 hours, 6 minutes, 55 secondsperfect. So we just installed that and uh let's go ahead and add it to our project ID layout. What we have to do is
5:07:055 hours, 7 minutes, 5 secondswe have to import allotment from allotment and we now have to define some
5:07:115 hours, 7 minutes, 11 secondsconstants here. So minimum sidebar width, maximum sidebar width, default
5:07:185 hours, 7 minutes, 18 secondsconversation sidebar width and default main size.
5:07:235 hours, 7 minutes, 23 secondsThen let's go ahead and wrap our children here in a div.
5:07:305 hours, 7 minutes, 30 secondsLet's give this div a class name flex one flex and overflow hidden.
5:07:395 hours, 7 minutes, 39 secondsAnd then let's add a lotment around the children itself.
5:07:455 hours, 7 minutes, 45 secondsThe allotment will have a class name of flex one
5:07:525 hours, 7 minutes, 52 secondsand default sizes of default conversation sidebar width
5:08:005 hours, 8 minutesand default main size. So let me collapse them so it's easier to read like this.
5:08:095 hours, 8 minutes, 9 secondsWhich means that we're now going to have to add two allotment panes here. So allotment oops allotment.pane
5:08:185 hours, 8 minutes, 18 secondsnumber one and allotment.pane number two around the children like this.
5:08:295 hours, 8 minutes, 29 secondsInside of this one, let's give it a snap property. a minimum size of minimum
5:08:365 hours, 8 minutes, 36 secondssidebar width, maximum size of maximum sidebar width, and preferred size of
5:08:455 hours, 8 minutes, 45 secondsdefault conversation sidebar width. And then in here, I'm going to add a div conversation sidebar.
5:08:545 hours, 8 minutes, 54 secondsSo, let's go ahead and save this. And so far, we're not really seeing much, right? So if you take a look at how
5:09:005 hours, 9 minutesaotment should be used, we install aotment, we use a lotment, but we also need to import its styles.
5:09:105 hours, 9 minutes, 10 secondsSo let's make sure we add that for now. I'm going to add it here.
5:09:145 hours, 9 minutes, 14 secondsActually, I think we have to like do it at the end. There we go. And here it is.
5:09:205 hours, 9 minutes, 20 secondsHere is the split. You can see how it has this almost recognizable uh VS Code like uh highlight and you can also snap. I think maybe you can't.
5:09:335 hours, 9 minutes, 33 secondsLet's see. Did I enable snap here? I did, which should make it possible for us to snap this all the way back, but
5:09:425 hours, 9 minutes, 42 secondsmaybe I'm not understanding its property correctly. There we go. You can snap, which kind of means hide it completely.
5:09:495 hours, 9 minutes, 49 secondsAnd you still have an option to bring it back. So this is where our conversation sidebar will be. And now we're going to
5:09:565 hours, 9 minutes, 56 secondsimplement this part right here in which we're simply going to implement you know the the tabs. So where is this part?
5:10:035 hours, 10 minutes, 3 secondsWell, it's the children. So let's go ahead inside of we don't have it yet. So inside of app folder projects project ID
5:10:125 hours, 10 minutes, 12 secondspage. This is where that is. So let's improve that.
5:10:175 hours, 10 minutes, 17 secondsSo instead of rendering in the project ID here, we're just going to render project ID view and pass it a prop
5:10:245 hours, 10 minutes, 24 secondsproject ID. Obviously, we have an error now because this doesn't exist. So let's create it. Back inside of features
5:10:325 hours, 10 minutes, 32 secondsprojects components, I will create a new file project- ID- view.tsx.
5:10:405 hours, 10 minutes, 40 secondsI'm going to mark this as use client.
5:10:445 hours, 10 minutes, 44 secondsAnd now I'm very simply going to prepare the following.
5:10:495 hours, 10 minutes, 49 secondsAnd let me end it here. There we go. So project ID view. It's going to have one prop project ID. And that project ID
5:10:585 hours, 10 minutes, 58 secondswill be the same type as in our project ID layout. If you remember id projects.
5:11:065 hours, 11 minutes, 6 secondsSo let's import id from convex generated data model and let's return a div project ID view.
5:11:165 hours, 11 minutes, 16 secondsGreat. Now let's go back inside of the project ID page and let's import project ID view. And in order to fix the type
5:11:255 hours, 11 minutes, 25 secondserror, we have to change this to be the ID projects as well. There we go. All fixed. So, we should now have the
5:11:345 hours, 11 minutes, 34 secondsconversation sidebar and the project ID on the other side. Going well. Let's go ahead inside of project ID view here.
5:11:455 hours, 11 minutes, 45 secondsAnd now what we're going to do is give this a class name height full flex and flex column.
5:11:555 hours, 11 minutes, 55 secondsCreate a navbar with a class name height of 35 pixels
5:12:025 hours, 12 minutes, 2 secondsflex items center background color of sidebar and border bottom.
5:12:105 hours, 12 minutes, 10 secondsAnd then let's develop a component called tab.
5:12:165 hours, 12 minutes, 16 secondsThis component will have some props such as label which is a type of string is
5:12:225 hours, 12 minutes, 22 secondsactive which is a boolean and on click which is a void I mean a function. So label is active and on click.
5:12:345 hours, 12 minutes, 34 secondsLet's go ahead and return a div a span inside and render the label. The span
5:12:415 hours, 12 minutes, 41 secondswill have a class name of text small and the div will have an on click on click
5:12:495 hours, 12 minutes, 49 secondsproperty and a class name which will use the CN util because this will be dynamic based on its active prop.
5:13:005 hours, 13 minutesSo if is active, it will have a bg background and text foreground.
5:13:115 hours, 13 minutes, 11 secondsBut if it is not, we're just going to have some default classes here such as
5:13:165 hours, 13 minutes, 16 secondsflex items center gap 2 full height px3
5:13:235 hours, 13 minutes, 23 secondscursor pointer text muted foreground border
5:13:295 hours, 13 minutes, 29 secondsright hover bg accent with a 30% opacity. That's our tab component. Now
5:13:375 hours, 13 minutes, 37 secondsthat we have our tab component, let's go ahead and render it inside of here. So tab like this
5:13:475 hours, 13 minutes, 47 secondslabel preview is active false on click empty arrow function.
5:13:555 hours, 13 minutes, 55 secondsDuplicate this and change this one actually the first one to be code. And yes, in here we have a warning. So looks like this can be written as height 8.75.
5:14:095 hours, 14 minutes, 9 secondsReally cool. Let's write it as such then.
5:14:135 hours, 14 minutes, 13 secondsAnd now as you can see we have tabs code and preview. Clicking on them doesn't do
5:14:205 hours, 14 minutes, 20 secondsmuch though. So let's improve that. In order to do that we have to introduce a state. So right here in the project ID view use state.
5:14:325 hours, 14 minutes, 32 secondsMake sure to import this from React. So I'm going to move this to the top.
5:14:385 hours, 14 minutes, 38 secondsSo what type can the state be? Well, only two things. Either an editor or preview. And by default, it's going to
5:14:475 hours, 14 minutes, 47 secondsbe editor. And the property that we're going to store is active view and set
5:14:545 hours, 14 minutes, 54 secondsactive view to control it. So now we can modify is active and on click here to be
5:15:015 hours, 15 minutes, 1 secondlike this and call the editor and the opposite in the preview if active view is preview and set active view to
5:15:105 hours, 15 minutes, 10 secondspreview. There we go. You can now switch between the two states. Perfect. Now we
5:15:185 hours, 15 minutes, 18 secondshave to add some content here. So outside of the nav here, let's create a div with a class name flex one and a relative.
5:15:295 hours, 15 minutes, 29 secondsAnd inside of here, a div with a class name CN absolute insert zero.
5:15:395 hours, 15 minutes, 39 secondsIf active view is editor, it is visible otherwise invisible.
5:15:475 hours, 15 minutes, 47 secondsAnd a div editor. There we go. And then let's go ahead and do this again. So I'm
5:15:555 hours, 15 minutes, 55 secondsjust going to copy this and we're going to do the opposite here. So if active view is preview,
5:16:035 hours, 16 minutes, 3 secondsrender preview. Let's try it out. So when I click on preview, I can see the preview content and when I click on code, I can see the editor content.
5:16:145 hours, 16 minutes, 14 secondsGreat. So, one left one thing left to do is to add a simple export to GitHub button, but without any functionality.
5:16:215 hours, 16 minutes, 21 secondsIt's not even going to open anything. I just want to have the UI ready.
5:16:275 hours, 16 minutes, 27 secondsSo, right below our last tab here, we're going to add a div. This div will have a
5:16:335 hours, 16 minutes, 33 secondsclass name flex one flex justify end and height full. And then inside of here,
5:16:425 hours, 16 minutes, 42 secondswe're going to do the following. So, this will later actually be in a separate component, but for now, we're going to keep it here. I want you to
5:16:505 hours, 16 minutes, 50 secondscopy the entire class name from the tab and go ahead and add it here in a div.
5:16:585 hours, 16 minutes, 58 secondsSo, class name and just paste the entire thing. The only thing we're going to change is from border right to border left and gap to be 1.5.
5:17:105 hours, 17 minutes, 10 secondsAnd then inside of here, let's go ahead and render FA GitHub, which we can import from React-
5:17:185 hours, 17 minutes, 18 secondsicons forward slash FA. And let's give it a class name of size 3.5.
5:17:265 hours, 17 minutes, 26 secondsAnd then a span, which will say export with a class name text small.
5:17:365 hours, 17 minutes, 36 secondsSo let's go ahead and check it out.
5:17:385 hours, 17 minutes, 38 secondsThere we go. We now have a button to export to GitHub that currently does nothing but will in the future. Amazing.
5:17:465 hours, 17 minutes, 46 secondsExactly what we envisioned and more. I didn't even I completely forgot about this indicator but we did it on the fly and it was quite easy for us to do so,
5:17:555 hours, 17 minutes, 55 secondswasn't it? So, we are now ready to start doing some real work here, aren't we?
5:18:005 hours, 18 minutesPretty good setup so far. So, we've created dynamic routing system. We build resizable ID split veins. We implemented
5:18:085 hours, 18 minutes, 8 secondsnubar with project actions. We've set up editor and preview containers. And we added the tab switching functionality.
5:18:155 hours, 18 minutes, 15 secondsAwesome. Let's go ahead and merge all of that.
5:18:205 hours, 18 minutes, 20 secondsSo this is chapter 8. I'm going to shut down all of my IDs here. I mean my terminals.
5:18:295 hours, 18 minutes, 29 secondsSo get add dot get commit 08
5:18:375 hours, 18 minutes, 37 secondsIDE layout get checkout-b08
5:18:435 hours, 18 minutes, 43 secondsIDE layout get push- u origin08 IDE
5:18:515 hours, 18 minutes, 51 secondslayout and once we've pushed it you should see it right here and now we can
5:18:585 hours, 18 minutes, 58 secondsgo ahead head and open a pull request. So, I'm going to go ahead and open a pull request and let's review our code.
5:19:105 hours, 19 minutes, 10 secondsAnd here we have the summary new features. We added individual project detail pages with dedicated layout. We
5:19:175 hours, 19 minutes, 17 secondsenabled inline editing of the project names in the navbar. We introduced split pane interface with sidebar navigation.
5:19:265 hours, 19 minutes, 26 secondsWe added code and preview tabs for project viewing. We added a placeholder of project exporting and we are displaying project status indicators.
5:19:375 hours, 19 minutes, 37 secondsImport progress and save timestamps.
5:19:405 hours, 19 minutes, 40 secondsLet's take a look at two important comments actually three important comments that code rabbit left. It actually found some bugs which uh I've
5:19:485 hours, 19 minutes, 48 secondsleft. The first bug is instead of our layout.tsx, it's a type mismatch. Basically in here
5:19:565 hours, 19 minutes, 56 secondswe define it as a string but code rabbit knows that instead of project ID layout we expect a type of convex ID of
5:20:065 hours, 20 minutes, 6 secondsprojects. We can actually confirm this bug. So if I go inside of app folder
5:20:135 hours, 20 minutes, 13 secondsprojects layout you can see it's a bug right? It's a super easy fix. We just have to modify this. But I'm going to
5:20:205 hours, 20 minutes, 20 secondsleave that for the next chapter. I don't like to modify my branches once I push them. So that's definitely a thing to
5:20:285 hours, 20 minutes, 28 secondsfix. Great catch by Code Rabbit. Then we have the second one in here. It mostly talks about how this is an incomplete
5:20:375 hours, 20 minutes, 37 secondsimplementation which is true, right? We have this unused project ID prop and it indicates that we should use this to
5:20:455 hours, 20 minutes, 45 secondsfetch data. Correct? But this is still just a mockup. We are later going to implement the file explorer so it will
5:20:535 hours, 20 minutes, 53 secondsmake sense. And here is an interesting one. So inside of the username project,
5:21:005 hours, 21 minutesit's telling us about a potential inconsistent ID usage in this optimistic update. That is because we are kind of
5:21:095 hours, 21 minutes, 9 secondsmixing the argument project ID and arguments dot project ID. You can see
5:21:175 hours, 21 minutes, 17 secondshow here we're using project ID but down here at least somewhere I think we're
5:21:255 hours, 21 minutes, 25 secondsusing arguments dot project ID or it's just the fact that we even use this
5:21:335 hours, 21 minutes, 33 secondsproject ID because again I'm going to take a look just to confirm. So in my navbar
5:21:415 hours, 21 minutes, 41 secondswhen I implement rename project yeah you can see that I pass in
5:21:495 hours, 21 minutes, 49 secondsdo ID so technically why am I passing it here then right we should probably get
5:21:565 hours, 21 minutes, 56 secondsrid of that because it's just it makes no sense we should access this through
5:22:025 hours, 22 minutes, 2 secondsarguments this should be arguments do ID I'm not going to do it now. I don't want to change my branch. But yes, Code
5:22:115 hours, 22 minutes, 11 secondsRabbit actually noticed an important mistake here. There's no reason for us to have to pass this because when you
5:22:185 hours, 22 minutes, 18 secondslook at it, its only purpose is [clears throat] optimistic mutation for which we have a solution. We have the
5:22:275 hours, 22 minutes, 27 secondsdirect arguments which are more reliable than this because yes if you pass one thing here and call another thing here
5:22:365 hours, 22 minutes, 36 secondsthere will be a mismatch with optimistic update very very good catch by code rabbit see this is what I was talking
5:22:445 hours, 22 minutes, 44 secondsabout this is why I think it's important to have another set of eyes take a look at the code amazing amazing job we're
5:22:525 hours, 22 minutes, 52 secondsgoing to merge this for now I like to fix these things in the second chapter rather than now so we don't mess the branch.
5:23:005 hours, 23 minutesAnd now that we have merged that, let's go ahead and go back to our main branch.
5:23:075 hours, 23 minutes, 7 secondsGet pull origin main. So we are up to date. There we go. And as always, I like
5:23:145 hours, 23 minutes, 14 secondsto confirm with my graph here. There we go. We checked out for chapter 8 and we
5:23:225 hours, 23 minutes, 22 secondsmerged it back to main. Amazing. Amazing job. I believe that marks the end of
5:23:285 hours, 23 minutes, 28 secondsthis chapter. We created this, this, this, and this. Amazing. Amazing job.
Chapter 10: 09 File Explorer
5:23:375 hours, 23 minutes, 37 secondsIn this chapter, we're going to develop the file explorer. We're going to design the file folder data model inside of the
5:23:445 hours, 23 minutes, 44 secondsconvex schema. We're going to build a recursive tree component. We're going to create the collapsible folder behavior.
5:23:525 hours, 23 minutes, 52 secondsWe're going to implement file and folder icons using VS Code icons.js package and we're going to add file selection state
5:23:595 hours, 23 minutes, 59 secondsmanagement. Let's take a look at how that actually looks like when it's finished. So this is what we are supposed to have at the end of this
5:24:085 hours, 24 minutes, 8 secondschapter. Basically a file explorer that let us well explore files folders recursively.
5:24:165 hours, 24 minutes, 16 secondsAnd we will also have the logic which decides what folder or file is currently open. You can see that we even have this
5:24:245 hours, 24 minutes, 24 secondsadvanced temporary open file logic. So when I click on something else, it overrides that tab. But if I
5:24:325 hours, 24 minutes, 32 secondsdoubleclick, it kind of makes it persistent and then the next one I click goes in that other tab. Similarly to how the actual VS Code works. And I think
5:24:405 hours, 24 minutes, 40 secondsthat's a better solution than just to open a bunch of tabs whenever you click.
5:24:465 hours, 24 minutes, 46 secondsSo let's go ahead and focus on building that. I'm going to go ahead and make sure we have our app running and make
5:24:525 hours, 24 minutes, 52 secondssure you have npx convex dev running as well since we are going to be updating our schema and creating some new
5:24:595 hours, 24 minutes, 59 secondsfunctions here. So in our project localhost 3000 here what we finished last time is the ability to click on a
5:25:085 hours, 25 minutes, 8 secondsproject and inside of here we have a lotment panes which we can resize and we've also prepared the code and preview
5:25:175 hours, 25 minutes, 17 secondsfeature. So now we're going to focus on the code feature. So make sure you have that opened here and let's start by
5:25:255 hours, 25 minutes, 25 secondsdefining the schema. The schema will basically define how this file explorer will actually be able to work. So I'm
5:25:345 hours, 25 minutes, 34 secondsgoing to go ahead and create a new files table here. Files, let's use define
5:25:415 hours, 25 minutes, 41 secondstable. And let's go ahead and give it some properties. So first things first, each file has to belong to a project. So
5:25:495 hours, 25 minutes, 49 secondseach file needs to have a project ID with the type of ID, specifically project ID. Next, each file can
5:25:585 hours, 25 minutes, 58 secondstechnically be a folder or it can be inside of another folder. Because of
5:26:055 hours, 26 minutes, 5 secondsthat, a file may or may not have a parent ID. So, it's optional and its ID is a reference to itself, another file.
5:26:165 hours, 26 minutes, 16 secondsEach file will also have a name. And now we we're going to add what I was talking about here for the parent ID. Each file can either be a file or a folder.
5:26:295 hours, 26 minutes, 29 secondsTechnically, we could separate those into two different tables, but I think the complexity is not necessary at the at this level of project. And more so,
5:26:395 hours, 26 minutes, 39 secondsthey're going to have a lot of similar fields. So, it will mostly just be maintaining two almost identical tables.
5:26:465 hours, 26 minutes, 46 secondsBecause of that, giving it a type which is a union which can either be a file or folder in my opinion makes more sense.
5:26:555 hours, 26 minutes, 55 secondsSo now we're going to add an optional field called content. Content will be optional and it's going to be a type of string. And you can see I have a comment
5:27:045 hours, 27 minutes, 4 secondshere text files only. Basically, if our file is textbased, like majority of the
5:27:125 hours, 27 minutes, 12 secondsfiles in a code editor, we will store that inside of content. But if we
5:27:195 hours, 27 minutes, 19 secondsattempt to add PNG, JPEG, uh a GIF or anything like that, which is basically a binary file and basically anything that
5:27:275 hours, 27 minutes, 27 secondsis not a text file, which is a binary file, we have a couple of options to store that. We technically could store that in content by [clears throat]
5:27:355 hours, 27 minutes, 35 secondsconverting it to base 64, but as far as I know that really isn't optimized and I'm pretty sure it will break some
5:27:435 hours, 27 minutes, 43 secondslimits in convex. So because of that we're going to use convex storage. So because of that we're going to have storage ID which again is optional and
5:27:535 hours, 27 minutes, 53 secondsit's basically going to have a reference to a storage property. So v id storage.
5:27:585 hours, 27 minutes, 58 secondsSo that's going to be used for binary files and it's optional. And the last property we're going to have is updated at. And now let's go ahead and let's add
5:28:085 hours, 28 minutes, 8 secondssome indexes here. So the first index we're going to add is going to be by project and it's going to be referencing
5:28:165 hours, 28 minutes, 16 secondsto the project ID. The second one will be by parent referencing to the parent ID. And the third one will be a
5:28:245 hours, 28 minutes, 24 secondscombination of the two if we ever need to do that. Great. So, make sure that you don't have any errors here. You
5:28:315 hours, 28 minutes, 31 secondsshould have successful indexes. You should have everything successful here.
5:28:355 hours, 28 minutes, 35 secondsIf you want to, you can do npx convex dev again just to confirm that you don't have any errors.
5:28:425 hours, 28 minutes, 42 secondsGreat. So, now that we have this done, let's go and inside of convex folder, create a new files.ts.
5:28:505 hours, 28 minutes, 50 secondsSo, this will be very similar to projects.ts. In fact, you can keep them both open because we are going to kind of copy and paste some things. So, how
5:28:595 hours, 28 minutes, 59 secondsabout we actually copy the get query since it it will be quite similar. So,
5:29:055 hours, 29 minutes, 5 secondsI'm going to go ahead and paste this and I'm going to go ahead and I'm going to copy all the imports here. So, we save
5:29:135 hours, 29 minutes, 13 secondssome time. So, make sure you have convex values, mutation query, and verify out.
5:29:195 hours, 29 minutes, 19 secondsSo for the get one uh let's call this get files and the arguments it's going to accept will actually be
5:29:275 hours, 29 minutes, 27 secondsproject id v id projects like that same things as the usual uh we
5:29:365 hours, 29 minutes, 36 secondsneed to verify our identity and then we need to first fetch the project and make sure to extract the arguments.
5:29:465 hours, 29 minutes, 46 secondsSo why do we need to fetch the project if we are just getting files? Well, first things first, we need to check if this project still exists because if it
5:29:545 hours, 29 minutes, 54 secondsdoesn't, we need to throw an error and not do any computation further. But there is another thing we have to check and that is the ownership. So we
5:30:015 hours, 30 minutes, 1 secondshouldn't just allow a user to fetch files if they know a project ID. We need to make sure that the user who is logged in actually has access to that project.
5:30:115 hours, 30 minutes, 11 secondsAnd only then let's go ahead and return await context database query files with
5:30:205 hours, 30 minutes, 20 secondsindex by project. And then inside of here, make sure to query for equals project ID arguments project ID. I'm
5:30:285 hours, 30 minutes, 28 secondsgoing to try and expand this so you can see how it looks like in one line like this. And make sure to execute collect.
5:30:345 hours, 30 minutes, 34 secondsIn the previous chapter, I believe I made this mistake. So make sure you don't do it. Great. That is our first one finished. So now I'm going to go
5:30:435 hours, 30 minutes, 43 secondsahead and copy it. And I'm going to create another one, but this one will be called get file as in individual one.
5:30:525 hours, 30 minutes, 52 secondsAnd in here the argument will simply be an id of files.
5:30:595 hours, 30 minutes, 59 secondsSo let's go ahead and first things first after we get the identity let's attempt to get the file and then if there is no
5:31:075 hours, 31 minutes, 7 secondsfile let's go ahead and throw an error file not found and now once we have the file we can actually do file.p project ID to do the exact same thing as above.
5:31:185 hours, 31 minutes, 18 secondsAnd then finally, if all of the checks pass, we don't have to fetch anything new. We can just return the file. There we go. So that's our code to get the
5:31:265 hours, 31 minutes, 26 secondsfile as in individual one. Now let's go ahead and let's build get folder contents. So again, I'm going to copy
5:31:355 hours, 31 minutes, 35 secondsget files because it's actually quite similar.
5:31:385 hours, 31 minutes, 38 secondsAnd I'm going to rename it to get folder contents.
5:31:435 hours, 31 minutes, 43 secondsAnd besides accepting the project ID, we're also going to accept parent ID.
5:31:505 hours, 31 minutes, 50 secondsAnd that's a type of well, it's not required. So let's go ahead and give it optional
5:31:585 hours, 31 minutes, 58 secondsan ID of files. So same things, uh, we're going to verify our identity.
5:32:045 hours, 32 minutes, 4 secondsWe're going to fetch the project. If it's not found, throw an error. If we don't have access to it, throw an error
5:32:115 hours, 32 minutes, 11 secondsagain. And then let's go ahead and just modify this again. So we're not returning early. We're just going to define files as await context. database
5:32:205 hours, 32 minutes, 20 secondsquery files with index by project and by parent get the query and immediately
5:32:275 hours, 32 minutes, 27 secondsreturn query equals project ID to arguments project ID and then go ahead and just chain maybe this will be easier to read like this.
5:32:395 hours, 32 minutes, 39 secondsChain parent ID arguments.parent parent ID and collect them. Once we have the files, let's go ahead and sort them. So,
5:32:475 hours, 32 minutes, 47 secondshow do we want to sort them? Folders first, then files, and alphabetically within each group. At least, this is the
5:32:555 hours, 32 minutes, 55 secondspattern I've noticed in all code editors. All of them show folders first and then files below them. So, they don't actually mix folders and files. I
5:33:035 hours, 33 minutes, 3 secondsdon't know if you noticed that. You can see that all the folders are at the top and only then files come. And same is true for individual inside u of the folders.
5:33:155 hours, 33 minutes, 15 secondsSo I'm going to go ahead and develop that here. Return files.sort, we receive an argument a and argument b. First
5:33:245 hours, 33 minutes, 24 secondsthings first is we do folders before files. So if a.type is folder and b.type
5:33:315 hours, 33 minutes, 31 secondsis file, return minus one as in the reverse order.
5:33:365 hours, 33 minutes, 36 secondsAnd if a type is file and b.type is folder, we just do the reverse. So reverse logic for a reverse return.
5:33:445 hours, 33 minutes, 44 secondsAnd in here within the same type. So if this is not the case, if all of these files are the same type, we just sort
5:33:515 hours, 33 minutes, 51 secondsalphabetically by name. So return a.name local compare b.name. Like that. Great.
5:34:005 hours, 34 minutesAnd I'm actually kind of um not sure uh just by looking at this. I think we can
5:34:075 hours, 34 minutes, 7 secondsactually use get folder contents without using get files because get files seems
5:34:145 hours, 34 minutes, 14 secondslike a primitive version of get folder contents. So I'm going to see uh except if we're going to use this later in some
5:34:225 hours, 34 minutes, 22 secondsother area. But I think we might not even need this. But still it's okay because we copied and pasted it here.
5:34:285 hours, 34 minutes, 28 secondsSo, it's mostly the same except this has proper sorting logic for the file explorer.
5:34:345 hours, 34 minutes, 34 secondsBut let's go ahead and continue uh developing all the mutations that we're going to need here. So, uh again, I'm going to copy the last one here even
5:34:445 hours, 34 minutes, 44 secondsthough uh this one will be a little bit different because this one will be called create file and it's going to be a mutation.
5:34:545 hours, 34 minutes, 54 secondsSo it will accept a project ID, it will accept an optional parent ID, it will accept a required name and it will accept a required content.
5:35:075 hours, 35 minutes, 7 secondsSo now let's go ahead and do what we usually do. Identity check. Check if the project doesn't exist. Check if we are
5:35:145 hours, 35 minutes, 14 secondsthe owner of that project. And then uh let's go ahead and check if the same
5:35:215 hours, 35 minutes, 21 secondsfile exists within the parent folder because we cannot have the same named files right so that's why I'm adding
5:35:295 hours, 35 minutes, 29 secondsthis comment here let me show you that if I go inside of convex and create a new file files.ts DS you can see I have an error. So we need the same behavior
5:35:375 hours, 35 minutes, 37 secondshere. So let's see can we maybe reuse this files query files by project and by
5:35:465 hours, 35 minutes, 46 secondsparent. This stays exactly the same and collect. Great. And then let's go ahead and just check if an existing file is present.
5:35:565 hours, 35 minutes, 56 secondsSo constant existing files.find file file.name name is equal to arguments.name
5:36:045 hours, 36 minutes, 4 secondsand file.t type is equal to file because this method right here will be used to create file specifically not folder.
5:36:125 hours, 36 minutes, 12 secondsThat's why we don't even accept the type here. We're going to make the type be file.
5:36:205 hours, 36 minutes, 20 secondsSo if this existing one is true, we're going to throw an error. File already exists within this folder.
5:36:305 hours, 36 minutes, 30 secondsAnd at the end here we actually do not need this at all. Instead we can just await context database insert into files
5:36:405 hours, 36 minutes, 40 secondsproject ID arguments project ID name arguments name content arguments content
5:36:485 hours, 36 minutes, 48 secondstype we hardcoded to file parent ID arguments parent ID updated at datenow
5:36:585 hours, 36 minutes, 58 secondsand that's it. That's how we create a file. So, we just make sure that it doesn't already exist within the same project parent situation.
5:37:095 hours, 37 minutes, 9 secondsAnd now, let's go ahead and copy it and do the identical one for folder. We could probably create some abstraction
5:37:175 hours, 37 minutes, 17 secondsto make this make more sense, but it's only two scenarios and I feel more confident having them separated uh so
5:37:255 hours, 37 minutes, 25 secondsthey don't mix or so I don't have to take care of things, right? So the only thing that's different here is folders do not accept any content. So we can
5:37:325 hours, 37 minutes, 32 secondsremove that. Other than that everything should exa be exactly the same. So we do identity, we do the project. If it
5:37:405 hours, 37 minutes, 40 secondsdoesn't exist, we throw an error. If we don't have access to it, we throw an error. And now we do the same thing here. So check if and change this. if
5:37:495 hours, 37 minutes, 49 secondsfolder within the same name already exists in the parent folder and then in the existing logic simply look for file
5:37:575 hours, 37 minutes, 57 secondstype folder and change this to folder already exists
5:38:045 hours, 38 minutes, 4 secondsand then inside of here we're going to modify this to not pass any content and this be a folder like
5:38:125 hours, 38 minutes, 12 secondsthat I think everything else is the same now we're going to implement and the
5:38:195 hours, 38 minutes, 19 secondsrename file logic. So this one will be a little bit different and you're going to see why. So let's go ahead and let me
5:38:275 hours, 38 minutes, 27 secondsjust fix this should be a curly bracket not a square one. This two the arguments is going to accept is just the ID of the
5:38:355 hours, 38 minutes, 35 secondsfile we are going to rename and the new name. Then let's define the handler.
5:38:425 hours, 38 minutes, 42 secondsLet me fix this to be context.
5:38:455 hours, 38 minutes, 45 secondsSo first things first, we do the identity check. As always, after we do a successful identity check,
5:38:535 hours, 38 minutes, 53 secondslet's see if the file arguments ID exists or not. And if it doesn't, we can just go ahead and throw an error. Then
5:39:025 hours, 39 minutes, 2 secondslet's go ahead and using that file. ID, let's get the project this file is located in. And then we do our usual
5:39:095 hours, 39 minutes, 9 secondscheck. If there is no project, throw an error. If we don't belong to that project, throw an error as well. What we
5:39:175 hours, 39 minutes, 17 secondshave to do now is we have to check if a file with the new name already exists in the same parent folder. So what does
5:39:265 hours, 39 minutes, 26 secondsthat mean? Well, uh let me try and show you somewhere.
5:39:315 hours, 39 minutes, 31 secondsUh I have to rename something. So if I want to rename projects to schema, same thing, same behavior as creating a new file. So that's what we're doing here.
5:39:415 hours, 39 minutes, 41 secondsWe have to check if a file with the new name already exists in the parent folder. So let's go ahead and let's fetch all the siblings.
5:39:505 hours, 39 minutes, 50 secondsSiblings await context database query files with index by project and by parent. And I'm going to do the same thing here so it's easier to understand.
5:40:015 hours, 40 minutes, 1 secondSo we are querying both by project ID using file.p project ID and parent ID using file parent ID.
5:40:095 hours, 40 minutes, 9 secondsAnd now we're going to check if we have an existing sibling. But this time we're going to check for both file and folder
5:40:175 hours, 40 minutes, 17 secondstype at the same type. So existing siblings.find sibling if sibling if sibling.name is
5:40:265 hours, 40 minutes, 26 secondsequal to arguments newame and if sibling.type is equal to file type and
5:40:325 hours, 40 minutes, 32 secondsif sibling ID is not the same as the arguments ID. So the only thing that should be allowed to have a new name is
5:40:405 hours, 40 minutes, 40 secondsthe very same file. That's why this is uh not true because the point is if this
5:40:475 hours, 40 minutes, 47 secondsresults to true, we throw an error. So the only way this will not resolve to true and still have the same name and
5:40:555 hours, 40 minutes, 55 secondsthe same type if it's the ID is the same. Other than that, if it's a it's obviously a different file. If we detect
5:41:025 hours, 41 minutes, 2 secondsthat the name is the same, we are getting ready to throw an error. But not just yet because you are allowed to have the same file and the same folder. Those
5:41:115 hours, 41 minutes, 11 secondsare two different things, right? That's why we also do a strict check on the type.
5:41:175 hours, 41 minutes, 17 secondsAnd now if we have the existing, let's throw a new error and it will basically throw a folder or a file with this name
5:41:275 hours, 41 minutes, 27 secondsalready exists. So that's the difference. And then we just have to uh update the files name. So, let's go
5:41:355 hours, 41 minutes, 35 secondsahead and do that. Update the files name like this.
5:41:405 hours, 41 minutes, 40 secondsWhoops, we don't need this one. So, context.database.patch files arguments ID new name and updated
5:41:495 hours, 41 minutes, 49 secondsat. So, yes, a lot of logic for a very simple result, but this is you know to create a good project, a high quality one. We don't want this bugs to happen.
5:41:595 hours, 41 minutes, 59 secondsWe have authorization, we have authentication, and we even have uh this logic to make sure we don't have the two
5:42:065 hours, 42 minutes, 6 secondssame named files because if we do that's an invalid file three structure and this project cannot run. Great. And we
5:42:145 hours, 42 minutes, 14 secondsactually don't have to update the descendants, right? Because of the way our schema is structured, uh we simply
5:42:235 hours, 42 minutes, 23 secondsrefer to the parent ID. So it doesn't matter if the name gets changed. Even if you change the name of the folder with a
5:42:305 hours, 42 minutes, 30 secondsbillion things inside, the parent ID is exactly the same to all of those inner files. So because of that, this is a
5:42:375 hours, 42 minutes, 37 secondsquite of a simple update. The one that will be a little bit different
5:42:445 hours, 42 minutes, 44 secondsis delete file. And that's because we're going to have to recursively delete things. And let's export constame file.
5:42:515 hours, 42 minutes, 51 secondsLet's not forget that. And let's copy the entire thing. Let's paste it here. Uh let me find which is the new one.
5:43:005 hours, 43 minutesHere it is. This will be called delete file.
5:43:045 hours, 43 minutes, 4 secondsSo let's see. Uh we don't need any new name here. So we can remove this. We
5:43:125 hours, 43 minutes, 12 secondsneed the identity file file error. We get the project. We throw if project
5:43:185 hours, 43 minutes, 18 secondsdoesn't exist. we throw if we don't have access to it. And now uh we don't need to do the sibling check. In fact, I'm
5:43:275 hours, 43 minutes, 27 secondsgoing to remove everything down here because it will be a little bit more complex than that. So what do we
5:43:355 hours, 43 minutes, 35 secondsactually have to do? Well, we have to recursively delete file or folder and all of its descendants. So basically we
5:43:435 hours, 43 minutes, 43 secondshave to tra traverse to find the most how do I call it the lowest file in the
5:43:525 hours, 43 minutes, 52 secondsfile tree structure and make sure that when a parent is deleted all the things down to the last file are deleted as
5:44:005 hours, 44 minuteswell. So let's go ahead and develop a constant delete recursive.
5:44:095 hours, 44 minutes, 9 secondsDelete recursive is an asynchronous function which accepts a file ID which is basically a type of arguments ID or
5:44:165 hours, 44 minutes, 16 secondswe can maybe ourselves say it's going to be this because that's what it is. You can import ID from
5:44:255 hours, 44 minutes, 25 secondsgenerated data model. So let me scroll all the way down to delete recursive and let's go ahead and build it. First
5:44:325 hours, 44 minutes, 32 secondsthings first, we're going to check if the file actually exists.
5:44:375 hours, 44 minutes, 37 secondsIf it doesn't, we break the method. So, let's go ahead and check the scenario.
5:44:425 hours, 44 minutes, 42 secondsIf it's a folder, we need to delete all children first. So, I'm going to go ahead and open an if clause.
5:44:505 hours, 44 minutes, 50 secondsAnd what I'm going to do is I'm first going to get all the children inside of this folder. So, children, I'm going to use await context database query all
5:44:585 hours, 44 minutes, 58 secondsfiles with index by project and by parent. Again, I'm going to make this look a little bit prettier. I find it easier to understand this way. So the
5:45:075 hours, 45 minutes, 7 secondsway we are fetching all ch children of a folder is by using our project parent index and we're using item which we
5:45:145 hours, 45 minutes, 14 secondsfetched right here dot project ID and the current file ID as the parent ID because that file itself is a folder. So we need to find all of its children.
5:45:245 hours, 45 minutes, 24 secondsRight? And now that we have that we have to basically call this function
5:45:335 hours, 45 minutes, 33 secondsagain because each of these children can be a folder itself. So basically for
5:45:435 hours, 45 minutes, 43 secondseach child of the children defined above we need to call delete recursive once
5:45:505 hours, 45 minutes, 50 secondsmore and then if that child is a folder same thing will happen. That's how we're going to find every single child when we
5:45:595 hours, 45 minutes, 59 secondsdelete a folder. Great. And then outside of this if clause, if type is folder, let's go ahead and do delete storage
5:46:085 hours, 46 minutes, 8 secondsfile if it exists. So that's for files which are binary if you remember. We are going to have this scenario later in the
5:46:175 hours, 46 minutes, 17 secondsproject, but I think it makes sense to implement it now. So if we have storage ID, we should also clean up the storage,
5:46:245 hours, 46 minutes, 24 secondsright? No need to have that populate our uh storage usage. So if we have item storage ID, go ahead and delete it. And
5:46:345 hours, 46 minutes, 34 secondsthen finally delete the file or folder itself. So it's safely going to go ahead through all of the recursive uh things
5:46:425 hours, 46 minutes, 42 secondsit needs to do and then in the end it's going to delete itself. So we are actually not calling this method right
5:46:495 hours, 46 minutes, 49 secondsnow. You can see it's just defined. So after you define it right here, await delete recursive and the first file
5:46:575 hours, 46 minutes, 57 secondswe're going to pass inside will be the one we passed in the arguments here. There we go.
5:47:055 hours, 47 minutes, 5 secondsAnd since we're finishing all the uh functions for files, I want to add one more. Even though we're not exactly
5:47:135 hours, 47 minutes, 13 secondsgoing to be using this inside of the file explorer, it's going to be the one that uh well is going to be used later.
5:47:205 hours, 47 minutes, 20 secondsAnd that is the general update file. Why do I say we are not going to use this right now? Well, because I remind you we're just building the file explorer.
5:47:295 hours, 47 minutes, 29 secondsNow, so we are only going to be able to rename, delete, and create. The update file is basically referring to modifying
5:47:365 hours, 47 minutes, 36 secondsthe content of the file, the actual code inside. So, we're not going to see that now because we don't have the editor set
5:47:435 hours, 47 minutes, 43 secondsup yet. But still, let's get ready. So the arguments it will accept is the ID and the new content that it's going to accept. And then as usual, let's go
5:47:525 hours, 47 minutes, 52 secondsahead and get the handler here. So we can actually copy a lot of things from the lead file here. We can copy from
5:48:015 hours, 48 minutes, 1 secondidentity all the way to here. So let's go ahead and just add that here.
5:48:075 hours, 48 minutes, 7 secondsBasically we get the identity, we get the file. If file doesn't exist, we throw. If project doesn't exist, we
5:48:145 hours, 48 minutes, 14 secondsthrow. If we don't belong to a project, we throw. And now let's go ahead and define uh a variable called now to be date.now.
5:48:265 hours, 48 minutes, 26 secondsAnd then we're just going to go ahead and await context. database.patch
5:48:345 hours, 48 minutes, 34 secondsfiles arguments ID content arguments.content content and updated at to now. And one cool thing we're also
5:48:435 hours, 48 minutes, 43 secondsgoing to do. So you see this right here which says saved two days ago. It would
5:48:495 hours, 48 minutes, 49 secondsbe fun for this to update every time we do some modifications for the files table because right now
5:48:595 hours, 48 minutes, 59 secondseven though we modify updated at individually in the files you can see
5:49:055 hours, 49 minutes, 5 secondshere for example this doesn't update the project table last updated at. So let's
5:49:135 hours, 49 minutes, 13 secondsstart with the last one, the last uh function we developed the new one update file at the end here. How about we add
5:49:235 hours, 49 minutes, 23 secondsand also update the projects. So context database patch projects file project ID
5:49:315 hours, 49 minutes, 31 secondsupdated at now. And I feel like this is a cool thing that we can now add into other places too. So I'm going to copy
5:49:385 hours, 49 minutes, 38 secondsthis. I'm going to find delete file. How about we do the same thing after you do the recursive delete? Let's also, you
5:49:475 hours, 49 minutes, 47 secondsknow, update a project here date.now like this, right? So, we kind of say, hey, some files were just deleted in
5:49:565 hours, 49 minutes, 56 secondsthis project. That probably means that when the user hovers over, we should say, yeah, we just saved those changes.
5:50:065 hours, 50 minutes, 6 secondsI think that makes sense. So I'm going to copy this again and let me add it to rename file as well.
5:50:155 hours, 50 minutes, 15 secondsAll of that makes sense if you ask me.
5:50:175 hours, 50 minutes, 17 secondsIf you want to use the exact one, you can do const now and then replace both of this to use the same one.
5:50:275 hours, 50 minutes, 27 secondsSo that's the rename file. We have create folder.
5:50:335 hours, 50 minutes, 33 secondsLooks like this one doesn't have project ID, but it does have arguments. project ID.
5:50:395 hours, 50 minutes, 39 secondsI'm just going to go ahead and make sure I have this. So now I'm going to use now here and here.
5:50:495 hours, 50 minutes, 49 secondsOkay.
5:50:505 hours, 50 minutes, 50 secondsSo that was create folder. Now let's do create file
5:50:565 hours, 50 minutes, 56 secondsconst now new. Whoops. date.now remove this and use the constant
5:51:065 hours, 51 minutes, 6 secondsand let's see what else create file get folder contents shouldn't update it get file should not update it and get files
5:51:155 hours, 51 minutes, 15 secondsshouldn't either so I believe those are all the changes we need for our files functions let's check convex and let's
5:51:235 hours, 51 minutes, 23 secondsrun npx convex dev just to confirm we have no bugs when it comes to uploading these functions. There we go. All
5:51:315 hours, 51 minutes, 31 secondsfunctions ready. So, we are now ready uh to build the UI. So, I'm going to go back inside of source features projects
5:51:405 hours, 51 minutes, 40 secondscomponents and I'm going to go inside of project ID view.
5:51:465 hours, 51 minutes, 46 secondsAnd inside of project ID view, we have the placeholder for an editor. So, let's go ahead and actually make this have its
5:51:545 hours, 51 minutes, 54 secondsown allotment panes. We're going to start by defining the constants, the minimum sidebar width, the maximum
5:52:025 hours, 52 minutes, 2 secondssidebar width, default, and default main size. And then let's go ahead and let's import aotment, our package that we used
5:52:115 hours, 52 minutes, 11 secondsin the previous chapter. And let's go ahead and prepare the layout of the editor.
5:52:185 hours, 52 minutes, 18 secondsSo, inside of here, instead of rendering just an empty uh div with a text editor, let's render a lotment.
5:52:305 hours, 52 minutes, 30 secondsThe allotment will have default sizes, default sidebar width, and the default main size.
5:52:385 hours, 52 minutes, 38 secondsThe children are going to be an allotment.pane.
5:52:425 hours, 52 minutes, 42 secondsAnd this allotment pane will be our file explorer.
5:52:495 hours, 52 minutes, 49 secondsAnd another allotment pane will be the editor view.
5:52:545 hours, 52 minutes, 54 secondsAnd now let's go ahead and give this a lotment pane for the file explorer
5:53:005 hours, 53 minutessnap minimum size, maximum size, and preferred size.
5:53:065 hours, 53 minutes, 6 secondsSo now you should be able to see another split pane right here. In the preview, it shouldn't exist. It should only exist
5:53:165 hours, 53 minutes, 16 secondswhen the user selects they want to see the code. So basically the file explorer
5:53:235 hours, 53 minutes, 23 secondsis where they are going to see uh well the list of files right and the editor
5:53:305 hours, 53 minutes, 30 secondsview you can see is larger and in here is where they're going to write the actual code and they will be able to expand this or they will be able to
5:53:395 hours, 53 minutes, 39 secondscollapse it and they can always bring it back. So now we can go ahead and develop the file explorer.
5:53:475 hours, 53 minutes, 47 secondsSo I'm going to keep the project ID open.
5:53:515 hours, 53 minutes, 51 secondsAnd inside of project components, I will create a new file. File explorer.
5:53:575 hours, 53 minutes, 57 secondsInside of file explorer, let's add an index.tsx.
5:54:025 hours, 54 minutes, 2 secondsAnd I will do export const file explorer.
5:54:085 hours, 54 minutes, 8 secondsreturn a div with a class name full height background
5:54:145 hours, 54 minutes, 14 secondscolor of sidebar scroll area from components UI scroll area
5:54:235 hours, 54 minutes, 23 secondsa div with a ro of button let's give it on click for now to just
5:54:325 hours, 54 minutes, 32 secondsbe an empty arrow function a class name of group forward/ / project
5:54:395 hours, 54 minutes, 39 secondscursor pointer full width text left
5:54:455 hours, 54 minutes, 45 secondsflex items center gap.5 height of 22 pixels background color of accent and
5:54:545 hours, 54 minutes, 54 secondsfont bold. Let's see how we can write this. So we can write this as height 5.5.
5:55:025 hours, 55 minutes, 2 secondsThere we go.
5:55:045 hours, 55 minutes, 4 secondsInside of here we're going to render a chevron. right icon from Lucid React.
5:55:115 hours, 55 minutes, 11 secondsWe're going to give the chevron right icon a dynamic class name. So, make sure to import the CN util.
5:55:205 hours, 55 minutes, 20 secondsAnd I'm going to add the following. I'm also going to add a state is open set is open here. Use state with a default one set to false.
5:55:335 hours, 55 minutes, 33 secondsAnd I think that's the only one I'm going to need right now. So then I can modify this div with a row of button to
5:55:405 hours, 55 minutes, 40 secondsuse set is open and set it to whatever is the opposite of the current
5:55:465 hours, 55 minutes, 46 secondsvalue like this. So like a toggle. And then inside of here the default class of
5:55:535 hours, 55 minutes, 53 secondsthis chevron right icon will be size four shrink zero and text muted foreground.
5:56:015 hours, 56 minutes, 1 secondBut if is open, we're going to rotate it by 90°.
5:56:085 hours, 56 minutes, 8 secondsLet's take a look at how this actually looks like. The only thing I have to personally do is rearrange my imports because I prefer them this way. Great.
5:56:175 hours, 56 minutes, 17 secondsSo, we now have the file explorer and I've purposely created it inside of a folder because we're going to have many subcomponents here. So let's go inside
5:56:265 hours, 56 minutes, 26 secondsof project ID view here and let's replace the placeholder file explorer with the actual
5:56:355 hours, 56 minutes, 35 secondsfile explorer. Let's click save. There we go. So you should now have this. And
5:56:415 hours, 56 minutes, 41 secondsyou can see how it kind of opens right when you click on it. The chevron rotates by 90°.
5:56:495 hours, 56 minutes, 49 secondsOkay. Now what we have to do is we have to bring the project information from file explorer I mean from project ID
5:56:565 hours, 56 minutes, 56 secondsview to the file explorer. We're going to do that using the project ID.
5:57:025 hours, 57 minutes, 2 secondsSo inside of here just go ahead and pass it.
5:57:065 hours, 57 minutes, 6 secondsNow inside of here uh we have to well define uh the props that it accepts. But that's quite easy. So it's going to be the only prop.
5:57:165 hours, 57 minutes, 16 secondsSo project ID is a type of project is a type of project ID. Yeah. So just import this.
5:57:275 hours, 57 minutes, 27 secondsAnd now in order to load a project using this project ID, we uh we have to call our use project hook. So const project
5:57:365 hours, 57 minutes, 36 secondsuse project from hooks use projects and pass in project ID. So just make sure you've imported hooks use project.
5:57:455 hours, 57 minutes, 45 secondsGreat. And now that we have the project, we can actually go down here uh right after the chevron right icon. Open a
5:57:535 hours, 57 minutes, 53 secondsparagraph and just render project question mark name or fall back to loading. And let's give this a text
5:58:015 hours, 58 minutes, 1 secondextra small uppercase and line clamp one.
5:58:065 hours, 58 minutes, 6 secondsAnd just like that, you should now have your project's name printed out right here.
5:58:135 hours, 58 minutes, 13 secondsGreat. So now what we have to do is we have to add a button that will allow us to create new files or folders.
5:58:245 hours, 58 minutes, 24 secondsSo I'm going to go ahead after this paragraph and I'm going to create a div.
5:58:285 hours, 58 minutes, 28 secondsNow this div will have a following class name opacity zero. On group hover, let
5:58:365 hours, 58 minutes, 36 secondsme go ahead and expand this so you can see it in one line. on group hover but specifically on the project group we are
5:58:435 hours, 58 minutes, 43 secondsgoing to change the opacity to 100 transition will be none duration will be none we're going to have flex items
5:58:515 hours, 58 minutes, 51 secondscenter gap.5 and margin left of auto in here I'm going to render chaten button
5:58:595 hours, 58 minutes, 59 secondsso I'm just going to move it here now let's go down to the button the button in here is going to have an
5:59:075 hours, 59 minutes, 7 secondson click And the first thing we're going to do is stop propagation.
5:59:135 hours, 59 minutes, 13 secondsWe're also going to prevent default set is open to true.
5:59:185 hours, 59 minutes, 18 secondsAnd let's just add set creating to true com comment here.
5:59:265 hours, 59 minutes, 26 secondsLet's go ahead and give it a variant of highlight.
5:59:345 hours, 59 minutes, 34 secondsLet's go ahead and give it a size of icon extra small. Uh, okay. So, what exactly is not working here? Button from
5:59:435 hours, 59 minutes, 43 secondscomponents UI button. Uh, okay. I think we're going to have to create both of those variants actually. So, let's go
5:59:515 hours, 59 minutes, 51 secondsahead and commandclick instead of button or go inside of source components UI and find a button here. And what I'm going to do is I'm going to change the sizes
6:00:006 hourshere. So, I need a size smaller than this. So, I'm going to add size 5.5. And I'm going to make it rounded like this.
6:00:116 hours, 11 secondsAnd for the variance, I'm also going to create my own variant called highlight.
6:00:176 hours, 17 secondsIt's going to have a transparent background. On hover, it's going to use BGX in foreground, but only on 5%
6:00:246 hours, 24 secondsopacity. And save the file. Close the button and go back. And you can see that now these are fully supported. So that's
6:00:326 hours, 32 secondsthe power of chat and UI. We can now uh modify our button source code in real time. Right? So inside of this button uh
6:00:416 hours, 41 secondsgo ahead and create file plus corner icon from Lucid React. And I think you can already see how this is going to
6:00:486 hours, 48 secondslook like. When you hover, you should see a button. Let me go ahead and zoom in a bit. When you hover, you should see a button here. Maybe I can snap this.
6:00:566 hours, 56 secondsThere we go. You should see a button which will be used to create new files.
6:01:016 hours, 1 minute, 1 secondAnd while we are here, we can also copy this button.
6:01:056 hours, 1 minute, 5 secondsSo this one will be used set creating folder to true and the icon will be
6:01:146 hours, 1 minute, 14 secondsfolder plus icon from Lucid React. So just make sure you've imported that. And let's go ahead and copy this one one more time.
6:01:246 hours, 1 minute, 24 secondsAnd then this one uh this one will be a little bit different. So this one will just be reset collapse. This one will be used to like collapse or expand again.
6:01:366 hours, 1 minute, 36 secondsSo let me show you. Copy minus icon from Lucid React again and give it a class name size 3.5. Let
6:01:466 hours, 1 minute, 46 secondsme fix the typo in the class name. So let's see all the three icons that we have now. So in here you can create new
6:01:536 hours, 1 minute, 53 secondsfile, new folder and you can kind of collapse the entire thing. So the
6:02:006 hours, 2 minuteseasiest one to implement right away might actually be the collapse one.
6:02:076 hours, 2 minutes, 7 secondsSo we're going to go ahead and just add a new state here. Collapse key and set
6:02:136 hours, 2 minutes, 13 secondscollapse key and make the use state be at zero. And while we are here, let's
6:02:206 hours, 2 minutes, 20 secondsalso implement creating and set creating from use state. So we will only be able
6:02:296 hours, 2 minutes, 29 secondsto create a file or a folder. And by default, it's going to be null. So let's set it to null.
6:02:396 hours, 2 minutes, 39 secondsGreat. Now that we have this, let's go ahead and check out the last button here.
6:02:496 hours, 2 minutes, 49 secondswhich is basically reset collapse.
6:02:536 hours, 2 minutes, 53 secondsSo what we're going to do is we're just going to increase the current or whatever it was the previous collapse key by one.
6:03:026 hours, 3 minutes, 2 secondsAnd the way we're going to be using this is so that later when we implement the
6:03:096 hours, 3 minutes, 9 secondsrecursive tree when the user clicks on this minus thing it will kind of uh
6:03:186 hours, 3 minutes, 18 secondsrecolapse the entire thing and user will have to load everything again. It serves as a kind of hard refresh of the entire
6:03:266 hours, 3 minutes, 26 secondsthing. Not much purpose right now. If you click on it, nothing's happening. But it you will see how it works later.
6:03:326 hours, 3 minutes, 32 secondsPerhaps I've implemented it too early, so you're just confused now. But you're going to see it's not too complicated.
6:03:376 hours, 3 minutes, 37 secondsIt's it's like it's we're purposely going to change the key property that we're going to pass down here to some elements. So that's how it's going to
6:03:456 hours, 3 minutes, 45 secondswork. And we could also set is open to false at that point, I think.
6:03:546 hours, 3 minutes, 54 secondsOr maybe not actually. Oh, well, we are implementing this. I can show you exactly what we're doing. This that's what we're doing.
6:04:046 hours, 4 minutes, 4 secondsSo, yeah, it actually doesn't have to close the entire thing. It will literally just collapse all the folders that were opened.
6:04:136 hours, 4 minutes, 13 secondsOkay. So now let's take a brief pause at developing the file explorer and instead let's go ahead inside of project hooks and let's create use files.
6:04:266 hours, 4 minutes, 26 secondsAnd inside of here let's go ahead and add our well let's see um I'm trying to
6:04:346 hours, 4 minutes, 34 secondssee what would be the most useful one for us to have. I think the most useful one would be to list files and to create
6:04:446 hours, 4 minutes, 44 secondsfiles. So let's go ahead and do export con use use create file
6:04:546 hours, 4 minutes, 54 secondsand uh we're going to do use create folder. They're going to be quite similar. So we're just going to copy and paste them. So we're going to pass project ID and parent ID.
6:05:046 hours, 5 minutes, 4 secondsThe types are going to be project ID, a type of ID, projects, parent ID
6:05:136 hours, 5 minutes, 13 secondsis going to be optional, and it's going to be a type of files.
6:05:186 hours, 5 minutes, 18 secondsSo, just make sure you set the parent ID to optional because it's not required, right?
6:05:246 hours, 5 minutes, 24 secondsAnd let's return use mutation API.
6:05:286 hours, 5 minutes, 28 secondsUh oh, we need to import API dot files.create file.
6:05:366 hours, 5 minutes, 36 secondsSo for now, that's all we have to do.
6:05:396 hours, 5 minutes, 39 secondsIn fact, yeah, I don't think we even need to pass the project ID and the parent ID. And that reminds me, we also
6:05:476 hours, 5 minutes, 47 secondshave to fix that problem from the previous chapter that Code Rabbit told us about. And I think we're doing the
6:05:546 hours, 5 minutes, 54 secondssame mistake here. You know what? Let's do this. Don't pass anything.
6:06:006 hours, 6 minutesJust very simply do this. And then in here, let's do use create folder.
6:06:086 hours, 6 minutes, 8 secondsCreate folder.
6:06:116 hours, 6 minutes, 11 secondsJust keep it simple. Now let's go back inside of index here. Basically our file explorer. Let's do con handle create.
6:06:236 hours, 6 minutes, 23 secondsAnd in here the name will be string. Now above this let's define create file
6:06:316 hours, 6 minutes, 31 secondsuse create file create folder use create folder.
6:06:406 hours, 6 minutes, 40 secondsSo I've just imported from my hooks those two new hooks we've just created.
6:06:496 hours, 6 minutes, 49 secondsNow that I have those, I'm going to first set creating back to null. And then I'm going to do if creating is
6:06:566 hours, 6 minutes, 56 secondsequal to file. I'm going to call create file.
6:07:016 hours, 7 minutes, 1 secondI'm going to pass in the project ID, the name, the content to be empty, and the parent ID to be undefined.
6:07:136 hours, 7 minutes, 13 secondscreating else create folder with project ID name
6:07:206 hours, 7 minutes, 20 secondsand parent ID explicitly to be undefined.
6:07:266 hours, 7 minutes, 26 secondsAll right. So now we have our handle create method right here.
6:07:326 hours, 7 minutes, 32 secondsAnd now in these buttons here, let's go ahead and make this one change
6:07:396 hours, 7 minutes, 39 secondsset creating to be file and this one to be set creating to be folder like that.
6:07:536 hours, 7 minutes, 53 secondsAnd now I'm going to go ahead outside of these two divs, but still inside of the scroll area. And I'm going
6:08:016 hours, 8 minutes, 1 secondto do if it's open, let's go ahead and render a fragment.
6:08:066 hours, 8 minutes, 6 secondsAnd if we are creating something, let's go ahead and do the create input here.
6:08:146 hours, 8 minutes, 14 secondsSo the create input will have a type of creating. So what are we creating? A file or a folder? It's going to have a
6:08:226 hours, 8 minutes, 22 secondslevel which is going to be zero right now because this is kind of the root on submit which will be handle create on
6:08:306 hours, 8 minutes, 30 secondscancel which is just going to set creating back to null and that's the only thing we're
6:08:376 hours, 8 minutes, 37 secondsgoing to do now because in order to fetch any file we first need to create it right now let's go ahead inside of the file
6:08:456 hours, 8 minutes, 45 secondsexplorer new file create input dsx X. Okay.
6:08:546 hours, 8 minutes, 54 secondsSo, I'm going to go ahead and import chevron right icon from Lucid React.
6:09:036 hours, 9 minutes, 3 secondsI'm going to import file icon and I'm going to import a folder icon from a package. We have to install React
6:09:126 hours, 9 minutes, 12 secondssymbols. So, react- symbols forward slash icons forward slashutils.
6:09:206 hours, 9 minutes, 20 secondsLet's go ahead and let's import react symbols mpm install
6:09:286 hours, 9 minutes, 28 secondsuh react- symbols. And let me actually check. I think the full package name is forward slash icons.
6:09:376 hours, 9 minutes, 37 secondsSo, I'm going to show you what is my latest version here. We should no longer have an error here.
6:09:446 hours, 9 minutes, 44 secondsThere we go. That's resolved. So I'm using 1.3.0.
6:09:536 hours, 9 minutes, 53 secondsAnd from here I can import file icon and folder icon from react symbols icons utils like this. Let's export const create input.
6:10:076 hours, 10 minutes, 7 secondsLet's go ahead and define the types. So type will be either file
6:10:146 hours, 10 minutes, 14 secondsor folder. Level is going to be a number. Onsubmit will be a function which accepts a new name.
6:10:246 hours, 10 minutes, 24 secondsOn cancel will very simply be a void.
6:10:296 hours, 10 minutes, 29 secondsNow we can dstructure all of those above. So type level onsubmit and on cancel.
6:10:376 hours, 10 minutes, 37 secondsNow let's start by defining uh the value right let's import use state from react let me
6:10:466 hours, 10 minutes, 46 secondsmove this at the top so value and set value let's develop the handle submit
6:10:536 hours, 10 minutes, 53 secondsmethod inside of here we're going to trim the value so the user isn't able to
6:10:596 hours, 10 minutes, 59 secondspass like a blank space and if trimmed value still exists onsubmit trimmed value otherwise just cancel. Great.
6:11:126 hours, 11 minutes, 12 secondsNow let's go ahead and let's return a div here with a class name full width flex
6:11:206 hours, 11 minutes, 20 secondsitems center gap one height of 22 pixels or if I remember correctly
6:11:286 hours, 11 minutes, 28 seconds5.5 and the BG accent of 30.
6:11:356 hours, 11 minutes, 35 secondsAnd in here another div with a class name flex items center and the gap.5 if type is equal to folder.
6:11:486 hours, 11 minutes, 48 secondsRender a chevron right icon.
6:11:526 hours, 11 minutes, 52 secondsGive it a class name size for shrink zero and the text muted foreground.
6:12:016 hours, 12 minutes, 1 secondIf type is equal to file, go ahead and render file icon.
6:12:086 hours, 12 minutes, 8 secondsGive it a file name of value auto assign property and a class name of size four.
6:12:216 hours, 12 minutes, 21 secondsAnd let's go ahead and do one more type folder here.
6:12:286 hours, 12 minutes, 28 secondsfolder icon with a class name size four, file name actually folder name value
6:12:386 hours, 12 minutes, 38 secondslike this and then below this div an input
6:12:456 hours, 12 minutes, 45 secondsa native HTML one. Give it autofocus type of text value of value on change
6:12:546 hours, 12 minutes, 54 secondsevent set value event target value.
6:13:006 hours, 13 minutesNow let's go ahead and pass in the following class name flex one background transparent text
6:13:076 hours, 13 minutes, 7 secondssmall outline none focus ring one focus ring inset and focus ring ring. If the
6:13:166 hours, 13 minutes, 16 secondsuser blurs, we're going to consider that a submit. And then a very simple onkey down method which checks the if the
6:13:256 hours, 13 minutes, 25 secondsevent key is enter and submits. And it also checks if event key is escape and cancels.
6:13:336 hours, 13 minutes, 33 secondsThere we go. So there is actually one thing missing here, but I it's the level thing, right? But I just want to make
6:13:416 hours, 13 minutes, 41 secondssure that you can see what we're doing before we implement that. So, import the create input file. And now, if we've
6:13:486 hours, 13 minutes, 48 secondsdone this correctly, first things first, make sure you have this kind of opened, right? And click on this. And you should
6:13:576 hours, 13 minutes, 57 secondsnow be able to see an input to create a new file. But if you click this, you should see that it's kind of ready to create a new folder.
6:14:076 hours, 14 minutes, 7 secondsAnd the cool thing is if I go ahead and type, you know, test.js, JSX.
6:14:146 hours, 14 minutes, 14 secondsYou can see it changes the icon. If I do app.ts, it changes the icon. TSX changes the
6:14:226 hours, 14 minutes, 22 secondsicon. Again, same thing is true for folder. If I call this source, it will change the source. Test. Same thing. I
6:14:326 hours, 14 minutes, 32 secondscan't think of anyone now, but I don't know, images. There we go. Changes to an appropriate images file.
6:14:396 hours, 14 minutes, 39 secondsSo this package that does that magic is called React symbols and it's actually made by the same person who developed
6:14:476 hours, 14 minutes, 47 secondsSVGL app if you've heard about it where you can basically find a bunch of SVG it's made by uh this guy Pablo Hernandez
6:14:566 hours, 14 minutes, 56 secondsI hope I pronounced it correctly uh and icons crafted by Miguel. So, shout out to those guys. Amazing, amazing work.
6:15:046 hours, 15 minutes, 4 secondsAnd you can see 229 file icons uh and 93 folder icons. And all of these, you can
6:15:136 hours, 15 minutes, 13 secondssee we just installed a package and we just used their React symbols icons
6:15:206 hours, 15 minutes, 20 secondsutils file and folder icon which allow us to pass the file name and auto assign
6:15:276 hours, 15 minutes, 27 secondswhich icon should be used, right? So every single thing that you see here can be rendered as a type of file. So if I
6:15:366 hours, 15 minutes, 36 secondsuse docker or maybe it's test.docer actually I have no idea how to do it.
6:15:416 hours, 15 minutes, 41 secondsDocker file. There we go. It's docker file. Even cloud works right. So every single thing you see here can be used in
6:15:506 hours, 15 minutes, 50 secondsyour file explorer. And I just want to tell you one more thing. In case you're having troubles with this icons for
6:15:576 hours, 15 minutes, 57 secondswhatever reason, you can still continue with the project, right? I mean, icons were kind of the last thing I implemented in this project. The reason
6:16:056 hours, 16 minutes, 5 secondsI'm telling you is just in case you're having trouble. I don't know. Uh I've had only the great things to say about this package. But you never know, you
6:16:136 hours, 16 minutes, 13 secondsknow, if something's not working for you or images are not loading for whatever reason, you can always, you know, not have this logic at all and just use the
6:16:216 hours, 16 minutes, 21 secondsinput, right? But I think it should work just fine for you. Great. Uh so yes, I'm using React symbols icon utils and again
6:16:316 hours, 16 minutes, 31 secondsI'm using version 1.3.0 if you want to use the same one as me. Perfect. Uh so even if we actually created something
6:16:396 hours, 16 minutes, 39 secondsright now test.jsx uh we don't really know what happened until we go to our convex dashboard and
6:16:476 hours, 16 minutes, 47 secondswe go inside of the project. And here in the database, let's go inside of files. And here we go. Test.jsx.
6:16:566 hours, 16 minutes, 56 secondsAnd I even have a one from before called images. And I believe this one is a folder. It is great. So we can now
6:17:036 hours, 17 minutes, 3 secondsofficially create folders and files. The only thing that's kind of missing is this level thing. This level thing will
6:17:096 hours, 17 minutes, 9 secondsbe used. Let me show you exactly how. So this is the finished project.
6:17:166 hours, 17 minutes, 16 secondsYou can see that if I want to create a new file here, I kind of have to Well, this is a bad example because it moves everything for some reason. But yeah,
6:17:246 hours, 17 minutes, 24 secondsyou can see how it's indented inside, right? That's the level the level of indentation because the same component
6:17:326 hours, 17 minutes, 32 secondswill be used here, but also in here. And you can see the level of indentation is different, right? So
6:17:406 hours, 17 minutes, 40 secondsthat's what we're going to do now. So in order to develop that thing uh what we have to do is develop something called
6:17:496 hours, 17 minutes, 49 secondsget item padding and it's actually super simple to implement. So inside of file explorer create constants
6:17:586 hours, 17 minutes, 58 secondsds and let's define base padding and level padding. So base padding for root level
6:18:076 hours, 18 minutes, 7 secondsitems and then additional padding for per nesting level. So the further down
6:18:136 hours, 18 minutes, 13 secondswe go, it's going to move by 12. And now a very simple function here.
6:18:226 hours, 18 minutes, 22 secondsMy apologies.
6:18:246 hours, 18 minutes, 24 secondsGet item padding which accepts a level and is file boolean.
6:18:306 hours, 18 minutes, 30 secondsFiles need extra padding since they don't have the chevron. So if it's file 16, otherwise zero. and then a simple
6:18:396 hours, 18 minutes, 39 secondsfunction to create the new padding. What do I mean by file doesn't have a chevron? Well, take a look.
6:18:476 hours, 18 minutes, 47 secondsYou can see it's just a file icon, but a folder has a chevron icon. So, we need
6:18:546 hours, 18 minutes, 54 secondsto offset by the width of the chevron icon, which is 16 pixels basically to make these two look the same because
6:19:036 hours, 19 minutes, 3 secondsright now there's a visible size difference in width. Right? So that's what we're going to do. All right. So just make sure you've implemented get
6:19:116 hours, 19 minutes, 11 secondsitem padding. Let's go back inside of create input here. And now what I'm going to do
6:19:196 hours, 19 minutes, 19 secondsis I'm going to give this a style property because um Tailwind is kind of
6:19:276 hours, 19 minutes, 27 secondstricky when it comes to computed values because of its just in time compiler. So
6:19:336 hours, 19 minutes, 33 secondsI believe you cannot do things like this using tailwind. So we're going to pass in level and type equal to file.
6:19:466 hours, 19 minutes, 46 secondsI mean we're going to do like a type check, right? If the type is equal to file, then the second argument is file
6:19:536 hours, 19 minutes, 53 secondsis going to be true. So now let's go ahead and test this out. And there we go. You can see that now they are
6:20:016 hours, 20 minutes, 1 secondbriefly at the same width level and there's an overall indentation here happening.
6:20:106 hours, 20 minutes, 10 secondsNow I want to create a function or a hook more specifically that's actually going to help us see the files in our file explorer.
6:20:196 hours, 20 minutes, 19 secondsSo let's go inside of source features projects hooks and let's go inside of our use files. And now let's do export const use folder contents.
6:20:326 hours, 20 minutes, 32 secondsAnd in here we are going to accept project ID, parent ID, enabled
6:20:416 hours, 20 minutes, 41 secondsand hardcoded to true. And now in here, let's go ahead and uh give it the types.
6:20:476 hours, 20 minutes, 47 secondsProject ID is an ID type of projects. Parent ID is optional and ID of files.
6:20:536 hours, 20 minutes, 53 secondsAnd enabled is an optional boolean. And let's just return use query api.files
6:21:006 hours, 21 minutesget folder contents as the first argument. If this function is enabled, pass in the project ID and the parent
6:21:086 hours, 21 minutes, 8 secondsID. Otherwise, skip the query and import use query from convex react. There we
6:21:176 hours, 21 minutes, 17 secondsgo. Now we have use folder contents. Now that we have used folder contents, we can go back inside of our file explorer index.ts file.
6:21:296 hours, 21 minutes, 29 secondsAnd in here, I'm going to define root files.
6:21:326 hours, 21 minutes, 32 secondsAnd my root files will be use folder contents from here.
6:21:396 hours, 21 minutes, 39 secondsAnd I'm going to pass in project ID and enabled only if is open. So if we close,
6:21:506 hours, 21 minutes, 50 secondsno need to fetch because user isn't seeing anything anyways. All right.
6:21:566 hours, 21 minutes, 56 secondsNow, let me also move the use project together with it here. It kind of makes
6:22:036 hours, 22 minutes, 3 secondssense. Now that we have all of that, let's go ahead and do a very simple loading indicator.
6:22:116 hours, 22 minutes, 11 secondsSo if root files are undefined, it means they're loading. So let's render a
6:22:186 hours, 22 minutes, 18 secondsloading row and let's give it a level of zero. So you're going to see this behavior a lot of times. This level
6:22:246 hours, 22 minutes, 24 secondsthing is basically our level of children indentation and since this is the root level all of it is zero and then later
6:22:346 hours, 22 minutes, 34 secondsas we defined in our constants uh each extra child or nesting level will
6:22:426 hours, 22 minutes, 42 secondsincrease by 12. Right? So that's why all of these are zero. So all of this calculation will will result to zero because whatever you multiply right is
6:22:506 hours, 22 minutes, 50 secondszero and then plus the offset. So only the offset will actually be calculated.
6:22:566 hours, 22 minutes, 56 secondsSo loading row let's go inside of file explorer and create loading row.tsx.
6:23:056 hours, 23 minutes, 5 secondsAnd in here we import CN and we import spinner. We import get item padding from
6:23:126 hours, 23 minutes, 12 secondsconstants. Let's go ahead and export loading row with class name and level.
6:23:196 hours, 23 minutes, 19 secondsBoth of them are optional as you can see.
6:23:226 hours, 23 minutes, 22 secondsAnd then in here, let's go ahead and uh let's return my apologies. What am I doing wrong here?
6:23:326 hours, 23 minutes, 32 secondsOkay, let's return a div with a class name CN first argument height 5.5 flex
6:23:416 hours, 23 minutes, 41 secondsitems center and text muted foreground and pass in the class name if we ever want to modify it from outside. Now
6:23:496 hours, 23 minutes, 49 secondslet's pass in the style attribute here padding left get item padding level and
6:23:566 hours, 23 minutes, 56 secondshardcode this to true. So this isn't exactly a folder loading level, but we want to use the same offset as if it
6:24:056 hours, 24 minutes, 5 secondswere a file. So I'm hard coding the is file property to true just so it looks good. That's the only reason. And in
6:24:126 hours, 24 minutes, 12 secondshere we render the spinner and give it a class name size for text ring ml.5.
6:24:196 hours, 24 minutes, 19 secondsThere we go.
6:24:216 hours, 24 minutes, 21 secondsAnd now in here, let's import the loading row. There we go.
6:24:276 hours, 24 minutes, 27 secondsSo now if you refresh here for a brief second, well when you click open, you should see loading, right? And then it's
6:24:356 hours, 24 minutes, 35 secondssupposed to display all of the files. So that's what we're going to display now. Okay, let's go down here.
6:24:446 hours, 24 minutes, 44 secondsSo root files. Okay, let me expand this more. This is the creating scenario. And now we're going to have the actual root files.m mapap scenario.
6:24:576 hours, 24 minutes, 57 secondsSo question mark map get the individual item and for each item we're going to
6:25:036 hours, 25 minutes, 3 secondsrender something called a tree and then each tree is going to have a key item
6:25:116 hours, 25 minutes, 11 secondsunderscore id combined with what collapse key remember we are using that
6:25:186 hours, 25 minutes, 18 secondsso we easily reset the entire three structure so that's why we're doing that
6:25:256 hours, 25 minutes, 25 secondsGreat. Let's give it a item a level. So this one by default will be
6:25:336 hours, 25 minutes, 33 secondszero. This is the root one. And you're going to see when these levels will start to increase in a moment. And we pass in the project ID.
6:25:446 hours, 25 minutes, 44 secondsThere we go. Now let's go ahead and let's develop the tree component. So let me go ahead and close everything.
6:25:536 hours, 25 minutes, 53 secondsactually go inside of features, projects, components, file explorer, and let's do 3.dsx.
6:26:046 hours, 26 minutes, 4 secondsAnd in here again, let's import chevron, write icon, file icon, and folder icon from react symbols icon utils.
6:26:166 hours, 26 minutes, 16 secondsLet's go ahead and import CN from lib utils.
6:26:216 hours, 26 minutes, 21 secondsAnd let's go ahead and import uh use create file use create folder use folder
6:26:286 hours, 26 minutes, 28 secondscontents from features. Actually I think can we just do
6:26:356 hours, 26 minutes, 35 secondsuh yeah we can just do hooks use files like this or if you prefer you can use
6:26:426 hours, 26 minutes, 42 secondsforward slash features projects hooks like that. Either will work.
6:26:516 hours, 26 minutes, 51 secondsAnd now uh let's go ahead and also import get item padding from constants.
6:26:576 hours, 26 minutes, 57 secondsimport loading row import create input from create input
6:27:076 hours, 27 minutes, 7 secondsand import document from data model from convex
6:27:146 hours, 27 minutes, 14 secondsid as well and let's start building the tree. So the tree will be a very powerful component. It will be able to
6:27:226 hours, 27 minutes, 22 secondsdo everything that our uh index file explorer can but at an indented nested
6:27:296 hours, 27 minutes, 29 secondslevel infinitely right recursively should I say maybe that's a better word for it. So let's first define the types.
6:27:386 hours, 27 minutes, 38 secondsIt will accept an ID, my apologies, an item, which is a type of file, level, which is an optional number, and the project ID.
6:27:496 hours, 27 minutes, 49 secondsLet's hardcode the level to zero when we extract it. Now, in here, we're going to start the same is open. Set is open.
6:28:006 hours, 28 minutesUse state false. Make sure to import use state from React. I'm just going to move it to the top here.
6:28:096 hours, 28 minutes, 9 secondsOkay, now that we have that, let's go ahead and add is renaming set is
6:28:156 hours, 28 minutes, 15 secondsrenaming use date false
6:28:216 hours, 28 minutes, 21 secondsand oops, let's do creating set creating
6:28:286 hours, 28 minutes, 28 secondsuse state and by default null. And now we simply go ahead and we give it those three possible types.
6:28:376 hours, 28 minutes, 37 secondsfile folder or null. Great.
6:28:436 hours, 28 minutes, 43 secondsSo now let's actually go ahead and pause and let's go back instead of hooks use files.
6:28:496 hours, 28 minutes, 49 secondsAnd I want to add use rename file.
6:28:586 hours, 28 minutes, 58 secondsRename file. And I want to add use delete file.
6:29:076 hours, 29 minutes, 7 secondsdelete file. And as far as I know, those are the only ones we need. I think we have create folder, we have create
6:29:156 hours, 29 minutes, 15 secondsfile, we have rename file, we have delete file. I think that should be okay.
6:29:226 hours, 29 minutes, 22 secondsSo now back inside of the tree here, let's import use rename file and use delete file from hooks. And now let's
6:29:316 hours, 29 minutes, 31 secondsprepare them right here because we are going to kind of use all of them here. So con rename file.
6:29:416 hours, 29 minutes, 41 secondsUse rename file. Let me fix the typo.
6:29:476 hours, 29 minutes, 47 secondsThen this one will be delete file. So use delete file.
6:29:536 hours, 29 minutes, 53 secondsCreate file. Use create file. This one will be create folder.
6:30:006 hours, 30 minutesUse create folder.
6:30:036 hours, 30 minutes, 3 secondsAll right, perfect. Then let's do con folder contents. Use folder contents.
6:30:116 hours, 30 minutes, 11 secondsPass in the project ID. Parent ID to be item
6:30:176 hours, 30 minutes, 17 secondsunderscore ID enabled to be item. is equal to folder
6:30:256 hours, 30 minutes, 25 secondsand only in that scenario we check for is open. Great.
6:30:326 hours, 30 minutes, 32 secondsNow let's go ahead and well let's um let's check. So actually yeah
6:30:416 hours, 30 minutes, 41 secondsuh here's the thing. We can start rendering things but we are missing a wrapper component. So I'm trying to
6:30:496 hours, 30 minutes, 49 secondsthink of how do I code this? So you don't because we've coded a lot right now but we aren't seeing anything and I don't like that since you know you're
6:30:576 hours, 30 minutes, 57 secondsjust getting confused like what are you coding here? So let me try and do something. How about we do this? If item
6:31:066 hours, 31 minutes, 6 secondstype is equal to file, let's just return a div which says I am a file.
6:31:136 hours, 31 minutes, 13 secondsAnd then down here let's just return a div. I am a folder.
6:31:226 hours, 31 minutes, 22 secondsThen let's go back inside of file explorer index and let's import tree
6:31:296 hours, 31 minutes, 29 secondsfrom dot forward slash tree and you should now see I am a folder and I am a file. If I click on a new file I
6:31:386 hours, 31 minutes, 38 secondsshould see a new one. If I click on a new folder I should see a new folder.
6:31:436 hours, 31 minutes, 43 secondsRight? But in order to display them properly we have to develop something called a tree item wrapper.
6:31:516 hours, 31 minutes, 51 secondsSo, inside of the components right here, inside of file explorer, let's create tree- item-wrapper.tsx.
6:32:026 hours, 32 minutes, 2 secondsLet's go ahead and all add all the imports. So, CN from lib utils. And then let's add all the components from
6:32:096 hours, 32 minutes, 9 secondscontext menu. So, the menu, menu item, menu content, trigger, shortcuts, and separator.
6:32:176 hours, 32 minutes, 17 secondsThen let's also import the constants meaning get item padding and document
6:32:246 hours, 32 minutes, 24 secondsfrom convex generated data model. And now let's export const tree item wrapper. Now this is a component that's
6:32:336 hours, 32 minutes, 33 secondsgoing to have a lot of props. So let's go ahead and extract all of them.
6:32:406 hours, 32 minutes, 40 secondsitem children level is active on click on doubleclick on rename on delete on
6:32:466 hours, 32 minutes, 46 secondscreate file and on create folder and inside of its props we're going to define each of them item is a type of
6:32:556 hours, 32 minutes, 55 secondsdocument file children are react.react React node level is a required number is active is an optional boolean on click
6:33:036 hours, 33 minutes, 3 secondsis an optional function as well as all the other functions. So all of them are optional.
6:33:096 hours, 33 minutes, 9 secondsGreat. Now in here let's go ahead and let's return a context menu
6:33:176 hours, 33 minutes, 17 secondsand let's add context menu trigger.
6:33:226 hours, 33 minutes, 22 secondsLet's give it an as child property inside of here. Let's render a button and this button will simply render the
6:33:316 hours, 33 minutes, 31 secondschildren. The button will have an on click of on click on double click on double click. So same named prompts on
6:33:406 hours, 33 minutes, 40 secondskey down event if event key is equal to enter.
6:33:486 hours, 33 minutes, 48 secondsWe're going to prevent default and attempt to call on rename.
6:33:556 hours, 33 minutes, 55 secondsAnd let's give it a class name which is going to be dynamic. So the classes that it's going to have is actually very
6:34:016 hours, 34 minutes, 1 secondsimilar to the create input one. Group flex items center gap one full width
6:34:096 hours, 34 minutes, 9 secondsheight of 22 pixels or 5.5 hover BG accent with 30% opacity outline
6:34:176 hours, 34 minutes, 17 secondsnone. And then all the focus ones and if is active
6:34:236 hours, 34 minutes, 23 secondsbg- accent with forward slash30 and then a style padding left
6:34:326 hours, 34 minutes, 32 secondsget item padding level item type is equal to file. This
6:34:406 hours, 34 minutes, 40 secondswill return true or false and give our is file boolean that value. Great. So
6:34:476 hours, 34 minutes, 47 secondsthat's for the context menu trigger. Now let's go inside of the context menu content on close auto focus here should simply
6:34:556 hours, 34 minutes, 55 secondsdo a prevent default class name should be W64.
6:35:046 hours, 35 minutes, 4 secondsAnd then inside of here, let's check if item dot type is equal to folder,
6:35:126 hours, 35 minutes, 12 secondswe should have a fragment rendered. And then we should have some items inside.
6:35:186 hours, 35 minutes, 18 secondsThe first item will be a context menu item which has a prop on click and class name text small with a label new file.
6:35:286 hours, 35 minutes, 28 secondsThen let's copy this, paste it, change this to new folder on create folder,
6:35:376 hours, 35 minutes, 37 secondsnew folder. And then below that, a context menu separator.
6:35:446 hours, 35 minutes, 44 secondsOtherwise, outside of this right here, still inside of the context menu content,
6:35:526 hours, 35 minutes, 52 secondsrender another context menu item with a prop on click on rename class name text
6:35:596 hours, 35 minutes, 59 secondssmall, a rename label, a context menu shortcut
6:36:066 hours, 36 minutes, 6 secondselement next to its label which simply says enter.
6:36:126 hours, 36 minutes, 12 secondsAnd then last item, we can actually duplicate this one if
6:36:186 hours, 36 minutes, 18 secondsit's easier that way. This one should say delete permanently
6:36:276 hours, 36 minutes, 27 secondsand it should have an on click on delete and its context menu shortcut will be
6:36:356 hours, 36 minutes, 35 secondsthe command icon and backspace. We're going to implement these shortcuts later. For now, let's just have them visually. Some of you have already
6:36:446 hours, 36 minutes, 44 secondsguessed what this is. We've created this tree item wrapper. So that every time we
6:36:506 hours, 36 minutes, 50 secondsright click on something here, we have these options regardless how deep they
6:36:576 hours, 36 minutes, 57 secondsare, we're always going to have either rename or delete.
6:37:046 hours, 37 minutes, 4 secondsSo let's go ahead and continue developing now because the tree item is now finished. So we can now go back to tree.tsx.
6:37:156 hours, 37 minutes, 15 secondsSo I'm going to go ahead in here item type file and instead of rendering a div, we're going to render tree item
6:37:246 hours, 37 minutes, 24 secondswrapper. So the tree item wrapper can now be imported from here. And let's go ahead and give it some props. Item will be item. level will be level.
6:37:386 hours, 37 minutes, 38 secondsIs active will be is active. Uh looks like is active is we're not currently uh okay for now hardcoded to false.
6:37:506 hours, 37 minutes, 50 secondsOn click for now shouldn't do anything.
6:37:536 hours, 37 minutes, 53 secondsWe just have to remember to add it later. Same thing with on double click.
6:37:586 hours, 37 minutes, 58 secondsOn rename should simply trigger the set is renaming to true.
6:38:056 hours, 38 minutes, 5 secondsOn delete should let's add a comment close tab and
6:38:126 hours, 38 minutes, 12 secondsthen delete file and pass in the ID to be item ID. What does close tab mean?
6:38:206 hours, 38 minutes, 20 secondsBasically later when we have the logic to have open and closed tab tabs when we delete a file we should also close if
6:38:276 hours, 38 minutes, 27 secondsit's opened in the in the code editor right and what do we render inside well either
6:38:346 hours, 38 minutes, 34 secondsa file icon with file name file name let me just see uh so this file name
6:38:436 hours, 38 minutes, 43 secondslet's do const file name item name the reason I'm defining it in a constant is
6:38:516 hours, 38 minutes, 51 secondsbecause later when we add the rename functionality, we're going to pass it through this constant as well.
6:38:596 hours, 38 minutes, 59 secondsLet's go ahead and give this auto assign and class name size four
6:39:056 hours, 39 minutes, 5 secondsand a span here file name and a class name truncate and text small. Let me fix this. Truncate.
6:39:186 hours, 39 minutes, 18 secondsThere we go. So now your files should display properly. Perfect. Now
6:39:276 hours, 39 minutes, 27 secondslet's go ahead and do the same for folders.
6:39:316 hours, 39 minutes, 31 secondsSo I'm going to go ahead down here and I'm going to define folder name to be item.name.
6:39:406 hours, 39 minutes, 40 secondsAnd then let's go ahead and define const folder content.
6:39:476 hours, 39 minutes, 47 secondsOpen a fragment. Open a div. Give this a class name flex.
6:39:536 hours, 39 minutes, 53 secondsItems center and gap five. Open chevron right icon.
6:40:026 hours, 40 minutes, 2 secondsGive it a class name CN size. Whoops. Size dash4.
6:40:096 hours, 40 minutes, 9 secondsWhoops. Uh, shrink zero. Text muted foreground is open. Rotate 90 degrees.
6:40:196 hours, 40 minutes, 19 secondsThen render a folder icon from React symbols. Give it a folder name. Folder
6:40:266 hours, 40 minutes, 26 secondsname like this. Give it a class name size 4.
6:40:366 hours, 40 minutes, 36 secondsAnd outside of the div, render a span rendering the folder name. and give this
6:40:436 hours, 40 minutes, 43 secondsa class name truncate text small.
6:40:496 hours, 40 minutes, 49 secondsAnd then let's go ahead down here replace this with tree item wrapper.
6:40:586 hours, 40 minutes, 58 secondsGo ahead and render this within a fragment.
6:41:026 hours, 41 minutes, 2 secondsInside of tree item wrapper, render folder content. And in here, give it an item of item.
6:41:126 hours, 41 minutes, 12 secondsGive it a level of level and then give it on click to be just an
6:41:186 hours, 41 minutes, 18 secondsempty arrow function. Same thing for on double click on rename.
6:41:256 hours, 41 minutes, 25 secondsLet's give it set is renaming to true.
6:41:306 hours, 41 minutes, 30 secondson delete a comment to close the tab and then delete file
6:41:396 hours, 41 minutes, 39 secondsID item ID and I'm just going to change this to be to-do close tab and I'm going to change that
6:41:486 hours, 41 minutes, 48 secondshere as well so I remember to search for that later so I don't forget and in here
6:41:546 hours, 41 minutes, 54 secondslet's also add on create file start creating set it to file
6:42:036 hours, 42 minutes, 3 secondsand on create folder start creating and set it to folder. So we don't have start
6:42:116 hours, 42 minutes, 11 secondscreating. We can very easily implement that up here.
6:42:176 hours, 42 minutes, 17 secondsConst start creating accepts either a file or a folder set is
6:42:256 hours, 42 minutes, 25 secondsopen to true and set creating to the type past.
6:42:316 hours, 42 minutes, 31 secondsSo we don't have to do the same thing twice here. Great. And now here's the thing. We're not done yet when it comes
6:42:396 hours, 42 minutes, 39 secondsto folder because folder can be opened and in that case if the folder is opened guess what we have to render the entire
6:42:486 hours, 42 minutes, 48 secondsthing again. So let's go ahead and do if folder contents are undefined
6:42:556 hours, 42 minutes, 55 secondsrender the loading row with level level + one. So we are finally indenting now and if folder
6:43:056 hours, 43 minutes, 5 secondscontents question mark map get the individual sub item here and guess what
6:43:116 hours, 43 minutes, 11 secondswe render the tree itself give it a key of sub item underscore id
6:43:186 hours, 43 minutes, 18 secondsitem of sub item and a level
6:43:246 hours, 43 minutes, 24 secondsof level + one and finally the project ID There we go. So now we should have a
6:43:346 hours, 43 minutes, 34 secondsvery basic file explorer working. Let's try and see that. So I'm going to collapse the this and open this. And
6:43:426 hours, 43 minutes, 42 secondsthere we go. So now when I create a new file and call it, I don't know, image.
6:43:516 hours, 43 minutes, 51 secondsDSX, it's right here. When I create a new folder and I call it source, there we go. It's right here. The only thing
6:43:596 hours, 43 minutes, 59 secondsthat uh I don't see happening is that when I click on it, it should expand. So let's go ahead and just see uh how do we
6:44:086 hours, 44 minutes, 8 secondsdo that? Oh, okay. So down down here, tree item wrapper. Make sure it's the
6:44:166 hours, 44 minutes, 16 secondsone which actually is the folder one, right? Because we have two instances of three item wrappers.
6:44:256 hours, 44 minutes, 25 secondsone is here inside of an if clause if item type is file not that one down here
6:44:326 hours, 44 minutes, 32 secondsand find its on click and simply do set is open and then whatever is the
6:44:406 hours, 44 minutes, 40 secondsopposite of the current value and you can actually remove on double click nothing will happen if you double click on the folder you can of course modify
6:44:486 hours, 44 minutes, 48 secondsthat for yourself but there we go since we don't have any nested ones oh yeah and if you write I forgot to show you
6:44:556 hours, 44 minutes, 55 secondsthat if you right click you can now well you you can you can see the delete works. Yes, but none of the
6:45:036 hours, 45 minutes, 3 secondsother ones are actually working. So yeah, you can try out to delete. It should be working just fine. The only thing you cannot test is um kind of
6:45:126 hours, 45 minutes, 12 secondsnested files. But you can see I managed to delete all of my files. So that's working uh fine, right?
6:45:196 hours, 45 minutes, 19 secondsUh but the one we should uh test out and the one I hope to uh I hope to add a few
6:45:276 hours, 45 minutes, 27 secondsmore features and that is to rename a file and to create a new file and folder inside because I think that shouldn't be
6:45:366 hours, 45 minutes, 36 secondstoo complicated simply because we can just copy and paste the create input.
6:45:436 hours, 45 minutes, 43 secondsIn fact for creating itself we already have everything we need. We just have to find the folder content here.
6:45:516 hours, 45 minutes, 51 secondsSo right after we define it before we return this, let's check if is creating and do the following. Return a fragment.
6:46:036 hours, 46 minutes, 3 secondsOpen a button here, a native HTML button element, not chat one. Let's give it an on click. Set is open.
6:46:136 hours, 46 minutes, 13 secondsAnd then just do whatever is the opposite of its current value.
6:46:196 hours, 46 minutes, 19 secondsThat's the first one. Then let's go ahead and give it a class name. Its class name will have group flex items
6:46:286 hours, 46 minutes, 28 secondscenter gap one height of 5.5 hover BG accent with 30% opacity. cursor pointed
6:46:376 hours, 46 minutes, 37 secondspointer. Actually, we don't need cursor pointer since this is already a button. And full width.
6:46:436 hours, 46 minutes, 43 secondsThen let's go ahead and give it a style padding left get item padding level and false since we know this is a folder.
6:46:526 hours, 46 minutes, 52 secondsAnd inside render the folder content.
6:46:576 hours, 46 minutes, 57 secondsAnd then is open should go ahead and render a fragment.
6:47:056 hours, 47 minutes, 5 secondsand then render folder contents.
6:47:116 hours, 47 minutes, 11 secondsCheck if it's undefined and render the loading row.
6:47:156 hours, 47 minutes, 15 secondsGive it level level + one prop. Be very careful here. So, not folder content,
6:47:236 hours, 47 minutes, 23 secondsfolder contents, right? You should probably go through the code and confirm you aren't doing that anywhere. Or maybe we can rename
6:47:316 hours, 47 minutes, 31 secondsthis to something better. folder contents. I don't know, folder content contents files.
6:47:406 hours, 47 minutes, 40 secondsFor now, I'm just going to leave it to be this. But make sure you aren't mistaking this variable right here.
6:47:496 hours, 47 minutes, 49 secondsAll right. So, folder content is rendered inside of the button, but folder contents are all the files which
6:47:576 hours, 47 minutes, 57 secondsbelong to that folder. And then in here let's render the create input which we already have imported. Give it a type of creating.
6:48:096 hours, 48 minutes, 9 secondsGive it a level of level + one. Give it onsubmit to be handle create. I'm not sure we have that. We will implement it.
6:48:196 hours, 48 minutes, 19 secondsAnd let's have set creating to null.
6:48:226 hours, 48 minutes, 22 secondsHere we're not done yet. We also have to check if folder content has its children open. If it does, we have to render them using a tree.
6:48:346 hours, 48 minutes, 34 secondsAnd then let's simply pass all the props. The tree expects key item level, which is level plus one, and project ID.
6:48:436 hours, 48 minutes, 43 secondsSo the only one we don't have is the handle create method. So let's go up here
6:48:516 hours, 48 minutes, 51 secondsand let's add it const handle create will accept a name which is a string.
6:49:026 hours, 49 minutes, 2 secondsWe're going to set creating to null.
6:49:066 hours, 49 minutes, 6 secondsIf we are creating a file, we're going to call create file
6:49:136 hours, 49 minutes, 13 secondswith project ID name empty content and parent ID of item underscore id. Else we
6:49:216 hours, 49 minutes, 21 secondsare going to create a folder with project ID name and parent ID. Great.
6:49:296 hours, 49 minutes, 29 secondsWe shouldn't have any errors. And now if you make sure you have a folder, right
6:49:366 hours, 49 minutes, 36 secondsclick on it and new file. And you should be able to create inner file.
6:49:436 hours, 49 minutes, 43 secondsThere we go. You should also be able to do inner folder. Just like that. And guess what? You should also be able to
6:49:526 hours, 49 minutes, 52 secondsdo inner inner file and you should also be able to do inner inner folder. And I
6:49:596 hours, 49 minutes, 59 secondsthink you get the point. I know this was a lot of work, but you can see that now we can create infinite nested files and
6:50:086 hours, 50 minutes, 8 secondsfolders. We can also delete them. And here's the thing. So, I have one, two, three, let me see, one, two, three,
6:50:166 hours, 50 minutes, 16 secondsfour, five items here. If I delete app, I should have just one left. There we
6:50:246 hours, 50 minutes, 24 secondsgo. So our delete method is working correctly because all the nested files and folders were deleted as well. Very
6:50:326 hours, 50 minutes, 32 secondsvery good. One more thing left to do since we are that close to kind of wrapping up this chapter and it kind of
6:50:406 hours, 50 minutes, 40 secondsmakes sense to do this in this chapter and that is the rename functionality.
6:50:496 hours, 50 minutes, 49 secondsAnd I just can't get over how we are calling this thing folder content.
6:50:566 hours, 50 minutes, 56 secondsLet's call it folder render because it's so close to being called
6:51:046 hours, 51 minutes, 4 secondsfolder contents which is something completely different and I have a feeling this will just confuse people. So let's rename this to
6:51:126 hours, 51 minutes, 12 secondsfolder render and let's see all the places where that is supposed to be rendered. Inside of if creating as the
6:51:216 hours, 51 minutes, 21 secondschild of this button we should use folder render. Down here in the main
6:51:276 hours, 51 minutes, 27 secondsreturn tree wrapper should use folder render. Everywhere else we are using
6:51:366 hours, 51 minutes, 36 secondsfolder contents. So you can see I have seven instances.
6:51:426 hours, 51 minutes, 42 secondsOkay, well not all of them but five actually constant names folder contents
6:51:496 hours, 51 minutes, 49 secondsbut yeah technically seven instances if we also count the name of the hook. So make sure you have the same numbers and
6:51:566 hours, 51 minutes, 56 secondsthat you didn't accidentally use folder render somewhere else. All right, one
6:52:026 hours, 52 minutes, 2 secondsmore thing to do. We can do it. Let's start by implementing the function handle rename. The same way we have this
6:52:106 hours, 52 minutes, 10 secondshandle create. So handle rename accepts a new name. Set is renaming to false. If new name is equal to item.name, we
6:52:186 hours, 52 minutes, 18 secondsreturn. And let's go ahead and simply call from this rename file. Great.
6:52:256 hours, 52 minutes, 25 secondsThat's the handle rename. And now let's go ahead and we have to do it in two places now. and we actually have to
6:52:336 hours, 52 minutes, 33 secondscreate it first. So, let's go ahead and do the following. We're going to go inside of source features projects
6:52:426 hours, 52 minutes, 42 secondscomponents file explorer, copy the create input, and rename it to rename input like so.
6:52:516 hours, 52 minutes, 51 secondsInside of the rename input, make sure to immediately change this. And let's see the props. So most of this will be the
6:53:006 hours, 53 minutessame, but we're also going to have default value and is open.
6:53:056 hours, 53 minutes, 5 secondsSo let's make sure to add those two.
6:53:116 hours, 53 minutes, 11 secondsBesides that, uh on cancel. Yeah, we should also have on cancel. So yeah, let's let's leave it as is.
6:53:206 hours, 53 minutes, 20 secondsValue set value will be the same. Trimmed value.
6:53:266 hours, 53 minutes, 26 secondsYeah, I want I I want the exact same logic as in my create input. I think that kind of makes sense, right? So, let's see. With full flex item, center gap one, height 5.5, which is 22 pixels.
6:53:386 hours, 53 minutes, 38 secondsBG accent padding left. All of this looks perfectly fine. Chevron right icon.
6:53:466 hours, 53 minutes, 46 secondsThe only thing uh we should do here. So, we have is open here. So perhaps what we
6:53:546 hours, 53 minutes, 54 secondsshould do if type is folder, how about we go ahead and wrap this inside of CN.
6:54:026 hours, 54 minutes, 2 secondsSo make sure you import CN and if is open rotate by 90°. So even
6:54:116 hours, 54 minutes, 11 secondsokay just confirm you have this. So even in the rename input if the folder is opened let's rotate the chevron right icon. Let's be consistent, right?
6:54:216 hours, 54 minutes, 21 secondsBecause I think currently that's a bug, right? If I open a new folder and call it app.
6:54:286 hours, 54 minutes, 28 secondsUh, actually, I can't test it now. Yeah. Okay, maybe it's not a bug.
6:54:346 hours, 54 minutes, 34 secondsYeah, because all basically I was thinking, should this chevron rotate? It shouldn't because we never open a
6:54:426 hours, 54 minutes, 42 secondsnon-created folder. So, this is actually perfectly fine. We should only have is open here in the rename input. Okay.
6:54:506 hours, 54 minutes, 50 secondsNow, if it's type file, it's super simple. No changes here. And if it's type folder, same thing here. Uh I think
6:54:586 hours, 54 minutes, 58 secondsthat folder icon here doesn't accept is open. So, no need for that. Okay.
6:55:046 hours, 55 minutes, 4 secondsAnd now for the input, I think most of it is exactly the same. Autofocus type is text value is value. On change flex
6:55:126 hours, 55 minutes, 12 secondsone, BG transparent text small outline none. Focus is exactly the same. On blur, handle submit on key down.
6:55:236 hours, 55 minutes, 23 secondsAll right. The only thing I think I want to change is the following. I want to do on focus.
6:55:356 hours, 55 minutes, 35 secondsIf type is equal to folder, let's go ahead and simply select the
6:55:436 hours, 55 minutes, 43 secondsentire thing. But else if it's file, let's go ahead and do the following.
6:55:506 hours, 55 minutes, 50 secondsLet's get the value. Let's get last dot index value last index of dot. If last
6:56:006 hours, 56 minutesdot index is larger than zero, let's go ahead and set selection oop
6:56:086 hours, 56 minutes, 8 secondsset selection range to start from zero and go to the last dot index.
6:56:146 hours, 56 minutes, 14 secondselse select the entire thing.
6:56:196 hours, 56 minutes, 19 secondsYou're probably wondering what does that mean? You're going to see in a second.
6:56:236 hours, 56 minutes, 23 secondsIt's a small implementation which kind of improves the quality of life. So, okay, we have on blur on key down and we have on cancel.
6:56:336 hours, 56 minutes, 33 secondsSo, I think all of this should be fine.
6:56:386 hours, 56 minutes, 38 secondsOkay, let's go ahead and render it. So I'm going to go inside a file explorer
6:56:456 hours, 56 minutes, 45 secondstree right here. And the first place we should render this is down here. If item type is file. And now if is renaming.
6:56:576 hours, 56 minutes, 57 secondsWe have is renaming stored right here.
6:57:036 hours, 57 minutes, 3 secondsSo if is renaming, we're going to return rename input.
6:57:106 hours, 57 minutes, 10 secondsSo, make sure you import that because this is the first time we are adding it.
6:57:176 hours, 57 minutes, 17 secondsThe rename input should have a type of file because we know it's a type of file, a default value of file name,
6:57:266 hours, 57 minutes, 26 secondsa level of level, and onsubmit handle rename.
6:57:366 hours, 57 minutes, 36 secondsAnd we are missing on cancel here which should very simply uh set is renaming back to false.
6:57:476 hours, 57 minutes, 47 secondsSo let me just check how does handle rename work. If new name is item.name and inside of the rename input here.
6:57:566 hours, 57 minutes, 56 secondsUh okay. And I mean if it's new name should it also close? I don't know. We'll see.
6:58:036 hours, 58 minutes, 3 secondsSo now make sure you have a file. Right click, rename.
6:58:086 hours, 58 minutes, 8 secondsOkay, some kind of works, but not really.
6:58:126 hours, 58 minutes, 12 secondsUh, let's let's try this again. Right click, rename. Okay, so it offers me to rename. Does it work? Let's see something new. DSX.
6:58:226 hours, 58 minutes, 22 secondsIt seems to work, but not as I want it to. So it kind of completely resets the current state. Why is that happening?
6:58:306 hours, 58 minutes, 30 secondsLet's take a look. So if is renaming here.
6:58:366 hours, 58 minutes, 36 secondsOh, we are missing something. We have the default value which is file name.
6:58:406 hours, 58 minutes, 40 secondsLet's go inside of rename input here. We are never using the rename inputs default uh value. So the default value should first of all be here.
6:58:526 hours, 58 minutes, 52 secondsThat's the first thing.
6:58:546 hours, 58 minutes, 54 secondsAnd then in here for the trimmed value, let's do either trim the value or fall back to the
6:59:036 hours, 59 minutes, 3 secondsdefault value. And then in that case, we can just call onsubmit like that.
6:59:116 hours, 59 minutes, 11 secondsLet's see if that improves it. So right click, rename. There we go. Do you see what this focus thing did?
6:59:206 hours, 59 minutes, 20 secondsBasically, it made it behave the same way as it does in a real code editor.
6:59:266 hours, 59 minutes, 26 secondsWhen you focus on a file, it's not going to highlight the entire thing. It's going to carefully highlight only until
6:59:356 hours, 59 minutes, 35 secondsthe extension. So, you can safely rename it without changing the extension of the file, which is actually exactly how it
6:59:426 hours, 59 minutes, 42 secondsbehaves in this. Take a look. If I want to change this, if I rightclick and rename,
6:59:496 hours, 59 minutes, 49 secondsyou can see it only highlights up to the extension. So, I kind of wanted it to behave the same way. I want this to be a
6:59:576 hours, 59 minutes, 57 secondscool project, right? So, I'm focusing on those details.
7:00:027 hours, 2 secondsUh, great. So, we have that inside of the rename input. I think uh this
7:00:107 hours, 10 secondsbehaves quite well. I'm not sure if we have to change anything. Let's see what if I rename and escape. So it will just kind of cancel, right? It won't do
7:00:197 hours, 19 secondsanything. I think that's fine. I think that's perfectly fine behavior. And one more place where we have to do this now is down here. So let's just copy the if clause if creating.
7:00:337 hours, 33 secondsAnd let's go ahead and now do if is renaming like that.
7:00:397 hours, 39 secondsAnd then instead of a button here we will have a rename input.
7:00:447 hours, 44 secondsAnd the rename input we'll have a type of folder default value folder name is open is open level
7:00:547 hours, 54 secondslevel onsubmit handle rename and on cancel set is renaming to false. There we go.
7:01:047 hours, 1 minute, 4 secondsAnd let's see. Type null is not assignable.
7:01:107 hours, 1 minute, 10 secondsUm, how did that happen? Uh, [laughter] it's not assignable type type of folder.
7:01:197 hours, 1 minute, 19 secondsThat makes sense. Yes. I mean, I think all of this is still working just fine.
7:01:257 hours, 1 minute, 25 secondsHow about we go inside of the create input and we allow it to be null?
7:01:337 hours, 1 minute, 33 secondsI don't think it's causing any problem.
7:01:387 hours, 1 minute, 38 secondsI think it works fine. I'm not sure if maybe it ruined something else here.
7:01:457 hours, 1 minute, 45 secondsNope. Uh, let me see. I think we can now rename folders. Yes, we can. So, if I change this to tests,
7:01:547 hours, 1 minute, 54 secondsthere we go. If I change this to something else, that works, too. One thing I don't like
7:02:017 hours, 2 minutes, 1 secondis the flash of a previous one. We can fix this with optimistic mutation, but since this chapter is already an hour
7:02:107 hours, 2 minutes, 10 secondsand 40 minutes long, I'm going to pause here. I think this will be the last thing we're going to implement. So,
7:02:167 hours, 2 minutes, 16 secondsbasically, you can see in 3.tsx, we successfully used every single thing.
7:02:217 hours, 2 minutes, 21 secondsWe no longer have any warnings about unused uh files or folders here. I guess if there was one thing I would have to
7:02:307 hours, 2 minutes, 30 secondsdo before we end. Uh I just want to make sure I kind of abruptly ended the is renaming here. I'm not sure I correctly
7:02:387 hours, 2 minutes, 38 secondschecked if that's really all we have to do but I think it is. Yeah, we have to render the rename input and then the rest is just the same. Uh folder
7:02:477 hours, 2 minutes, 47 secondscontents loading row level + one we Oh, create input.
7:02:527 hours, 2 minutes, 52 secondsOh, this is where it was throwing me the error.
7:02:577 hours, 2 minutes, 57 secondsOkay, in is renaming, we do not need the create input. Okay, we just need to
7:03:057 hours, 3 minutes, 5 secondscheck for folder contents. No need for the rename input. And I think that now instead of create input, I can remove
7:03:147 hours, 3 minutes, 14 secondsthis because we will never render the create input if we don't explicitly give it a type, I think.
7:03:257 hours, 3 minutes, 25 secondsOkay, I just lied because we do that here very clearly. But you can see that
7:03:317 hours, 3 minutes, 31 secondshere it is already kind of solved that it's not going to be null
7:03:397 hours, 3 minutes, 39 secondsbecause we check that right here. Okay, I understand now. Uh, okay. I guess there's only like one possible race
7:03:477 hours, 3 minutes, 47 secondscondition if you at the same time create and rename, but uh I'm not sure how that would happen. And so what if you do this and then right click. Yeah, you see it's
7:03:567 hours, 3 minutes, 56 secondsnot possible because that resets it. So yeah, it can only be creating or renaming, not both at the same time.
7:04:067 hours, 4 minutes, 6 secondsGreat. So quite powerful uh file explorer from this session. Uh we can do
7:04:137 hours, 4 minutes, 13 secondsso many things inside of here. Let's see. Can we rename? We can. Amazing.
7:04:197 hours, 4 minutes, 19 secondsAmazing. I'm going to test this thoroughly before the next chapter if I can detect any bugs. But I think we did a very good job here and you can test it
7:04:277 hours, 4 minutes, 27 secondstoo, you know. Uh, all right. One thing I want to do before we wrap up is just fix the bugs from the previous chapter.
7:04:367 hours, 4 minutes, 36 secondsSo the first thing is the invalid project ID label in our layout.tsx.
7:04:447 hours, 4 minutes, 44 secondsSo if we go inside of source app folder projects project ID layout here it is
7:04:517 hours, 4 minutes, 51 secondslet's change this to be a type of ID from convex projects. Okay that's one fixed.
7:05:017 hours, 5 minutes, 1 secondNow let's go down here. Okay we don't have to fix this one. This is just telling us that it's an incomplete implementation which it is. But in here
7:05:107 hours, 5 minutes, 10 secondswe do have something that's wrong and it's the op optimistic mutation. So let's go inside of our features projects
7:05:187 hours, 5 minutes, 18 secondshooks use projects and let's find this use rename project. There is no reason
7:05:257 hours, 5 minutes, 25 secondsthis hook should be accepting the project ID. Why? Because we have it in the arguments. We can just do arguments
7:05:357 hours, 5 minutes, 35 secondsdo ID. You can see we even have autocomplete.
7:05:397 hours, 5 minutes, 39 secondsSo we definitely know that this is the one. And I think that now works perfectly fine. Just in case we can
7:05:477 hours, 5 minutes, 47 secondscheck. Let's go back here. If I create a new one. Immediately created. Working just fine.
7:05:567 hours, 5 minutes, 56 secondsAwesome. So that all seems to be working. Let's close this and let's go ahead and merge our changes. Right. So
7:06:057 hours, 6 minutes, 5 secondsI'm going to shut down all of my terminals. Now this is chapter 9. So get add and then a
7:06:137 hours, 6 minutes, 13 secondsdot get commit 9 file explorer. Perfect.
7:06:217 hours, 6 minutes, 21 secondsGet checkout-b 09 file explorer.
7:06:277 hours, 6 minutes, 27 secondsGet push u origin 09 file explorer. Perfect. Once this is
7:06:367 hours, 6 minutes, 36 secondspushed, you will see in your IDE the file explorer. And now let's go inside
7:06:437 hours, 6 minutes, 43 secondsof our repository and let's open a new pull request. This was a lot of new
7:06:507 hours, 6 minutes, 50 secondsfiles, 17. So definitely a good idea to get it checked by code rabbit.
7:06:567 hours, 6 minutes, 56 secondsAnd here is the summary. New features.
7:06:597 hours, 6 minutes, 59 secondsWe introduced a file explorer with collapsible tree view for managing project files and folders. We can create files and folders with inline editing.
7:07:107 hours, 7 minutes, 10 secondsWe can rename and delete files or folders via context menu options. We've added split pane layout with the file explorer sidebar and the editor pane.
7:07:217 hours, 7 minutes, 21 secondsFolder contents has sorted with folders first and then files alphabetically.
7:07:287 hours, 7 minutes, 28 secondsProject timestamps automatically updates when file changes. And now in here we have some comments. First things first,
7:07:377 hours, 7 minutes, 37 secondsit commented on my usage of convex's context.
7:07:427 hours, 7 minutes, 42 secondsSo as I told you in the past, Convex actually didn't allow um passing the
7:07:507 hours, 7 minutes, 50 secondstable name, right? They just ex uh accepted the ID, right? this didn't exist like a few weeks ago. So that's why AI is still outdated on that.
7:08:017 hours, 8 minutes, 1 secondUsually you would just pass in the arguments ID. So this is actually an update, a very recent one. So So I gave
7:08:087 hours, 8 minutes, 8 secondsit information about that that the Convex's API has updated and you can see that it read the documentation and it
7:08:177 hours, 8 minutes, 17 secondsupdated its learnings. So very cool to see how even these production grade applications are using something like
7:08:257 hours, 8 minutes, 25 secondsfirecrol to update their learnings which is exactly what we implemented a few chapters ago. Right? So we keep seeing
7:08:327 hours, 8 minutes, 32 secondshow useful tools like firecrol are. This is another comment on that same thing.
7:08:377 hours, 8 minutes, 37 secondsSo I made sure it knows that going forward and now it will not correct us anymore.
7:08:447 hours, 8 minutes, 44 secondsPerfect. And in here yes there is kind of a problem here. Um, it's what I told you in the beginning. We could
7:08:517 hours, 8 minutes, 51 secondstechnically create a separate files, folders, and binary table, but I just found it to be at least for a tutorial
7:09:007 hours, 9 minutesvery simple to keep it all together later. If you want to, you can keep all three separated because yes, there is
7:09:097 hours, 9 minutes, 9 secondstechnically a scenario here where we could have a storage ID, content, and a type of folder, which is something that
7:09:187 hours, 9 minutes, 18 secondsshouldn't exist. A folder cannot have content, and it cannot have storage ID.
7:09:227 hours, 9 minutes, 22 secondsA file cannot have both content and storage ID. Basically, it's telling us that we are not enforcing this at all.
7:09:307 hours, 9 minutes, 30 secondsSo right now the only thing that's preventing this from not breaking is the fact that we know what's supposed to exist and what isn't. But yeah, we could
7:09:397 hours, 9 minutes, 39 secondseither consider uh making strict checks in our create file and create folder so that storage can under no circumstances
7:09:487 hours, 9 minutes, 48 secondsbe added uh or we could look into some schema level enforcement in convex. But right now I think we are completely okay
7:09:567 hours, 9 minutes, 56 secondsgoing uh this way further. But I'm still very happy that Code Rabbit commented on this because yes, there is kind of, you
7:10:057 hours, 10 minutes, 5 secondsknow, some odd behavior here. I mean, it's not odd behavior. It's the fact that nothing is preventing us from creating a state which shouldn't exist.
7:10:147 hours, 10 minutes, 14 secondsThat's what Code Rabbit is commenting on. So, good comment here. Yes, in here it's commenting about the fact that we
7:10:227 hours, 10 minutes, 22 secondsmodified our layout.tsx tsx project ID type from string to ID layouts. In fact, it's not telling us that we shouldn't
7:10:307 hours, 10 minutes, 30 secondsuse ID projects. It knows it should be ID projects. But it is warning us that Nex.js route parameters are always a
7:10:397 hours, 10 minutes, 39 secondstype of string. We are only using this so we get rid of the type errors. So here is the suggestion
7:10:467 hours, 10 minutes, 46 secondsit gave me. Keep them as string and then cast it as an ID. The reason this might
7:10:547 hours, 10 minutes, 54 secondsbe a better solution is because you never know that Nex.js version might might update whereas if you define the
7:11:017 hours, 11 minutes, 1 secondwrong type in its params because these are Nex.js specific things, it might break the build. So I might actually
7:11:097 hours, 11 minutes, 9 secondslean towards doing this change because for long-term that made more sense. You can see it completely understands what we're doing. So this is a branded convex type that requires validation, right?
7:11:207 hours, 11 minutes, 20 secondsBut it's suggesting casting that rather than changing what is not true. Yes, Nex.js project ID is
7:11:307 hours, 11 minutes, 30 seconds100% a string. That's simply how the framework works. It's never going to be this. But technically in our case, we
7:11:397 hours, 11 minutes, 39 secondsknow it is. So we kind of using a hacky solution to fix our types. So perhaps we should do this in a proper way.
7:11:487 hours, 11 minutes, 48 secondsWe can even add a runtime validation if we if we really want to, right? But convex usually takes care of that. And
7:11:567 hours, 11 minutes, 56 secondsin here, you can see it's telling us to double check if size 5.5 actually exists. Uh, and I've told it that it
7:12:047 hours, 12 minutes, 4 secondsdoes. But you can see that even I, if you've probably noticed, I didn't use size 5.5 in my code. I used size uh 22
7:12:137 hours, 12 minutes, 13 secondspixels and then Tailwind extension CSS told me, hey, you can use size 5.5. So,
7:12:217 hours, 12 minutes, 21 secondsit's obviously a very new thing that just came out and I couldn't even find public documentation about it. But you can see I just said that to code rabbit
7:12:297 hours, 12 minutes, 29 secondsand it learned the same way I learned this chapter, right? the extension taught me and I just taught my AI reviewer here. And you can see that it
7:12:377 hours, 12 minutes, 37 secondsnow knows that and it's not going to mess with that anymore. In here, it suggests not using both default sizes
7:12:457 hours, 12 minutes, 45 secondsand preferred size for the a lotment paints. That's probably true. Yeah. Uh I'm going to take a look if we can remove one or the another or if it
7:12:547 hours, 12 minutes, 54 secondscauses any problems. I think as long as it doesn't cause any errors or problems, we're good to go. Uh awesome. Amazing.
7:13:017 hours, 13 minutes, 1 secondAmazing check by code rabbit here. So, we're going to merge this. And now we should have this branch visible right
7:13:097 hours, 13 minutes, 9 secondshere. Here it is. Let's go ahead and do get checkout main. Get pool origin main.
7:13:197 hours, 13 minutes, 19 secondsThere we go. I think that marks the end of the chapter. Let's make sure we are on the main branch right here. And
7:13:277 hours, 13 minutes, 27 secondsinside of here, I always like to confirm I've checked out number nine and merged it back to main. Amazing. So, we've
7:13:367 hours, 13 minutes, 36 secondsdesigned the file folder data model in convex. We built a recursive tree component. We've created collapsive folder behavior. We implemented file
7:13:457 hours, 13 minutes, 45 secondsicons. And we did not implement this, but we did implement create, rename, and
7:13:527 hours, 13 minutes, 52 secondsthe context menu. So, we actually did way more. And then in the next chapter, we're just going to have to implement this, which is way simpler than what we
7:14:017 hours, 14 minutes, 1 secondjust did. Amazing, amazing job. And see you in the next chapter.
Chapter 11: 10 Code Editor State
7:14:067 hours, 14 minutes, 6 secondsIn this chapter, we're going to implement the code editor as well as state management of our files. We're
7:14:137 hours, 14 minutes, 13 secondsgoing to do that by setting up Sushtand State management, installing and configuring code mirror 6, setting up
7:14:217 hours, 14 minutes, 21 secondsone dark theme configuration, building a tabbed file switcher component, and adding syntax highlighting for
7:14:307 hours, 14 minutes, 30 secondslanguages. So this is how that's going to look like. This is the finished project. In the previous chapter, we actually implemented the file explorer.
7:14:397 hours, 14 minutes, 39 secondsBut what we didn't implement is the logic of what file is selected and we didn't implement the ability to see the
7:14:477 hours, 14 minutes, 47 secondscontents of that file instead of a code editor which has the proper syntax highlighting for its file. So the first
7:14:567 hours, 14 minutes, 56 secondsthing we're going to do is we're going to implement the state management. As you can see, it has a very specific temporary state, right? So right now
7:15:057 hours, 15 minutes, 5 secondswhen I switch between different files you can see that it's temporary unless I doubleclick then it becomes permanent
7:15:147 hours, 15 minutes, 14 secondsand when I click on the next one that one becomes temporary instead of just opening a bunch of tabs. I found this uh
7:15:237 hours, 15 minutes, 23 secondsbehavior from the actual VS code. You can see that right now I have this file open create input but when I click on another one it doesn't open a new tab.
7:15:337 hours, 15 minutes, 33 secondsit just replaces the existing one until I doubleclick and then you can see it starts opening multiple tabs. So I
7:15:417 hours, 15 minutes, 41 secondsborrowed the behavior from the original editor because I think it's a very good implementation. So I want to bring it to
7:15:507 hours, 15 minutes, 50 secondsour editor as well. So without further ado, uh let's get started on that. So I'm going to go ahead and do npm rundev.
7:16:007 hours, 16 minutesAnd we're going to start by installing tushand. So let's go ahead and do mpm install tushand. I'm going to show you the version that I'm using immediately.
7:16:117 hours, 16 minutes, 11 secondsEven though very rarely have I heard of any breaking changes inside of Tsushan.
7:16:177 hours, 16 minutes, 17 secondsUh state management is kind of solved, you know. So let's go ahead and go
7:16:237 hours, 16 minutes, 23 secondsinside of the following I want to kind of prepare source features projects components file
7:16:337 hours, 16 minutes, 33 secondsexplorer tree. So this specific file the reason is because this file is almost finished besides a few things and those
7:16:437 hours, 16 minutes, 43 secondsfew things are let me find it here they are on click is empty on doubleclick is
7:16:497 hours, 16 minutes, 49 secondsalso empty to-do close tab right we have kind of this leftover things that we just left here right uh so that's what
7:16:587 hours, 16 minutes, 58 secondswe're going to be able to wrap up and forever finish this tree component we first have to implement the state
7:17:057 hours, 17 minutes, 5 secondsmanagement. So let's go ahead and do that. I'm going to go inside of source features projects and let's create a new
7:17:137 hours, 17 minutes, 13 secondsfolder called store and inside use editor-store.ts.
7:17:227 hours, 17 minutes, 22 secondsLet's import create from tushand let's import the id from convex generated data
7:17:307 hours, 17 minutes, 30 secondsmodel. Now let's create an interface called tab state. It's going to have an array of open tabs which are just a
7:17:387 hours, 17 minutes, 38 secondsbunch of ID files and active tab ID and preview tab ID which are the same type but optional.
7:17:477 hours, 17 minutes, 47 secondsNow let's go ahead and according to that interface create a default tab state and give it the proper interface empty array and null null as the initial values.
7:17:587 hours, 17 minutes, 58 secondsNow, let's go ahead and let's open interface editor store. Inside of here,
7:18:067 hours, 18 minutes, 6 secondsI want to start with tabs. So, tabs are going to be a map and we're going to give it a type first arguments id of project and the second one tab state.
7:18:177 hours, 18 minutes, 17 secondsThose are going to be the tabs. Then let's go ahead and let's open get uh let's create get tab state which accepts
7:18:257 hours, 18 minutes, 25 secondsthe project ID which is this type and simply returns tab state. Then let's go
7:18:327 hours, 18 minutes, 32 secondsahead and create open file. Open file is a function which accepts project ID file
7:18:407 hours, 18 minutes, 40 secondsID options in which we have one property pinned. That is the functionality I was talking to you about right. uh will it
7:18:497 hours, 18 minutes, 49 secondspersist or will it replace on next click? So we're just writing types for the editor store. Now after open file,
7:18:587 hours, 18 minutes, 58 secondslet's implement close tab which accepts a project ID, a file ID and a void.
7:19:077 hours, 19 minutes, 7 secondsThen let's go ahead and implement close all tabs which accepts project ID and a
7:19:137 hours, 19 minutes, 13 secondsvoid. So this will be uh per project, right? And the last one we have is set active tab which accepts a project ID
7:19:227 hours, 19 minutes, 22 secondsand a file ID and returns a void. Let me expand this even more so perhaps you can
7:19:277 hours, 19 minutes, 27 secondssee all of them in one line. Great. So now I'm going to remove the spaces between them. I just added them so it's
7:19:367 hours, 19 minutes, 36 secondseasier for you to look at. Now that we have the interface for the editor store, let's actually go ahead and develop
7:19:437 hours, 19 minutes, 43 secondsexport const use editor store. We're going to use the create method from sushand and let's give it an argument of
7:19:517 hours, 19 minutes, 51 secondseditor store the interface we've just created. Go ahead and execute it and then immediately execute again. And from
7:19:597 hours, 19 minutes, 59 secondshere open another parenthesis. So be mindful a lot of parenthesis happening here. and again open parenthesis and
7:20:077 hours, 20 minutes, 7 secondsimmediately return an object inside like this. And now in here, let's start defining things. So we're now going to
7:20:147 hours, 20 minutes, 14 secondshave a bunch of errors until we uh populate all of these functions and types we've added. So let's start with the tabs. That's going to be a new map.
7:20:247 hours, 20 minutes, 24 secondsThen let's go ahead and let's implement get tab state. The second one get tab
7:20:327 hours, 20 minutes, 32 secondsstate will accept a project ID and it will return get which is this method
7:20:387 hours, 20 minutes, 38 secondsright here dot tabs.get get which is using a get from the map JavaScript OB
7:20:477 hours, 20 minutes, 47 secondsJavaScript what should I use entity I guess that's the word uh or fallbacks to default tab state we're using map
7:20:567 hours, 20 minutes, 56 secondsbecause it doesn't allow duplicates so it kind of uh does a lot of work for us in making sure no duplicate tabs are
7:21:037 hours, 21 minutes, 3 secondsopen great so that is get tab state now let's implement a complex one open file
7:21:107 hours, 21 minutes, 10 secondsit will accept accept a project ID, file ID, and last but not least, the options
7:21:187 hours, 21 minutes, 18 secondsin which we have the pinned property. So let's go ahead and start defining the things we need. First, let's get all the
7:21:267 hours, 21 minutes, 26 secondstabs using new map get tabs. Make sure to execute the get. Then let's get the
7:21:347 hours, 21 minutes, 34 secondscurrent state using tabs.get project ID. So we are getting all the currently opened tabs for this project
7:21:427 hours, 21 minutes, 42 secondsID or we are defaulting to well default tab state from the state we can extract open tabs
7:21:507 hours, 21 minutes, 50 secondsand preview tab ID and now we can check if this current file is already open do
7:21:577 hours, 21 minutes, 57 secondsopen tabs include the file ID we are attempting to open now let's have some
7:22:037 hours, 22 minutes, 3 secondsscenarios so first scenario opening as preview view. So that is this when I
7:22:107 hours, 22 minutes, 10 secondsclick on something you can see how it opens it's not persistent because if I
7:22:177 hours, 22 minutes, 17 secondsclick something else it changes right so we call that preview not pinned right
7:22:247 hours, 22 minutes, 24 secondsthat is case one so let's go ahead and do an if jack if it is not opened and
7:22:337 hours, 22 minutes, 33 secondswe are not pinning it so if not open and not pinned. Let's go ahead and
7:22:417 hours, 22 minutes, 41 secondsreinitialize new tabs with this new preview tab. So, preview tab ID which we've destructured from the state.
7:22:517 hours, 22 minutes, 51 secondsLet's check if uh we have it. If we do call open tabs dom find the ID
7:23:017 hours, 23 minutes, 1 secondopen parenthesis and check if ID is equal to preview tab ID then use the file ID we just passed
7:23:107 hours, 23 minutes, 10 secondshere. Otherwise just return the ID you found.
7:23:167 hours, 23 minutes, 16 secondsAnd the alternative is to simply add to the list of open tabs a new file ID. All right. Now, here's the thing.
7:23:287 hours, 23 minutes, 28 secondsIt's very annoying to look at these errors here. So, I'm thinking if I remove this, does it make it easier to look at? Oh, kind of, but not too much.
7:23:387 hours, 23 minutes, 38 secondsUnfortunately, we're going to have to go through this with a bunch of errors and then hopefully we won't have any at the end. It's just hard to define like did
7:23:477 hours, 23 minutes, 47 secondswe make a mistake in the syntax or is it just a type error but let's just continue for now. All right. So we've just successfully defined new tabs here.
7:23:567 hours, 23 minutes, 56 secondsThe only problem is we are not using it. So let's call tabs dot set project ID
7:24:057 hours, 24 minutes, 5 secondsopen tabs new tabs active tab ID file ID preview tab ID
7:24:157 hours, 24 minutes, 15 secondsfile ID. So an active tab is the one the user is currently seeing in the code editor. The preview tab ID is referring
7:24:227 hours, 24 minutes, 22 secondsto the top bar here. So a file can be both active but still in the preview phase. For example, like this. It's
7:24:317 hours, 24 minutes, 31 secondsactive, but it's in preview, right? You can see it's italic.
7:24:367 hours, 24 minutes, 36 secondsSo that's the first scenario. And let's call set tabs and do an early return. So
7:24:457 hours, 24 minutes, 45 secondsthat is case one finished. Make sure you've closed the if clause.
7:24:507 hours, 24 minutes, 50 secondsNow let's do a second scenario which is much simpler. Case two, opening a tab
7:24:587 hours, 24 minutes, 58 secondsimmediately as pinned. In that case, all we have to do is just open a new tab. So
7:25:047 hours, 25 minutes, 4 secondsif the tab is not open, but we called it with a purpose to be pinned, which could be initiated through a doubleclick. For
7:25:137 hours, 25 minutes, 13 secondsexample, let's simply call tabs set for this project ID. Spread the state. call
7:25:237 hours, 25 minutes, 23 secondsopen tabs spread open tabs and simply add file ID here and set the file tab ID
7:25:327 hours, 25 minutes, 32 secondsmy apologies the active tab ID to the file ID then call set
7:25:397 hours, 25 minutes, 39 secondsput in the new tabs and do an early return I think that maybe we can just every now and then remove the editor
7:25:487 hours, 25 minutes, 48 secondsstore just to confirm you know you don't have any big syntax X errors. Okay, now that I look at it, it's definitely
7:25:557 hours, 25 minutes, 55 secondseasier to look at without giving it the type. Like, okay, this we're going to see if this actually works later or not.
7:26:047 hours, 26 minutes, 4 secondsYou should have all of these errors. All of this is perfectly fine. It's mostly just type errors, right? But it's way easier to look at, especially when
7:26:127 hours, 26 minutes, 12 secondsbuilding long uh ones like this. So, that was case two. Now, let's go ahead and do case three, which isn't going to
7:26:197 hours, 26 minutes, 19 secondsbe complicated. Case three, the file is already open, but we attempted to open it again and pin if doubleclicked.
7:26:307 hours, 26 minutes, 30 secondsSo, const should we pin it? If we specifically gave it an option to pin or if preview tab ID is equal to file ID.
7:26:417 hours, 26 minutes, 41 secondsSo, if we attempt to open a previewed file once more, obviously we want it to
7:26:477 hours, 26 minutes, 47 secondsbe pinned. So tabs dot set project ID
7:26:547 hours, 26 minutes, 54 secondsstate active tab ID set to file ID preview tab ID.
7:27:037 hours, 27 minutes, 3 secondsLet's go ahead and do should we pin it?
7:27:057 hours, 27 minutes, 5 secondsIf we should null otherwise keep it as preview tab ID and go ahead and set
7:27:137 hours, 27 minutes, 13 secondstabs. No need to do an early return because this is the last if clause. Keep in mind if this is like super
7:27:217 hours, 27 minutes, 21 secondscomplicated that's kind of okay. It's very hard to imagine how this actually works but once we connect it to the UI
7:27:287 hours, 27 minutes, 28 secondsit will be easier. Uh you can see that even I myself made these comments so it's easier to explain what we're doing
7:27:357 hours, 27 minutes, 35 secondshere. So perfectly fine if you feel confused here. It's a big chunk of logic and it will make more sense once we have the UI to go with it. So yes, don't
7:27:457 hours, 27 minutes, 45 secondsworry. Let's go ahead and continue developing uh our methods here. So I'm going to add close tab method now which
7:27:527 hours, 27 minutes, 52 secondswill accept a project ID and a file a file ID right. So again uh let's start
7:28:017 hours, 28 minutes, 1 secondfirst we get the tabs using new map get tabs from that let's go ahead and get
7:28:107 hours, 28 minutes, 10 secondsthe state from the current project ID or fallback to the default state. We
7:28:177 hours, 28 minutes, 17 secondsalready know that from the state we can extract open tabs active tab ID and preview tab ID. And now let's just wrap
7:28:277 hours, 28 minutes, 27 secondsit up by adding a tab index from the open tabs. So we are attempting to find if the file ID is one of the open tabs
7:28:367 hours, 28 minutes, 36 secondsby using index off and we are going to use it later. So the first thing we can check if the tab index is minus one it
7:28:467 hours, 28 minutes, 46 secondsmeans it's already closed. We have nothing to close. So let's just do an early return. Now let's go ahead and prepare how the new tabs are going to
7:28:557 hours, 28 minutes, 55 secondslook like. So the new tabs will be open tabs.filter and basically just filter out the file
7:29:027 hours, 29 minutes, 2 secondsID that we have passed. So make sure you use the opposite logic here. Right now let's go ahead and let's define the
7:29:107 hours, 29 minutes, 10 secondsfollowing new active tab ID. That's basically the complicated part here.
7:29:167 hours, 29 minutes, 16 secondsOnce we close a tab, what should become the next active tab? We could just fall back to a blank page. But why should we?
7:29:257 hours, 29 minutes, 25 secondsWe can implement a very simple uh kind of decide decision of what should be the next tab. So if an active tab ID is
7:29:357 hours, 29 minutes, 35 secondsequal to the file we have just closed, we have to do something. So first things
7:29:427 hours, 29 minutes, 42 secondslet's check are the new tabs meaning once we removed this file are there any
7:29:487 hours, 29 minutes, 48 secondstabs left over because if there aren't there's nothing we can do. Let's just go ahead and pass a new active tab ID to
7:29:567 hours, 29 minutes, 56 secondsnull. Alternatively if we are able to find some other tabs.
7:30:047 hours, 30 minutes, 4 secondsSo else if tab index is greater or equal than the new tabs.length,
7:30:127 hours, 30 minutes, 12 secondswe are basically doing a logic. Should we uh make the next active tab the one that was opened before this one we just
7:30:217 hours, 30 minutes, 21 secondsclosed or after it? So for this scenario, let's set the new active tab
7:30:287 hours, 30 minutes, 28 secondsto be new tabs. New tabs.length minus one. basically the last one we opened.
7:30:357 hours, 30 minutes, 35 secondsElse, let's just go ahead and fall back to new active tab ID and then to whatever tab index we just found. What
7:30:447 hours, 30 minutes, 44 secondsis why can we do that? Well, because this tab index is no longer this closed tab. So, it's just the last one left, right?
7:30:537 hours, 30 minutes, 53 secondsOnce we do that, we can call tabs set project ID open tabs new tabs
7:31:037 hours, 31 minutes, 3 secondsactive tab ID new active tab ID preview
7:31:097 hours, 31 minutes, 9 secondstab ID preview tab ID equals to
7:31:167 hours, 31 minutes, 16 secondswhat we passed file ID null otherwise preview tab ID and finally Finally, let's set those tabs.
7:31:267 hours, 31 minutes, 26 secondsThere we go.
7:31:287 hours, 31 minutes, 28 secondsAnd now we have a few very simple methods. So the first one is to close all tabs in a project. We pass in the
7:31:377 hours, 31 minutes, 37 secondsproject ID. We call the tabs using new map and inside we execute get and we
7:31:447 hours, 31 minutes, 44 secondsaccess the tabs property and we call tabs set project ID simply defaulted to
7:31:527 hours, 31 minutes, 52 secondsan empty array with no open tabs or anything like that and call a setter on
7:31:597 hours, 31 minutes, 59 secondsthat. And last one, set active tab for a project for this file.
7:32:087 hours, 32 minutes, 8 secondsAs always, let's go ahead and copy how we uh get the tabs like this.
7:32:157 hours, 32 minutes, 15 secondsConstate tabs.get for this project or default tab state if this project has no open tabs.
7:32:297 hours, 32 minutes, 29 secondscall tabs set and add to this project ID whatever is the current state and simply
7:32:377 hours, 32 minutes, 37 secondsmodify the current active tab ID to be file ID
7:32:447 hours, 32 minutes, 44 secondsand set tabs that's it now ready to give
7:32:507 hours, 32 minutes, 50 secondsthis a proper type so go to use editor store and give it the editor store And
7:32:587 hours, 32 minutes, 58 secondsif you've done it correctly, you shouldn't have any errors at all. So if you do have some errors, it's most likely a typo, right? Because for
7:33:087 hours, 33 minutes, 8 secondsexample, in things like this, if I do active tab ID 2, you can see it gives me
7:33:147 hours, 33 minutes, 14 secondsan error. But if I don't have editor store here, I don't think it's going to give me an error. Yeah, you can see how it's completely allowing me to do that.
7:33:247 hours, 33 minutes, 24 secondsSo if you have some typo here uh these adding editor store will help you do that. So yeah you should definitely have no errors once you add the editor store.
7:33:387 hours, 33 minutes, 38 secondsThe editor store will ensure that you have complete type safety here. I am slowly going to go through the entire
7:33:457 hours, 33 minutes, 45 secondsfile once again. if you want to pause and if you want to check and compare of course you can access the source code
7:33:547 hours, 33 minutes, 54 secondstoo but still if you want to do it this way I'm just going over everything once again so you can pause the screen and
7:34:027 hours, 34 minutes, 2 secondssee great now let's go inside of the hooks and let's create use editor tts
7:34:107 hours, 34 minutes, 10 secondsand inside of use editor let's go ahead and export const use editor project ID
7:34:187 hours, 34 minutes, 18 secondsa type of ID projects and let's go ahead and add some other imports we are going to need use
7:34:277 hours, 34 minutes, 27 secondscallback from react and we are going to need use editor store from store use
7:34:367 hours, 34 minutes, 36 secondseditor store now I'm going to define the store here store from use editor store.
7:34:447 hours, 34 minutes, 44 secondsThen I'm going to grab the tab state for my specific project ID. So tab state,
7:34:517 hours, 34 minutes, 51 secondsuse editor store. We get the entire state and then we call get tab state but just for this one project that I
7:35:007 hours, 35 minutescurrently have opened. Right? This is the logic.
7:35:067 hours, 35 minutes, 6 secondsOnce I have the tab state, I can start developing things like open file. We're going to call use call back
7:35:157 hours, 35 minutes, 15 secondsso we don't have any reactivity problems here. So what are the arguments we're going to pass? Well, the first argument
7:35:237 hours, 35 minutes, 23 secondsis going to be the file ID and the second argument will be options. Should we pin this file or not?
7:35:337 hours, 35 minutes, 33 secondsAnd then the logic in here is actually very easy.
7:35:387 hours, 35 minutes, 38 secondsstore, open file, project ID, file ID, and options. And the dependency array should have store and project ID. So,
7:35:487 hours, 35 minutes, 48 secondsbecause we did all the complex logic inside of the actual store, we don't have to do it here. In here, we just make sure that we can easily uh call
7:35:567 hours, 35 minutes, 56 secondsthis hook use editor and pass in the project ID and we don't have to worry about passing project ID in every single
7:36:057 hours, 36 minutes, 5 secondsuh store function because right now take a look at all of these functions. They all accept project ID. That's very
7:36:127 hours, 36 minutes, 12 secondsannoying, right? So, we are creating an abstraction over that so that we kind of have a easier and better developer experience when calling these functions.
7:36:227 hours, 36 minutes, 22 secondsNow, same thing is true for close tab.
7:36:247 hours, 36 minutes, 24 secondsFor example, close tab use callback which accepts a file ID and simply calls store close tab passes in the project ID
7:36:337 hours, 36 minutes, 33 secondsand the file ID. So, the exact same thing as here, right?
7:36:387 hours, 36 minutes, 38 secondsI I try to like write it in the same way, but I think you get the idea, right?
7:36:457 hours, 36 minutes, 45 secondsThis first one is just the parameters of the function, right? Okay. So that was
7:36:527 hours, 36 minutes, 52 secondsclose tab. Now let's go ahead and let's do close all tabs again. Use callback.
7:36:597 hours, 36 minutes, 59 secondsThis time no props at all. Just store close all tabs for this project. And then let's go ahead and do the last one.
7:37:107 hours, 37 minutes, 10 secondsSet active tab. Again use callback accepts a file ID calls store set active
7:37:167 hours, 37 minutes, 16 secondstab. Project ID file ID. and these two in the dependency array. Now let's go ahead and let's return all the things
7:37:257 hours, 37 minutes, 25 secondswe're going to need. So we are going to map uh tab stateopen tabs to just open tabs. Same thing with active tab id and
7:37:347 hours, 37 minutes, 34 secondspreview tab id and then we have open file close tab close all tabs and finally set active tab. Great. So a very
7:37:427 hours, 37 minutes, 42 secondsuseful abstraction over our sushan store. So what I want to do now is go inside of features and actually create a
7:37:487 hours, 37 minutes, 48 secondsnew folder called editor and I want to create store here and I want to create
7:37:557 hours, 37 minutes, 55 secondshooks here because what we've just done doesn't belong in the projects. Right?
7:38:027 hours, 38 minutes, 2 secondsSo I'm going to uh move use editor to our editor feature hooks. I'm going to
7:38:097 hours, 38 minutes, 9 secondsmove it there. I'm going to update the imports even though it doesn't matter because I'm now going to move use editor
7:38:187 hours, 38 minutes, 18 secondsstore to our features editor store. I'm going to move it there and I'm going to
7:38:247 hours, 38 minutes, 24 secondsupdate the imports. So let's see inside of our projects feature we shouldn't have a store folder at all. We can
7:38:337 hours, 38 minutes, 33 secondsdelete it. The hooks should only have these two. You can now close the projects folder. But your new editor
7:38:407 hours, 38 minutes, 40 secondsfeature should now have use editor which calls use editor store from dot dot/store use editor store and you should find use editor store right here.
7:38:527 hours, 38 minutes, 52 secondsAnd maybe the only thing that you have to fix is this import if you even have to. I don't think you do. I think it's exactly the same level as we had it in
7:39:007 hours, 39 minutesprojects. Great. So that's one thing I wanted us to do. So now before we can actually implement the logic so that
7:39:087 hours, 39 minutes, 8 secondswhen you click on a file it opens it. Um well actually I think we can do it. Uh
7:39:167 hours, 39 minutes, 16 secondslet me go ahead and do file one.ts and let's do file oops this is a folder file 2.tsx.
7:39:267 hours, 39 minutes, 26 secondsSo right now you know clicking on them doesn't really do much. So I think we
7:39:347 hours, 39 minutes, 34 secondscan improve that now by going inside of features projects components file explorer
7:39:427 hours, 39 minutes, 42 secondstree right here. And now what I want to do is I want to add the logic to well you know open some files right.
7:39:537 hours, 39 minutes, 53 secondsSo after we do these instances like create folder and such things I want to
7:39:597 hours, 39 minutes, 59 secondscall use editor. So not use editor store specifically
7:40:067 hours, 40 minutes, 6 secondsuse editor from features editor hooks use editor our abstraction and then
7:40:147 hours, 40 minutes, 14 secondswe're going to get all of those functions from our tushan store but for this project ID so we don't have to pass the project ID a million times. So in
7:40:237 hours, 40 minutes, 23 secondshere I can extract open file close tab and active tab ID. I can now do all of
7:40:317 hours, 40 minutes, 31 secondsthose. So I'm going to start with open file. Let's go ahead down here.
7:40:387 hours, 40 minutes, 38 secondsIf item type is equal to file and let's go ahead and do const is
7:40:457 hours, 40 minutes, 45 secondsactive if active tab ID is equal to item ID because we now have access to the active tab ID, right?
7:40:577 hours, 40 minutes, 57 secondsAnd let's scroll down here to the tree item wrapper. In the on click add open
7:41:047 hours, 41 minutes, 4 secondsfile pass in item ID and pinned to be false. Meaning this is
7:41:117 hours, 41 minutes, 11 secondsjust a preview. And then in the on doubleclick we do the exact same method but with pinned set to true. On delete.
7:41:227 hours, 41 minutes, 22 secondsLet's go ahead and delete this to-do one. close the tab. So if this tab happened to be opened by at the time we
7:41:307 hours, 41 minutes, 30 secondsare deleting it through the file explorer, let's close it, right? No need for it to be open.
7:41:377 hours, 41 minutes, 37 secondsGreat. And I actually think let's see is there any other place where we could close tab? So we just did it here.
7:41:497 hours, 41 minutes, 49 secondsLet me go ahead down here. Does it make any sense to do it here?
7:41:557 hours, 41 minutes, 55 secondsNo, because this is a folder. I wrote to-do close tab here. But this is a folder.
7:42:027 hours, 42 minutes, 2 secondsI don't think we should do that. I think delete [clears throat] file is sufficient here. And I think that
7:42:097 hours, 42 minutes, 9 secondsfinally uh oh I I'm not using is active anywhere. Okay. So that's one thing uh I have forgot. And again only a file can
7:42:177 hours, 42 minutes, 17 secondsbe active because what does is active represent? It represents whether we should open a file in an explorer or not
7:42:257 hours, 42 minutes, 25 secondsor or not. There we go. Is active is active. And I think that's it. Great.
7:42:327 hours, 42 minutes, 32 secondsSo, should we see any differences? Well, I think we should. Let's go ahead and see. So, when I click on this file, I
7:42:417 hours, 42 minutes, 41 secondsdon't think you can see, but there's a very subtle shadow like a background which kind of indicates is open. So
7:42:497 hours, 42 minutes, 49 secondsclick on it and then click somewhere else. You can see how it stays selected, right? Even if you kind of click in
7:42:577 hours, 42 minutes, 57 secondsbetween preview and code, it stays selected. So this is the only thing we can actually see now because that's the only UI we have built. Uh what we have
7:43:057 hours, 43 minutes, 5 secondsto do now is we have to build the tabs, right? So let's go ahead and do that. So in order to build the tabs, there's
7:43:137 hours, 43 minutes, 13 secondsactually one more files convex function that we have to implement and it's used for the breadcrumbs. Uh let me actually show you how it's going to look like.
7:43:217 hours, 43 minutes, 21 secondsRight? So when I click on globe for example, see this source components globe jsx or source index css. Right? No
7:43:297 hours, 43 minutes, 29 secondsmatter how deep I go inside it, it can always find its way to its root file. In order to do that, we need to traverse up
7:43:377 hours, 43 minutes, 37 secondsthe parent chain. So I'm going to go inside of convex files.ts and we have a bunch of uh things here.
7:43:467 hours, 43 minutes, 46 secondsSo I will copy uh get folder contents because it's very similar.
7:43:527 hours, 43 minutes, 52 secondsLet's copy it and let's just paste it here. Let me expand this as much as I can. So I'm going to go to this copied
7:43:597 hours, 43 minutes, 59 secondsone and I will rename it to get file path. And it will only accept one thing
7:44:047 hours, 44 minutes, 4 secondsand one thing only. id v do id files. So we start with the identity as usual then
7:44:147 hours, 44 minutes, 14 secondswe go ahead and we get the file if the file does not exist with throw and then
7:44:217 hours, 44 minutes, 21 secondsinstead of arguments project ID we use that file project ID to confirm do we even have access to get the file path
7:44:317 hours, 44 minutes, 31 secondsright let me explain actually what this is in fact I made a little comment you don't have to copy the whole comment but
7:44:397 hours, 44 minutes, 39 secondsI think it will help you understand. So this function builds the full path to a file by traversing up the parent parent chain. The input is a simple file ID.
7:44:527 hours, 44 minutes, 52 secondsFor example, id of button.dsx and the output will be an array of answer answers
7:44:597 hours, 44 minutes, 59 secondsfrom root to file. So for example, if I have a folder source components button.tsx, tsx I will get back an array
7:45:087 hours, 45 minutes, 8 secondswith the first one being source the second one being components and the third one being my file and then in the
7:45:147 hours, 45 minutes, 14 secondsbreadcrumbs I can use it to display this is there is this the most optimized
7:45:217 hours, 45 minutes, 21 secondsthing to do uh it can probably be better why am I saying that um another solution
7:45:297 hours, 45 minutes, 29 secondsof doing this would be to maintain the path right so I can have source
7:45:357 hours, 45 minutes, 35 secondsyou know, components button. DSX. This could be cool. But imagine if I want to
7:45:427 hours, 45 minutes, 42 secondsrename the folder source. What do I do in that case? I would have to for one
7:45:497 hours, 45 minutes, 49 secondssimple folder rename, I would potentially have to update thousands of
7:45:557 hours, 45 minutes, 55 secondsfiles which all have this path cached and stored. So I guess the best solution
7:46:037 hours, 46 minutes, 3 secondsis some kind of hybrid or some kind of background job that will take care of updating the path for all files. So in
7:46:127 hours, 46 minutes, 12 secondscase you kind of shook your head and said, "Is this really the best thing we can do?" Probably not. But at the
7:46:207 hours, 46 minutes, 20 secondscurrent state of this project, I think it's more worth it doing this than
7:46:267 hours, 46 minutes, 26 secondsmodifying all of our delete and update simple renames to be a super expensive query because this one isn't that
7:46:357 hours, 46 minutes, 35 secondsexpensive really, right? And it won't really appear anywhere besides when you click and it will it will be cached on top of that. So I think it's an okay
7:46:457 hours, 46 minutes, 45 secondsdeal. later. You are welcome to of course modify to whatever you think is best. So I'm now going to remove
7:46:537 hours, 46 minutes, 53 secondseverything here. I just want the the checks, right? And I'm going to start by defining constant path which is going to
7:47:017 hours, 47 minutes, 1 secondbe an empty array. But in the array each item will be an object which has underscore ID and name.
7:47:107 hours, 47 minutes, 10 secondsAnd then let's go ahead and start with the current ID. The current ID is a type of ID files
7:47:187 hours, 47 minutes, 18 secondsor undefined and we start with arguments ID.
7:47:247 hours, 47 minutes, 24 secondsWhile we have the current ID, let's go ahead and do const file open parenthesis
7:47:347 hours, 47 minutes, 34 secondsawait context.database.get Get files pass in the current ID as document files or undefined.
7:47:497 hours, 47 minutes, 49 secondsLet's import document from generated data model here.
7:47:567 hours, 47 minutes, 56 secondsIf there is no file, break the while. Otherwise, path.unshift.
7:48:047 hours, 48 minutes, 4 secondsSo add to the array the following object file ID
7:48:117 hours, 48 minutes, 11 secondsname file.name and then the current ID simply becomes
7:48:177 hours, 48 minutes, 17 secondsthis files parent ID until there is no current ID meaning we found the root one
7:48:257 hours, 48 minutes, 25 secondswhich has parent ID as undefined meaning that will break the while method. So, a pretty brute force way to do it, but it
7:48:337 hours, 48 minutes, 33 secondsgets the job done. I've explained the complexity and the alternative uh moments before, right? We could kind of
7:48:407 hours, 48 minutes, 40 secondsmaintain path, but the problem is a very expensive rename queries. So, it's kind of a compromise. Uh again, you're welcome to improve this of course at the
7:48:497 hours, 48 minutes, 49 secondsend of the project as a personal challenge.
7:48:537 hours, 48 minutes, 53 secondsAwesome. So, let's now go ahead and start uh building the UI.
7:49:007 hours, 49 minutesSo we have to go back to our source features projects components and let's
7:49:077 hours, 49 minutes, 7 secondsfind the project ID view. We have added the file explorer but we never added the
7:49:147 hours, 49 minutes, 14 secondseditor view. So now we're going to add the editor view and it's going to have the exact same prop as the file
7:49:227 hours, 49 minutes, 22 secondsexplorer. So obviously we are getting errors. And now let's go inside of editor new file components and let's go ahead and do editor- view.tsx.
7:49:367 hours, 49 minutes, 36 secondsNow inside of this editor view, let's export const editor view like this. Uh let's do a super simple
7:49:447 hours, 49 minutes, 44 secondstype here. Project id project ID which is a type of id like so. And in here,
7:49:527 hours, 49 minutes, 52 secondslet's return a div class name heightful flex flex column div.
7:50:037 hours, 50 minutes, 3 secondsThe div will have a class name flex items center. And finally, top
7:50:107 hours, 50 minutes, 10 secondsnavigation component inside. And inside of here, we just pass in the project ID.
7:50:187 hours, 50 minutes, 18 secondsGreat. So we now have top navigation.
7:50:217 hours, 50 minutes, 21 secondsBefore we start creating it, let's import the existing editor view from features editor
7:50:287 hours, 50 minutes, 28 secondscomponents editor view. But we didn't do much because now we have an error here, of course. So I'm going to go inside of
7:50:357 hours, 50 minutes, 35 secondseditor components, new file, and I'm going to call this top navigation.tsx.
7:50:437 hours, 50 minutes, 43 secondsLet's export contop navigation.
7:50:477 hours, 50 minutes, 47 secondsAnd let's go ahead and return a scroll area from components UI scroll area. And
7:50:537 hours, 50 minutes, 53 secondslet's create a nav element. This nav element will have a background color of
7:51:007 hours, 51 minutessidebar flex items center height of 35 pixels or let's see
7:51:077 hours, 51 minutes, 7 secondsuh height 8.75. 8.75 border bottom. And I believe that's it.
7:51:167 hours, 51 minutes, 16 secondsAnd let's give this one a class name of flex one. And then in here, I'm going to
7:51:247 hours, 51 minutes, 24 secondsextract the project ID and just give it the exact same prop scenario as our previous ones. So, let me go ahead and
7:51:327 hours, 51 minutes, 32 secondscollapse this in case you can't understand what it is. I feel like this might be easier. Now that we have the
7:51:407 hours, 51 minutes, 40 secondsskeleton of top navigation, let's go inside of editor view. Let's import top navigation right here. And this should
7:51:477 hours, 51 minutes, 47 secondsbe project ID. There we go. And we shouldn't see much difference besides this. There is now this black line here.
7:51:567 hours, 51 minutes, 56 secondsAnd you can see what it's going to become. It will become the tab, right?
7:52:007 hours, 52 minutesBut right now, just a tab, just a line should be rendered, right? Uh, great. We
7:52:067 hours, 52 minutes, 6 secondsnow have this. Now, what I'm going to do is I'm going to get all of my open tabs
7:52:167 hours, 52 minutes, 16 secondsfor this project using my use editor hook and by passing in the project ID.
7:52:257 hours, 52 minutes, 25 secondsAnd now that I have my open uh oh, my apologies, not here. So, sorry.
7:52:327 hours, 52 minutes, 32 secondsInside of the top navigation, there we go. Here, let's do it again. So inside of top navigation, I'm going to get all
7:52:387 hours, 52 minutes, 38 secondsof the open tabs for this project and import use editor from hooks use
7:52:467 hours, 52 minutes, 46 secondseditor, not the store one, the hooks one, the abstraction. Right? And then
7:52:527 hours, 52 minutes, 52 secondsinside of here I can do open tabs do map file ID
7:53:017 hours, 53 minutes, 1 secondand then index and I can return back a tab component
7:53:087 hours, 53 minutes, 8 secondsand each tab component will have the following props key which is a file ID file ID is first which is a very simple
7:53:177 hours, 53 minutes, 17 secondsindex logic and the project ID and Let's also make sure to add inside of this scroll area scroll bar component from
7:53:267 hours, 53 minutes, 26 secondscomponents UI scroll area and give it an orientation of horizontal.
7:53:337 hours, 53 minutes, 33 secondsGreat. Now it's time for us to develop the tab component. I'm going to do that here. const tab.
7:53:417 hours, 53 minutes, 41 secondsSo first things first, what props will this accept? Well, we defined them below, but let's do it here. File ID
7:53:507 hours, 53 minutes, 50 secondswhich is an ID of files is first which is a boolean and project ID which is an ID of projects.
7:53:587 hours, 53 minutes, 58 secondsFile ID is first and project ID. Great.
7:54:047 hours, 54 minutes, 4 secondsNow let's go ahead and just return something so we don't have any errors.
7:54:087 hours, 54 minutes, 8 secondsGreat. And in here first thing I'm going to do is I'm going to attempt to load the file. So use file. And I can see
7:54:167 hours, 54 minutes, 16 secondssince I don't have um autocomplete here, we most likely didn't implement the hooks for use files. So
7:54:267 hours, 54 minutes, 26 secondslet's quickly go inside of our projects hooks use files. Okay, so I have a lot
7:54:347 hours, 54 minutes, 34 secondsof them, but a lot of them are missing too. So let's see. Export const use file
7:54:417 hours, 54 minutes, 41 secondsaccepts file ID to be an ID of files or null
7:54:497 hours, 54 minutes, 49 secondsand it will return use query API files and we have the function great get file
7:54:567 hours, 54 minutes, 56 secondsand if we have file ID we pass that as the options otherwise we skip this query.
7:55:057 hours, 55 minutes, 5 secondsSo now seems like that is causing a problem. Oh, it's file ID
7:55:127 hours, 55 minutes, 12 secondsnot file. Okay. So that was use file and now we need to use our newly created one
7:55:217 hours, 55 minutes, 21 secondsfile path. So this is the new hook you need to add use file path which accepts the exact same thing and it returns use
7:55:307 hours, 55 minutes, 30 secondsquery API files get file path. If it has a file ID, it will pass it along.
7:55:377 hours, 55 minutes, 37 secondsOtherwise, it's going to skip this query. Confirm you have get file path and confirm you have get file. I can see
7:55:457 hours, 55 minutes, 45 secondswe implemented this in the ninth chapter file explorer. So, it should be here as
7:55:527 hours, 55 minutes, 52 secondswell. If it isn't, here's [snorts] a very easy function for you to write. So, it's actually the simplest of out of all
7:55:597 hours, 55 minutes, 59 secondsof these. Okay. Now that we have this, let's call use file from features
7:56:067 hours, 56 minutes, 6 secondsprojects hooks use file. So we just get the one and we pass in the file ID.
7:56:147 hours, 56 minutes, 14 secondsGreat. Now let's call use editor. So basically use editor from hooks use
7:56:247 hours, 56 minutes, 24 secondseditor the one from our editor feature basically in the same folder here.
7:56:307 hours, 56 minutes, 30 secondsRight? I just want to make sure you're not accidentally importing this one. Make sure you are importing that one.
7:56:367 hours, 56 minutes, 36 secondsSo, use editor accepts project ID. And in return, we get active tab ID, preview
7:56:447 hours, 56 minutes, 44 secondstab ID, set active tab, open file, and close tab. All of those things. So now,
7:56:537 hours, 56 minutes, 53 secondslet's go ahead and add some constants here which are going to help us style this. Is active. If active tab ID is
7:57:017 hours, 57 minutes, 1 secondequal to file ID is preview. If preview tab id is file ID. File name did we load
7:57:087 hours, 57 minutes, 8 secondsfile.name. If not loading now let's go ahead and let's give this div right here
7:57:147 hours, 57 minutes, 14 secondsfor the tab some attributes on click set active tab. On double click we just pin
7:57:227 hours, 57 minutes, 22 secondsthe file which is already open. So I believe if uh let me try and find so
7:57:297 hours, 57 minutes, 29 secondsopen file open file open file again open file let's find it this would
7:57:377 hours, 57 minutes, 37 secondsbe scenario two no case three file is already open just activated and pin if
7:57:477 hours, 57 minutes, 47 secondsdoubleclicked. So that is this scenario here. When we open a file which is inside of our tabs, it means it's opened
7:57:567 hours, 57 minutes, 56 secondsbut perhaps it's not pinned. And now in here we have to add a class name. So let's add a class name
7:58:047 hours, 58 minutes, 4 secondsCN util. Make sure you've added the import.
7:58:097 hours, 58 minutes, 9 secondsNow inside of here, let's start adding some classes. It's going to be uh some of them. So flex item center gap two.
7:58:197 hours, 58 minutes, 19 secondsThen we're going to add some height and some padding here. So height 35 or what does it say? 8.75.
7:58:287 hours, 58 minutes, 28 secondsPL and uh padding right functions.
7:58:337 hours, 58 minutes, 33 secondsThen let's add cursor pointer text muted foreground group and border Y.
7:58:417 hours, 58 minutes, 41 secondsThen let's go ahead and let's add border X and border transparent.
7:58:487 hours, 58 minutes, 48 secondsAnd finally let's add on hover border accent with a 30% opacity. Then for the first dynamic
7:58:577 hours, 58 minutes, 57 secondsone will be if the tab is active. So if it is active render BG background text
7:59:047 hours, 59 minutes, 4 secondsforeground border X border border bottom background minus
7:59:107 hours, 59 minutes, 10 secondsuh margin bottom by a single pixel and drop shadow. This will just create a kind of a cool effect. You're going to
7:59:197 hours, 59 minutes, 19 secondssee what it is. And let's just add is first. if it's first border on the left side is transparent and put an
7:59:267 hours, 59 minutes, 26 secondsexclamation point at the end which then results to important.
7:59:337 hours, 59 minutes, 33 secondsSo inside of here, if file is undefined, let's go ahead and render a spinner from components UI spinner.
7:59:467 hours, 59 minutes, 46 secondsLet's give it a class name text ring. Otherwise, let's use the file icon
7:59:547 hours, 59 minutes, 54 secondsfrom React symbols. Make sure you didn't accidentally import one from Lucid React. So, React symbols icons utils.
8:00:038 hours, 3 secondsWe're going to give this file name file name auto assign
8:00:128 hours, 12 secondsand a class name size 4. Below that, we're going to have a span rendering the
8:00:208 hours, 20 secondsfile name with a class name CN
8:00:268 hours, 26 secondstext small white space no wrap
8:00:338 hours, 33 secondsand let's give it is preview itallic.
8:00:398 hours, 39 secondsI think this might be enough for us to start seeing something. So if I click on here, there we go. And you can see how
8:00:488 hours, 48 secondsthey replace each other. But if I double click, you can see how it stopped being itallic. And now when I click on another
8:00:558 hours, 55 secondsone, the preview is now handled in this other tab. This one simply uh highlights back to that one. Right? Let's try creating file three.
8:01:078 hours, 1 minute, 7 secondsYou can see it only replaces what was previously in the preview tab. If I double click on file three, that becomes
8:01:158 hours, 1 minute, 15 secondspermanent. You can see how everything is synchronized. And clicking on the file two opens a third preview tab. Great.
8:01:248 hours, 1 minute, 24 secondsOur logic is working. And if you're wondering that like minus margin bottom pixel is doing this. So it kind of looks
8:01:338 hours, 1 minute, 33 secondslike the border is going up and down. So and this doesn't have a border. It's just like a little trick to make that
8:01:418 hours, 1 minute, 41 secondscool effect. All right, now let's go ahead and implement the buttons which will help us close these tabs. So these
8:01:508 hours, 1 minute, 50 secondswill be normal HTML buttons and let's go ahead and do on click here event prevent
8:01:578 hours, 1 minute, 57 secondsdefault and stop propagation and close the tab. Then let's go ahead and add on
8:02:058 hours, 2 minutes, 5 secondskey down if the key is [snorts] enter or if the key is an empty space prevent default stop propagation and close the
8:02:148 hours, 2 minutes, 14 secondstab and add a class name here again CN util the first one will be just the
8:02:228 hours, 2 minutes, 22 secondsgeneral style padding.5 rounded small hover background white with 10% opacity opacity zero group hover opacity 100.
8:02:338 hours, 2 minutes, 33 secondsAnd then for the second one, if it's active, opacity is just a constant 100.
8:02:418 hours, 2 minutes, 41 secondsAnd an X icon from Lucid React.
8:02:468 hours, 2 minutes, 46 secondsThere we go. I think that is it. So now we should be able to close tabs.
8:02:558 hours, 2 minutes, 55 secondsAwesome. We have a fully working tab system here. Super cool. Now let's go
8:03:038 hours, 3 minutes, 3 secondsahead and add the breadcrumbs which are going to help us tell where this file is located at. To implement breadcrumbs, we
8:03:118 hours, 3 minutes, 11 secondshave to go back. So let's go back inside of editor component editor view where we
8:03:198 hours, 3 minutes, 19 secondsactually render the top navigation. And now using this project ID, we're going to actually use our previously imported
8:03:288 hours, 3 minutes, 28 secondshook use editor. So import that from hooks use editor. Get the active tab id.
8:03:358 hours, 3 minutes, 35 secondsAnd then outside of this div encapsulating the top navigation, we're going to check if we have active tab ID.
8:03:438 hours, 3 minutes, 43 secondsLet's render file breadcrumbs.
8:03:468 hours, 3 minutes, 46 secondsThe file breadcrumbs will then again have a project ID as the prop. Now let's implement the file breadcrumbs. So I'm
8:03:558 hours, 3 minutes, 55 secondsgoing to do that here again. File breadcrumbs. TSX.
8:04:048 hours, 4 minutes, 4 secondsLet's import.
8:04:078 hours, 4 minutes, 7 secondsUh okay. Let's import React from React.
8:04:148 hours, 4 minutes, 14 secondsfile icon from react symbols.
8:04:198 hours, 4 minutes, 19 secondsLet's import use file path from features projects hooks use files once again.
8:04:278 hours, 4 minutes, 27 secondsLet's import use editor from features editor hooks use editor. Let's import
8:04:358 hours, 4 minutes, 35 secondseverything from breadcrumbs from components UI breadcrumbs. So item page link list and separator.
8:04:448 hours, 4 minutes, 44 secondsLet's go ahead and import ID from convex generated data model. And now let's go
8:04:518 hours, 4 minutes, 51 secondsahead and prepare the file breadcrumbs component. The file breadcrumbs component accepts a project ID which is
8:04:598 hours, 4 minutes, 59 secondsa type of ID projects. In here two things. Extract active tab ID from use editor project ID and get the file path
8:05:088 hours, 5 minutes, 8 secondsfrom use file path. This will allow us to get this in this kind of um well I
8:05:168 hours, 5 minutes, 16 secondshave it here right in an array of an ancestors from root to file and then we will be able to create this
8:05:258 hours, 5 minutes, 25 secondsonce we have that let's check if file path is undefined
8:05:318 hours, 5 minutes, 31 secondsand there is no active tab id in that case let's just go ahead and return kind
8:05:388 hours, 5 minutes, 38 secondsof a placeholder so a div with class name padding two bg background padding left four and border bottom breadcrumb
8:05:478 hours, 5 minutes, 47 secondsbreadcrumb list with class name on small gap.5 oh it's always gap five okay breadcrumb item with class name text
8:05:558 hours, 5 minutes, 55 secondssmall breadcrumb page and now this is a special uni code uni-ode sign for an empty string I'm not sure if this would
8:06:048 hours, 6 minutes, 4 secondsdo the same purpose I think I didn't manage to get that result that's why I'm specifically uh doing this in case you're wondering.
8:06:138 hours, 6 minutes, 13 secondsSo just a normal breadcrumb composition as a placeholder, right? This is a loading scenario.
8:06:218 hours, 6 minutes, 21 secondsAnd now we can kind of uh copy this actually. So let me just copy this and return it here
8:06:298 hours, 6 minutes, 29 secondsbecause now we're going to actually be building the real thing. So close the div.
8:06:368 hours, 6 minutes, 36 secondsLet's indent this back inside of the breadcrumb list. Let's get file path dom item and the index.
8:06:478 hours, 6 minutes, 47 secondsAnd let's go ahead and check is it the last element. So if index is equal to the overall length of the file path minus one because arrays start at zero.
8:06:588 hours, 6 minutes, 58 secondsLet's go ahead and do react.fragment here in this form. So react.fragment fragment
8:07:068 hours, 7 minutes, 6 secondsgive it a key item underscore id then inside we are
8:07:148 hours, 7 minutes, 14 secondsgoing to render the breadcrumb item with class name text small and now let's do
8:07:218 hours, 7 minutes, 21 secondstwo scenarios the first one will check if is last and the other one will do well something else if it is last
8:07:308 hours, 7 minutes, 30 secondswe are going to render breadcrumb page with class name flex items center and
8:07:378 hours, 7 minutes, 37 secondsgap one. Inside of that breadcrumb page, we're going to render the file icon with file name, auto assign, and class name.
8:07:468 hours, 7 minutes, 46 secondsAnd next to it, the file name. And alternatively, we're just going to render the item name
8:07:568 hours, 7 minutes, 56 secondsusing a breadcrumb link. Nothing more. I will collapse it so it's easier to look
8:08:028 hours, 8 minutes, 2 secondsat. like this. Okay. And then let's go outside of the breadcrumb item and do if
8:08:098 hours, 8 minutes, 9 secondsit is not last render breadcrumb separator like that. There we go. That's it.
8:08:208 hours, 8 minutes, 20 secondsNow that we have the file breadcrumbs, we can now go back to the editor view and we can import file breadcrumbs.
8:08:298 hours, 8 minutes, 29 secondsLet's check it out.
8:08:318 hours, 8 minutes, 31 secondsSo now when I go ahead and I open a file. Whoops. Looks like something's not working. Could not find public function
8:08:388 hours, 8 minutes, 38 secondsfor files get file path. Oh, that's because I don't have it running. npx
8:08:458 hours, 8 minutes, 45 secondsconvex dev. This will synchronize that new function or it will show us an error if something's wrong. Let's go ahead and
8:08:528 hours, 8 minutes, 52 secondstry this again. I'm going to go ahead and open a file. And you can see right now it's super simple, right? because these are root files. But if I go ahead
8:09:018 hours, 9 minutes, 1 secondand if I create a new file inside of here, so nested file and if I click on
8:09:088 hours, 9 minutes, 8 secondsit, you can see how it tells me exactly what folder it's in. And if I go ahead and create a folder two, and if I go
8:09:178 hours, 9 minutes, 17 secondsahead here and create a folder three, and inside folder three, I create super
8:09:258 hours, 9 minutes, 25 secondsnested.tsx the SX and click on it. You can see that it can traverse up the path until it finds the exact child.
8:09:358 hours, 9 minutes, 35 secondsOne noticeable difference I can immediately tell from the original one is that the gap between the separator
8:09:428 hours, 9 minutes, 42 secondsand items is much smaller. So I just want to uh quickly investigate why is that. So I'm going to go back inside of
8:09:508 hours, 9 minutes, 50 secondsfile breadcrumbs here. And I think I found exactly why. Let me see.
8:09:578 hours, 9 minutes, 57 secondsUh I think I know. Remember how I removed this small gap five because I
8:10:068 hours, 10 minutes, 6 secondsthought logically it's not needed but looks like you have to explicitly tell it that even on small make the gap smaller.
8:10:158 hours, 10 minutes, 15 secondsThere we go. You can see that now it looks better. Currently clicking on it doesn't do anything. uh later you could implement something like a dropdown of
8:10:238 hours, 10 minutes, 23 secondsthe current files but for our use case this is more than enough. So yes it has a brief loading state but after that it
8:10:318 hours, 10 minutes, 31 secondsactually hits cache every time. I'm pretty satisfied with how this turned out. Amazing. Now let's actually
8:10:408 hours, 10 minutes, 40 secondsimplement the editor down here. We are not going to implement any AI features or things like this. We're just going to
8:10:488 hours, 10 minutes, 48 secondsmake sure we have the basic code mirror 6 added in this project. So in order to implement the code editor down here, we
8:10:578 hours, 10 minutes, 57 secondshave to start by defining what happens when a file is not selected. So that's actually quite an easy state. The only
8:11:068 hours, 11 minutes, 6 secondsthing we have to do first is head to Polaris assets and in here find logo
8:11:128 hours, 11 minutes, 12 secondsalternative. I found it from the exact same place where I found logo SVG. So logo ipsum and untitled UI. So now let's
8:11:238 hours, 11 minutes, 23 secondsgo ahead and add this. I just copy the raw file. I'm going to go inside of public and I will add logo alt SVG. I'm
8:11:328 hours, 11 minutes, 32 secondsgoing to open this file and just paste the code inside. If you really want to, you can use the exact same icon which is your main logo. And then let's go back
8:11:408 hours, 11 minutes, 40 secondsinside of the editor view. And now let's go ahead and do a scenario which is if there is no active file. So let's also
8:11:508 hours, 11 minutes, 50 secondsdo const active file to be use file from features projects hooks use file and
8:11:598 hours, 11 minutes, 59 secondspass in the active tab id like this. So that's our active file. And now we are
8:12:078 hours, 12 minutes, 7 secondsgoing to check within a div which we give a class name flex one minimum
8:12:138 hours, 12 minutes, 13 secondsheight of zero bg background if there is no active file whatsoever or
8:12:218 hours, 12 minutes, 21 secondswe maybe can't load it. Let's go ahead and create a div with a class name size
8:12:298 hours, 12 minutes, 29 secondsfull flex items center justify center
8:12:358 hours, 12 minutes, 35 secondsand inside we import image from next image. So, make sure you add this.
8:12:438 hours, 12 minutes, 43 secondsAnd we give it source logo, my apologies, logo-altt svg, alt polaris, or whatever is the name of your project.
8:12:558 hours, 12 minutes, 55 secondsWidth of 50, height of 50, and a class name opacity 25. Let's take a look at that.
8:13:078 hours, 13 minutes, 7 secondsSo now if I close this, you can see that I have like a nice placeholder which is branded as my project until I click on a
8:13:158 hours, 13 minutes, 15 secondsfile and it loads. You can see that then uh it's supposed to well load something. But right now it isn't loading anything.
8:13:238 hours, 13 minutes, 23 secondsSo what we're going to do is do the opposite. If we have an active file
8:13:308 hours, 13 minutes, 30 secondsin that case, let's go ahead and render code editor which we don't have. But let's go ahead and just well actually let's not pass any values right now.
8:13:418 hours, 13 minutes, 41 secondsWe're going to implement values later.
8:13:448 hours, 13 minutes, 44 secondsSo now let's go inside of editor components. Let's create a new file called editor.tsx.
8:13:558 hours, 13 minutes, 55 secondsAnd let's see how do we set it up. So we're going to be using code mirror
8:14:038 hours, 14 minutes, 3 secondsspecifically code and mirror version six. And this is kind of a basic example. So let's see examples basic editor. Looks like this is enough.
8:14:168 hours, 14 minutes, 16 secondsSo I'm going to go ahead and do the following. I will install. We're going to do all of these later and dive in like what are all of these classes. But
8:14:248 hours, 14 minutes, 24 secondslet's start with I don't know maybe something like this.
8:14:298 hours, 14 minutes, 29 secondsnpm install code mirror.
8:14:338 hours, 14 minutes, 33 secondsAnd let's do mpm install code mirror slash language- javascript.
8:14:438 hours, 14 minutes, 43 secondsLet me show you what versions I'm working with. I think minor versions are not as important as the major one which
8:14:528 hours, 14 minutes, 52 secondsis version six. So you can see my code mirror is 6.0.2 and my lang JavaScript is 6.2.4.
8:15:018 hours, 15 minutes, 1 secondBasically both are on version 6. Now that I have that I'm going to go ahead and export const code editor.
8:15:148 hours, 15 minutes, 14 secondsAnd in order to kind of render this, I'm going to go ahead and do const editor
8:15:198 hours, 15 minutes, 19 secondsref use ref from React HTML div element
8:15:258 hours, 15 minutes, 25 secondsand pass in null. Then const view ref use ref.
8:15:328 hours, 15 minutes, 32 secondsLet's pass in editor view or null and null here as well.
8:15:418 hours, 15 minutes, 41 secondsNow let's go ahead and return div
8:15:508 hours, 15 minutes, 50 secondsrefitor ref with a class name size full plg
8:16:018 hours, 16 minutes, 1 secondbackground and it's actually a self-closing tag. There's nothing we need to pass inside.
8:16:098 hours, 16 minutes, 9 secondsAnd it looks like, oh yeah, this is an unfortunate name here. It's called editor view. And we should import it
8:16:188 hours, 16 minutes, 18 secondsfrom a package code mirror forward slash view. So let's actually install that package. npm install code mirror slash
8:16:288 hours, 16 minutes, 28 secondsview. And then I'm going to show you my package JSON again. There we go. 6.39.8 8 in case you want to use the same version of my code mirror forward/ view.
8:16:388 hours, 16 minutes, 38 secondsWhy do I say unfortunate name? Uh well because we have editor view right here.
8:16:478 hours, 16 minutes, 47 secondsSo be careful not to import this one. So let's manually go here. Editor view. Not
8:16:568 hours, 16 minutes, 56 secondsthere we go. This is a mistake. Not that one from code mirror view like that. And maybe I can import type editor view. So
8:17:048 hours, 17 minutes, 4 secondsit's very strictly used as a type. I don't know. Okay, so that's the view ref. And I think actually we will use it later. And for now, let's just call a
8:17:138 hours, 17 minutes, 13 secondsuse effect which we can import from React.
8:17:188 hours, 17 minutes, 18 secondsAnd inside of here, I'm just going to go ahead and create const view, new editor view.
8:17:298 hours, 17 minutes, 29 secondsdocument will be start document parent is going to be editor ref.tc current
8:17:378 hours, 17 minutes, 37 secondslike that. Uh editor view cannot be used as this. Okay. So remove type from here.
8:17:458 hours, 17 minutes, 45 secondsOkay. Uh before we do it let's actually check if there is no editor ref current
8:17:518 hours, 17 minutes, 51 secondsreturn. So we get rid of that error. And then in here extensions are going to be an array.
8:18:008 hours, 18 minutesThe first one will be basic setup. And we should be able to import basic setup.
8:18:068 hours, 18 minutes, 6 secondsLet's see from code mirror itself. Okay.
8:18:138 hours, 18 minutes, 13 secondsFrom code mirror. Let's see. And it looks like it also imports editor view.
8:18:198 hours, 18 minutes, 19 secondsSo yeah, you can import that from here too. So basic setup. And let's import JavaScript
8:18:268 hours, 18 minutes, 26 secondsand pass in Typescript to be true.
8:18:318 hours, 18 minutes, 31 secondsAnd where do we import that from? Well, from the package we installed previously. Code mirror lang JavaScript.
8:18:388 hours, 18 minutes, 38 secondsJust destructure the import like this.
8:18:438 hours, 18 minutes, 43 secondsOkay. So the view ref I think uh will not be used uh or maybe it will. Let's
8:18:508 hours, 18 minutes, 50 secondssee. So now down here after we initialize the view, let's actually do view ref.curren and
8:18:578 hours, 18 minutes, 57 secondspass in the view. And let's go ahead and create an unmount function. view.destroy. Whoops.
8:19:068 hours, 19 minutes, 6 secondsThere we go.
8:19:088 hours, 19 minutes, 8 secondsAnd I think that this should be enough for us to just render a super basic code
8:19:168 hours, 19 minutes, 16 secondseditor here. Let's go back inside of the component editor view and import it from dot /code editor.
8:19:258 hours, 19 minutes, 25 secondsAnd now when I go ahead and select the random file, I should see a text start document and I should be able to type in here.
8:19:388 hours, 19 minutes, 38 secondsAnd you can even see that there is some kind of syntax. obviously doesn't work well because this is a light themed syntax put into our dark mode app. So we
8:19:478 hours, 19 minutes, 47 secondsare going to have to change the theme but try the indentation on or things like that. Try collapsing. You can see that it works right. There are a few
8:19:568 hours, 19 minutes, 56 secondsbugs here and there like this indentation is kind of being funky right now. Uh but we will work towards fixing
8:20:048 hours, 20 minutes, 4 secondsall of those things right now. So, uh, what I want to do now is I want the ability to, well, it makes no sense to
8:20:138 hours, 20 minutes, 13 secondsload the actual like value now because all of these files are empty. So, all of them are going to be completely empty.
8:20:228 hours, 20 minutes, 22 secondsIt makes no sense to load that. Instead, uh, how about we go inside of code editor and we change the document to be
8:20:318 hours, 20 minutes, 31 secondsjust like a super simple implementation. Let me go ahead and see.
8:20:388 hours, 20 minutes, 38 secondsCan I write this like const I don't know counter
8:20:448 hours, 20 minutes, 44 secondsand then in here const value set value
8:20:508 hours, 20 minutes, 50 secondsuse state zero const on increase
8:20:568 hours, 20 minutes, 56 secondscall the set value value + one like something super simple
8:21:048 hours, 21 minutes, 4 secondson decrease and return
8:21:108 hours, 21 minutes, 10 secondsand in here a div maybe div
8:21:178 hours, 21 minutes, 17 secondsand in here a button which shows the current value
8:21:258 hours, 21 minutes, 25 secondsduplicate that I don't know I'm just kind of making things up as I go on increase
8:21:348 hours, 21 minutes, 34 secondsand on click on decrease Actually, how about we just do one? There we go. That's kind of code that makes sense.
8:21:428 hours, 21 minutes, 42 secondsSo, some default value that's kind of a good example of uh a JSX document, right? So that we can work with this.
8:21:518 hours, 21 minutes, 51 secondsCurrently looks horrible. So, we are going to work our way uh through improving it and adding it some fun things, right?
8:22:028 hours, 22 minutes, 2 secondsSo, uh let's see what is the easiest thing we can add here. Well, I think the easiest thing we can add is the one
8:22:118 hours, 22 minutes, 11 secondstheme, one dark theme. It's called like that, right? So, let me go ahead and expand this and let's do npm install
8:22:208 hours, 22 minutes, 20 secondscode mirror slash theme one dark. Let's install it.
8:22:268 hours, 22 minutes, 26 secondsI'm going to show you my package. JSON code mirror theme one dark 6.1.3.
8:22:328 hours, 22 minutes, 32 secondsYou can see that six is kind of the only important thing here. Once we have uh one dark theme, I'm going to go ahead
8:22:418 hours, 22 minutes, 41 secondsand import one dark. And all I'm going to do is I'm going to add it to my extensions list like this. One dark. And
8:22:508 hours, 22 minutes, 50 secondsI'm going to save. And then uh I'm going to have to refresh here. And let's see. Hopefully, it kind of looks better now.
8:22:588 hours, 22 minutes, 58 secondsLooks much much better. How about this?
8:23:028 hours, 23 minutes, 2 secondsTry copying your entire file from your actual editor and paste it here. Look at
8:23:098 hours, 23 minutes, 9 secondsthat. Looks pretty good. You can scroll, but it looks pretty good. You can fold things, right? Looking really, really
8:23:178 hours, 23 minutes, 17 secondsgood, but not perfect. So we are now going to add more and more stuff here until it looks better and better. So how
8:23:268 hours, 23 minutes, 26 secondsabout we start by giving it uh a full height team. This should uh enable it
8:23:348 hours, 23 minutes, 34 secondsenable us to scroll down. I think that one is an easy win too. So the place I
8:23:418 hours, 23 minutes, 41 secondswant to develop that is within the editor. But I'm going to specifically start calling these extensions.
8:23:478 hours, 23 minutes, 47 secondsSo they aren't, you know, combined with components or anything like that. And I will call this one theme. DS. And let's
8:23:568 hours, 23 minutes, 56 secondsdo export con custom theme editor view from code mirror not from our
8:24:048 hours, 24 minutes, 4 secondscomponents, right? And let's go ahead and call dot theme here. The first one will be and which simply uh hides the outline.
8:24:158 hours, 24 minutes, 15 secondsUh then we're going to go ahead and add cm content here and the font family. I think this is actually not the correct
8:24:248 hours, 24 minutes, 24 secondsvariable. Where do we find the correct variable in our source app layout? So we added font enter and font plex mono.
8:24:348 hours, 24 minutes, 34 secondsMake sure yours is the same inside of source app layout. You can see it's just simple next font Google imports. Copy the variable name. And now add it here.
8:24:468 hours, 24 minutes, 46 secondsAnd also double check in your globals.css.
8:24:518 hours, 24 minutes, 51 secondsSo your source app globals.css all the way up here. Font mono should
8:24:578 hours, 24 minutes, 57 secondsalso be fontlex mono here. Great. So that's CM content and font size 14 pixels.
8:25:068 hours, 25 minutes, 6 secondsCM scroller scroll bar width thin and transparent. And uh let me see. Let me
8:25:148 hours, 25 minutes, 14 secondssee. I think I'm I'm missing something because I have a feeling like none of these will actually help me with my scroll situation.
8:25:258 hours, 25 minutes, 25 secondsLet me refresh. Oh, I didn't add this theme. So, I won't see it anyway. So, I have to go inside of components code editor right here.
8:25:368 hours, 25 minutes, 36 secondsAnd uh we have to add the theme. So after one dark I'm going to add custom theme
8:25:448 hours, 25 minutes, 44 secondswhich we import from extensions theme. I'm going to refresh again.
8:25:538 hours, 25 minutes, 53 secondsLet me open this.
8:25:558 hours, 25 minutes, 55 secondsAnd uh I don't think much has improved really. I mean nothing that I can see.
8:26:028 hours, 26 minutes, 2 secondsAnd I'm still having a problem with scrolling. So, I still cannot scroll.
8:26:078 hours, 26 minutes, 7 secondsI'm trying to figure out why that is. I mean, this happened to me as well. I just can't pinpoint what exactly was the
8:26:158 hours, 26 minutes, 15 secondsfix. I was kind of sure it was going to be the theme here, but maybe it is not.
8:26:238 hours, 26 minutes, 23 secondsSo, let me go ahead and kind of discover a bit. All right. So I did some research and I actually couldn't don't really understand why uh we are having the
8:26:328 hours, 26 minutes, 32 secondsissue that we're having. uh you know basically you can see it doesn't take a 100% of the screen right so if I copy
8:26:408 hours, 26 minutes, 40 secondsalong um I mean this is how I tried debugging so inside of my code editor I changed from BG background to red
8:26:498 hours, 26 minutes, 49 seconds500 and I saw okay so it's taking 100% of the space right so why is the editor ref not being populated 100%.
8:27:018 hours, 27 minutes, 1 secondSo then I went inside of my extensions custom theme here and in this one I gave it a height of 100%.
8:27:098 hours, 27 minutes, 9 secondsAnd that actually fixes it. So if I go ahead now inside of this, you can see there's
8:27:188 hours, 27 minutes, 18 secondsspace down here. And if I go inside of code editor and I copy something along, you can see that now I can scroll. But
8:27:268 hours, 27 minutes, 26 secondsI'm not sure why because this was not needed in my original source code. So
8:27:338 hours, 27 minutes, 33 secondsI'm just not 100% sure why and I'm not sure how it's going to behave going forward. Let me try with zoom in and
8:27:428 hours, 27 minutes, 42 secondszoom out. It seems to be working very well. It's important that no lines are being cut off. Uh let me try triggering
8:27:528 hours, 27 minutes, 52 secondssearch functionality. You can uh uh do command F and that should trigger the search functionality. So let me try
8:27:598 hours, 27 minutes, 59 secondsclosing it. That doesn't seem to create any problem either. So I'm very confused right now. I have no idea why in my
8:28:088 hours, 28 minutes, 8 secondsoriginal source code I didn't need to put height 100, but here I need to put height 100. So, what I'm going to do now
8:28:178 hours, 28 minutes, 17 secondsis I'm just going to make sure that I'm using everything the same as an in in my original source code. For example, I don't import from code mirror here.
8:28:268 hours, 28 minutes, 26 secondsInstead, I import from code mirror view.
8:28:308 hours, 28 minutes, 30 secondsSo, I'm just going to make sure. Okay, I'm going to use that here too. Let me try. If I comment out height, does that maybe resolve it? I doubt it. It
8:28:398 hours, 28 minutes, 39 secondsshouldn't. It makes no sense for that one because they're essentially the exact same thing. Oh, wait. Was it that?
8:28:468 hours, 28 minutes, 46 secondsNo, it's not because I can see the scroll bar is here, which means if I copy something larger, yeah, I can't
8:28:528 hours, 28 minutes, 52 secondsscroll no matter what I do. Okay, so looks like we just need height 100 in
8:29:008 hours, 29 minutesour custom theme. I'm not sure why. So, if it's not working for you, okay, you know, just continue going through this chapter and I'm going to investigate
8:29:108 hours, 29 minutes, 10 secondsthis later so we can determine exactly what's happening here. How come I didn't need this in my original source code,
8:29:178 hours, 29 minutes, 17 secondsbut I need it now. Maybe the answer is in some other components. I don't know.
8:29:218 hours, 29 minutes, 21 secondsBut I doublech checked everything and everything looks fine. So yeah, let's just, you know, wing it. And we're going to use our custom theme like this. Okay.
8:29:328 hours, 29 minutes, 32 secondsAnd now I think that we kind of hit the limit of what we can do ourselves. Uh
8:29:408 hours, 29 minutes, 40 secondswell maybe the only thing we can improve is implementing our own language extension recognizer because right now
8:29:498 hours, 29 minutes, 49 secondsthis only works for JSX or TS files right if I for example try creating I
8:29:558 hours, 29 minutes, 55 secondsdon't know a index.html HTML uh you can see it's using the invalid
8:30:028 hours, 30 minutes, 2 secondssyntax right well unfortunately this will work too but maybe not fully I
8:30:118 hours, 30 minutes, 11 secondsdon't know um try some other language right inside I think we can maybe copy something here let's see do we have
8:30:208 hours, 30 minutes, 20 secondsanything here like a readme try pasting it in in here yeah you can see this is not correct
8:30:278 hours, 30 minutes, 27 secondssee the syntax breaking, right? So, how do you implement a smart recognizer of syntax? Well, step by step and one by
8:30:378 hours, 30 minutes, 37 secondsone. So, what we're going to need to do is create another extension here. So, inside of your extensions, create a new
8:30:438 hours, 30 minutes, 43 secondsfile. I'm going to uh call this actually Huh. Okay. Yeah. Let's go here.
8:30:548 hours, 30 minutes, 54 secondsAnd I will call this uh language extension DS.TS specifically. And now here's the thing.
8:31:058 hours, 31 minutes, 5 secondsYou decide how many languages you want to support.
8:31:088 hours, 31 minutes, 8 secondsSo I imported code mirror state code mirror lang JavaScript. And now what I have to do is I have to install all of
8:31:168 hours, 31 minutes, 16 secondsthese packages. So pause the screen and install all of them. And I'm going to show you my versions.
8:31:238 hours, 31 minutes, 23 secondsSo these are all the packages code mirror HTML CSS JSON markdown Python and there's so many more you can do but you
8:31:318 hours, 31 minutes, 31 secondshave to install them all and you have to configure them. So now while this is doing let's go ahead and let's export
8:31:398 hours, 31 minutes, 39 secondsconst get language extension accept file name which is a string and return extension from code mirror state.
8:31:508 hours, 31 minutes, 50 secondsUh now in order to get the extension from the file name we will split it by a
8:31:578 hours, 31 minutes, 57 secondsdot separator get the last one and lowercase it and then we're going to use
8:32:038 hours, 32 minutes, 3 secondsa switch case on the extension. If case is JS we are going to return
8:32:128 hours, 32 minutes, 12 secondsJavaScript right and so on and so on. So I'm just going to go ahead uh and copy and paste the rest.
8:32:218 hours, 32 minutes, 21 secondsHere it is. So let me show you so you can pause. JS JavaScript JSX JavaScript with the config. Same for TypeScript and
8:32:308 hours, 32 minutes, 30 secondsTSX which enables both of them. HTML CSS JSON for both MD and MDX we use markdown Python and by default an empty array.
8:32:418 hours, 32 minutes, 41 secondsGreat. So that's the language extension.
8:32:438 hours, 32 minutes, 43 secondsI didn't show you my package JSON. So here it is. If you want to see all the languages that I have again six, the major version is the one that's important.
8:32:538 hours, 32 minutes, 53 secondsNow that we have the language extension, uh let's go ahead and initialize it here. Const language extension will be use memo.
8:33:058 hours, 33 minutes, 5 secondsAnd let's go ahead and call it like this. get language extension from
8:33:118 hours, 33 minutes, 11 secondsextensions language extension and pass in the file name. The problem is we
8:33:188 hours, 33 minutes, 18 secondsdon't have the file name. Yes. So, okay, pass in the file name and put it in the
8:33:258 hours, 33 minutes, 25 secondsdependency array. File name. So, let's import use memo from React. And for the
8:33:338 hours, 33 minutes, 33 secondsfile name, let's go ahead and create an interface props file name string extract file name and assign the props.
8:33:468 hours, 33 minutes, 46 secondsAnd now we have that error resolved.
8:33:508 hours, 33 minutes, 50 secondsAnd now inside of here after you do the basic setup,
8:33:598 hours, 33 minutes, 59 secondslet's add language extension in place of the JavaScript one like that. Let me go
8:34:058 hours, 34 minutes, 5 secondsahead and maybe write this in a prettier way like this.
8:34:108 hours, 34 minutes, 10 secondsRemove the unused import. Now, now let's go back to the editor uh view where we
8:34:178 hours, 34 minutes, 17 secondsactually do this and let's pass in file name to be active file name like that.
8:34:278 hours, 34 minutes, 27 secondsThere we go. So now when I open tsx it should Oh, I have to refresh first. Yes,
8:34:358 hours, 34 minutes, 35 secondsalways refresh first because the hot reload does not affect this. So you can see this is now tsx right but you can
8:34:428 hours, 34 minutes, 42 secondssee how here the syntax breaks which is correct because this is an HTML file right so it shouldn't render the same
8:34:518 hours, 34 minutes, 51 secondssyntax and just like that we've implemented our own uh language syntax decider
8:34:588 hours, 34 minutes, 58 secondsand now uh let's see what else can we do so for example our tab indentation
8:35:068 hours, 35 minutes, 6 secondscurrently sucks it doesn't work let's Let's go ahead and improve it by adding code mirror commands.
8:35:148 hours, 35 minutes, 14 secondsSo, npm install. Let me go ahead and fix this. Code mirror commands.
8:35:228 hours, 35 minutes, 22 secondsAnd once you install it, let's go ahead right here. Import indent with tab from code mirror commands.
8:35:338 hours, 35 minutes, 33 secondsAnd then down here after language extension add keymap.off and inside of here add indent with tab.
8:35:458 hours, 35 minutes, 45 secondsAnd the keymap solution comes from the following. So I'm going to do a slight modification here simply so I have the exact same as
8:35:548 hours, 35 minutes, 54 secondsmy source code because I'm still basled you know why it works on one example but doesn't with the other. So edit view
8:36:018 hours, 36 minutes, 1 secondfrom code mirror view and keymap from here.
8:36:068 hours, 36 minutes, 6 secondsAnd now you should be able to indent with tab. Let's go ahead and see again.
8:36:158 hours, 36 minutes, 15 secondsLet's do a refresh.
8:36:188 hours, 36 minutes, 18 secondsLet's go ahead and try. There we go. You can see that now it doesn't escape the
8:36:258 hours, 36 minutes, 25 secondseditor. I can now safely indent. Who knows? Maybe it was some of these extensions which enabled the full height
8:36:338 hours, 36 minutes, 33 secondsview, right? But let me try pasting again. It seems fine. It seems to work.
8:36:378 hours, 36 minutes, 37 secondsOkay. Right. I'm not sure what was the issue, but I'm just confused. Why do I need it here? But I didn't need it in my source code. But still seems to work great. Uh, okay. What else should we do?
8:36:508 hours, 36 minutes, 50 secondsHow about a mini map? Right. You see this? How about we add that? So that is
8:37:008 hours, 37 minutesactually uh implemented by Replet, right? They actually have a package of
8:37:078 hours, 37 minutes, 7 secondstheir own. So basically a bunch of community packages exist for code mirror and this one is from Replet because
8:37:148 hours, 37 minutes, 14 secondsReplet itself decided to use code mirror uh over all the other editors that exist. So I actually gave you a very
8:37:218 hours, 37 minutes, 21 secondsgood and tested solution. Once we install that, let me show you my package JSON. So, Replet code mirror mini map
8:37:298 hours, 37 minutes, 29 seconds0.5.2 if you want to use the same version and we're going to head inside of the extensions here and I will just add mini map.ts.
8:37:418 hours, 37 minutes, 41 secondsI'm going to import show mini map from replet code mirror mini map. I'm going
8:37:488 hours, 37 minutes, 48 secondsto do a simple create mini map. And the last time I mentioned mini map hopefully
8:37:558 hours, 37 minutes, 55 secondsexport const mini map with show mini map compute document and return create and
8:38:028 hours, 38 minutes, 2 secondsthe create method above. All right. Now that we have that we can go back inside of the uh code editor
8:38:118 hours, 38 minutes, 11 secondsand after keymap off add mini map from the extension
8:38:188 hours, 38 minutes, 18 secondsright here. extensions mini map. There we go. Let's try it out. So, copy code editor entirely. Make sure to refresh this page.
8:38:308 hours, 38 minutes, 30 secondsAnd let's go ahead and select the file, paste things inside. And look at it go. A beautiful mini map right here.
8:38:408 hours, 38 minutes, 40 secondsHow about we add another useful feature?
8:38:448 hours, 38 minutes, 44 secondsFor example, you can see in my uh finished source code, I have this kind of indentation indicators. I can see the
8:38:518 hours, 38 minutes, 51 secondsdepth of indentation that is actually also handled uh by replet. So, let's go ahead and do a quick install.
8:39:038 hours, 39 minutes, 3 secondsMPM install replet code mirror indentation markers. And I'm going to show you what package JSON version I'm
8:39:138 hours, 39 minutes, 13 secondsusing. So package oops, here it is. Package JSON 6.5.3 version for the indentation markers.
8:39:228 hours, 39 minutes, 22 secondsThis one is much simpler to add. We just import indentation markers from replet
8:39:298 hours, 39 minutes, 29 secondscode mirror indentation markers. And let's go ahead now and just add them after the mini map
8:39:388 hours, 39 minutes, 38 secondslike that. indentation uh markers. And I believe that that is kind of the
8:39:468 hours, 39 minutes, 46 secondsuh end of what we can do without modifying the basic setup. Here it is.
8:39:528 hours, 39 minutes, 52 secondsYou can see how we now have indentation uh markers here and how they change depending on the indentation level.
8:40:018 hours, 40 minutes, 1 secondSo, what do I mean uh by the end of what we can do without modifying this basic
8:40:078 hours, 40 minutes, 7 secondssetup? Well, here's the problem. You see this uh kind of fold gutters? You see
8:40:158 hours, 40 minutes, 15 secondsthis? It kind of looks weird. It's not centered. And if you try to like use CSS
8:40:238 hours, 40 minutes, 23 secondsto center it, you will very closely come to a limitation. Very soon come to a limitation. Uh because this is just a
8:40:318 hours, 40 minutes, 31 secondsuni code. This is a character. It's not actually an SVG icon. You can see how good it looks on my finished source code
8:40:388 hours, 40 minutes, 38 secondshere. And the problem is the fold gutters do exist as something you can
8:40:458 hours, 40 minutes, 45 secondsextend, right? So you would have to add fold gutters here and then you would do render icon or whatever is the syntax
8:40:528 hours, 40 minutes, 52 secondsSVG blah blah blah. You would add your own. The problem is fold gutters are already implemented in here in the basic
8:41:008 hours, 41 minutessetup. So that's a problem. You can't implement it twice and you can't extend basic setup. But thankfully the creators
8:41:088 hours, 41 minutes, 8 secondsof code mirror have that solution for us because basic setup is an amazing set of all the packages you need to have your
8:41:158 hours, 41 minutes, 15 secondsapp up and running. Right? So using the link on the screen you can uh first I'm going to show you how to find it yourself. But I also if you cannot find
8:41:248 hours, 41 minutes, 24 secondsit, you can always find this my assets folder in here. In here we have the custom setup file entirely everything we're going to need. Why am I telling
8:41:328 hours, 41 minutes, 32 secondsyou to copy this and why are we not implementing this? Well, because I didn't implement it either. All I did was I searched for uh code mirror basic
8:41:418 hours, 41 minutes, 41 secondssetup on Google and this repository came up from code mirror basic setup and
8:41:488 hours, 41 minutes, 48 secondsinside of the source I have code mirror.ts the S and here it is the entire thing right and here it is the
8:41:568 hours, 41 minutes, 56 secondsfold gutter the one I want to modify the icon for so that's how you do it and it's actually intended to be used like
8:42:048 hours, 42 minutes, 4 secondsthat so the extension itself does not allow customization the the idea is that once you decide you want to configure your editor more precisely you take this
8:42:128 hours, 42 minutes, 12 secondspackages source code which we are doing and copy it into your own code that's exactly what we are doing right now so we are doing this in the way it was
8:42:218 hours, 42 minutes, 21 secondsintended. So using the link on the screen you can find Polaris assets and in here custom setup or you can just you know visit the source code and you can
8:42:298 hours, 42 minutes, 29 secondsjust copy the entire thing here. So it is exactly the same as this one here.
8:42:338 hours, 42 minutes, 33 secondsThe only difference is I added SVGs for folder gutter icons and everything else
8:42:408 hours, 42 minutes, 40 secondsis I'm pretty sure the same. Maybe I did some modifications but I highly doubt and I kind of removed the comments and
8:42:488 hours, 42 minutes, 48 secondseverything else to make it cleaner. So, I'm going to copy this entire thing. And then I'm going to go inside of my extensions again. So, in here in the
8:42:568 hours, 42 minutes, 56 secondsextensions, new file, custom- setup DSX, my apologies.
8:43:038 hours, 43 minutes, 3 secondsDS. And let's paste the entire thing inside. That's it. I'm not even going to go through this because, you know, it's
8:43:118 hours, 43 minutes, 11 secondsjust a copy from the source code. So the only thing we do is we modify the folder gutter because I want it to have a nicer
8:43:188 hours, 43 minutes, 18 secondsSVG icon than whatever it's currently using. And once I have custom setup, I can go back inside of the code editor
8:43:278 hours, 43 minutes, 27 secondsand I can remove basic setup in place of custom setup from extensions custom setup and let's remove basic setup from code mirror now.
8:43:388 hours, 43 minutes, 38 secondsAll right, let's go ahead and check it out now. And now we should have a much nicer icon to collapse things. There we go. This looks much much better.
8:43:508 hours, 43 minutes, 50 secondsPerfect. And see this happening. You can kind of select this. This is the reason why I went inside of my globals. CSS and
8:44:008 hours, 44 minutesdown here uh I added a to-do add select none later. So that's why I did that. Select-
8:44:088 hours, 44 minutes, 8 secondsnone. We can bring it back now because it actually just works better. You can you you shouldn't be able to select things anywhere here. Everything kind of
8:44:178 hours, 44 minutes, 17 secondsis supposed to look like and feel like an app. So that's why I did that. All right. Awesome. So there are definitely
8:44:278 hours, 44 minutes, 27 secondsmore things we can do with our code editor, but I think I want to keep that for another chapter simply because those
8:44:358 hours, 44 minutes, 35 secondsare AI related things. So it makes no sense uh to implement them right now because we won't be able to implement
8:44:448 hours, 44 minutes, 44 secondsthe entire thing. But one thing uh I want to do is the ability to preserve content. Right? So I want to give you
8:44:518 hours, 44 minutes, 51 secondsthe option to save a file. Let's start by changing the code editor interface.
8:44:588 hours, 44 minutes, 58 secondsSo besides file name, let's also give it an onchange and let's also give it an
8:45:058 hours, 45 minutes, 5 secondsinitial value. So this is not going to be a controlled component. Uh because if it is a controlled component, if you
8:45:128 hours, 45 minutes, 12 secondsconstantly accept the new updated value, it it's very annoying because you are typing something here and it receives a
8:45:208 hours, 45 minutes, 20 secondsnew like updated value of this document and it will reset your cursor up here.
8:45:258 hours, 45 minutes, 25 secondsSo it's super annoying. So because of that, we are not going to treat it as a controlled component. We're just going to accept the initial value once we load
8:45:348 hours, 45 minutes, 34 secondsand reset the and reset the initial value on every file change. All right.
8:45:408 hours, 45 minutes, 40 secondsSo we have editor view ref. We have the language extension here. Let's change this document to instead be initial
8:45:478 hours, 45 minutes, 47 secondsvalue and yes we can destructure these now. So file name initial value and on
8:45:548 hours, 45 minutes, 54 secondschange. All right. So we are using initial value here. document initial
8:46:018 hours, 46 minutes, 1 secondvalue. Perfect. Uh let's see what are we missing here. We are missing language
8:46:088 hours, 46 minutes, 8 secondsextension here and we actually don't need the initial value uh because it's only used for the
8:46:168 hours, 46 minutes, 16 secondsinitial document. So we don't want to track its changes. So it isn't this isn't the best thing. But let's doint
8:46:248 hours, 46 minutes, 24 secondsdisable next line react hooks exhaustive depths. And then I'm going to add a little explanation. So dash initial
8:46:328 hours, 46 minutes, 32 secondsvalue is only used for the initial document. I will see if there's like a prettier way of doing this. But for now it gets the job done. So we don't have to pass the initial value here. Great.
8:46:458 hours, 46 minutes, 45 secondsThat part is now done.
8:46:488 hours, 46 minutes, 48 secondsAnd now let's go ahead and implement the onchange.
8:46:528 hours, 46 minutes, 52 secondsI first just want to confirm that we have the necessary uh files here. Too many files open inside of convex files.
8:47:018 hours, 47 minutes, 1 secondDo we have update file? We do. Great.
8:47:068 hours, 47 minutes, 6 secondsNow let's go ahead inside of source features projects hooks use files. And
8:47:148 hours, 47 minutes, 14 secondsthe same thing as we have use create file. Let's go ahead and do use update file. And let's just call update file.
8:47:248 hours, 47 minutes, 24 secondsThat's it. And we need to add I'm going to add to-do add optimistic mutation to
8:47:318 hours, 47 minutes, 31 secondsthese things simply because they make the app fill that much faster, right?
8:47:378 hours, 47 minutes, 37 secondsBut we're not going to do it now. Um we don't need to do it for queries and we don't need to do it for this because uh
8:47:448 hours, 47 minutes, 44 secondsit makes no sense, right? Because this is not a controlled component. So now that we have this, let's go inside of the editor view.tsx dsx right here.
8:47:568 hours, 47 minutes, 56 secondsSo the component right and what I'm going to do is I'm going to add con
8:48:038 hours, 48 minutes, 3 secondsupdate file use update file a hook from features projects hooks use
8:48:118 hours, 48 minutes, 11 secondsfiles. Let me reorder my imports just a little bit here.
8:48:188 hours, 48 minutes, 18 secondsOkay.
8:48:218 hours, 48 minutes, 21 secondsAnd now that I have that, I'm going to go ahead and define a timeout ref
8:48:288 hours, 48 minutes, 28 secondsbecause I want to create a debounce. So I don't want to update on every keystroke. Even though convex can
8:48:358 hours, 48 minutes, 35 secondsprobably handle that, still no reason to do so. Let's be gentle with our updates.
8:48:408 hours, 48 minutes, 40 secondsSo use ref from React. And we're going to implement our very own debounds here.
8:48:478 hours, 48 minutes, 47 secondsSo let's go ahead to the code editor right here. First things first, it
8:48:568 hours, 48 minutes, 56 secondsshould reset on every active file ID, right? And then let's give it the
8:49:038 hours, 49 minutes, 3 secondsinitial value active active file dot content or an empty string.
8:49:138 hours, 49 minutes, 13 secondsFile name is already given. So on change should accept the content which is a type of string.
8:49:248 hours, 49 minutes, 24 secondsFirst things first if we have an existing debounce timeout clear it
8:49:318 hours, 49 minutes, 31 secondsotherwise let's go ahead and let's time out. So we're creating a timeout for
8:49:378 hours, 49 minutes, 37 secondsthis much. So we could store that up here. Const debounce in milliseconds
8:49:458 hours, 49 minutes, 45 secondslike that. So you can easily change it later without having to find the exact function. There we go. Like this. It
8:49:538 hours, 49 minutes, 53 secondswill update using ID active file and the new content. Now we have to go back inside of the code editor here and
8:50:018 hours, 50 minutes, 1 secondactually use on change. So after indentation markers use editor view
8:50:098 hours, 50 minutes, 9 secondsupdate listener of update if update doc changed on change actually
8:50:198 hours, 50 minutes, 19 secondsit's going to be required so you can pass in on change update state document to string
8:50:278 hours, 50 minutes, 27 secondsand let's see on change uh it shouldn't be optional it's required like that.
8:50:348 hours, 50 minutes, 34 secondsAnd I think that should work. So, let's try let's copy code editor here.
8:50:418 hours, 50 minutes, 41 secondsAnd let's see. Last saved 15 minutes ago. I'm going to refresh this entire project now. I'm going to go here,
8:50:498 hours, 50 minutes, 49 secondsselect file one, still saved 25 minutes ago. And I'm going to paste the entire code. And I'm going to wait for a
8:50:558 hours, 50 minutes, 55 secondssecond. So now saved less than a minute ago. And if I refresh and if I click on
8:51:038 hours, 51 minutes, 3 secondsfile one, there we go. We are successfully persisting our content. Amazing. Autosave. No need to save.
8:51:128 hours, 51 minutes, 12 secondsLet's now see uh does it actually actually do something. Right. I'm going I'm again waiting. I'm waiting. I'm
8:51:218 hours, 51 minutes, 21 secondswaiting. So updated definitely. And it didn't move my cursor. At least not what I've noticed. So that's what I was
8:51:288 hours, 51 minutes, 28 secondstesting, right? I think it works very very well. Let's see how it behaves when
8:51:358 hours, 51 minutes, 35 secondsI change different files. Works just as well. Amazing. I'm super satisfied with this. We still have one mystery and that
8:51:448 hours, 51 minutes, 44 secondsis why do I need this? I just want to test one more time. Is it maybe once I add a bunch of these other extensions that something magical happens here?
8:51:568 hours, 51 minutes, 56 secondsOh, looks like it is. Yeah, when I add a bunch of extensions, maybe it's like the mini map or something. You can see that
8:52:038 hours, 52 minutes, 3 secondsat one point we no longer need height 100. I'm not sure why. Maybe it's the mini map. Maybe it's the indentation markers. Let me try commenting this out.
8:52:168 hours, 52 minutes, 16 secondsOh yeah, that's what makes it able to scroll. Okay. So, yes, when we have mini
8:52:238 hours, 52 minutes, 23 secondsmap and indentation markers on, probably just one of them, the scroll is 100%.
8:52:298 hours, 52 minutes, 29 seconds[snorts]
8:52:308 hours, 52 minutes, 30 secondsSo, if you have those two, you can most likely remove height 100. So, however
8:52:378 hours, 52 minutes, 37 secondsyou want to proceed, I don't think this will hurt. So, maybe we can keep it here. But looks like those extensions of
8:52:458 hours, 52 minutes, 45 secondsours do the job as well. Amazing. So I'm just trying to see if there's any last thing we can do, but I think you've
8:52:538 hours, 52 minutes, 53 secondsworked hard enough. Uh there is just one thing actually. Yes, I'm sorry. And that is um we shouldn't always render the
8:53:028 hours, 53 minutes, 2 secondscode editor, right? So let's go ahead and do the following. Const is active
8:53:098 hours, 53 minutes, 9 secondsbinary is active file a binary file. So if we have an active file and if active
8:53:158 hours, 53 minutes, 15 secondsfile has a storage ID it means it is is active file text if we have an active
8:53:238 hours, 53 minutes, 23 secondsfile and if not active files storage ID don't make the mistake of checking if we
8:53:318 hours, 53 minutes, 31 secondshave active file.content content because we don't have to. A file is allowed to be empty. The question is if we have
8:53:398 hours, 53 minutes, 39 secondsstorage ID, it means this is not supposed to have any content at all. And now let's only render the active file
8:53:498 hours, 53 minutes, 49 secondsand the code editor if is active file a textual file. And this should still uh
8:53:578 hours, 53 minutes, 57 secondswork just fine. Um you know what? Maybe instead of doing this, we can go inside of code editor and change the initial
8:54:068 hours, 54 minutes, 6 secondsvalue to an empty string because we obviously want our files to be empty in the beginning. So why don't we modify
8:54:158 hours, 54 minutes, 15 secondsthe code editor to accept that rather than this? And then we can make the initial value optional. There we go.
8:54:228 hours, 54 minutes, 22 secondsThat looks much cleaner on our side. Uh, perfect. And then let's go ahead and do if is active file binary. And we're just
8:54:328 hours, 54 minutes, 32 secondsgoing to do a paragraph to-do implement binary preview.
8:54:398 hours, 54 minutes, 39 secondsGreat. So let's just do one more check and then we're going to open a pull request.
8:54:468 hours, 54 minutes, 46 secondsAnd oh yeah, this is super annoying.
8:54:498 hours, 54 minutes, 49 secondsCan we please go inside of file explorer index tsx
8:54:568 hours, 54 minutes, 56 secondsand just change the default value of is open to true. It's super annoying that we have to open it every single time.
8:55:078 hours, 55 minutes, 7 secondsSo now when I refresh it's open by default and everything here is saved.
8:55:148 hours, 55 minutes, 14 secondsAmazing. Amazing job. works super well.
8:55:198 hours, 55 minutes, 19 secondsWe have everything here. Awesome. So, let's go ahead and let's merge this, right? So, we have 18 files, 19 files,
8:55:288 hours, 55 minutes, 28 secondsright? Package, JSON package, lock files, new image, globals, code editor, editor view, breadcrumbs, navigation,
8:55:368 hours, 55 minutes, 36 secondscustom setup, language extension, mini map, theme, use editor, use editor, store, project ID, view, index.tsx3,
8:55:448 hours, 55 minutes, 44 secondsand use files. Okay, let's go ahead and stop all of our terminals here.
8:55:528 hours, 55 minutes, 52 secondsChapter 10. So, get add dot get commit chapter 10 code editor and state.
8:56:038 hours, 56 minutes, 3 secondsGreat. Get checkout-b 10 code editor and state like this. So
8:56:098 hours, 56 minutes, 9 secondscode editor state and get push u origin 10 code editor state. This will then
8:56:188 hours, 56 minutes, 18 secondspush it. You should be able to see the new branch down here. And let's go ahead onto our GitHub. Let's open a pull
8:56:278 hours, 56 minutes, 27 secondsrequest and let's let code rabbit review this massive PR we've prepared.
8:56:358 hours, 56 minutes, 35 secondsAnd here we have the summary.
8:56:388 hours, 56 minutes, 38 secondsWe added code editor with syntax highlighting, mini map indentation markers and multi- language support. We
8:56:458 hours, 56 minutes, 45 secondsadded file breadcrumb navigation showing a file hierarchy, editor tabs for managing open files with preview and
8:56:538 hours, 56 minutes, 53 secondspinned modes. We integrated file explorer for direct file opening and tab management. And we disabled text
8:57:018 hours, 57 minutes, 1 secondselection across the application. So, looks like we were pretty good. only three uh actionable comments. We do have
8:57:098 hours, 57 minutes, 9 secondssome nitpick comments, but um these aren't critical, right? So, you can always see the nitpick comments, right?
8:57:168 hours, 57 minutes, 16 secondsThey personally define them uh as that and they hide it by default, right? For example, potential stale closure on
8:57:258 hours, 57 minutes, 25 secondschange not in effect dependencies. So, yeah, technically that is correct, but you can see it doesn't actually break anything.
8:57:348 hours, 57 minutes, 34 secondsSo, uh, in here it's actually warning us about adding this select none thing to our body. So, its concern is that it
8:57:438 hours, 57 minutes, 43 secondsbreaks the editor itself that you can select within the editor. I can personally still select. I'm not sure
8:57:518 hours, 57 minutes, 51 secondsabout other browsers or if you have bad experience with select none, feel free to remove it from the body. You don't need it. I just think it's a like a cool thing to make it look like a native app.
8:58:028 hours, 58 minutes, 2 secondsBut um yeah, maybe not the smartest solution giving all the browsers and mobile ones and who knows what select
8:58:118 hours, 58 minutes, 11 secondsnone will actually do. So perhaps in my next chapter I might remove it and just uh revert it to as it was. So good
8:58:188 hours, 58 minutes, 18 secondscomment here. Inside of here we actually do have a real mistake. Uh we never
8:58:248 hours, 58 minutes, 24 secondsclean up pending debounced updates. We clean it up here, but we don't have a
8:58:328 hours, 58 minutes, 32 secondsuse effect with unmount to make sure the timeout ref is clear is cleared. So,
8:58:398 hours, 58 minutes, 39 secondsthis can cause uh memory leaks from uncancled timers, attempted updates after unmounts, and updates to the wrong
8:58:468 hours, 58 minutes, 46 secondsfile if active file changes before the timeout fires. So, a very serious issue that we have to fix in the next chapter.
8:58:558 hours, 58 minutes, 55 secondsThank you, Code Rabbit. uh in here. It doesn't like the fact that we remove the outline, but it just looks so much
8:59:028 hours, 59 minutes, 2 secondsbetter without it. So, I'm going to keep it removed in this case. Awesome. Let's go ahead and merge this pull request. We
8:59:108 hours, 59 minutes, 10 secondsjust did an amazing job. So, almost a thousand new lines. So, we have chapter
8:59:178 hours, 59 minutes, 17 seconds10 right here. Let's go ahead back to main. Get pool origin main. We are now
8:59:258 hours, 59 minutes, 25 secondssynchronized completely. I like to do a little sanity check. I should be on main
8:59:328 hours, 59 minutes, 32 secondsbranch and inside of my graph I should see 10 detached and then merged back
8:59:398 hours, 59 minutes, 39 secondshere. Amazing. So I believe that marks the end of this chapter. We implemented shushand state management code mirror 6
8:59:488 hours, 59 minutes, 48 secondsone dark theme tabbed file switcher syntax highlighting and a bunch of other things actually. Amazing amazing job and see you in the next chapter.
Chapter 12: 11 AI Features
8:59:598 hours, 59 minutes, 59 secondsIn this chapter we're going to add AI features to our code editor. This will include implementing the ghost text
9:00:069 hours, 6 secondssuggestions, handling tab key suggestion acceptance, creating the command or
9:00:129 hours, 12 secondscontrol + k quickedit model, adding a file crawl scraping functions so users
9:00:199 hours, 19 secondscan paste URLs into those quickedit models, and we're going to add all other selectionbased code editing features.
9:00:289 hours, 28 secondsIt's better to show you exactly what I mean. So this is the final product. And you can see that if I attempt to write my own on click method, I have AI giving
9:00:389 hours, 38 secondsme auto completion. And besides that, I am able to use quick edit and give this
9:00:459 hours, 45 secondsfor example a prompt rename these two on enter or anything like that. And you can see it gets the job done. So that's going to be the purpose of this chapter.
9:00:569 hours, 56 secondsWe also have some things from the previous chapter from code rabbit. So, we're going to start by just fixing those issues such as some memory leaks
9:01:059 hours, 1 minute, 5 secondsand then we're going to go right into building the AI features. So, for now, you can just have your npm rundev running and npx convex dev running.
9:01:169 hours, 1 minute, 16 secondsLet's go ahead and refresh our localhost 3000. The first thing I'm going to do is I'm going to go inside of my source app
9:01:259 hours, 1 minute, 25 secondsfolder globals and I'm going to remove select none from here simply because I don't know how this behaves in other browsers and I don't want to give you
9:01:339 hours, 1 minute, 33 secondssome bad advice. It's better to have uh that not here especially in global CSS
9:01:419 hours, 1 minute, 41 secondslater we can add it to like specific elements but in global body element maybe not the best idea. And the second
9:01:499 hours, 1 minute, 49 secondsproblem is we have no cleanup for our debounced updates. So that is inside of the editor view specifically talking
9:01:589 hours, 1 minute, 58 secondsabout this timeout ref. So every time we call on change we debounce using the timeout ref. And we do clear it if uh
9:02:069 hours, 2 minutes, 6 secondstwo of them appear at the same time but we never clear it if this unmounts. So that's something we should do. Uh we can
9:02:149 hours, 2 minutes, 14 secondsdo it very easily using use effect. So down here, I'm just going to do a use effect. Clean up pending debounced
9:02:229 hours, 2 minutes, 22 secondsupdates on unmount or file change. So if active tab ID has changed, we're going to have a different unmount function
9:02:319 hours, 2 minutes, 31 secondshere. If we have timeout ref, let's just clear it and make sure to import use
9:02:379 hours, 2 minutes, 37 secondseffect from React. That's it. That's all we have to add in our editor view.
9:02:439 hours, 2 minutes, 43 secondsPerfect. Now let's go ahead and let's implement a new extension called suggestion. So for that I'm going to go
9:02:519 hours, 2 minutes, 51 secondsinside of features editor components and I'm going to go inside of the code editor. And in here we have to add our own extension.
9:03:029 hours, 3 minutes, 2 secondsSo I'm going to go ahead and do that right here. And it's going to be called a suggestion.
9:03:099 hours, 3 minutes, 9 secondsAnd I'm going to pass in the file name here.
9:03:139 hours, 3 minutes, 13 secondsNow let's go ahead inside of extensions let's create a new folder suggestion
9:03:209 hours, 3 minutes, 20 secondsand inside of suggestion create an index.ts DS it will have multiple files inside. So that's why I'm creating a
9:03:289 hours, 3 minutes, 28 secondsfolder. And now we have to go ahead and build this. So I'm going to build this in stages so it's easier to understand.
9:03:359 hours, 3 minutes, 35 secondsWe're going to start with uh stage one.
9:03:399 hours, 3 minutes, 39 secondsStage one is basically going to be static ghost text. It's going to teach you how to implement a basic widget
9:03:479 hours, 3 minutes, 47 secondstype, decoration, state, field, key map, and it's always going to show the exact
9:03:549 hours, 3 minutes, 54 secondssame suggestion. So no fetching, no AI just yet because that's too much information at once. So let's start very
9:04:039 hours, 4 minutes, 3 secondsvery slow. So obviously I have to create some kind of function which accepts the file name. So let's do that. That's
9:04:109 hours, 4 minutes, 10 secondseasy. export const suggestion which accepts a file name. And let's go ahead
9:04:179 hours, 4 minutes, 17 secondsand return an array. And now in here we're going to build three different let's call them mini extensions, right?
9:04:269 hours, 4 minutes, 26 secondsThe first one will be the suggestion state. Basically, uh that's going to be our state storage, right? What's the
9:04:359 hours, 4 minutes, 35 secondscurrent suggestion? And now let's go ahead and build it. So in order to build that we actually have to add some
9:04:439 hours, 4 minutes, 43 secondsimports from code mirror state. Let me go ahead and expand this here. State effect and state field from code mirror forward/state.
9:04:549 hours, 4 minutes, 54 secondsAnd I don't know if you've noticed but we actually have access to a bunch of code mirror packages that we never
9:05:019 hours, 5 minutes, 1 secondexplicitly installed. If I search for code mirror state it doesn't exist. And I've actually noticed that uh in the
9:05:109 hours, 5 minutes, 10 secondsprevious chapter because we added this extension called custom setup and I just pasted this entire thing and I've
9:05:199 hours, 5 minutes, 19 secondsnoticed I'm not getting any errors for this and that's when it clicked. Oh, it's probably because we have code
9:05:279 hours, 5 minutes, 27 secondsmirror installed and that's serving as kind of the base package. You can confirm that. So, we should both have
9:05:369 hours, 5 minutes, 36 secondscode mirror installed, right? And if you actually go inside of node modules and
9:05:439 hours, 5 minutes, 43 secondsspecifically search for code mirror here and in in its package JSON, you can see it maintains all of these dependencies.
9:05:549 hours, 5 minutes, 54 secondsSo, in case you're wondering how come we didn't have to install any of these is because we have all of them. So I think
9:06:029 hours, 6 minutes, 2 secondswe actually don't need to have code mirror view or code mirror commands, right? Because if I search for it, you
9:06:109 hours, 6 minutes, 10 secondscan see it's one version here and then another version here. So that's actually conflicting. So what I'm actually going
9:06:179 hours, 6 minutes, 17 secondsto do is I'm going to uninstall code mirror commands and I'm going to uninstall code mirror view
9:06:279 hours, 6 minutes, 27 secondssimply because I can see that both of them are maintained in here. I think all
9:06:349 hours, 6 minutes, 34 secondsother ones are actually good right none of these seem to appear in here especially not the replet ones. So just
9:06:429 hours, 6 minutes, 42 secondsfor sanity check, I'm now going to search through my code for all the places where I import code mirror commands. So one of them is inside of
9:06:519 hours, 6 minutes, 51 secondscode editor where I import indent with tab. And you can see in here it's works
9:06:589 hours, 6 minutes, 58 secondsperfectly fine. It's still inside of my node modules because it was maintained uh by another package. Right? So looks
9:07:079 hours, 7 minutes, 7 secondslike that is working perfectly fine. If it's not working for you, you can always manually uh do npm install and just have
9:07:159 hours, 7 minutes, 15 secondsit installed. That's actually what I did in the initial build of this project.
9:07:199 hours, 7 minutes, 19 secondsBut understanding the code more now I can see that all of these dependencies are actually maintained here. So I'm not sure it makes sense to install them
9:07:279 hours, 7 minutes, 27 secondsseparately when all of them live within this uh base code mirror configuration
9:07:349 hours, 7 minutes, 34 secondshere. All right. So now that we solved that mystery, let's go back inside of our suggestions index here. So I've just
9:07:439 hours, 7 minutes, 43 secondsimported code mirror from state. And while I'm here, I'm also going to add the following imports from code mirror
9:07:509 hours, 7 minutes, 50 secondsview decoration, decoration set, editor view, view plug-in, view update, widget
9:07:589 hours, 7 minutes, 58 secondstype, and keymap. All coming from code mirror forward slash view. So let's
9:08:059 hours, 8 minutes, 5 secondsstart by building something called set suggestion effect. Set suggestion effect
9:08:129 hours, 8 minutes, 12 secondsuses state effect and we simply define it first. So it can be a type of string or it can be null. I'm going to add a
9:08:209 hours, 8 minutes, 20 secondslittle comment here so you know what this is. State effect is a way to send messages to update our state. Think of
9:08:289 hours, 8 minutes, 28 secondsit like an action in a reducer if you've ever used Redux. and we define one effect type for setting the suggestion
9:08:359 hours, 8 minutes, 35 secondstext. Now the second thing we have to do is we have to define our suggestion state and that's going to use the state
9:08:449 hours, 8 minutes, 44 secondsfield dodeefine. Again it can be string or null. So I'm going to add some more comments here so it's easier to
9:08:529 hours, 8 minutes, 52 secondsunderstand what that does. State field holds our suggestion state in the editor. The create method which we're
9:08:599 hours, 8 minutes, 59 secondsgoing to build returns the initial value when the editor loads and the update method is called on every transaction.
9:09:069 hours, 9 minutes, 6 secondsTransaction is basically things like keystroke uh cursor changed I mean cursor position like this right every
9:09:149 hours, 9 minutes, 14 secondstime that happens we're going to call the update method and we will recomputee what the AI should suggest to
9:09:229 hours, 9 minutes, 22 secondspotentially update the value. So let's start with the create method because that's the uh simple one. And in here
9:09:309 hours, 9 minutes, 30 secondsfor now all we're going to do is just add to-do implement this because right now we don't really have anything
9:09:379 hours, 9 minutes, 37 secondsfunctional, right? We don't have any endpoints to call. And in the update we have value and transaction here. And in
9:09:469 hours, 9 minutes, 46 secondshere what we're going to do, we're going to check each effect in this transaction.
9:09:539 hours, 9 minutes, 53 secondsIf we find our set suggestion effect, we're going to return its new value.
9:10:019 hours, 10 minutes, 1 secondOtherwise, we're going to keep the current value unchanged. And we're going to do that using a for loop. For effect
9:10:099 hours, 10 minutes, 9 secondsof transaction effects, if effect is set suggestion effect, which we have defined above, simply return its value.
9:10:219 hours, 10 minutes, 21 secondsOtherwise, so outside of this for loop, return value. And let me go ahead and fix the typo. There we go. So you
9:10:299 hours, 10 minutes, 29 secondsshouldn't have any errors in the suggestion state nor in the set suggestion effect. So that is the simple
9:10:379 hours, 10 minutes, 37 secondsone done. You can see suggestion state is now fully functional here. Now the second one we have to add is the render plugin. So what's that going to serve?
9:10:489 hours, 10 minutes, 48 secondsWe currently implemented the state management for our suggestion text and we implement what's going to be in
9:10:559 hours, 10 minutes, 55 secondsfuture logic to update the current value. Right? So if I put my cursor here, AI will give me relevant
9:11:039 hours, 11 minutes, 3 secondsinformation about this. But if I change my cursor here, it's going to give me relevant information about this. That's what this is doing, right? And this
9:11:119 hours, 11 minutes, 11 secondsbasically just holds the state. But we don't actually render this anywhere. So that's what we are doing now. We need
9:11:199 hours, 11 minutes, 19 secondsour render plugin to render the ghost text. So let's go ahead and build that
9:11:269 hours, 11 minutes, 26 secondsconst render plugin uses view plugin from class and in here we have to define
9:11:349 hours, 11 minutes, 34 secondsa class. We have to give it decorations decoration set. So everything that I'm
9:11:419 hours, 11 minutes, 41 secondsadding here decoration set view plugin we've added all of those imports here. So make sure you have all of them.
9:11:489 hours, 11 minutes, 48 secondsGreat. We now have decoration set. Now let's go ahead and build a constructor that's going to initialize this dot
9:11:569 hours, 11 minutes, 56 secondsdecorations which we've defined above and it's going to use a build method which doesn't exist yet. We're going to create it and make sure to have the
9:12:049 hours, 12 minutes, 4 secondsproper props here. Now besides the constructor we're are going to have our update method here which is going to
9:12:139 hours, 12 minutes, 13 secondsaccept a view update. So basically what this function will do is it will rebuild
9:12:219 hours, 12 minutes, 21 secondsdecorations if the document has changed, cursor has moved or the suggestion has changed. So this one makes sure that a
9:12:309 hours, 12 minutes, 30 secondsnew AI uh suggestion is being created and this one ensures that it's being
9:12:379 hours, 12 minutes, 37 secondsshown again so it's not stale. Right? So that's the difference. This is the render plugin and this is the state
9:12:449 hours, 12 minutes, 44 secondsmanagement plugin. That's why I'm separating them. All right. So let's see if the suggestions have changed. We are
9:12:539 hours, 12 minutes, 53 secondsgoing to go through update.transactions transactions do sum find the transaction inside and I'm immediately returning transaction.
9:13:049 hours, 13 minutes, 4 secondsDo sum find the effect and immediately check effect is set suggestion effect.
9:13:139 hours, 13 minutes, 13 secondsAll right, now that we have that, we are going to finally check if update.doccument
9:13:219 hours, 13 minutes, 21 secondshas changed or if update selection set or if the suggestion from the AI model
9:13:299 hours, 13 minutes, 29 secondsis different. In any of those scenarios, we have to display something new to the user. Right? So, if I move the cursor
9:13:389 hours, 13 minutes, 38 secondshere, I have to update the render plug-in. If I move it here, I have to update it again. If the AI builds something new, I have to update it
9:13:469 hours, 13 minutes, 46 secondsagain. If I write something, I have to update the suggestion again. So, all of these scenarios are covered here. I just hope this is not confusing you. I'm not a big fan of this early returns, right?
9:13:589 hours, 13 minutes, 58 secondsSo, let me try and kind of rework this so it's easier to look at.
9:14:049 hours, 14 minutes, 4 secondsSo, basically like this suggestions change. Let me try expand it even more.
9:14:109 hours, 14 minutes, 10 secondsSuggestion changed. Upave transactions sum transaction. And then you can see I'm now opening a function. Return
9:14:189 hours, 14 minutes, 18 secondstransaction.xum effect. Open a new function. Return effect is set suggestion effect. Right?
9:14:259 hours, 14 minutes, 25 secondsSo this or this same thing. I just kind of feel like this is easier to read. I always find these very confusing. So whichever one you prefer, this or this.
9:14:389 hours, 14 minutes, 38 secondssame thing. All right. So, now uh that we have that, let's go ahead and do one more thing.
9:14:509 hours, 14 minutes, 50 secondsInstead of adding all of these in a big if clause, we can kind of separate them in a constant, right? So, should rebuild
9:14:589 hours, 14 minutes, 58 secondsand then the exact same thing that we have in our if clause and then we can just use should rebuild here. So should rebuild basically means rebuild the
9:15:069 hours, 15 minutes, 6 secondsdecorations if the document has changed, cursor has moved or suggestion itself has changed. I feel like this is easier
9:15:149 hours, 15 minutes, 14 secondsto understand, right? I know this is a very new syntax, right? I doubt any of you was building uh code mirror
9:15:229 hours, 15 minutes, 22 secondsextensions. So I'm trying to make it as primitive as possible uh so it's easy to follow along, right? I don't want you to just blindly follow me. I want you to
9:15:309 hours, 15 minutes, 30 secondsunderstand what we're doing. So that was the update method and now we have to build this build method that's currently
9:15:369 hours, 15 minutes, 36 secondsunderlined uh red. So let's build we get the view which is a type of editor view
9:15:469 hours, 15 minutes, 46 secondsand what we have to currently do is get the current suggestion from the state.
9:15:529 hours, 15 minutes, 52 secondsSo const suggestion view state field suggestion state
9:15:599 hours, 15 minutes, 59 secondswhich is our state from above. If there is no suggestion return decoration do
9:16:059 hours, 16 minutes, 5 secondsnone. And now what we have to do is we have to create a widget decoration at
9:16:129 hours, 16 minutes, 12 secondsthe cursor position. So first let's get the cursor. You can do that using view
9:16:189 hours, 16 minutes, 18 secondsstate selection main head and then return decoration set. So now we're going to display
9:16:279 hours, 16 minutes, 27 secondssomething and that's basically going to be a decoration. Whoops, not an object, an array.
9:16:349 hours, 16 minutes, 34 secondsDecoration dot vidget. Pass in the vidget. New suggestion.
9:16:429 hours, 16 minutes, 42 secondsOops. Suggestion vidget and pass in the suggestion.
9:16:489 hours, 16 minutes, 48 secondsUh now we also have to build the suggestion widget. That's one thing uh I've missed. My apologies. And it's
9:16:579 hours, 16 minutes, 57 secondsgoing to be super simple. Basically, we can also write this directly here, but I just want to keep it separate. What we're doing now in the build here is
9:17:059 hours, 17 minutes, 5 secondsjust telling the decoration, okay, now finally show this to the user, right?
9:17:119 hours, 17 minutes, 11 secondsUser should now see this. So, let's keep this red for now. And let's just pass in side to be one. So, what does side
9:17:199 hours, 17 minutes, 19 secondsrepresent? It basically means render this after cursor not before which would
9:17:279 hours, 17 minutes, 27 secondsbe minus one. Right? So if my cursor is here, this is where I expect my AI suggestion to arrive. And let's also chain dot range cursor.
9:17:389 hours, 17 minutes, 38 secondsSo this should be the only uh uh red underlined thing here. And we're not just done yet. So after this last curly
9:17:469 hours, 17 minutes, 46 secondsbracket right here, open another set of objects, add decorations,
9:17:539 hours, 17 minutes, 53 secondsget plugin, and execute plug-in dot decorations. And this basically tells the code mirror to use our decorations.
9:18:049 hours, 18 minutes, 4 secondsAll right. Now, let's go ahead and let's build the suggestion widget. So I'm going to do that right above uh our
9:18:139 hours, 18 minutes, 13 secondsrender plugin here. So class suggestion widget extends widget type
9:18:219 hours, 18 minutes, 21 secondsand in here let's simply define a constructor readonly text and call and execute super
9:18:309 hours, 18 minutes, 30 secondsthen go ahead and call to DOM. So what are we writing to DOM? Well, an element,
9:18:379 hours, 18 minutes, 37 secondsa span element. And the span text content will be whatever we pass along
9:18:449 hours, 18 minutes, 44 secondsfrom the build function. And you can see that that is basically going to be the suggestion, right? So, whatever we
9:18:529 hours, 18 minutes, 52 secondsmanage to extract from the suggestion field, we're now going to add to this span element. Now, let's go ahead and make this ghost text appearance by
9:19:009 hours, 19 minutesgiving it an opacity. Let's make sure this doesn't interfere with clicks. So it has the real kind of uh unobstructed
9:19:089 hours, 19 minutes, 8 secondsfeeling. And let's return a span just like that. And we can add some comment at the top of the class widget here.
9:19:179 hours, 19 minutes, 17 secondsWidget type creates custom DOM elements to display in the editor. To do DOM is called by code mirror to create an
9:19:239 hours, 19 minutes, 23 secondsactual HTML element. There we go. Uh and now let's go ahead and yes, the file
9:19:319 hours, 19 minutes, 31 secondsname is still unused because we're going to need it later. Let's actually go inside of components code editor here
9:19:389 hours, 19 minutes, 38 secondsand let's import suggestion from extensions suggestion and let's try
9:19:459 hours, 19 minutes, 45 secondsit out. So don't expect too much right but it should when you hover somewhere.
9:19:529 hours, 19 minutes, 52 secondsSo let me find something where I have some code wherever your cursor is you should have hardcoded to-do implement this and it shouldn't interfere at all.
9:20:039 hours, 20 minutes, 3 secondsRight? But you can see how it rerenders exactly where I put my cursor or
9:20:109 hours, 20 minutes, 10 secondswhenever I type. Right? So that's what all of those updates are doing. They are keeping track that we have a new display
9:20:199 hours, 20 minutes, 19 secondsof our ghost text suggestion. Obviously right now it's not very intelligent, right? It's just going to add this
9:20:269 hours, 20 minutes, 26 secondseverywhere. But I wanted to introduce you to building extensions through this very primitive, easy way. I feel like
9:20:339 hours, 20 minutes, 33 secondsit's easier to digest it this way rather than just building the entire thing and you just building along with me without understanding what we're actually doing.
9:20:439 hours, 20 minutes, 43 secondsSo that was the suggestion state and that was the render plugin. How about we make it even better by adding the accept
9:20:529 hours, 20 minutes, 52 secondssuggestion keymap plugin. And that's pretty easy actually. So that is tab to accept right because right now uh we can
9:21:029 hours, 21 minutes, 2 secondssee the suggestion but there's no way of accepting it. So I'm going to go ahead right here and I'm going to build it. So
9:21:109 hours, 21 minutes, 10 secondsconst accept suggestions keymap is keymap off.
9:21:159 hours, 21 minutes, 15 secondsGo ahead and find the tab key run view.
9:21:239 hours, 21 minutes, 23 secondsLet's go ahead and find the suggestion using view state field and suggestion state from above. If there is no
9:21:319 hours, 21 minutes, 31 secondssuggestion, let me go ahead and copy it. In that case, we simply return false. Basically,
9:21:389 hours, 21 minutes, 38 secondsthat means no suggestion found. Let tab do its normal thing, which in our case will be to indent.
9:21:509 hours, 21 minutes, 50 secondsOtherwise, if suggestion was found, let's go ahead and find the cursor position. And then let's go ahead and let's call view.ispatch.
9:22:019 hours, 22 minutes, 1 secondAnd inside of view.dispatch, first things first, insert the suggestion text. So changes from cursor
9:22:109 hours, 22 minutes, 10 secondsinsert suggestion. Insert the suggestion text. Then let's move the cursor to the
9:22:179 hours, 22 minutes, 17 secondsend of the suggestion length. Right? So we have to move our cursor now after we've accepted that new thing. And finally we have to clear the suggestion.
9:22:309 hours, 22 minutes, 30 secondsSo we simply call set suggestion effect of null. And last thing return true which means we handled tab don't indent.
9:22:409 hours, 22 minutes, 40 secondsWe are kind of overwriting the native tab functionality. Well, not exactly
9:22:469 hours, 22 minutes, 46 secondsnative but uh which is the one keymap indent with tab right we are overwriting
9:22:539 hours, 22 minutes, 53 secondsthis. So now if we've done this correctly when you hit tab you can see
9:23:019 hours, 23 minutes, 1 secondthis is actually inserted now right try refreshing after that suggestion is lost so you need to
9:23:089 hours, 23 minutes, 8 secondsrefresh. So try you know going somewhere like this and press tab and you can see it's inserted now. So we are
9:23:159 hours, 23 minutes, 15 secondssuccessfully accepting a suggestion. The problem is suggestion right now is quite dumb right it doesn't do anything. It
9:23:249 hours, 23 minutes, 24 secondshas no idea where we are. It has no context. It doesn't do any AI stuff. But this is kind of the simplest extension I could think of to help you build this.
9:23:359 hours, 23 minutes, 35 secondsSo now it's time to go uh to stage two.
9:23:399 hours, 23 minutes, 39 secondsIn stage two, we start differently. So let's go ahead. Where am I? Uh all the
9:23:469 hours, 23 minutes, 46 secondsway to the suggestion state. In stage two, instead of returning a pre-made string, we are going to start with null,
9:23:569 hours, 23 minutes, 56 secondsright? So we start with null because we aren't going to have anything in the beginning. Uh, and then we have to
9:24:059 hours, 24 minutes, 5 secondscreate something called debouncing and suggestion generation.
9:24:129 hours, 24 minutes, 12 secondsSo I'm just trying to find a proper place to do this. So I'm going to do it after the suggestion widget here. So
9:24:189 hours, 24 minutes, 18 secondsstage two will basically be creating the debounce functionality.
9:24:249 hours, 24 minutes, 24 secondsStart with debounce timer which can be a number or null. By default, null is waiting for suggestion will be false and debounce delay will be 300.
9:24:369 hours, 24 minutes, 36 secondsNow what we have to do is we have to build a fake suggestion. So still no AI
9:24:429 hours, 24 minutes, 42 secondscalls yet. Let's just do generate fake suggestion.
9:24:499 hours, 24 minutes, 49 secondsText before cursor will be one thing we're going to accept. So now we're building a kind of more advanced text
9:24:569 hours, 24 minutes, 56 secondssuggestions simply because we will have some information for example like text before cursor and we're going to trim
9:25:059 hours, 25 minutes, 5 secondsthat. So whatever we have passed here trim the end and then let's just check for example if trimmed ends with
9:25:149 hours, 25 minutes, 14 secondsconstant return my variable. So if I start typing const text will suggest my variable right. So
9:25:239 hours, 25 minutes, 23 secondssomewhat smarter, right? We're just learning how it works. And you can add as many examples here. It doesn't really matter. You don't have to add all of
9:25:319 hours, 25 minutes, 31 secondsthese. I'm just adding them so it's easier to understand the state of our current app. And last return null here.
9:25:409 hours, 25 minutes, 40 secondsSo we are mocking suggestions. We are making them up. We're kind of pretending how AI is going to behave.
9:25:499 hours, 25 minutes, 49 secondsNow down here, let's go ahead uh and let's create the debounce plugin.
9:25:559 hours, 25 minutes, 55 secondsSo let's create create debounce plugin which accepts file name and return view plugin dot
9:26:049 hours, 26 minutes, 4 secondsfrom class. And let's go ahead and define the class here again. So we're going to have a constructor a view type
9:26:139 hours, 26 minutes, 13 secondsof editor view calling this dot trigger suggestion with the view. Then besides
9:26:219 hours, 26 minutes, 21 secondsthe constructor we're going to again have an update which accepts update which is a type of a view update. If
9:26:299 hours, 26 minutes, 29 secondsdocument has changed or selection has set, call this dot trigger suggestion
9:26:369 hours, 26 minutes, 36 secondsand pass along update dot view. And then finally, let's go ahead and let's implement the trigger suggestion here.
9:26:459 hours, 26 minutes, 45 secondsSo this accepts the editor view. And first things first, if an existing debounce timer exists, let's clear it.
9:26:539 hours, 26 minutes, 53 secondsSo this is our debounce protection. Now let's go ahead and change the variable is waiting from suggestion to be true.
9:27:019 hours, 27 minutes, 1 secondAnd now in here I'm going to define my debounce timer to be window set timeout
9:27:089 hours, 27 minutes, 8 secondsasynchronous method. And in here let's go ahead and do uh a fake suggestion.
9:27:169 hours, 27 minutes, 16 secondsAnd I'm going to just add a little parenthesis here. Delete this block later in stage three. So this is now
9:27:239 hours, 27 minutes, 23 secondsstage two, right? So let's go ahead and start by seeing where is our cursor.
9:27:309 hours, 27 minutes, 30 secondsThen let's go ahead and do what line we are currently at. And let's find text
9:27:389 hours, 27 minutes, 38 secondsbefore cursor line text slice starting from zero and going to cursor minus line.
9:27:469 hours, 27 minutes, 46 secondsAnd then we are going to generate a fake suggestion using this text before cursor. So this will return something
9:27:549 hours, 27 minutes, 54 secondsright it will either return my variable my function log or null. We are kind of learning what AI will be doing uh in
9:28:039 hours, 28 minutes, 3 secondsthis example. So right now this is just well fake. Let's now change is waiting
9:28:089 hours, 28 minutes, 8 secondsfor suggestion back to false. Let's call view dispatch effects set suggestion
9:28:189 hours, 28 minutes, 18 secondseffect do off suggestion like so. And in here add a debounce
9:28:269 hours, 28 minutes, 26 secondsdelay which we have defined above. Looks like we are still not uh using this is
9:28:339 hours, 28 minutes, 33 secondswaiting for suggestion anywhere but we will uh later. for now. Let's go ahead
9:28:409 hours, 28 minutes, 40 secondsand just finish this. So after debounce delay and after this function here, let
9:28:479 hours, 28 minutes, 47 secondsme see. I'm trying to figure out where am I. So this is a class. Uh let's just see.
9:28:559 hours, 28 minutes, 55 secondsI think we should do it here. Destroy. Let me see.
9:29:029 hours, 29 minutes, 2 secondsIs that working here? If debounce timer is not null, clear time out debounce timer.
9:29:129 hours, 29 minutes, 12 secondsAll right, I'm trying to figure out if I did this in the correct indentation. So this ends the trigger suggestion and
9:29:209 hours, 29 minutes, 20 secondsafter that we call destroy. I think this should work uh just fine.
9:29:269 hours, 29 minutes, 26 secondsNow that we have this create debounce plugin, let's go inside of the render plugin right here. uh update is fine as
9:29:359 hours, 29 minutes, 35 secondsis but build should be modified now. So what we're going to do here is we're
9:29:429 hours, 29 minutes, 42 secondsgoing to call if is waiting for suggestion return decoration
9:29:509 hours, 29 minutes, 50 secondsnone. So if the suggestion is currently uh in process of being created do not
9:29:579 hours, 29 minutes, 57 secondsreturn anything. So that's one thing we have to do. And then let's go down here
9:30:079 hours, 30 minutes, 7 secondsto our export con suggestion. And it should be a little bit different now. So we should still have the suggestion
9:30:149 hours, 30 minutes, 14 secondsstate, but we should also now have create debounce plugin and pass in the
9:30:209 hours, 30 minutes, 20 secondsfile name like this. So what that's going to do is it will trigger
9:30:279 hours, 30 minutes, 27 secondssuggestions on typing. So if we've done this correctly, I'm just going to do a
9:30:349 hours, 30 minutes, 34 secondsquick check through the code. If we've done this correctly, uh we now should not see the default suggestion. Only
9:30:449 hours, 30 minutes, 44 secondswhen we start typing something. Uh more specifically, only when we start typing. And yes, file
9:30:519 hours, 30 minutes, 51 secondsname is still unused. That's fine. So, let me find where is the generate suggestion function. I'm trying to find
9:30:599 hours, 30 minutes, 59 secondsit. So, if you type const, you should get my variable uh back. Or if you type function or console or return. Let's try
9:31:089 hours, 31 minutes, 8 secondsall of them here. So, I'm going to go ahead at the bottom of the file. I can see that no suggestion is happening on
9:31:169 hours, 31 minutes, 16 secondscursor change. Good. If I type gibberish, nothing is happening. But if I type const, there we go. I get my
9:31:239 hours, 31 minutes, 23 secondsvariable. If I get function, I get my function. If I add return, I get null.
9:31:299 hours, 31 minutes, 29 secondsIf I write console, does it work? Is it console? Oh, it's
9:31:369 hours, 31 minutes, 36 secondsconsole dot. Okay, console dot I can see out the suggestion for log. So, yes,
9:31:449 hours, 31 minutes, 44 secondsobviously it's working. Perfect. Um, now the biggest problem is it's still not
9:31:509 hours, 31 minutes, 50 secondscalling any AI. This is all still just fake. So what we have to do now is we
9:31:589 hours, 31 minutes, 58 secondshave to start building the actual uh endpoint for this because the AI suggestion cannot work without calling an endpoint.
9:32:099 hours, 32 minutes, 9 secondsSo in order to build that let's go inside of source app folder API and in here I'm going to build suggestion and inside let's add route.ts.
9:32:229 hours, 32 minutes, 22 secondsLet's start by preparing some imports such as generate text and output from AI. Let's go ahead and import next
9:32:309 hours, 32 minutes, 30 secondsresponse from next server. Let's go ahead and import
9:32:359 hours, 32 minutes, 35 secondsZ from zod. and then import your provider for example anthropic not from
9:32:449 hours, 32 minutes, 44 secondsingest from AI SDK anthropic or Google from AIS SDK Google. So whichever one
9:32:539 hours, 32 minutes, 53 secondsyou chose to use. Now we have to build the suggestion schema which is going to be a zod object which accepts a single
9:33:029 hours, 33 minutes, 2 secondsproperty called suggestion. It's a type of string and we describe it as the code to insert at cursor or empty string if
9:33:119 hours, 33 minutes, 11 secondsno completion is needed. Now what we have to do is we have to build the suggestion prompt suggestions.
9:33:209 hours, 33 minutes, 20 secondsSuggestion prompts are always kind of tricky and it definitely makes no sense to type it out here. So you can just go ahead and visit the Polaris assets folder uh using the link on the screen.
9:33:339 hours, 33 minutes, 33 secondsAnd in here I have prepared uh first of all uh you can find both my suggestion
9:33:419 hours, 33 minutes, 41 secondsextension here and the fetcher. So if you don't want to go through me going through these stages of the suggestion,
9:33:479 hours, 33 minutes, 47 secondsyou can just find the full code here. Uh but if you are going along with me, you need the prompt. So here it is, the
9:33:569 hours, 33 minutes, 56 secondssuggestion prompt. It's not really any magical. I just kind of built it and changed it until it works. So you can see later we also have another prompt
9:34:049 hours, 34 minutes, 4 secondshere but for now uh this is the one we want. So let's just add suggestion prompt. You are a code suggestion
9:34:129 hours, 34 minutes, 12 secondsassistant. And what I'm using here is XML type of syntax because that works
9:34:199 hours, 34 minutes, 19 secondsvery well with anthropic. I have no idea how well it works with Google. In fact, I don't know what works well with Google
9:34:269 hours, 34 minutes, 26 secondsproviders. If you know, feel free to change this and alter it. ask Gemini to kind of modify this prompt for Gemini.
9:34:369 hours, 34 minutes, 36 secondsUh but for anthropic, this works great.
9:34:399 hours, 34 minutes, 39 secondsIt's basically instructing it what it is. Feel free to use this prompt for Gemini. I think it should work just fine. Now let's export asynchronous function post. We get a request.
9:34:529 hours, 34 minutes, 52 secondsLet's go ahead and open try. And let's also prepare a catch here.
9:35:009 hours, 35 minutesSo in here I've started extracting some things and that's the following file name code current line previous line
9:35:109 hours, 35 minutes, 10 secondsuh previous lines text before cursor text after cursor next lines and line number all from await request.json.
9:35:209 hours, 35 minutes, 20 secondsAnd if we don't have the code, which is the most important part of this request, we're simply going to go ahead and throw
9:35:289 hours, 35 minutes, 28 secondsa next response JSON with an error code is required and pass along a status of 400. Meaning whatever came from the
9:35:379 hours, 35 minutes, 37 secondsfront end is not good. We cannot work with that. Now what we have to do is we have to
9:35:449 hours, 35 minutes, 44 secondscreate a prompt from the suggestion prompt by replacing file name to be the actual file name. Then we have to
9:35:549 hours, 35 minutes, 54 secondsreplace code to be actual code and then the exact same thing for all other things. Current line for current line,
9:36:029 hours, 36 minutes, 2 secondsprevious lines for previous lines or fall back to an empty string. text before cursor, text after cursor, next
9:36:109 hours, 36 minutes, 10 secondslines or fall back to this and line to number. Make sure you transform it to string. So this is the prompt. Do you
9:36:199 hours, 36 minutes, 19 secondsneed all of these? Probably not. You can maybe just do I don't know text before cursor. I'm just the more context you
9:36:279 hours, 36 minutes, 27 secondsgive it, the better it's going to perform obviously, right? But you can do fun things with just code and file name,
9:36:339 hours, 36 minutes, 33 secondsright? But I think at least current line and text before cursor I'd say like these ones are the most important ones.
9:36:459 hours, 36 minutes, 45 secondsSo otherwise how does it know what to even suggest you right and now that we have our prompt we can go ahead and
9:36:539 hours, 36 minutes, 53 secondscreate this output using await generate text model. Now in here it's going to be anthropic or it's going to be Google.
9:37:019 hours, 37 minutes, 1 secondAnd if it's going to be Google, you obviously have to give it whatever model you're using. For example, Gemini 2.0
9:37:099 hours, 37 minutes, 9 secondsflash. Output.object schema suggestion schema and prompt. And let's return next response.json uh suggestion.
9:37:219 hours, 37 minutes, 21 secondsSo this is important, right? what you respond is important because that's what we're going to look at at the front end and simply pass in my apologies output.uggestion.
9:37:329 hours, 37 minutes, 32 secondsSo you can see this is hardcoded suggestion. I mean this is typed suggestion. Why? Because we gave it uh where is it? We gave it an output.
9:37:439 hours, 37 minutes, 43 secondsRight? So right here we have the suggestion schema which accepts a suggestion. So when we pass that here,
9:37:519 hours, 37 minutes, 51 secondssuggestion schema, it knows that's what it has to return. So I'm not sure if this is the proper Google model to use.
9:37:589 hours, 37 minutes, 58 secondsI will try with Google first because I know a lot of you are using the free API key, but then later I will switch to anthropic simply because the results are
9:38:079 hours, 38 minutes, 7 secondsmuch better. But I think we should get some fun results with Google one as well. Uh and let's also just catch the error, right? If we do have an error,
9:38:159 hours, 38 minutes, 15 secondslet's console dot error suggestion error and let's pass the error and let's
9:38:239 hours, 38 minutes, 23 secondsreturn next response.json with an error failed to generate suggestion.
9:38:359 hours, 38 minutes, 35 secondsThis will also get logged to sentry. So no worries. Let's go ahead and end it like this.
9:38:439 hours, 38 minutes, 43 secondsThere we go. So that is our end point.
9:38:479 hours, 38 minutes, 47 secondsWe can comment out and drop it now. So that is our end point for suggestions.
9:38:529 hours, 38 minutes, 52 secondsWhat we have to do now is we have to create a fetcher. So uh we can do this in a very very simple way. But I just
9:38:599 hours, 38 minutes, 59 secondslike some level of type safety when it comes to you know calling these things.
9:39:049 hours, 39 minutes, 4 secondsSo to make it easier and less errorprone, I'm going to go inside of features editor extensions suggestion and in here I'm going to create fetcher.ts.
9:39:139 hours, 39 minutes, 13 secondsts and in here let's go ahead and install a package called KY.
9:39:219 hours, 39 minutes, 21 secondsSo KY is like a lightweight alternative to fetch and Axios maybe
9:39:289 hours, 39 minutes, 28 secondsspecifically Axio. It's not an alternative to fetch. It probably definitely uses fetch inside. Uh but yes, like a lightweight alternative to
9:39:379 hours, 39 minutes, 37 secondsAxios. So let's go ahead and install import ky from KY. Uh and let's import Z
9:39:459 hours, 39 minutes, 45 secondsfrom zod. And now what we're going to do is we're going to create the suggestion request schema using zod. So what is
9:39:559 hours, 39 minutes, 55 secondsthis? Well, remember how we had route.ts in here? We had all of this. So now we
9:40:049 hours, 40 minutes, 4 secondshave to validate all of them here in this object. So let's go ahead and create that. File name is a string. Code is a string. Current line is a string.
9:40:139 hours, 40 minutes, 13 secondsPrevious lines. Text before cursor. Text after cursor. Next lines and line number which is a type of number. And we also have to uh define what do we get back?
9:40:269 hours, 40 minutes, 26 secondsWell, a very simple suggestion which is a type of string. So let's define that.
9:40:299 hours, 40 minutes, 29 secondsSuggestion response schema is an object with a string back. Now we can go ahead and infer from those zod definitions to
9:40:399 hours, 40 minutes, 39 secondscreate actual types. So z.infer type of suggestion request schema and suggestion response schema. And now we have nice
9:40:459 hours, 40 minutes, 45 secondstypes which we can use here. Now let's export const fetcher. It's an asynchronous method which accepts a
9:40:529 hours, 40 minutes, 52 secondspayload which is a suggestion request and a signal which offers the option to abort signal. We can use that in case
9:41:019 hours, 41 minutes, 1 secondthe user starts typing again. So we can easily abort the request we just started to create and thus we can save some
9:41:109 hours, 41 minutes, 10 secondstokens so we don't create unnecessary uh AI things. Right? Let's open a try and catch here. And the first thing we're
9:41:189 hours, 41 minutes, 18 secondsgoing to do is we're going to validate the payload. So validated payload is suggestion request schema.parse
9:41:269 hours, 41 minutes, 26 secondspayload. So if whatever we pass to this fetcher function doesn't pass this, we're simply going to throw an error.
9:41:349 hours, 41 minutes, 34 secondsAnd now let's go ahead and get the response by doing await ky.post/
9:41:409 hours, 41 minutes, 40 secondsAPI slash suggestion json validated payload.
9:41:489 hours, 41 minutes, 48 secondsPass in the signal timeout is 10,000 and retry will be zero. And let's go ahead
9:41:559 hours, 41 minutes, 55 secondsand chain JSON and execute it and give JSON a type of suggestion
9:42:049 hours, 42 minutes, 4 secondsresponse. So we know exactly what we're getting back. And then let's do const validated response suggestion response
9:42:129 hours, 42 minutes, 12 secondsschema.parse response. So we do another check. Did we get back what we expect to get back? And
9:42:209 hours, 42 minutes, 20 secondsthen finally return validated response.suggest. suggestion like so uh
9:42:279 hours, 42 minutes, 27 secondsor if we don't we can get null but I think we should always do it um you can leave it like this it should be fine
9:42:359 hours, 42 minutes, 35 secondsso in the catch the only thing that's important is to differentiate if the error is because we cancelled it with
9:42:419 hours, 42 minutes, 41 secondsthe abort signal so if we did so if error is an instance of error and error name is abort error don't do anything
9:42:499 hours, 42 minutes, 49 secondsjust return null otherwise return null as Great. So now while I'm here, I also
9:42:579 hours, 42 minutes, 57 secondswant to import toast from Soner. We already have Soner installed. It comes with Shats CNN UI. You can see 2.0.7.
9:43:079 hours, 43 minutes, 7 secondsAnd I just want to throw an error here. Toast.
9:43:139 hours, 43 minutes, 13 secondsFailed to fetch AI completion simply so the user is aware this is not working.
9:43:199 hours, 43 minutes, 19 secondsBut in order for the toast to work, we have to quickly revisit not the environment file, the app file layout
9:43:289 hours, 43 minutes, 28 secondsfile right here. And let's just add toaster from components UI soner like this. And let's just move it here.
9:43:409 hours, 43 minutes, 40 secondsThat's it. That's all we have to do.
9:43:429 hours, 43 minutes, 42 secondsGreat. So that is the fetcher. But now what we have to do is we have to implement stage three. So let's go ahead
9:43:519 hours, 43 minutes, 51 secondsinside of features editor extensions suggestion index.ts.
9:43:589 hours, 43 minutes, 58 secondsSo what should we do first? Well, we should import our fetcher. So let's go
9:44:059 hours, 44 minutes, 5 secondsahead and go at the top here and import fetcher from dot /fetcher right here.
9:44:159 hours, 44 minutes, 15 secondsUh once we have the fetcher uh we should start doing some changes. So we no
9:44:229 hours, 44 minutes, 22 secondslonger need the generate fake suggestion. We can get rid of that. But uh let me just add to-do
9:44:309 hours, 44 minutes, 30 secondsclean up this fake function because it is fake, right? It's not doing anything.
9:44:359 hours, 44 minutes, 35 secondsIt's pretending it's AI. And now we are going to have uh a proper AI method. So
9:44:449 hours, 44 minutes, 44 secondslet's start by doing const generate payload. And that will accept a view
9:44:519 hours, 44 minutes, 51 secondseditor view and a file name which is a string.
9:44:589 hours, 44 minutes, 58 secondsAnd now let's go ahead and start by getting the entire code. So view state document to string. That's the entire code. There's a chance the code is
9:45:069 hours, 45 minutes, 6 secondscompletely empty. So if there is no code or when we trim the code the length is zero, return null. No reason to make an API request over something that small.
9:45:179 hours, 45 minutes, 17 secondsNow let's go ahead and define the cursor position using view state selection main head. Then let's go ahead and let's get the current line using view state
9:45:269 hours, 45 minutes, 26 secondsdocument line at cursor position. Then let's go ahead and get cursor in line which means cursor position minus the
9:45:349 hours, 45 minutes, 34 secondscurrent line dot from. Now let's go ahead and get the last five previous
9:45:419 hours, 45 minutes, 41 secondslines. So prepare an array like this. So we're going to get five of them.
9:45:469 hours, 45 minutes, 46 secondsPrevious lines to fetch math minimum five and then current line number minus one. And then in here we're going to do
9:45:559 hours, 45 minutes, 55 secondsa simple for loop to achieve that for let I be a previous lines to fetch I is
9:46:039 hours, 46 minutes, 3 secondsgreater or equal than one and simply go down to zero. I mean to one uh and
9:46:119 hours, 46 minutes, 11 secondsprevious lines and then for each line that you find go ahead and push it to the previous lines array. So view state
9:46:189 hours, 46 minutes, 18 secondsdo line and we find it using current number minus the current iterator I do.ext
9:46:269 hours, 46 minutes, 26 secondsa bit complicated so pause and make sure you write it correctly. And then we do a very very similar thing uh for next
9:46:349 hours, 46 minutes, 34 secondslines. Right? So first let's find the total lines using view state document lines. Then let's go ahead and define uh
9:46:439 hours, 46 minutes, 43 secondswhich lines we should fetch next. So math min five total lines minus the current line dot number. And then again
9:46:519 hours, 46 minutes, 51 secondswe do a for loop here with the iterator starting from one being less or or equal than lines to fetch and increasing.
9:46:599 hours, 46 minutes, 59 secondsRight? So then we do kind of the opposite thing. In here we went uh up and in here we went and we go down but the logic you can see it highlights it's
9:47:089 hours, 47 minutes, 8 secondsexactly the same except this is plus the iterator and this is going minus the iterator and the logic is in reverse.
9:47:159 hours, 47 minutes, 15 secondsThis is I minus minus and this is I ++.
9:47:189 hours, 47 minutes, 18 secondsSo just be mindful of that. You can always pause to double check or if you're just unsure, you can always use
9:47:249 hours, 47 minutes, 24 secondsthe assets here to just see the complete suggestion uh extension
9:47:319 hours, 47 minutes, 31 secondshow it looks in its final form. I will share that with you again later. And you also have the fetcher just in case since I know this is a bit complicated and
9:47:409 hours, 47 minutes, 40 secondsit's an important feature. I want you to have it working. So I'm I'm going to make sure that you have the answer. All
9:47:479 hours, 47 minutes, 47 secondsright. And now what we have to do is we have to return all of those things. So things like file name code is simple but
9:47:559 hours, 47 minutes, 55 secondsthen we get to a bit more complicated things. For example, current line will be uh current line.ext.
9:48:029 hours, 48 minutes, 2 secondsPrevious lines is an array. So we are using previous lines.join with a page break like this. So we are preparing
9:48:109 hours, 48 minutes, 10 secondsthis for AI consumption. Text before cursor is current line.ext Text slice starting from zero and going to cursor
9:48:189 hours, 48 minutes, 18 secondsin line. Text after cursor is current line text slice cursor in line. Next
9:48:259 hours, 48 minutes, 25 secondslines in is an array again. So we join it using page break. And finally we have the line number which is current line dot number.
9:48:359 hours, 48 minutes, 35 secondsUh great. So now let's go ahead inside of create debounce plugin. And now after
9:48:429 hours, 48 minutes, 42 secondswe do trigger suggestion here, after we do this,
9:48:499 hours, 48 minutes, 49 secondslet's go ahead and do an abort controller. Uh, so let me just see.
9:48:569 hours, 48 minutes, 56 secondsOkay, how we have to go right here. Let's go. Let's go above generate payload.
9:49:049 hours, 49 minutes, 4 secondsActually, let me just I'm trying to find the best place to do this. I want to do it here with a debounce timer. So just
9:49:119 hours, 49 minutes, 11 secondshere go ahead and add let current abort controller to be a type of abort
9:49:169 hours, 49 minutes, 16 secondscontroller or null and default it to null like so.
9:49:249 hours, 49 minutes, 24 secondsAnd now let's go ahead let me see aboard controller exists.
9:49:339 hours, 49 minutes, 33 secondsLet's go ahead and use it down here in the create debounce plugin.
9:49:409 hours, 49 minutes, 40 secondsSo after trigger suggestion, I started to leave some space here. So if current
9:49:469 hours, 49 minutes, 46 secondsabort controller is not null, call current abort controller.abort.
9:49:559 hours, 49 minutes, 55 secondsUh it seems like I'm having some problem here. Abort does not exist on type never. So let me quickly check what that's about.
9:50:039 hours, 50 minutes, 3 secondsI think this is perfectly fine. It's because we never actually give it a type of abort controller. So it's confused
9:50:109 hours, 50 minutes, 10 secondsabout what it has to abort and we do that here. So this is a fake suggestion.
9:50:159 hours, 50 minutes, 15 secondsSo we can delete this block and we are now in stage three. So uh okay, let's
9:50:229 hours, 50 minutes, 22 secondsdelete this entirely and just leave this and instead we're going to add payload
9:50:309 hours, 50 minutes, 30 secondsusing generate payload. the method we defined above which accepts the view and the file name which we pass in here. So we have access to view from trigger
9:50:389 hours, 50 minutes, 38 secondssuggestion and file name from the created debounce plug-in here. Awesome.
9:50:449 hours, 50 minutes, 44 secondsSo that's the first thing and now we have to check if there is no payload.
9:50:539 hours, 50 minutes, 53 secondsWe have to switch is waiting for suggestion back to false and we have to
9:50:599 hours, 50 minutes, 59 secondsupdate our view dispatch and set suggestion effect of null. And then let's go ahead and do an early return.
9:51:109 hours, 51 minutes, 10 secondsAnd then outside of this if clause assign to the current abort controller to be new abort controller.
9:51:209 hours, 51 minutes, 20 secondsAnd then finally the new suggestion will come from await fetcher payload and pass in current
9:51:299 hours, 51 minutes, 29 secondsabboard controller signal here. So basically it's going to accept two things. the payload which we generate
9:51:389 hours, 51 minutes, 38 secondsand the current abort signal and in here is waiting for suggestion is again false. The view dispatch is exactly the
9:51:469 hours, 51 minutes, 46 secondssame. Uh very good. Okay. Now the what's missing is in the destroy method here.
9:51:539 hours, 51 minutes, 53 secondsSo we should also besides doing the debounce check we also have to check if current abort controller is not null.
9:52:019 hours, 52 minutes, 1 secondLet's make sure to abort it so we don't have any memory uh leaks. Uh great. So
9:52:089 hours, 52 minutes, 8 secondsnow I am just checking you know is there anything important I've missed here? And I think this might be it. Uh let me see
9:52:179 hours, 52 minutes, 17 secondswhat is the warning about here. Generate fake suggestion. Yeah, we no longer need it. We can remove generate fake suggestion. We can keep all of these closed together and let's check it out.
9:52:299 hours, 52 minutes, 29 secondsSo again, I have no idea if it's going to work the first try simply because I'm I set up to use Gemini and I'm never familiar with their code. So let try
9:52:389 hours, 52 minutes, 38 secondshave some try picking something like this, right? Or you can just copy one of your components. So if I just go ahead and add on
9:52:479 hours, 52 minutes, 47 secondssomething. Let's see if it will give me any suggestion or it gives me an error.
9:52:559 hours, 52 minutes, 55 secondsOkay, I think this is an error because of an invalid model. This happens almost every single time, but at least the toaster is working on failed to fetch a
9:53:049 hours, 53 minutes, 4 secondscompletion. So, I'm going to go to aisdk.dev simply because I want to show you how I fix problems like this. I mean, this
9:53:119 hours, 53 minutes, 11 secondsonly happens with Gemini for me to like no one else. Let me go ahead and try going inside of providers
9:53:209 hours, 53 minutes, 20 secondsand I'm going to try and find uh where is Google? Here it is. Google generative AI.
9:53:329 hours, 53 minutes, 32 secondsWhat do they use? Gemini 2.5 flash. Okay.
9:53:389 hours, 53 minutes, 38 secondsI don't know why this is like that. So, uh let's go inside of app folder API suggestion. Also, make sure you you know
9:53:479 hours, 53 minutes, 47 secondsyou can see suggestion here and in here API suggestion. Make sure you didn't accidentally misspell the folder name.
9:53:539 hours, 53 minutes, 53 secondsIt should be inside of API and it should have route. So, I'm going to change this to be 2.5 flash. Maybe we'll have more
9:54:029 hours, 54 minutes, 2 secondsluck then. Let me refresh again. Let me go inside of this one. Let me write on
9:54:109 hours, 54 minutes, 10 secondschange to and will it auto suggest something or not? There we go. It works.
9:54:179 hours, 54 minutes, 17 secondsIf I start writing const. Let's see.
9:54:209 hours, 54 minutes, 20 secondsWill it think of something? Sometimes it can decide that you know nothing should be added here. Sometimes it just fails.
9:54:279 hours, 54 minutes, 27 secondsLet me go ahead and see why it has failed. So the problem is I never know.
9:54:359 hours, 54 minutes, 35 secondsYou can see it's telling me I have exceeded my current quota, but I'm almost 99% sure that's not the case. I
9:54:449 hours, 54 minutes, 44 secondsjust think it works funky. Sometimes it works, sometimes it doesn't. Let me try writing const on click here. Will it work or not?
9:54:569 hours, 54 minutes, 56 secondsLooks like not. But let's simply check.
9:54:599 hours, 54 minutes, 59 secondsIf I go ahead inside of my route.ts suggestion and if I change this to anthropic.
9:55:079 hours, 55 minutes, 7 secondsSo I mean for you Google might work perfectly fine but for me it's always funky. I don't know why. I mean we are talking about their free tier right? So
9:55:169 hours, 55 minutes, 16 secondsthat's obviously different. And yeah, for for something like this when it comes to a thropic, you should kind of use one of the cheaper models like haiku
9:55:259 hours, 55 minutes, 25 secondsor something like that simply because this shouldn't be too expensive, right?
9:55:319 hours, 55 minutes, 31 secondsUh I mean in my original source code, it seems like I have used this 37 set. Now I'm not sure what
9:55:399 hours, 55 minutes, 39 secondsspecific version, right? Uh but let me go ahead and refresh and see if this will work better. So I will delete this
9:55:489 hours, 55 minutes, 48 secondsand do it again. Const on click. Uh let's see. There we go. You can see how anthropic works very nice. Const on enter. Let's see.
9:55:589 hours, 55 minutes, 58 secondsThere we go. And if I move it resets.
9:56:019 hours, 56 minutes, 1 secondThat's what's important too. We have to test all of those things. And when I come back here, I can still accept.
9:56:079 hours, 56 minutes, 7 secondsVery, very cool. Make sure your indentation is still working fine.
9:56:119 hours, 56 minutes, 11 secondsRight. Uh let's see. If I go ahead and just add a new line here, will it maybe suggest some extension here? And sometimes it just won't do anything. And
9:56:199 hours, 56 minutes, 19 secondsthat won't be an error. It just decides I shouldn't do anything. Let's see if I add console here.
9:56:289 hours, 56 minutes, 28 secondsWill it suggest maybe a log? Here it is.
9:56:309 hours, 56 minutes, 30 secondsCleaning up editor view. A very relevant log. So it completely understand the lines coming before and after our code.
9:56:389 hours, 56 minutes, 38 secondsSo it definitely works. Uh, I just not sure how do I make it work reliably with
9:56:459 hours, 56 minutes, 45 secondsGoogle. I mean, you saw for a second that it does work, right? So, obviously something is working here, but I just
9:56:539 hours, 56 minutes, 53 secondshave so little awareness of like it's uh models that I don't know what's good and
9:57:009 hours, 57 minuteswhat's bad. Let's try Gemini 2.5 Pro. I don't even know can I use this in free tier? If I add on key down here, this
9:57:099 hours, 57 minutes, 9 secondsshould be a relatively simple autocomplete, but I don't know. It seems like it's just not uh working like I like I I want
9:57:189 hours, 57 minutes, 18 secondsto give you the option to use free uh AI models, but they're just not reliable
9:57:249 hours, 57 minutes, 24 secondsfor me. I don't know uh if maybe for you they are working. I mean, it's telling
9:57:309 hours, 57 minutes, 30 secondsme I have exceeded my quotota. So, I think that might also just mean that I'm
9:57:379 hours, 57 minutes, 37 secondsusing a Google model that should not be used for um
9:57:469 hours, 57 minutes, 46 secondsfor the free tier, but I'm not sure. I have no idea. If you have better knowledge of Google, you might solve
9:57:549 hours, 57 minutes, 54 secondsthis for yourself, right? Oh, there we go. That works. Let's try const click. Let's see.
9:58:039 hours, 58 minutes, 3 secondsWill it suggest something for me or will we throw an error? Again, you can see it does work obviously, but I guess it's
9:58:119 hours, 58 minutes, 11 secondsjust the fact that it's free tier is not too powerful. So, it very easily hits some limits, I guess. But yeah, it
9:58:189 hours, 58 minutes, 18 secondsdefinitely works and it works quite well. You can see how it suggested just a single line and nothing more than that. But then very soon it starts to
9:58:279 hours, 58 minutes, 27 secondsfail, right? So, because of that, uh I'm going to switch to anthropic. Again, I understand a lot of you are not able uh
9:58:359 hours, 58 minutes, 35 secondsto do that, you know, but I'm not really sure what to do in this situation. Feel free to try other models. I mean, there's X AI, right? So, you can you can
9:58:449 hours, 58 minutes, 44 secondsimport X AI just have to install AI SDK X AI and I think they offer free tier 2.
9:58:519 hours, 58 minutes, 51 secondsUh there's DeepSseek. Uh right, feel free to, you know, uh research because any model can work with this. It's just
9:58:589 hours, 58 minutes, 58 secondsthat the free ones are not reliable when it comes to rate limiting. So that's why I'm using Enthropic to demonstrate and prove that our code is actually working
9:59:079 hours, 59 minutes, 7 secondsright. It's just uh the fact that the models that we choose will depend on the result. See anthropic works perfectly immediately throws something relevant.
9:59:199 hours, 59 minutes, 19 secondsExcellent. So amazing amazing job. So what can be improved here? One thing that immediately comes to mind is this.
9:59:259 hours, 59 minutes, 25 secondsSo we are not doing any validation on the server but we are doing it here in the fetcher right.
9:59:339 hours, 59 minutes, 33 secondsSo let me see if it would be easy to maybe share these suggestion request
9:59:419 hours, 59 minutes, 41 secondsschemas and then validate them. I mean I don't know we are validating them here in the fetcher. So we know that this
9:59:489 hours, 59 minutes, 48 secondsJSON is pretty reliable, but it could be a good idea to also uh verify it here.
9:59:579 hours, 59 minutes, 57 secondsSo it shouldn't be too complicated to add that, you know, but for tutorial purposes, I think this is just perfectly fine. We do have a validation here.
10:00:0510 hours, 5 secondsObviously, if you expect someone else to call this endpoint that's not your app, well then you should probably uh you
10:00:1410 hours, 14 secondsknow limit this and validate it and things like that, right? But for a purpose like this where it's just our
10:00:2110 hours, 21 secondsapp, it's fine, right? But obviously you know uh this API suggestion should only be hit if you're logged in. So that's one of the things we can actually do
10:00:2910 hours, 29 secondshere. I think we can just do user id
10:00:3410 hours, 34 secondsuh await out from clerk next.js server
10:00:4110 hours, 41 secondslike this and then if there is no user ID return next response.json
10:00:4910 hours, 49 secondsJSON and pass in uh let's see how do I return errors like this
10:00:5810 hours, 58 secondsright just to make sure that no one no malicious actors are trying to
10:01:0710 hours, 1 minute, 7 secondsaccess this okay let can I do it like this and this would be unauthorized
10:01:1410 hours, 1 minute, 14 secondswith a 403 like that. So now only logged in users can do this. And then later when we
10:01:2210 hours, 1 minute, 22 secondsenable billing, we can also super easily check that uh the user is also on a pro plan, right? So no one can spend your tokens who isn't uh paying for your SAS.
10:01:3410 hours, 1 minute, 34 secondsSo yes, that's one thing I would recommend doing. And since I'm logged in, uh I would expect being able to do this. Let's see.
10:01:4410 hours, 1 minute, 44 secondsUh there we go. Still works perfectly fine. Awesome.
10:01:4810 hours, 1 minute, 48 secondsUh great. So uh let's see what we have to do next.
10:01:5510 hours, 1 minute, 55 secondsSo I think it makes the most sense to immediately implement the second custom suggestion we're going to have which is
10:02:0210 hours, 2 minutes, 2 secondsthe suggestion tool tip. So uh let's go ahead and start by uh going with the API
10:02:1010 hours, 2 minutes, 10 secondsroute because this time we won't be going through stages, right? We won't be doing any mock things. We're just going to go ahead outright and build it. So quick dashedit and inside route.ts.
10:02:2410 hours, 2 minutes, 24 secondsSo this time I'm going to be using anthropic simply because I'm having problems with Google. But again, you can go ahead and import Google and use Google if you prefer.
10:02:3410 hours, 2 minutes, 34 secondsBesides that, we're also going to import firecrawl using at lib firecrawl. Let's
10:02:4110 hours, 2 minutes, 41 secondsgo ahead and define the quick edit schema which is going to be a Zod object and it accepts edited code. The edited version of the selected code based on
10:02:5010 hours, 2 minutes, 50 secondsthe instruction. So this is a bit different because the user will directly select and highlight a line of code it wants to modify.
10:02:5810 hours, 2 minutes, 58 secondsLet's define the URL ragex. You can Google this if you don't know which one it is or you can pause the screen. And
10:03:0810 hours, 3 minutes, 8 secondsnow we need to define the quickedit prompt. So you can head to my Polaris suggestions, my apologies, uh, Polaris assets and you can find prompts.ts.
10:03:1910 hours, 3 minutes, 19 secondsAnd in here we have suggestion prompt and here we have quick edit prompt. So let me go ahead and copy it.
10:03:2710 hours, 3 minutes, 27 secondsNow let's go ahead and let's paste it.
10:03:3010 hours, 3 minutes, 30 secondsSo here it is. Quick edit prompt. You are a code editing assistant. to edit the selected code based on the user's
10:03:3810 hours, 3 minutes, 38 secondsinstruction. Return only the edited version of the selected code. Maintain the same indentation level as original.
10:03:4410 hours, 3 minutes, 44 secondsDo not include any explanations or comments unless requested. If the instruction is unclear or can be applied, return the original code unchanged.
10:03:5310 hours, 3 minutes, 53 secondsAll right. And now let's export asynchronous function
10:04:0010 hours, 4 minutespost accept a request and let's open a try and catch. So what
10:04:1010 hours, 4 minutes, 10 secondswe're going to the structure here from the request.json is simpler selected code the full code for the context and the instruction.
10:04:2010 hours, 4 minutes, 20 secondsAnd let's check if there is no selected code simply throw selected code is required. If there is no instruction,
10:04:2910 hours, 4 minutes, 29 secondsinstruction is required. And while we are here, we can also do user ID from await out
10:04:3710 hours, 4 minutes, 37 secondsfrom clerk next.js server. Let me go ahead and just move this here.
10:04:4610 hours, 4 minutes, 46 secondsI like to order them by length.
10:04:4910 hours, 4 minutes, 49 secondsAnd now in here, I'm also going to do the exact same check, but just if there is no user ID, unauthorized.
10:05:0210 hours, 5 minutes, 2 secondsAll right. So, now that we have checks for all of those things, let's see if the user gave us any URLs. URLs is going
10:05:1110 hours, 5 minutes, 11 secondsto be an array of strings and we're simply going to go over the instruction the user gave us and match it using the URL regax which we've defined up here
10:05:2010 hours, 5 minutes, 20 secondsotherwise fall back to an empty array and then let's go ahead and define the documentation context. So if the URL's
10:05:3010 hours, 5 minutes, 30 secondslength is larger than zero let's go ahead and scrape the results. So const
10:05:3610 hours, 5 minutes, 36 secondsscraped results await promise all URLs dom
10:05:4510 hours, 5 minutes, 45 secondsasynchronous get the individual URL open a try and catch block
10:05:5210 hours, 5 minutes, 52 secondsand in here attempt to get the result using await firecrol scrape URL in the
10:05:5910 hours, 5 minutes, 59 secondsmarkdown format if result domarkdown return and then the syntax I'm going to
10:06:0910 hours, 6 minutes, 9 secondsreturn here is very specific again works very well for claude for enthropic it's in formative XML if you want to you can
10:06:1710 hours, 6 minutes, 17 secondsliterally just return result domarkdown but this will kind of make it serve
10:06:2510 hours, 6 minutes, 25 secondsbetter as context when it comes to um when it comes to
10:06:3210 hours, 6 minutes, 32 secondsI'm not sure what I'm trying to explain uh understanding that this is an additional documentation something that
10:06:3810 hours, 6 minutes, 38 secondswas scraped right this exact format like a XML syntax this is a document this is the URL and this is the result of the
10:06:4610 hours, 6 minutes, 46 secondsURL but again you can just return result domarkdown otherwise we are returning null and in
10:06:5510 hours, 6 minutes, 55 secondsthe catch we are returning null as well and then let's go ahead and only grab the valid results from that.
10:07:0410 hours, 7 minutes, 4 secondsSo, let's see. Uh, scrape the results.
10:07:0810 hours, 7 minutes, 8 secondsScrape the results. Filter boolean. They now turn into valid results. And then
10:07:1410 hours, 7 minutes, 14 secondswe're going to push all of these if they are more than zero. We're going
10:07:2110 hours, 7 minutes, 21 secondsto add documentation context to be the following. Inside of the documentation XML tag, we're going to add a page
10:07:2910 hours, 7 minutes, 29 secondsbreak. And then we're going to join an array of these using more page breaks.
10:07:3410 hours, 7 minutes, 34 secondsSo basically it's going to be like documentation and documentation and in here URL
10:07:4410 hours, 7 minutes, 44 secondsnext.js.org proxy.ts right and then in here blah blah blah what is proxy and doc and just
10:07:5310 hours, 7 minutes, 53 secondsa bunch of doc urls. That's how the result is going to look like. So again you don't have to use XML but it works
10:08:0210 hours, 8 minutes, 2 secondsvery well with clause. So if we have any valid results we simply append the documentation context with that XML tag
10:08:0910 hours, 8 minutes, 9 secondsand we join all the valid results using double page break here and we end with another page break in here to format it nice for the AI.
10:08:1810 hours, 8 minutes, 18 secondsAwesome. So now uh outside of this if URL's length is larger than zero, let's
10:08:2510 hours, 8 minutes, 25 secondsgo ahead and modify our prompt. So that's going to be quickedit prompt. And let's start replacing some things. So
10:08:3410 hours, 8 minutes, 34 secondsthe first thing we're going to replace is selected code with the variable selected code. Then full code or an empty string.
10:08:4510 hours, 8 minutes, 45 secondsThen instruction with instruction and finally documentation with the
10:08:5210 hours, 8 minutes, 52 secondsdocumentation context and then let's go ahead and define the output using a way to generate text.
10:09:0010 hours, 9 minutesAgain I'm using entropic and claw model.
10:09:0310 hours, 9 minutes, 3 secondsYou can use uh Google here. Just make sure to use proper Google model. You can use XAI whatever you want. I'm using
10:09:1010 hours, 9 minutes, 10 secondsanthropic because it's very reliable for me. And now I'm just going to go ahead and return next response.json edited
10:09:1810 hours, 9 minutes, 18 secondscode output.edited code. And you can see that is the edited version of the selected code based on the instruction uh which we have defined in the quickedit schema.
10:09:2910 hours, 9 minutes, 29 secondsAnd in the cache here we're just going to go ahead and throw some errors. So make sure to grab an error here and go
10:09:3610 hours, 9 minutes, 36 secondsahead and just throw like this edit error and next response.json JSON failed
10:09:4210 hours, 9 minutes, 42 secondsto generate edit. Uh, awesome. So that is forward slashquickedit.
10:09:5010 hours, 9 minutes, 50 seconds[snorts]
10:09:5010 hours, 9 minutes, 50 secondsNow what I would like to do is I would like to go inside of projects. My apologies inside of features editor
10:09:5810 hours, 9 minutes, 58 secondsextensions. I'm going to copy and paste suggestion and I'm going to rename this to quick-ashedit.
10:10:0510 hours, 10 minutes, 5 secondsAnd I'm going to go inside of fetcher here and just modify it so it works for fetcher. So, it's not going to be called suggestion request schema. It's going to
10:10:1310 hours, 10 minutes, 13 secondsbe called edit request schema with selected code, full code, and instruction. And for the edit response
10:10:2010 hours, 10 minutes, 20 secondsschema, we're just going to have edited code ZTS string. That's also going to change these two types,
10:10:2810 hours, 10 minutes, 28 secondsit's going to be edit request type of edit request schema and edit response type of edit response schema.
10:10:3610 hours, 10 minutes, 36 secondsSo, let's see. Uh this will now be edit request and this will now be edit request
10:10:4610 hours, 10 minutes, 46 secondsschema like that. The API endpoint will go to quick dashedit.
10:10:5210 hours, 10 minutes, 52 secondsWe can increase the timeout to 30,000 because we allow this one to think longer. And let's use edit response
10:11:0010 hours, 11 minuteshere. And let's use edit response schema. And this is edited code or null.
10:11:0810 hours, 11 minutes, 8 secondsAnd this will be fail to fetch AI quick edit.
10:11:1410 hours, 11 minutes, 14 secondsThere we go. So that's a very quick uh fetcher modified. And now we go to the
10:11:2110 hours, 11 minutes, 21 secondsuh extension of the quick edit. So uh the extension of the quickedit is a bit different. Let's go all the way down
10:11:2910 hours, 11 minutes, 29 secondshere. I I personally think it's a bit simpler, so don't worry. And we won't go through all the stages. We're just going to build it out, right? So, export constit.
10:11:3810 hours, 11 minutes, 38 seconds[snorts]
10:11:4010 hours, 11 minutes, 40 secondsUh, we're actually not going to be using the file name, but maybe that's not such a good idea. Maybe we should use the file name for now. I'm just going to leave it here as a prop, but I'm not
10:11:4810 hours, 11 minutes, 48 secondsgoing to use it anywhere. So, the first thing we're going to do, we can remove all this. Is going to be quickedit state. So, I'm just going to remove
10:11:5710 hours, 11 minutes, 57 secondseverything up to the state. That's the only thing I'm going to leave. There we go. We obviously are going to still use the fetcher and I'm just going to remove
10:12:0610 hours, 12 minutes, 6 secondsall the comments simply because uh I think I removed something other than a comment,
10:12:1310 hours, 12 minutes, 13 secondsright? Uh because we explained how extensions work in the previous one and I think now we can just focus on building one. So quickedit state, let's
10:12:2310 hours, 12 minutes, 23 secondsgo ahead and start with setting the effect. So it's not going to be set suggestion effect. It's going to be show quickedit effect state effect define
10:12:3210 hours, 12 minutes, 32 secondsboolean. Then let's go ahead and let's define a few things here.
10:12:3710 hours, 12 minutes, 37 secondsEditor view to be a type of editor view or null and the current abboard controller to be aboard controller or null. Right here
10:12:4610 hours, 12 minutes, 46 secondsI'm going to make it easier and just delete everything like this. So let's go ahead and define the quick edit state.
10:12:5610 hours, 12 minutes, 56 secondsThe quick edit state will be a state field dodee define which accepts a boolean.
10:13:0210 hours, 13 minutes, 2 secondsAnd we're going to start with a simple create method in which we are going to return false. We are then going to create an update method which has a value and transaction.
10:13:1410 hours, 13 minutes, 14 secondsAnd let's go ahead and search for const effect of transaction.
10:13:1910 hours, 13 minutes, 19 secondsIf effect is show quickedit effect, return effect do value. And then after
10:13:2510 hours, 13 minutes, 25 secondsthat for loop if transaction selection exists let's go ahead and get the selection
10:13:3310 hours, 13 minutes, 33 secondsand if the selection is empty return false right so if the user didn't select anything return false otherwise just
10:13:4210 hours, 13 minutes, 42 secondsreturn the value great so now our quickedit state is finished so now what
10:13:4810 hours, 13 minutes, 48 secondsI want to do is I want to add quickedit tool tip field. Let's go ahead and uh build this
10:13:5810 hours, 13 minutes, 58 secondsone next. I'm just trying to see uh okay yes so in order to build that
10:14:0610 hours, 14 minutes, 6 secondswe have to define the following function create quickedit tool tip which accepts
10:14:1310 hours, 14 minutes, 13 secondsa state of editor state and returns read only tool tip I mean an array of tool tips and let's start with getting our
10:14:2210 hours, 14 minutes, 22 secondsselection if the selection is empty return an empty array
10:14:3010 hours, 14 minutes, 30 secondsThen let's go ahead and see is quickedit active. Right?
10:14:3710 hours, 14 minutes, 37 secondsSo that's why we are returning false here because by default it's not active. That's how this is going to serve.
10:14:4410 hours, 14 minutes, 44 secondsAnd if it is not again return an empty array otherwise return an array and an object inside.
10:14:5310 hours, 14 minutes, 53 secondsAnd now in here the position is select.2 to above is going to be false.
10:15:0110 hours, 15 minutes, 1 secondStrict side is going to be false. And then we're going to call the create method.
10:15:0810 hours, 15 minutes, 8 secondsThe create method will create a div element. We're then going to give that a class name. So we're just styling it
10:15:1610 hours, 15 minutes, 16 secondsnow. So this class name right here that you're seeing, let me show you how that's going to look like so it's easier. Uh so if I switch to localhost
10:15:2410 hours, 15 minutes, 24 seconds3005 here, this is my finished product here. So when I select something and click quick edit, this is what we're
10:15:3310 hours, 15 minutes, 33 secondsbuilding. So this is cancel submit. This is the div the input, right? We
10:15:4010 hours, 15 minutes, 40 secondscurrently do not have that. If I select something, nothing happens. And if I press command K, nothing happens. So
10:15:4910 hours, 15 minutes, 49 secondsthat's what we're doing now. Uh now after that DOM class name we need to define a form element and we need to
10:15:5710 hours, 15 minutes, 57 secondsgive that form some class names flex flex call and gap 2. Then we're creating our input element where the user will
10:16:0410 hours, 16 minutes, 4 secondsactually type what they want. We are going to give it a type of text placeholder of edit selected code. Let's
10:16:1110 hours, 16 minutes, 11 secondsgo ahead and give it a class name of background transparent border noun none outline none padding on x-axis 2 on yaxis one font sense and a width of 100.
10:16:2410 hours, 16 minutes, 24 secondsThen autofocus on true. Then let's create a button container which is going to hold our two buttons. So another div
10:16:3210 hours, 16 minutes, 32 secondswith flex item center justify between gap two. Fun fact, this is how we built components before react. So now let's go
10:16:4010 hours, 16 minutes, 40 secondsahead and do a cancel button here. And let's go ahead and give it some properties. Type is button. Text content is cancel.
10:16:4810 hours, 16 minutes, 48 secondsNow let's go ahead and give it some class name font sands padding one px2 text muted foreground hover text foreground on hover bg foreground with a
10:16:5710 hours, 16 minutes, 57 seconds10% opacity and rounded small. Now let's go ahead and define what happens when we click the cancel button.
10:17:0510 hours, 17 minutes, 5 secondsSo when we click the cancel button, if we have the abort controller, let's make sure to abort and return it back to
10:17:1210 hours, 17 minutes, 12 secondsnull. Otherwise, I mean still if we have editor view, let's call editor view.dispatch
10:17:1910 hours, 17 minutes, 19 secondseffects show quick edits off and set it back to false.
10:17:2410 hours, 17 minutes, 24 secondsSo now let's go ahead and do very similar to submit method. I mean submit button.
10:17:3310 hours, 17 minutes, 33 secondsSubmit button is another button. Submit button type is submit. Submit button text content is submit.
10:17:4010 hours, 17 minutes, 40 secondsLet's go ahead and add a class name.
10:17:4210 hours, 17 minutes, 42 secondsFont sands padding one px2 text muted foreground basically I think identical to this one. I don't think there are any differences.
10:17:5110 hours, 17 minutes, 51 secondsAnd this one won't have its own on click because this is a type of submit. So instead we are going to access our form
10:17:5810 hours, 17 minutes, 58 secondselement on submit. And the first thing we're going to do is make sure to prevent default so it doesn't refresh the page. In case we cannot access the editor view, we're going to break the
10:18:0610 hours, 18 minutes, 6 secondsmethod. Then we're going to attempt to trim the instruction. And if it is not available after the trim, it means it's
10:18:1310 hours, 18 minutes, 13 secondsempty. So we return it. Then we are going to go ahead and get the selection from the editor view state selection
10:18:2010 hours, 18 minutes, 20 secondsmain. We are going to get the selected code using again editor view state document slice string selection from selection to uh these errors are fine.
10:18:3110 hours, 18 minutes, 31 secondsWe're going to fix them later. Then let's add the full code editor view state document to string.
10:18:3810 hours, 18 minutes, 38 secondsThen let's go ahead and make sure that while this is submitting we set the submit button to disabled and change it the content to editing.
10:18:4710 hours, 18 minutes, 47 secondsLet's go ahead and assign the new abboard controller here. And finally we can go ahead and get edited code using our fetcher.
10:18:5810 hours, 18 minutes, 58 secondsIn the first argument we send the payload which is selected code full code and instruction. And in the second
10:19:0510 hours, 19 minutes, 5 secondsargument we send the abort controller signal so that we can abort if user uh changes it mind.
10:19:1410 hours, 19 minutes, 14 secondsSo now let's go ahead and open if the edited code was received. We now have to call editor view dispatch and we have to
10:19:2310 hours, 19 minutes, 23 secondsmodify it. So we first have to define where changes from selection from to selection to insert what the edited code
10:19:3210 hours, 19 minutes, 32 secondswe just got back from the API. Then let's go ahead and make sure to modify the selection. So we move it to the end
10:19:3810 hours, 19 minutes, 38 secondsof the edited code and return this state to false. So it's no longer opened like that. else. If edited code was not
10:19:4810 hours, 19 minutes, 48 secondsreceived, we're simply going to make sure that we reset submit button disabled back to false and this back to submit, which most likely means something went wrong.
10:19:5810 hours, 19 minutes, 58 secondsAnd finally, current aboard controller is null. And now what we have to do is we have to append these things to button
10:20:0610 hours, 20 minutes, 6 secondscontainer. So cancel button and submit button. And then we have to append all of those things to form. So append the input and append the button container.
10:20:1610 hours, 20 minutes, 16 secondsAnd finally append the form to the dome.
10:20:1910 hours, 20 minutes, 19 secondsAnd to [snorts] make out of focus work, let's do a simple set timeout trick. And then in the end, let's return
10:20:2710 hours, 20 minutes, 27 secondsdome like this. Quite a long function uh but a very useful one. I mean most of it was
10:20:3410 hours, 20 minutes, 34 secondsjust building the UI, right? This would be way easier to write if we had access to JSX and React. But we are in this
10:20:4210 hours, 20 minutes, 42 secondsenvironment where we have to write code this way. But yeah, this is how people wrote before react.
10:20:4910 hours, 20 minutes, 49 secondsUh all right. So we have that and now we can define quickedit tool tip field. So
10:20:5610 hours, 20 minutes, 56 secondsconst quickedit tool tip field state field define read only tool tip and then
10:21:0410 hours, 21 minutes, 4 secondsan array like this.
10:21:0910 hours, 21 minutes, 9 secondsLet's go ahead and add create here. Uh, and let me just see. Uh, okay. The tool tip needs to be imported.
10:21:1710 hours, 21 minutes, 17 secondsYeah, let me fix all the imports actually.
10:21:2210 hours, 21 minutes, 22 secondsSo, from code mirror view, we're going to need tool tip, show tool tip, keymap, and editor view. And from state, we're
10:21:3110 hours, 21 minutes, 31 secondsgoing to need state field, editor state, and state effect. And then the fetcher. Okay.
10:21:3910 hours, 21 minutes, 39 secondsLet's go down here where we started building the quick edit tool tip field.
10:21:4810 hours, 21 minutes, 48 secondsSo we have create here. Now let's create an update which accepts tool tips and transaction.
10:21:5910 hours, 21 minutes, 59 secondsAnd in here if transaction document changed or transaction selection return create new
10:22:0810 hours, 22 minutes, 8 secondsquickedit tool tip. Basically uh we need to define where to render the tool tip to render to allow user to write
10:22:1710 hours, 22 minutes, 17 secondssomething. We can't just render it anywhere. We need to be aware is the cursor here is the selection here. Right? That's what this update is doing.
10:22:2410 hours, 22 minutes, 24 secondsIt's kind of like doing the visual thing. And then outside of this if clause do a for loop. So again searching for an effect in all of our transaction
10:22:3210 hours, 22 minutes, 32 secondseffects. If we find one with show quickedit effect we return again create quickedit tool tip with the current transaction state. And let's finally go ahead and return tool tips.
10:22:4510 hours, 22 minutes, 45 secondsAnd then in here let's add provide field and return show tool tip compute n.
10:22:5710 hours, 22 minutes, 57 secondsFirst argument is an array of field.
10:23:0010 hours, 23 minutesSecond argument is a function which accepts state and returns state.field and passes in the field like that.
10:23:1010 hours, 23 minutes, 10 secondsGreat. Uh and now there are a couple of more we have to implement. So they're just easier than all of these. So the
10:23:1810 hours, 23 minutes, 18 secondsnext one is quick edit keymap. This will basically allow us to use a shortcut to open this.
10:23:2610 hours, 23 minutes, 26 secondsSo quickedit keymap here. Open an array.
10:23:2910 hours, 23 minutes, 29 secondsInsert an object here. The key will be mod and then the letter K. And what that's going to do is it's going to run
10:23:3710 hours, 23 minutes, 37 secondssomething with the view. So we get the current selection where it happened. If the selection was empty, there's nothing
10:23:4510 hours, 23 minutes, 45 secondswe can do. But if it isn't, we call view.dispatch effects show quickedit effects off and
10:23:5210 hours, 23 minutes, 52 secondspass true. And then we return true simply to override if mod k was any other method already. Great. So that was
10:24:0110 hours, 24 minutes, 1 seconda simple one. And the last one we need is capture uh the last one we need is capture view extension. This one is the simplest.
10:24:1410 hours, 24 minutes, 14 secondsCapture view extension editor view update listener off update editor view update view. I think this just refreshes
10:24:2110 hours, 24 minutes, 21 secondsthe uh state like when we type and things. I will double check. I'm not 100% sure. Uh it is my first time
10:24:2810 hours, 24 minutes, 28 secondsbuilding code mirror extensions too. So I'm trying my best with that first one to go through stages so we both understand how they work from
10:24:3610 hours, 24 minutes, 36 secondsprimitives. But with this one I think you know we can just go ahead and build it. Uh okay. Okay, I think yeah and you
10:24:4310 hours, 24 minutes, 43 secondscan see all errors actually went away as we built. So all of this should be fine.
10:24:4810 hours, 24 minutes, 48 secondsFile name is expected to be like that here. So now let's go inside of our
10:24:5610 hours, 24 minutes, 56 secondscomponents code editor here and after suggestion pass the quick edit from extensions quickedit and simply pass the
10:25:0510 hours, 25 minutes, 5 secondsfile name here too even though we don't use that. So now what you should be able to do is
10:25:1310 hours, 25 minutes, 13 secondsselect the thing like this using control key or command key should open this edit selected code and I should be able to
10:25:2210 hours, 25 minutes, 22 secondssay rename this to folder name and I should be able to press enter and submit and it was just successfully renamed to
10:25:3010 hours, 25 minutes, 30 secondsfolder name. So if yours is not working, make sure to try control key, command
10:25:3810 hours, 25 minutes, 38 secondskey, you know, whatever your action key is, whatever your modulus key is. Mod mod key is you can also like manually
10:25:4610 hours, 25 minutes, 46 secondschange this if you want to just try it out. You can try I don't know the letter B.
10:25:5410 hours, 25 minutes, 54 secondsI think this might work. So if I highlight this and do shift B, it opens. ShiftB. Try that.
10:26:0510 hours, 26 minutes, 5 secondsOr if I use a lowercase letter B, I think it's then going to like pop up every time I press letter B. Yes. So
10:26:1210 hours, 26 minutes, 12 secondsevery time I press the letter B, it opens. So let's bring it back to mod K.
10:26:2110 hours, 26 minutes, 21 secondsAnd now to wrap this up, there is actually one more thing we have to do. I mean, you might be satisfied with this as it is, but uh it might be like cool to have, let me go ahead and show you.
10:26:3310 hours, 26 minutes, 33 secondsIt might be cool to have an ability that when you highlight [snorts] in general, it shows you the option to quickedit,
10:26:4110 hours, 26 minutes, 41 secondsright? So, let's go ahead and implement that. This one actually doesn't include any complicated logic. It's just tedious
10:26:4910 hours, 26 minutes, 49 secondsto write the components that way, but let's go ahead and do it. So, one thing I already know we're going to have to do
10:26:5610 hours, 26 minutes, 56 secondsis inside of the extensions inside of QuickEdit here index, we're going to have to
10:27:0510 hours, 27 minutes, 5 secondsexport I think this one. I think we're going to have to export quickedit state
10:27:1110 hours, 27 minutes, 11 secondsand also yeah, so export show quickedit effect and export quick state. Make sure you export both of these two.
10:27:1910 hours, 27 minutes, 19 secondsAnd now we're going to go ahead inside of extensions and we're going to create a new one. And this one uh actually no need for a folder. This one is simpler.
10:27:2910 hours, 27 minutes, 29 secondsSo we can just call it selection-tool tip.ts. So selection tool tip. And let's
10:27:3610 hours, 27 minutes, 36 secondsgo ahead and start with export con selection tool tip which will accept selection tool tip field and capture view extension. We can go ahead and
10:27:4510 hours, 27 minutes, 45 secondsimmediately fix the capture view extension. It's editor view update listener off update
10:27:5210 hours, 27 minutes, 52 secondseditor view update view. The exact same one we had from before. I mean in this one right if you scroll down here you
10:28:0010 hours, 28 minuteswill see at least the thing it's exactly the same. Yeah. So for the imports of selection tool tip,
10:28:0810 hours, 28 minutes, 8 secondslet's go ahead and import tool tip, show tool tip and editor view from code mirror view, state field and editor state from code mirror state and show
10:28:1610 hours, 28 minutes, 16 secondsquick edit and quick edit state from quick edit. And now let's go ahead and start developing this. Right? So I'm
10:28:2310 hours, 28 minutes, 23 secondsgoing to define editor view to be editor view or null. And then I'm going to go ahead and create a function
10:28:3210 hours, 28 minutes, 32 secondscreate tool tip for selection. It's going to accept state and it's going to return a readonly array of tool tips.
10:28:4110 hours, 28 minutes, 41 secondsWe're going to start with a selection and if selection is empty, we're going
10:28:4710 hours, 28 minutes, 47 secondsto return an empty array. Then let's check if quickedit is active like this.
10:28:5410 hours, 28 minutes, 54 secondsIf it is active, we're going to return an empty array.
10:28:5910 hours, 28 minutes, 59 secondsOtherwise, we're going to go ahead and build UI.
10:29:0510 hours, 29 minutes, 5 secondsSo, let's go ahead and again start with the position, which is selection two above false, strict side false, and then we go ahead and build the create.
10:29:1810 hours, 29 minutes, 18 secondsSo, again, we start with the DOM, right?
10:29:2210 hours, 29 minutes, 22 secondsWe then go ahead and give the DOM class name BG popover text popover foreground Z50 rounded small border border input
10:29:3010 hours, 29 minutes, 30 secondspadding one shadow medium flex item center gap two and text small. We then go ahead and start with uh add to chat
10:29:4010 hours, 29 minutes, 40 secondsbutton which we will see how we will implement this functionality later but for now it's just going to be visual.
10:29:4710 hours, 29 minutes, 47 secondsSo let me just properly indent this There we go. So, add to chat button is a
10:29:5410 hours, 29 minutes, 54 secondsbutton with text content add to chat and class name here. And then we have the familiar one.
10:30:0110 hours, 30 minutes, 1 secondQuick edit button again. Document create element button. Let's go ahead and give it the following class name. Feel free to pause the screen to copy the class
10:30:0910 hours, 30 minutes, 9 secondsnames. Now, let's go ahead and give the quickedit button the span element quickedit. So text content is quickedit.
10:30:2210 hours, 30 minutes, 22 secondsLet's go ahead and create a shortcut element. So quickedit button shortcut is another span element. The text content
10:30:3110 hours, 30 minutes, 31 secondsis again this is my Mac OS control sign right. So command K text small opacity
10:30:3810 hours, 30 minutes, 38 seconds60. You can also write control + K here whatever you want.
10:30:4410 hours, 30 minutes, 44 secondsAnd now let's go ahead and let's append these elements. Quick edit button, append child, quick edit button text,
10:30:5210 hours, 30 minutes, 52 secondsand append child quickedit button shortcut. And now on quick edit button on click, if we
10:31:0010 hours, 31 minuteshave the editor view, simply dispatch and change the uh state of show quickedit effect to be true. And that
10:31:0810 hours, 31 minutes, 8 secondswill then trigger this what we've just built previously. We did this entire thing before, right? All right. And then
10:31:1610 hours, 31 minutes, 16 secondswe just have to append all of these to the DOM. Add to chat button and quick edit button. And finally return dome.
10:31:2610 hours, 31 minutes, 26 secondsGreat. So what's left is the selection tool tip field. So let's go ahead and develop that here.
10:31:3710 hours, 31 minutes, 37 secondsSelection tool tip field. State field define a readonly tool tip. Let's go ahead and call create
10:31:4510 hours, 31 minutes, 45 secondsin which we are going to return tool tip for selection and pass the state along.
10:31:5010 hours, 31 minutes, 50 secondsAs always, we're going to have an update function which accepts the tool tip and the transaction.
10:31:5610 hours, 31 minutes, 56 secondsIf transactions document has changed and transaction selection return again create tool tip for selection. You can see this is a pattern right we keep
10:32:0510 hours, 32 minutes, 5 secondsdoing this uh right here. Right? So we are no okay this is the state not that one. Let me scroll down here. There we
10:32:1210 hours, 32 minutes, 12 secondsgo. See, every time kind of the document changes, we have to recalculate where we are going to build the UI.
10:32:2010 hours, 32 minutes, 20 secondsOutside of the if clause here, let's do a for loop for const effect of transaction effects. If effect is show quick effect, show quick edit effect.
10:32:3010 hours, 32 minutes, 30 secondsAgain, go ahead and build it. And then right here, return tool tips.
10:32:3710 hours, 32 minutes, 37 secondsAnd then let's add provide again which is a field. Show tool tip compute n field in array as the first argument.
10:32:4910 hours, 32 minutes, 49 secondsState state field as the second argument.
10:32:5410 hours, 32 minutes, 54 secondsThere we go. And seems like no errors here. So I believe this should work just fine. So now if you go inside of your
10:33:0510 hours, 33 minutes, 5 secondscomponents code editor right here and if you just add selection tool tip
10:33:1310 hours, 33 minutes, 13 secondsfrom extensions selection tool tip and let's execute that it should work. So now when I highlight
10:33:2210 hours, 33 minutes, 22 secondslet me just confirm I am on my uh realtime project. Okay it's local host 3000. We are getting so close to the finished project that I don't even know
10:33:3010 hours, 33 minutes, 30 secondswhich one is uh the one. And there we go. Add to chat does nothing. But quick edit triggers this. Rename props to uh globe props for example. Let's see.
10:33:4110 hours, 33 minutes, 41 secondsThere we go. Amazing. Amazing job. We implemented so many amazing features. We have shadow text. We have a mini map.
10:33:5210 hours, 33 minutes, 52 secondsAmazing. So that is 13 files. And now it's time to uh get Code Rabbit to
10:34:0010 hours, 34 minutesreview all of this. Right. So I'm just going to go ahead and shut down all of my terminals here. Let's see. Chapter
10:34:0710 hours, 34 minutes, 7 seconds11. So get add dot get commit 11 AI features.
10:34:1710 hours, 34 minutes, 17 secondsGet checkout-b 11 AI features. Git push U origin 11 AI features. And then let's
10:34:2610 hours, 34 minutes, 26 secondsgo ahead and open a pull request. A lot of changes. I'm very interested in the amount of files we have created this
10:34:3510 hours, 34 minutes, 35 secondstime. I mean the lines of code. Well, less than the previous pull request, but still. Let's go ahead and review it.
10:34:4210 hours, 34 minutes, 42 secondsSo what we've added in this chapter are AI powered quickedit functionality with keyboard shortcuts, intelligent code
10:34:5010 hours, 34 minutes, 50 secondssuggestions displayed as ghost text while typing, selection action tool for selected code, and we did some improvements. We enabled text selection
10:34:5810 hours, 34 minutes, 58 secondsthroughout the editor by removing select none from the body. We added toast notifications for user feedback. And we do have quite some comments here. So 10
10:35:0710 hours, 35 minutes, 7 secondscomments. uh some of them we already are aware of like the missing zod schema before the structuring which I told you
10:35:1510 hours, 35 minutes, 15 secondsyou can do of course but you know for tutorial purposes I'm going to keep it this way but yes obviously a good comment by code rabbit uh in here I
10:35:2310 hours, 35 minutes, 23 secondsforgot to change to 401 or 403 uh it definitely shouldn't be status code 400 if I'm throwing unauthorized but still
10:35:3110 hours, 35 minutes, 31 secondsnot anything that will break the app right uh in here we are not using uh fire crawls
10:35:3910 hours, 35 minutes, 39 secondstimeout features. So yes, uh if a single URL hangs indefinitely, it blocks the entire promise all causing the request
10:35:4710 hours, 35 minutes, 47 secondsto time out at the client's 30-second limit resulting in a poor user experience. So we could definitely add a timeout to each of the requests here to improve that.
10:35:5810 hours, 35 minutes, 58 secondsThen in here we have a very interesting comment. Yeah, this is quite fragile simply because if the user literally
10:36:0610 hours, 36 minutes, 6 secondstypes in things like this inside of their instruction. Uh we are
10:36:1310 hours, 36 minutes, 13 secondsgoing to replace it, right? Uh so yeah, it's kind of brittle, but I mean for
10:36:2010 hours, 36 minutes, 20 secondsmost use cases I've tried it works correctly. But still important for you to know. Uh if any input field like file
10:36:2810 hours, 36 minutes, 28 secondsname, code or current line contains a placeholder like these ones which we have defined the replacement will incorrectly modify the user's actual
10:36:3510 hours, 36 minutes, 35 secondscontent corrupting the prompt. Though I'm not sure since we are directly modifying the constant here. So I'm not
10:36:4210 hours, 36 minutes, 42 secondssure how this can modify our oh maybe if it is inside of here somewhere.
10:36:5010 hours, 36 minutes, 50 secondsNot sure. Okay. But as I said for most use cases I think this is fine. And now this is interesting. Yeah. So in couple
10:36:5710 hours, 36 minutes, 57 secondsof places it's telling us about this module level mutable state which can cause issues with multiple editor instances. So right now not an issue
10:37:0610 hours, 37 minutes, 6 secondsbecause we don't have multiple editor instances. But if you in the future plan to implement this you could probably uh
10:37:1410 hours, 37 minutes, 14 secondsuse a different architecture to not use this global definitions of editor view and abort controllers. So in here it
10:37:2110 hours, 37 minutes, 21 secondsrecommends using a uh weak map keyed by the editor view uh storing state in a custom state field using editor view
10:37:3010 hours, 37 minutes, 30 secondsfacets. So that's one of the solutions here. Uh in here uh actually this is a
10:37:3710 hours, 37 minutes, 37 secondsnew tailwind utility in version 4. No documentation is present
10:37:4410 hours, 37 minutes, 44 secondsbut the class name works. So let's make sure code rabbit learns that uh in here it noticed the unused file name
10:37:5310 hours, 37 minutes, 53 secondsparameter which we are aware of. We will see if we will do something non-functional add to chat button. Same thing same comment as before. So global
10:38:0210 hours, 38 minutes, 2 secondsstate shared across multiple editor instances right so it's basically telling us that uh this can cause race
10:38:0910 hours, 38 minutes, 9 secondsconditions if multiple editors are ever a feature incorrect cancellation wrong UI state right basically a bunch of
10:38:1710 hours, 38 minutes, 17 secondsproblems so we need to make sure that each editor instance has its own isolated state I will see if this is something that we can easily fix uh
10:38:2610 hours, 38 minutes, 26 secondsmaybe in the next chapter or so you can see it's using yeah like scoping it to this instead of just using
10:38:3410 hours, 38 minutes, 34 secondsyeah interesting and definitely a good comment here. Uh but as I said for our use case this is okay and it kind of
10:38:4410 hours, 38 minutes, 44 secondssays that down here if you read it. So the current situation is okay but if multiple editor instances exist simultaneously it will cause a problem.
10:38:5510 hours, 38 minutes, 55 secondsWhile the current UI architecture only renders a single editor at a time uh the implementation is fragile. So if a split view or multi-editor feature is added in
10:39:0310 hours, 39 minutes, 3 secondsthe future, these globals would cause race conditions and unexpected behavior.
10:39:0710 hours, 39 minutes, 7 secondsSo I didn't really build this with multi-editor feature or split view in mind, but it's good that you are aware of this. So this is why it's always good
10:39:1410 hours, 39 minutes, 14 secondsto have someone review the code. Uh I will see how easy it is to fix this. I mean judging by what they've recommended me here, it's not too difficult really.
10:39:2410 hours, 39 minutes, 24 secondsLooks like there are some built-in mechanisms to solve this. Maybe this can be a good challenge for you if you want to go even further. But for our use
10:39:3210 hours, 39 minutes, 32 secondscase, this is perfectly fine. I didn't encounter any problems at all. Uh great.
10:39:3810 hours, 39 minutes, 38 secondsIronic saying that I just received a failed fetch here. Uh but that is from a different project. That's from the
10:39:4410 hours, 39 minutes, 44 secondsfinished project. So yes. Okay. Uh amazing. So I'm going to go ahead and
10:39:5110 hours, 39 minutes, 51 secondsmerge this pull request. We are aware of those global shared instances and I will you know review that just to know check
10:39:5910 hours, 39 minutes, 59 secondsif it's not something that will cause problems in our current implementation but I highly doubt it will. Great. Now that we've done that let's go ahead and
10:40:0810 hours, 40 minutes, 8 secondsget checkout main get pool origin main right here. And once we've done that we
10:40:1510 hours, 40 minutes, 15 secondscan always double check we are on the main branch. Let's go ahead and open the graph. Here it is. We detached 11 and
10:40:2210 hours, 40 minutes, 22 secondsmerged it back here. So in this chapter we have successfully implemented ghost text suggestion handle tab key
10:40:3010 hours, 40 minutes, 30 secondssuggestion acceptance. Let me go ahead and mark it. Uh implemented mod k quickedit model firecross scraping
10:40:3810 hours, 40 minutes, 38 secondsfunctions and all other selection based code editing features. Amazing amazing job and see you in the next chapter. In
Chapter 13: 12 Conversation System
10:40:4510 hours, 40 minutes, 45 secondsthis chapter we're going to build the conversation system. We're going to learn how to store conversations and messages, build a chat sidebar with user
10:40:5510 hours, 40 minutes, 55 secondsand assistant messages, create past conversations history dialogue, handle message sending and cancellation functionality, display the thinking
10:41:0310 hours, 41 minutes, 3 secondsindicator while processing and many other things. Let's take a look. So this is the final product and take a look that when I send a message for example,
10:41:1210 hours, 41 minutes, 12 secondshey, how are you? The chat turns into processing state. So that's what we're going to implement. You can see it's now
10:41:2010 hours, 41 minutes, 20 secondsthinking and I have an option to cancel this and then I get back an answer. We are not exactly going to be focusing on
10:41:2810 hours, 41 minutes, 28 secondshow the AI model works nor how it responds. Uh we are more going to focus on the system architecture behind
10:41:3610 hours, 41 minutes, 36 secondsstoring the conversation and the messages itself. So we will also have this history dialogue where we will be
10:41:4310 hours, 41 minutes, 43 secondsable to go in the past. We will be able to of course cancel a message like this. You can see I have canceled my request.
10:41:5110 hours, 41 minutes, 51 secondsSo we spare tokens and we will be able to create a new conversations. So that's the goal. Uh we will see if the actual
10:42:0010 hours, 42 minutesAI responses is something we can build in this chapter or if it's logical to move that into its own chapter. So, for
10:42:0810 hours, 42 minutes, 8 secondsnow, we're just going to focus on making the UI of the chat sidebar as well as the actual back end of uh maintaining, storing, and displaying those messages.
10:42:1810 hours, 42 minutes, 18 secondsSo, let's go ahead and do npm rundev in our project here. And let's refresh localhost 3000.
10:42:2910 hours, 42 minutes, 29 secondsSo, right now, our conversation sidebar is completely empty. And that's perfectly fine because I'm not going to build the UI yet. I want to start with
10:42:3810 hours, 42 minutes, 38 secondsthe back end. I feel like it's always easier that way. Let's go inside of Convex schema and let's build the
10:42:4510 hours, 42 minutes, 45 secondsconversations table. So, make sure you also have npx convex dev running as we
10:42:5210 hours, 42 minutes, 52 secondswill need to synchronize our new schema here. So, I'm going to go ahead and define the table for conversations.
10:43:0110 hours, 43 minutes, 1 secondEach conversation will have its project stored in project ID and then it's going
10:43:0910 hours, 43 minutes, 9 secondsto have a title which is a string created at uh which is not needed.
10:43:1510 hours, 43 minutes, 15 secondsCreation time exists by itself but it will have updated at and we're going only going to have one index which is going to be by project.
10:43:2510 hours, 43 minutes, 25 secondsNow besides conversations we're also going to need messages. So let's go ahead and define the messages table.
10:43:3210 hours, 43 minutes, 32 secondsEach message will have to belong to a certain conversation, meaning it's going to need to have a conversation ID. And
10:43:3910 hours, 43 minutes, 39 secondsfor for easier traversing through, you know, messages and right now if if I want to find out uh if this message
10:43:4710 hours, 43 minutes, 47 secondsbelongs to a project ID, I will first have to fetch the conversation and then fetch the project. similarly to what we
10:43:5410 hours, 43 minutes, 54 secondshad to do with our uh files a lot of times uh specifically for the owner ID right so to avoid that let's add the
10:44:0310 hours, 44 minutes, 3 secondsproject ID directly to messages because it's going to be very useful later so for the role the message can either
10:44:1010 hours, 44 minutes, 10 secondsbelong to a user or an assistant so we are creating a union of those two literal then for the content it's just going to
10:44:1810 hours, 44 minutes, 18 secondsbe a string and then for the status it will be again an optional union of three
10:44:2510 hours, 44 minutes, 25 secondsstates, processing, completed, or cancelled. And let's go ahead and keep it at that. That is good. Now, we're going to have to add two indexes.
10:44:3810 hours, 44 minutes, 38 secondsSo, right here, I'm going to chain by conversation, which is basically using the conversation ID, and by project and
10:44:4610 hours, 44 minutes, 46 secondsstatus, which will use project ID and status. This will help us query uh the messages faster. Great. So, we now have
10:44:5410 hours, 44 minutes, 54 secondsmessages and conversations. Let's go here and confirm all functions are ready. Table indexes have been added and
10:45:0110 hours, 45 minutes, 1 secondno errors have been found. Perfect. Now that we have this, let's go ahead and new file here, conversations.ts.
10:45:1210 hours, 45 minutes, 12 secondsAnd inside of here, we're going to go ahead and import V from convex values, mutation, and query from generated server and verify out from dot /out.
10:45:2410 hours, 45 minutes, 24 secondsWe're going to start with a very simple create mutation.
10:45:2910 hours, 45 minutes, 29 secondsSo, let's go ahead and give it an arguments of project ID and title.
10:45:3410 hours, 45 minutes, 34 secondsAnd let's go ahead and give it a handler. I'm just trying to close this function so we get rid of the syntax
10:45:4210 hours, 45 minutes, 42 secondserror. There we go. So the handler needs access to context and arguments so that we can properly get our identity using
10:45:4910 hours, 45 minutes, 49 secondsverify out. We are then going to get the project using arguments project ID. And as always, let's do a quick check. If
10:45:5710 hours, 45 minutes, 57 secondsthere is no project, project is not found. If the project's owner ID doesn't match the identity subject, this is unauthorized and we shouldn't allow them
10:46:0510 hours, 46 minutes, 5 secondsto do that. And now let's go ahead and build this by using await context database insert
10:46:1410 hours, 46 minutes, 14 secondsinto conversations project ID title and the only thing we're going to need is updated at which can be date.now. That's
10:46:2310 hours, 46 minutes, 23 secondsit. And the conversation ID here is what convex uh context.database.insert
10:46:3010 hours, 46 minutes, 30 secondswill return. This is actually quite important. So make sure that you return the conversation ID because we are going to be using it later on the front end
10:46:4010 hours, 46 minutes, 40 secondswhen we invoke this mutation. We are going to be using it to immediately select that as the active conversation.
10:46:4610 hours, 46 minutes, 46 secondsSo that's why it's important to return the newly created conversation ID because usually in mutations we just do this right. So just make sure you return
10:46:5410 hours, 46 minutes, 54 secondsit this time. And then besides uh creation, we're going to have some quite
10:47:0110 hours, 47 minutes, 1 secondnormal functions such as get by ID. So get by ID
10:47:0910 hours, 47 minutes, 9 secondswill have the arguments ID which is belonging to a conversations ID. And then as usual, we're going to go ahead
10:47:1710 hours, 47 minutes, 17 secondsand get the identity. We're going to get the conversation itself from context database. get conversations arguments
10:47:2410 hours, 47 minutes, 24 secondsID. If there is no conversation, we're going to throw an error. Otherwise, we're going to check. We're going to try
10:47:3310 hours, 47 minutes, 33 secondsto fetch the project using the conversation project ID. If the project doesn't exist, we throw an error.
10:47:3910 hours, 47 minutes, 39 secondsOtherwise, we throw unauthorized to access this project if the owner ID is different than the currently currently
10:47:4510 hours, 47 minutes, 45 secondslogged in identity subject. And last thing, return the conversation. So if it passes all of these checks, it means
10:47:5310 hours, 47 minutes, 53 secondsokay, we can definitely access this conversation. Perfect. So nothing we haven't built yet, right? So now let's
10:48:0110 hours, 48 minutes, 1 secondgo ahead and prepare this again. So I keep copying this because it's always the same code, right? For the get by
10:48:0810 hours, 48 minutes, 8 secondsproject, obviously we are accepting project ID and in here we are going to fetch all conversations that belong to
10:48:1710 hours, 48 minutes, 17 secondsthat project. So we start with our identity and we grab the project using
10:48:2310 hours, 48 minutes, 23 secondsarguments project ID. We do our usual checks. If there is no project, we throw an error. If project's owner ID is different, we throw an error as well.
10:48:3410 hours, 48 minutes, 34 secondsAnd then we're going to do a simple query using our by project index. Right?
10:48:4010 hours, 48 minutes, 40 secondsSo we have defined by project index here. So now we can do return await context database query conversations
10:48:4910 hours, 48 minutes, 49 secondswith index by project query equals project ID arguments project ID order by descending so the newest one are on top
10:48:5810 hours, 48 minutes, 58 secondsand collect all the data. Excellent. So I'm going to start copying entire functions at this point. You can do that too.
10:49:0810 hours, 49 minutes, 8 secondsThe next one will be get messages and we're going to get all messages in a conversation. So change the argument to
10:49:1510 hours, 49 minutes, 15 secondsbe by conversation id. So instead of fetching the project, we can only fetch the conversation right now. So con
10:49:2210 hours, 49 minutes, 22 secondsconversation context database get conversations using arguments do conversation id. Then let's do a usual
10:49:3010 hours, 49 minutes, 30 secondscheck. If there is no conversation, let's throw an error. Conversation not found. And instead of using arguments dot project id, we're going to do
10:49:3910 hours, 49 minutes, 39 secondsconversation.p project ID. And the rest of the checks are exactly the same. And now we have to modify the query, right?
10:49:4610 hours, 49 minutes, 46 secondsBut again, the query is quite easy because we have an index already. So inside of our schema, you can see we have by conversation. So we are simply
10:49:5410 hours, 49 minutes, 54 secondsgoing to query the messages and use the by conversation index. Let's go ahead and do that here. Very simple. Query
10:50:0210 hours, 50 minutes, 2 secondsmessages with index by conversation using the conversation ID arguments conversation ID order by ascending simply because messages are loaded in reverse and collect all the information.
10:50:1410 hours, 50 minutes, 14 secondsThere we go. We just built the entire backend for conversation and messages.
10:50:2010 hours, 50 minutes, 20 secondsSo now let's go ahead and immediately create our features for conversations.
10:50:2610 hours, 50 minutes, 26 secondsSo features conversations. Let me fix the typo here.
10:50:3110 hours, 50 minutes, 31 secondsconversations and let's go ahead and create hooks and inside of here use-con conversations.ts.
10:50:3910 hours, 50 minutes, 39 secondsSo I'm going to start by importing use mutation and use query. I'm going to import API from convex generated API and
10:50:4810 hours, 50 minutes, 48 secondsID from data model. Let's start with a very simple use conversation which
10:50:5410 hours, 50 minutes, 54 secondsaccepts the ID of conversations or null and it returns use query and calls our
10:51:0110 hours, 51 minutes, 1 secondnewly created API conversations get by ID. In case you're getting an error here, it means the conversations functions have not properly registered.
10:51:1110 hours, 51 minutes, 11 secondsMake sure you have created them within the convex folder and make sure you have no errors inside of this. If you do,
10:51:1810 hours, 51 minutes, 18 secondslet's go ahead and do npx convex deb again. And you will see the most latest error message appear here. For example,
10:51:2710 hours, 51 minutes, 27 secondsyou can see I have none, meaning the convex functions are ready and synchronized. Your error will be written here in case you have any. And then you
10:51:3510 hours, 51 minutes, 35 secondscan debug. So just make sure you have conversations inside of the convex folder. And then you should be able to query API. Conversations do get by ID.
10:51:4410 hours, 51 minutes, 44 secondsIt's important to allow ID to be null.
10:51:4610 hours, 51 minutes, 46 secondsSo we can skip this query if we want to do so. Then let's go ahead and do the very same to use messages. So use
10:51:5510 hours, 51 minutes, 55 secondsmessages hook again accepts conversation ID which can be ID conversations or null and it returns a use query API
10:52:0410 hours, 52 minutes, 4 secondsconversations get messages and again checks for the conversation ID.
10:52:0910 hours, 52 minutes, 9 secondsThen let's go ahead and create use conversations hook which will simply load all conversations for a project. So
10:52:1710 hours, 52 minutes, 17 secondsget by project we are calling it use conversations because it makes more semantic sense to be used that way when
10:52:2310 hours, 52 minutes, 23 secondsit comes to our UI blocks. So use query is using API conversations get by project. That's important.
10:52:3310 hours, 52 minutes, 33 secondsAnd then let's go ahead and create another one.
10:52:3810 hours, 52 minutes, 38 secondsuse create conversation and let me just go ahead and close this.
10:52:4210 hours, 52 minutes, 42 secondsThere we go. Use create conversation will not accept any props actually and we're just going to go ahead and return
10:52:5010 hours, 52 minutes, 50 secondsuse mutation API conversations create and I will add to-do add optimistic mutation here simply because it's not
10:52:5810 hours, 52 minutes, 58 secondsrequired but it makes a much nicer user experience when it's instantly created.
10:53:0310 hours, 53 minutes, 3 secondsRight? We actually have a lot of mutations where we have to add optimistic mutation but once you learn how to add them in one place it's almost identical in every other place. Perfect.
10:53:1210 hours, 53 minutes, 12 secondsSo uh those are all the hooks we need to have and now we are ready to revisit our
10:53:2010 hours, 53 minutes, 20 secondsfeatures projects components and I think it is project ID view in here. Let's see. Uh I
10:53:3110 hours, 53 minutes, 31 secondsdon't actually think it's ID view. I think it's id layout right here. You can see we have a div conversation sidebar.
10:53:4010 hours, 53 minutes, 40 secondsSo let's go ahead and this time render an actual component conversations sidebar. Conversation sidebar like this.
10:53:5010 hours, 53 minutes, 50 secondsPass in the project ID and let's go ahead and create it. So I'm going to create the conversation sidebar
10:53:5810 hours, 53 minutes, 58 secondsinside of conversations here. So, I'm going to create components and then I will create conversation-side.tsx.
10:54:0910 hours, 54 minutes, 9 secondsLet's go ahead and quickly create our props. So, conversation sidebar props accepts
10:54:1710 hours, 54 minutes, 17 secondsproject ID. And let's go ahead and return I mean export conversation
10:54:2410 hours, 54 minutes, 24 secondssidebar function. In here, I'm just going to return a div conversation sidebar.
10:54:3110 hours, 54 minutes, 31 secondsThere we go. Now, let's go back to project ID layout and let's import conversation sidebar from features.
10:54:4010 hours, 54 minutes, 40 secondsUh, let me just move it here.
10:54:4410 hours, 54 minutes, 44 secondsAnd let's also do uh one more thing. We can move this allotment this style CSS away from here. And we can add it to our
10:54:5410 hours, 54 minutes, 54 secondsroot layout. So this way, wherever we decide to use it, it's added.
10:55:0110 hours, 55 minutes, 1 secondMaybe it should be before globals, maybe after, I'm not sure. Just make sure it works, right? So nothing should really be changed here. You can see that the only thing has changed is the text here.
10:55:1010 hours, 55 minutes, 10 secondsI think I added an exclamation point now. Great. So how do we develop the conversation sidebar? There's so many elements we have to add. Well, we are in
10:55:1910 hours, 55 minutes, 19 secondsluck because AI SDK, yes, the toolkit we actually used to add providers and various things has a thing called AI
10:55:2810 hours, 55 minutes, 28 secondselements. Using the link on the screen, you can visit that or you can just see the command you have to run. So, they actually offer you two ways of adding
10:55:3610 hours, 55 minutes, 36 secondsthis to your project. You can use npxi elements or chat cli. Since we're using chatn, I'm just going to use chatn. So,
10:55:4510 hours, 55 minutes, 45 secondswhat that's going to do, it's going to add a bunch of elements to our project inside of components here. So, let's go ahead and run that in our project.
10:55:5710 hours, 55 minutes, 57 secondsChatzen. Well, okay. I'm going to use the latest for now. If you want to, you can use the exact same version you did at the beginning of the tutorial. And it's just going to add all AI elements.
10:56:0610 hours, 56 minutes, 6 secondsSo, this is using chats and registry.
10:56:0910 hours, 56 minutes, 9 secondsSo, they are kind of verified components. They're not just random components. So you have to be scared of what's being added to your project. Uh
10:56:1610 hours, 56 minutes, 16 secondsso there's quite a lot of them. So maybe this will take a moment. So let's just go ahead and wait for it to install. If you're being asked if you want to
10:56:2510 hours, 56 minutes, 25 secondsoverride the button, select no simply because we added some custom changes to that button. So it's detecting that it
10:56:3210 hours, 56 minutes, 32 secondsalready exists, but we don't have to override it. So select no. If you selected yes, it's not a big problem.
10:56:3910 hours, 56 minutes, 39 secondsYou can always just revert that using git or you can just copy the button like command Z to what it was before.
10:56:4510 hours, 56 minutes, 45 secondsBasically, we added icon extra small variant and the highlight variant to our button. But you can see besides that
10:56:5310 hours, 56 minutes, 53 secondseverything else is fine. Let's take a look at all the components that were added. So you can find all of them in one place. AI elements. Keep in mind
10:57:0110 hours, 57 minutes, 1 secondthat some of them might be a little bit buggy when it comes to type errors. I've noticed that myself. But most of them should be completely fine. The reason
10:57:1010 hours, 57 minutes, 10 secondsI'm telling you that they might be buggy is because uh this will maybe um cause build errors when you try to
10:57:1910 hours, 57 minutes, 19 secondsdeploy, right? So just be mindful of that. But we're not going to concern ourselves with that right now. We're going to go ahead and build. So you can
10:57:2810 hours, 57 minutes, 28 secondssee I have 40 un saved changes here. And you can see besides layout, schema, conversations and some generated files
10:57:3610 hours, 57 minutes, 36 secondshere. Uh all of other ones are source components AI elements, right? And use conversation conversation cybar. Okay.
10:57:4610 hours, 57 minutes, 46 secondsSo you should have well you shouldn't have the exact amount of changes, but you know maybe you did something that I didn't but yeah that's how many files
10:57:5410 hours, 57 minutes, 54 secondshave been added. Also maybe in the future more files or less files will be added. So yes, don't don't take this number too seriously. Let's go ahead now
10:58:0310 hours, 58 minutes, 3 secondsand go back inside of the conversation sidebar. So that's inside of features conversations components conversation
10:58:1010 hours, 58 minutes, 10 secondssidebar. And in here I want to start importing some things. So we have ID imported. But now I'm going to add from
10:58:1810 hours, 58 minutes, 18 secondscomponents AI elements conversation conversation content and conversation scroll button. Then I'm going to go
10:58:2510 hours, 58 minutes, 25 secondsahead and add message content response actions and actions and action from AI
10:58:3310 hours, 58 minutes, 33 secondselements message. After that, I'm going to import prompt input body footer
10:58:4010 hours, 58 minutes, 40 secondssubmit text area tools and type prompt input message from AI elements prompt input. So I'm going to remove all the
10:58:4810 hours, 58 minutes, 48 secondsgaps between the imports now because we know what they are. And since I'm wrapping up the imports, I'm just going to add all of them. So besides this, I
10:58:5710 hours, 58 minutes, 57 secondswill also have KY package, toast from Soner, use state from React, and from Lucid icon, I'm going to have copy icon,
10:59:0510 hours, 59 minutes, 5 secondshistory icon, loader icon, and plus icon. All right. And uh let's see. I don't think we need to use client here
10:59:1410 hours, 59 minutes, 14 secondsbecause it already is within a client component. Let's go ahead and add button from components UI button.
10:59:2210 hours, 59 minutes, 22 secondsAnd I think that uh that's it for components. Uh now let's go ahead and import all hooks from use conversations.
10:59:3110 hours, 59 minutes, 31 secondsUse conversation, use conversations, use create conversation, and use messages.
10:59:3610 hours, 59 minutes, 36 secondsSo this is a hook we've developed before we started building the conversation sidebar. So you should have all of these
10:59:4210 hours, 59 minutes, 42 secondshere. Great. Let's see. Uh what should I do next?
10:59:5110 hours, 59 minutes, 51 secondsUh inside of convex I'm going to create a constants.ts and I'm going to prepare the following
10:59:5910 hours, 59 minutes, 59 secondsdefault conversation title. I'm going to make it new conversation. That's what I'm going to do.
11:00:0711 hours, 7 secondsSo just save that and nothing more. All right. And now I'm going to go ahead and
11:00:1411 hours, 14 secondsbuild the UI. So conversations sidebar conversation that sidebar.
11:00:2111 hours, 21 secondsAnd we're going to start by giving this div a class name flex flex column height full
11:00:2911 hours, 29 secondsand background sidebar. Going to open a new div here with a class name height of 35 pixels. And we've already learned we
11:00:3711 hours, 37 secondscan write that as 8.75. Maybe I will learn at the end of the tutorial. Flex
11:00:4511 hours, 45 secondsitems center justify between border bottom. And that's it. And another div
11:00:5411 hours, 54 secondsinside in which we are going to simply render the default conversation title which we can import from convex
11:01:0311 hours, 1 minute, 3 secondsconstants. So default conversation title and this will have a class name
11:01:1411 hours, 1 minute, 14 secondstext small truncate and PL of three.
11:01:2211 hours, 1 minute, 22 secondsLet's go ahead and start actually taking a look here. Whoops. This is the final product. Not that this. So now you can
11:01:3011 hours, 1 minute, 30 secondssee I have a text which says new conversation at the top. I'm going to snap this and I'm going to expand this so I can focus on this as much as
11:01:3911 hours, 1 minute, 39 secondspossible. So there we go. New conversation is now written at the top because that is right here the constant we are exporting. Great.
11:01:4911 hours, 1 minute, 49 secondsAnd below this let's open a new div with a class name flex
11:01:5811 hours, 1 minute, 58 secondsitems center px1 and gap one. And in here, we're going to render a button.
11:02:0611 hours, 2 minutes, 6 secondsThis button will be a history icon renderer. Like so. Again, I'm just going to snap this, expand this so I can focus
11:02:1511 hours, 2 minutes, 15 secondson that. And let's start giving this button some props. So, it will have size icon extra small and variant of
11:02:2411 hours, 2 minutes, 24 secondshighlight. And the history icon will have a class name size 3.5. So, that's what it should look like. Then I'm going
11:02:3211 hours, 2 minutes, 32 secondsto duplicate that and the bottom one is going to have a plus icon from Lucid React.
11:02:4111 hours, 2 minutes, 41 secondsAnd then after that we are let's see um
11:02:4911 hours, 2 minutes, 49 secondslet's keep it like that. Okay. So yes, we're going to have two of them. This is kind of the the history and this is the plus button.
11:02:5911 hours, 2 minutes, 59 secondsThis uh this creates the new one.
11:03:0211 hours, 3 minutes, 2 secondsSo now uh outside of this div right here in the place of the text let's add the
11:03:0911 hours, 3 minutes, 9 secondsconversation component let's give it a class name flex one
11:03:1711 hours, 3 minutes, 17 secondsand inside let's add conversation content and then inside of here we have to basically render the messages.
11:03:2711 hours, 3 minutes, 27 secondsSo how do we render the messages? Well, before we can do that, we have to display
11:03:3511 hours, 3 minutes, 35 secondsthe the prompt input that will allow us to create new messages, right? So, the only thing we also have to add within
11:03:4211 hours, 3 minutes, 42 secondsthe conversation composition is conversation scroll button and it's a self-closing tag like this. And then
11:03:5111 hours, 3 minutes, 51 secondsoutside of conversation, create a div with a class name padding three. And in
11:03:5711 hours, 3 minutes, 57 secondshere we're going to add prompt input like so. The prompt input will have
11:04:0411 hours, 4 minutes, 4 secondsonsubmit and it's just going to be an empty arrow function. And it will also have a class name margin top to rounded full.
11:04:1711 hours, 4 minutes, 17 secondsLet's go ahead and add this.
11:04:2011 hours, 4 minutes, 20 secondsActually, this rounded full doesn't do anything. I think when I save, I think it's exactly the same.
11:04:2611 hours, 4 minutes, 26 secondsBesides that, uh let's also prepare a value of empty. Can I do that? Okay.
11:04:3511 hours, 4 minutes, 35 secondsUh that's not where I do that. Instead, inside of prompt input, we render prompt input body.
11:04:4411 hours, 4 minutes, 44 secondsAnd then I do prompt input text area.
11:04:5011 hours, 4 minutes, 50 secondsAnd this is where I can add a placeholder such as ask Polaris anything.
11:04:5811 hours, 4 minutes, 58 secondsLet me go ahead and expand this a bit.
11:05:0211 hours, 5 minutes, 2 secondsUh let me see if I did the composition correctly. We have prompt input prompt input body and then prompt input text
11:05:1111 hours, 5 minutes, 11 secondsarea. Okay, we are here also going to have on change which for now is just going to be an
11:05:2011 hours, 5 minutes, 20 secondsempty arrow function value which is going to be an empty string and disabled which will be explicitly false and this is actually a self-closing tab.
11:05:3111 hours, 5 minutes, 31 secondsThere we go.
11:05:3411 hours, 5 minutes, 34 secondsThen within outside of prompt prompt input body we will add prompt input footer
11:05:4411 hours, 5 minutes, 44 secondsand prompt input tools which is a self-closing tag simply because usually you can open it and put things inside
11:05:5111 hours, 5 minutes, 51 secondsbut in this case I'm just using it to fill uh the area the empty area and prompt input submit is also a
11:05:5811 hours, 5 minutes, 58 secondsself-closing one and you can leave as the default. But for now, let's just
11:06:0611 hours, 6 minutes, 6 secondsgo ahead and make sure disabled is false and status is ready
11:06:1311 hours, 6 minutes, 13 secondssimply so we are aware that it can have different props here. Uh okay. So we just developed this. Now let's go ahead
11:06:2111 hours, 6 minutes, 21 secondsand let's create uh a function that will help us create new conversations.
11:06:2811 hours, 6 minutes, 28 secondsSo I'm going to go ahead and add our use create conversation. So con create
11:06:3611 hours, 6 minutes, 36 secondsconversation conversation use create conversation hook
11:06:4311 hours, 6 minutes, 43 secondsand then I will also prepare use state here
11:06:5211 hours, 6 minutes, 52 secondssomething called selected conversation ID and set selected conversation ID
11:07:0011 hours, 7 minutesand by default I'm going to make it null.
11:07:0411 hours, 7 minutes, 4 secondsSo since these are long words, I'm just going to collapse the state like this.
11:07:0811 hours, 7 minutes, 8 secondsAnd the type will be basically an ID of conversations or null.
11:07:1911 hours, 7 minutes, 19 secondsLet's go ahead and keep that. Okay.
11:07:2411 hours, 7 minutes, 24 secondsAnd now let's go ahead and implement constant handle create conversation.
11:07:3111 hours, 7 minutes, 31 secondsis going to be an asynchronous method. We're going to open a try and catch.
11:07:3911 hours, 7 minutes, 39 secondsLet's go ahead and grab the conversation ID from await create conversation.
11:07:4611 hours, 7 minutes, 46 secondsInside of create conversation, let me go ahead and expand this a little bit.
11:07:5011 hours, 7 minutes, 50 secondsWe're going to pass in the project ID and the title which will be default conversation title. There we go. And
11:07:5811 hours, 7 minutes, 58 secondsthen immediately after it has been created, set selected conversation ID to be the new conversation ID. Let's call
11:08:0511 hours, 8 minutes, 5 secondsthis new conversation ID. And then we can pass that here. There we go. And return new conversation ID from this
11:08:1411 hours, 8 minutes, 14 secondsmethod as well. In the catch, we can just do toast error unable
11:08:2011 hours, 8 minutes, 20 secondsto create new conversation and return null.
11:08:2611 hours, 8 minutes, 26 secondsAll right. So that's a method handle create conversation and that's why I was telling you that it is important that in API
11:08:3411 hours, 8 minutes, 34 secondsconversations create we return the conversation ID because this is where we are using it right we need it here so we
11:08:4311 hours, 8 minutes, 43 secondscan set the selected conversation ID to the newest one. All right so let's go
11:08:5011 hours, 8 minutes, 50 secondsahead and now add this to our button which has the plus icon. So in here I'm just going to do on click handle create
11:08:5811 hours, 8 minutes, 58 secondsconversation. So the UI actually won't be too noticeable right now. So I would
11:09:0511 hours, 9 minutes, 5 secondsrather we go to dashboardconvex.dev and head into our project database. In here you can see I have conversations
11:09:1311 hours, 9 minutes, 13 secondsand the table is completely empty. So if I go ahead and click on the plus button right here, as I said, nothing much
11:09:1911 hours, 9 minutes, 19 secondschanges here. But you can see something obviously changes here. And to prove
11:09:2611 hours, 9 minutes, 26 secondsthat in the UI too, let's go ahead and go up here where we render the default conversation title and do the following.
11:09:3711 hours, 9 minutes, 37 secondsTry and load active conversation.
11:09:4011 hours, 9 minutes, 40 secondsUh actually, let's see. We don't have Okay. Uh, one thing I forgot. I thought
11:09:4811 hours, 9 minutes, 48 secondsI could do it from this, but I can't. So now that we have selected conversation
11:09:5411 hours, 9 minutes, 54 secondsID, what we can do is compute the active conversation ID and we can make that
11:10:0311 hours, 10 minutes, 3 secondseither selected conversation ID or we can get all conversations using use
11:10:1111 hours, 10 minutes, 11 secondsconversations for this project ID. So we already have that hook and then grab the first conversation.
11:10:2111 hours, 10 minutes, 21 secondsSo question mark first in the array and then grab its ID or fall back to null as
11:10:2911 hours, 10 minutes, 29 secondsthe last resort. So why what is this? If the user manually selects a conversation, we're going to compute
11:10:3611 hours, 10 minutes, 36 secondsthat. If the user just refreshed the page, we're going to fall back to picking this project's latest
11:10:4411 hours, 10 minutes, 44 secondsconversation. And if that doesn't exist, we're going to fall back to null. So, make sure you've added use conversations
11:10:5211 hours, 10 minutes, 52 secondsfor this project ID hook. Use conversation which accepts project ID.
11:10:5811 hours, 10 minutes, 58 secondsAnd let's go ahead and see it calls a function get by project. So, that's the one we are calling here. So we get an array of conversations.
11:11:0711 hours, 11 minutes, 7 secondsNow that we have active conversation ID, we can get the actual active conversation using use conversation and
11:11:1711 hours, 11 minutes, 17 secondspass in the active conversation ID. Let me go ahead and uh active conversation ID. There we go.
11:11:2911 hours, 11 minutes, 29 secondsAnd now by using active conversation we can go ahead and try and use active conversation.title
11:11:3711 hours, 11 minutes, 37 secondsor the default conversation title like this. So let's recap what we just did.
11:11:4511 hours, 11 minutes, 45 secondsWe com we are now computing an active conversation ID from three sources. The priority is the selected conversation
11:11:5411 hours, 11 minutes, 54 secondsID. This means the user directly uh used the history dialogue to select a conversation. But if the user never did
11:12:0311 hours, 12 minutes, 3 secondsthat, meaning they just jumped on this project's page, we're going to fall back to loading all conversations for this
11:12:1211 hours, 12 minutes, 12 secondsproject and simply picking the latest convers conversation that the user engaged into. And if that doesn't exist,
11:12:2011 hours, 12 minutes, 20 secondswe are going to fall back to null. No conversations available. Once we get a computed active conversation ID, we use
11:12:2811 hours, 12 minutes, 28 secondsit as a param for use conversation hook which fetches by ID. And then we finally have active conversation in here. And then if it exists, we render its title.
11:12:4011 hours, 12 minutes, 40 secondsOtherwise, we render the default conversation title to create an illusion that a new conversation is already
11:12:4611 hours, 12 minutes, 46 secondscreated, but we actually save some uh space in our database. So, it seems like this was just created, but it actually
11:12:5411 hours, 12 minutes, 54 secondswasn't, right? But now, uh, if you go ahead and do the following. So, do a hard refresh. Okay.
11:13:0611 hours, 13 minutes, 6 secondsAnd, well, okay, there's an easy way to test. Change this to empty like this.
11:13:1611 hours, 13 minutes, 16 secondsAnd let's refresh.
11:13:1811 hours, 13 minutes, 18 secondsWhy does it still say oh okay uh create a new project
11:13:2611 hours, 13 minutes, 26 secondsuh and go into that project? You can see it says empty right now. So this is the default state right? Not a single
11:13:3311 hours, 13 minutes, 33 secondsconversation for this project. But when I click on the plus button it says new conversation because that is the newest
11:13:4011 hours, 13 minutes, 40 secondscreated one. So if I go ahead and say uh a convo about things
11:13:4711 hours, 13 minutes, 47 secondsand save it immediately reflects here a convo about things. Great. And you can see that the next time you visit so I
11:13:5611 hours, 13 minutes, 56 secondsrefresh will immediately you can see for a brief second it said empty and then it fall back it fell back to this right. So
11:14:0511 hours, 14 minutes, 5 secondsit it will always pick the recent conversation that just existed. So now you can bring this to default conversation title. So we create an
11:14:1311 hours, 14 minutes, 13 secondsillusion that every time you know the user creates a new project and goes into it, we already have a conversation for
11:14:2011 hours, 14 minutes, 20 secondsthem. We actually don't. We didn't create any third conversation as you can see here. But we give the user an illusion like oh yeah we did it right.
11:14:3011 hours, 14 minutes, 30 secondsBut we save time and it looks good. It's a good user experience. All right. So now that we have the active conversation, we can actually do uh more
11:14:3911 hours, 14 minutes, 39 secondsthings. For example, we can load all messages. So down here, how about we add all conversation messages using use
11:14:4611 hours, 14 minutes, 46 secondsmessages active conversation ID. And now that we have conversation messages, let's go ahead and do another computed
11:14:5511 hours, 14 minutes, 55 secondsvalue. Is any message currently processing? So is processing will amount to true if any of the current
11:15:0311 hours, 15 minutes, 3 secondsconversations messages have a status of processing.
11:15:0711 hours, 15 minutes, 7 secondsIf it does, if they do, we are simply going to not allow the user to send any more messages until that is resolved and
11:15:1611 hours, 15 minutes, 16 secondsthe user will be able to cancel a request. So if it is in processing status, the user will always be able to
11:15:2311 hours, 15 minutes, 23 secondsmanually stop that status. So it's never kind of uh locked in that state.
11:15:3011 hours, 15 minutes, 30 secondsSo since we already are here, we can compute is processing even though we're not going to use it right now. Great.
11:15:3711 hours, 15 minutes, 37 secondsNow that we have the conversation messages, we can actually go ahead and develop the conversation content because
11:15:4611 hours, 15 minutes, 46 secondswe stopped here, right? Because we didn't have anything to load. So, conversation messages question mark get
11:15:5311 hours, 15 minutes, 53 secondsthe message message index and in here render the message composition. Let's go ahead and give it
11:16:0211 hours, 16 minutes, 2 secondsa key of message underscore id and from message roll then a message content. So,
11:16:1111 hours, 16 minutes, 11 secondswe're just continuing with the composition. If message status is equal to processing, in that case we're going
11:16:1811 hours, 16 minutes, 18 secondsto go ahead and open a thinary and we're going to add a div oops a loader icon
11:16:2711 hours, 16 minutes, 27 secondsand span thinking as in we are loading this message, right? The AI is still processing. It still hasn't given us the
11:16:3511 hours, 16 minutes, 35 secondscorrect answer. And for this div, we're going to give it flex items center gap 2
11:16:4211 hours, 16 minutes, 42 secondsand text muted foreground. And for the loader icon, class name size 4 and animate spin. And now to finish the
11:16:5111 hours, 16 minutes, 51 secondsturnary in the alternative way, we're going to use message response to simply render message.content.
11:16:5811 hours, 16 minutes, 58 secondsThe message response actually uses streamdown. So it will automatically handle markdown or anything else that AI
11:17:0711 hours, 17 minutes, 7 secondsthrows at us. So it's such little work for a great experience.
11:17:1311 hours, 17 minutes, 13 secondsGreat. And now let's go ahead outside of message content and let's check if message roll is assistant. In that case
11:17:2311 hours, 17 minutes, 23 secondsuh let's also check if message ro is assistant and message.st status is completed.
11:17:3011 hours, 17 minutes, 30 secondsAnd if message index is equal to conversation messages
11:17:3811 hours, 17 minutes, 38 secondsquestion mark length or fallback to zero minus one and
11:17:4611 hours, 17 minutes, 46 secondslet me expand further so you can see how it looks like. Okay. Render message actions.
11:17:5511 hours, 17 minutes, 55 secondsactions, then a single message action with a copy icon.
11:18:0411 hours, 18 minutes, 4 secondsSo if the AI has responded, let's go ahead and give the user an ability to copy the answer. This is a common thing
11:18:1111 hours, 18 minutes, 11 secondswe can see, right? So navigator clipboard write text message content and give it a label of copy.
11:18:2211 hours, 18 minutes, 22 secondsGreat. There we go.
11:18:2411 hours, 18 minutes, 24 secondsSo right now this is ready to render but we are not actually creating any messages.
11:18:3311 hours, 18 minutes, 33 secondsSo let's go ahead and see what we can uh do right now. I'm trying to make the most out of the things we've already built. Let's go ahead and use this is
11:18:4211 hours, 18 minutes, 42 secondsprocessing to see it behave visually. So in the prompt input submit if is
11:18:4911 hours, 18 minutes, 49 secondsprocessing disabled will be false otherwise it's going to be true and the status will check if is
11:18:5811 hours, 18 minutes, 58 secondsprocessing streaming mode on otherwise undefined.
11:19:0411 hours, 19 minutes, 4 secondsSo now if I go ahead let's go ahead and just focus on this button here. If I go ahead and find is processing constant
11:19:1311 hours, 19 minutes, 13 secondsand if I manually change it, let me go ahead and change it to true.
11:19:1911 hours, 19 minutes, 19 secondsYou can see it will kind of have a button that indicates to the user they can click to stop this, right? But if
11:19:2611 hours, 19 minutes, 26 secondsyou revert it, obviously it's not going to have anything. Great. Now, let's create an ability to actually submit a message. So, in order to do that, we
11:19:3511 hours, 19 minutes, 35 secondsneed to add a new state here. So input set input use state and empty string.
11:19:4211 hours, 19 minutes, 42 secondsAnd let's go ahead and allow the user to fill that input in the prompt input text area.
11:19:5011 hours, 19 minutes, 50 secondsSo set input get the event. Oops. Event target value.
11:19:5811 hours, 19 minutes, 58 secondsThe value will then be input. Disabled will be is processing here. Great. And
11:20:0511 hours, 20 minutes, 5 secondsnow that we have input, we're going to modify the disabled mode. So if we are processing, it's going to be false.
11:20:1411 hours, 20 minutes, 14 secondsOtherwise, it's not just going to fall back to true. Only if input is not here, it's going to fall back to true. You can see now it's disabled. But if I start
11:20:2311 hours, 20 minutes, 23 secondstyping, it's enabled. Right? So that's the logic we are trying to achieve.
11:20:2911 hours, 20 minutes, 29 secondsAll right. Now that we have that, we have to develop handle submit method. So change this to handle submit. And now
11:20:3811 hours, 20 minutes, 38 secondslet's go ahead and implement that. So I'm going to do that right below our handle create conversation const handle
11:20:4611 hours, 20 minutes, 46 secondssubmit asynchronous method. And in here I will accept a message to be a type of prompt input message.
11:20:5511 hours, 20 minutes, 55 secondsLet's go ahead and do uh actually no need to do this right now. So if
11:21:0311 hours, 21 minutes, 3 secondsprocessing and no new message this is just a stop function. So yes if we if
11:21:1211 hours, 21 minutes, 12 secondsthe user just send a message and we are processing and the user attempts to
11:21:1911 hours, 21 minutes, 19 secondsclick on the stop sign here that will trigger handle submit. So the message will actually be empty. So we can detect
11:21:2811 hours, 21 minutes, 28 secondsthat by checking if is processing and if there is no message.ext
11:21:3411 hours, 21 minutes, 34 secondsin that scenario we know to do await handle cancel. We don't yet have this function but that's what we're supposed
11:21:4211 hours, 21 minutes, 42 secondsto do. And then we are going to reset the input to an empty string and return.
11:21:4911 hours, 21 minutes, 49 secondsSo that's a scenario for later. It's going to make more sense then. Now let's go ahead and see to which conversation should we submit this message. We're
11:21:5811 hours, 21 minutes, 58 secondsdefining a conversation ID here and by default we assume it's going to be the active conversation ID.
11:22:0511 hours, 22 minutes, 5 secondsBut the active conversation ID can be null. So if there is no conversation ID, we're going to create a new one. So
11:22:1411 hours, 22 minutes, 14 secondsconversation id will be await handle conversation handle create conversation a function from above and if even then
11:22:2411 hours, 22 minutes, 24 secondsthere is no conversation ID we are simply going to break this method. So this is a scenario if the user just
11:22:3311 hours, 22 minutes, 33 secondsuh got here in a new project and doesn't click create a new conversation. So right now it's sending a message to
11:22:4111 hours, 22 minutes, 41 secondsnowhere. So we just go ahead and create a new conversation for them and this handle conversation method will automatically select it as the active
11:22:5011 hours, 22 minutes, 50 secondsone. So it kind of does a lot of job for us.
11:22:5411 hours, 22 minutes, 54 secondsNow finally once we have that we can go ahead and trigger ingest function via
11:23:0011 hours, 23 minutesAPI. So now we open our try and catch method with toast error message failed to send.
11:23:1111 hours, 23 minutes, 11 secondsAnd in here we do await ky.post API messages which we have to develop.
11:23:1911 hours, 23 minutes, 19 secondsAnd the payload we're going to send is the conversation ID and the message me of message.ext
11:23:2711 hours, 23 minutes, 27 secondslike this. So now we have to develop API messages.
11:23:3211 hours, 23 minutes, 32 secondsSo now we have to implement this API route. Let's go ahead and do source app
11:23:3811 hours, 23 minutes, 38 secondsAPI. And I'm going to open a new folder uh called
11:23:4511 hours, 23 minutes, 45 secondsmessages. And inside of messages, create a route.ts.
11:23:5211 hours, 23 minutes, 52 secondsAnd let's start by importing zod next response and out from clerk
11:23:5811 hours, 23 minutes, 58 secondsnext.js server. Let's go ahead and quickly define our request schema using zod. So we expect conversation ID and
11:24:0711 hours, 24 minutes, 7 secondsmessage. If you take a look at conversation sidebar, you can see that that's what we send conversation ID and message. So since we
11:24:1611 hours, 24 minutes, 16 secondsare not doing any zod validation on the front end, let's this time do it on the back end. If you remember during our extension creation, we did the opposite.
11:24:2311 hours, 24 minutes, 23 secondsSo I just want to show you how you can do it on the back end here. This is the request schema. So now when we define our post method here, asynchronous post
11:24:3311 hours, 24 minutes, 33 secondsrequest and we go ahead and grab our user ID using clerk's await out, we throw an error unauthorized.
11:24:4311 hours, 24 minutes, 43 secondsIf user ID does not exist, we can go ahead and extract body from a weight request JSON.
11:24:5211 hours, 24 minutes, 52 secondsAnd then we can go ahead and parse request schema.parse parse body and in here we get almost
11:25:0111 hours, 25 minutes, 1 secondcertain conversation ID and message because this will throw if it doesn't pass the validation. So if this isn't a
11:25:0811 hours, 25 minutes, 8 secondsstring and this isn't a string, it's going to break. Great. So now we kind of have a problem because what we have to
11:25:1711 hours, 25 minutes, 17 secondsdo in this API post request is somehow call convex mutation and convex query
11:25:2611 hours, 25 minutes, 26 secondsand also invoke injest background jobs because invest inest background jobs are going to serve uh the purpose of being
11:25:3511 hours, 25 minutes, 35 secondsthe agent who is going to call tools within a loop to give us an answer. and
11:25:4311 hours, 25 minutes, 43 secondsconvex is our database. So how do we do this? Because we are now in an API route
11:25:4911 hours, 25 minutes, 49 secondsof Nex.js and we know that usually we uh access convex through their set of hooks. Well, Convex actually offers
11:25:5811 hours, 25 minutes, 58 secondssomething called convex client. So if you go inside of source lib and create a
11:26:0411 hours, 26 minutes, 4 secondsnew file called convex-client.ts, DS
11:26:1011 hours, 26 minutes, 10 secondsyou can import convex http client from convex forward slash browser and then in
11:26:1811 hours, 26 minutes, 18 secondshere all you have to do is export convex new convex http client and the only prop
11:26:2511 hours, 26 minutes, 25 secondsit accepts is next public convex url. So just make sure that inside of your environment.local you have next public convex url.
11:26:3611 hours, 26 minutes, 36 secondsPerfect.
11:26:3811 hours, 26 minutes, 38 secondsAnd now for example let's attempt to load the conversation
11:26:4511 hours, 26 minutes, 45 secondsusing this conversation ID. So let's call a convex query. How would we do that? Const conversation will be await
11:26:5411 hours, 26 minutes, 54 secondsconvex which we can now import from lib convex client doquery.
11:27:0111 hours, 27 minutes, 1 secondAnd in here we can call our API as usual. The problem is what do we call?
11:27:1011 hours, 27 minutes, 10 secondsWell, the way I like to do this is by creating another set of convex functions specifically
11:27:1911 hours, 27 minutes, 19 secondsdesigned for calling convex from a third-party source, right? For from not using their hooks. So, I'm going to go
11:27:2811 hours, 27 minutes, 28 secondsahead inside of convex here and I will call those system functions.
11:27:3411 hours, 27 minutes, 34 secondsAnd now these system functions are a bit tricky. For example, I want to implement
11:27:4111 hours, 27 minutes, 41 secondsget conversation by ID. So I'm going to import query. I'm going to define the arguments. I'm going to prepare an asynchronous handler here. The arguments
11:27:5011 hours, 27 minutes, 50 secondswill be conversation ID which is convex values ID conversations.
11:27:5911 hours, 27 minutes, 59 secondsRight? So nothing unusual so far. We accept context and arguments and then from here return await context database
11:28:0811 hours, 28 minutes, 8 secondsget arguments conversation ID and that seems simple enough right so I saved
11:28:1511 hours, 28 minutes, 15 secondsthis file I'm going to check here I can see all of my convex functions are ready so nothing unusual right and in here I
11:28:2411 hours, 28 minutes, 24 secondsshould now fully be able to do API uhsystem get conversation
11:28:3211 hours, 28 minutes, 32 secondsby ID and in here I can pass conversation ID to be conversation ID
11:28:3911 hours, 28 minutes, 39 secondsfrom above as we have to cast the type ID of conversations.
11:28:4611 hours, 28 minutes, 46 secondsSo is there anything wrong with this?
11:28:5011 hours, 28 minutes, 50 secondsWell in theory no right just make sure you import this ID. But here's the thing. I'm not comfortable with the idea
11:28:5911 hours, 28 minutes, 59 secondsof there being what's essentially an API route. You can think of convex functions as API routes. I'm not saying it's
11:29:0711 hours, 29 minutes, 7 secondsexactly the same thing. I'm just personally not comfortable with the idea of having a fully unprotected out uh
11:29:1611 hours, 29 minutes, 16 secondsunprotected route like this. And you might think, okay, so we just do our verify out, right? Well, not exactly
11:29:2511 hours, 29 minutes, 25 secondsbecause uh we will be calling these system functions from various things.
11:29:3211 hours, 29 minutes, 32 secondsSome will be API routes. Uh some will be background jobs, right? And even if we are able to extract the user token and
11:29:4111 hours, 29 minutes, 41 secondsthen we pass it along here, still think of this as something an attacker can get
11:29:4711 hours, 29 minutes, 47 secondsaccess to. Imagine your attacker getting access to this API. It's obviously not that simple because we uh initialize the
11:29:5511 hours, 29 minutes, 55 secondsconvex with our environment keys and everything, right? But just always think about it like that. We shouldn't allow them to just enter a user token here.
11:30:0711 hours, 30 minutes, 7 secondsAnd even if we did, user tokens can expire, change, and things like that. So the solution I have thought of is to
11:30:1711 hours, 30 minutes, 17 secondsimplement something called an internal key and we are going to use that as
11:30:2411 hours, 30 minutes, 24 secondssimple as this. After we check one authentication we're going to check for the internal key. Do we have process
11:30:3211 hours, 30 minutes, 32 secondsenvironment convex internal key? And if we don't we're going to throw internal key is not
11:30:4111 hours, 30 minutes, 41 secondsconfigured. I'm not going to allow you to make requests to this API. Functions,
11:30:4811 hours, 30 minutes, 48 secondsright? So now let's go inside of environment uh.local here and let's define the convex internal key. So I'm
11:30:5711 hours, 30 minutes, 57 secondsgoing to go to the top here and I'm going to add convex internal
11:31:0411 hours, 31 minutes, 4 secondskey and I'm going to give it your secret key here value. Please change this to
11:31:1111 hours, 31 minutes, 11 secondssomething else, especially in production. This is just for a tutorial.
11:31:1511 hours, 31 minutes, 15 secondsIn fact, just smash your keyboard instead of writing your secret key here.
11:31:2111 hours, 31 minutes, 21 secondsYes, this will work simply because it's a string. But please don't forget, and then publish this. Okay. And now that
11:31:2811 hours, 31 minutes, 28 secondsyou have that, copy it, save your environment local, go inside of your convex, go inside of your settings,
11:31:3711 hours, 31 minutes, 37 secondsenvironment variable, add, and just add it here to and click save. And make sure
11:31:4311 hours, 31 minutes, 43 secondsit's the same. Okay. And now let's go ahead inside of our system.ts ts and
11:31:5211 hours, 31 minutes, 52 secondslet's implement a simple helper function called validate internal key again
11:32:0011 hours, 32 minutesinternal key using process. environment convex internal key like that and if the
11:32:0611 hours, 32 minutes, 6 secondskey that we pass to this function doesn't match what we have in our environment throw an error. And now that
11:32:1611 hours, 32 minutes, 16 secondswe have validate internal key, we can finally use it inside of our mutations right here.
11:32:2611 hours, 32 minutes, 26 secondsSo now I'm going to add internal key here to be a type of required string.
11:32:3511 hours, 32 minutes, 35 secondsAnd now whoever attempts to call my get conversation by ID which is in my system
11:32:4311 hours, 32 minutes, 43 secondshere. So I'm purposely separating this from all others because others are using normal AL checks. This one is using a special internal key validation check.
11:32:5311 hours, 32 minutes, 53 secondsAnd you can call this key whatever you want, right? If you want, you can give it a little prefix like P as in Polaris
11:33:0111 hours, 33 minutes, 1 secondinternal key, right? So you know this is not uh something that you should expect.
11:33:0711 hours, 33 minutes, 7 secondsIn fact, that might be a good idea like Polaris convex internal key. I'm purposely going to change it to this and I want you to
11:33:1511 hours, 33 minutes, 15 secondsdo the same simply so you see all the places it's being used. Okay. So change it here in route. We changed it in
11:33:2311 hours, 33 minutes, 23 secondssystem. We are now going to change in this kind of environment.local. So polaris convex internal key. And then
11:33:3011 hours, 33 minutes, 30 secondslast thing go ahead and change it in your environment variables. Click on edit and change this to polaris convex
11:33:3711 hours, 33 minutes, 37 secondsinternal key. There we go. This way, even if Convex decides to add a variable like that in the future, it will not
11:33:4511 hours, 33 minutes, 45 secondsconflict because this one has a prefix of our own project here. So, we know this is something we use, something that's important for us. So, this is no
11:33:5211 hours, 33 minutes, 52 secondslonger just a random unauthenticated function. And now we can safely, in my opinion, safely call and query convex uh
11:34:0311 hours, 34 minutes, 3 secondsthrough various third-party apps. So, let's pass in the internal key. There we go. And now we actually have access to
11:34:1211 hours, 34 minutes, 12 secondsthis conversation. Great. And let's go ahead and do the usual checks now. So if there is no conversation, I'm going to
11:34:2111 hours, 34 minutes, 21 secondsreturn next response. JSON conversation was not found. And now that I have the conversation, I can get the project ID.
11:34:3011 hours, 34 minutes, 30 secondsSo, what I want to do now is I want to create the user message. I'm going to do to-do
11:34:3911 hours, 34 minutes, 39 secondscheck for processing messages. We're going to do that in a moment, but I just want to show you how like, hey, let's go ahead and create a user message.
11:34:4911 hours, 34 minutes, 49 secondsTo create a message, we again need to visit our system here and let's go ahead and create a new mutation. create
11:34:5811 hours, 34 minutes, 58 secondsmessage is going to accept a whole bunch of arguments. Internal key, conversation
11:35:0511 hours, 35 minutes, 5 secondsID, project ID, role of the message, content, and the status with all the uh
11:35:1311 hours, 35 minutes, 13 secondsoptions it accepts. Make sure this matches exactly what you have in your schema defined table. So the status
11:35:2111 hours, 35 minutes, 21 secondsneeds to match otherwise your function will be able to create an error in the database which is not something we want
11:35:2811 hours, 35 minutes, 28 secondsof course. And then let's go ahead and create a handler.
11:35:3311 hours, 35 minutes, 33 secondsLet's go ahead and validate the internal key. And once we do that, let's simply
11:35:4111 hours, 35 minutes, 41 secondscreate a new message using await context database insert into messages conversation ID, project ID, roguments,
11:35:5111 hours, 35 minutes, 51 secondscontent, arguments status, uh, and created at. Do we actually have created at?
11:35:5911 hours, 35 minutes, 59 secondsWe don't. Yeah, no, no need for that.
11:36:0111 hours, 36 minutes, 1 secondOkay, do not pass that. And then uh let's also update conversations updated
11:36:0811 hours, 36 minutes, 8 secondsat if you uh want to right remember how we did this for projects. I personally think that yeah every time you send a
11:36:1611 hours, 36 minutes, 16 secondsnew message the conversation should be considered updated. We currently don't have much purpose for showing updated ad of a conversation but uh well actually
11:36:2511 hours, 36 minutes, 25 secondswe do because every time you refresh the conversation we load is the latest uh updated conversation. So maybe it makes
11:36:3311 hours, 36 minutes, 33 secondssense. Yeah. And remember to return the message ID. Very important. All right.
11:36:4111 hours, 36 minutes, 41 secondsSo now we are able to create the conversation. And let me just see. Uh oh, I didn't import mutation. Make sure
11:36:5011 hours, 36 minutes, 50 secondsyou import mutation from generated server. There we go. And now we can go back inside of our route here. And we
11:36:5611 hours, 36 minutes, 56 secondscan first go ahead and create uh a user message await convex which comes from our convex client lib.
11:37:0811 hours, 37 minutes, 8 secondsThere we go. Convex mutation API system create message. Pass the internal key, the conversation ID, the project ID
11:37:1611 hours, 37 minutes, 16 secondswhich we fetched from above. So we don't have to cast it because it's already a correct type. The role this is the user and the content. This is the message.
11:37:2511 hours, 37 minutes, 25 secondsAnd then let's go ahead and immediately create the assistant message
11:37:3211 hours, 37 minutes, 32 secondsplaceholder. Right? So we are sending uh to await convex mutation.
11:37:4111 hours, 37 minutes, 41 secondsLet me go ahead and maybe move it like this. It's easier to look at.
11:37:4711 hours, 37 minutes, 47 secondsConvex mutation API system create message internal key conversation ID.
11:37:5311 hours, 37 minutes, 53 secondsproject ID, ro content, and status processing like that. There we go. I'm going to add to-do invoke ingest to process the message.
11:38:0511 hours, 38 minutes, 5 secondsAll right. And let's return next response.json success true. Uh event ID for now is going to be zero.
11:38:1711 hours, 38 minutes, 17 secondsLet's add a comment to do later. use inest event ID and message ID will be assistant message ID
11:38:2611 hours, 38 minutes, 26 secondsand let's add a comma here so we can actually go further. All right. So the to-dos we have to do are check for any
11:38:3411 hours, 38 minutes, 34 secondsprocessing messages and stop them if there are and invo uh invoke inest to
11:38:4111 hours, 38 minutes, 41 secondsprocess the message which right now isn't happening because we are not going to work on that now. We just want to work on the UI and the database storage,
11:38:4911 hours, 38 minutes, 49 secondsright? So, let's go back inside of our conversation sidebar. Make sure you
11:38:5611 hours, 38 minutes, 56 secondsactually develop this inside of app API messages route.ts. So, this route works
11:39:0411 hours, 39 minutes, 4 secondsand let's try it out. Let's see if this will work or not. So, if I say we can refresh, we can do whatever. Perhaps it's best to test if everything works by
11:39:1211 hours, 39 minutes, 12 secondscreating a new project, clicking on it, and then let's do hello world. Let's go ahead and press enter. And there we go.
11:39:2111 hours, 39 minutes, 21 secondsHello world has been sent. And you can see that in here it's immediately set to thinking. And if you look at our data,
11:39:2811 hours, 39 minutes, 28 secondswe should have two messages. One from the user and one from the assistant with the status of processing right here.
11:39:3711 hours, 39 minutes, 37 secondsPerfect. And you can see that while the message is processing, the user is not allowed to send any new messages. They
11:39:4511 hours, 39 minutes, 45 secondswill only be allowed to stop, right? So they can cancel the current request.
11:39:5111 hours, 39 minutes, 51 secondsThis is kind of a protection so not too many costs occur.
11:39:5711 hours, 39 minutes, 57 secondsNow let's go ahead and create another system function. So I'm going to go inside of system here and I'm going to
11:40:0511 hours, 40 minutes, 5 secondsimplement a mutation called update message content. Here it is. Update message content is a mutation which
11:40:1411 hours, 40 minutes, 14 secondsaccepts the internal key, the message ID and the new content. We do the usual. We validate the internal key and we do await context database.batch.
11:40:2611 hours, 40 minutes, 26 secondsAnd now let's create the uh ingest background job to process a message. So we're not going to do any AI processing.
11:40:3511 hours, 40 minutes, 35 secondsI just want to simulate how it's going to look like and we're going to nip this mutation for that. So let's go ahead
11:40:4211 hours, 40 minutes, 42 secondsinside of source features conversations and I will create an ingest folder here
11:40:4811 hours, 40 minutes, 48 secondsand then inside process message.ts DS let's create an interface message
11:40:5611 hours, 40 minutes, 56 secondsevent which is going to define what is the payload of this background job a message ID conversation ID project ID
11:41:0511 hours, 41 minutes, 5 secondsand the message in a form of a string so let's export const process message
11:41:1211 hours, 41 minutes, 12 secondswhich will use the inest client and the create function in the first argument we're going to define the ID to
11:41:2011 hours, 41 minutes, 20 secondsbe process message and then let's go ahead and add
11:41:2711 hours, 41 minutes, 27 secondsuh let me just see like this. Okay, event message forward
11:41:3411 hours, 41 minutes, 34 secondsslash send and more importantly how about we add an ability we do this here
11:41:4011 hours, 41 minutes, 40 secondsactually called cancel on. Cancel on is actually a super cool feature which
11:41:4811 hours, 41 minutes, 48 secondsallows you to cancel a function a running background job simply by invoking a very specific event which in
11:41:5711 hours, 41 minutes, 57 secondsthis case will be message cancel but only if we match data message ID. So we
11:42:0811 hours, 42 minutes, 8 secondscan simply trigger this from ingest client and if the message ID is a match
11:42:1511 hours, 42 minutes, 15 secondsthen it's going to cancel whatever processing of that message ID we had. So super cool built-in feature uh from
11:42:2411 hours, 42 minutes, 24 secondsingest and I just took a peek and looks like it's deprecated. So let's use if instead
11:42:3211 hours, 42 minutes, 32 secondsand I believe it works the same. Let's see if asynchronous data user equals
11:42:3911 hours, 42 minutes, 39 secondsevent data user ID. All right, not 100% sure. So, I'm just going to go ahead and research just a bit.
11:42:4811 hours, 42 minutes, 48 secondsSo, if is definitely the new one and it uses a common expression language where
11:42:5511 hours, 42 minutes, 55 secondsthis is how you would do it. Event data dossage ID equals asynchronous data
11:43:0211 hours, 43 minutes, 2 secondsdossage ID. event refers to the incoming uh cancel event and async refers to the
11:43:1011 hours, 43 minutes, 10 secondsoriginal event that triggered the function. So a much more explicit language. All right.
11:43:1711 hours, 43 minutes, 17 secondsNow let's go ahead and uh do the following. So we have to open
11:43:2511 hours, 43 minutes, 25 secondsasync event and step like so. And let's start by extracting
11:43:3511 hours, 43 minutes, 35 secondsfrom event data which we can cast as message event.
11:43:4111 hours, 43 minutes, 41 secondsLet's extract message ID, conversation ID, project ID and message like that.
11:43:4911 hours, 43 minutes, 49 secondsLet's get the internal key and we are just going to do a slight modification here. So we know that this is Polaris convex internal key.
11:44:0211 hours, 44 minutes, 2 secondsThen if there is no internal key, let's throw a non retriable error which you can import from ingest and just do
11:44:1111 hours, 44 minutes, 11 secondspolaris convex internal key is not configured.
11:44:1511 hours, 44 minutes, 15 secondsAnd now what I want to do here is simply do await step.
11:44:2311 hours, 44 minutes, 23 secondsAnd let me actually find the proper syntax for this. Just a moment.
11:44:2811 hours, 44 minutes, 28 secondsBasically, I'm just using sleep to pretend some AI processing is happening like let's wait 5 seconds for example.
11:44:3711 hours, 44 minutes, 37 secondsAnd then what we are going to do is we're going to create a step
11:44:4411 hours, 44 minutes, 44 secondsupdate assistant message and in here we're going to call await convex which we have to import. So from
11:44:5211 hours, 44 minutes, 52 secondslib convex client dot mutation API which we have to import
11:45:0011 hours, 45 minutesfrom generated API dot system update message content
11:45:0811 hours, 45 minutes, 8 secondspass in the internal key the message ID and the content in here will be AI processed this message to do like that.
11:45:1911 hours, 45 minutes, 19 secondsSo a super simple step and we're not using these. So we can remove them from now. Let's just go ahead and get rid of all of these which we are not using. So
11:45:2711 hours, 45 minutes, 27 secondsit's not confusing us here. And I guess we can also remove them from the message event as well. So super simple step
11:45:3611 hours, 45 minutes, 36 secondswhich we can cancel if the message ID matches and which fails immediately if it's
11:45:4311 hours, 45 minutes, 43 secondsnon-retriable and it pretends to do some AI processing. So now let's go ahead and
11:45:5011 hours, 45 minutes, 50 secondsregister that method inside of API inest route. So I'm going to add process
11:45:5711 hours, 45 minutes, 57 secondsmessage from features conversations ingest process message. Let's go ahead and do npx
11:46:0611 hours, 46 minutes, 6 secondsuh inest cli latest dev. Let me just try and expand this.
11:46:1611 hours, 46 minutes, 16 secondsLet's make sure this is running, let's go ahead and visit localhost 8282 just to confirm all is well and so that we have that new function. Uh, okay.
11:46:2911 hours, 46 minutes, 29 secondsLooks like I have a bunch of them here.
11:46:3311 hours, 46 minutes, 33 secondsUh, I think it's because I have my other app opened. Just a second.
11:46:3811 hours, 46 minutes, 38 secondsAll right, here we go. So now I have demo error, demo generate in process message. Uh, make sure you are running
11:46:4511 hours, 46 minutes, 45 secondsyour app with this npx ignore scripts false ninja cla dev since that's the official instructions. Yeah. Uh, great.
11:46:5311 hours, 46 minutes, 53 secondsAnd we now have that method here.
11:46:5711 hours, 46 minutes, 57 secondsProcess message. And now that we have it, let's go back inside of our API messages route.
11:47:0811 hours, 47 minutes, 8 secondsAnd in here after we create the user message after we create the assistant message ID we can go ahead and invoke inest to process the message.
11:47:1811 hours, 47 minutes, 18 secondsSo we need to know the events name which is message
11:47:2511 hours, 47 minutes, 25 secondssent. So that's what we're going to call here. So let's do const event awaiting.
11:47:3311 hours, 47 minutes, 33 secondsMake sure to import that from ingest client. I'm going to move it here.
11:47:3911 hours, 47 minutes, 39 secondsing inest send name message forward slash send
11:47:4511 hours, 47 minutes, 45 secondsdata and simply pass in the message id which is assistant message ID. Later we're going to have more info but for now that's the only one we are working
11:47:5311 hours, 47 minutes, 53 secondswith. So now we can go ahead and pass the event ids and then the first one in the array here. I mean we're not really
11:48:0211 hours, 48 minutes, 2 secondsusing that but you know just more info doesn't hurt. So what's supposed to happen now is that when you send a
11:48:0911 hours, 48 minutes, 9 secondsmessage, it shouldn't get stuck in the thinking phase. Let me open a new conversation. Hey, how are you? So now I
11:48:1811 hours, 48 minutes, 18 secondsshould send it. It should think for 4 seconds and then it should update the message content. There we go. AI
11:48:2611 hours, 48 minutes, 26 secondsprocessed this message in parenthesis to-do. So that is the general idea of how this is going to work. We are mixing
11:48:3511 hours, 48 minutes, 35 secondsuh convex database access and ingest and we are doing it all very securely with the internal key here. Amazing.
11:48:4511 hours, 48 minutes, 45 secondsWe can also very easily implement a native failure message. So instead of
11:48:5211 hours, 48 minutes, 52 secondsprocess message inest function uh if we go ahead and add on failure we can make
11:48:5911 hours, 48 minutes, 59 secondsthis an asynchronous method. get the event and the step and in here we can
11:49:0611 hours, 49 minutes, 6 secondsextract message id from event dot data dovent dot data as message event so we
11:49:1411 hours, 49 minutes, 14 secondshave some type safety and then we can again attempt to get the internal key here
11:49:2211 hours, 49 minutes, 22 secondspolaris convex internal key and we can update the message with the error content. So for example, if we have the
11:49:3111 hours, 49 minutes, 31 secondsinternal key call step.run update message on failure and call convex
11:49:3811 hours, 49 minutes, 38 secondsmutation API system update message content with internal key message ID and content and then some error message. My
11:49:4711 hours, 49 minutes, 47 secondsapologies, I encountered an error while processing your request. How do we test this? Well, let's purposely throw an
11:49:5511 hours, 49 minutes, 55 secondserror here. So I'm going to go ahead and do await step.r run throw error async
11:50:0211 hours, 50 minutes, 2 secondsthrow non retryable error purposely through this or maybe I can just do it like this.
11:50:1511 hours, 50 minutes, 15 secondsHow does this work non-retable error? Oh, throw new non retryable error. So await step.r run
11:50:2411 hours, 50 minutes, 24 secondsthrow on purpose and let's go ahead and add that here.
11:50:3311 hours, 50 minutes, 33 secondsSo if we try this again now let me go ahead and refresh and if I say this will
11:50:4111 hours, 50 minutes, 41 secondsnot work after 4 seconds it should throw on purpose and it should update the
11:50:4811 hours, 50 minutes, 48 secondscontent of this message with this. My apologies. I encountered an error while processing your request. Let me know if you need anything else.
11:50:5911 hours, 50 minutes, 59 secondsAnd if you haven't noticed already, this method you Okay, make sure to remove this throw on purpose. It was just to
11:51:0611 hours, 51 minutes, 6 secondstest it out. Uh when we call this update message content, we also set the status to be completed. Right? I don't think I brought your attention to that. Right?
11:51:1711 hours, 51 minutes, 17 secondsThat's what makes this display a message instead of infinitely spinning. And let's try one more time. This will now
11:51:2411 hours, 51 minutes, 24 secondswork. So the only thing that doesn't work well is this set input doesn't reset. So let's quickly go inside of the
11:51:3211 hours, 51 minutes, 32 secondsconversation sidebar and in here set input to an empty string. So I'm talking about the handle
11:51:4211 hours, 51 minutes, 42 secondssubmit method right here. So let's go ahead and refresh. And let's do another try. There we go.
11:51:5111 hours, 51 minutes, 51 secondsNow it clears it. Uh the cancel is not yet working. We will implement that.
11:51:5611 hours, 51 minutes, 56 secondsIt's a little bit more complicated, but I want to keep that in the next chapter since we are already more than an hour in. So let's go ahead and merge all of these changes. There is a lot of them.
11:52:0611 hours, 52 minutes, 6 secondsSo let's see. I'm going to shut down all of these files
11:52:1311 hours, 52 minutes, 13 secondsand I will create get add get commit 12 conversation system
11:52:2111 hours, 52 minutes, 21 secondsget checkout B12 conversation system get push u origin 12 conversation system
11:52:3111 hours, 52 minutes, 31 secondsthere we go you can see I am on conversation system and let's go ahead
11:52:3811 hours, 52 minutes, 38 secondsand open a pull request and review our changes. There's a lot of them. So, if Code Rabbit comments on our components
11:52:4611 hours, 52 minutes, 46 secondsfile, we're mostly going to ignore those. We're just going to focus on uh if there are some any serious issues in what we've currently implemented that
11:52:5511 hours, 52 minutes, 55 secondsisn't in a temporary state because we will be working further on this system.
11:53:0011 hours, 53 minutesWe still have to connect it with AI, of course.
11:53:0411 hours, 53 minutes, 4 secondsSo, as I suspected, the release notes are mostly skewed due to the fact that we've added 40 components from AI
11:53:1111 hours, 53 minutes, 11 secondselements. So, let's take a look at the new features, but do understand that it took context of all the new components
11:53:1911 hours, 53 minutes, 19 secondswe added. So, perhaps some things might not make sense. We added conversation and messaging system for multi-turn interactions. We introduced
11:53:2711 hours, 53 minutes, 27 secondscomprehensive AI UI components for content visualization, code blocks, citations, reasoning panels and image display. We added message processing
11:53:3511 hours, 53 minutes, 35 secondswith ingest integration for asynchronous handling. We implemented prompt input with file attachment and speechto text
11:53:4211 hours, 53 minutes, 42 secondssupport. So this is the functionality inside of the prompt input component. We are not using it, but it exists. The code is there. That's why it's adding
11:53:5111 hours, 53 minutes, 51 secondsthese things which seem like we didn't do this but we actually did by adding all of those components. Majority of the
11:53:5811 hours, 53 minutes, 58 secondscomments here are actually referring to those uh for a few of them are for our things like this route which is missing
11:54:0611 hours, 54 minutes, 6 secondserror handling. Uh we can use safe bars here I think so it throws the error or we can just implement try catch to fix
11:54:1411 hours, 54 minutes, 14 secondsthis. But you can see majority of the comments are for this. I think the only one I actually found is at the end here which is simply warning us about the
11:54:2311 hours, 54 minutes, 23 secondsfact that we are sending this placeholder message to the public and to confirm that this will be changed later
11:54:3111 hours, 54 minutes, 31 secondsas well as the status should transition to something like completed. Uh let's see well update message content actually
11:54:4011 hours, 54 minutes, 40 secondsalready does that. It's just not clear in the name. And in here, it's telling us to do a runtime check on this missing
11:54:4711 hours, 54 minutes, 47 secondsenvironment variable if it's missing. So mostly nothing serious and majority of the comments are about all the components we've added. Amazing. Amazing
11:54:5611 hours, 54 minutes, 56 secondsjob. So let's go ahead and sync get checkout main get pool origin main. So
11:55:0211 hours, 55 minutes, 2 secondswe are up to date. And as always, I like to confirm by opening my source here
11:55:1011 hours, 55 minutes, 10 secondsgraph. And I've checked out for 12 and merged back in. Amazing. Amazing job. We've set up conversation and messages.
11:55:1811 hours, 55 minutes, 18 secondsWe can send both user and receive assistant messages. We didn't do the past conversations history dialogue.
11:55:2411 hours, 55 minutes, 24 secondsWe're going to do that in the next chapter. Uh we handled message sending but we kind of prepared consolation but
11:55:3211 hours, 55 minutes, 32 secondsnot fully. And we did display the thinking indicator. So good job. uh some things will be left for the next chapter
11:55:4011 hours, 55 minutes, 40 secondsand then we will be able to immediately combine all of that with AI functionality. Amazing, amazing job and see you in the next one.
Chapter 14: End of Part 1

Sync to video time
