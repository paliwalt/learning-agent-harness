https://www.youtube.com/watch?v=_y_ixdk9aRg&t=25142s



Build and Deploy an AI Coding Agent | Cursor Clone with Next.js 16 | Full Course 2026
Code With Antonio
Code With Antonio
419k subscribers

Join


823


Share

Ask

Save

28,413 views  30 Jan 2026
🎥 PART 1:    • Build a Cursor Clone from Scratch (AI IDE)...  

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
01:40 13 AI Agent Tools
2:17:46 14 WebContainers Terminal Preview
3:43:55 15 GitHub Import Export
5:52:31 16 Billing Final Polish
6:55:59 17 Deployment
7:11:57 End
6:55:35 17 Deployment
7:11:31 End
Ask
Get answers, explore topics and more

Ask questions

----------------------------------------------------------------------------------------
In this video


Chapters

Transcript
Search transcript
Search transcript

Chapter 1: Intro
0:000 secondsEnter a prompt and watch the AI build.
0:044 secondsIt creates files, modifies components, wires up logic, all in real time. When it's done, hit preview and your app is
0:1313 secondsrunning right in the browser. This is Polaris, an AI powered IDE we're building from scratch. In part one, we
0:2222 secondsset up authentication, the convex database, and built out the entire editor with syntax highlighting, code
0:2929 secondsfolding, minim, and AI powered suggestions. Now, in part two, we're making the AI conversation system
0:3838 secondsactually do things. We're using Inest agent Kit to build a tool loop so the AI
0:4444 secondscan create files, update code, delete folders, and keep iterating until the task is complete. Then there's web
0:5353 secondscontainers, so you can see your project running live with full terminal output.
0:5959 secondsGitHub integration lets you import existing repositories or push your work to a new one. Clerk handles billing to get premium features behind a pro plan.
1:111 minute, 11 secondsAnd at the end, we're deploying the whole thing to production. And now, let's finish this project. Using the
1:191 minute, 19 secondslink on the screen and coupon code Antonio, you can get an extra,000 Fiocrol credits for free. We'll be using
1:281 minute, 28 secondsit to scrape documentation and feed it directly to our AI as context throughout this build. If that sounds useful for
1:361 minute, 36 secondsyour project, feel free to grab the deal. In this chapter, we're going to continue working on our conversation
Chapter 2: 13 AI Agent Tools
1:441 minute, 44 secondssystem by enhancing it with AI agent and tool execution capabilities. Before we dive into that, we're going to go back
1:521 minute, 52 secondsand implement what we left over from the previous chapter. We still have to implement message consolation flow and we have to build the history dialogue.
2:012 minutes, 1 secondAfter we do those two, we can go ahead and configure the AI agent with system prompts and create a complete tool
2:092 minutes, 9 secondsexecution system. So let's go ahead and make sure our app is running. So make sure you have npm rundev.
2:172 minutes, 17 secondsMake sure you have npx convex dev
2:222 minutes, 22 secondsand make sure you also have npx inest- cliv.
2:292 minutes, 29 secondsSo you should have three running. npm rundev, npx convex dev, and npx in
2:372 minutes, 37 secondsjustest cli at latest dev. Great. Now let's go ahead and just test out test
2:442 minutes, 44 secondsout our app a bit just to see what we can do and what we can't. So if I go ahead and open my app right now, I can definitely send a message hello world.
2:552 minutes, 55 secondsBut one thing I immediately notice is I cannot cancel it, right? So even though I have an indicator to cancel it, there's nothing really happening here.
3:053 minutes, 5 secondsUh also uh I don't think there is a possibility to revisit older conversations. So I can definitely start
3:123 minutes, 12 secondsa new one, new conversation. That works too. But I cannot revisit the old one we've just tested out.
3:223 minutes, 22 secondsAnd besides that, obviously there is no AI processing. This is just mock. So let's start by giving the ability to
3:303 minutes, 30 secondscancel a message. So this will be very useful to save some tokens, right? If you want to quickly cancel, you should be able to do that. Same goes if there
3:383 minutes, 38 secondsis a very long running message here and the user in the meantime opens a new conversation and they send a new message. We should also make sure to
3:463 minutes, 46 secondscancel the previous one because obviously they meant to discard that. So let's go ahead and see how we're going
3:533 minutes, 53 secondsto do that. And I just want to give you uh one quick tip. If you go inside of your graph here, source control, you
4:004 minutesprobably see that I have these two commits that you never saw me do. Uh, I call them override because that's what
4:084 minutes, 8 secondsthey are. Uh, I just use them to update my readme file. That's it. It's because I finished part one of this tutorial.
4:164 minutes, 16 secondsSo, I had to update the readme so people can actually see what the project is about. That's it. you your last commit
4:244 minutes, 24 secondsshould be this 12 conversation system inside of a merged pull request. So all good. Don't worry about the fact that I
4:324 minutes, 32 secondshave additional commits. It's just uh a readme change. So the first thing I want to do is I want to implement the route
4:414 minutes, 41 secondsto cancel a message. So I'm going to go inside of source app folder API and inside of here we already have messages
4:494 minutes, 49 secondsfolder. Perfect. So let's go ahead and simply create a new folder called cancel and inside a route.ts.
4:584 minutes, 58 secondsNow in here let's go ahead and import the following. We're going to import Z from zod next response from next server
5:065 minutes, 6 secondsand out from clerk next.js server. Let's import inest client as well as the
5:135 minutes, 13 secondsconvex client. And then finally, let's import API and ID type from convex.
5:205 minutes, 20 secondsLet's quickly define the request schema.
5:235 minutes, 23 secondsSo what will this request accept? Very simply, a project ID where the message is currently processing. So we're going
5:305 minutes, 30 secondsto make sure that at any point only one message can be processing for this
5:365 minutes, 36 secondsproject. Now the reason I'm doing this is simply so in this state of the application we don't have too many uh
5:455 minutes, 45 secondsways to overspend our tokens. Obviously this can very easy easily become a limitation if you ever wish to implement
5:535 minutes, 53 secondssomething like multiple agents right but it's a very easy change. We're not really doing any architectural uh
6:016 minutes, 1 secondpreventions of multiple running or processing messages. I'm simply implementing this so you don't have
6:086 minutes, 8 secondsaccidental running and spending requests. So this will be a post request. So let's go ahead and simply
6:166 minutes, 16 secondsexport that and let's extract the user ID. Then we can immediately do an out
6:236 minutes, 23 secondscheck. So if the user ID is missing, let's simply throw a 401.
6:296 minutes, 29 secondsAfter that, we're going to go ahead and extract the body using await request.json.
6:376 minutes, 37 secondsAnd let's immediately parse that using our request schema. This will allow us to have a type safe param and also throw
6:456 minutes, 45 secondsan error in case it's invalid. Now, let's go ahead and let's get our internal key. So, const
6:546 minutes, 54 secondsinternal key process.vironment environment. And let me go ahead and remind myself of how
7:017 minutes, 1 secondwe actually call this. Do we mention that here? We do. Here it is. Polaris convex internal key. So I'm just going
7:107 minutes, 10 secondsto use that here. Again, the exclamation point at the end basically makes sure that this right now this is string or
7:197 minutes, 19 secondsundefined. If I add an exclamation point, it's just a string. So it's just for type safety. So, I have a habit of
7:267 minutes, 26 secondsputting an exclamation point at the end in case you were wondering. But we don't have to do that because we're going to do a check here. If the internal key is
7:357 minutes, 35 secondsmissing, we're again going to throw a next response 500 with an error internal key not configured. To give you a quick
7:427 minutes, 42 secondsreminder, we need the internal key because that's the only way we can query a convex client from Nex.js API routes.
7:527 minutes, 52 secondsSo what we have to do now is we have to find all processing messages in this project. So yes, every time the user
8:018 minutes, 1 secondhits this cancel endpoint, we're going to make sure that we cancel every single message that's currently processing. So
8:088 minutes, 8 secondswe have at least one button which says okay stop all token spend right just stop abort everything. So we can very
8:178 minutes, 17 secondseasily uh abort every single running background job which is very useful. So how do we get processing messages?
8:268 minutes, 26 secondsWell, by awaiting a convex query. The problem is we haven't developed this query. So let's go ahead and do that. So
8:348 minutes, 34 secondssave this file and then we're going to revisit our convex system.ts.
8:428 minutes, 42 secondsI'm quickly going to check do we have anything called processing messages. We do not. Great. It means we have to
8:508 minutes, 50 secondsdevelop it. So I'm going to go all the way at the bottom here and I will do export const get processing messages
8:598 minutes, 59 secondsand this will be a query which will accept arguments of internal key and project ID and then as usual we're going
9:089 minutes, 8 secondsto have a handler which is an asynchronous function which allows us to access the context and the arguments.
9:169 minutes, 16 secondsFirst things first, we're going to validate the internal key using a helper we have developed. Uh I think this type
9:249 minutes, 24 secondserror here is just something I have to restart.
9:299 minutes, 29 secondsYeah, that's it. Let me go down to the project uh to the function I was developing. So validate internal key is
9:379 minutes, 37 secondsjust a little helper. So we don't have to write this whole thing every single time. It basically checks that the proper and matching internal key was
9:459 minutes, 45 secondspassed. And then from here all we have to do is we have to query the database for messages. So let's go ahead and do that. I'm going to query for messages.
9:579 minutes, 57 secondsAnd then because if you take a look inside of our schema DS in the messages,
10:0410 minutes, 4 secondswe have an index called by project status.
10:0810 minutes, 8 secondsAnd so basically this means not by project's status. It means both by a project ID
10:1510 minutes, 15 secondsand by messages status. So we can very easily and in an optimized way using an
10:2210 minutes, 22 secondsindex find a message from a specific project which is currently processing which is exactly what we need right now.
10:2910 minutes, 29 secondsSo we're going to use the width index helper like this calling the by project status which we defined right here. And
10:3710 minutes, 37 secondsthen we're simply going to query if let me go ahead and display this like so. If
10:4510 minutes, 45 secondsquery project ID equals arguments project ID and if status is currently processing and make sure to execute the collect method at the end. That's it.
10:5710 minutes, 57 secondsThis will be a system helper which will allow us to at any point in time show us all messages which are currently processing.
11:0611 minutes, 6 secondsThis will almost exactly well should always correlate to us having a running background job. So now that we have that
11:1511 minutes, 15 secondsfunction, we can go ahead and go back inside of our new cancel route here and we can call that specific query APIs
11:2611 minutes, 26 secondssystem get processing messages. The arguments it accepts is our internal key
11:3311 minutes, 33 secondsand project ID. project ID which I'm going to type cast as ID project.
11:4111 minutes, 41 secondsThere we go. Now that we have the processing messages, let's first check if we can easily return already if there
11:5111 minutes, 51 secondsare none. So if there are no processing messages, well, let's just break this API method. No need to go any further
11:5811 minutes, 58 secondsbecause we can end here. But if that's not the case, we now have to cancel all the background jobs for each of these
12:0612 minutes, 6 secondsmessages. How do we cancel a background job? Well, programmatically we do that
12:1312 minutes, 13 secondsuh the following way. Let me just remind myself a little bit. Uh we have this functions uh I think it is inside of
12:2212 minutes, 22 secondsfeatures conversations inest process message.
12:2712 minutes, 27 secondsHere it is. Instead of our process message in justest function, we have developed a cancel on property here. And
12:3512 minutes, 35 secondsthe way we can programmatically cancel a background job is if we send an event message forward slashcancel.
12:4412 minutes, 44 secondsAnd if we pass along a message ID property and then this uh syntax right
12:5212 minutes, 52 secondshere is going to check if this events message ID matches process message event
12:5912 minutes, 59 secondsdata ID. So we have to explicitly know what message ID we want to cancel for.
13:0613 minutes, 6 secondsLuckily for us, we have all of that information. So since this can be a lot of processing messages, even though it
13:1413 minutes, 14 secondsshouldn't, it should only be one still, I want to develop it in a way that uh many of them can be cancelled at the
13:2213 minutes, 22 secondssame time just in case so you don't have to think of that. We're going to do const cancel ids await promise.all all
13:3113 minutes, 31 secondsand let's do processing messages dom let's run asynchronous method
13:3913 minutes, 39 secondsand very simply let's call inest dot send I mean let's await inest
13:4813 minutes, 48 secondsmessage forward slash cancel and we also have to pass the necessary
13:5413 minutes, 54 secondsarguments so data is going to be message id message underscore
14:0214 minutes, 2 secondsid like that. So now for each of these processing messages which we have successfully queried that they have a processing status in the convex
14:1014 minutes, 10 secondsdatabase, we are going to attempt to cancel their respective background job because uh we have to assume that if a
14:1914 minutes, 19 secondsmessage has a processing status, it must have a running background job because the only way a message can stop having a
14:2714 minutes, 27 secondsprocessing status is after process message function actually finishes.
14:3214 minutes, 32 secondsBecause if you go at the end here, here it is update assistant message. And this system function calls update message
14:4014 minutes, 40 secondscontent. And in here we set the status to completed. So if there actually is
14:4714 minutes, 47 secondssomething in the database which is still in processing status, it must mean most likely that there is an equivalent
14:5514 minutes, 55 secondsbackground job running. And this way we cancel it. Great. Now that we have that,
15:0215 minutes, 2 secondswe should also uh tell the user that a message has been cancelled. So for that, I'm going to call convex dot mutation APIsystem.
15:1415 minutes, 14 secondsAnd similarly to update message content, we're actually going to implement a new method called update message status. So
15:2215 minutes, 22 secondswe are not really interested in anything other than the status. So let's go ahead and quickly implement update message status. I'm going to go back inside of
15:3115 minutes, 31 secondsmy system.ds and uh let me see can I maybe copy?
15:3815 minutes, 38 secondsYeah, we can copy this entire thing.
15:4315 minutes, 43 secondsThis will be called update message status. It's going to be a mutation. It will accept an internal key. It will
15:5015 minutes, 50 secondsaccept a message ID. But for the stat uh for the next argument, it's not going to be content. It's going to be status,
15:5815 minutes, 58 secondswhich is a union of processing, completed, and cancelled. Always double check that that matches your schema. So,
16:0616 minutes, 6 secondsyou should be able to copy it from here and add it here,
16:1316 minutes, 13 secondsand it should be exactly the same. I don't think the order matters, but there should be no typos, right?
16:2216 minutes, 22 secondsAs always, we have to validate the internal key. And after that we do the patch method but only on status and
16:3016 minutes, 30 secondsspecifically we do it on arguments status. There we go. That's our update message status. We can now go back
16:3816 minutes, 38 secondsinside of the route where we now have the equivalent update message status. We can pass in the internal key message ID
16:4816 minutes, 48 secondsto be message underscore ID and the status will be cancelled.
16:5416 minutes, 54 secondsAnd finally, return message ID like that.
17:0117 minutes, 1 secondAnd once we've done all of that, let's go ahead and do return next response
17:0917 minutes, 9 secondslike so.json success true cancelled
17:1717 minutes, 17 secondstrue and message ids cancelled ids. What we returned from this API endpoint is
17:2417 minutes, 24 secondscompletely irrelevant. I just want to make it useful. So we successfully did it and we successfully cancelled. Do we
17:3117 minutes, 31 secondsreally need both? Ah I don't know. I think we can make do with just success true and message ids is useful just so
17:3917 minutes, 39 secondsyou can at least see in your network history. All right. Uh how many of these messages were actually cancelled by calling this endpoint. Right. Great. So that's the uh backend part finished.
17:5217 minutes, 52 secondsWhat we have to do now is we have to revisit the conversation sidebar.
17:5617 minutes, 56 secondsSo the conversation sidebar is currently missing a proper handle cancel method.
18:0418 minutes, 4 secondsSo conversation sidebar located in features conversations components right here. Let's go ahead and let me just
18:1218 minutes, 12 secondsfind. Yeah. So nowhere in this code do we have a proper developed handle cancel method. So let's go ahead and do it.
18:2118 minutes, 21 secondsConst handle cancel is going to be an asynchronous method. So let me fix the typo. Async.
18:2918 minutes, 29 secondsAnd in here we're going to open a try and a catch method. In the catch method we can already throw an error. unable to cancel request.
18:3918 minutes, 39 secondsAnd in the try, we're going to await ky.post API messages cancel. So just make sure
18:4818 minutes, 48 secondsyou don't misspell this part because it's not type safe. What I mean by that is that there's nothing stopping you from writing this accidentally. So
18:5718 minutes, 57 secondsalways double check you know is your API actually called that messages cancel
19:0419 minutes, 4 secondslike this and in the post we have to pass in the JSON the only thing we actually expect is the project ID which
19:1319 minutes, 13 secondswe can use a shorthand alias like this perfect now that we have the handle cancel let's
19:2119 minutes, 21 secondsfirst learn how to call it uh explicitly And I think the simplest way simplest
19:2919 minutes, 29 secondsway is to add it inside of the handle submit and it's this case. So if we are currently processing and no new message
19:3719 minutes, 37 secondshas been submitted. This means that this is just a stop function. So now we can actually await handle cancel in here if
19:4519 minutes, 45 secondsis processing and if there is no message.ext.
19:4919 minutes, 49 secondsSo let's see that in action. In fact, I want to make sure that I have my ingest uh running somewhere.
19:5719 minutes, 57 secondsHere it is. All right. And I have this uh and I also just for fun, I'm going to
20:0520 minutes, 5 secondsmake sure to increase the sleep time of my functions so we can actually see this effect. So go inside of features
20:1220 minutes, 12 secondsconversations inest process message and change this from 5 seconds to 50 seconds.
20:2020 minutes, 20 secondssimply so we can actually see the cancel effect happening.
20:2520 minutes, 25 secondsSo now I'm going to go ahead and do testing cancellation and I'm going to send it and we should
20:3420 minutes, 34 secondshave a new background job running here and this should wait for 50 seconds. But if I click this hopefully and looks like
20:4320 minutes, 43 secondssuccessfully we have cancelled it. Here it is. You can see it says cancelled and
20:5020 minutes, 50 secondsuh I think there is somehow a way to observe be observe this cancel event
20:5720 minutes, 57 secondsbecause technically we did just send a whole new event. So it should be documented somewhere. I'm just not sure
21:0521 minutes, 5 secondswhere. Right. But what we just did is we used convex database to find let's let me actually open convex. Perhaps that's going to help us too.
21:1621 minutes, 16 secondsSo if you go inside of your project here in the convex dashboard inside of data specifically inside of messages here you
21:2421 minutes, 24 secondsshould find status column here and you can see that my last one has cancelled status. So, just to make things easier, I'm going to delete all of my messages.
21:3621 minutes, 36 secondsAnd um I'm going to also delete all of the conversations.
21:4121 minutes, 41 secondsAnd then I'm just going to go ahead and create a new brand new project here so it's easier for me to understand what's
21:4821 minutes, 48 secondsgoing on. And I'm going to send again testing cancellation.
21:5621 minutes, 56 secondsSo right now what's happening here is that we have a new message. So go inside of your messages table and you can see
22:0322 minutes, 3 secondsthat right now there is a response from the assistant which is currently in its
22:1022 minutes, 10 secondsprocessing status. So this is now spending tokens. Well not right now but it will in the future. This means AI is thinking of something. So if user
22:1922 minutes, 19 secondschanges their mind and if they hit this what we do is we query all of those messages which are currently processing
22:2622 minutes, 26 secondsand we fire a cancel event on their ingest background job and then we also change that their status to cancelled.
22:3922 minutes, 39 secondsRight? So, one thing I wish we could do as well inside of the inest. Perhaps we
22:4422 minutes, 44 secondscan somehow uh I wish I could change the actual cancel status in here in the
22:5222 minutes, 52 secondscancel on. Maybe there kind of is a way to do that. I I'm not sure. I have to check documentation. But right now, what
23:0023 minuteswe're doing is we're doing it directly in the API route of the cancel right here. So we simply fetch all the
23:0823 minutes, 8 secondsprocessing messages from the database which basically means all the assistant messages that are currently processing.
23:1423 minutes, 14 secondsWe early return if there are none but if there are we send ingest message forward slashcancel because that's exactly what we defined here and we send message ID.
23:2723 minutes, 27 secondsSo what's important is that you didn't misspell message ID anywhere in here, right?
23:3423 minutes, 34 secondsUh and also when you invoke process message, let me see process message.
23:4123 minutes, 41 secondsWhere do I define the event? Here it is.
23:4423 minutes, 44 secondsMessage forward slash sent. So when you invoke this in source app API messages, it's also important that you didn't
23:5223 minutes, 52 secondsmisspell the variable here. All of those variables are important for this clause right here, which will allow us to successfully cancel a message. Perfect.
24:0324 minutes, 3 secondsSo explicitly cancelling a message seems to work just fine. The problem is user
24:1024 minutes, 10 secondshas no idea what just happened. Well, they technically do, right? But it would be nice if there was an explicit way to show to the user, hey, this message has
24:1924 minutes, 19 secondsno content, and that's because it was cancelled. So for that, we should uh go
24:2624 minutes, 26 secondsahead and find I think it's also inside of the conversation sidebar.
24:3124 minutes, 31 secondsLet me find it right here. Where we iterate over our conversation messages.
24:3724 minutes, 37 secondsUh we should check if a message has been cancelled. Right now instead of the message content here we have if message
24:4724 minutes, 47 secondsstatus is processing show thinking otherwise show the content. So we should do kind of a double otherwise.
24:5824 minutes, 58 secondsI'm I'm sure there was better ways to say that, but yeah, I think you know what I mean. And in here, let's just go
25:0525 minutes, 5 secondsahead and check. Otherwise, if message status is equal to cancelled,
25:1325 minutes, 13 secondsthen go ahead and render a span request cancelled.
25:2225 minutes, 22 secondsAnd let's simply give it a class name text muted foreground. and italic.
25:3025 minutes, 30 secondsAnd then in here, let's go ahead and make sure we return a
25:3725 minutes, 37 secondsmessage response. I hope this is proper syntax. It is. There we go. You can see it says request cancel, right? So, if I
25:4525 minutes, 45 secondsgo ahead and send another message here, you can see that right now it's thinking
25:5225 minutes, 52 secondsand when I hit cancel, it will change to request cancelled and allow us to send a new one. So, we don't allow the user to
25:5925 minutes, 59 secondsspam and have a bunch of background jobs running. Great. So, now that we have that finished, there is still another
26:0826 minutes, 8 secondsway a user can have both. So if I do this for example,
26:1626 minutes, 16 secondsif I go uh in this convo I am processing. So I will send this message. This is now processing right?
26:2526 minutes, 25 secondsYou can see that a message is processing. A background job is running.
26:2926 minutes, 29 secondsAnd if I attempt to send anything else here I'm going to cancel it. But if I open a new one and do hello now we don't actually cancel anything.
26:3926 minutes, 39 secondsWe just have two processing messages and two uh running background jobs. Chances are user probably doesn't care about
26:4926 minutes, 49 secondswhat is in the other one. Maybe in the future your users will and you will change this behavior but I feel like most of the time this is just user deciding to start a new conversation.
26:5926 minutes, 59 secondsSo, it would be a good idea that every single time we send the new message, we cancel all the currently running requests for this project.
27:1127 minutes, 11 secondsSo, let's go ahead and do that. We're going to revisit our source app API messages route.ts.
27:2127 minutes, 21 secondsAnd basically what we have to do is uh well we have this to-do called invoke inest to process the message but I think
27:3027 minutes, 30 secondswe are already doing that. So I think we can remove this to-do. We're just missing some data which we're going to have to update. But this is the to-do I
27:4027 minutes, 40 secondscare about. Check for processing messages. So inside of this async post
27:4727 minutes, 47 secondsfunction here, let's go ahead and find the place where we define the project ID before we call convex mutation create
27:5727 minutes, 57 secondsmessage. Before we do any of that, we're going to go ahead and check for processing messages. Lucky for us, we
28:0528 minutes, 5 secondscan now do this quite easily. So in in fact you can open your cancel right here and you can go ahead and do this right.
28:1628 minutes, 16 secondsSo instead of this to-do copy this paste it find all processing messages in this project. So we are calling the same
28:2428 minutes, 24 secondsfunction get processing messages and I don't think we have to cast it this time. Yes, we don't have to. We can just
28:3228 minutes, 32 secondsuse this. What's important is that you pass the internal key along and the project ID.
28:3928 minutes, 39 secondsAnd now we're going to check if processing messages.length is larger than zero, meaning we have some
28:4628 minutes, 46 secondsprocessing messages in this project while the user is trying to send a new one. Let's cancel all of those
28:5328 minutes, 53 secondsprocessing messages and we can actually copy this uh entire thing. So this await
29:0129 minutes, 1 secondpromise all can be copied entirely like this and just paste it here. I'm
29:1029 minutes, 10 secondsjust going to fix the indentation. There we go. So await promise all processing messages do map. We get the individual
29:1929 minutes, 19 secondsmessage. We first trigger the cancel event from ingest. So we shut down the background job using the equivalent
29:2629 minutes, 26 secondsmessage ID. And after that we update the message status to cancelled. Why? Well, because remember we can't do that inside
29:3529 minutes, 35 secondsof the cancel event. So we have to do it here. And uh we actually don't have to return the message ID. Previously we do that because we want to return the
29:4329 minutes, 43 secondsnetwork request. But in here we don't have to do anything like that. And I think that's all we really need to do.
29:5229 minutes, 52 secondsEverything else I think works just fine.
29:5529 minutes, 55 secondsSo here we create the user message. Uh in here we create the assistant message which is set to processing.
30:0530 minutes, 5 secondsLet me just go ahead and add a comment so we understand what we're doing here.
30:0830 minutes, 8 secondsIn here we add a trigger to process the message and then we just return like hey we're doing something. If you want to uh
30:1630 minutes, 16 secondsyou can also add a little boolean like uh did cancel any messages and then you can return did cancel any messages true
30:2530 minutes, 25 secondssimply so in your network history you are aware that uh what happened here was some messages were cancelled before a
30:3230 minutes, 32 secondsnew one was created. So let's take a look at our situation now. Uh I'm going to do the same thing. I'm going to start a completely new conversation and I will
30:4030 minutes, 40 secondssay in this conversation I am running right. So now when I take a look at here
30:4830 minutes, 48 secondsone processing message one running background job and now I'm going to open
30:5530 minutes, 55 secondsa new conversation. Previously the problem was if I send something I would have two of them running. This should
31:0231 minutes, 2 secondscancel the old one. So right now nothing should be different here but you can see this one was automatically cancelled.
31:1031 minutes, 10 secondsOnly the newest one is processing and this background job was cancelled. Only the newest one is processing. And now I
31:1831 minutes, 18 secondscan explicitly cancel this one too. And there we go. We now have a very safe way of sending messages without polluting
31:2731 minutes, 27 secondsour background jobs, without spending too many tokens. Because remember, all of these are going to be very complex AI requests. You can't really afford to
31:3631 minutes, 36 secondshave a leak in your processing somewhere. That's why we are focusing on this so much. Excellent. So with just a
31:4431 minutes, 44 secondsfew system functions and just a few routes, uh we created a very thorough system for keeping track that only one
31:5231 minutes, 52 secondsmessage for a project is currently processing. What we ought to do next is implement the history dialogue because
32:0032 minutesat the moment there is no way to revisit previous conversations.
32:0532 minutes, 5 secondsLet's get started by creating the past conversations dialogue component. I'm going to go inside of source features
32:1332 minutes, 13 secondsconversations components and in here I'm going to create a new file
32:2032 minutes, 20 secondspast dash conversations dialogue.dsx.
32:2632 minutes, 26 secondsI'm going to go ahead and import start with a directive use client and then I'm going to import format distance to now
32:3432 minutes, 34 secondsI'm going to add the following elements from the command component dialogue empty group input item and list I'm
32:4332 minutes, 43 secondsgoing to add if we have it let me quickly check use conversations
32:4932 minutes, 49 secondscook from hooks use conversations and I'm going to import ID E from convex
32:5732 minutes, 57 secondsgenerated data model. Let's go ahead and define the interface pass conversations dialogue props which will accept the
33:0533 minutes, 5 secondsproject ID for which we are going to load the conversations. Open on open change and on select which will allow us to select a conversation.
33:1733 minutes, 17 secondsNow that we have those props we can define our component like so. Make sure to extract project ID open on open
33:2533 minutes, 25 secondschange and on select. Now let's load all conversations for a project ID that the
33:3233 minutes, 32 secondsuser has passed. Let's implement a very simple handle select method which will accept a conversation ID call the on
33:4133 minutes, 41 secondsselect which we can we might as well make on select required and then we don't have to do this weird optional
33:4933 minutes, 49 secondschain. and make sure to close this dialogue after the user selects a new an older conversation.
33:5733 minutes, 57 secondsNow, let's go ahead and return. What we're going to return is the command dialogue component. The command dialogue component will have the following props.
34:0834 minutes, 8 secondsOpen and on open change as well as a title and description. The title will
34:1434 minutes, 14 secondssay past conversations and s and the description will say search and select a past conversation.
34:2234 minutes, 22 secondsNow we have to define the command input with a placeholder which will be search for conversations.
34:2934 minutes, 29 secondsThen we have to add a command list and we have to add a command empty. This will serve as a placeholder if something
34:3734 minutes, 37 secondsthe user wrote does not exist in our database. So no conversations found.
34:4334 minutes, 43 secondsFinally, let's go ahead and add the con command group component with a heading conversations.
34:5134 minutes, 51 secondsNow we can go ahead and iterate over our conversations using conversations.m map.
34:5734 minutes, 57 secondsMake sure to add a question mark since conversations can be undefined.
35:0235 minutes, 2 secondsNow in here we're going to return a command item.
35:0835 minutes, 8 secondsThe command item will have a key of conversation underscore id. It will have a value which will combine the
35:1535 minutes, 15 secondsconversations title with the ID. This is to prevent multiple uh conversations from being selected at the same time in
35:2435 minutes, 24 secondscase they have the same title. And let's pass in our handle select right here.
35:3035 minutes, 30 secondsNow in here I see I have an error. So let me quickly see what that's about. I think I'm missing a parenthesis. There
35:3835 minutes, 38 secondswe go. So, I was missing one parenthesis here. Inside of command item, I'm going to open a div. I'm going to render span
35:4735 minutes, 47 secondsinside with a conversation title. And I'm going to show the created at timestamp with another span.
35:5735 minutes, 57 secondsAnd instead of using created at, we will simply use underscorecreation time because that's built in with convex. So
36:0536 minutes, 5 secondsthe div has flex flex column and gap 0.5.
36:1036 minutes, 10 secondsThe span for the title has no styles whereas the span for the timestamp has an extra small text and kind of a muted
36:2036 minutes, 20 secondscolor for the text. Perfect. So that is our command dialogue finished. And now we have to find uh a way to render it.
36:3536 minutes, 35 secondsSo we're going to go ahead back inside of the conversations sidebar, which I believe is yeah, it's in the exact same folder. I didn't even have to close it.
36:4536 minutes, 45 secondsAnd the first thing we're going to do is we're going to define uh the state which is going to control whether this is open
36:5336 minutes, 53 secondsor not. So let's add it right here underneath the selected conversation ID.
37:0037 minutesSo we're going to call this state past conversations open and set past conversations open.
37:0937 minutes, 9 secondsAnd now let's find a button which is going to toggle that. In our case that's going to be this the history icon button. So simply give it an on click.
37:2237 minutes, 22 secondsset past conversations open to true.
37:2637 minutes, 26 secondsNow, after this button right here, actually, well, it doesn't really matter where we do this, but I what I like to
37:3437 minutes, 34 secondsdo with dialogues is I like to wrap my entire component inside of a fragment.
37:4037 minutes, 40 secondsAnd then I like to render it outside.
37:4437 minutes, 44 secondsSo, past conversations dialogue like this. You don't have to do it this way.
37:4937 minutes, 49 secondsI believe all of these dialogues from Shatsen use React portal which moves them to the outer dome. But I still like
37:5737 minutes, 57 secondsto semantically render my components how they are going to appear in the DOM and this will be kind of above all this
38:0738 minutes, 7 secondscontent because when I see something rendered inside I kind of expect it to be shown inside but that's not the
38:1438 minutes, 14 secondsscenario for the dialogue. But just to be clear you can render this wherever you want. It doesn't matter. So what do we need to pass here? We need to pass
38:2238 minutes, 22 secondsthe project ID so we know exactly what conversations to load. We need to pass the open status. We need to pass on open
38:3138 minutes, 31 secondschange and we also need to pass on select and the on select will simply
38:3838 minutes, 38 secondscall our set selected conversation ID which we have already utilized uh in this project. So let's go ahead and try.
38:4838 minutes, 48 secondsIf I go ahead and click on this button, you can now see that I have a bunch of these previous conversations and you can see that we can see exactly this test
38:5638 minutes, 56 secondscancellations which we were trying just a moment ago. So we have successfully implemented that too. At the moment we can't really do any useful search here.
39:0839 minutes, 8 secondsUh you might see some results like this.
39:1139 minutes, 11 secondsThis is because we are matching the ID, right? because we combine the title and the ID of the conversation. And this is
39:1839 minutes, 18 secondshow it looks like if uh there is no results found. This makes this isn't too useful right now because they are all
39:2539 minutes, 25 secondsnamed exactly the same. And that brings us to well our next step which is basically implementing the agent.
39:3639 minutes, 36 secondsI want to start by revisiting our ingest process message function as well as our
39:4339 minutes, 43 secondsAPI endpoint to create a message. So instead of API messages route.ts. Right
39:5039 minutes, 50 secondsnow when we trigger this message send event we only pass in the message ID because that's the only thing we need.
39:5939 minutes, 59 secondsBut now let's extend it by passing the conversation ID, project ID and the actual message.
40:0840 minutes, 8 secondsNow we have to strictly type those inside of the actual uh feature. So
40:1440 minutes, 14 secondsfeatures conversations inest process message. The message event only accepts this too. So now let's enhance that.
40:2440 minutes, 24 secondsBesides the message ID, we will also accept conversation ID. We're also going to accept project ID and finally the actual message.
40:3640 minutes, 36 secondsNow that we have a proper message event from here, we will be able to extract
40:4240 minutes, 42 secondseverything else we need. But let's go ahead and stop here and let's install a
40:4940 minutes, 49 secondspackage which we are going to use uh to well set up the ingest agent kit. So I'm
40:5740 minutes, 57 secondsgoing to go ahead and just do npm install atingest forward slash agent kit like so. I
41:0741 minutes, 7 secondsdidn't shut down my app. I still have all three running. There is no need to shut down your app at the moment. And
41:1541 minutes, 15 secondsonce this function has installed, I'm going to go ahead and show you exactly inside of package.json which version I'm using. So for me, it is 0.13.2.
41:2941 minutes, 29 secondsAnd it's also a good idea to use the link on the screen uh to visit inest
41:3841 minutes, 38 secondsagent kit. In here you can find the actual documentation and you can find the exact quick start that we just did.
41:4641 minutes, 46 secondsWe already have inest installed and now we also added inest agent kit and you
41:5341 minutes, 53 secondscan see that starting with agent kit 9.0 inest is a required pure dependency. You must install both packages together to
42:0242 minutes, 2 secondsensure proper runtime. This is actually a good tip. Perhaps we should run the whole thing again. And if we're going to
42:0942 minutes, 9 secondsdo that, we should shut down the ingest tab. So yes, I'm going to run this again simply because it's a pure dependency.
42:1642 minutes, 16 secondsI'm not sure if it's any different if you install them in the same turn. Let me see is my package JSON any different.
42:2342 minutes, 23 secondsThis is my inest agent kit version and this is my inest version. So yeah, I mean I would suggest just running the install at the same time like this.
42:3642 minutes, 36 secondsAfter that, go ahead and run npx inest cli at latestdev. Again, I don't think there should be any issues. Uh if there
42:4442 minutes, 44 secondsare, it's probably version related. You didn't uh write anything incorrectly.
42:5042 minutes, 50 secondsAll right. So, we have that ready. And now before we explore uh inest agent kit
42:5742 minutes, 57 secondsany further, let's go ahead inside of source. Let's go inside of uh features
43:0543 minutes, 5 secondsconversations. And in here in the inest folder, I'm going to create a file constants.ts.
43:1343 minutes, 13 secondsIn here, we're going to define our system prompts. Obviously, you can change and tune your system prompts to
43:2043 minutes, 20 secondswhatever you prefer, but these are the ones I'm going to use. You can find this using my source code, which you can find
43:2743 minutes, 27 secondsthe link for uh on the screen. uh it's free and you can also find it in the assets uh file which I usually show you.
43:3743 minutes, 37 secondsSo go ahead and add the coding agent system prompt. If you're using the source code, simply navigate to the
43:4443 minutes, 44 secondsexact file I am in right now. And let's go ahead and also add one more which is
43:5243 minutes, 52 secondsgoing to be the title generator system prompt. again using the link on the
43:5843 minutes, 58 secondsscreen. You can uh find these in my source code or you can find them in the public assets repository.
44:0844 minutes, 8 secondsNow, in order to prepare for tool calling, we're going to have to add a bunch of system queries and mutations uh
44:1644 minutes, 16 secondsin here in the convex system file. So, let's go ahead and have that ready so later we can just simply query them.
44:2544 minutes, 25 secondsWe're going to start with a very simple get recent messages. We're going to use this for conversation context. Perhaps
44:3344 minutes, 33 secondsyou can add little comments here. Used for agent conversation context. This can
44:4044 minutes, 40 secondshelp you understand why you need these system functions. The arguments it accepts are very familiar. Internal key,
44:4844 minutes, 48 secondsconversation ID, and then the limit. The limit is basically to decide you know how much context do we want to give to
44:5644 minutes, 56 secondsthe AI last five messages, last 10 messages or 100, right? Depending on how uh AI's advance, you might be able to
45:0645 minutes, 6 secondspass along all of them. After you validate the internal key, you're going to query the messages using the by
45:1345 minutes, 13 secondsconversation index and simply passing along arguments conversation ID. Make sure to order them by ascending and make sure to execute the collect. Perfect.
45:2445 minutes, 24 secondsAnd then let's go ahead and simply uh limit them like this and then slice them. There we go. So that is the first
45:3345 minutes, 33 secondsone we have to do. The second one we have to do is a mutation called update conversation title.
45:4545 minutes, 45 secondsThis will be used to get rid of the annoying new conversation for every single conversation that we have.
45:5245 minutes, 52 secondsBasically, using the context of the messages, AI will be able to update the conversation title. Uh the arguments in
46:0046 minuteshere are similar. So, internal key, conversation ID, and the title. And in
46:0746 minutes, 7 secondsthe handler here, we're going to first, as always, validate the internal key.
46:1446 minutes, 14 secondsAnd then we're going to simply call patch on the that on the conversation ID with the new title. And we're going to
46:2146 minutes, 21 secondsrefresh the updated ad key simply so we know which one was the latest one we worked on. So you can go ahead and if
46:3046 minutes, 30 secondsyou want to you know add a comment what this is used for. So used for agent to update conversation title.
46:3846 minutes, 38 secondsGreat. Uh, next one we need is get project files.
46:4646 minutes, 46 secondsSo I'm going to go ahead and start preparing this.
46:5246 minutes, 52 secondsGet project files accepts internal key and project ID.
46:5846 minutes, 58 secondsThe handler will validate the internal key and it will simply call all files by
47:0547 minutes, 5 secondsa project ID. As simple as that. So this will be uh basically used for list files
47:1447 minutes, 14 secondstools used for agent list files tool. We are going to have to create tools
47:2247 minutes, 22 secondsourselves and we're going to have to uh define what those tools do. So when the user asks how many files do I have in
47:3147 minutes, 31 secondsthis project, the agent will call list files tool and then we're going to make
47:3747 minutes, 37 secondsthe agent call this muta this query right here which will uh send back to the agent all the files in this project.
47:4847 minutes, 48 secondsSo that's how that's going to work. That is uh get project files. Uh now we need
47:5647 minutes, 56 secondsget file by ID. So this right here which I've just pasted. Get file by ID is a
48:0348 minutes, 3 secondsquery which accepts internal key and file ID and very simply just returns the file ID. As simple as that. The next one
48:1248 minutes, 12 secondswill be update file. So this one is what it says. It's used to update the file.
48:1948 minutes, 19 secondsIf we instruct the agent to change something in the file, we need to create a tool which will do that. So let's go
48:2748 minutes, 27 secondsahead and start by defining the handler which is always is going to validate the internal key. We are first going to
48:3648 minutes, 36 secondscheck if the file even exists. So we can uh return early if it doesn't. And then finally we're going to call a patch
48:4448 minutes, 44 secondsmethod like this. So the only thing we're going to patch are the content and the updated
48:5048 minutes, 50 secondsat. And finally, let's return arguments file ID. So let's slow down a bit and
48:5848 minutes, 58 secondssimply write some comments. So get file uh by ID will be used for read files tool.
49:1049 minutes, 10 secondsThe update file will be used for update file tool.
49:1749 minutes, 17 secondsAnd now let's go ahead and go on to the next one which is create file. And you can already guess what tool that's going
49:2549 minutes, 25 secondsto be using. So again let's create uh the same mutation. Create file accepts
49:3249 minutes, 32 secondsinternal key project ID name content and a parent ID with an which is optional.
49:4049 minutes, 40 secondsRight? So if this is inside of a folder it's going to have a parent ID.
49:4549 minutes, 45 secondsotherwise it's in the root of the project and make sure to do the validate internal key. So the first thing we're
49:5449 minutes, 54 secondsgoing to do is we're going to get uh we're going we have to make sure that the agent doesn't accidentally create
50:0250 minutes, 2 secondsthe same name the file in the folder right so because of that we have to get
50:0850 minutes, 8 secondsall files which are currently in this uh files project uh in this files parent or
50:1650 minutes, 16 secondsif there's no parent in the root folder because remember when you create new files I think we can actually try this
50:2250 minutes, 22 secondsout. If I call this hello.jsx and if I try to do another one, hello jsx, I get an error. We shouldn't be
50:3150 minutes, 31 secondsable to do that. And neither should the agent. So that's why we have to in this create file method in the system prevent
50:3950 minutes, 39 secondsthe agent from doing that. So if we can find an existing file with the same name and file type file, we're going to go
50:4850 minutes, 48 secondsahead and throw an error. Hey, this file already exists. You cannot create this
50:5450 minutes, 54 secondsotherwise let's simply insert a new file. So inside of context database
51:0151 minutes, 1 secondinsert files add project ID name content type of file parent ID and updated at and lastly return file ID.
51:1551 minutes, 15 secondsSo you've already guessed it. The create file will be used for create file tool.
51:2451 minutes, 24 secondsAnd now we're going to create a very very similar one. It's just going to be used for bulk creation and it's going to
51:3351 minutes, 33 secondsbe very useful in fact. So create files not create file. This one is create
51:4051 minutes, 40 secondsfiles. So let me define uh the handler.
51:4651 minutes, 46 secondsLet me go ahead and fix the indentation and like this. There we go. So what are
51:5451 minutes, 54 secondsthe arguments? Internal key, project ID, parent ID and then an array of files
52:0152 minutes, 1 secondwhich uh is an object. I mean each of the item in the array is an object which has a name and content inside. So
52:0952 minutes, 9 secondsbasically we can give AI 50 files to be created but it can only be for a specific folder. So that's kind of the
52:1752 minutes, 17 secondslimitation. Uh we can already go ahead and add a little comment here. The create files
52:2452 minutes, 24 secondswill be used for agents and let's add bulk create files tool because that's what it is. It's used to create files in
52:3252 minutes, 32 secondsbulk. We also have to be careful here, right? So let's make sure that there are no existing files with the same name.
52:4152 minutes, 41 secondsNow the way we can do that is a little bit complicated. We're going to define an empty array and we're going to give
52:4752 minutes, 47 secondsit a very specific uh type. So the results is by default an
52:5452 minutes, 54 secondsempty array and inside of here we expect objects with name property, file ID
53:0253 minutes, 2 secondsproperty and an optional error property because any of these files in the array can be problematic. So let's start by going over them.
53:1353 minutes, 13 secondsfor file of arguments.file. First thing we're going to do is we're going to check if there is an existing file with the same name and the same type.
53:2253 minutes, 22 secondsIf there is an existing file, we're simply going to push to the results array, the name of the file, the ID of the
53:3153 minutes, 31 secondsexisting file, and the error file already exists. And let's continue because we have more files to create and
53:4053 minutes, 40 secondswe can very easily just create a file otherwise. So insert into files project ID
53:4753 minutes, 47 secondsname content type parent ID and updated at and finally let's do results.push
53:5853 minutes, 58 secondsname file.name and file ID and make sure to return results.
54:0454 minutes, 4 secondsSo that tool is used to create files in bulk. Now let's go ahead and develop the
54:1154 minutes, 11 secondscreate folder method. So the create folder method is almost identical to the create file one. Let's go ahead and copy
54:2054 minutes, 20 secondsthis. Let's go to the bottom and let's change this used for agent
54:2854 minutes, 28 secondscreate folder tool. So this will be create folder and
54:3554 minutes, 35 secondsit's just not going to have content. So it will have the internal key, project ID, name and parent ID. Then we're going to validate the internal key as always.
54:4654 minutes, 46 secondsAnd we're going to query files. So by project parent, all of this is cool, but we're just going to change the existing query to check by file type folder.
54:5854 minutes, 58 secondsand it's going to throw folder already exists.
55:0355 minutes, 3 secondsThe content in here will be empty and the type will be folder like that. Now, if you want to, you can
55:1255 minutes, 12 secondscreate the equivalent uh create folders, but more often than not, um it's not
55:1955 minutes, 19 secondsthat useful. I've seen agents uh call create files way more than create folders. If you want to, you can create
55:2855 minutes, 28 secondsit. In fact, it will be a nice challenge for you to create a tool that I don't write simply so you learn how to create different tools.
55:3755 minutes, 37 secondsAll right. Now, we have only two left.
55:4155 minutes, 41 secondsSo, next one is rename file which is used to allow the agent to rename a file
55:4855 minutes, 48 secondsif the user requests. So, internal key, file ID and the new name as the arguments.
55:5555 minutes, 55 secondsThen a check if that file actually exists. And then again uh we have to check we have to check if a file with
56:0456 minutes, 4 secondsthe new name the agent wants to rename it to exists in the same parent folder.
56:1056 minutes, 10 secondsSame with creating a file. So let's get all the siblings using query files by
56:1756 minutes, 17 secondsproject parent index querying by project ID and by file parent ID and collect.
56:2656 minutes, 26 secondsAnd now we can go ahead and check if it exists. And we have to check if the
56:3356 minutes, 33 secondssibling name matches the new name. We have to check if the sibling type matches the file type. And we have to of
56:4256 minutes, 42 secondscourse check that we are not comparing with the file we are intending to rename
56:4856 minutes, 48 secondsright because there is always one file with the same name. We should allow the user to rename to the same file. I mean
56:5656 minutes, 56 secondsthe agent in this case. So this will take care of both folders and files.
57:0357 minutes, 3 secondsGreat. Uh if existing ends up being true, we have to throw an error. So, a
57:1057 minutes, 10 secondsfile or folder named whatever it's named already exists. As simple as that. And
57:1757 minutes, 17 secondsthen let's go ahead and patch this arguments file ID name arguments name updated at date.now.
57:2757 minutes, 27 secondsAnd finally, return arguments file ID.
57:3257 minutes, 32 secondsTo be consistent, I'm going to add a little comment here simply so I know that all of these ones are used for agent tools. So this one would be for
57:4157 minutes, 41 secondsrename file tool. There is uh only last one we have to do uh which is the delete
57:4957 minutes, 49 secondsfile mutation. So I'm going to go ahead and define it here.
57:5657 minutes, 56 secondsCan I quickly copy the comment here and just change this to delete file
58:0458 minutes, 4 secondstool? There we go. It will accept internal key and file ID. And after we validate the internal key, let's check
58:1258 minutes, 12 secondsif the file even exists in the first place. And then depending if this is a folder, we have to recursively delete file folder and all of its descendants.
58:2358 minutes, 23 secondsSo let's go ahead and define a constant delete recursive. It's going to be an asynchronous function which accepts file
58:3258 minutes, 32 secondsID to be a type of arguments file ID.
58:3858 minutes, 38 secondsThen inside let's first fetch the item item await context database get file ID.
58:4758 minutes, 47 secondsIf we failed to fetch it, let's break this function.
58:5158 minutes, 51 secondsThen let's check if it's a folder, delete all the children first. So if
58:5858 minutes, 58 secondsitem type is equal to a folder, first let's query all the children by using by
59:0459 minutes, 4 secondsproject parent query using the file ID that's currently passed here. There we go. Once we have the children, we're
59:1359 minutes, 13 secondsgoing to delete them using the very same method. So for child of children call
59:2159 minutes, 21 secondsitself it's a recursive method and this way if we encounter another folder it's going to do the same until
59:3159 minutes, 31 secondsall files are deleted. All right so that's why we're developing a recursive method.
59:3759 minutes, 37 secondsNow we also have to delete the storage file if it exists. We currently don't really use this at all, but it's
59:4559 minutes, 45 secondsimportant to not forget that we will have a way to store binary files. We will see this in action once we
59:5359 minutes, 53 secondsimplement GitHub imports. So, if the file was a binary file, we should delete its equivalent uh storage key.
1:00:031 hour, 3 secondsOtherwise, it's just going to be taking up space. And then finally, let's delete the file or folder itself.
1:00:121 hour, 12 secondsAnd then we actually have to call that function for the first time. So await delete recursive with arguments file ID
1:00:191 hour, 19 secondsthat the agent provided. And let's return arguments file ID. This way we are completely ready to develop our
1:00:271 hour, 27 secondsexecution tools. We don't have to worry about revisiting this file again for agent purposes. At least I'm pretty sure this is all that we need. Most of these
1:00:361 hour, 36 secondsare pretty similar. You can always visit the source code if you're unsure or if you think you've made a mistake or if something doesn't work. Great. Now that
1:00:451 hour, 45 secondswe have this developed, uh let's actually go ahead and develop the agent.
1:00:511 hour, 51 secondsSo the work we have developed now is inside of process message. So inside of conversations inest process message.ts.
1:01:011 hour, 1 minute, 1 secondSo far what we have in here is a cancel event. We have a proper on failure. if something goes wrong. But we don't actually have a real uh message.
1:01:131 hour, 1 minute, 13 secondsYou can see we are just pretending to do some AI processing here. So let's go ahead and change that. Let's actually
1:01:201 hour, 1 minute, 20 secondsstart uh well doing everything that we need. Let's start by destructuring the proper items. So it's no longer going to
1:01:291 hour, 1 minute, 29 secondsbe just message ID. It's now conversation ID, project ID, message ID, and the actual message. The internal key check can stay the same. That's good.
1:01:411 hour, 1 minute, 41 secondsNow, we don't have to delete sleep. What I would do is wait for database sync and give it maybe one or maximum 5 seconds.
1:01:511 hour, 1 minute, 51 secondsAnd to do, I'm going to add check if this is needed. Uh I'm doing this because during my development I've encountered
1:01:591 hour, 1 minute, 59 secondsum some kind of out of sync state where an ingest agent can run faster than convex database updates and that kind of
1:02:081 hour, 2 minutes, 8 secondsputs it in a weird position. I'm 99% sure this is not needed. But just to stay true to my original source code, I
1:02:161 hour, 2 minutes, 16 secondswill show you that I had this and we're going to try and remove it later and then we're going to see what happens.
1:02:221 hour, 2 minutes, 22 secondsAll right. So the first thing we have to do is we have to change the conversation's title. So get conversation for a title generation
1:02:291 hour, 2 minutes, 29 secondscheck. And now let's go ahead and do the following. So we are defining a new
1:02:361 hour, 2 minutes, 36 secondsstep. Basically we're going to get the conversation using a step. So await
1:02:431 hour, 2 minutes, 43 secondsstep.run which we're going to call get conversation. And in here we are very simply going to return await
1:02:511 hour, 2 minutes, 51 secondsconvex.query API dots system get conversation by id
1:02:591 hour, 2 minutes, 59 secondspass in the internal key and the conversation ID. This way we can use the
1:03:061 hour, 3 minutes, 6 secondsconversation to see uh well first of all does it exist? If it doesn't let's throw a nonretable error. It's not found.
1:03:161 hour, 3 minutes, 16 secondsThere is no need to retry any steps.
1:03:181 hour, 3 minutes, 18 secondsRight? Now that we have the conversation ID, uh we can also fetch recent messages for conversation context. So again another step we are defining here.
1:03:311 hour, 3 minutes, 31 secondsGet recent messages.
1:03:331 hour, 3 minutes, 33 secondsAnd inside of here we are going to call our API system get recent messages query with the internal key conversation ID.
1:03:431 hour, 3 minutes, 43 secondsand we're going to limit it to 10 messages. Of course, depending on how good AI models get, or more precisely, how cheap AI models get, you might
1:03:511 hour, 3 minutes, 51 secondsincrease this, but the more context you give it, the worse uh results it actually gives you right now, and it's
1:03:591 hour, 3 minutes, 59 secondsjust more expensive altogether. So, that's why 10 is kind of a sweet spot right now. Great. So, now we have the entire conversation object. We have the
1:04:071 hour, 4 minutes, 7 seconds10 most recent messages inside of this conversation for context. And what we can do now is we can build the system
1:04:151 hour, 4 minutes, 15 secondsprompt. So I'm going to add a little comment here. We're not going to build system prompt with conversation history.
1:04:221 hour, 4 minutes, 22 secondsWe're going to exclude the current processing message though. So let's start by defining the system prompt in a
1:04:291 hour, 4 minutes, 29 secondschangeable let and we're going to give it coding agent system prompt which we can import from constants. Remember we
1:04:371 hour, 4 minutes, 37 secondsdeveloped this. I told you you can find it in the source code or in the public assets along with the title generator system prompt. This is also optimized
1:04:461 hour, 4 minutes, 46 secondsfor anthropic models. Uh it should work just fine with Gemini models too, but anthropic models work very well when it
1:04:551 hour, 4 minutes, 55 secondscomes to XML. I'm not sure what is the structure for other ones, but I think this should work just fine for all
1:05:021 hour, 5 minutes, 2 secondsgenerally. Great. So, by default, the system prompt is just the default coding agent system prompt. But what we're
1:05:091 hour, 5 minutes, 9 secondsgoing to do now is we're going to attempt to inject the context of the recent messages into the prompt. So,
1:05:171 hour, 5 minutes, 17 secondsfirst we're going to filter out the current processing message. So, no need for that. We are just interested in the past, right? So, context messages recent
1:05:261 hour, 5 minutes, 26 secondsmessages do. And we are simply looking at the message, the current message ID, and we remove it from the last 10 recent
1:05:351 hour, 5 minutes, 35 secondsmessages because we're not interested to adding that into the context. That message will be processed either way.
1:05:411 hour, 5 minutes, 41 secondsAnd now we have to check are there any messages at all before this message? But because maybe it's the first one, right?
1:05:501 hour, 5 minutes, 50 secondsNow, if it is, we have to create that history text using context messages. And
1:05:561 hour, 5 minutes, 56 secondsthen we have to map each message inside of the context messages with the
1:06:031 hour, 6 minutes, 3 secondsfiltered out current message. So each message will return a template literal string message roll to uppercase which it's basically going to look like this.
1:06:141 hour, 6 minutes, 14 secondsIt's going to look like assistant how can I help you? And then it's going to be user do this and this. So that's going to be the history basically.
1:06:251 hour, 6 minutes, 25 secondsThat's why we are doing this. Message roll colon message.content. That's the structure we are developing right now.
1:06:331 hour, 6 minutes, 33 secondsAnd let's also join with backward slashbackward slashn. Uh this basically
1:06:401 hour, 6 minutes, 40 secondsmeans empty space. And I think AI likes it this way. And what we're going to do
1:06:471 hour, 6 minutes, 47 secondsnow is we're going to append to the system prompt all of this history text.
1:06:531 hour, 6 minutes, 53 secondsSo system prompt plus equals and I would highly recommend just using the link on
1:07:001 hour, 7 minutesthe screen to uh copy this part or using uh you can again you can use the source code by going directly instead of the
1:07:071 hour, 7 minutes, 7 secondsprocess message to just copy this. Of course you can also pause the screen if you want to write it out or you can use the public assets folder.
1:07:171 hour, 7 minutes, 17 secondsGreat. Now we have the updated system prompt. Now let's see if we should generate a new title or not. So how do
1:07:251 hour, 7 minutes, 25 secondswe define that? Well, we should have constants.ts in the convex folder. And in here you
1:07:341 hour, 7 minutes, 34 secondsshould find default conversation title new conversation.
1:07:381 hour, 7 minutes, 38 secondsSo what we're going to do now here is we are very simply going to check if the current conversation.title matches the default conversation title.
1:07:511 hour, 7 minutes, 51 secondsNow you can make sure to just import this from convex constants. Is this the most you know nice way to do this? H
1:07:591 hour, 7 minutes, 59 secondsthere are probably better ways you know inside of your schema. We could have nicely added something like is title
1:08:071 hour, 8 minutes, 7 secondsupdated something like that but I'm just using a very quick and easy way to do that. Uh, also I'm not sure how
1:08:171 hour, 8 minutes, 17 secondsthis works, right? I can import from convex constants. So I I assume everything is fine. I mean convex is
1:08:251 hour, 8 minutes, 25 secondsjust a folder. So yes, this should be working just fine. This isn't a protected folder or anything. But in
1:08:331 hour, 8 minutes, 33 secondscase this ever causes problems, you can always try moving constants somewhere outside and then just having duplicate
1:08:401 hour, 8 minutes, 40 secondsdefault conversation title one in convex for the convex functions. Let's see if I go find in folder and if I search for
1:08:501 hour, 8 minutes, 50 secondsdefault conversation title. Oh, looks like we're only exporting from here. So perhaps we don't even need this here.
1:08:591 hour, 8 minutes, 59 secondsLet me go ahead and actually improve this if I can at the moment. So I want to find all the places where I'm using
1:09:061 hour, 9 minutes, 6 secondsdefault conversation title. Uh I can see I'm using it in the conversation sidebar and I'm using it in the process message but I'm not actually using it in convex.
1:09:171 hour, 9 minutes, 17 secondsSo it makes no sense that this constants file is there. Obviously I planned on using it there. Maybe I will in the future. For now what I want to do is I
1:09:261 hour, 9 minutes, 26 secondswant to move it. and I'm going to move it. Uh, so I'm going to copy the constants file and I'm going inside of
1:09:331 hour, 9 minutes, 33 secondsfeatures conversations right here. So we already have constants inside of the inest folder. I want to
1:09:421 hour, 9 minutes, 42 secondskeep that there. These are system prompts, right? So no need to uh pollute that. So make sure that you have new
1:09:491 hour, 9 minutes, 49 secondsconstants.ts DS inside of your conversations folder and inside of your convex delete constants.ds.
1:10:001 hour, 10 minutesNow your app will break. So you have to revisit conversation sidebar.tsx.
1:10:071 hour, 10 minutes, 7 secondsAnd let's go ahead and simply change this to a much more. There we go. This looks better, right? Inside of the
1:10:161 hour, 10 minutes, 16 secondsconversation sidebar features conversations components conversation sidebar. You can now import that from the near constants. Right? We've just
1:10:251 hour, 10 minutes, 25 secondswe've just added here. Nothing else needs changing in the conversation sidebar. The other problematic spot is the process message which we are
1:10:341 hour, 10 minutes, 34 secondsdeveloping right now which we can again simplify.
1:10:381 hour, 10 minutes, 38 secondsLet me see. Maybe another one back or maybe this one. There we go. So, we have
1:10:441 hour, 10 minutes, 44 secondstwo constants. One inside of the ingest folder right here, the other one outside of the inest folder, but still inside of
1:10:531 hour, 10 minutes, 53 secondsfeatures conversations. So, that's a better place to uh to have that in my
1:10:591 hour, 10 minutes, 59 secondsopinion. Great. So, if we should generate a new title, let's go ahead and
1:11:071 hour, 11 minutes, 7 secondscreate a title agent. So, if you're wondering about this create agent and
1:11:141 hour, 11 minutes, 14 secondshow it works, I highly recommend having agent kit documentation open because uh I mean this is how I learned how to use
1:11:221 hour, 11 minutes, 22 secondsit. We're now going to import create agent and enthropic from injust agent kit. You can of course import Google if
1:11:291 hour, 11 minutes, 29 secondsyou're using Gemini. We've already went over how you can define different models. It works very similarly to AI SDK. So, let's actually do this. So
1:11:381 hour, 11 minutes, 38 secondslet's import create agent and enthropic from injust agent kit. I'm going to go
1:11:451 hour, 11 minutes, 45 secondsahead at the top. I'm importing create agent and enthropic from ingest agent kit. Now
1:11:551 hour, 11 minutes, 55 secondsmy title agent here will have a name title generator.
1:12:011 hour, 12 minutes, 1 secondIt will have a system prompt of title generator system prompt which I can import from dot /constance alongside my coding agent system prompt.
1:12:141 hour, 12 minutes, 14 secondsIt is this one right here the short one.
1:12:171 hour, 12 minutes, 17 secondsOnce I've added the title generator system prompt I have to define the model that is going to execute this agent. So in my case that's going to be entropic.
1:12:281 hour, 12 minutes, 28 secondsAgain, in your case, this can be whatever you want. It can be open AAI, it can be uh Grock. Uh let me see. Okay,
1:12:371 hour, 12 minutes, 37 secondsit's Gemini. It's not Google. Keep in mind that I mean we're not executing any tools yet, but in the past, Gemini had
1:12:451 hour, 12 minutes, 45 secondsvery bad performance with executing tools. So that might be something uh you should be aware of simply so you understand that you didn't do anything
1:12:531 hour, 12 minutes, 53 secondswrong. Sometimes it might just be the model. If possible in any way, using anthropic models would be amazing. But I
1:13:021 hour, 13 minutes, 2 secondsunderstand uh if it's not possible, go ahead and try with Gemini. Either way, so use a cheap model for title
1:13:101 hour, 13 minutes, 10 secondsgeneration. That's why I'm choosing Haiku because it's fast and it's cheap.
1:13:151 hour, 13 minutes, 15 secondsUh for Gemini, I'm not sure what's the equivalent, but you can just use the same model. And you have to add a default parameters. Now you don't have
1:13:231 hour, 13 minutes, 23 secondsto do this for every model for enthropic you have to otherwise you have an error right if you switch to I don't know
1:13:301 hour, 13 minutes, 30 secondsGemini let's see does it need it
1:13:381 hour, 13 minutes, 38 secondsuh no not from injust whoops so if you try gemini you can see there's no error but if I
1:13:451 hour, 13 minutes, 45 secondsuse anthropic it requires default parameters so be aware of that too temperature is going to be zero. Maximum
1:13:541 hour, 13 minutes, 54 secondstokens is going to be 50. So we don't need too much power here. We're just generating a title.
1:14:011 hour, 14 minutes, 1 secondNow let's go ahead and actually run that agent here.
1:14:061 hour, 14 minutes, 6 secondsSo await title agent.run pass in the message and pass in the step. And in here we have the output. From that
1:14:141 hour, 14 minutes, 14 secondsoutput we have to find a text message from the assistant. So the text message can be found using output.find and in
1:14:241 hour, 14 minutes, 24 secondsthat message search if the type is text and if the role is assistant. So we successfully found a response from the
1:14:301 hour, 14 minutes, 30 secondsassistant in a form of text because the assistant can return tools, executions, a bunch of things. That's why we have to
1:14:371 hour, 14 minutes, 37 secondscheck if the type is text. And now let's do if text message.ype type
1:14:441 hour, 14 minutes, 44 secondsactually is text simply because this can yield uh undefined right so if it is text let's go ahead and extract the new
1:14:541 hour, 14 minutes, 54 secondstitle which we have to update the conversation for so first things first if type of text message dot content is
1:15:021 hour, 15 minutes, 2 secondsequal to string in that case let's make sure to do text message dotcontent dot trim otherwise
1:15:121 hour, 15 minutes, 12 secondslet's do text message dotcontent dom map for each content we have simply
1:15:191 hour, 15 minutes, 19 secondsreturn the text part of that content join all of it and then trim it what we're doing here is we're handling
1:15:271 hour, 15 minutes, 27 secondsvarious scenarios in uh ways AI assistants can respond uh you can try and be you know strict with AI
1:15:361 hour, 15 minutes, 36 secondsassistance to always to tell them to basically do this but you can never rely on them fully uh that's why We are doing the trimming and the joining. And then
1:15:461 hour, 15 minutes, 46 secondsfinally, if we manage to obtain the title, let's go ahead and do await step.r run
1:15:551 hour, 15 minutes, 55 secondsupdate title. Let's do update conversation title. It's going to be an asynchronous method.
1:16:021 hour, 16 minutes, 2 secondsLet's do await convex dot mutation APIs system update conversation title which we've developed at the start.
1:16:121 hour, 16 minutes, 12 secondspass in the internal key conversation ID and the new title. So you remember we developed this update conversation title
1:16:211 hour, 16 minutes, 21 secondsused for agent to update the conversation title accepts internal key conversation ID and very simply the new
1:16:281 hour, 16 minutes, 28 secondstitle and we are using it right here to let the agent do the update it needs to
1:16:341 hour, 16 minutes, 34 secondsdo. Perfect. So, uh perhaps, um we could already try this out. I think let's see.
1:16:451 hour, 16 minutes, 45 secondsLet's see if we can try this out. I'm going to refresh my Polar app here. Uh my Polaris app here. I'm going to start
1:16:521 hour, 16 minutes, 52 secondsa brand new conversation and I'm going to try and ask it something specific.
1:16:571 hour, 16 minutes, 57 secondsSet up a React plus V project. I'm going to try something like that and let's see
1:17:041 hour, 17 minutes, 4 secondsif it will uh run this or not. Uh because I'm not sure we
1:17:111 hour, 17 minutes, 11 secondsit's not doing anything. And I think it's because um let's see.
1:17:191 hour, 17 minutes, 19 secondsShould generate title. I think all of this passes. I just think that the title agent H
1:17:281 hour, 17 minutes, 28 secondsI'm not 100% sure if it's up to us uh or if it's up to something else.
1:17:381 hour, 17 minutes, 38 secondsI what I'm interested in is the actual inest server here. Oh, looks like there is error here. Oh, my balance is too
1:17:471 hour, 17 minutes, 47 secondslow. Okay, so that's the problem. I'm going to go ahead and just update my anthropic balance.
1:17:541 hour, 17 minutes, 54 secondsAnd just as I uh updated my balance, you can see that the next one succeeded. So let's go ahead and look at it again in
1:18:041 hour, 18 minutes, 4 secondsaction. So create a React plus V project. Right now it is named new
1:18:111 hour, 18 minutes, 11 secondsconversation, but after it processes this, it should change this to reactivate project setup guide. There we
1:18:191 hour, 18 minutes, 19 secondsgo. So, our first agent actually works and it works quite well and it's quite cheap and fast. And basically, this is a
1:18:291 hour, 18 minutes, 29 secondssuper primitive version of what we're going to build next, which is another agent, but it's going to be a coding
1:18:371 hour, 18 minutes, 37 secondsagent. And it's going to be uh way more advanced in a sense that well, it will be able to call and execute tools. So, let's go ahead and start doing that.
1:18:491 hour, 18 minutes, 49 secondscreate the coding agent with file tools.
1:18:521 hour, 18 minutes, 52 secondsWe're going to start by defining the coding agent and let's go ahead and give it the name.
1:18:591 hour, 18 minutes, 59 secondsI'm going to call this Polaris. I'm going to give it a description of an expert AI coding assistant. The system
1:19:081 hour, 19 minutes, 8 secondswill be a system prompt. Remember, we have extended the system prompt with the history text, right? With all the
1:19:161 hour, 19 minutes, 16 secondsprevious messages. So now the system prompt is much better and now we have to define the model. Again this is uh your
1:19:241 hour, 19 minutes, 24 secondsown choice. Again anthropic is really really impressive when it comes to tool execution. Uh so I'm going to go ahead and use claude oppus simply opus oppus.
1:19:361 hour, 19 minutes, 36 secondsI'm not sure how you pronounce it simply because I found it to be you know the most impressive. It's also very expensive so you know be careful. You
1:19:441 hour, 19 minutes, 44 secondscan also do it with haiku but uh the better the model is the better the results are going to be right and you need to pass default parameters. So
1:19:521 hour, 19 minutes, 52 secondstemperature.3 max tokens 16,000.
1:19:571 hour, 19 minutes, 57 secondsSo these are random limits I found work well. You can of course tweak them if you know what you're doing. And in here
1:20:051 hour, 20 minutes, 5 secondswe're going to add tools. Right now we have uh no tools at all. So, how about
1:20:131 hour, 20 minutes, 13 secondswe create our first tool? Uh, I'm trying to think of the simplest one of these we
1:20:201 hour, 20 minutes, 20 secondscan do. Well, let's just start with read files tool. That's going to be the one we're going to need. So, I will simply
1:20:301 hour, 20 minutes, 30 secondsclose everything that's not process message. And inside of the ingest folder, let's go ahead and create a new
1:20:371 hour, 20 minutes, 37 secondsfolder called tools. and inside read files.ts.
1:20:451 hour, 20 minutes, 45 secondsNow I'm going to import zod and create tool from ing inest agent kit. Again I
1:20:531 hour, 20 minutes, 53 secondswould highly recommend that while you're doing this you're also reading the documentation on tools. So you are not
1:21:001 hour, 21 minutesyou know just blindly following but understanding where I found this information and how I know how to write it. Right.
1:21:081 hour, 21 minutes, 8 secondsAll right. So once you've imported zod and create tool, let's also import the convex uh util API and ID from convex generated folder.
1:21:211 hour, 21 minutes, 21 secondsCreate an interface read files tool options to be internal key and a string.
1:21:271 hour, 21 minutes, 27 secondsAnd let's also define the params schema here. So we're going to accept file ids
1:21:341 hour, 21 minutes, 34 secondswhich is going to be an array of ids and we're going to throw errors if it's empty or if the array is empty.
1:21:441 hour, 21 minutes, 44 secondsSo now let's go ahead and let's create create read files tool which accepts the
1:21:501 hour, 21 minutes, 50 secondsinternal key and it simply uses the interface we defined above.
1:21:571 hour, 21 minutes, 57 secondsNow let's go ahead and immediately return create tool.
1:22:031 hour, 22 minutes, 3 secondsLet's give it a name of read files. So that's the name of the tool. Let's give it a description. Descriptions are
1:22:101 hour, 22 minutes, 10 secondsactually quite important. The same as the name of the tool. So read the content of files from the project returns file contents. Now let's go
1:22:201 hour, 22 minutes, 20 secondsahead and define the parameters. So the parameters are az.object object
1:22:271 hour, 22 minutes, 27 secondsfile ids and then inside we're going to define an array of string with describe
1:22:351 hour, 22 minutes, 35 secondsarray of file ids to read like that.
1:22:421 hour, 22 minutes, 42 secondsThen we have a handler in which we can uh get the params
1:22:501 hour, 22 minutes, 50 secondsand we can get step give it an alias of tool step for easier understanding.
1:22:591 hour, 22 minutes, 59 secondsLet's go ahead and do parsed params schema safe parse params. This way it
1:23:071 hour, 23 minutes, 7 secondswill throw an error if the tool is attempting to fire with um weird parameters if they are not what we
1:23:151 hour, 23 minutes, 15 secondsexpect. Right? So if not parsed success let's go ahead and return error
1:23:251 hour, 23 minutes, 25 secondsparsed error issues first in the array message and this will
1:23:331 hour, 23 minutes, 33 secondsbe sent to the agent. So the agent can then retry even if it fails. So it won't make the same mistake twice. Let's
1:23:411 hour, 23 minutes, 41 secondsdstructure the file IDs from uh parsed data. So now we have completely valid
1:23:501 hour, 23 minutes, 50 secondsfile ids at this point or at least we should have. Let's go ahead and open a try and catch block here.
1:23:581 hour, 23 minutes, 58 secondsAnd I'm going to do return await tool step question mark.run run read files.
1:24:061 hour, 24 minutes, 6 secondsIt's going to be an asynchronous method.
1:24:081 hour, 24 minutes, 8 secondsAnd in here, let's go ahead and define the results.
1:24:131 hour, 24 minutes, 13 secondsResults by default are going to be an empty array. But what we expect here is an array with objects. Each object
1:24:211 hour, 24 minutes, 21 secondsshould have an ID, a name, and the content inside. So now that we have that defined, let's run them through a for loop. for const file id of file ids.
1:24:341 hour, 24 minutes, 34 secondsLet's go ahead and fetch the file using await convex query API system get file
1:24:411 hour, 24 minutes, 41 secondsby id pass in the internal key pass in file ID file ID as ID files so we don't
1:24:501 hour, 24 minutes, 50 secondshave any type errors if we successfully fetch the file and the file has content. Let's do
1:24:581 hour, 24 minutes, 58 secondsresults.push ID file ID name file name content file.content.
1:25:091 hour, 25 minutes, 9 secondsThere we go.
1:25:121 hour, 25 minutes, 12 secondsNow that we have that defined, let's go ahead and check if
1:25:191 hour, 25 minutes, 19 secondsresults.length is equal to zero. Let's return an error. No files found with provided ids.
1:25:301 hour, 25 minutes, 30 secondsUse list files to get valid file IDs.
1:25:371 hour, 25 minutes, 37 secondsAnd writing this error message, I realized before we can actually test this out. Uh we will have to write one
1:25:451 hour, 25 minutes, 45 secondsmore function. Sorry about that. But yes, um I completely forgot that the agent uh right now doesn't really know where to pass the file ids from, right?
1:25:581 hour, 25 minutes, 58 secondsHow is it supposed to know what file ids to read? Right? So this function will actually be used once the agent is instructed to read a specific file ID.
1:26:101 hour, 26 minutes, 10 secondsSo still we're going to need this function either way. Um we're just not going to be able to test it out right away. So uh make sure to return
1:26:191 hour, 26 minutes, 19 secondsstringified results and in the catch method here grab the error and return error reading files.
1:26:291 hour, 26 minutes, 29 secondsError instance of error display the error message otherwise
1:26:371 hour, 26 minutes, 37 secondsunknown error like so. Let me go ahead and check what
1:26:441 hour, 26 minutes, 44 secondsthe uh Okay, I should not do something here. I should end that here. There we
1:26:531 hour, 26 minutes, 53 secondsgo. All right. So, that's our first function implemented. And now that we have read files tool, let's go back
1:27:011 hour, 27 minutes, 1 secondinstead of process message here. And let's go ahead and pass create read files tool. You can import it from tool
1:27:091 hour, 27 minutes, 9 secondsread files. And in here simply pass the internal key. Now technically
1:27:161 hour, 27 minutes, 16 secondswe could have just as easily used the internal key uh right here, right? We
1:27:231 hour, 27 minutes, 23 secondscould have defined const internal key process.vironment blah blah blah. But if
1:27:321 hour, 27 minutes, 32 secondswe pass it as a prop here, it's kind of already validated at this point, you know, simply because we have used it in
1:27:401 hour, 27 minutes, 40 secondsall of these previous steps and we've checked if it's valid here, right? So I kind of feel like we can just pass it. I
1:27:481 hour, 27 minutes, 48 secondsdon't know if you feel like this is not a good practice, you can of course define it here directly. All right, so that's the create uh read files tool.
1:27:571 hour, 27 minutes, 57 secondsNow let's go ahead and implement create list files tool. I'm going to copy read files and I will rename it to list files.ts.
1:28:081 hour, 28 minutes, 8 secondsSo let's check. First things first, I will modify the interface which is now called list files tool options. It will
1:28:161 hour, 28 minutes, 16 secondsaccept the project ID and the internal key. It's not going to have any params since it's just going to read all the
1:28:231 hour, 28 minutes, 23 secondsfiles that we have. So let's go ahead and change this to it's no longer called
1:28:301 hour, 28 minutes, 30 secondscreate read files tool. It is create list files tool which uses list file
1:28:361 hour, 28 minutes, 36 secondstool options and extracts project ID and the internal key.
1:28:431 hour, 28 minutes, 43 secondsThe create tool itself will have a name list files and the description is also uh as always important and you might
1:28:521 hour, 28 minutes, 52 secondswant to copy this one from the source code as well simply because it's long. I mean or you can just pause the screen and you know write it out. List all
1:29:011 hour, 29 minutes, 1 secondfiles and folders in the project. Return names, IDs, types and parent ID for each of them. Items with parent ID null are
1:29:101 hour, 29 minutes, 10 secondsat root level. Use the parent ID to understand the folder structure. Items with the same parent ID are in the same
1:29:181 hour, 29 minutes, 18 secondsfolder. So I'm just giving it a little bit of context of the of what it will receive. Right now the parameters are
1:29:251 hour, 29 minutes, 25 secondsjust going to be an empty object. So write them as such. To skip the params you can just write an underscore here.
1:29:331 hour, 29 minutes, 33 secondsNow we're not going to have anything to parse. So we can remove all of that.
1:29:381 hour, 29 minutes, 38 secondsNow inside of the try method here, let's go ahead and do a similar thing. So return await tool.step. This will be called list files and it's going to be a little bit simpler.
1:29:501 hour, 29 minutes, 50 secondsSo I'm going to remove everything inside of here. Can I do that? I think I went a bit too much.
1:30:011 hour, 30 minutes, 1 secondOkay. And we still Okay. Let me just bring this back. I think I just needed to remove
1:30:081 hour, 30 minutes, 8 secondsthis. There we go. All right. So, tool.steplist files. The first thing we're going to do is call convex.query
1:30:181 hour, 30 minutes, 18 secondsAPI system get project files. So, we developed this specifically for list files tool. And all it does is list all
1:30:271 hour, 30 minutes, 27 secondsthe files in the project using the internal key and the project ID. So we make sure that we pass the internal key
1:30:341 hour, 30 minutes, 34 secondsand the project ID here. Perfect. Now let's go ahead and sort folders first then files alphabetically.
1:30:451 hour, 30 minutes, 45 secondsSo we've already done this before for our file explorer because it displays it in the exact same file. We're just giving the agent the exact same view
1:30:541 hour, 30 minutes, 54 secondsnow. So we're sorting the files by type first and then using a simple local
1:31:011 hour, 31 minutes, 1 secondcompare for the name alphabetical and then let's go ahead and structure the file list. So using those sorted
1:31:101 hour, 31 minutes, 10 secondsfiles, let's go ahead and create an array of objects with an ID of the file, name of the file, type, and a parent ID
1:31:181 hour, 31 minutes, 18 secondsor null. Just make sure it's not undefined. So parent ID or null like this
1:31:251 hour, 31 minutes, 25 secondsand then let's go ahead and let's return JSON stringify file list. The error will be error listing files or unknown error.
1:31:361 hour, 31 minutes, 36 secondsThere we go. Another tool finished. Let me remove the extra space here. Let's go back instead of processing message here and let's do create list files tool.
1:31:481 hour, 31 minutes, 48 secondsSo from list files and let's go ahead and let's pass in the project ID and the internal key.
1:31:571 hour, 31 minutes, 57 secondsNow I will order this one first uh simply because it's going to be used more often than the read files tool. And
1:32:051 hour, 32 minutes, 5 secondsof course I've messed up my imports. So let me just go ahead and quickly fix that.
1:32:111 hour, 32 minutes, 11 secondsSo let's see. Is it still okay?
1:32:181 hour, 32 minutes, 18 secondsSo in here internal key and project ID and I change the order. That's it. So I
1:32:261 hour, 32 minutes, 26 secondsthink that at this point we might already have something. So uh actually I
1:32:351 hour, 32 minutes, 35 secondsthought we can already try it but we can't try it simply because the coding agent is unused. So we defined the tools great but u there's nowhere to try it
1:32:441 hour, 32 minutes, 44 secondsout right. So, okay, I'm going to stop at these two tools simply because uh I think it's better for us to start seeing
1:32:521 hour, 32 minutes, 52 secondssome results before we write all the tools because we just won't be able to see the results until we finish the entire thing. So, uh how do we call this
1:33:021 hour, 33 minutes, 2 secondscoding agent? Well, what we have to do is we have to create a network. Again, uh this is a term from agent kit. So I
1:33:121 hour, 33 minutes, 12 secondshighly recommend to read about networks to understand how they work and why we uh need them. Specifically, we need them
1:33:201 hour, 33 minutes, 20 secondsbecause we need to create loops. We need the agent to iterate with itself uh with its state and call various tools until
1:33:291 hour, 33 minutes, 29 secondsit determines that what there is no more work to be done. That's why you need networks to create loops, right? Because
1:33:371 hour, 33 minutes, 37 secondsagents, smart agents work in loops until they're finished.
1:33:411 hour, 33 minutes, 41 secondsSo in order to do that we're using the create network.
1:33:461 hour, 33 minutes, 46 secondsSo let's import create network from ing inest agent kit.
1:33:531 hour, 33 minutes, 53 secondsIn the create network give it a name polaris network.
1:33:581 hour, 33 minutes, 58 secondsLet's give it a which is coding agent just a single one. And then we have something called max iterations. So I
1:34:061 hour, 34 minutes, 6 secondskeep this at 20 simply because I find it to be a sweet spot. Basically iterations are how many loops it you will allow it to create before you abruptly stop it.
1:34:181 hour, 34 minutes, 18 secondsThis def depends on your budget most of the time, right? So if you have an infinite budget, you might run this infinitely, but you most likely want to
1:34:271 hour, 34 minutes, 27 secondskeep it at something like 20. For example, each tool execution is an iteration, right? So, if you have a
1:34:351 hour, 34 minutes, 35 secondsthousand tools, well, I mean, uh, it's probably not going to use all tools all the time, but depending on how smart
1:34:431 hour, 34 minutes, 43 secondsyour agent is, you might need more or less iterations. Again, this is something you can read more and and understand by reading the documentation
1:34:501 hour, 34 minutes, 50 secondshere. So, routing and maximum iterations. You can see why and how you can define what it is. So specifying a
1:34:581 hour, 34 minutes, 58 secondsmax iteration option is useful when using a default routing engine or a hybrid router to avoid infinite loops.
1:35:041 hour, 35 minutes, 4 secondsYes, I mean it's not like it's going to run always infinitely, but there is a chance it can get stuck and it can uh
1:35:111 hour, 35 minutes, 11 secondscause you a very big bill. Great. Now let's go ahead and define the actual router here.
1:35:191 hour, 35 minutes, 19 secondsSo we extract network from here. And what we have to do is we have to get the
1:35:261 hour, 35 minutes, 26 secondslast result. The last result is network.state.res results at minus one. Now let's go ahead
1:35:341 hour, 35 minutes, 34 secondsand check if we have a text response from that last result. So last result question mark.output sum message has a
1:35:441 hour, 35 minutes, 44 secondstype of text and it's coming from an assistant. Similarly to how we checked if the title is finished, right? We
1:35:521 hour, 35 minutes, 52 secondschecked if the assistant message is text. So we are now doing the same here.
1:35:561 hour, 35 minutes, 56 secondsWe are checking if it's finished. So just as we developed has text response, let's do has tool calls. It's the same
1:36:051 hour, 36 minutes, 5 secondsthing. Last result output sum message.ype is tool call. This should be type safe, I believe. Yes, tool call.
1:36:151 hour, 36 minutes, 15 secondsSo now it's it depends which model you're using. Again, for example,
1:36:221 hour, 36 minutes, 22 secondsAnthropic can output both text and the tool calls together.
1:36:281 hour, 36 minutes, 28 secondsGemini, for example, doesn't do that or open AI. So, what I'm going to do here is only stop if there is text without
1:36:371 hour, 36 minutes, 37 secondstool calls final response. So if we detect that an assistant just sent us a
1:36:461 hour, 36 minutes, 46 secondstext response and assistant has no more tool calls, we return undefined which basically breaks the router or it
1:36:541 hour, 36 minutes, 54 secondssignifies that it's finished. Otherwise we return coding agent which symbolizes run another loop basically. So basically
1:37:031 hour, 37 minutes, 3 secondsthis is the code which decides should we do another iteration or should we break it? We're finished. All right.
1:37:111 hour, 37 minutes, 11 secondsNow, let's actually run the agent like this result await network.run with
1:37:181 hour, 37 minutes, 18 secondsa message. Now, let's go ahead and let's extract the assistant's last text response from the last agent result. So
1:37:261 hour, 37 minutes, 26 secondsagain, last results at minus one. Then let's find the text
1:37:341 hour, 37 minutes, 34 secondsmessage. If message type is text and message.roll role is assistant.
1:37:401 hour, 37 minutes, 40 secondsLet's go ahead and give it a default assistant response.
1:37:451 hour, 37 minutes, 45 secondsI processed your request. Let me know if you need anything else. So, we're going to use this if we are just unable to find the last message of the assistant.
1:37:541 hour, 37 minutes, 54 secondsRight? Depending on which uh AI model you use, uh this code might work or maybe it expects something completely
1:38:011 hour, 38 minutes, 1 seconddifferent. These AI models change very frequently. Uh, but you will be able to debug this yourself if you've come this far into the tutorial. I will show you
1:38:101 hour, 38 minutes, 10 secondshow you can see the output and then you will be able to tweak things, maybe even ask AI to help you with it. Right? So,
1:38:171 hour, 38 minutes, 17 secondswe now have to check if we can modify the default assistant response. So, if the type of text message content is
1:38:251 hour, 38 minutes, 25 secondsactually a string, we're going to use text message dot content.
1:38:301 hour, 38 minutes, 30 secondsNow, on an off chance, it's not a string, but instead it's an array. We're going to map over the content, return the text part of the content, and then
1:38:391 hour, 38 minutes, 39 secondsjoin it like so. There we go. And now that we have the assistant response, we can actually update the assistant
1:38:471 hour, 38 minutes, 47 secondsmessage. So, I'm going to add a little comment here. Update the assistant message with the response. This also sets the status to completed. So, update
1:38:561 hour, 38 minutes, 56 secondsassistant message. And this time the content will be assistant response.
1:39:011 hour, 39 minutes, 1 secondThere we go. And what I like to do at the very end here is simply return
1:39:071 hour, 39 minutes, 7 secondssuccess true message ID and conversation ID so it's easier to debug if it goes wrong.
1:39:161 hour, 39 minutes, 16 secondsAll right, I think that now we might be able to try this out. So I'm just going to copy this entire file here and I'm going to create a new file functions.ts.
1:39:261 hour, 39 minutes, 26 secondsTS and I will paste it inside. So I believe
1:39:321 hour, 39 minutes, 32 secondsthis is now saved. It is perfect. So I will start a new conversation and I will focus on the inest server too.
1:39:421 hour, 39 minutes, 42 secondsAnd let's see. So what files do I have in this project? Did we do this correctly? Did we forget to plug
1:39:501 hour, 39 minutes, 50 secondssomething in? Let's just see. So right now it's generating the title list project files and now you can see it is
1:39:581 hour, 39 minutes, 58 secondscreating the network. It is listing files successfully. So that's great. You can see it it managed to call the tool
1:40:071 hour, 40 minutes, 7 secondslist files. You can see it didn't even need the read files tool. It just needed list files which gave it back an array
1:40:161 hour, 40 minutes, 16 secondswith functions.ts ts a type of file parent ID null and I think the response should be there we go you have two files
1:40:251 hour, 40 minutes, 25 secondsin this project both at the root level functions.ts a TypeScript file hello.jsx
1:40:311 hour, 40 minutes, 31 secondsJSX a React JSX component file. There are no folders in the project currently.
1:40:371 hour, 40 minutes, 37 secondsBoth files are located at the root directory. Amazing. So, we successfully
1:40:431 hour, 40 minutes, 43 secondsmade an agent uh use a tool called create list files and give us a
1:40:521 hour, 40 minutes, 52 secondsresponse. Now, I've succeeded with this with Enthropic. Uh, I'm not sure what the results are going to be with Gemini.
1:41:001 hour, 41 minutesTechnically, it should work just as fine with Gemini, but you saw me have a bunch of problems with Gemini before. Uh, I
1:41:081 hour, 41 minutes, 8 secondskeep running into timeouts and limited requests. I'm not sure if I'm doing something wrong. Uh, but because of that, I just have to, you know, continue developing with reliable models.
1:41:191 hour, 41 minutes, 19 secondsOtherwise, it's just very, very difficult to get a proper reliable result for the tutorial. Uh still uh if you are using Gemini you know let me
1:41:271 hour, 41 minutes, 27 secondsknow in the comments if it works if it doesn't work and how you debug it uh if you encountered any problems. Uh the code itself should work just fine for
1:41:361 hour, 41 minutes, 36 secondsany model. This isn't tailored to entropic. Right? The only thing I have tailored to enthropic is making sure
1:41:441 hour, 41 minutes, 44 secondsright here that we make sure there are no tool calls because entropic also responds with tool calls. Uh for other
1:41:531 hour, 41 minutes, 53 secondsmodels, you can just check if there's a text response. It's most likely the last response. With Enthropic, it can't really be as reliable.
1:42:011 hour, 42 minutes, 1 secondAll right. All that's left to do now is just create more tools. So, we only have two tools now. And we have to add update
1:42:101 hour, 42 minutes, 10 secondsfile, create file, create folder, rename file, delete files, and also scrape URLs for file crawl.
1:42:191 hour, 42 minutes, 19 secondsI'm going to start with creating the update file tool so we finally see some changes in action. I will copy read
1:42:271 hour, 42 minutes, 27 secondsfiles. I will paste it and I will rename it to update file.ts.
1:42:331 hour, 42 minutes, 33 secondsThen I'm going to update the interface here to be update file pool options with internal key. I'm going to modify the
1:42:411 hour, 42 minutes, 41 secondsparams schema to accept an individual file ID as well as the new content we attempt to update. I'm going to update
1:42:501 hour, 42 minutes, 50 secondsthe entire function here to be called create update file tool uh accept this new params and then return create tool.
1:43:011 hour, 43 minutes, 1 secondI'm going to change the name here to be update file. I will change the description to be update the content of
1:43:081 hour, 43 minutes, 8 secondsan existing file and I'm going to modify the parameters to match the schema file ID with a describe of the ID of the file
1:43:181 hour, 43 minutes, 18 secondsto update content the new content for the file. We're going to start by parsing. So this can stay the same in
1:43:271 hour, 43 minutes, 27 secondsfact and the only thing we're going to extract from the parsed data will be an individual file ID and the content. So
1:43:351 hour, 43 minutes, 35 secondspreviously it was ids but now it's file ID and content.
1:43:411 hour, 43 minutes, 41 secondsSo now what I'm going to do is I'm just going to uh validate if the file exists before I even run this step using
1:43:501 hour, 43 minutes, 50 secondsconvex.query API system get file by ID. I've mentioned it will be used by read files
1:43:581 hour, 43 minutes, 58 secondstool but it can be used by various tools basically by agent tool right get file
1:44:051 hour, 44 minutes, 5 secondsby ID accepts the internal key and the file ID and in case the file doesn't
1:44:121 hour, 44 minutes, 12 secondsexist I'm just going to go ahead and return an early error and instruct the agent to use list files to get valid
1:44:211 hour, 44 minutes, 21 secondsfile ids and I will also So check if the file type exists but its type is folder and I
1:44:301 hour, 44 minutes, 30 secondswill give the agent similar instructions. File is a folder not a file. You can only update file contents.
1:44:391 hour, 44 minutes, 39 secondsGreat. So after we do this early checks which kind of improves the user experience and they don't have to
1:44:461 hour, 44 minutes, 46 secondsbecause if you don't do this early errors it will get stuck in trying to repeat the API call because it thinks
1:44:541 hour, 44 minutes, 54 secondsthat maybe the network timed out or something. Basically the agent doesn't know what it did wrong. Right? So that's
1:45:011 hour, 45 minutes, 1 secondwhy you kind of have to do early returns with descriptive errors to let it know, hey, this is not a file ID or this is
1:45:081 hour, 45 minutes, 8 secondsthe wrong file ID. You're probably not looking for that. So the tool step uh is called update file.
1:45:191 hour, 45 minutes, 19 secondsAnd in here, well, it's actually quite simple. Let me go ahead and remove everything in here. The update file will
1:45:281 hour, 45 minutes, 28 secondssimply call a convex mutation API system update file with internal key file ID and the new content. And let's also make
1:45:371 hour, 45 minutes, 37 secondssure the agent knows it was successfully updated. In the error, I'm going to change this to error updating file unknown error. There we go. That's it.
1:45:501 hour, 45 minutes, 50 secondsNow I'm going to go ahead back inside of processing message and I'm going to pass in create update file tool with the
1:46:001 hour, 46 minutesinternal key. Make sure to import it like so. So let's see if this will work
1:46:081 hour, 46 minutes, 8 secondsnow. Um update functions ts to be a simple hello world console log. nothing else.
1:46:201 hour, 46 minutes, 20 secondsUm, we're going to see does it have enough tools? Does it need any more tools? Also, keep in mind, uh, just because it succeeds today, it might fail
1:46:291 hour, 46 minutes, 29 secondstomorrow. Uh, AI models are nondeterministic. They are unpredictable, right? Sometimes it might work a thousand times and then fail a
1:46:371 hour, 46 minutes, 37 secondsthousand first time for no reason at all. It's just got confused. Sometimes it's context, sometimes it's something
1:46:441 hour, 46 minutes, 44 secondselse. Uh, all right. Let's see what did it do here. I've updated functions.ts.
1:46:531 hour, 46 minutes, 53 secondsIt did. Perfect. So the reason it didn't immediately update here is because of the way uh we defined the this component
1:47:021 hour, 47 minutes, 2 secondsright here. Uh it cannot immediately receive updates because it will reset your cursor position and then it's very annoying to type code. So just you know
1:47:101 hour, 47 minutes, 10 secondskind of change files or change code something or restart or refresh so you can see the update here. There we go. It works. There are some bugs in styles
1:47:201 hour, 47 minutes, 20 secondshere. We're also going to take care of that. Don't worry. But uh the more important thing it works. We can now ask
1:47:271 hour, 47 minutes, 27 secondsan agent to update a specific file for us. It can find that file and it can update it. And now we're just going to
1:47:341 hour, 47 minutes, 34 secondscontinue, you know, creating tools for uh other things. Now I'm going to copy
1:47:401 hour, 47 minutes, 40 secondsupdate file and I will call this one create files. So a bulk update. And
1:47:491 hour, 47 minutes, 49 secondsagain if you don't want to write all of these one by one, you can just visit the source code of course. But I will try my
1:47:571 hour, 47 minutes, 57 secondsbest to at least kind of explain what's going on here. Even though I think at this point you understand what's going on, right? So create files tool options
1:48:041 hour, 48 minutes, 4 secondsaccepts project ID and the internal key params are parent ID an array of files and each of those files has a name and a
1:48:131 hour, 48 minutes, 13 secondscontent content can be empty right we don't require that but at least one file needs to be created if we're using this tool
1:48:221 hour, 48 minutes, 22 secondsthen we're going to change the name and the props of this tool to create create
1:48:281 hour, 48 minutes, 28 secondsfiles tool uh this error I believe is just a TypeScript server error. If I restart my VS Code, it goes away.
1:48:411 hour, 48 minutes, 41 secondsSo, we use project ID and internal key here. I'm going to go ahead and change the name of the tool to be create files.
1:48:491 hour, 48 minutes, 49 secondsI'm going to go ahead and give it a bit of a longer description simply so it works better. Create multiple files at once in the same folder. Use this to
1:48:581 hour, 48 minutes, 58 secondsbatch create files that share the same parent folder. more efficient than creating files one by one. So the reason
1:49:051 hour, 49 minutes, 5 secondsI developed this tool in the first place is because it's very easy to hit maximum iterations if you use just you know
1:49:131 hour, 49 minutes, 13 secondscreate file one by one. So this bulk create tool actually helps a lot. Now the parameters are going to be uh a bit different more of them.
1:49:241 hour, 49 minutes, 24 secondsOops. Let me just go ahead and indent this properly. There we go. So parameters are going to be an object.
1:49:321 hour, 49 minutes, 32 secondsThe first item in the object is going to be the parent ID which is a type of string and it's the ID of the parent folder. Use empty string for root level
1:49:401 hour, 49 minutes, 40 secondsmust be a valid folder ID from list files. So we indicate to the agent again if you forget how to get the ID just
1:49:481 hour, 49 minutes, 48 secondslist all files. The second argument in the parameters is an array of files and inside of that array we have an object.
1:49:581 hour, 49 minutes, 58 secondsThe object needs to have a name, the file name which is going to be created including the extension and the content
1:50:061 hour, 50 minutes, 6 secondsthe actual file content and we describe this as an array of files to create.
1:50:121 hour, 50 minutes, 12 secondsAll right. So exactly what we defined here just with describe methods.
1:50:191 hour, 50 minutes, 19 secondsSo in the handler uh again we do the parsing which is fine but we don't really expect file ID or content.
1:50:271 hour, 50 minutes, 27 secondsInstead, we expect parent ID and files.
1:50:321 hour, 50 minutes, 32 secondsNow, uh what we're going to do is I'm going to clear up this code here simply
1:50:391 hour, 50 minutes, 39 secondsbecause uh let me see. I'm going to clear this up like so. And I'm going to clear up everything in the try method.
1:50:471 hour, 50 minutes, 47 secondsWe're going to start by calling the tool.
1:50:531 hour, 50 minutes, 53 secondsSo, return. Okay. Like this.
1:50:571 hour, 50 minutes, 57 secondsreturn await toolstep.r run create files asynchronous function.
1:51:061 hour, 51 minutes, 6 secondsLet's go ahead and first resolve the parent ID.
1:51:101 hour, 51 minutes, 10 secondsNow let's check if there is a parent ID and if the parent ID is not an empty string, we're going to open another try
1:51:191 hour, 51 minutes, 19 secondsmethod here. So make sure it has an equivalent catch method down here.
1:51:251 hour, 51 minutes, 25 secondsLet's go ahead and do resolve parent ID to be parent ID as ID files.
1:51:321 hour, 51 minutes, 32 secondsThen we're going to use convex query and API system get file by ID to get the parent folder. So we pass in the
1:51:401 hour, 51 minutes, 40 secondsinternal key and file ID resolve parent ID. And we're basically doing this again to throw early errors. So if there is no
1:51:501 hour, 51 minutes, 50 secondsparent folder, we're going to do parent folder with ID. Parent ID is not found.
1:51:561 hour, 51 minutes, 56 secondsUse list files to get valid folder ids.
1:52:001 hour, 52 minutesAgain, we're just doing this for early return methods. So uh it it under it it will be much faster if we throw an early
1:52:081 hour, 52 minutes, 8 secondserror than if it has to figure out what it did wrong. So only if the agent decided to pass parent ID because the
1:52:181 hour, 52 minutes, 18 secondsagent is allowed to not pass a parent ID if it wants to create files in the root folder. So if it passes a parent ID and
1:52:261 hour, 52 minutes, 26 secondsif we detect that the parent folder cannot be loaded using that ID, we simply tell it right away, hey, something's wrong. You cannot do this.
1:52:371 hour, 52 minutes, 37 secondsSo if parent folder doesn't exist, we throw an error. If parent folder type is not a folder, we throw an error. The
1:52:451 hour, 52 minutes, 45 secondsparent ID is a file, not a folder. Use a folder ID as a parent ID. We're just making sure uh the it can understand
1:52:541 hour, 52 minutes, 54 secondswhat it's doing wrong. And in here, we just throw like an overall error invalid parent ID. Use list files to get valid
1:53:031 hour, 53 minutes, 3 secondsfolder ids or use empty string for root level.
1:53:091 hour, 53 minutes, 9 secondsGreat. And now let's go ahead and simply do convex mutation
1:53:171 hour, 53 minutes, 17 secondsAPI system create files pass in the internal key project ID parent ID and files.
1:53:271 hour, 53 minutes, 27 secondsNow in here let's see which files we have successfully created because remember create files will keep track of
1:53:371 hour, 53 minutes, 37 secondsall the results which have failed such as file already exists and all the files which have succeeded.
1:53:451 hour, 53 minutes, 45 secondsSo we are filtering out all the files which have been successfully created and those which have failed. So be mindful of the exclamation point here.
1:53:571 hour, 53 minutes, 57 secondsAnd let's start with a response. You need to give the agent a response so it knows if it did good or not. So created for example five files.
1:54:091 hour, 54 minutes, 9 secondsAnd then let's go ahead and do if created.length is larger than zero.
1:54:151 hour, 54 minutes, 15 secondsInside of the response, let's go ahead and actually display which files were just created. And then we're going to
1:54:231 hour, 54 minutes, 23 secondssimply do the same if some files have failed like so. So let me just quickly zoom out so you can see how this looks
1:54:321 hour, 54 minutes, 32 secondsin one line because when when it collapses it's kind of hard to understand. So you can pause the screen
1:54:381 hour, 54 minutes, 38 secondsand it pro copy it. All right. So we're just doing this so we have a nice response for the AI model. There we go.
1:54:481 hour, 54 minutes, 48 secondsAnd in here, let's do error creating files like this. There we go. Another
1:54:561 hour, 54 minutes, 56 secondstool finished. We're going to try this one later. I just want to work on knocking out all the uh tools that we
1:55:031 hour, 55 minutes, 3 secondsneed. So, this is the create create files tool.
1:55:101 hour, 55 minutes, 10 secondsSo, import it.
1:55:131 hour, 55 minutes, 13 secondsThere we go. The next one we're going to do is the uh create create folder tool
1:55:211 hour, 55 minutes, 21 secondswhich will accept project ID and the internal key. So we don't yet have it.
1:55:261 hour, 55 minutes, 26 secondsSo we're going to go ahead and develop it right now. So I am going to copy create files, paste it here, rename it to create folder.
1:55:391 hour, 55 minutes, 39 secondsI'm going to go ahead and change the interface.
1:55:431 hour, 55 minutes, 43 secondsThere we go. It accepts the exact same props. The params are going to be different though.
1:55:501 hour, 55 minutes, 50 secondsIt will accept the name of the folder and the parent ID in case it's a subfolder.
1:55:561 hour, 55 minutes, 56 secondsI'm going to change the props here and the name of the function to create create folder tool. And the same with the props here.
1:56:051 hour, 56 minutes, 5 secondsThen I'm going to go ahead and change the name of the tool to be create folder. I'm going to go ahead and change the description to be create a new
1:56:131 hour, 56 minutes, 13 secondsfolder in the project. I'm going to change the parameters
1:56:211 hour, 56 minutes, 21 secondsto be an object. First item in the object will be the name, the name of the folder to create and the second is going
1:56:291 hour, 56 minutes, 29 secondsto be the parent ID. So the ID not the name of the parent folder from list files or empty string if we are creating the folder at the root level.
1:56:421 hour, 56 minutes, 42 secondsGreat. So parsing works exactly the same except we are not expecting parent ID or
1:56:491 hour, 56 minutes, 49 secondsfiles. So let's just do name and parent ID.
1:56:531 hour, 56 minutes, 53 secondsNow let's go ahead and again call await tool step within try and catch except this one will be here in the create folder.
1:57:041 hour, 57 minutes, 4 secondsSo let's start by validating the parent ID if it is provided.
1:57:111 hour, 57 minutes, 11 secondsSo let's check if we have parent ID. Let's try and get the parent folder using API system get
1:57:201 hour, 57 minutes, 20 secondsfile by ID and parent ID here. Let's just do as ID files.
1:57:311 hour, 57 minutes, 31 secondsIf there is no parent folder, let's go ahead and throw the exact same error. So parent folder with ID, parent ID is not
1:57:381 hour, 57 minutes, 38 secondsfound, use list files to get the correct uh ID.
1:57:431 hour, 57 minutes, 43 secondsYou can of course I mean you can use the same errors and we do the same thing if the parent folder is not a type of
1:57:501 hour, 57 minutes, 50 secondsfolder basically as much as possible to let the agent know what it did wrong. All right.
1:57:581 hour, 57 minutes, 58 secondsSo now that we have the parent ID let's go ahead and simply
1:58:051 hour, 58 minutes, 5 secondscall the mutation. So new folder ID await convex mutation API system create folder.
1:58:121 hour, 58 minutes, 12 secondsThere we go. Pass in the internal key project ID name. And then if we have a parent ID, pass it as parent ID and cast it as ID files or pass along undefined.
1:58:251 hour, 58 minutes, 25 secondsYou can remove the created and the response. And we're very simply going to return a static response.
1:58:331 hour, 58 minutes, 33 secondsFolder created with ID folder ID error creating folder like this.
1:58:421 hour, 58 minutes, 42 secondsLet's go back inside of process message and let's go ahead and import create create folder tool like so. All
1:58:511 hour, 58 minutes, 51 secondsright. At this point, let's just try it out a bit. So we have two that we have to check. Can it create multiple files
1:58:581 hour, 58 minutes, 58 secondsand can it create a folder? Create two files named fu.tsx and bar.tsx.
1:59:091 hour, 59 minutes, 9 secondsPut simple content inside.
1:59:121 hour, 59 minutes, 12 secondsSo let's see if it is able to use the create files tool. That's the first thing we're going to do. So right now
1:59:191 hour, 59 minutes, 19 secondsit's generating the agent and it's generating the network and it uses the create files tool and you can see the output. This is what we were doing
1:59:281 hour, 59 minutes, 28 secondscreated two files fu and bar. There we go. FU and bar and very simple props
1:59:351 hour, 59 minutes, 35 secondsinside. Now I'm going to uh say create a simple folder called source nothing
1:59:431 hour, 59 minutes, 43 secondsmore. So I'm trying to give it very simple explicit instructions. Right now it should use the create folder function
1:59:521 hour, 59 minutes, 52 secondsand it is folder created with ID successfully and I have the source folder inside. Amazing. Both of our
1:59:591 hour, 59 minutes, 59 secondstools are working just fine. So now let's go ahead and add rename file tool.
2:00:082 hours, 8 secondsThe rename file tool is quite similar to update file. So, close others. Okay, I'm
2:00:162 hours, 16 secondsgoing to copy update file and I'm going to rename it to rename file tool.
2:00:242 hours, 24 secondsNow, I'm going to go ahead and change the interface. The prop is exactly the same. The params are quite similar
2:00:312 hours, 31 secondsexcept instead of content, it's going to be the new name. Now, I'm going to update the props and the name of the tool itself to create the rename file
2:00:392 hours, 39 secondstool and rename file tool options. I'm going to update the name of the tool and the description of the tool as well.
2:00:482 hours, 48 secondsThen I'm going to update the parameters to match new name. Perfect.
2:00:542 hours, 54 secondsNow in here instead of extracting content we will extract new name and this can actually be the same. So we are
2:01:022 hours, 1 minute, 2 secondsvalidating if the file exists before running the step. Uh if it doesn't we throw an error. If the type is folder,
2:01:102 hours, 1 minute, 10 secondswell, in this case, no. We should allow read file, I mean rename file to rename
2:01:182 hours, 1 minute, 18 secondsfolders. That's perfectly fine. So, remove that check. And here, let's go ahead and make sure to call this
2:01:252 hours, 1 minute, 25 secondstoolstep run to be rename file. And we are simply calling rename file.
2:01:352 hours, 1 minute, 35 secondsAnd we are passing along new name.
2:01:382 hours, 1 minute, 38 secondsThat's it. And this will be Let's go ahead and give the agent as much information as possible. So this will be
2:01:472 hours, 1 minute, 47 secondsrenamed file name to new name like so.
2:01:542 hours, 1 minute, 54 secondsAnd in the error it will be error renaming file. Perfect. Let's go inside of
2:02:022 hours, 2 minutes, 2 secondsprocess message and let's add create rename file tool and pass in the internal key.
2:02:102 hours, 2 minutes, 10 secondsGreat. So what else do we have to do? We have to implement delete files tool. So
2:02:162 hours, 2 minutes, 16 secondsI think out of all of these the most similar one might be create files.
2:02:242 hours, 2 minutes, 24 secondsSo I'm going to copy it and rename it to delete files.
2:02:292 hours, 2 minutes, 29 secondsSo, let me go ahead and start with this interface delete files tool options.
2:02:362 hours, 2 minutes, 36 secondsLet's change the params to be file IDs. It's going to be an array of strings
2:02:452 hours, 2 minutes, 45 secondslike so. As always, I'm going to update the tool name and the props.
2:02:522 hours, 2 minutes, 52 secondsI'm going to go ahead and change the name of the tool to be delete files.
2:02:582 hours, 2 minutes, 58 secondsI'm going to go ahead and change the description. Delete files or folders from the project. If deleting a folder, all contents will be deleted recursively.
2:03:092 hours, 3 minutes, 9 secondsAnd then I'm going to repeat the parameters once more with the proper describe handlers.
2:03:162 hours, 3 minutes, 16 secondsThere we go.
2:03:182 hours, 3 minutes, 18 secondsNow, inside of handler, we parse as we usually do and we extract file ids from here.
2:03:262 hours, 3 minutes, 26 secondsSo now uh what I want to do is I want to validate if all files actually exist
2:03:322 hours, 3 minutes, 32 secondsbefore we run the step. So files to delete are going to be an arrays
2:03:412 hours, 3 minutes, 41 secondsand in each of that object inside of the array we expect an ID name and a type.
2:03:492 hours, 3 minutes, 49 secondsSo let's go ahead and very simply run a for loop.
2:03:532 hours, 3 minutes, 53 secondsSo for each file ID inside of the parsed file ids, I'm going to go ahead and attempt to fetch the file using convex
2:04:032 hours, 4 minutes, 3 secondsquery API system get file by ID. Pass in the internal key and pass in the file ID itself.
2:04:102 hours, 4 minutes, 10 secondsThen I'm going to go ahead and check if there is no file. Let's return an error.
2:04:162 hours, 4 minutes, 16 secondsFile with ID file ID not found. Use list files to get valid file IDs. So the agent doesn't attempt to delete files
2:04:252 hours, 4 minutes, 25 secondswhich don't even exist. Otherwise, let's go ahead and push them to the array.
2:04:302 hours, 4 minutes, 30 secondsFiles to delete. Push the ID of the file, the name, and the type of the file. There we go. Now we are ready to
2:04:372 hours, 4 minutes, 37 secondsopen try catch and call a tool. So the tool is going to be called delete files.
2:04:422 hours, 4 minutes, 42 secondsSo let's go ahead and change this. Let's go ahead and uh let's modify everything inside. I think it's easier this way.
2:04:532 hours, 4 minutes, 53 secondsSo inside of delete files, let's start with results, which is an array of strings. We're going to open another for loop iterating over our array files to delete, which we have confirmed exist.
2:05:052 hours, 5 minutes, 5 secondsWe're then going to go ahead and call convex mutation API system delete file for each of those files along with the internal key.
2:05:142 hours, 5 minutes, 14 secondsAnd then in the results, we're simply going to go ahead and push deleted file or folder and then the name of that file
2:05:222 hours, 5 minutes, 22 secondsor folder successfully. And then finally, what we're going to do is
2:05:272 hours, 5 minutes, 27 secondsreturn results.join. So the agent um the to the agent, we're just going to return
2:05:342 hours, 5 minutes, 34 secondsa plain string saying these are the files we have deleted. Error deleting files so the agent doesn't get confused.
2:05:432 hours, 5 minutes, 43 secondsAll right. Now let's go inside of process message.
2:05:462 hours, 5 minutes, 46 secondsLet's add create delete files tool and the internal key inside. Great. So I
2:05:572 hours, 5 minutes, 57 secondsbelieve there is one more tool to create and that is the ability to scrape URLs using file crawl. So I'm going to go
2:06:052 hours, 6 minutes, 5 secondsahead inside of tools here and this time I'm just going to create a new one from scratch. So scrape urls.ds.
2:06:132 hours, 6 minutes, 13 secondsDS.
2:06:152 hours, 6 minutes, 15 secondsLet's go ahead and import zod and create tool. Let's go ahead and import params schema which will basically just accept
2:06:232 hours, 6 minutes, 23 secondsan array of URLs. So array of URLs like so.
2:06:282 hours, 6 minutes, 28 secondsLet's go ahead and export create script URL tool. Let's return the actual create tool util.
2:06:382 hours, 6 minutes, 38 secondsI'm going to indent this back. Let's go ahead and give this a name of the tool to be scrape URLs.
2:06:462 hours, 6 minutes, 46 secondsAnd then I'm going to go ahead and write a description.
2:06:502 hours, 6 minutes, 50 secondsScrape content from URLs to get documentation or reference material. Use this when the user provides URLs or references external documentation.
2:07:002 hours, 7 minutesReturns markdown content from the script pages. Perfect.
2:07:062 hours, 7 minutes, 6 secondsNow, let's go ahead and actually add the parameters.
2:07:112 hours, 7 minutes, 11 secondsThere we go. And I believe the last thing we need is a handler. So we get rid of those errors. There we go. So
2:07:202 hours, 7 minutes, 20 secondsparameters are just an array of uh strings.
2:07:242 hours, 7 minutes, 24 secondsThere we go. Okay. So inside of the handler itself, as usual, we get the params and we destructure the step and we rename it or alias it to tool step.
2:07:352 hours, 7 minutes, 35 secondsWe do the usual parsing here. parse parse schema save parse we break if there's any error with parsing and now
2:07:442 hours, 7 minutes, 44 secondsfrom the parsed data we can extract the URLs let's go ahead and open try
2:07:522 hours, 7 minutes, 52 secondsand catch like so in the try method uh we're going
2:08:002 hours, 8 minutesto go ahead and open the actual tool called scrape URL URLs.
2:08:092 hours, 8 minutes, 9 secondsLet's go ahead and prepare the results.
2:08:112 hours, 8 minutes, 11 secondsSo, it's going to be an array of URLs and the content behind the URLs.
2:08:172 hours, 8 minutes, 17 secondsLet's go ahead and do four const URL of URLs. Open another try and catch
2:08:282 hours, 8 minutes, 28 secondsin this inner try. Let's go ahead and use result from await firecrol.scrape.
2:08:362 hours, 8 minutes, 36 secondsscrape pass in the URL and formats into markdown.
2:08:432 hours, 8 minutes, 43 secondsNow that we have the result, let's simply check if it's valid and then push it to the array. So if result domarkdown is received, simply push it and mark its content as result domarkdown.
2:08:552 hours, 8 minutes, 55 secondsIn the catch, we are going to push that we failed to do something. So if whatever error happens, just fail to scrape scrape that URL.
2:09:052 hours, 9 minutes, 5 secondsPerfect.
2:09:072 hours, 9 minutes, 7 secondsNow let's go ahead and do if results.length length is zero, no content could be scraped from the provided URLs
2:09:142 hours, 9 minutes, 14 secondsotherwise return JSON stringify results and then in the catch method here
2:09:242 hours, 9 minutes, 24 secondslet's simply return error scraping URLs if error is instance of error display the error message otherwise fall back to
2:09:322 hours, 9 minutes, 32 secondsunknown error string that's it let's go inside of process message And let's add the last tool which is create scrape URLs tool.
2:09:452 hours, 9 minutes, 45 secondsPerfect. So I believe our agent is quite capable at the moment. So if I go ahead for example and start a completely new
2:09:542 hours, 9 minutes, 54 secondsproject now. Let me go ahead and do that. And if I tell it to uh for example
2:10:012 hours, 10 minutes, 1 secondcreate a react plus v app and a simple to-do app inside.
2:10:112 hours, 10 minutes, 11 secondsI think it should be able to do that.
2:10:152 hours, 10 minutes, 15 secondsAgain uh AIs are non-deterministic. You can get as many successful results as you can get bad ones, right? But the
2:10:232 hours, 10 minutes, 23 secondsmore tools you give it, uh, the more descriptive you are, the better that these tools get and the more tokens and
2:10:302 hours, 10 minutes, 30 secondsthe higher budget you have, obviously the better results you are going to have. So, what we've developed right now
2:10:382 hours, 10 minutes, 38 secondsis a good harness, right? Uh, we and you can always improve this harness. I'm kind of limiting myself so we don't This
2:10:472 hours, 10 minutes, 47 secondstutorial can go on forever, right? I could be doing this for months, but I have to call it quits somewhere. So that's what I'm doing right now. If you
2:10:552 hours, 10 minutes, 55 secondswant to create more tools, if you see any, you know, gaps for optimization, go ahead, do it. And you can see how this
2:11:022 hours, 11 minutes, 2 secondsis happening right now, right? Our agent is just calling a bunch of tools. Create files, create folder. Here it is. You can see how it's creating all these
2:11:102 hours, 11 minutes, 10 secondsfiles in real time. Uh I suggest like opening these folders so you can actually uh see when the new files are
2:11:182 hours, 11 minutes, 18 secondscreated. So what I'm going to do now is I'm just going to pause and you know maybe it's going to be successful, maybe it's not. Sometimes it will be
2:11:262 hours, 11 minutes, 26 secondssuccessful the next time you do it. Uh and this things you see like 1 2 3 4 5 those are iterations. So, if you see
2:11:332 hours, 11 minutes, 33 secondsit's getting close to 20 or it often gets interrupted near 20, uh you might have to increase your amount.
2:11:412 hours, 11 minutes, 41 secondsAnd here we go. In my example, it was successful. Uh it's telling me how to install it, how to run it, and where to see it. Uh of course, we can't really do
2:11:502 hours, 11 minutes, 50 secondsthat right now, uh simply because we don't have the preview ready, but that's what the preview is going to be for.
2:11:562 hours, 11 minutes, 56 secondsIt's going to be able to actually install, run, and open the browser. But looking at the code, I see no reason why
2:12:032 hours, 12 minutes, 3 secondsthis shouldn't be working just fine. Uh so yeah, very very impressive clone of cursor already. I mean we are basically
2:12:122 hours, 12 minutes, 12 secondsfinished. We at this point we have finished majority of things that a very basic cursor clone would have. Uh cursor
2:12:192 hours, 12 minutes, 19 secondsfor example doesn't even have preview, doesn't even have export. So those are the things we're going to do next. We're going to do export. We're going to do preview. And I'm going to make sure that
2:12:282 hours, 12 minutes, 28 secondsthis markdown looks a bit better because right now the contrast behind this messages is kind of invisible and we've saw some markdowns where it just looks
2:12:362 hours, 12 minutes, 36 secondsbad. So that's going to be a super simple styling fix but I'm going to do that later. Amazing. So that marks the end of this chapter. Uh we implemented
2:12:442 hours, 12 minutes, 44 secondsproper message consolation which you can see now is very useful. Right? If I go ahead and start a new project now and if
2:12:522 hours, 12 minutes, 52 secondsI tell you know create a React plus V app u and a simple weather app and my
2:12:592 hours, 12 minutes, 59 secondsagent starts going wild you know it starts calling all of these tokens blah blah blah. Previously we'd have no way of stopping that. Now we can just press
2:13:082 hours, 13 minutes, 8 secondsstop. That's it. Request canceled. You can see that it's canceled. It's no longer spending any tokens. So that's why that cancellation was important for
2:13:162 hours, 13 minutes, 16 secondsus to develop initially. Perfect. So, let's go ahead and merge all of this.
2:13:202 hours, 13 minutes, 20 secondsSo, I'm going to shut down a bunch of my apps right here.
2:13:252 hours, 13 minutes, 25 secondsAnd let's see, chapter 13. So, this will be get well, we can check out first.
2:13:312 hours, 13 minutes, 31 secondsYeah, get checkout new branch 13 uh AI agent and tools. Get add dot get commit.
2:13:412 hours, 13 minutes, 41 secondsIt's going to be 13 AI agent and tools.
2:13:462 hours, 13 minutes, 46 secondsand then get push u origin 13 AI agent tools like so.
2:13:542 hours, 13 minutes, 54 secondsOnce this has been pushed, I'm going to go ahead and go inside of my uh
2:14:012 hours, 14 minutes, 1 secondrepository here. I'm going to open a new pull request and then I'm going to go ahead and review it.
2:14:112 hours, 14 minutes, 11 secondsAnd here we have the summary. New features. We added ability to cancel inprogress message processing. We added
2:14:192 hours, 14 minutes, 19 secondspast conversations history dialogue with searchable list. We introduced comprehensive file management tools.
2:14:252 hours, 14 minutes, 25 secondsCreate, update, delete, rename files and folders. We added URL content scraping
2:14:322 hours, 14 minutes, 32 secondscapability using file crawl and our scrape URLs tool. Implemented dynamic conversation title generation. with
2:14:402 hours, 14 minutes, 40 secondsenhanced message status tracking with processing, completion, and cancellation states.
2:14:462 hours, 14 minutes, 46 secondsAnd now we have eight comments, but they're nothing scary. Don't worry. So the first thing here is that we are
2:14:542 hours, 14 minutes, 54 secondsreturning an invalid uh request on the body. Here it says we are so okay
2:15:012 hours, 15 minutes, 1 secondrequest schema parse throws on validation failure and will surface as 500. Oh, so I should be using safe parse
2:15:102 hours, 15 minutes, 10 secondsinstead of parse. All right, I see. Yes, because technically this failing shouldn't be an internal server error
2:15:172 hours, 15 minutes, 17 seconds500. It should be just a userfacing error 400. User sends something incorrectly. All right. Yes. And now for
2:15:262 hours, 15 minutes, 26 secondsthe rest of the comments, it is simply telling me that I need to handle tool step to avoid returning undefined.
2:15:342 hours, 15 minutes, 34 secondsSo, I'm not exactly sure what it means here, but yeah, I think it's just the fact that when I in invoke toolstep.run,
2:15:442 hours, 15 minutes, 44 secondsI use a question mark here. Uh, I'm yet to see if this behavior is needed. I
2:15:502 hours, 15 minutes, 50 secondsthink from the agent kit, it's not. Uh, I will make sure to research uh the
2:15:572 hours, 15 minutes, 57 secondsdocumentation a bit more, but I do not think this is needed. I think it's fine like this. And all the other comments
2:16:052 hours, 16 minutes, 5 secondsare referring to the same tool step just so it doesn't cause a failure. But all of those are labeled as minor. So we did
2:16:132 hours, 16 minutes, 13 secondsa very very good job. Almost uh two almost 3,000 lines changed and 19 files
2:16:202 hours, 16 minutes, 20 secondschanged. Uh some of them are of course generated files and package locks and package JSON. But overall amazing
2:16:272 hours, 16 minutes, 27 secondsamazing job. Let's go ahead and merge this pull request.
2:16:322 hours, 16 minutes, 32 secondsAnd then let's go ahead uh and let's go back here. Get checkout main
2:16:412 hours, 16 minutes, 41 secondsand get uh pool origin main. I almost forgot how to write the command. There we go. And
2:16:492 hours, 16 minutes, 49 secondsnow we are officially up to date on our main branch here.
2:16:542 hours, 16 minutes, 54 secondsSo if I go ahead now in here in graph you can see that I have detached for 13
2:17:012 hours, 17 minutes, 1 secondAI agent and tools and then I have merged that pull request back inside. Uh so yes as I said I have these two
2:17:092 hours, 17 minutes, 9 secondscommits here which I just used to update the readme because I finished part one of this tutorial. You don't have these
2:17:162 hours, 17 minutes, 16 secondstwo commits that's perfectly fine. Your last commit should be 12 conversation system and we now finished 13 AI agent
2:17:242 hours, 17 minutes, 24 secondsand tools. So uh that marks the end of this chapter. We implemented message cancellation flow. We built conversation
2:17:332 hours, 17 minutes, 33 secondshistory dialogue. We configured AI agent with system prompt and we created a complete tool execution sim system.
2:17:412 hours, 17 minutes, 41 secondsAmazing amazing job and see you in the next chapter.
Chapter 3: 14 WebContainers Terminal Preview
2:17:462 hours, 17 minutes, 46 secondsIn this chapter, we're going to add preview to our project. We're going to be doing this using web containers and
2:17:542 hours, 17 minutes, 54 secondsterminal. In order to implement web containers, we have to configure them using a specific package and by setting up specific course settings. We're also
2:18:022 hours, 18 minutes, 2 secondsgoing to have to build a complete file tree mounting system because our database stores our files in one structure whereas web container expects
2:18:112 hours, 18 minutes, 11 secondsa whole different structure. We're going to implement the actual terminal using a package called Xterm.js.
2:18:182 hours, 18 minutes, 18 secondsAnd finally, we're going to create preview settings allowing the users to add custom commands on how to run their project. Let's get started by installing
2:18:272 hours, 18 minutes, 27 secondsthe dependencies we need. MPM install at webcontainer slappi.
2:18:342 hours, 18 minutes, 34 secondsThen the second package is xterm xterm.
2:18:382 hours, 18 minutes, 38 secondsAnd finally xterm sladdon fit. So make sure you have these three packages installed.
2:18:452 hours, 18 minutes, 45 secondsNext thing we're going to do is set up the foundation on which everything else will depend on. And we're going to start by configuring cross origin isolation
2:18:532 hours, 18 minutes, 53 secondsheaders. So how do I know that I have to do this? Well, very simply by following the web containers documentation.
2:19:022 hours, 19 minutes, 2 secondsIn here you can see that in order to configure the headers, I mean in order to make web containers work, we have to configure the headers, right? But they
2:19:092 hours, 19 minutes, 9 secondsgive us a couple of options. uh we can either use require corp or we can use credentials. Uh, I have not researched
2:19:162 hours, 19 minutes, 16 secondsthis too much, so I'm not really that familiar with course and all of the headers, but what I do know is that require Corp will actually cause
2:19:242 hours, 19 minutes, 24 secondsproblems with some other features that we have in our app, such as billing, which will come in later. Because of that, we're going to be using
2:19:322 hours, 19 minutes, 32 secondscredentialless. I just wanted to make that clear. So the only reason I'm choosing credentialless is because this
2:19:392 hours, 19 minutes, 39 secondsenables web containers to work within our project and it also doesn't break anything else in our app. So that's the only reason and I just don't want you to
2:19:472 hours, 19 minutes, 47 secondsthink that I'm pulling this information out of nowhere. Uh there actually is a reason why I'm choosing one over the other. So let's get started by going inside of next.config.ts.
2:19:582 hours, 19 minutes, 58 secondsOf course, just before that, I always love to show you my package JSON. So, you can see my packages. Web container API version 1.6.1,
2:20:072 hours, 20 minutes, 7 secondsXterm add-on fit 11.0, Xterm Xterm 6.0.0.
2:20:142 hours, 20 minutes, 14 secondsSo, let's go inside of next.config.ds.
2:20:172 hours, 20 minutes, 17 secondsSo far, we only have an empty next config and sentry configuration if you have set it up. If you didn't, then you
2:20:252 hours, 20 minutes, 25 secondsdon't have this. But what we need right now is this part right here. So in here we have to add specific headers.
2:20:322 hours, 20 minutes, 32 secondsBasically we have to add these two to our next config. Now the way you do that inside of next config is by using
2:20:402 hours, 20 minutes, 40 secondsasynchronous headers. Inside of here you have to return an array of objects. So let's go ahead
2:20:492 hours, 20 minutes, 49 secondsand return an array of objects. Let's go ahead and select the following source.
2:20:542 hours, 20 minutes, 54 secondsBasically every path in our project and then we have to add an array of headers.
2:21:022 hours, 21 minutes, 2 secondsThe headers will be objects basically defining these two inside. So the first
2:21:092 hours, 21 minutes, 9 secondsone will have a key of cross origin embed policy.
2:21:142 hours, 21 minutes, 14 secondsThen the second one will be the value which is credentialless.
2:21:192 hours, 21 minutes, 19 secondsAnd then we're going to go ahead and do the other one which is cross origin opener policy.
2:21:252 hours, 21 minutes, 25 secondsSo make sure you have that key and value same origin. So basically we have transferred the rule that we need right
2:21:332 hours, 21 minutes, 33 secondshere into proper next headers. To check if you've done it correctly, you can go ahead and npm rundev your app and you shouldn't see any errors in your app.
2:21:432 hours, 21 minutes, 43 secondsYou should just be able to run localhost 3000 normally with no errors. Great.
2:21:512 hours, 21 minutes, 51 secondsNow that we've got that ready, let's go ahead and update our convex schema. So, you know, we need to update our convex
2:21:582 hours, 21 minutes, 58 secondsschema because of this to create preview settings with custom commands to allow users to uh clearly define how to run
2:22:062 hours, 22 minutes, 6 secondstheir app because your app can be running on port 3000, 3005, 5000 depending if you're using create react
2:22:132 hours, 22 minutes, 13 secondsapp or vit or nux or nex.js JS or a bunch of other apps, right? So that's why we need to allow our users to
2:22:212 hours, 22 minutes, 21 secondsspecify themselves if the AI cannot figure out how to run the app itself. So I'm going to go ahead and find the
2:22:282 hours, 22 minutes, 28 secondsprojects table. Here it is. And after export repo URL, I'm going to extend it with another field called settings.
2:22:392 hours, 22 minutes, 39 secondsSo settings is going to be completely optional and it's going to be an object.
2:22:442 hours, 22 minutes, 44 secondsthe object will require I mean it won't require anything basically everything here is optional but you will be able to
2:22:512 hours, 22 minutes, 51 secondspass install command and dev command basically we're going to instruct the uh
2:22:592 hours, 22 minutes, 59 secondsweb container on how to install the packages in the project and we're going to instruct web container on how to run
2:23:072 hours, 23 minutes, 7 secondsthe developer script so we can actually see it. So now that we've added this, let's go ahead and save. And let's make
2:23:152 hours, 23 minutes, 15 secondssure that we have npx convex dev running. This will synchronize our new schema. And since this is a completely
2:23:222 hours, 23 minutes, 22 secondsoptional new field, uh we won't have to delete any of the previous projects.
2:23:272 hours, 23 minutes, 27 secondsGreat. Now let's go ahead and implement a mutation that will allow users to update the settings. So head inside of convex projects.ds.
2:23:372 hours, 23 minutes, 37 secondsAnd in here, I'm going to go ahead and I will prepare the update settings mutation. So, let me go ahead and close this.
2:23:452 hours, 23 minutes, 45 secondsThere we go. The update settings is a mutation which accepts ID and the actual settings object for the arguments. Just
2:23:542 hours, 23 minutes, 54 secondsmake sure that the install command and dev command aren't accidentally misspelled. They need to match exactly the settings object above. Great. Now,
2:24:032 hours, 24 minutes, 3 secondsfirst things first, let's go ahead and verify our identity. So, we've already done this a couple of times. So, we can
2:24:102 hours, 24 minutes, 10 secondsjust copy it from here like so. Now, uh once we have the identity, let's go ahead and get the
2:24:202 hours, 24 minutes, 20 secondsproject. We can get the project using arguments ID since the ID in the arguments is referring to the project.
2:24:292 hours, 24 minutes, 29 secondsIf we don't have a project, let's go ahead and throw an error. Project not found. And we also have to check if we
2:24:362 hours, 24 minutes, 36 secondsactually own this project. So if project owner ID is not identical to identity subject, we are not authorized to update
2:24:442 hours, 24 minutes, 44 secondsthis project. We shouldn't allow anyone else to change the developer and install script of this project. And finally,
2:24:512 hours, 24 minutes, 51 secondslet's patch the project table using the project ID and the new settings we have.
2:24:562 hours, 24 minutes, 56 secondsAnd let's also tweak the updated ad since it's just been renewed. Perfect.
2:25:022 hours, 25 minutes, 2 secondsThe next thing we have to do is we have to build the file tree utility. So that's referring to this part basically.
2:25:102 hours, 25 minutes, 10 secondsRight now let's take a look at how uh in our schema here it is. It's open. We
2:25:172 hours, 25 minutes, 17 secondsstore our files. So here they are right files. So when you when you load files
2:25:232 hours, 25 minutes, 23 secondsfor a project, you basically get an array of objects and each object has a
2:25:312 hours, 25 minutes, 31 secondsproject ID, parent ID, name, type, content, storage ID, an updated, right?
2:25:372 hours, 25 minutes, 37 secondsSo it's just a very flat array. This is how it looks like. Basically an array and then you have an id one two three
2:25:452 hours, 25 minutes, 45 secondstype is probably file name is fu.js JS and
2:25:532 hours, 25 minutes, 53 secondsthen inside you have uh what is it content which can be something like console log hello world
2:26:022 hours, 26 minutes, 2 secondsright and so on and so on with a bunch of objects and even folders aren't really
2:26:092 hours, 26 minutes, 9 secondsnested right you just have parent ID 1 2 3 so for example this file would be within this one makes no sense right now
2:26:172 hours, 26 minutes, 17 secondsbecause then this has to be a folder and it shouldn't have any content but I think you get the point. Basically, we have a very flat structure which works
2:26:252 hours, 26 minutes, 25 secondsfor us and for our file tree. That's why we've developed it this way. Uh but it's not exactly compatible uh with web
2:26:332 hours, 26 minutes, 33 secondscontainers, right? Because if you go ahead inside of the web containers documentation here, uh you will find that their file system expects this,
2:26:422 hours, 26 minutes, 42 secondsright? So they have a very different kind of structure here. You can see how they do folders, right? We basically
2:26:502 hours, 26 minutes, 50 secondshave to create a util which will convert our flat array structure into this. And
2:26:582 hours, 26 minutes, 58 secondsI'm going to show you how this function looks like. And honestly, I think it might be better if you just went to to my source code and copied this function.
2:27:062 hours, 27 minutes, 6 secondsAnd you will see why. Uh we're going to attempt to build it together, but it's very very complicated. I think you might it might be of you to just visit the
2:27:142 hours, 27 minutes, 14 secondssource code anyway simply because it's a very complex function. So, we're going to go ahead inside of features. And in here, I'm going to create a new folder called preview.
2:27:242 hours, 27 minutes, 24 secondsAnd inside of preview, I'm going to create a new folder called utils. And finally, inside file-tree.ts.
2:27:332 hours, 27 minutes, 33 secondsAnd the first thing I'm going to do is I'm going to import from my new web containers API the type that they expect, which is the file system tree.
2:27:472 hours, 27 minutes, 47 secondsAnd the reason we are importing this is because that's going to guide us into
2:27:542 hours, 27 minutes, 54 secondsconfirming uh that we've developed the proper function which matches this cast at the end. So let's import document and ID from convex generated data model.
2:28:062 hours, 28 minutes, 6 secondsLet's go ahead and define our file document by using document files. So now you can see exactly how our file looks
2:28:132 hours, 28 minutes, 13 secondslike and using this type safety what we're going to do now is very simply convert flat convex files into nested
2:28:222 hours, 28 minutes, 22 secondsfile system tree for web container. So we are now converting to this right here and it's basically just a very boring recursive function you're going to see.
2:28:332 hours, 28 minutes, 33 secondsSo let's export const build tree file and we accept files. Now those files are
2:28:422 hours, 28 minutes, 42 secondsa type of array of file document and what we expect to return from this function is the file system tree which we've imported above. That's the goal.
2:28:522 hours, 28 minutes, 52 secondsRight now we have an error because we are obviously not returning that. So we have to start by defining a tree which is an object with a type of file system
2:29:012 hours, 29 minutes, 1 secondtree. Then in order to remove any duplicates and for easier manipulation of these files, let's go ahead and put them inside of a map. So files map new
2:29:102 hours, 29 minutes, 10 secondsmap and inside for each file go ahead and return an array of file ID and then the rest of the file content.
2:29:182 hours, 29 minutes, 18 secondsNow the first thing we're going to develop is get path function.
2:29:232 hours, 29 minutes, 23 secondsSo get path function will accept a file which is a file dock type and it will return an array of strings. This will
2:29:302 hours, 29 minutes, 30 secondsallow us to traverse through their parent ID to get the full path of the project, right? So something like components,
2:29:392 hours, 29 minutes, 39 secondsI don't know, navbar icon.dsx, right? That's what we kind of plan on returning here. So we have to start by
2:29:482 hours, 29 minutes, 48 secondsgetting the file name. So initially the parts of the path will start with just the file name because that's the one
2:29:562 hours, 29 minutes, 56 secondsthing we know, right? For example, navbar.d the sx. This is what we know about every file. So that's the
2:30:032 hours, 30 minutes, 3 secondsbeginning of the array. And we also know the parent ID. So let's assign file.p parent ID here as well. And now we're
2:30:122 hours, 30 minutes, 12 secondssimply going to traverse up the path. So while parent ID is available, let's go ahead and get the parent using files
2:30:202 hours, 30 minutes, 20 secondsmap.get parent ID. So this is why putting them in a map is useful because we can very easily just uh get the exact
2:30:282 hours, 30 minutes, 28 secondsparent of the file whose path we are just trying to find. In case there is no parent, we can just break the method.
2:30:352 hours, 30 minutes, 35 secondsOtherwise, let's go ahead and unshift into our array parent.name and then let's assign the parent ID to
2:30:432 hours, 30 minutes, 43 secondsbe its parent. ID and finally return parts.
2:30:502 hours, 30 minutes, 50 secondsSo basically in the first iteration of this loop, we're going to go ahead and start with something like icon.tsx.
2:30:582 hours, 30 minutes, 58 secondsThen this icon.tsx file will have a parent. And then in the second iteration, we might have something like components/icon.tsx.
2:31:092 hours, 31 minutes, 9 secondsIf components has a parent, we might have something like source components icon. DSX. That's what we're doing right
2:31:162 hours, 31 minutes, 16 secondsnow. So we have so we are trying to generate a path similar like that. All right. Now what we have to do is for
2:31:252 hours, 31 minutes, 25 secondseach file of files which we have in the param that we've passed here we have to generate
2:31:342 hours, 31 minutes, 34 secondsthe path parts using our get path. So passing the file here
2:31:402 hours, 31 minutes, 40 secondsassign the current to be tree which we also have. Let me just find uh here.
2:31:462 hours, 31 minutes, 46 secondsRight. So this is the tree in this stage of iteration. So basically we're just going to be adding files to an object
2:31:542 hours, 31 minutes, 54 secondsuntil it looks like this. So let current is a tree. Let's go ahead and open a for loop within a for loop. Let iterator be
2:32:032 hours, 32 minutes, 3 secondszero. Iterator is smaller than path parts.length. And iterator is increasing.
2:32:122 hours, 32 minutes, 12 secondsAnd now in here we're going to go ahead and change the part to be whatever is the current iterator from path parts.
2:32:202 hours, 32 minutes, 20 secondsAnd we're also going to check if that part is last. So if iterator is equal to total amount of path parts
2:32:302 hours, 32 minutes, 30 secondsin case if it's last we also have to check if file.type is folder.
2:32:392 hours, 32 minutes, 39 secondsNow if it is we have to display that in this type of structure. Now, in order to
2:32:462 hours, 32 minutes, 46 secondsdo that, this is how we do it. In we're going to add to the current object for that specific part a very simple indicator of an empty directory like so.
2:32:582 hours, 32 minutes, 58 secondsElse if not file dot storage id
2:33:052 hours, 33 minutes, 5 secondsand file.content is not undefined.
2:33:112 hours, 33 minutes, 11 secondsSo else this is a case for last file and if it's a folder this is a case for text
2:33:182 hours, 33 minutes, 18 secondsfiles. We are purposely skipping storage ID or binary files because they just increase the complexity of this by 100.
2:33:262 hours, 33 minutes, 26 secondsWe might revisit this later but right now we're not even working with storage with binary files. So it's fine. So let's just go ahead and make sure that
2:33:342 hours, 33 minutes, 34 secondswe can add normal content here. So that would be again current part open an object file contents file.content
2:33:442 hours, 33 minutes, 44 secondsbecause usually for storage ID we would have to load the storage ID and then load base 64 content inside of it. So uh
2:33:532 hours, 33 minutes, 53 secondsreally a lot of complexity for something that we don't even have yet. Now that's the case for is last. If it's not last,
2:34:012 hours, 34 minutes, 1 secondwe're going to go ahead and do something else. So let's check if we don't already have that inside of our current tree. So
2:34:102 hours, 34 minutes, 10 secondsif we don't have that part, let's go ahead and simply add that part like so with an empty directory. And then let's
2:34:182 hours, 34 minutes, 18 secondsgo ahead and do const node current path. My apologies not path part.
2:34:272 hours, 34 minutes, 27 secondsIf there is directory in node current is node dot directory. It's very
2:34:362 hours, 34 minutes, 36 secondseasy to get lost in this function. It's really not a a simple one, right? But it is what we have to do. And make sure to
2:34:432 hours, 34 minutes, 43 secondsreturn the tree at the end. Okay. So you shouldn't have any errors here. You should now successfully accept flat
2:34:512 hours, 34 minutes, 51 secondsconvex files and it should return this my project directory fu.js file and then
2:34:582 hours, 34 minutes, 58 secondsthe contents inside or empty folder just directory. That's what we were doing right here, right? Uh feel free to open
2:35:052 hours, 35 minutes, 5 secondsthe source code for this. You know, this is super complicated. Even I used the AI assistance on this. I get very easily
2:35:122 hours, 35 minutes, 12 secondslost in in like these kind of recursive functions. Actually, I don't think this is recursive at all, but I think you get
2:35:192 hours, 35 minutes, 19 secondswhat I'm saying. Okay. Now, what we have to do is we have to create a simpler method which will help us get a full
2:35:272 hours, 35 minutes, 27 secondspath for a file by traversing the parent chain. very very similar to what we did here except this doesn't actually create
2:35:352 hours, 35 minutes, 35 secondsuh the full path. This just returns an array of strings. Right? So what this
2:35:422 hours, 35 minutes, 42 secondsdoes is it accepts an input. For example, let me show you. It accepts an object
2:35:512 hours, 35 minutes, 51 secondsID 1 2 3 content console log
2:35:572 hours, 35 minutes, 57 secondslike this. Name food.j JS and it also probably has a parent ID of
2:36:052 hours, 36 minutes, 5 seconds3 to1, right? And it returns uh an array of something like source
2:36:122 hours, 36 minutes, 12 secondscomponents food.js, right? That's what this get path function does. But what
2:36:192 hours, 36 minutes, 19 secondswe're going to develop now at the bottom is actual source components
2:36:262 hours, 36 minutes, 26 secondsfood.js JS in like a breadcrumb type of string.
2:36:312 hours, 36 minutes, 31 secondsSo nothing we haven't done already, right? So let's go ahead and define a function. It it will be called get file
2:36:382 hours, 36 minutes, 38 secondspath. And the function itself will accept two params. The actual file that we're trying to traverse through and the
2:36:462 hours, 36 minutes, 46 secondsfiles map. Basically a map of ID of files and file doc.
2:36:512 hours, 36 minutes, 51 secondsLet's go ahead and very simply define the parts starting with file name exactly as above. Let's go ahead and
2:36:582 hours, 36 minutes, 58 secondsdefine the parent ID to be file.parent ID. And again while the parent ID is
2:37:062 hours, 37 minutes, 6 secondsactive, let's go ahead and traverse up the chain by getting the current parent.
2:37:132 hours, 37 minutes, 13 secondsIf there is no parent, let's break. But if there is, let's go ahead and add it to the array
2:37:202 hours, 37 minutes, 20 secondsat the start of the array. That's what unshift does at the start of the array.
2:37:252 hours, 37 minutes, 25 secondsAnd let's assign the new parent ID to that file's parent ID. And the only difference we're going to do is instead
2:37:342 hours, 37 minutes, 34 secondsof returning parts like we did here is parts.jin. So why did I just duplicate the function again? uh well because
2:37:432 hours, 37 minutes, 43 secondswe're going to use this independently of this one. Basically, we are going to repeat this many times. It's a very
2:37:492 hours, 37 minutes, 49 secondsuseful uh function. All right. So, again, feel free to just open the source code if you think there's a bug here and
2:37:572 hours, 37 minutes, 57 secondsyou can just copy it and then uh it will work right away. But I kind of tried to explain what we're doing here.
2:38:032 hours, 38 minutes, 3 secondsBasically, we have our file structure and we need to convert it to this file structure. Great. Now let's go ahead and
2:38:102 hours, 38 minutes, 10 secondsimplement the web container hook. The web container hook is what will actually start the web container uh use these functions which we've just developed and
2:38:192 hours, 38 minutes, 19 secondsallow us to well see something right. Uh do we need a hook for that? Well, no.
2:38:252 hours, 38 minutes, 25 secondsBut since we are in React and XJS, we work with hooks and I kind of feel like this is a natural way of using web containers. So let's go inside of
2:38:342 hours, 38 minutes, 34 secondsfeatures preview. And in here I'm going to create hooks. And in here, let's add use- webcontainer.ts.
2:38:432 hours, 38 minutes, 43 secondsPerfect. Let's start with use client.
2:38:452 hours, 38 minutes, 45 secondsActually, no need to start with use client because we are only going to use this within a client. Instead, let's go ahead and start with all the imports.
2:38:552 hours, 38 minutes, 55 secondsSo, make sure you have use callback, use effect, use ref, and use state from react, use query from convex react, and web container from web container API.
2:39:052 hours, 39 minutes, 5 secondsNow let's go ahead and reference uh our build file tree and get file path features. And looks like I have forgotten to export one of these.
2:39:172 hours, 39 minutes, 17 secondsSo let me quickly go back here. Utils file tree. I'm exporting a build tree
2:39:242 hours, 39 minutes, 24 secondsfile and I wanted to name it build file tree. There we go. So that resolves uh the problem. Okay.
2:39:352 hours, 39 minutes, 35 secondsUh then let's also import the usual suspects API from generated API from convex and ID from generated data model.
2:39:472 hours, 39 minutes, 47 secondsWhat we're building now is a singleton web container instance. So we're going to need to have a let web container
2:39:552 hours, 39 minutes, 55 secondsinstance which is a type of web container or null and boot promise which is a promise of web container or null.
2:40:012 hours, 40 minutes, 1 secondRight now they can only be null. So this is throwing errors but later uh we will change it to have this other type so it
2:40:102 hours, 40 minutes, 10 secondswon't throw any errors anymore. We're going to start by defining a function called get web container.
2:40:182 hours, 40 minutes, 18 secondsThis will return a promise and web container inside like so. So first things first, if we
2:40:272 hours, 40 minutes, 27 secondsalready have a web container instance, we're going to return a web container instance. This way we don't have two instances.
2:40:352 hours, 40 minutes, 35 secondsThen if we have a boot promise, if we don't have boot promise, my apologies, we're going to start a new boot promise using webcontainer.boot.
2:40:432 hours, 40 minutes, 43 secondsAnd what this is referring to is our cross origin policy. And if you remember, we've set it to credentialless. So instead of
2:40:512 hours, 40 minutes, 51 secondsnext.config.ds, we've set the value to be credentialless. And basically because of the instructions here in the
2:40:582 hours, 40 minutes, 58 secondsdocumentation, let me go ahead and show you. uh configuring headers. If you switch to credentialless, you also have
2:41:052 hours, 41 minutes, 5 secondsto boot your web container specifying uh this key right here to be credentialless. So that's where I got
2:41:122 hours, 41 minutes, 12 secondsthat from. All right. And if you're wondering about exact documentation for this, uh it's also here, but it will not
2:41:192 hours, 41 minutes, 19 secondsexactly uh you know, show you how to do it like I'm doing it. you can, you know, see how to create a web container
2:41:262 hours, 41 minutes, 26 secondsinstance using webcontainer boot. But this is more like an overall guide on how you would quick start it. Uh what
2:41:332 hours, 41 minutes, 33 secondswe're doing is basically a compilation of a bunch of this uh references and ways of booting it into a hook, right?
2:41:432 hours, 41 minutes, 43 secondsThat's kind of the complicated part, but feel free to look through quick start so you can actually uh see some of these functions that I will be calling here.
2:41:522 hours, 41 minutes, 52 secondsAll right.
2:41:542 hours, 41 minutes, 54 secondsSo, so far we are making sure that we are not able to boot the web container instance twice. That's why we're checking if there is no boot promise
2:42:022 hours, 42 minutes, 2 secondsonly then assign a web container boot with credentialless um headers.
2:42:092 hours, 42 minutes, 9 secondsThen let's go ahead and set the web container instance to be await boot promise. And finally return web container instance. And just like that,
2:42:182 hours, 42 minutes, 18 secondswe've resolved those two errors right here because now in the runtime, we actually assign them to their types.
2:42:242 hours, 42 minutes, 24 secondsGreat. So that's it for get web container.
2:42:272 hours, 42 minutes, 27 secondsNow what we have to do is develop a very simple method to tear down the web container so we don't have any memory leaks. So we're going to tear down the
2:42:362 hours, 42 minutes, 36 secondsweb container if we have the web container instance. So if the web container instance already exists, let's
2:42:432 hours, 42 minutes, 43 secondsdo webcontainer instance. tear down and let's do web container instance and assign it back to null. Let me just fix
2:42:522 hours, 42 minutes, 52 secondsthe indentation here and outside of the if clause set the boot promise to be null. There we go. So
2:43:002 hours, 43 minutesnow we have tear down web container and get web container functions ready.
2:43:052 hours, 43 minutes, 5 secondsWhat we have to do now is we have to develop an interface for our hook. So our interface use web container props
2:43:122 hours, 43 minutes, 12 secondswill accept project ID which is a type of ID complex projects enabled which is a boolean and optional settings which we
2:43:192 hours, 43 minutes, 19 secondsdefine in our database. Remember install command and dev command. If you're unsure, you can always open your schema.ts file and go inside of your projects table and find the settings.
2:43:312 hours, 43 minutes, 31 secondsMake sure you have install command and dev command and don't mistype them here.
2:43:352 hours, 43 minutes, 35 secondsGreat. Now we have the interface for our hook which means we are ready to start building the actual hook.
2:43:432 hours, 43 minutes, 43 secondsSo use web container hook uses the same named props here accepts project ID enabled and settings. The first thing
2:43:522 hours, 43 minutes, 52 secondswe're going to do is we're going to set the status of this web container. So status set status from use state. It can
2:44:002 hours, 44 minuteseither be idle, booting, installing, running or error. And by default, it's going to be idle.
2:44:082 hours, 44 minutes, 8 secondsAnd while we are here, let's also define all other states which we're going to need. Starting with the preview URL, which can be a string or null. And by
2:44:162 hours, 44 minutes, 16 secondsdefault, it's going to be null. Then let's go ahead and add the error, which can again be string or null. The restart
2:44:252 hours, 44 minutes, 25 secondskey will very simply be used to change the key of an element. Changing the key of an element in React makes it rerender
2:44:322 hours, 44 minutes, 32 secondsentirely. So we're going to use this as kind of a hack to refresh the web container. So in case it gets stuck or
2:44:402 hours, 44 minutes, 40 secondsit boots incorrectly, the user can always uh forcefully restart it. So it installs the dependencies again.
2:44:482 hours, 44 minutes, 48 secondsThen let's go ahead and also prepare the state for the terminal output which can be a string and well when you define the
2:44:552 hours, 44 minutes, 55 secondsdefault type and it can only be that type you don't have to uh define it the same way we didn't have to define number
2:45:022 hours, 45 minutes, 2 secondshere right only when it can be multiple types does it make sense to define it like string and null. Great. Now let's
2:45:102 hours, 45 minutes, 10 secondsgo ahead and prepare some references here. So we're going to need two references. the container ref which is
2:45:172 hours, 45 minutes, 17 secondsuse ref and it can be either web container type or null and by default it's going to be null and has started
2:45:252 hours, 45 minutes, 25 secondsref which we are very simply going to be used to prevent some duplication so by default this one will be false great
2:45:342 hours, 45 minutes, 34 secondswhat we have to do now is we have to fetch files from convex and this is where convex real time actually comes in so handy
2:45:432 hours, 45 minutes, 43 secondsconvex auto updates on any changes which means we accidentally developed hot
2:45:492 hours, 45 minutes, 49 secondsreload just by using convex. So if I want to get my files, all I have to do
2:45:562 hours, 45 minutes, 56 secondsis call usequery from convex and call api.files
2:46:032 hours, 46 minutes, 3 secondsget files and pass in the project ID from the files which I need or let me
2:46:102 hours, 46 minutes, 10 secondscheck even further. Maybe I even have a hook for that instead of use conversation use file. Actually this
2:46:172 hours, 46 minutes, 17 secondswill be in the projects I believe. Hooks use files. Do I have that?
2:46:252 hours, 46 minutes, 25 secondsLooks like I don't have use files. So, let's go ahead and quickly create use files here.
2:46:332 hours, 46 minutes, 33 secondsUse files. And all it accepts is a project ID.
2:46:392 hours, 46 minutes, 39 secondsAnd I'm not sure if it should be able to be skipped. So, this will be an ID of projects.
2:46:492 hours, 46 minutes, 49 secondsget files either pass in the project ID or skip it. So
2:46:592 hours, 46 minutes, 59 secondsjust like that we've developed an abstraction use files. So now in here I can just call use files and pass in the project ID.
2:47:122 hours, 47 minutes, 12 secondsThere we go. Use files from features projects hooks use files. and I'm going to move it here and I'm going to remove the import of use query from convex react. I think this will work just fine.
2:47:222 hours, 47 minutes, 22 secondsWe're going to see later if it doesn't by chance. So what we ought to do now is boot the actual web container. So
2:47:312 hours, 47 minutes, 31 secondsinitial boot and mount using a use effect.
2:47:362 hours, 47 minutes, 36 secondsLet's prepare an empty use effect like so. And now in here we're first going to check if we should prevent this from
2:47:442 hours, 47 minutes, 44 secondshappening. So if we are not enabling this or if there are no files or if
2:47:502 hours, 47 minutes, 50 secondsfiles.length is zero and remove the exclamation point here or if has started
2:48:002 hours, 48 minutesref.tc current is true. If any of that happens we have to return early and not
2:48:082 hours, 48 minutes, 8 secondsdo anything. It either means we didn't enable it, there are no files to load, or we have already started and this is
2:48:162 hours, 48 minutes, 16 secondsan accidental reboot. So, we're immediately going to change this to true then. So, now it makes sense if this happens twice, this will prevent that
2:48:242 hours, 48 minutes, 24 secondsfrom happening. Now, let's go ahead and develop the actual start method, which is going to be an asynchronous function.
2:48:322 hours, 48 minutes, 32 secondsLet's go ahead and open a very simple try and catch block here.
2:48:372 hours, 48 minutes, 37 secondsInstead of try, let's go ahead and set the status to be booting.
2:48:442 hours, 48 minutes, 44 secondsThen set the error to null.
2:48:482 hours, 48 minutes, 48 secondsThen set terminal output to be an empty string. This is kind of like a reset.
2:48:552 hours, 48 minutes, 55 secondsAnd now we have to create a function to append the output to terminal. So append output accepts data which is a string.
2:49:032 hours, 49 minutes, 3 secondsand it returns set terminal output and it will simply append the data to the current value of the state like so. Then
2:49:122 hours, 49 minutes, 12 secondslet's go ahead and actually get the web container and assign it to a ref. So container is await get web container a
2:49:202 hours, 49 minutes, 20 secondsfunction we've developed first here and then we simply assign that to a reference.
2:49:262 hours, 49 minutes, 26 secondsThen we have to build the file tree so we can actually mount the files to a web container. So file tree build file tree
2:49:342 hours, 49 minutes, 34 secondsfiles and let's go ahead and mount that using await container.mmount file tree.
2:49:412 hours, 49 minutes, 41 secondsYou can see that if we didn't build the build file tree function these files from convex which we load here would be
2:49:492 hours, 49 minutes, 49 secondscompletely incompatible. Right? You can see it's an inal incorrect structure.
2:49:542 hours, 49 minutes, 54 secondsThat's why we have to build the file tree first.
2:49:582 hours, 49 minutes, 58 secondsThen let's go ahead and uh look for an event called container on server- ready. Skip the port, only focus
2:50:072 hours, 50 minutes, 7 secondson the URL and set the preview URL to that URL we've received from an event server ready and change the status of this hook to running.
2:50:182 hours, 50 minutes, 18 secondsAt this moment, we can also set the status outside of this event, right, to installing because this will change.
2:50:262 hours, 50 minutes, 26 secondsThis won't go before this one. Only once we receive server ready will it change to running. So ignore the fact that we are defining this before we define this.
2:50:362 hours, 50 minutes, 36 secondsOkay. After we set this to installing, we actually have to parse the install command which by default is going to be npm install.
2:50:462 hours, 50 minutes, 46 secondsSo how do we define the install command?
2:50:492 hours, 50 minutes, 49 secondsWell, very simply, we can use the settings, right? Let me go ahead and find where we define the settings. Just a second. So, we pass the settings, right?
2:50:592 hours, 50 minutes, 59 secondsWe could technically also fetch the settings. That might also work, but then we'd also have to restart the project uh
2:51:072 hours, 51 minutes, 7 secondscarefully. So, I'm going to use it as a prop for now. So, it's going to be
2:51:132 hours, 51 minutes, 13 secondssettings dotinstall command or npm install
2:51:192 hours, 51 minutes, 19 secondslike so. And then go ahead and use install command.split. split
2:51:262 hours, 51 minutes, 26 secondssplit it basically by space because the way web containers accept install commands are
2:51:362 hours, 51 minutes, 36 secondsuh in a very specific way. So what we have to do is uh basically separate this array install and then the rest of the
2:51:442 hours, 51 minutes, 44 secondsinstall arguments like so. So we are basically going to
2:51:502 hours, 51 minutes, 50 secondshave an array mpm and install or npm run install whatever the user specifies.
2:52:002 hours, 52 minutesAnd then let's go ahead and append output to a terminal. So the terminal shows the user exactly what we're doing right now. So the append output will have install command and a line break.
2:52:122 hours, 52 minutes, 12 secondsAnd now we actually have to spawn this command. So all of this right now is just cosmetics. And now we are
2:52:192 hours, 52 minutes, 19 secondsinitializing install process with await container.spawn and passing the install bin command followed by the rest of the arguments inside of the command. Great.
2:52:302 hours, 52 minutes, 30 secondsNow let's go ahead and create a writable stream from the install process.
2:52:372 hours, 52 minutes, 37 secondsSo install process.output.pipe Pipe two. Execute that and call new writable stream.
2:52:472 hours, 52 minutes, 47 secondsOpen an object inside.
2:52:512 hours, 52 minutes, 51 secondsDefine the write function which has data as a prop and very simply use the append output and pass in the data here like
2:53:002 hours, 53 minutesso. And it's not write stream, it's writable stream.
2:53:062 hours, 53 minutes, 6 secondsHow do you uh write this? Write write double stream. There we go. So I believe that I have might have imported write
2:53:152 hours, 53 minutes, 15 secondsstream from fs. So if you have done that you can remove it. Okay. So it's writable stream. Okay.
2:53:252 hours, 53 minutes, 25 secondsAnd this will basically display the entire output of the install process into the terminal.
2:53:312 hours, 53 minutes, 31 secondsNow let's go ahead and also catch the install exit code using await install process.exit.
2:53:412 hours, 53 minutes, 41 secondsIf install exit code is not zero, it probably means there is an error. So
2:53:492 hours, 53 minutes, 49 secondslet's go ahead and throw an error. Throw new error. And inside we can just add a template literal showing the command we
2:53:582 hours, 53 minutes, 58 secondsattempted to run failed with code. and then show the code which was thrown because the exit code can be zero which
2:54:062 hours, 54 minutes, 6 secondsbasically means okay I've successfully finished mpm install or it can be something else so we just show that back to the user great
2:54:152 hours, 54 minutes, 15 secondswhat we have to do now is we have to parse the developer command the developer command is basically npm
2:54:242 hours, 54 minutes, 24 secondsrundev something to start the project and we're going to go ahead and use the same logic right so developer command is parsed through settings.dev command.
2:54:322 hours, 54 minutes, 32 secondsKeep in mind that both settings and dev command can be optional. So we have to add a fallback npm rundev. So we're going to assume most of the projects
2:54:392 hours, 54 minutes, 39 secondswill be run with npm install and mpm rundev. But of course users will be able to define their own. And then we also
2:54:462 hours, 54 minutes, 46 secondshave to split the dev bin and the dev arguments using dotsplit with an empty space.
2:54:532 hours, 54 minutes, 53 secondsLet's go ahead and immediately append output to the terminal with a new line brace and the developer command.
2:55:002 hours, 55 minutesLet's go ahead and initialize the actual def process by spawning this. So developer process await container.spawn
2:55:072 hours, 55 minutes, 7 secondsdeveloper bin and the rest of the developer arguments.
2:55:112 hours, 55 minutes, 11 secondsAnd now we just have to do another writable stream here. So developer process.output pipe to new writable
2:55:182 hours, 55 minutes, 18 secondsstream call the write function which accepts the data and simply appends the output to the terminal of that data. So everything that's happening during the
2:55:252 hours, 55 minutes, 25 secondsspawning of this command will be uh shown to the user in their terminal simulating the exact experience you would in a real terminal. All right.
2:55:352 hours, 55 minutes, 35 secondsAnd in the catch method here, let's go ahead and do catch error set error if
2:55:432 hours, 55 minutes, 43 secondserror is instance of error. Do error dot message otherwise unknown error
2:55:522 hours, 55 minutes, 52 secondslike so. and set the status of the entire hook to error. So for example when we throw from the install code that
2:56:002 hours, 56 minuteswill be called right here and set the status to error. Perfect.
2:56:052 hours, 56 minutes, 5 secondsAnd now execute the start method like so. So we've just defined the entire start method, right? But we never called it. So make sure that at the end you
2:56:142 hours, 56 minutes, 14 secondsactually call it. And now for the dependency array there are a couple of those we have to add. So let's add
2:56:212 hours, 56 minutes, 21 secondsenabled. Let's add files. Let's add restart key. Let's add settings.
2:56:292 hours, 56 minutes, 29 secondsQuestion mark.install command. Well, dev command, install command. Both of them are needed basically. Great. Now let's
2:56:382 hours, 56 minutes, 38 secondsgo ahead and implement a simple hook to enhance the hot reload of the files. So sync files file changes hot reload.
2:56:492 hours, 56 minutes, 49 secondsThis will be another use effect though much simpler. So let's open an empty use effect once again.
2:56:582 hours, 56 minutes, 58 secondsLet's go ahead and check if we have the container from our ref. If there is no container or if the status is incorrect
2:57:072 hours, 57 minutes, 7 secondsor if there are no files. Basically if any of these cases happen, let's do an early return. What we ought to do then
2:57:142 hours, 57 minutes, 14 secondsis create a simple file map. So file map new map files.m map get the individual file and add them in an array showing
2:57:242 hours, 57 minutes, 24 secondsthe file ID and the file content as the other part in the array. Great. Now
2:57:302 hours, 57 minutes, 30 secondslet's go ahead and open a simple for const file of files. Let's go ahead and check if the file is an actual type of
2:57:392 hours, 57 minutes, 39 secondsfile and it has content and it's not a binary file. We can do that by adding an if clause. If file.t type is not a file
2:57:472 hours, 57 minutes, 47 secondsor if file has a storage ID or if file has no content at all just continue no need to do anything. But if the file is
2:57:562 hours, 57 minutes, 56 secondsan actual file which has text content let's go ahead and define the file path using get file path util pass in the
2:58:042 hours, 58 minutes, 4 secondsfile and the file is mapped and then we can go ahead and write that file to the container container. FS write file file
2:58:132 hours, 58 minutes, 13 secondspath file.content content in the dependency array. Add files and status.
2:58:202 hours, 58 minutes, 20 secondsThere we go. Let's go ahead and reset the entire thing if we receive a
2:58:272 hours, 58 minutes, 27 secondsdisabled event. So, this is a much simpler use effect. Here it is. So, if we reset the enabled prop, so if not
2:58:362 hours, 58 minutes, 36 secondsenabled, immediately change has started ref.curren to false. Set the status to idle. set preview URL to null and set
2:58:442 hours, 58 minutes, 44 secondserror to null. Basically, a complete reset.
2:58:482 hours, 58 minutes, 48 secondsAnd then let's go ahead and just implement a function to restart the entire web container process. So we're
2:58:552 hours, 58 minutes, 55 secondsjust doing some tearowns now, right? So restart is going to be a use callback
2:59:032 hours, 59 minutes, 3 secondsand the first thing it's going to do is going to call a function tear down web container. After that it will set the
2:59:112 hours, 59 minutes, 11 secondscontainer ref.curren to null. It will start it will reset has started ref.curren to false. It will set the
2:59:202 hours, 59 minutes, 20 secondsstatus to idle. Set the preview URL to null. Set the error to null. And
2:59:282 hours, 59 minutes, 28 secondsfinally, we're going to forcefully increase the key, which will again just reset everything even more. All right.
2:59:392 hours, 59 minutes, 39 secondsAnd finally, let's return status, preview, URL, error, restart, and
2:59:472 hours, 59 minutes, 47 secondsterminal output. That's it. That's our complete hook. We are now ready to develop the actual terminal component.
2:59:582 hours, 59 minutes, 58 secondsOur ne next task, our next task uh is to implement the terminal component. Uh fun
3:00:063 hours, 6 secondsfact, the library which we're using, XtermJS, is actually used in real VS Code and various other projects. So
3:00:153 hours, 15 secondslet's go ahead and see how we can implement a terminal component using the package we installed XERMJS. So I'm
3:00:223 hours, 22 secondsgoing to go inside of features preview and I'm going to go inside of uh let me see I have to create a new
3:00:313 hours, 31 secondsfolder called components and I will create preview- terminal dsx.
3:00:403 hours, 40 secondsI'm going to start by marking it as use client. And then I'm going to import use effect and use ref from react followed
3:00:483 hours, 48 secondsby extern basically the terminal and fit add-on package. The fit add-on package will be
3:00:563 hours, 56 secondsused because the terminal will be within an allotment pane which can be resized. So because of that we need that package.
3:01:033 hours, 1 minute, 3 secondsOtherwise you can develop it without this package. And we also need to import the CSS for the Xterm. Let's start by
3:01:123 hours, 1 minute, 12 secondscreating an interface preview terminal props which very simply accepts the output. So in order to actually develop
3:01:203 hours, 1 minute, 20 secondsthe component, we need to export preview terminal and define the output here. All right.
3:01:293 hours, 1 minute, 29 secondsNow inside of the preview terminal, let's add a few refs. We're going to have a container ref, which can be HTML
3:01:383 hours, 1 minute, 38 secondsdev element or null. We're going to add terminal ref, fit add-on ref, and last
3:01:453 hours, 1 minute, 45 secondslength ref. All of this. Then let's go ahead and create a use effect, which will initialize the terminal. So, I'm
3:01:543 hours, 1 minute, 54 secondsgoing to go ahead and open an empty use effect like we usually do.
3:02:003 hours, 2 minutesAnd I will first check if we are ready to run the terminal. So if there is no container ref or if there is no terminal ref, let's do an early return.
3:02:123 hours, 2 minutes, 12 secondsOtherwise, let's go ahead and initialize a new terminal. Now inside of these options here, you can add a few settings. Now I will configure it the
3:02:213 hours, 2 minutes, 21 secondsway I prefer it and the way I found it looks the best for our project. You can of course tweak this later on. So I'm
3:02:283 hours, 2 minutes, 28 secondsgoing to enable this setting. I'm going to enable this setting. I will set the font size to 12. And lastly, I'm going
3:02:373 hours, 2 minutes, 37 secondsto add font family and a background color. So font family will be monospace.
3:02:423 hours, 2 minutes, 42 secondsAnd the theme will use this specific background.
3:02:473 hours, 2 minutes, 47 secondsNow outside of this terminal constant, let's go ahead and define a new fit add-on plugin. So this fit add-on plugin
3:02:573 hours, 2 minutes, 57 secondswill very simply be loaded into a terminal using their built-in load add-on function. And after that we are
3:03:053 hours, 3 minutes, 5 secondsready to open the terminal in the container which we store in ref. And then let's simply go ahead and add both
3:03:143 hours, 3 minutes, 14 secondsof those fit add-on and terminal to their refs. So terminal ref.curren gets the terminal and fit add-on.ref ref gets
3:03:233 hours, 3 minutes, 23 secondsfit addon we have to write existing output the moment we mount the terminal
3:03:323 hours, 3 minutes, 32 secondsso if there is any output use terminal write and pass in the
3:03:403 hours, 3 minutes, 40 secondsoutput and also change the last length refc current to be outputlength
3:03:473 hours, 3 minutes, 47 secondsthen we're going to add a request animation frame name function call back
3:03:533 hours, 3 minutes, 53 secondsand call fit add-on.fit every time a new animation frame is rendered. This way we can have a
3:04:013 hours, 4 minutes, 1 secondterminal which expands within our resizable panels. Let's also add a resizable observer.
3:04:093 hours, 4 minutes, 9 secondsSo resize observer calls new resize observer and also calls fit add-on.fit.
3:04:153 hours, 4 minutes, 15 secondsAnd we actually have to observe something. So let's observe the container ref.curren current using the resize observer.observe
3:04:233 hours, 4 minutes, 23 secondsfunction. The last thing we ought to do is a cleanup function in this hook. So in the cleanup function, we're going to
3:04:313 hours, 4 minutes, 31 secondsdisconnect the resize observer. We're going to dispose of the terminal and we're going to reset our refs.
3:04:393 hours, 4 minutes, 39 secondsThen let's go ahead and add the output into the dependency array right here.
3:04:503 hours, 4 minutes, 50 secondsUh uh let me just see do we actually need uh well yes this is output is only
3:04:573 hours, 4 minutes, 57 secondsused uh to write existing output. It's not used to be updated. So do not add it
3:05:053 hours, 5 minutes, 5 secondshere. I'm going to add a little comment here. uh output does not need to be a
3:05:113 hours, 5 minutes, 11 secondsdependency since it is not intended
3:05:173 hours, 5 minutes, 17 secondsto update anything just used on mount intended. All right,
3:05:253 hours, 5 minutes, 25 secondsthen let's go ahead and create another use effect which will be used to write the received output. So this is where we
3:05:333 hours, 5 minutes, 33 secondswill use the output in the dependency array. So let's go ahead and define
3:05:413 hours, 5 minutes, 41 secondsthis pass in the output in here because now we will need the output. So again we're going to check uh if we have no
3:05:503 hours, 5 minutes, 50 secondsterminal ref.curren or if the output.length is smaller than last length ref.curren.
3:05:593 hours, 5 minutes, 59 secondsSo if output.length is smaller than last length ref.curren, current. Let's simply clear the terminal and reset this ref we
3:06:083 hours, 6 minutes, 8 secondsare tracking back to zero. Uh I found that this helps with the resizable issue because there was some issues. I was
3:06:163 hours, 6 minutes, 16 secondskind of fighting the terminal to work within resizable panels. So this is one solution that I found helps to clear up some of the content.
3:06:273 hours, 6 minutes, 27 secondsThen let's go ahead and define new data to be output. slice last length ref.curren.
3:06:353 hours, 6 minutes, 35 secondsAnd if we have new data, let's go ahead and write it to the terminal. We can access the terminal instance using our
3:06:423 hours, 6 minutes, 42 secondsref. So if we have new data, call terminal ref.curren.right and pass in the new data and update the last length ref.curren to be output.length.
3:06:523 hours, 6 minutes, 52 secondsThere we go. One more thing we have to do is a very simple return method. It will return a one single div, a self-closing div.
3:07:033 hours, 7 minutes, 3 secondsAnd this div will have a reference of container ref. And then it will have a class name flex one, minimum height of
3:07:113 hours, 7 minutes, 11 secondszero, padding three. And now we're going to have some very specific uh styles for the terminal. So we're going to be using
3:07:203 hours, 7 minutes, 20 secondsthis a lot. So feel free to you know copy that. And the classes I'm adding
3:07:273 hours, 7 minutes, 27 secondsnow is basically just very specific styling of the terminal. So this is one class. Never mind that it's collapsed.
3:07:353 hours, 7 minutes, 35 secondsSee besides height full we're also going to have Xterm
3:07:433 hours, 7 minutes, 43 secondsscreen to be height full and background color will be sidebar. There we go.
3:07:513 hours, 7 minutes, 51 secondsThat is our preview terminal component.
3:07:543 hours, 7 minutes, 54 secondsGreat. Now that we have that, let's go ahead and implement the settings popover component, which will allow us to change the install script and the dev command.
3:08:073 hours, 8 minutes, 7 secondsSo, I'm going to go ahead back inside of features preview components. And in
3:08:133 hours, 8 minutes, 13 secondshere, I'm going to add preview- settings popover.tsx.
3:08:223 hours, 8 minutes, 22 secondsThis will mostly be a form. So, let's go ahead and mark it as use client, import zod, and let's import everything else
3:08:313 hours, 8 minutes, 31 secondswe're going to need, which is going to be use state, uh, use mutation, use form, settings icon. Uh, looks like we
3:08:403 hours, 8 minutes, 40 secondsdon't have tan stack react form. So did we not build any forms before?
3:08:473 hours, 8 minutes, 47 secondsUh we do have form itself but we don't have this. Basically uh chaten added a
3:08:543 hours, 8 minutes, 54 secondsnew way uh to write forms. So you can now write forms uh either in the old
3:09:033 hours, 9 minutes, 3 secondsway. Let me find form. Where is it? I cannot find form. Maybe I should search for form.
3:09:123 hours, 9 minutes, 12 secondsOops. Looks like something's not working on the website.
3:09:183 hours, 9 minutes, 18 secondsAll right. So, if you scroll down and find forms, you will find react hook form, which is I believe how we've built
3:09:263 hours, 9 minutes, 26 secondsforms so far or no, this is the new one. Okay. So they now have basically either you can
3:09:353 hours, 9 minutes, 35 secondsuse react hook form or tanstack form and tanstack form is the new one. So I think
3:09:423 hours, 9 minutes, 42 secondsit might be better to you know teach you how to use this one simply because I don't know I mean I've built the react
3:09:503 hours, 9 minutes, 50 secondshook form many times but I didn't build this one uh too much. Uh, so I just want to find a way to install this because I
3:10:003 hours, 10 minutescan see that I have a missing tanstack react form. And I will save this file anyway. And I'm just going to go ahead
3:10:093 hours, 10 minutes, 9 secondsand research a bit inside of my source components UI.
3:10:143 hours, 10 minutes, 14 secondsDo I have something called the field? I do have. So I think I should be able to,
3:10:223 hours, 10 minutes, 22 secondsyou know, run this normally. I'm just surprised that shhatsen command didn't install
3:10:313 hours, 10 minutes, 31 secondstanstack react form. So I'm going to check in my package json to confirm. And we truly don't have tanstack react form.
3:10:423 hours, 10 minutes, 42 secondsSo what I'm going to do is I'm just going to install it. I think that's the only package we need. So, mpm install at
3:10:503 hours, 10 minutes, 50 secondstanstack/react form. Usually, these kinds of things get installed by running this command, but
3:10:583 hours, 10 minutes, 58 secondslooks like it's somehow missed now. So, let me see if I have it now. Here it is.
3:11:043 hours, 11 minutes, 4 secondsAnd I'm using 1.27.7 version. All right. So, back to business. Tanstack uh React form.
3:11:153 hours, 11 minutes, 15 secondsBesides these imports, we're also going to need a button component. We're going to need all the imports from the popover
3:11:243 hours, 11 minutes, 24 secondscomponent, which is popover, popover content, and popover trigger. We're going to need to import all the field
3:11:323 hours, 11 minutes, 32 secondscomponents, field, field label, and field description from components UI field. And we're going to need to import the input from components UI input.
3:11:433 hours, 11 minutes, 43 secondsLet's go ahead and import API and let's go ahead and import document and ID from generated data model. I'm going to start
3:11:523 hours, 11 minutes, 52 secondsby defining the form schema which is an object which accepts install command and dev command. We've already seen this a few times.
3:12:023 hours, 12 minutes, 2 secondsThen let's create an interface preview settings popover props which accepts the project ID for the settings initial values if we already have some settings and an onsave method.
3:12:143 hours, 12 minutes, 14 secondsThen let's go ahead and actually define and export a component.
3:12:193 hours, 12 minutes, 19 secondsSo preview settings popover uses the props accepts project ID initial values and on save. It will have its own open
3:12:283 hours, 12 minutes, 28 secondsand set open use state. It will have a very simple method to update the settings you calling use mutation API
3:12:373 hours, 12 minutes, 37 secondsproject update settings if you wish to you can always um abstract this let me
3:12:463 hours, 12 minutes, 46 secondssee so this is for projects so this would be inside of projects hooks we have use projects so yeah you could do
3:12:543 hours, 12 minutes, 54 secondsexport const let's see what we call it use rename project so this would be use update project settings
3:13:033 hours, 13 minutes, 3 secondslike so and it will just return this and then later you can add optimistic mutation. Let me see do we have any
3:13:113 hours, 13 minutes, 11 secondsto-do for optimistic mutation? We do not to do add optimistic mutation if you want to improve it later. So I
3:13:203 hours, 13 minutes, 20 secondslike to abstract them this way especially because of those optimistic mutation things. It's way easier to maintain that in a different file. So
3:13:293 hours, 13 minutes, 29 secondsthat's what I'm going to do. I'm going to import it like that. I'm going to move it here separately and I'm going to remove the use mutation import since I
3:13:373 hours, 13 minutes, 37 secondsno longer need it. I can directly access update settings from the hook now.
3:13:423 hours, 13 minutes, 42 secondsGreat. Now what we ought to do is create the form. So we're going to start by calling the use form hook
3:13:503 hours, 13 minutes, 50 secondsfrom tanstack react form. So this is a different uh hook than your usual react hook form. We're going to define the
3:13:583 hours, 13 minutes, 58 secondsdefault values which can be install command and developer command which come uh from the initial values prop. If we
3:14:053 hours, 14 minutes, 5 secondshave it, we use it otherwise we fall back to an empty string. Now for the for the validators, we're simply going to
3:14:123 hours, 14 minutes, 12 secondsuse onsubmit validate using form schema which we defined right here.
3:14:203 hours, 14 minutes, 20 secondsAfter the validators, let's call the actual onsubmit method which is going to be asynchronous accepts a value.
3:14:283 hours, 14 minutes, 28 secondsMy apology, yes, just a single value.
3:14:323 hours, 14 minutes, 32 secondsAnd you can see how uh in tan stack react form, we define all of those things instead of use form. Whereas in
3:14:403 hours, 14 minutes, 40 secondsthe react hook form, you have to do it kind of all over the place. I think I kind of prefer this one to be honest.
3:14:483 hours, 14 minutes, 48 secondsNow inside of this onsubmit let's simply define what we do await update settings pass in the ID to be project ID and the
3:14:573 hours, 14 minutes, 57 secondsactual settings install command value.install command or undefined if we ever want to reset the values and
3:15:063 hours, 15 minutes, 6 secondsdeveloper command to be value developer command or undefined. There we go. After
3:15:123 hours, 15 minutes, 12 secondsthat we close the popover and then we call the onsave call back if
3:15:193 hours, 15 minutes, 19 secondswe have it. There we go. Now let's go ahead and define a very simple const
3:15:263 hours, 15 minutes, 26 secondshandle open change method which will receive a new is open value which is a type of boolean.
3:15:333 hours, 15 minutes, 33 secondsAnd in here what we're going to do is check if is open. If it is, call form.reset with an install command of the initial values.
3:15:443 hours, 15 minutes, 44 secondsCheck if we have install command or fall back to an empty string. And then do the same for dev command.
3:15:513 hours, 15 minutes, 51 secondsAnd finally, outside of the if clause, simply call set open to is open. So every single time handle
3:16:013 hours, 16 minutes, 1 secondopen change triggers, if we actually open it, we're just going to reset the form.
3:16:073 hours, 16 minutes, 7 secondsGreat. And now we just have to build a composition for the popover. So let's go ahead and return the actual popover
3:16:163 hours, 16 minutes, 16 secondselement which will accept an open prop and onopen change which we've defined just now. Then we're going to have a
3:16:243 hours, 16 minutes, 24 secondspopover trigger which will have an as child prop. So it will actually become the element inside. The element inside
3:16:323 hours, 16 minutes, 32 secondswill be the button with the size of small variant of ghost class name height full and rounded none and the title
3:16:403 hours, 16 minutes, 40 secondspreview settings. And inside we're simply going to render a settings icon which we've imported from Lucid React
3:16:473 hours, 16 minutes, 47 secondswith a size three. Then it's time to build the popover content which we uh composition outside of the popover
3:16:543 hours, 16 minutes, 54 secondstrigger. It will have a class name of width 80 and a line of end. Inside we are working with a normal form element.
3:17:033 hours, 17 minutes, 3 secondsSo a native HTML form element which has an onsubmit in which we prevent a default and simply handle submit from the form hook.
3:17:133 hours, 17 minutes, 13 secondsSo that form is referring to this form right here.
3:17:173 hours, 17 minutes, 17 secondsThen let's go ahead and add a div here so we can separate the fields. I'm going
3:17:253 hours, 17 minutes, 25 secondsto add just one more div so we have further separation.
3:17:303 hours, 17 minutes, 30 secondsAn H4 which serves as a label preview settings. Let's give the heading for a
3:17:373 hours, 17 minutes, 37 secondsclass name of font medium and text small and the paragraph configure how your project runs in the preview.
3:17:483 hours, 17 minutes, 48 secondsLet me fix the typo and let's give this a class name text extra small and text muted foreground.
3:17:593 hours, 17 minutes, 59 secondsThen let's go ahead and develop our first field. So that's going to be outside of this div right here. And
3:18:053 hours, 18 minutes, 5 secondswe're going to add form dot field like so. And let's go ahead and give it a
3:18:123 hours, 18 minutes, 12 secondsname which can be install command. And then we're going to render a field by
3:18:183 hours, 18 minutes, 18 secondsextracting the field prop and using the field composition. So
3:18:263 hours, 18 minutes, 26 secondsfield label, let me go ahead and fix the typo here. Field label will have a text
3:18:333 hours, 18 minutes, 33 secondsof install command and HTML 4 field.name.
3:18:403 hours, 18 minutes, 40 secondsSo these are completely accessible fields. And below the field label, let's add an input with an ID of field name,
3:18:483 hours, 18 minutes, 48 secondsname of field name, value, field.state dot value, on blur, field, handle blur,
3:18:563 hours, 18 minutes, 56 secondson change, event field, handle change, event target value, and a placeholder npm install indicating to the user what
3:19:043 hours, 19 minutes, 4 secondsis a default value and a little description to explain to the user what this is. And then we can repeat the
3:19:133 hours, 19 minutes, 13 secondsentire thing. So I'm going to paste out the entire thing here. Here it is.
3:19:183 hours, 19 minutes, 18 secondsAnother form field. This one for dev command. Again we extract the field. We render the field label with HTML 4
3:19:283 hours, 19 minutes, 28 secondsfield.name. And we simply render start command inside. And then again another input with the exact same props with a
3:19:353 hours, 19 minutes, 35 secondsdifferent placeholder npm rundev and a slightly different description explaining that this is a uh command to
3:19:423 hours, 19 minutes, 42 secondsstart the developer server. So these two are identical. This one is for dev command and the one above is for the install command. Great.
3:19:533 hours, 19 minutes, 53 secondsAnd now let's go ahead and add one thing you probably didn't see before which is a form.subscribe.
3:19:593 hours, 19 minutes, 59 secondsAnd inside of here it can have a selector and it can look for can submit and is submitting. And then using those
3:20:083 hours, 20 minutes, 8 secondsfields we can go ahead and render something inside.
3:20:143 hours, 20 minutes, 14 secondsAnd what we're going to render is a button component which will have a type of submit size of
3:20:223 hours, 20 minutes, 22 secondssmall class name with full. It will be disabled if we can't submit or if we are already submitting. And if we are, we're
3:20:303 hours, 20 minutes, 30 secondsgoing to display saving. Otherwise, we're going to display save changes.
3:20:353 hours, 20 minutes, 35 secondsThere we go. That's it for the preview settings popover. And that's what it's like to work with tanstack uh form. I
3:20:423 hours, 20 minutes, 42 secondspersonally prefer this over react hook form. And I'm going to remove API from here. Not to say that reactful form is
3:20:493 hours, 20 minutes, 49 secondsan amazing library. It absolutely is. I just always feel like developer experience with Tanstack is just a tiny bit more nicer.
3:21:003 hours, 21 minutesGreat. Now, let's go ahead and start bringing everything together and finally rendering this. So, we're going to go
3:21:073 hours, 21 minutes, 7 secondsinside of features projects components and I'm going to create preview dash view.tsx.
3:21:183 hours, 21 minutes, 18 secondsI'm going to go ahead and mark this as use client. I'm going to import use state and allotment.
3:21:253 hours, 21 minutes, 25 secondsAnd then I'm going to go ahead and import loader to icon, terminal square icon, alert triangle icon, and refresh
3:21:333 hours, 21 minutes, 33 secondsCW icon. I'm going to import our use web container from features preview hooks use web container which we've developed.
3:21:423 hours, 21 minutes, 42 secondsI'm going to import our preview settings popover from features preview components preview settings popover which we just finished. Then I'm going to add the
3:21:513 hours, 21 minutes, 51 secondspreview terminal from the exact same place. We've finished all of these components already. Then I'm going to
3:21:573 hours, 21 minutes, 57 secondsadd a button component. I'm going to add a very simple use project from hooks.
3:22:043 hours, 22 minutes, 4 secondsUse project and I'm going to add ID from generated data model from convex.
3:22:123 hours, 22 minutes, 12 secondsI'm going to export const preview view which very simply accepts project ID
3:22:193 hours, 22 minutes, 19 secondswhich is a type of ID projects in here the first thing I'm going to do is I'm going to load the project using
3:22:263 hours, 22 minutes, 26 secondsthe hook project use project ID then I'm going to decide whether I should show or
3:22:353 hours, 22 minutes, 35 secondsshouldn't show the terminal using a simple state then we can go ahead head
3:22:413 hours, 22 minutes, 41 secondsand call use web container. Finally, now use web container needs to have a
3:22:483 hours, 22 minutes, 48 secondscouple of properties such as the project ID so we know what files to load and what files to uh transform into a
3:22:563 hours, 22 minutes, 56 secondsspecific file tree, whether it's enabled or not, and finally the settings for the project. So the user can change the
3:23:043 hours, 23 minutes, 4 secondsinstall command and the developer command. The web container gives us the following items. Status preview URL
3:23:133 hours, 23 minutes, 13 secondserror restart and terminal output. Let's go ahead and show the loading state
3:23:213 hours, 23 minutes, 21 secondsif the status of the web container is booting or installing.
3:23:263 hours, 23 minutes, 26 secondsAnd now let's go ahead and start rendering the entire thing.
3:23:313 hours, 23 minutes, 31 secondsSo we're going to start by defining a div which will take the full height, initiate the flex system and a
3:23:383 hours, 23 minutes, 38 secondsbackground. Then we're going to display a navbar with a height of 35 or as written here 8.75.
3:23:483 hours, 23 minutes, 48 secondsSo I'm going to change it to that. Flex item center border bottom background sidebar and shrink zero.
3:23:573 hours, 23 minutes, 57 secondsAfter that, I'm going to go ahead and add a button allowing us to refresh the web container. This button will have a
3:24:053 hours, 24 minutes, 5 secondssize of small, variant of ghost, class name of height full, and rounded none.
3:24:103 hours, 24 minutes, 10 secondsIt will be disabled if the web container is loading. And on click, we will call the restart method from the web container. The title will be restart
3:24:183 hours, 24 minutes, 18 secondscontainer and it's going to have a refresh icon. Then what we're going to do is we're going to display
3:24:273 hours, 24 minutes, 27 secondssomething like a little URL bar uh showing us exactly what URL we are loading.
3:24:343 hours, 24 minutes, 34 secondsSo this is how that's going to look like. A div with a class name flex one height full flex items center px of
3:24:423 hours, 24 minutes, 42 secondsthree background color border x text extra small text muted foreground truncate and font mono.
3:24:523 hours, 24 minutes, 52 secondsFirst thing we're going to check if are we loading? If we are loading, instead of displaying the URL, what we're going to do is simply display a loader to icon
3:25:013 hours, 25 minutes, 1 secondfrom Lucid React. I'm going to give it a class name of size three and animate spin.
3:25:093 hours, 25 minutes, 9 secondsThen I'm going to give this parent div a class name flex items center and gap 1.5.
3:25:183 hours, 25 minutes, 18 secondsAnd then I will check the status. If the status is booting, I'm going to display a more userfriendly starting otherwise
3:25:283 hours, 25 minutes, 28 secondsinstalling so the user is aware of what's actually happening.
3:25:323 hours, 25 minutes, 32 secondsAnd then I'm going to check if I have the preview URL inside of a simple span.
3:25:393 hours, 25 minutes, 39 secondsI will display that preview URL. I'm just going to make sure to truncate it so it doesn't overflow. So let's give it a class name truncate.
3:25:503 hours, 25 minutes, 50 secondsThen I will check if not loading and if not preview URL
3:25:583 hours, 25 minutes, 58 secondspreview URL and if there is no error either I will just add a span ready to preview.
3:26:103 hours, 26 minutes, 10 secondsGreat.
3:26:113 hours, 26 minutes, 11 secondsAnd one more button actually two more buttons we have to add. One is to trigger the terminal. So a button size
3:26:203 hours, 26 minutes, 20 secondssmall variant ghost class name height full rounded none with a title toggle terminal on click set show terminal. And
3:26:303 hours, 26 minutes, 30 secondswhat I actually prefer is if we just reverse the current value. This way it will not get conflicted with any other
3:26:383 hours, 26 minutes, 38 secondsasync state. So we just toggle the current state of the terminal like show it or hide it. And then we need to add a button which will open the preview
3:26:473 hours, 26 minutes, 47 secondssettings popover which is very easy because we just have to render the preview settings popover and pass it project ID the initial values and on
3:26:553 hours, 26 minutes, 55 secondssave. That's it. And that automatically renders if you look down the trigger which is a button with the exact same
3:27:043 hours, 27 minutes, 4 secondssize variant and class name as its uh siblings. So it looks exactly the same.
3:27:113 hours, 27 minutes, 11 secondsGreat. Now outside of this div which represents the navbar, we have to render the actual content. Right? So I will
3:27:203 hours, 27 minutes, 20 secondsstart with a class name flex one and a minimum height of zero. And then we're going to go ahead and start working with
3:27:283 hours, 27 minutes, 28 secondsallotments. So we start with the main allotment and we're going to make it vertical.
3:27:353 hours, 27 minutes, 35 secondsThen let's add the first allotment pane inside. This allotment pane will first check if there is an error present. So
3:27:443 hours, 27 minutes, 44 secondsif we have any error from the web container, let's go ahead and display that.
3:27:503 hours, 27 minutes, 50 secondsThat's going to be size full flex item center justify center and text muted foreground inside another div just to
3:27:583 hours, 27 minutes, 58 secondscenter it further. flex flex column item center gap to maximum width medium MX auto and text center.
3:28:093 hours, 28 minutes, 9 secondsI'm going to add an alert triangle icon with class name size six. I'm going to add a paragraph showing the exact error
3:28:183 hours, 28 minutes, 18 secondsand I'm going to display a button component allowing the user to restart.
3:28:233 hours, 28 minutes, 23 secondsSo on click restart size small variant outline refresh icon and the restart label. So this is the error state. If
3:28:333 hours, 28 minutes, 33 secondssomething goes wrong with the web container, this is what the user will be shown.
3:28:393 hours, 28 minutes, 39 secondsNow let's go ahead and display a very similar loading indicator.
3:28:443 hours, 28 minutes, 44 secondsSo still within the allotment pane let's check if we are loading and if we have no error in that case display a div with
3:28:533 hours, 28 minutes, 53 secondssize full flex item center justify center and text muted foreground within
3:28:593 hours, 28 minutes, 59 secondsanother div flex flex call item center gap to maximum width medium MX auto and
3:29:073 hours, 29 minutes, 7 secondstext center. Finally, loader 2 icon with size six and animate spin. A paragraph with text small, font medium, and the
3:29:163 hours, 29 minutes, 16 secondslabel installing. And the moment you've been waiting for, the actual preview URL. That's the easiest part. Just a very simple iframe source preview URL.
3:29:283 hours, 29 minutes, 28 secondsThis is why we needed to set up proper course otherwise iframe would not be able to be loaded. and the class name size full border zero and the title of
3:29:373 hours, 29 minutes, 37 secondspreview. Great. The last thing we ought to do is the allotment pane for the terminal. So outside of this allotment
3:29:463 hours, 29 minutes, 46 secondspane, go ahead and add a uh check if we should show the terminal or not.
3:29:543 hours, 29 minutes, 54 secondsIf we should go ahead and open an allotment pane with the minimum size 100, maximum 500, and preferred size of
3:30:013 hours, 30 minutes, 1 second200. Then in here a div hide full flex flex column bg background and border on
3:30:103 hours, 30 minutes, 10 secondstop within another div with a class name height 7 flex item
3:30:193 hours, 30 minutes, 19 secondscenter px3 text extra small gap 1.5 text muted foreground border bottom border
3:30:273 hours, 30 minutes, 27 secondsborder with a 50% opacity and shrink zero. Then I'm going to add a very simple terminal square icon for lucid
3:30:363 hours, 30 minutes, 36 secondsreact with class name size three and a label terminal.
3:30:423 hours, 30 minutes, 42 secondsAnd finally let's render preview terminal component with an output terminal output which we receive from use web container hook.
3:30:533 hours, 30 minutes, 53 secondsAnd that is it. We are now finally ready to display this inside of the actual
3:30:593 hours, 30 minutes, 59 secondspage. So let's go ahead inside of let me just remind myself this is inside
3:31:083 hours, 31 minutes, 8 secondsof projects components project ID view. So in here we have two allotment panes.
3:31:163 hours, 31 minutes, 16 secondsOne for the file explorer, one for editor view. But actually this isn't in an allotment pane. This is in kind of
3:31:233 hours, 31 minutes, 23 secondslike this tab switcher, right? So we have a tab for editor. But we never developed the tab for preview. So
3:31:303 hours, 31 minutes, 30 secondsfinally let's find this where active view checks for preview. And instead of rendering this, let's render preview view.
3:31:403 hours, 31 minutes, 40 secondsMake sure to import it and pass in the project ID. Project ID. Make sure you
3:31:473 hours, 31 minutes, 47 secondshave preview view imported. So, we were just working on this, I believe, with all of these components. And we are now ready. Let's go ahead and check it out.
3:31:573 hours, 31 minutes, 57 secondsSo, I'm going to go ahead and revisit the last app I have developed. Uh oh, or maybe I have maybe this isn't the one.
3:32:073 hours, 32 minutes, 7 secondsThis one. basically the one that apparently should be working and it should be a simple to-do app. So my
3:32:133 hours, 32 minutes, 13 secondsprompt was create a React plus V app and a simple to-do app inside. And when I click on preview, you can see that now I am installing it here, here, and here.
3:32:243 hours, 32 minutes, 24 secondsSo I have synchronized outputs everywhere. I'm going to go ahead and try toggling the terminal. You can see that I can do that. I can also click on
3:32:323 hours, 32 minutes, 32 secondshere and I can see the preview settings with my install command and my start command. So, what I'm going to do now is I'm just going to leave it for a few seconds. And looks like it's working.
3:32:433 hours, 32 minutes, 43 secondsThere we go. You can see the allotment pane can be moved. And now I can go ahead and add hello world. Add to-do.
3:32:503 hours, 32 minutes, 50 secondsAnd just like that, it works. Very, very good. You can see that even the actual code works. So, I'm super super happy
3:32:583 hours, 32 minutes, 58 secondswith this one. Uh basically uh the only way you can test whether this works right now is with a working code. Right?
3:33:073 hours, 33 minutes, 7 secondsIf you go ahead and just start a new project and go into preview, there is nothing to preview. Uh you can try
3:33:143 hours, 33 minutes, 14 secondsadding something like index.js and try console log hello world inside
3:33:213 hours, 33 minutes, 21 secondsand this will be synchronized. Uh sometimes you might need to do a refresh especially in development. it kind of uh uses the old one, but you can see it fails because it's not a real project.
3:33:313 hours, 33 minutes, 31 secondsIt doesn't have a package JSON. So, you need to be able to at least ask your AI
3:33:373 hours, 33 minutes, 37 secondsagent create a minimum uh how do I preview
3:33:443 hours, 33 minutes, 44 secondsApple project that can be started with web containers.
3:33:553 hours, 33 minutes, 55 secondsSo basically ask your AI to do something like that. Uh okay, my message failed to
3:34:023 hours, 34 minutes, 2 secondssend. Maybe I have some tokens or something. Uh oh, my ingest is not running. npx.
3:34:103 hours, 34 minutes, 10 secondsSo you probably have the same error then. Let me try npx inest. There we go.
3:34:163 hours, 34 minutes, 16 secondsLet me start again. I will start a completely new project. go here and I will again ask it to create a minimum
3:34:253 hours, 34 minutes, 25 secondspreviewable project that can be started with web containers. So yes, you basically have to ask your app to create
3:34:333 hours, 34 minutes, 33 secondssomething simple. And then I'm going to try a few of these examples and I'm going to kind of purposely try and
3:34:403 hours, 34 minutes, 40 secondschange the install script so we can see if the preview settings are working because everything else is working just fine. So I'm going to pause and we're going to see the result.
3:34:513 hours, 34 minutes, 51 secondsAnd here is my result. So just a super simple index html, a super simple
3:34:583 hours, 34 minutes, 58 secondspackage JSON which uses npx to serve, some readme script.js and styles.css. So you can see it should be able to generate something like this.
3:35:093 hours, 35 minutes, 9 secondsAnd you can see it works, right? It successfully run npm install and npm rundev. So, what I'm going to do now is
3:35:173 hours, 35 minutes, 17 secondsI'm going to change my dev script to be 4,000 for example. I'm purposely going to do that and I'm going to do a hard refresh here. So, now uh I am expecting
3:35:263 hours, 35 minutes, 26 secondsthis to uh install but to fail when it needs to start. Okay, I couldn't do
3:35:343 hours, 35 minutes, 34 secondsthat. Um Oh, because it the port doesn't matter. My apologies. This matters. So,
3:35:403 hours, 35 minutes, 40 secondslet's see what does it run. It uses npxs serve-s. So it runs npm rundev. So if I
3:35:493 hours, 35 minutes, 49 secondschange this to I don't know custom, right? And do a hard refresh. I now
3:35:563 hours, 35 minutes, 56 secondsexpect again install to work. But I think h again it keeps working. Um I'm not sure why.
3:36:113 hours, 36 minutes, 11 secondsI'm trying to make it fail. Oh, looks like I don't know why it keeps working.
3:36:173 hours, 36 minutes, 17 secondsOh, this didn't update it seems. Let me go ahead and make sure this is updated.
3:36:243 hours, 36 minutes, 24 secondsDo I have my convex functions ready custom? Perhaps we have some bug if it's not updated. Okay, now it's custom.
3:36:343 hours, 36 minutes, 34 secondsLet's give it a third try. There we go.
3:36:363 hours, 36 minutes, 36 secondsMissing script dev. So, now it's failing. Okay, just make sure that your code was actually saved. I probably refreshed too fast. And now I'm going to
3:36:453 hours, 36 minutes, 45 secondsgo ahead inside of project settings and I'm going to change this to npm run custom. And I'm going to click save changes. And let's see if it will work
3:36:543 hours, 36 minutes, 54 secondsnow. And there we go. Because we are able to change to npm run custom. What an amazing job you've done here. you
3:37:033 hours, 37 minutes, 3 secondsdevelop the entire preview tab, the URL, the web containers, the terminal output, absolutely everything. Uh, one thing I
3:37:113 hours, 37 minutes, 11 secondswant to make you aware of before we finish the chapter is the license of web containers. So, web containers are absolutely the best solution for this.
3:37:203 hours, 37 minutes, 20 secondsYou can try it with sandboxes or something else, but truly nothing's come close to instantaneous hot reload preview like this. Sandboxes cannot do
3:37:283 hours, 37 minutes, 28 secondsthat. Uh so because of that you should be aware of web containers pricing uh which is basically free for I believe
3:37:383 hours, 37 minutes, 38 secondsyes for non-commercial usages is completely free uh these API sessions I'm not even sure how much this is but I
3:37:463 hours, 37 minutes, 46 secondsit never stopped working for me so I doubt it's going to start stop working for your personal projects but if you plan to commercialize your project make
3:37:553 hours, 37 minutes, 55 secondssure to contact them right so this is uh I'm telling this to people who want to build this into a business or something, you should probably check out stack
3:38:033 hours, 38 minutes, 3 secondsblitz uh pricing. I haven't found any better solution than web containers. I think they're an industry standard. If
3:38:113 hours, 38 minutes, 11 secondsyou uh know something better, feel free to leave a comment so I will review and maybe teach that in the future. But uh I mean you can see how well web containers
3:38:203 hours, 38 minutes, 20 secondsactually work. So go ahead and play around you know uh ask AI to create something and try and running it in the preview. Perhaps you will see some
3:38:293 hours, 38 minutes, 29 secondserrors you know just you can see how error screens look and things like that. Uh other than that I think we're done.
3:38:353 hours, 38 minutes, 35 secondsSo we completed web containers file tree terminal and the preview settings. So chapter 14 web containers terminal and
3:38:433 hours, 38 minutes, 43 secondspreview. I'm going to do get checkout-b chapter 14 web containers
3:38:533 hours, 38 minutes, 53 secondsterminal and preview get addit commit 14 web containers terminal and
3:39:033 hours, 39 minutes, 3 secondspreview and get push u origin 14 web containers terminal and preview. So, we now just
3:39:123 hours, 39 minutes, 12 secondspushed a new branch in your IDE. You should now see that you are on your new branch. You shouldn't have any unstaged
3:39:193 hours, 39 minutes, 19 secondschanges anymore. And we're going to do the usual thing now. We're going to open a new pull request and we're going to
3:39:273 hours, 39 minutes, 27 secondsreview it. So, let me go ahead and create a pull request. And now we're going to go file by file to see if we made any critical mistakes here.
3:39:363 hours, 39 minutes, 36 secondsAnd here we have the summary by Code Rabbit. We added project preview capability with live development server display. We integrated terminal pane to
3:39:453 hours, 39 minutes, 45 secondsview server output and commands in real time. We added settings panel to configure custom install and dev commands per project. We added a restart
3:39:543 hours, 39 minutes, 54 secondsbutton to reset the preview server. We enhanced security headers for cross origin resource sharing. And now let's
3:40:013 hours, 40 minutes, 1 secondtake a look at some issues it found. So the first issue it found is the fact that we are applying this headers across
3:40:113 hours, 40 minutes, 11 secondsall paths. Initially I did this simply because that's what fixed my issue. But looking at it now perhaps we could limit
3:40:193 hours, 40 minutes, 19 secondsit to specific forward/ projects and then a specific project ID because that is the URL where we actually need that
3:40:273 hours, 40 minutes, 27 secondscourse to happen because of the iframe and web containers. So in here it's warning us that this might in infer with
3:40:353 hours, 40 minutes, 35 secondssomething else we might be doing in the future. So that's actually a very good comment. We might actually especially for production if you're planning I
3:40:433 hours, 40 minutes, 43 secondswould recommend just specifying uh the specific path where this is needed where we render the I frame. So that would be
3:40:503 hours, 40 minutes, 50 secondsthis path as uh code rabbit so politely told us. Great.
3:40:563 hours, 40 minutes, 56 secondsUh and you can see this is how you would write it. So it gave you the solution forward/ projects and then you would do
3:41:033 hours, 41 minutes, 3 secondsany path after the projects in here. It told me that I'm using tailwind incorrectly that I should be using the
3:41:103 hours, 41 minutes, 10 secondsimportant sign uh at the beginning. Uh you can do that but it also works this way. I gave it a screenshot showing that
3:41:173 hours, 41 minutes, 17 secondsit's parsed correctly and after that it stored that information. So now it knows that it works in this hook use web
3:41:263 hours, 41 minutes, 26 secondscontainer. it noticed that uh we are not guarding the async boot sequence against restart or unmmon races. Uh so yeah, we
3:41:353 hours, 41 minutes, 35 secondscould look into that. I'm not exactly sure what it means just at the top of my mind, but I will research if this is something critical. It does say it is
3:41:443 hours, 41 minutes, 44 secondsmajor, but I will I will take a look and see, you know, how exactly we can fix this. Is it something simple or
3:41:523 hours, 41 minutes, 52 secondssomething we would have to rewrite entirely? But you know for this state of the project it works pretty well. But just keep in mind that yes there are
3:42:003 hours, 42 minutespossible restart or unmmon races going on here.
3:42:043 hours, 42 minutes, 4 secondsAnd in here it's basically making us aware that we are skipping empty files during hot reload. And we know that we
3:42:123 hours, 42 minutes, 12 secondswrote that on purpose. Same with storage files simply because they increase complexity. And I just wanted to show you that it works at the moment. Uh in
3:42:213 hours, 42 minutes, 21 secondshere it is telling us that there is a potential okay so potential issue we can
3:42:293 hours, 42 minutes, 29 secondsavoid rendering a stale preview when error is set. So if we have a preview oh that's because yes we independently
3:42:373 hours, 42 minutes, 37 secondsrender preview URL and we independently render the error. So we should probably not render the preview URL if error
3:42:443 hours, 42 minutes, 44 secondsexists because there is a chance we render both of them at the same time. I think that's the the problem. Yes, because we independently render this and
3:42:523 hours, 42 minutes, 52 secondswe independently render this. There's a chance both of them are active at the same time. Good catch. So, those are some things to fix. Other than that,
3:43:013 hours, 43 minutes, 1 secondpretty good pull request. Uh, let's go ahead and merge the pull request. And once we do that, let's go ahead back to
3:43:093 hours, 43 minutes, 9 secondsget checkout main and get pull origin main. So, we are up
3:43:183 hours, 43 minutes, 18 secondsto date. And as always, what I like to do is confirm that inside of my IDE. So I am on the main branch and inside of my
3:43:273 hours, 43 minutes, 27 secondssource graph right here, you can see I've detached to 14 to implement web containers terminal and preview and merge that into main. I believe that
3:43:363 hours, 43 minutes, 36 secondsmarks uh the end of this chapter. So we have successfully uh implemented uh web containers and course. We built
3:43:453 hours, 43 minutes, 45 secondscomplete file tree mounting system and we implemented the terminal with Xterm.
3:43:493 hours, 43 minutes, 49 secondsAnd finally, we created preview settings with custom commands. Amazing job and see you in the next chapter.
Chapter 4: 15 GitHub Import Export
3:43:563 hours, 43 minutes, 56 secondsIn this chapter, we're going to implement GitHub import and export functionality. We're going to enable
3:44:033 hours, 44 minutes, 3 secondsusers to import a GitHub repository into Polaris as a new project. And we're going to allow them to export a Polaris
3:44:113 hours, 44 minutes, 11 secondsproject to a new GitHub repository. Both of these features will require GitHub oath integration via clerk, a background
3:44:203 hours, 44 minutes, 20 secondsjob processing viaest as well as binary file support for which we have already prepared when we started building the
3:44:293 hours, 44 minutes, 29 secondsschema. So let's start by installing the dependencies needed to make this work.
3:44:363 hours, 44 minutes, 36 secondsSo the dependencies we're going to install are Octokit which is the official GitHub API client is binary
3:44:433 hours, 44 minutes, 43 secondsfile which is a simple npm package I found which is very good at detecting whether a file is binary. There are many
3:44:503 hours, 44 minutes, 50 secondsways you can do this many packages. I just found this one to do the job uh as I wanted to and react icons simply because I know there is an icon for a
3:44:593 hours, 44 minutes, 59 secondsGitHub logo there. So let's go ahead and install these three packages. After that, I'm going to go ahead and show you
3:45:083 hours, 45 minutes, 8 secondsmy package JSON so you can see exactly the versions that I have.
3:45:143 hours, 45 minutes, 14 secondsSo, is binary file 5.0.7, octokit 5.5, and looks like we already had React icons uh 5.5.0.
3:45:253 hours, 45 minutes, 25 secondsIf you didn't have it, now you do.
3:45:283 hours, 45 minutes, 28 secondsGreat. So what we ought to do next is actually configure our clerk and add an
3:45:373 hours, 45 minutes, 37 secondsadditional o scope to our github oath provider.
3:45:433 hours, 45 minutes, 43 secondsSo using the link on the screen you can visit uh clerk's dashboard here and let's go ahead inside of configure SSO
3:45:523 hours, 45 minutes, 52 secondsconnections. Now in here you will basically see providers you have decided to add when you configured clerk. If you
3:46:003 hours, 46 minutesdon't have GitHub here, go ahead click add a connection for all users and search for GitHub.
3:46:083 hours, 46 minutes, 8 secondsOnce you've added GitHub here, go ahead and open it. I would recommend that you enable it for sign up and sign in. This
3:46:153 hours, 46 minutes, 15 secondsis what I told you to do in the beginning. So it's very easy for your users to immediately uh get uh their
3:46:243 hours, 46 minutes, 24 secondsGitHub connected otherwise they would have to do it additionally but it's perfectly fine if you have multiple
3:46:313 hours, 46 minutes, 31 secondsproviders right you can have Google you can have email and password username right but it's very useful to have GitHub as well since our accounts will
3:46:393 hours, 46 minutes, 39 secondsbe so tightly coupled with them anyway now here's the problem uh GitHub Oout comes with some scopes But right now if
3:46:493 hours, 46 minutes, 49 secondswe tried to use uh the token from the user who logs in using GitHub uh we wouldn't have the necessary permissions
3:46:563 hours, 46 minutes, 56 secondsto actually load their private repositories. Because of that we have to enable use custom credentials. And lucky
3:47:043 hours, 47 minutes, 4 secondsfor us uh clerk actually shows you the exact documentation on how to add GitHub as a social connection.
3:47:133 hours, 47 minutes, 13 secondsSo we already did this. We navigated to SSO connections. We selected add connection for all users and we added
3:47:203 hours, 47 minutes, 20 secondsGitHub or we already had it from the beginning.
3:47:243 hours, 47 minutes, 24 secondsNow to make the setup process easier, they recommend keeping two browser tabs open. One for the clerk dashboard and one for GitHub developer settings. So
3:47:343 hours, 47 minutes, 34 secondsmake sure you have your developer settings open on GitHub. You can use the link from the documentation right here.
3:47:403 hours, 47 minutes, 40 secondsGitHub developer settings and you should then see all the GitHub apps that you have all all out apps and all personal access tokens.
3:47:523 hours, 47 minutes, 52 secondsAll right. So now what we have to do is we basically have to create a new GitHub
3:47:593 hours, 47 minutes, 59 secondsO for clerk. So let's register a new O here. I'm going to go ahead and select
3:48:063 hours, 48 minutes, 6 secondsnew ALF app. I'm going to call this Polaris. For the homepage URL, for now, you can just go ahead and use localhost
3:48:143 hours, 48 minutes, 14 seconds3000 because that's where our app is running. But for authorization callback URL, you have to copy exactly what's
3:48:223 hours, 48 minutes, 22 secondswritten here. So, let's go ahead and paste that. And let's click register application. Now, in here, you have the
3:48:303 hours, 48 minutes, 30 secondsclient ID, which you can immediately copy. You can go back to clerk and you can paste the client ID. And now we need
3:48:373 hours, 48 minutes, 37 secondsto obtain the client secret by clicking generate a new client secret. This will uh most likely require you to do two factor authentication.
3:48:473 hours, 48 minutes, 47 secondsOnce you've successfully authenticated, you will have access to the secret. Go ahead and copy it as this is the only
3:48:543 hours, 48 minutes, 54 secondstime you will see it. And once you have the secret, you can go ahead and paste the secret here. And now here's the deal
3:49:023 hours, 49 minutes, 2 secondswith the scopes. Basically, right now, as you can see, I have scopes for user email and read user. And I'm going to go
3:49:113 hours, 49 minutes, 11 secondsahead and also add repo scope. So, at the time of me making this tutorial, this is the scope that is required in
3:49:193 hours, 49 minutes, 19 secondsorder to access users reposi repositories. So, that's the scope we need. And you can of course later always
3:49:273 hours, 49 minutes, 27 secondsadd or remove scopes. So, let's go ahead and click save. Great.
3:49:323 hours, 49 minutes, 32 secondsNow, uh what I would suggest doing is running your app and simply checking if everything still works just fine. Uh regarding the login.
3:49:443 hours, 49 minutes, 44 secondsSo, let's go ahead and see. Did we implement a way to log out? I think we did right here. So, I'm going to go ahead and log out now. I will refresh my
3:49:533 hours, 49 minutes, 53 secondspage and I'm going to go ahead and sign in. Uh, I'm going to use GitHub to sign in. And let's see. There we go. You can
3:50:003 hours, 50 minutessee that now the scopes are a little bit different. So, besides my personal data, email address and profile information,
3:50:083 hours, 50 minutes, 8 secondsit also shows access to repositories, both public and private. So, this is what all of your users will see that
3:50:173 hours, 50 minutes, 17 secondsPolaris is using that scope to access repositories. Uh perhaps there is a more granular uh scope which might be better
3:50:273 hours, 50 minutes, 27 secondsto use but for our purposes repo is the one we need. Basically you should see this now and you can also see that user
3:50:343 hours, 50 minutes, 34 secondscan also give access to any organizations that they have. Basically let's just authorize the user and everything seems to work just fine.
3:50:443 hours, 50 minutes, 44 secondsGreat. So that part is officially finished.
3:50:483 hours, 50 minutes, 48 secondsSo what we have to do next is we have to develop some system mutations. Now most of these system mutations will also
3:50:573 hours, 50 minutes, 57 secondsrefer to something we already implemented. So I'm just going to give you a reminder inside of convex schema.ts.
3:51:053 hours, 51 minutes, 5 secondsIf you take a look at projects, you can see that we already have import status and we already have export status as
3:51:133 hours, 51 minutes, 13 secondswell as export repo URL. So these three have not been used at all but we already
3:51:203 hours, 51 minutes, 20 secondsimplemented them. Uh you can see let me see in chapter 7 projects that's where we implemented these three fields. So
3:51:293 hours, 51 minutes, 29 secondsjust confirm that you have them. If by any chance you don't go ahead and pause the screen and add these three fields.
3:51:363 hours, 51 minutes, 36 secondsEverything else I think is pretty standard. So now we're going to go ahead and we're going to focus on Convex's
3:51:433 hours, 51 minutes, 43 secondssystem mutations here. So the last thing we added here are a bunch of agent tools. And now we're going to go ahead
3:51:523 hours, 51 minutes, 52 secondsand implement all the mutations we need to successfully import a GitHub project or export a
3:52:003 hours, 52 minutesGitHub project. So the first one we're going to do is called cleanup. So I'm going to go ahead and prepare it.
3:52:083 hours, 52 minutes, 8 secondsThe cleanup mutation will accept the internal key such as every single mutation inside of system.ds
3:52:163 hours, 52 minutes, 16 secondsand it will also accept project ID. What this will be used for is to very simply clean up all files within a project.
3:52:253 hours, 52 minutes, 25 secondsSince if you trigger an action to import from GitHub, it might be a good idea to clean up any files you might have
3:52:333 hours, 52 minutes, 33 secondscreated before that because an import opinion is a mirror, right? So it should be a one by one replica of what's in the
3:52:423 hours, 52 minutes, 42 secondsGitHub. So the first thing we're going to do here is we're going to fetch all the files using a project ID using by
3:52:493 hours, 52 minutes, 49 secondsproject index here. And then what we're going to do is very simply uh delete the
3:52:553 hours, 52 minutes, 55 secondsfiles here like so. And let's go ahead and simply delete any storage files if
3:53:043 hours, 53 minutes, 4 secondsthey exist. And let's go ahead and delete file ID. So in this scenario, I
3:53:123 hours, 53 minutes, 12 secondsdon't think we need to do any recursive deleting. Usually that's the first thing that I think of whenever we delete file is like hey I need to detect if this is
3:53:193 hours, 53 minutes, 19 secondsa folder and then delete all of its descendants but not in this case because these are literally all the files both
3:53:263 hours, 53 minutes, 26 secondsfolders and files we are not querying by type anywhere just by project. So in
3:53:333 hours, 53 minutes, 33 secondsthis for loop all files and folders will be deleted as well as any storage if
3:53:393 hours, 53 minutes, 39 secondsthey were binary files. Great. Now let's go ahead and implement a very simple
3:53:453 hours, 53 minutes, 45 secondsgenerate upload URL. Generate upload URL is a mutation which will accept the internal key and it will very simply be
3:53:543 hours, 53 minutes, 54 secondsused to use context.s storage to generate upload URL. This is from the convex's documentation on how to upload
3:54:023 hours, 54 minutes, 2 secondsfiles. And basically in order uh to upload a file you first need to obtain the upload URL from the back end. And in
3:54:113 hours, 54 minutes, 11 secondsour case, since this will be a background job communicating with convex, we've put this inside of this
3:54:193 hours, 54 minutes, 19 secondssystem queries. Uh well, system mutation to be specific. And we will very simply return to the ingest background job.
3:54:263 hours, 54 minutes, 26 secondsHere's the upload URL for any files you want to upload. Those will probably be some images or some fonts, any binary
3:54:353 hours, 54 minutes, 35 secondsfiles that the GitHub repository might have.
3:54:393 hours, 54 minutes, 39 secondsAnd now let's go ahead and develop the actual uh create binary file mutation.
3:54:473 hours, 54 minutes, 47 secondsSo the create binary file mutation will accept internal key, project ID, name,
3:54:563 hours, 54 minutes, 56 secondsstorage ID, and an optional parent ID with an ID of files.
3:55:023 hours, 55 minutes, 2 secondsAs usual, the handler will be validated using validate internal key. Then we're
3:55:103 hours, 55 minutes, 10 secondsgoing to go ahead and we're going to fetch all files by this project's parent
3:55:173 hours, 55 minutes, 17 secondsID. Uh my apologies. No, that's I I was focusing on the name of the index. We
3:55:243 hours, 55 minutes, 24 secondsare going to uh fetch all files in a specific project and by a parent ID. So
3:55:333 hours, 55 minutes, 33 secondsindependently not by project's parent right it's just that the name of this index confuses me so much every time I read it I read it like that and what we
3:55:423 hours, 55 minutes, 42 secondshave to do here is we basically have to check when we create a binary file this is the exact same thing as if we were
3:55:513 hours, 55 minutes, 51 secondscreating a new file in a folder so let me show you again if I have fu.js and if I attempt to create another fu.js JS I
3:55:593 hours, 55 minutes, 59 secondsget an error. I should not be able to do that. Right? So imagine if they were binary files. So if this were image.png
3:56:073 hours, 56 minutes, 7 secondsfor example and I created another image.png again I shouldn't be able to do that. Now these are not how images are created. Images are going to be
3:56:163 hours, 56 minutes, 16 secondscreated uh in a binary format. But we still have to check in this specific folder. Folder being the parent ID. Are
3:56:263 hours, 56 minutes, 26 secondsthere any existing files? So if we can find an existing file with the same name
3:56:333 hours, 56 minutes, 33 secondswhich is a type of file as well. Let's go ahead and prevent this from happening by throwing file already exists. And
3:56:423 hours, 56 minutes, 42 secondsthen we can simply go ahead and create a new file using context database insert
3:56:483 hours, 56 minutes, 48 secondsfiles with a project ID name type of file storage ID arguments storage ID and
3:56:573 hours, 56 minutes, 57 secondsparent ID arguments parent ID and let's initiate the updated at. And finally let's return file ID.
3:57:073 hours, 57 minutes, 7 secondsGreat. Now we're going to go ahead and create an a mutation called update
3:57:143 hours, 57 minutes, 14 secondsimport status. So this mutation right here update import status which
3:57:223 hours, 57 minutes, 22 secondsI've just added will accept the following arguments internal key project ID status which needs to match what's in
3:57:323 hours, 57 minutes, 32 secondsour schema. So let me confirm import status. importing completed and failed.
3:57:403 hours, 57 minutes, 40 secondsImporting completed and failed. So these need to match. In the handler, we're going to validate internal key. And we
3:57:493 hours, 57 minutes, 49 secondsare very simply going to just patch the project ID. Uh also there is a new syntax for this. You can now
3:57:573 hours, 57 minutes, 57 secondsspecifically define which table you want to patch. I think this is better. I like the explicitness. Basically uh convexes
3:58:073 hours, 58 minutes, 7 secondsids have a very specific prefix which tells them whether something is a table of project or file. So you can just pass
3:58:153 hours, 58 minutes, 15 secondsthis but they've updated it so that you can explicitly select a table and I prefer this way more simply. I think
3:58:243 hours, 58 minutes, 24 secondsexplicitness is always better. Okay. So this is why I just added this function without typing it because it's a super simple one. It's just used to update.
3:58:353 hours, 58 minutes, 35 secondsGreat. Now we're having uh a very similar thing which is the exact same function as this but instead of for
3:58:433 hours, 58 minutes, 43 secondsimport status it's for export status. So it's exactly the same. I'm just going to add it. Let me go ahead and show you.
3:58:523 hours, 58 minutes, 52 secondsUpdate export status is a mutation which again accepts the internal key project ID status which can be exporting
3:59:003 hours, 59 minutescompleted failed and cancelled as well as as well as the repo URL which is an optional string. So just make sure that all of these here match exactly.
3:59:133 hours, 59 minutes, 13 secondsWe are going to validate the internal key and then we're simply going to update again. Let's do patch projects
3:59:203 hours, 59 minutes, 20 secondshere. arguments. ID export status arguments.st status export repo url
3:59:273 hours, 59 minutes, 27 secondsarguments.reo URL and update it at date.now.
3:59:323 hours, 59 minutes, 32 secondsGreat. Now let's go ahead and add a function called get project files with
3:59:383 hours, 59 minutes, 38 secondsURLs. So this is going to be a different one. So let's just prepare it like so.
3:59:463 hours, 59 minutes, 46 secondsGet project files with URLs. It will accept an internal key project ID. It
3:59:533 hours, 59 minutes, 53 secondswill start by validating the internal key so that we know we have access to do this. And we're just going to load every
4:00:014 hours, 1 secondsingle file in the project just as we did in the cleanup function. Right? So using the by project index, we're simply
4:00:094 hours, 9 secondsloading every single file here. And what we're going to do now is we're going to
4:00:144 hours, 14 secondsreturn await promise doall. And inside of here, we're going to go ahead and
4:00:224 hours, 22 secondscall files.m mapap. And then inside for each file, we're going to initiate an
4:00:294 hours, 29 secondsasynchronous function which gives us access to a file. And we are very simply going to check if that file has a storage ID. We have to fetch that file.
4:00:414 hours, 41 secondsSo let's go ahead and do URL await context storage get URL using file.sto
4:00:494 hours, 49 secondsURL because right now if we were to just load all files in a project right if I were to just you know load files here
4:00:584 hours, 58 secondsand one of these files was a binary file. I couldn't do much with storage ID. What do I do with storage ID on the
4:01:084 hours, 1 minute, 8 secondsfront end? I need some kind of URL something to display it. So that's what we're doing here. We are kind of
4:01:154 hours, 1 minute, 15 secondspreparing this uh files so that they are readable by the front end using the
4:01:224 hours, 1 minute, 22 secondsstorage ID which we store in the database. So each file has an option of storage ID which will allow it to become
4:01:304 hours, 1 minute, 30 secondsa binary file. But again we can't do anything on the front end with the storage ID. But by using context.sto.get
4:01:404 hours, 1 minute, 40 secondsURL, we can get an actual URL. And then we are very simply going to go ahead and modify that current file by passing in
4:01:494 hours, 1 minute, 49 secondsthe storage URL. So the front end can then do something with it. And for all other files, we're just going to return the exact same file and set the storage
4:01:574 hours, 1 minute, 57 secondsURL to null. Great. Now let's go ahead and implement a very simple create
4:02:054 hours, 2 minutes, 5 secondsproject mutation. This will be used exclusively uh for when we import a GitHub project.
4:02:134 hours, 2 minutes, 13 secondsSo we already have I think the exact same one in projects create. It's very similar to this one. I'm just going to add it so you can see the differences.
4:02:254 hours, 2 minutes, 25 secondsThe create project mutation accepts internal key name of the project and uh
4:02:324 hours, 2 minutes, 32 secondslet me see owner ID uh that's not something we need I believe or maybe okay we do let me see
4:02:424 hours, 2 minutes, 42 secondsyeah okay so internal key name and owner ID we're going to validate internal key
4:02:504 hours, 2 minutes, 50 secondsand then we're going to simply create a new project with the name the owner ID updated at and here's a catch. The import status will be set to importing.
4:03:024 hours, 3 minutes, 2 secondsWhy? Well, because we know that this specific create project will only be used by inest background job when it's
4:03:114 hours, 3 minutes, 11 secondsstarting to import a project from GitHub. That's why this is inside of a system and not inside of any other one.
4:03:184 hours, 3 minutes, 18 secondsThat's why it's using an internal key to validate because there's no out here. So yes, that's the only thing. I kind of
4:03:244 hours, 3 minutes, 24 secondsdon't like having such a generic name with such an important status here, but you know, for tutorial purposes, this is
4:03:334 hours, 3 minutes, 33 secondsfine right now. You can, of course, change the name later to something more specific.
4:03:384 hours, 3 minutes, 38 secondsAll right, that's all for the system mutations that we have to do. Now, let's go ahead and focus on building the API
4:03:464 hours, 3 minutes, 46 secondsroutes. So, we're going to start by a import route. Let's go ahead and inside of app API and let's create a new folder
4:03:554 hours, 3 minutes, 55 secondscalled GitHub inside import and inside a file route. DS. Oh, I made
4:04:044 hours, 4 minutes, 4 secondsa mistake. As you can see, route.ts is not inside of the import folder. That means in Nex.js, this will not register
4:04:134 hours, 4 minutes, 13 secondsas a route. So, I have to drag it inside to make sure it's registered.
4:04:184 hours, 4 minutes, 18 secondsThis might trigger some cache invalidation. You can just save this file, close this file, and then close
4:04:244 hours, 4 minutes, 24 secondsthe entire next folder so it doesn't uh distract you. Let's go back inside of route.ds.
4:04:334 hours, 4 minutes, 33 secondsLet's start by importing zod next response from next server out and clerk client from clerk next.js server. In
4:04:414 hours, 4 minutes, 41 secondshere, I'm going to import convex from convex client and ingest from ingest client. Then I'm going to import API
4:04:494 hours, 4 minutes, 49 secondsfrom convex generated API. I'm going to define the request schema for this API endpoint which is just a simple URL. And
4:04:584 hours, 4 minutes, 58 secondsthen I'm going to create just a simple function which will help us parse GitHub URL. Now you can decide whether you want
4:05:064 hours, 5 minutes, 6 secondsto do this or not. So function parse GitHub URL accepts a URL string and it
4:05:134 hours, 5 minutes, 13 secondswill check if URL matches this specific regx. I don't expect you to write this out. If you want to, of course, you can,
4:05:214 hours, 5 minutes, 21 secondsbut you can also just visit the source code and copy this from this exact location
4:05:274 hours, 5 minutes, 27 secondsapp folder API GitHub import route. Uh, and again, this isn't anything important, right? It's just something to
4:05:354 hours, 5 minutes, 35 secondstell to the back to the user on the front end like, "Hey, uh, I think you gave us the wrong URL." But then again,
4:05:434 hours, 5 minutes, 43 secondsURLs might change in the future. So, I'm not sure how good or bad this is. I'm basically going to show you that uh you
4:05:514 hours, 5 minutes, 51 secondscan do it both with or without this function. So, don't worry about this function too much, right? You can completely choose to skip using this function.
4:06:004 hours, 6 minutesNow, we're going to actually export the post request. So what I'm going to start is by using await out which we've
4:06:084 hours, 6 minutes, 8 secondsimported from clerk and check if we have a user ID. In case the user ID is missing, I'm just going to throw a next response unauthorized.
4:06:184 hours, 6 minutes, 18 secondsThen I'm going to go ahead and do an await request.json and I'm going to do request schema.parse
4:06:254 hours, 6 minutes, 25 secondson the body. And here I'm going to have parsed URL.
4:06:314 hours, 6 minutes, 31 secondsThen what I can do here is I can extract from the URL using the function parse GitHub URL the owner and the repository.
4:06:454 hours, 6 minutes, 45 secondsRight? So basically if I go ahead and do github.com Antonio my profile name basically
4:06:544 hours, 6 minutes, 54 secondsand then the name of the repository like this this function parse GitHub URL
4:07:014 hours, 7 minutes, 1 secondwould extract that into an object owner
4:07:084 hours, 7 minutes, 8 secondsthis and repo this. Right? So you don't really need
4:07:164 hours, 7 minutes, 16 secondsthat but you know it is useful especially since I'm don't think the
4:07:244 hours, 7 minutes, 24 secondsURLs are going to change like tomorrow but again be careful with this because URLs sure can change in the future but
4:07:314 hours, 7 minutes, 31 secondsat this point there's so many GitHub URLs that they are going to have to maintain them or backlink them or something right so this for example is a
4:07:404 hours, 7 minutes, 40 secondscompletely valid URL Right. And what we have to do now is we have to obtain our GitHub token. So we're going to start by
4:07:494 hours, 7 minutes, 49 secondscreating the clerk client and then we're going to get all the tokens we have for this user. So await client do users get
4:07:574 hours, 7 minutes, 57 secondsuser oout access token and simply pass in the user ID and then for which provider for GitHub. I think this is
4:08:064 hours, 8 minutes, 6 secondsstrictly typed. Yes, you can select exactly for which one.
4:08:114 hours, 8 minutes, 11 secondsand then very simply choose the first one tokens data first in the array token.
4:08:194 hours, 8 minutes, 19 secondsIn case we are not able to obtain the GitHub token, unfortunately we can't even begin uh fetching a URL. So let's go ahead and throw nextresponse.json.
4:08:304 hours, 8 minutes, 30 secondsGitHub is not connected. Please reconnect your GitHub account. At least that's what we assume the problem is. Now we have to set up our internal key.
4:08:394 hours, 8 minutes, 39 secondsSo that's going to be process environment. Oops.
4:08:444 hours, 8 minutes, 44 secondsAnd let me go ahead and check. I think I've done this a few times before. I have Polaris convex internal key. So I'm just going to copy that. Paste it here.
4:08:554 hours, 8 minutes, 55 secondsAnd again, if we don't have the internal key for whatever reason, let's throw 500. Basically a server configuration
4:09:024 hours, 9 minutes, 2 secondserror. And now that we have the internal key, we can create a new project from here. So I told you this will happen
4:09:094 hours, 9 minutes, 9 secondsfrom the inest background job but actually it will happen here in the route. My apologies. So we're going to
4:09:164 hours, 9 minutes, 16 secondscall await convex.mutation api.system.create project which is exactly what we've created last I believe. And we have
4:09:254 hours, 9 minutes, 25 secondsinternal key the name of the repository which we can just uh we can call the
4:09:334 hours, 9 minutes, 33 secondsproject exactly what the repository is called. For example, here the repository is called cursor dev. So instead of, you
4:09:414 hours, 9 minutes, 41 secondsknow, anonymizing the name or randomizing the name like we do when we create a new project from the projects page, we can just reuse the name here,
4:09:484 hours, 9 minutes, 48 secondsright? Why not? And we match the owner ID to be the currently logged in user ID. Great.
4:09:564 hours, 9 minutes, 56 secondsAnd then what we're going to do is we're going to trigger a background job which is going to start synchronizing from
4:10:044 hours, 10 minutes, 4 secondsGitHub to projects. So awaiting injust send name. This will be the name of the
4:10:114 hours, 10 minutes, 11 secondsevent which we are going to create and the data will be the owner, the repository, the project ID and the GitHub token.
4:10:224 hours, 10 minutes, 22 secondsAnd then finally, let's go ahead and just return next response.json success true and the project ID.
4:10:314 hours, 10 minutes, 31 secondsAnd now while we are developing API routes, I also want to develop the export
4:10:384 hours, 10 minutes, 38 secondsAPI route. So let's go ahead and create another route.ts inside. So this one is app folder API GitHub export route.ts.
4:10:504 hours, 10 minutes, 50 secondsAgain, we're going to start with zod next response out and clerk client inest
4:10:564 hours, 10 minutes, 56 secondsfrom ingest client and ID from convex generated data model. We're then going
4:11:044 hours, 11 minutes, 4 secondsto develop the request schema for this API project ID repository name. So this is now in reverse. This is for creating
4:11:134 hours, 11 minutes, 13 secondsa repository on GitHub. So we're kind of going to have some limits here. If you want to create a new repository, the name needs to be a minimum of one
4:11:214 hours, 11 minutes, 21 secondscharacter and a maximum of 100. The visibility can either be public or private, and we're going to default it to private. The description can either
4:11:314 hours, 11 minutes, 31 secondscan be maximum of 350 characters, and it's optional.
4:11:364 hours, 11 minutes, 36 secondsNow, let's go ahead in here and let's start by obtaining the user ID.
4:11:464 hours, 11 minutes, 46 secondsLet's check if we user ID is missing and throw 401. Then let's go ahead and get the body.
4:11:554 hours, 11 minutes, 55 secondsLet's go ahead and parse project ID, repository name, visibility, and description from the body. So we're using request schema.pars body.
4:12:074 hours, 12 minutes, 7 secondsThen let's go ahead and initiate the clerk client. Let's go ahead and get all the tokens we have for GitHub. So the
4:12:164 hours, 12 minutes, 16 secondssame thing we just did in the previous route and let's get the GitHub token from the first one in the array. In case the GitHub token is not connected, let's
4:12:244 hours, 12 minutes, 24 secondsgo ahead and throw an error. Let's prepare by copying the internal key from here.
4:12:314 hours, 12 minutes, 31 secondsAdding it here. Then doing a check if the internal key is missing and throw 500.
4:12:394 hours, 12 minutes, 39 secondsSo since we just moved between these two, just make sure you are developing the export one. Don't accidentally override your import one. Great. And
4:12:474 hours, 12 minutes, 47 secondswhat we have to do now is just send another background job event. So this event will be awaiting injust send
4:12:564 hours, 12 minutes, 56 secondsGitHub export.reo with data project ID project ID as ID
4:13:034 hours, 13 minutes, 3 secondsprojects repository name visibility description GitHub token and internal key. We can see we can decide if we want
4:13:124 hours, 13 minutes, 12 secondsto pass the internal key as a prop since we can just easily u check it there but in here it's kind
4:13:194 hours, 13 minutes, 19 secondsof already checked so we don't have to do double checks but we'll see and I don't think we need to do any type casting here actually. Yeah. Okay. And
4:13:294 hours, 13 minutes, 29 secondsthen we could just go ahead and return something like next response.json success true event ID event ID is zero.
4:13:374 hours, 13 minutes, 37 secondsSo this event ID is not important. For example, here I don't think we even threw it. So you can decide if you want
4:13:454 hours, 13 minutes, 45 secondsto be specific so that your network logs show the event ID, you can copy.
4:13:524 hours, 13 minutes, 52 secondsSo the same appears.
4:13:564 hours, 13 minutes, 56 secondsOkay. So the same appears in the import one.
4:14:004 hours, 14 minutesAnd let me just go ahead and check if there are any more things that are not missing. So success through project ID.
4:14:074 hours, 14 minutes, 7 secondsI think in here we're not passing project ID. Great. So I just want to make them the same since they are so similar already.
4:14:154 hours, 14 minutes, 15 secondsOkay. So now let's go ahead and implement a cancel route.
4:14:234 hours, 14 minutes, 23 secondsSo far we've implemented the export and import. Now let's give the user ability to cancel. So another route.ts.
4:14:334 hours, 14 minutes, 33 secondsAnd at this point, let's just copy one of the other ones. So, I'm going to copy the export one and I'm going to paste it
4:14:414 hours, 14 minutes, 41 secondshere. Actually, I'm going to copy import since it's more similar.
4:14:464 hours, 14 minutes, 46 secondsSo, copy the import route. Go inside of cancel and paste it here. So, we need
4:14:534 hours, 14 minutes, 53 secondszod next response. We're not going to need clerk client. You can remove that.
4:14:584 hours, 14 minutes, 58 secondssuggest out convex ingest API and we're also going to need
4:15:064 hours, 15 minutes, 6 secondsID from generated data model. We're not going to need the function parse GitHub URL. The request schema will not accept the URL but a project ID.
4:15:194 hours, 15 minutes, 19 secondsThe out check will be exactly the same. The parsing will parse for project ID.
4:15:284 hours, 15 minutes, 28 secondsWe can skip the entire check here and go immediately down to the internal key.
4:15:354 hours, 15 minutes, 35 secondsAnd let me just see what's the problem.
4:15:384 hours, 15 minutes, 38 secondsCannot redeclare block scope variable project ID.
4:15:444 hours, 15 minutes, 44 secondsHuh, that's odd. Okay. Oh, because it appears later. No worries. So, we were here,
4:15:534 hours, 15 minutes, 53 secondsright? We check if we don't have the project the internal key and we're not
4:15:594 hours, 15 minutes, 59 secondsgoing to be calling any convex mutations I mean here but we are going to send an event.
4:16:104 hours, 16 minutes, 10 secondsSo let's just go ahead and send an event called GitHub export
4:16:174 hours, 16 minutes, 17 secondsdot cancel and the data is just going to be project ID.
4:16:264 hours, 16 minutes, 26 secondsSo basically we are going to give the user ability to cancel an export. Right?
4:16:334 hours, 16 minutes, 33 secondsSo if the user attempts to export it, I'm not sure how long that's going to take, right? You can it can have
4:16:424 hours, 16 minutes, 42 secondsthousands of files, right? So for them not to be in a forever stuck state, we're going to give them the option to
4:16:504 hours, 16 minutes, 50 secondscancel. Uh now we could develop the same for import
4:16:574 hours, 16 minutes, 57 secondsbut uh the user can just delete the project because you know uh we we want
4:17:044 hours, 17 minutes, 4 secondsto give the user option to cancel when they are exporting since that is a project they have developed in Polaris.
4:17:124 hours, 17 minutes, 12 secondsSo we need them we need to give them a way to get out of this situation.
4:17:164 hours, 17 minutes, 16 secondsWhereas with import it's a brand new project. nothing of value will be lost if they just delete the project. Right?
4:17:234 hours, 17 minutes, 23 secondsUh but of course you can just develop the same uh once you see how we're going to do it. All right. So once we send the
4:17:324 hours, 17 minutes, 32 secondscancel event we also have to update the status to cancel. So this is where we
4:17:404 hours, 17 minutes, 40 secondsare going to do the mutation. So await convex mutation API system update export
4:17:464 hours, 17 minutes, 46 secondsstatus to cancel with the internal key and with the project and let's go ahead
4:17:544 hours, 17 minutes, 54 secondsand just let's just return success true.
4:18:004 hours, 18 minutesIf you want to you can do the event again simply so we are consistent in all three there. Okay. So that's the cancel route.
4:18:124 hours, 18 minutes, 12 secondsAnd then let's go ahead and copy the cancel route and do the last route here which will be reset.
4:18:224 hours, 18 minutes, 22 secondsIn reset route DS, we're going to need zod next response out convex not inest
4:18:324 hours, 18 minutes, 32 secondsAPI and ID. The request schema is the same. OL check is the same. Parsing is
4:18:394 hours, 18 minutes, 39 secondsthe same, internal key check is the same. We're not going to be triggering any events and we are very simply going
4:18:484 hours, 18 minutes, 48 secondsto clear export status. So this will again call update export status and
4:18:564 hours, 18 minutes, 56 secondswe're just going to reset everything. So status will be undefined and repo URL will be undefined.
4:19:054 hours, 19 minutes, 5 secondsSo what exactly is this used for? Well, the difference between cancel and reset
4:19:114 hours, 19 minutes, 11 secondsis that cancel is simply used to allow the user to stop the export. The reset
4:19:184 hours, 19 minutes, 18 secondsis used if the user wants to once again export their Polaris project but maybe
4:19:264 hours, 19 minutes, 26 secondsto another repository. Right? So there is no synchronization between GitHub and
4:19:334 hours, 19 minutes, 33 secondsPolaris. There is only manual synchronization. It's not going to be an ongoing thing, right? They are two
4:19:404 hours, 19 minutes, 40 secondsdifferent separate entities. So that's why we allow user to also just uh reset entirely if they want to export to
4:19:484 hours, 19 minutes, 48 secondsGitHub in five different repositories like sure do it. All right. Now let's go ahead and start building uh those in
4:19:554 hours, 19 minutes, 55 secondsjustest functions. So I'm going to go ahead inside of source inside of features projects and in here
4:20:054 hours, 20 minutes, 5 secondsI'm going to create a new folder ingest and inside of that I will create import github repository.ts DS.
4:20:164 hours, 20 minutes, 16 secondsAnd while we're here, I think it might be a good idea to just run npx convex dev simply to synchronize all of those
4:20:244 hours, 20 minutes, 24 secondsfunctions and simply to catch if there is an error in any of them. In my case, there was no error. So, convex functions
4:20:314 hours, 20 minutes, 31 secondsare ready. If you're seeing an error, it might be a good idea to go back and fix them. So, all of the functions which we've written today is inside of system.ds.
4:20:414 hours, 20 minutes, 41 secondsSo, it has to be somewhere here. You can see my green line here. Meaning all the newly added ones are these. The cleanup,
4:20:484 hours, 20 minutes, 48 secondsthe create binary file, the update import status, update export status, get project files with URLs, and create
4:20:564 hours, 20 minutes, 56 secondsproject. So if you have any errors, they're going to be here. All right. Now, let's focus on the inest function.
4:21:044 hours, 21 minutes, 4 secondsWe're going to import ky. We're going to import our newly installed octoit. Same with the binary file. and non-retriable error from ingest.
4:21:164 hours, 21 minutes, 16 secondsWe're going to import the convex client, the ingest client and API and ID from convex generated.
4:21:254 hours, 21 minutes, 25 secondsLet's create an interface for this event. So what do we expect to receive?
4:21:304 hours, 21 minutes, 30 secondsSo when we are importing we need the owner we need the repository we need the project ID to which project we're going
4:21:394 hours, 21 minutes, 39 secondsto synchronize this entire repository and finally we need the logged in users GitHub token. So once we have those
4:21:484 hours, 21 minutes, 48 secondsthings we can go ahead and create an ingest function.
4:21:544 hours, 21 minutes, 54 secondsLet's go ahead and start with some configuration. The ID will be import GitHub repo.
4:22:024 hours, 22 minutes, 2 secondsAnd let's first do on failure. So what should happen when this fails? We have an event and step. And the first thing
4:22:114 hours, 22 minutes, 11 secondswe're going to do is just check if we have the internal key. So I keep forgetting the name of my internal key
4:22:184 hours, 22 minutes, 18 secondshere. Polaris convex internal key. So const internal key process. uh event
4:22:274 hours, 22 minutes, 27 secondsenvironment polaris convex internal key if there is no internal key let's just return
4:22:364 hours, 22 minutes, 36 secondsnow what we're going to do is we're going to import the project ID for which importing just failed to so you can
4:22:444 hours, 22 minutes, 44 secondsextract project ID from event dot data doevent dot data usually uh it's just
4:22:524 hours, 22 minutes, 52 secondsevent dot data but when working within on failure this is how you get the project ID and in here I'm casting it as
4:22:594 hours, 22 minutes, 59 secondsthis event simply so we have the ID of convex here and then what we're going to
4:23:064 hours, 23 minutes, 6 secondsdo is run a step called set failed status so at this point importing has
4:23:144 hours, 23 minutes, 14 secondsfailed so what I'm going to do is I'm going to await convex domutation APIs
4:23:204 hours, 23 minutes, 20 secondssystem update import status pass in the internal the relevant project ID and set the
4:23:294 hours, 23 minutes, 29 secondsstatus to failed. So whatever goes wrong in this background job after several retries of course will simply trigger
4:23:364 hours, 23 minutes, 36 secondsthis on failure which is going to call the system mutation to indicate to the user hey we failed importing this repository so they can try again. Great.
4:23:494 hours, 23 minutes, 49 secondsSo now that we have that, let's go ahead and define an event name which is GitHub/import.reo.
4:23:594 hours, 23 minutes, 59 secondsWhat I would suggest you do is you do a search throughout your repository here.
4:24:034 hours, 24 minutes, 3 secondsYou can use command shift F or control shift F while it's highlighted. So it opens like this. And just double check that inside of your source app API
4:24:124 hours, 24 minutes, 12 secondsGitHub import, you have the exact same name for the event that you trigger. So, github_/imp import.reo. It should be a
4:24:204 hours, 24 minutes, 20 secondsone by one match here. Great. And now we build the actual background job. Of course, it's going to be asynchronous.
4:24:304 hours, 24 minutes, 30 secondsAnd let's start by simply extracting the data we need. So, owner repo project ID,
4:24:374 hours, 24 minutes, 37 secondsGitHub token, and event data as import GitHub repo event.
4:24:434 hours, 24 minutes, 43 secondsThen I'm just going to go ahead and copy the internal key situation here. I'm going to paste it. I'm just going to
4:24:514 hours, 24 minutes, 51 secondsslightly modify it by throwing a nonretable error which will simply say Polaris convex
4:25:004 hours, 25 minutesinternal key is not configured because if that's not configured the background jobs uh sorry it's throw new nonabular.
4:25:094 hours, 25 minutes, 9 secondsThe background jobs cannot do any convex mutations.
4:25:134 hours, 25 minutes, 13 secondsNow let's go ahead and establish octokit by passing the out property as GitHub
4:25:204 hours, 25 minutes, 20 secondstoken which we extract from clerk which we now have with the proper scope because we configured it at the start of
4:25:274 hours, 25 minutes, 27 secondsthis chapter. Great. So now we're going to use the first mutation we've created today. We're going to clean up any
4:25:354 hours, 25 minutes, 35 secondsexisting files in the project whenever this import background job happens. So let's go ahead and run a step called cleanup project which will call await
4:25:444 hours, 25 minutes, 44 secondsconvex.mmutation API system cleanup and then it's just going to pass the internal key and the project ID because that's all we need.
4:25:554 hours, 25 minutes, 55 secondsOnce it's been cleaned up let's go ahead and fetch the entire repository tree.
4:26:034 hours, 26 minutes, 3 secondsSo a step called fetch repo tree will have a try and catch method inside.
4:26:114 hours, 26 minutes, 11 secondsIn the try method, we're simply going to go ahead and extract the data from await octokit.rest.git.get
4:26:214 hours, 26 minutes, 21 secondsGet tree using the owner the repository
4:26:274 hours, 26 minutes, 27 secondsthree sh h a main and recursive one
4:26:344 hours, 26 minutes, 34 secondsthe one is not a integer it's a string like so and let me just see
4:26:434 hours, 26 minutes, 43 secondsuh the problem here oh it's uh my apologies uh tree
4:26:514 hours, 26 minutes, 51 secondsS ha uh this can be main or it can be master depending if it's an older one.
4:26:584 hours, 26 minutes, 58 secondsWell, I mean technically you could also uh add an input so the user enters exactly which branch they want to clone
4:27:074 hours, 27 minutes, 7 secondsbut what I'm doing right now for tutorial purposes is just fetching the main branch. So I'm just going to either try with main or I'm going to fall back
4:27:154 hours, 27 minutes, 15 secondsto master. So let's return data. And then we're simply going to do the exact
4:27:224 hours, 27 minutes, 22 secondssame thing in the catch by trying with master branch because some older projects might use master.
4:27:324 hours, 27 minutes, 32 secondsSo we're just trying to fetch the tree now. All right, that is that step done.
4:27:404 hours, 27 minutes, 40 secondsWhat we have to do now is we have to sort the folders by depth. So parents
4:27:484 hours, 27 minutes, 48 secondsare created before their children because we first need to create folders before we can start creating the rest of
4:27:554 hours, 27 minutes, 55 secondsthe files. So for example uh the input we're going to receive the input being
4:28:014 hours, 28 minutes, 1 secondthis right the data here is basically this kind of structure path source
4:28:084 hours, 28 minutes, 8 secondsforward/components path source path source components UI
4:28:144 hours, 28 minutes, 14 secondsand the output that we need to create is path source first path source components
4:28:224 hours, 28 minutes, 22 secondsnext and source components UI last so we can't basically allow source components to be created because we don't have
4:28:304 hours, 28 minutes, 30 secondstheir parent yet. Right? This is all all coming back to our schema structure and our parent ID reference. So let's go
4:28:394 hours, 28 minutes, 39 secondsahead and start developing this folders will be tree dot tree dot filter
4:28:474 hours, 28 minutes, 47 secondsget the item check if item.type type is tree and if we have item path then let's
4:28:574 hours, 28 minutes, 57 secondssort check if a depth has a.path
4:29:054 hours, 29 minutes, 5 secondsif it has let's do apath dotsplit forward slash dotlength or zero.
4:29:174 hours, 29 minutes, 17 secondsThen let's go ahead and duplicate this.
4:29:194 hours, 29 minutes, 19 secondsChange this to B depth and change the variable to use the B variable. B.path B.Path.split.
4:29:304 hours, 29 minutes, 30 secondsAnd let's return A depth minus B depth, which will basically sort them as we've defined above.
4:29:404 hours, 29 minutes, 40 secondsGreat.
4:29:414 hours, 29 minutes, 41 secondsNow that we have the folders, let's go ahead and do the following.
4:29:464 hours, 29 minutes, 46 secondsWe're going to return the folder map from the step so it can be used in subsequent steps. This is inest
4:29:544 hours, 29 minutes, 54 secondsspecific. So inest serializes step results. So we must use a plane object instead of map.
4:30:044 hours, 30 minutes, 4 secondsSo what I'm going to do now is try to define a folder ID map within a step. So
4:30:124 hours, 30 minutes, 12 secondsawait step.run run create folders async
4:30:194 hours, 30 minutes, 19 secondsand now I will create a map but just by using a normal object. So map will be a
4:30:264 hours, 30 minutes, 26 secondstype of object which accepts a key and on the other end it's an id of the file.
4:30:344 hours, 30 minutes, 34 secondsNow we're going to go ahead and first go through the folders. So for const folder of folders
4:30:414 hours, 30 minutes, 41 secondsif folder path is missing let's just continue forward there's nothing we can do here but otherwise let's go ahead and
4:30:494 hours, 30 minutes, 49 secondsprepare a few things path parts which are folder.path.split.
4:30:574 hours, 30 minutes, 57 secondsSo basically when we have things like this it will be split into source and components.
4:31:054 hours, 31 minutes, 5 secondsThe name will basically be the first one in the array. So we pop and the parent path which will be the rest. So we are separating the name basically.
4:31:174 hours, 31 minutes, 17 secondsAnd the last one we need is to find the parent ID. So the parent ID will check if we have parent path and it will look
4:31:244 hours, 31 minutes, 24 secondsthrough the map and check if it's there or mark it as undefined.
4:31:324 hours, 31 minutes, 32 secondsAnd then let's go ahead and get the folder ID by creating it. Await convex
4:31:404 hours, 31 minutes, 40 secondsdot mutation api.system dot create folder.
4:31:464 hours, 31 minutes, 46 secondsPass in the internal key project ID name and parent ID. And then we're going to
4:31:544 hours, 31 minutes, 54 secondsadd to our map for that folder path the equivalent folder ID we have created in
4:32:024 hours, 32 minutes, 2 secondsour database. So then in the next iteration if that repeats we will find
4:32:094 hours, 32 minutes, 9 secondsthat because of this we will now find that parent path in the map. So we know okay the parent has already been
4:32:184 hours, 32 minutes, 18 secondscreated. We can now start importing the children. Right? So that's kind of the tricky part here is because uh octokit
4:32:264 hours, 32 minutes, 26 secondsjust returns us a bunch of files and structures but we have to create them in a way that we create parents first and
4:32:344 hours, 32 minutes, 34 secondsthen their children. So that's why we're doing this somewhat complicated logic.
4:32:404 hours, 32 minutes, 40 secondsAll right. And of course return map.
4:32:464 hours, 32 minutes, 46 secondsThen let's go ahead and solve the uh binary files. So these are a bit more
4:32:544 hours, 32 minutes, 54 secondscomplicated. So let's start by getting all files or blobs from a tree.
4:33:024 hours, 33 minutes, 2 secondsAll files tree.
4:33:054 hours, 33 minutes, 5 secondsCheck if item type is blob and we have item.path and item.sha.
4:33:124 hours, 33 minutes, 12 secondsThen let's go ahead and create the files. So, a step called create files.
4:33:204 hours, 33 minutes, 20 secondsWe're going to go ahead and go through each files in our all files filter here.
4:33:274 hours, 33 minutes, 27 secondsIn case file path or filesh is missing, we're just going to continue. And then we're going to open a try and catch block here.
4:33:374 hours, 33 minutes, 37 secondsLet me go ahead and fix the indentation.
4:33:394 hours, 33 minutes, 39 secondsOkay. Inside of try, we're going to go ahead and get the blob using the file sha and owner and repo. Uh, I'm not sure
4:33:494 hours, 33 minutes, 49 secondshow to pronounce this. So when you hear me say sha, this is what I mean. All right. So how do we get the blob? By
4:33:564 hours, 33 minutes, 56 secondscalling octokit rest get blob function which needs the owner repository and the exact file sha. And that will basically give us back the blob.
4:34:084 hours, 34 minutes, 8 secondsOnce we have the blob, we can go ahead and create a buffer using buffer from and com and and using the blob content with base 64.
4:34:174 hours, 34 minutes, 17 secondsAnd then once we have the buffer, we can call our is binary function is binary file and pass in the buffer is binary
4:34:264 hours, 34 minutes, 26 secondsfrom is binary file. This will allow us to decide how we store this file. Now we also have to define if this is inside of
4:34:344 hours, 34 minutes, 34 secondssome folder. So we have to check for path parts using file.path.split.
4:34:404 hours, 34 minutes, 40 secondsLet's get the name of the file using pop. Let's go ahead and get the parent path using parts.join.
4:34:494 hours, 34 minutes, 49 secondsAnd then let's check if we have the parent ID. So very similar to what we did before.
4:34:564 hours, 34 minutes, 56 secondsIf we have parent path, check if we have stored it inside of a folder ID map. Otherwise, mark it as undefined.
4:35:054 hours, 35 minutes, 5 secondsSo this folder ID map I believe is returned from here right.
4:35:134 hours, 35 minutes, 13 secondsSo now let's check if a file is binary we have to upload it. So let's first get
4:35:214 hours, 35 minutes, 21 secondsthe upload URL. We can do that using our system mutation. So upload URL is obtained with await convex mutation API
4:35:294 hours, 35 minutes, 29 secondssystem generate upload URL and it just needs the internal key.
4:35:354 hours, 35 minutes, 35 secondsThen we can go ahead and fetch that URL.
4:35:404 hours, 35 minutes, 40 secondsSo we will get back storage ID which we can store into the database by making a
4:35:474 hours, 35 minutes, 47 secondspost request. So let's go ahead and use KY for that. to upload URL which we've just obtained.
4:35:554 hours, 35 minutes, 55 secondsSo this is a signed upload URL from convex. So we can safely upload here.
4:36:024 hours, 36 minutes, 2 secondsIt needs to accept specific headers. So these are the ones it needs. I'm going to show you content type application
4:36:094 hours, 36 minutes, 9 secondsocted stream and the body will be the buffer. So we are now uploading a binary file and we are
4:36:194 hours, 36 minutes, 19 secondsreturning back in JSON format storage ID which will be a type of ID
4:36:264 hours, 36 minutes, 26 secondsunderscore storage.
4:36:304 hours, 36 minutes, 30 secondsAnd once we have the storage ID, we can go ahead and do await convex mutation
4:36:374 hours, 36 minutes, 37 secondsAPI system create binary file. Pass in the internal key, the project ID, name,
4:36:474 hours, 36 minutes, 47 secondsstorage ID, and parent ID. So this function was already created in the beginning. We are now using it through a
4:36:544 hours, 36 minutes, 54 secondsbackground job to actually create that binary file after it's been uploaded to Convex through a secure background job using a secure uh signed upload URL.
4:37:084 hours, 37 minutes, 8 secondsUh great. So that's the case for if is binary. But if it is not binary, in that
4:37:144 hours, 37 minutes, 14 secondscase we're simply going to uh convert the buffer to string using UTF8.
4:37:224 hours, 37 minutes, 22 secondsAnd then we're just going to call a normal API system create file with
4:37:304 hours, 37 minutes, 30 secondsinternal key project ID name content and parent ID.
4:37:364 hours, 37 minutes, 36 secondsAnd in the catch here, we're going to go ahead and do console error fail to import file file.path.
4:37:434 hours, 37 minutes, 43 secondsGreat.
4:37:454 hours, 37 minutes, 45 secondsAnd then let's go ahead and do one more step. An easy one. Set completed status.
4:37:524 hours, 37 minutes, 52 secondsIt will run await convex.mmutation API system update import status. At this point, we have already finished
4:38:004 hours, 38 minutesimporting. We have finished uploading binary files. We finished creating normal files. We created parents first
4:38:084 hours, 38 minutes, 8 secondsand assigned everything properly. So at this point, we can just call our system update import status mutation with the
4:38:154 hours, 38 minutes, 15 secondsstatus of completed. Great. And let's go ahead and return it a very simple
4:38:244 hours, 38 minutes, 24 secondssuccess true and project ID. Great. So that is our import GitHub repo. Uh I will admit it was a bit complicated.
4:38:344 hours, 38 minutes, 34 secondsEven I was getting lost a bit here. So if we made some mistake, we will uh test that out once we implement the UI. So we
4:38:434 hours, 38 minutes, 43 secondscan actually fire this. But I think it's mostly okay. I think mostly we did everything right. All right. So the next
4:38:504 hours, 38 minutes, 50 secondsthing we have to do is create a very similar background job but for exporting a GitHub repository.
4:38:594 hours, 38 minutes, 59 secondsThe export inest background job will be similar but not too similar. So I'm just going to start a completely blank file.
4:39:094 hours, 39 minutes, 9 secondsSo inside of inest folder here I'm going to create export to GitHub. export to github.ts
4:39:184 hours, 39 minutes, 18 secondsand the imports are quite similar. So those are KY, octokit, non retriable
4:39:244 hours, 39 minutes, 24 secondserror, convex, injest, API and ID. Now let's go ahead and add the interface
4:39:314 hours, 39 minutes, 31 secondsexport to GitHub event. Export to GitHub event will have a project ID, repo name,
4:39:394 hours, 39 minutes, 39 secondsvisibility public or private, optional description, GitHub token, and I don't think it makes sense to pass the internal key. So let's remove that.
4:39:514 hours, 39 minutes, 51 secondsThen let's create a specific type called file with URL.
4:39:584 hours, 39 minutes, 58 secondsIt has an underscore ID of ID files underscore creation time which is a number project ID optional parent ID
4:40:074 hours, 40 minutes, 7 secondsname type file or folder content storage ID and storage URL. Now
4:40:154 hours, 40 minutes, 15 secondsthat I look at it I think we can do this in a better way. I think we can do
4:40:224 hours, 40 minutes, 22 secondslet me just see this will be a type of I mean I'm not sure let's see type file
4:40:294 hours, 40 minutes, 29 secondswith URL to a type of doc from data model so let me show you that import
4:40:374 hours, 40 minutes, 37 secondsright here doc from generated data model and we import uh we use files so right
4:40:464 hours, 40 minutes, 46 secondsnow I think they would have like almost 99% match. The only thing we want to extend with is the storage URL.
4:40:564 hours, 40 minutes, 56 secondsI think these are now exactly the same.
4:41:004 hours, 41 minutesI think I think this is a much more elegant way of defining that. Okay.
4:41:084 hours, 41 minutes, 8 secondsAnd now let's go ahead and create the ingest function. Export to GitHub. Let's start with the ID. export to GitHub.
4:41:194 hours, 41 minutes, 19 secondsLet's define the cancel on event.
4:41:244 hours, 41 minutes, 24 secondsThe cancel on event will listen to GitHub forward slashexport.
4:41:354 hours, 41 minutes, 35 secondsAnd okay, so we cannot use match. Let me see what is the name of the new one. I mean we can use match but it's deprecated. I want to teach you that. Uh
4:41:444 hours, 41 minutes, 44 secondsso let's see. We have to use if and I think I have to check data project
4:41:534 hours, 41 minutes, 53 secondsID matches data project ID but not exactly like this. So let me check if.
4:42:014 hours, 42 minutes, 1 secondAll right. So we have one example in process message.ds.
4:42:064 hours, 42 minutes, 6 secondsSo let's use it to learn. We have event data and we have async data. So that's what we have to check for. If event dot
4:42:154 hours, 42 minutes, 15 secondsdata is equal to a project ID and async data is equal to a project ID and they
4:42:224 hours, 42 minutes, 22 secondsare using double these. Okay, I think we've done this correctly. All right, besides cancel on, we're also going to
4:42:314 hours, 42 minutes, 31 secondshave on failure. Now on failure is very similar to the on failure in the import one. So let's go ahead and revisit it.
4:42:414 hours, 42 minutes, 41 secondsI'm going to scroll up here to find the on failure. Where is it?
4:42:504 hours, 42 minutes, 50 secondsHere it is. We're going to start by checking if we have the internal key.
4:42:574 hours, 42 minutes, 57 secondsAnd if we don't have it, we just do an early return. And now let's go ahead and let's dstructure the project ID
4:43:084 hours, 43 minutes, 8 secondsfrom event dot data doevent dot data and let's cast it as export to GitHub event.
4:43:184 hours, 43 minutes, 18 secondsAll right. And then what I'm going to do is call a function very similar to this
4:43:274 hours, 43 minutes, 27 secondsone. So an entire step called set failed status set failed status
4:43:354 hours, 43 minutes, 35 secondscall convex domutation instead of update import status is going to be update export status and I believe the queries
4:43:444 hours, 43 minutes, 44 secondsare exactly the same the internal key the project ID and the status so yeah I
4:43:524 hours, 43 minutes, 52 secondsthink this works just fine now let's go ahead and let's define the event name. So the event name will be GitHub export.reo.
4:44:044 hours, 44 minutes, 4 secondsAgain, I recommend searching through your project and confirming that this is the event that you trigger inside of app folder API GitHub export route.ds.
4:44:154 hours, 44 minutes, 15 secondsSo GitHub export.reo, it should match exactly and it should also uh match this one. So check this
4:44:244 hours, 44 minutes, 24 secondsgithub export.ancel. search for that too inside of your source app API GitHub
4:44:314 hours, 44 minutes, 31 secondscancel. You should have that event here as well. Great. So you don't have any misspellings.
4:44:394 hours, 44 minutes, 39 secondsAnd now let's go ahead and actually build the function. It's going to be an asynchronous function which accepts
4:44:464 hours, 44 minutes, 46 secondsevent and step. Let's go ahead and start by extracting everything we need. So
4:44:544 hours, 44 minutes, 54 secondsproject ID, repo name, visibility, description, and GitHub token. We don't need the internal key. Then I'm going to
4:45:024 hours, 45 minutes, 2 secondscopy from import a check of the internal key once again and a throw of a non-retriable error. And I'm just going
4:45:114 hours, 45 minutes, 11 secondsto paste it here. So we're going to attempt to get the internal key. If it's missing, simply throw a non-retriable
4:45:194 hours, 45 minutes, 19 secondserror. Great. Let's start by running a step which will change this project's status to exporting.
4:45:284 hours, 45 minutes, 28 secondsSo set exporting status. We'll call convex mutation API system update export
4:45:344 hours, 45 minutes, 34 secondsstatus internal key project id status exporting.
4:45:414 hours, 45 minutes, 41 secondsThen just as we did in the import background job, we're going to initiate the octokit using out and github token which we obtain.
4:45:524 hours, 45 minutes, 52 secondsLet's go ahead and get the authenticated user using the octokit.
4:45:574 hours, 45 minutes, 57 secondsSo we can uh run a step get github user and return
4:46:044 hours, 46 minutes, 4 secondsawait octokit rest users get authenticated. This will basically return whatever user has passed the
4:46:134 hours, 46 minutes, 13 secondsGitHub token to. And let's go ahead and alias it as user.
4:46:194 hours, 46 minutes, 19 secondsAnd now let's start by creating a new repository without auto in it. So we
4:46:264 hours, 46 minutes, 26 secondshave an initial commit. So this step will be called create repo.
4:46:334 hours, 46 minutes, 33 secondsAnd in here what we're going to do is return await octokit rest repos create
4:46:414 hours, 46 minutes, 41 secondsfour authenticated user pass the name repo name description to be description or a very simple exported from polaris
4:46:514 hours, 46 minutes, 51 secondsprivate will be if visibility is set to private and out init will be set to true
4:46:584 hours, 46 minutes, 58 secondsgreat then let's go ahead and wait for GitHub to initialize the repository simply because auto initialize is async on
4:47:074 hours, 47 minutes, 7 secondsGitHub side. So I'm going to sleep for 3 seconds. If this uh step fails too much
4:47:164 hours, 47 minutes, 16 secondsfor you, you can increase this to five or 6 seconds. But most of the time this works with 3 seconds. In fact, um I mean this is what my debugging led me to.
4:47:254 hours, 47 minutes, 25 secondsThis is my conclusion that that's what happens because I had some annoying bug with this. It could be that I was doing something wrong at the time which I
4:47:334 hours, 47 minutes, 33 secondsfixed later because uh this never happened again. But still I want to show you that this is an asynchronous
4:47:394 hours, 47 minutes, 39 secondsfunction. So the next step is basically to like get the initial commit uh sha
4:47:484 hours, 47 minutes, 48 secondshowever you pronounce it right uh but we can do that if the repo has not yet initialized right so that's why we want
4:47:564 hours, 47 minutes, 56 secondsto avoid uh any errors but still a background job will retry itself if it fails so this isn't too important right
4:48:054 hours, 48 minutes, 5 secondsall right so yes next step is to get the initial commit we need this as the parent for our commit. So let's go ahead
4:48:144 hours, 48 minutes, 14 secondsand create a background job called get initial commit.
4:48:224 hours, 48 minutes, 22 secondsMake sure it's an asynchronous function.
4:48:244 hours, 48 minutes, 24 secondsAnd basically what we're going to do in here is again call octokit SDK. So await octokit rest get ref owner user.lo.
4:48:374 hours, 48 minutes, 37 secondsRemember user comes from a previous step get GitHub user in which we return get authenticated and we await it and we
4:48:454 hours, 48 minutes, 45 secondsalias that to user. So now we can uh use it here repo name ref heads forward/main and return ref object sha.
4:48:574 hours, 48 minutes, 57 secondsNow let's go ahead and fetch all project files with storage urls.
4:49:054 hours, 49 minutes, 5 secondsSo this will be some binary file things right. Let me go ahead and prepare this step.
4:49:124 hours, 49 minutes, 12 secondsFetch project files.
4:49:164 hours, 49 minutes, 16 secondsAnd in here we are going to do the following.
4:49:214 hours, 49 minutes, 21 secondsWe're going to return open parenthesis await convex.query API system get project files with URLs.
4:49:344 hours, 49 minutes, 34 secondspass in the internal key and project ID and cast this as file with URL and then
4:49:414 hours, 49 minutes, 41 secondsan array of those. So looks like we since we're not getting any errors here, looks like this cast is correct. I think if I change this to something, you will
4:49:504 hours, 49 minutes, 50 secondssee that this then causes an error which means that we have correctly extended the storage URL part. So yes, if you
4:49:574 hours, 49 minutes, 57 secondsremember this system function basically loads all the files in a project and it simply makes use of that storage ID by
4:50:064 hours, 50 minutes, 6 secondsturning it into a URL. So in this scenario, when we want to export those binary files to GitHub, we need to
4:50:144 hours, 50 minutes, 14 secondsconvert them to a URL that GitHub can well turn into a binary file and upload onto their system because GitHub can't
4:50:234 hours, 50 minutes, 23 secondsdo much with our internal storage ID. So that's why we're doing that.
4:50:304 hours, 50 minutes, 30 secondsNow that we have all the files ready, we have to do the reverse of what we were
4:50:374 hours, 50 minutes, 37 secondsdoing in the import background job. We have to build a map of file IDs to their full paths. But luckily, this is
4:50:454 hours, 50 minutes, 45 secondsactually a little bit simpler than doing the other thing. All right, so build file paths function accepts an
4:50:544 hours, 50 minutes, 54 secondsarray of files with their storage URLs if there are any. We're going to prepare a file map using new map. It will have
4:51:034 hours, 51 minutes, 3 secondsan ID of files and object file with URL.
4:51:084 hours, 51 minutes, 8 secondsAnd then let's go ahead and run a quick files for each file and simply set it in
4:51:174 hours, 51 minutes, 17 secondsthe file map mapping their ID with their content inside.
4:51:234 hours, 51 minutes, 23 secondsThen let's develop a method inside to get the full file the full path of a file. So this method will accept a
4:51:324 hours, 51 minutes, 32 secondsentire object of file with URL and it will return a string. First things first, if there is no parent ID, we
4:51:414 hours, 51 minutes, 41 secondsreturn a file name. So the point of this function is to return things like source components index.js.
4:51:514 hours, 51 minutes, 51 secondsBut in case it's a root file, it's just index.js. That's why we just return the file name if there's no parent.
4:52:014 hours, 52 minutes, 1 secondOtherwise, open back in this return statement here and simply call get full
4:52:104 hours, 52 minutes, 10 secondspath again with the parent and then forward slash file.name.
4:52:204 hours, 52 minutes, 20 secondsNow let's go ahead and just uh see the problem here. My apologies. Inside of get full path here.
4:52:294 hours, 52 minutes, 29 secondsUh so after we check if there's no file parent ID, we have to get the parent of
4:52:354 hours, 52 minutes, 35 secondscourse. So filemap.get file.parent id then if there's no parent return file.name.
4:52:474 hours, 52 minutes, 47 secondsMy apologies. I I'm kind of getting lost. These files are way too similar.
4:52:524 hours, 52 minutes, 52 secondsAll right. So, in order to get full path, we check if there's no parent ID and do an early return. Otherwise, if
4:52:594 hours, 52 minutes, 59 secondsthe we attempt to get the parent from the file map using file parent ID because we map all the files with their
4:53:064 hours, 53 minutes, 6 secondsID and their content and if it doesn't exist there, we again return file.name. So, this is kind of an edge case, right?
4:53:154 hours, 53 minutes, 15 secondsOtherwise, we recursively call this function until it generates the full path string. So, it will either early
4:53:224 hours, 53 minutes, 22 secondsreturn or it will continue generating the string. Great.
4:53:284 hours, 53 minutes, 28 secondsNow that we have that, let's go ahead and prepare an object which will store all the files with their paths.
4:53:384 hours, 53 minutes, 38 secondsSo files for each file simply assign to the paths object their full path and their content inside and return paths.
4:53:534 hours, 53 minutes, 53 secondsThen outside of this function let's go ahead and actually get all file paths by calling build file paths.
4:54:044 hours, 54 minutes, 4 secondsThen let's filter to only actual files not folders.
4:54:104 hours, 54 minutes, 10 secondsSo file entries object dot entries file paths dot filter skip the first argument
4:54:184 hours, 54 minutes, 18 secondswhich is the ID and go into the object and access file.type comparison for file. If it's true, it's going to filter out all of those which are not files.
4:54:314 hours, 54 minutes, 31 secondsAnd then if that length is zero, let's throw a non retryable error. No files to export.
4:54:414 hours, 54 minutes, 41 secondsAnd now what we have to do is we have to create blobs for each file. Let me fix the typo here.
4:54:544 hours, 54 minutes, 54 secondsSo let's go ahead and prepare this function. create blobs.
4:55:014 hours, 55 minutes, 1 secondSo the blob has the following structure path, string, mode, type, and sha.
4:55:134 hours, 55 minutes, 13 secondsIf you're curious about this magic number right here, feel free to Google that along with blob so you will see a more in-depth explanation. But
4:55:214 hours, 55 minutes, 21 secondsbasically, this is the mode uh that makes it exportable to GitHub file system.
4:55:294 hours, 55 minutes, 29 secondsSo simply create an empty array and give it a type of this. It's important that
4:55:364 hours, 55 minutes, 36 secondsyou don't forget this array type at the end.
4:55:404 hours, 55 minutes, 40 secondsAll right. So now that we have file entries and file paths, let's go ahead and do a for loop. So for each path and
4:55:484 hours, 55 minutes, 48 secondsfile of file entries, let's prepare their content to just be a string. And let's go ahead and prepare their
4:55:564 hours, 55 minutes, 56 secondsencoding. Are they content? Are they textual content? We're going to use UTF8. Or are they a binary file, in which case we're going to use base 64.
4:56:104 hours, 56 minutes, 10 secondsSo first things first, if file.content is not undefined, that means this is a
4:56:194 hours, 56 minutes, 19 secondstext file. So let's do content equals file.content.
4:56:264 hours, 56 minutes, 26 secondselse if we have file storage URL
4:56:314 hours, 56 minutes, 31 secondsthis is a binary file fetch and base 64 end code so let's go ahead and do that
4:56:404 hours, 56 minutes, 40 secondsnow we can get a very quick response using kyget on file storage URL once we
4:56:474 hours, 56 minutes, 47 secondsget the response we can turn that into a buffer using buffer from await response array buffer
4:56:554 hours, 56 minutes, 55 secondsAnd then we can store that into content by turning it into base 64. And let's go
4:57:024 hours, 57 minutes, 2 secondsahead and set the encoding to base 64 in that case. Else, so if it's not a text
4:57:094 hours, 57 minutes, 9 secondsfile and not a binary file, skip files with no content at all and continue. All right.
4:57:194 hours, 57 minutes, 19 secondsNow let's go ahead and actually create the blob using octokit.
4:57:264 hours, 57 minutes, 26 secondsSo await octokit rest get create blob owner user login repo content and coding data blob.
4:57:384 hours, 57 minutes, 38 secondsAnd then let's go ahead and push to our items array. Path again the same mode as
4:57:454 hours, 57 minutes, 45 secondsbefore. type of blob and sh a blob sha and let's return items. There we go.
4:57:564 hours, 57 minutes, 56 secondsThen let's check if tree items.length is zero, it means we failed to create any file blobs. We didn't export anything.
4:58:084 hours, 58 minutes, 8 secondsSo we throw back because this is a non retryable error, right? Something went very wrong up there. But otherwise we are ready to start creating the tree.
4:58:194 hours, 58 minutes, 19 secondsSo this is very simple. We are going to create a step called create tree and simply return octoit rest get create
4:58:284 hours, 58 minutes, 28 secondstree owner user login repo repo name tree tree items
4:58:374 hours, 58 minutes, 37 secondsand then we have to create the commit with the initial commit as the parent.
4:58:424 hours, 58 minutes, 42 secondsSo we are now creating a new commit, right? We've just uh pushed these files and we have to commit that. That's how
4:58:494 hours, 58 minutes, 49 secondsgit works. So again just a very simple octokit SDK function. Octokit.rest.git
4:58:594 hours, 58 minutes, 59 secondscreate commit owner repo name message it can be whatever you want. We're going to
4:59:054 hours, 59 minutes, 5 secondsuse initial commit from Polaris three and parents which is initial commit sha.
4:59:154 hours, 59 minutes, 15 secondsGreat.
4:59:174 hours, 59 minutes, 17 secondsNow let's go ahead and let's update the main branch reference to point to our new commit.
4:59:254 hours, 59 minutes, 25 secondsThat's again going to be a simple octokit function. So a step called update branch ref return await octokit
4:59:344 hours, 59 minutes, 34 secondsrest get update ref with the owner repository ref heads main sha commit.sha
4:59:424 hours, 59 minutes, 42 secondsand force to true and then last step here set status to completed with repo URL.
4:59:554 hours, 59 minutes, 55 secondsSo set completed status convex mutation API system update export status internal
5:00:025 hours, 2 secondskey project ID status completed and finally the repo URL using repo.html
5:00:125 hours, 12 secondsURL. So we know we have accessed this from the start actually it's just empty I believe. So let me find where do we get the repo from? Here it is. Great.
5:00:225 hours, 22 secondsAll right. Uh that is it. All we ought to do now is just a simple return here.
5:00:305 hours, 30 secondsThere we go. Success true repo URL. And how many files were actually exported?
5:00:365 hours, 36 secondsGreat. So that is our export to GitHub function. Now we have to register these
5:00:445 hours, 44 secondsingest functions. For that we have to go inside of app API inest route.ds DS
5:00:525 hours, 52 secondsand let's go ahead and pass in import GitHub repo export to GitHub and that's
5:00:595 hours, 59 secondsit. And at this point we can remove demo generate and demo error.
5:01:065 hours, 1 minute, 6 secondsGreat.
5:01:085 hours, 1 minute, 8 secondsNow let's go ahead and add some UI so we can actually test this. So, we're going to go inside of source, inside of
5:01:175 hours, 1 minute, 17 secondsfeatures, inside of projects components, and I'm going to go ahead and create a
5:01:245 hours, 1 minute, 24 secondsnew file called import github dialogue.tsx.
5:01:315 hours, 1 minute, 31 secondsI'm going to go ahead and import ky and http error from ky.
5:01:395 hours, 1 minute, 39 secondsI'm going to import zod son toast use router from next navigation use form
5:01:455 hours, 1 minute, 45 secondsfrom tanstack react form use clerk from clerk nextjs I'm going to import button from
5:01:535 hours, 1 minute, 53 secondscomponents ui button dialogue dialogue content description footer header and
5:01:595 hours, 1 minute, 59 secondstitle from components UI dialogue and then I'm going to import input from
5:02:065 hours, 2 minutes, 6 secondscomponents UI input field field error and field label.
5:02:135 hours, 2 minutes, 13 secondsThen I'm going to import ID from convex generated data model. Let's go ahead and
5:02:205 hours, 2 minutes, 20 secondsdefine the form schema. It's very simply going to ask the user for the URL they want to import. As simple as that. And thanks to our function, let me go ahead.
5:02:315 hours, 2 minutes, 31 secondsUh is it here in GitHub import? I think it is. It is parse GitHub URL. So this
5:02:385 hours, 2 minutes, 38 secondsis why I've kind of developed it. So we allow the user to just enter a URL, right? And then on the back end, we're
5:02:465 hours, 2 minutes, 46 secondsjust going to extract the owner and the repository, right? So I think it's a useful function. Feel free to copy it from the
5:02:535 hours, 2 minutes, 53 secondssource code simply because this is a bit heavy to copy. Uh so this will make it easier on the user experience. So we do
5:03:025 hours, 3 minutes, 2 secondsthe hard work for them. All right. So the props for this component are going to be open and unopen change. And let's
5:03:105 hours, 3 minutes, 10 secondsgo ahead and export the component. So import GitHub dialogue accepts open and unopen change. Let's prepare a router
5:03:195 hours, 3 minutes, 19 secondsfrom use router and let's prepare open user profile from use clerk. So, we're going to use this
5:03:265 hours, 3 minutes, 26 secondsin case we get an error that user doesn't have their GitHub connected because remember uh while we do allow uh
5:03:355 hours, 3 minutes, 35 secondsGitHub login, you can also enable Google login or a bunch of other ones even email and password, right? But good news
5:03:435 hours, 3 minutes, 43 secondsis user can always connect additional ones from their account settings. Clerk makes that very very easy.
5:03:535 hours, 3 minutes, 53 secondsNow let's go ahead and define the form.
5:03:565 hours, 3 minutes, 56 secondsThe form will start with default values which is just empty URL. The validators are going to be onsubmit which will simply look for form schema.
5:04:095 hours, 4 minutes, 9 secondsAnd then we'll develop the actual onsubmit asynchronous method which gives us access to the value.
5:04:165 hours, 4 minutes, 16 secondsAnd what we're going to do is we're going to initiate a post request to so let's do the following. Let's extract
5:04:255 hours, 4 minutes, 25 secondsproject ID from await ky.post forward slappi github import. Don't
5:04:345 hours, 4 minutes, 34 secondsmisspell this. Right? This is not type safe. You can write whatever you want here. Just make sure that you actually
5:04:405 hours, 4 minutes, 40 secondshave a github import. Right? So no typos anywhere.
5:04:465 hours, 4 minutes, 46 secondsAll right. And as the body of this post request, we're going to add JSON URL value URL. So exactly what user writes, we're going to parse this back as JSON.
5:04:595 hours, 4 minutes, 59 secondsAnd let's go ahead and write what we expect, which is success boolean project ID ID
5:05:085 hours, 5 minutes, 8 secondsof projects. And let's see what else do we expect. also the event ID which is a
5:05:155 hours, 5 minutes, 15 secondstype of string. All right. So let's be correct for our front end here and write exactly what we expect back. So after
5:05:235 hours, 5 minutes, 23 secondsproject ID it's event ID which is a type of string. Great. At this point we can
5:05:305 hours, 5 minutes, 30 secondsalready send toast.success importing repository
5:05:375 hours, 5 minutes, 37 secondssince it's a background job. So it didn't finish it just started. And let's go ahead and close this dialogue. And
5:05:445 hours, 5 minutes, 44 secondslet's reset the form. All right. And after that, what I want to do is also do
5:05:525 hours, 5 minutes, 52 secondsa router.push to projects project ID simply so we can immediately uh well redirect the user there.
5:06:075 hours, 6 minutes, 7 secondsLet's wrap this inside of a try and catch.
5:06:125 hours, 6 minutes, 12 secondsAnd in the catch method, let's go ahead and grab the error.
5:06:185 hours, 6 minutes, 18 secondsAnd let's check if error is instance of HTTP error.
5:06:265 hours, 6 minutes, 26 secondsLet's go ahead and extract the body of the error using await error response JSON.
5:06:355 hours, 6 minutes, 35 secondsLet's go ahead and add types here. Error string.
5:06:405 hours, 6 minutes, 40 secondsAnd now what we can do is we can check if body question mark error question mark includes GitHub not connected.
5:06:505 hours, 6 minutes, 50 secondsIn that case, we can throw toast error GitHub account not connected
5:07:015 hours, 7 minutes, 1 secondand an action with a label of connect and an on click open user profile.
5:07:135 hours, 7 minutes, 13 secondsSo if there is an error happening here, user will simply get a subtle toast which says GitHub account is not connected and an action. So down here
5:07:225 hours, 7 minutes, 22 secondsthat's where it's going to happen and an action to open clerk user profile which will basically just trigger manage
5:07:305 hours, 7 minutes, 30 secondsaccount here which will allow the user to then connect another account. All right.
5:07:395 hours, 7 minutes, 39 secondsAnd at this point, so what I'm going to do is just indent my thing in the try here.
5:07:465 hours, 7 minutes, 46 secondsAnd for this part, GitHub not connected.
5:07:495 hours, 7 minutes, 49 secondsSo again, be careful here. Do we throw that error? Here it is. GitHub not connected. For example, here's the bug.
5:07:595 hours, 7 minutes, 59 secondsI'm not sure this would work now because my GitHub here is capitalized, but it's
5:08:055 hours, 8 minutes, 5 secondsnot here. So make sure to capitalize it here in the includes because it's checking for a string. You can see it's
5:08:135 hours, 8 minutes, 13 secondsa fragile way to do it. You could do it with a very specific status or maybe adding code here which could be an enum
5:08:215 hours, 8 minutes, 21 secondslike GitHub missing and then you can check for that instead of a string. Uh but of course that is for actual you
5:08:295 hours, 8 minutes, 29 secondsknow production problems for now just for tutorial sake we can just check for a string. But just to make it work, make
5:08:365 hours, 8 minutes, 36 secondssure you're actually throwing that part of the string so you can actually catch it here.
5:08:425 hours, 8 minutes, 42 secondsAll right. So after we throw that error, we also ought to close the dialogue as well.
5:08:525 hours, 8 minutes, 52 secondsGreat.
5:08:535 hours, 8 minutes, 53 secondsAnd then finally outside of this if clause here, let's just do toast.
5:09:025 hours, 9 minutes, 2 secondsUnable to import repository.
5:09:075 hours, 9 minutes, 7 secondsPlease check the URL and try again. So there's a chance that the error is unrelated to the GitHub account. Since
5:09:155 hours, 9 minutes, 15 secondswe do an early return here, we don't have to put this instead of an else, right?
5:09:205 hours, 9 minutes, 20 secondsAll right. And now let's go ahead and actually uh build the UI. So let's go
5:09:275 hours, 9 minutes, 27 secondsahead and add a return here. Dialogue open. and on open change. Let's go ahead
5:09:345 hours, 9 minutes, 34 secondsand add dialogue header, dialogue content, and dialogue title.
5:09:415 hours, 9 minutes, 41 secondsThen let's go ahead and add dialogue description. Enter a GitHub repository URL to import.
5:09:495 hours, 9 minutes, 49 secondsA new project will be created with the repository contents.
5:09:545 hours, 9 minutes, 54 secondsFor the actual form, we're going to go ahead outside of the dialogue header and define the form element with onsubmit
5:10:015 hours, 10 minutes, 1 secondprevent default calling form handle submit. Inside, let's go ahead and do form.form field. So, what's the deal
5:10:095 hours, 10 minutes, 9 secondshere? I don't think I've explained this previously. So, uh form in this case is just a native HTML form element. Form in
5:10:175 hours, 10 minutes, 17 secondsthis case is referring to this form, right? So don't be confused about that.
5:10:245 hours, 10 minutes, 24 secondsSo this form field is not native HTML.
5:10:275 hours, 10 minutes, 27 secondsThis is a specific component that's being exported through the hook. That's why we can access it this way. It just
5:10:355 hours, 10 minutes, 35 secondscoincidentally perfectly matches with this. I actually like it. But it is a bit confusing when you don't understand what's going on
5:10:435 hours, 10 minutes, 43 secondsbecause this also feels like it's native. It's not. This is a hook. All right. So form field with the name of
5:10:495 hours, 10 minutes, 49 secondsURL we'll have access to that field properties in this way and then in here we can immediately check if it is
5:10:575 hours, 10 minutes, 57 secondsinvalid. So we're going to store the is invalid state using field state meta is touched and if not field state meta is
5:11:075 hours, 11 minutes, 7 secondsvalid. All right now we can finally return how the field is going to look
5:11:135 hours, 11 minutes, 13 secondslike. So let's do field data invalid. So basically just an accessibility attribute here is invalid.
5:11:235 hours, 11 minutes, 23 secondsAnd let's go ahead and define the field label again HTML 4. So it has an accessibility attribute. The name is I mean the actual label is repository URL.
5:11:365 hours, 11 minutes, 36 secondsAnd then let's go ahead and define the input. The input has ID of field name of
5:11:445 hours, 11 minutes, 44 secondsfield dotname value of field state value on blur field handle blur on change
5:11:535 hours, 11 minutes, 53 secondsfield handle change event target value area invalid is invalid and a
5:12:005 hours, 12 minutesplaceholder explaining to the user the structure that we expect. So then our backend parse GitHub URL function will
5:12:075 hours, 12 minutes, 7 secondsextract the owner and the repository and pass it as separate objects or keys should I say to relevant inest
5:12:165 hours, 12 minutes, 16 secondsbackground jobs which call the octtokit further on in case there's an error in the actual field let's display that by
5:12:245 hours, 12 minutes, 24 secondschecking if is invalid and rendering the field error and passing the errors with field state meta errors. Great.
5:12:355 hours, 12 minutes, 35 secondsSo that marks the end of the form field.
5:12:375 hours, 12 minutes, 37 secondsAll we have to do now is create the dialogue footer which with a margin top four class name which will simply give us two buttons.
5:12:505 hours, 12 minutes, 50 secondsThe first button will be a type of button. This is very important. So this button is not used for submitting.
5:12:555 hours, 12 minutes, 55 secondsThat's why we explicitly give it a type of button. a variant of outline and on click on open change false. Basically,
5:13:035 hours, 13 minutes, 3 secondsthis is used to close the model like cancel it. And for the submit one, we're going to uh access that through another
5:13:125 hours, 13 minutes, 12 secondsform.subscribe element. The subscribe element will have a selector uses state and returns an
5:13:225 hours, 13 minutes, 22 secondsarray. state can submit and state is submitting then we can uh we can work with those two fields using the following syntax.
5:13:345 hours, 13 minutes, 34 secondsSo again can submit and is submitting and we're very simply going to return button type submit which is disabled if
5:13:425 hours, 13 minutes, 42 secondsnot can submit or is submitting. If it is submitting, display importing,
5:13:495 hours, 13 minutes, 49 secondsotherwise import. So to make it easier for you to read, I'm going to collapse it a bit. There we go.
5:13:575 hours, 13 minutes, 57 secondsUh, great. That is it for import GitHub dialogue.
5:14:045 hours, 14 minutes, 4 secondsAnd now the last UI component we need to create before we test this out is the export popover. So, I'm going to go
5:14:125 hours, 14 minutes, 12 secondsahead and copy and paste this since they are somewhat similar and rename the copy to export popover.tsx.
5:14:225 hours, 14 minutes, 22 secondsDouble click to make sure you are working inside of export popover. And let's go ahead and start by checking our
5:14:305 hours, 14 minutes, 30 secondsimports. So, I'm just going to add an overall import for React since we're going to need it. So, React from React.
5:14:385 hours, 14 minutes, 38 secondsKY is good. Zod toast. We're not going to need use router. So, we can remove that. We will need use form and use
5:14:475 hours, 14 minutes, 47 secondsclerk. And for the icons, we're going to need check check icon, check circle 2
5:14:555 hours, 14 minutes, 55 secondsicon, external link icon, loader icon, and x circle icon.
5:15:025 hours, 15 minutes, 2 secondsFor the component, uh we're going to use button. We are not going to use dialogue. Instead, we're going to use popover. So popover popover content and trigger.
5:15:135 hours, 15 minutes, 13 secondsWe are going to be using the input so that can stay and we're going to have field field error and field label. And
5:15:225 hours, 15 minutes, 22 secondswe're going to have two more components besides that. We're going to have select select content select item select trigger select value and text area.
5:15:335 hours, 15 minutes, 33 secondsThen I'm also going to import a hook called use project from hooks use
5:15:415 hours, 15 minutes, 41 secondsprojects. Uh we already have id from uh generated data model. And let's also add
5:15:495 hours, 15 minutes, 49 secondsan icon from react- icons forward/fa fa github. All right. Now let's modify
5:15:575 hours, 15 minutes, 57 secondsthe form schema. So the form schema will have a field called repo name.
5:16:065 hours, 16 minutes, 6 secondsRepo name will be a string with a minimum length of one, maximum of 100
5:16:135 hours, 16 minutes, 13 secondsand a reg x for only alpha numeric characters, hyphens, underscores and dots. Basically the same rules that
5:16:195 hours, 16 minutes, 19 secondsGitHub enforces. So a very simple regex here. You don't need to add it, but it will prevent the user from trying to
5:16:265 hours, 16 minutes, 26 secondssubmit an incorrect one. For the visibility prop, it's going to be an enum of public and
5:16:335 hours, 16 minutes, 33 secondsprivate. And then the description, which has a maximum length of 350, which is too long after that. All right.
5:16:445 hours, 16 minutes, 44 secondsFor the props, the only thing we're going to need is the project ID, and it's going to be called export popover props.
5:16:535 hours, 16 minutes, 53 secondsThen let's go ahead and change the export instead of import GitHub dialogue to export popover. Export popover simply
5:17:025 hours, 17 minutes, 2 secondsuses the project ID and the same named props. Since we don't have the router hook, we no longer need it. But beside
5:17:105 hours, 17 minutes, 10 secondsuh instead of that, we can add the project and load it. And we can define a
5:17:175 hours, 17 minutes, 17 secondssimple use state from react use state open and set open. And we can leave the profile here. Then let's keep track of
5:17:265 hours, 17 minutes, 26 secondsthe export status of the project and export repo URL of the project. So this way we can track since convex is a
5:17:345 hours, 17 minutes, 34 secondsreal-time database what's the current status of the background job and did we receive a final rep repo URL we can visit.
5:17:435 hours, 17 minutes, 43 secondsNow we go to the form. So the form will have uh three different values here.
5:17:505 hours, 17 minutes, 50 secondsrepository name in which we are going to attempt to load the current project's name. But since there are different
5:17:595 hours, 17 minutes, 59 secondsrules for what we allow users to name our project and what GitHub uh accepts, we have to use replace and only accept
5:18:085 hours, 18 minutes, 8 secondsalpha numeric characters, dashes, hyphens, and dots. If you want to uh you don't have to do again this reax at all.
5:18:165 hours, 18 minutes, 16 secondsYou can just do a fallback like this.
5:18:195 hours, 18 minutes, 19 secondsBut this will prevent any problems from happening. Visibility will fall back to private and we're going to cast it as the only two enems we accept and
5:18:275 hours, 18 minutes, 27 secondsdescription will be empty. Uh validators object stays the same. And now in the onsubmit it's going to be a little bit
5:18:345 hours, 18 minutes, 34 secondsdifferently. Uh so in here we are going going to call API GitHub export. Again
5:18:445 hours, 18 minutes, 44 secondsmake sure you didn't misspell this right. So just double check inside of your import my apologies inside of your
5:18:525 hours, 18 minutes, 52 secondsAPI GitHub export right export. All right. So the JSON it accepts is a little bit different. It's not URL.
5:19:025 hours, 19 minutes, 2 secondsInstead, it's the project ID, repository name, which is value.reo
5:19:115 hours, 19 minutes, 11 secondsname, visibility, value.visisibility, description value.escription or
5:19:175 hours, 19 minutes, 17 secondsundefined. And this will not be needed at all.
5:19:235 hours, 19 minutes, 23 secondsThere we go. So now there should be no problems here.
5:19:275 hours, 19 minutes, 27 secondsUh for the JSON we don't really care. We don't have to. We're just initiating. We don't really care about the result itself.
5:19:365 hours, 19 minutes, 36 secondsUh and we can remove uh well I guess we can
5:19:445 hours, 19 minutes, 44 secondsjust leave the toast message which would say export started. I think we can kind of
5:19:515 hours, 19 minutes, 51 secondssend a success message. And then immediately let's go into catch uh and make sure to check for the exact same
5:19:585 hours, 19 minutes, 58 secondserror GitHub uh not connected and allow the user to connect and change this set
5:20:065 hours, 20 minutes, 6 secondsopen to be false. The reason we are not doing set open false here is simply it's a different UI you will see. But uh just
5:20:145 hours, 20 minutes, 14 secondsin case you were wondering like, hey, why are not we closing it here? Because we are closing the import one because that's a dialogue. This is a popover. So
5:20:215 hours, 20 minutes, 21 secondsit's a little bit different. Uh okay, what I want to do now is just double check that this error actually works. So
5:20:305 hours, 20 minutes, 30 secondsfor that, we're going to go inside of export route.ts and check GitHub not connected. Make sure you're throwing this. Make sure the capitalization is
5:20:395 hours, 20 minutes, 39 secondscorrect. Make sure it's the exact same line you're checking here. Great. So instead of toast error saying unable to
5:20:475 hours, 20 minutes, 47 secondsuh import repository, it will be unable to export repository. Unfortunately, this is not due to the URL. It can be many things. So we're just going to say unable to export repository.
5:20:595 hours, 20 minutes, 59 secondsAll right. Uh for the return here, I am okay. I'm not going to delete anything just yet because there are uh a few more
5:21:085 hours, 21 minutes, 8 secondsfunctions we have to develop. The first function is handle cancel export which is basically a button to cancel the
5:21:155 hours, 21 minutes, 15 secondsexport. So it's going to call API GitHub export cancel. Make sure it actually exists.
5:21:235 hours, 21 minutes, 23 secondsAPI GitHub cancel. Uh and now that I look at it, uh mine is actually
5:21:305 hours, 21 minutes, 30 secondsincorrect. So my cancel route is in a different uh place here. So yes, I'm
5:21:395 hours, 21 minutes, 39 secondsgoing to drag my cancel route and put it inside of export because that's where I meant to add it. So yes, it should be API GitHub export cancel. My apologies.
5:21:525 hours, 21 minutes, 52 secondsI think I've missed this uh completely.
5:21:565 hours, 21 minutes, 56 secondsAll right, so now this makes sense. API GitHub export cancel allowing us to cancel an export. Then let's go ahead
5:22:055 hours, 22 minutes, 5 secondsand add a function to reset the export again. I think we're going to have to move this. So API GitHub export reset.
5:22:145 hours, 22 minutes, 14 secondsLet me see inside of my API here.
5:22:175 hours, 22 minutes, 17 secondsYes, let's move reset and put it inside of export folder because that's where I meant to do it. I just completely forgot. My apologies. So yes, because
5:22:265 hours, 22 minutes, 26 secondsboth of these entirely refer to exporting.
5:22:305 hours, 22 minutes, 30 secondsPerfect. Now let's go ahead and develop a function called render content.
5:22:385 hours, 22 minutes, 38 secondsIf export status is exporting, in that case, we're just going to go
5:22:465 hours, 22 minutes, 46 secondsahead and display a div with class name flex, flex skull,
5:22:525 hours, 22 minutes, 52 secondsitem center, and gap three. a loader icon with class name size six animate
5:23:005 hours, 23 minutesspin and text muted foreground a paragraph with text exporting to GitHub text small text muted foreground
5:23:105 hours, 23 minutes, 10 secondsas the class names and finally a button to cancel it. So this button will have a size of small variant of outline class
5:23:185 hours, 23 minutes, 18 secondsname of width full and on click handle cancel export and the label cancel.
5:23:255 hours, 23 minutes, 25 secondsAll right.
5:23:275 hours, 23 minutes, 27 secondsSo that is for that case. Now let's do if export status is completed and if we
5:23:365 hours, 23 minutes, 36 secondshave export repository URL in that case let's go ahead and copy the
5:23:445 hours, 23 minutes, 44 secondsouter div since that stays the same. The only thing we're going to check uh is the icon which will be check circle to
5:23:535 hours, 23 minutes, 53 secondsicon size six and text emerald 500 to give it a nice greenish color. Uh beneath a small description repository
5:24:025 hours, 24 minutes, 2 secondscreated with text small and font medium class name. Beneath that another text text extra small text muted foreground
5:24:105 hours, 24 minutes, 10 secondstext center. Your project has been exported to GitHub. Then let's go ahead and create a div class name flex flex
5:24:185 hours, 24 minutes, 18 secondscolumn width full and gap 2. In here let's go ahead and add a button to open that GitHub repository.
5:24:265 hours, 24 minutes, 26 secondsSo this button right here size small class name with full as child property inside an href with a target forward
5:24:355 hours, 24 minutes, 35 secondsslank my apologies underscore blank. I think we can do this with a normal link though. Let me see.
5:24:445 hours, 24 minutes, 44 secondsWe just have to import link from next link. I think this should work just fine. Yes.
5:24:535 hours, 24 minutes, 53 secondsAnd external link icon icon and view on GitHub label.
5:24:595 hours, 24 minutes, 59 secondsNow we're also going to add a button to reset the entire thing. Right. So once the link is shown view on GitHub next to
5:25:095 hours, 25 minutes, 9 secondsit, this button will serve as the reset button. And by reset, we don't mean we're going to delete it from GitHub.
5:25:175 hours, 25 minutes, 17 secondsNo, the user now knows, hey, that's the link. Go on your GitHub and maintain it there. But click this button if you want
5:25:255 hours, 25 minutes, 25 secondsto change the repository, right? If you want to export it again to some other place. So that's button size small
5:25:325 hours, 25 minutes, 32 secondsvariant outline class name with full on click handle reset export with a close label. Great. Uh now in case the export
5:25:435 hours, 25 minutes, 43 secondsfails, we need to display uh an error in that case.
5:25:505 hours, 25 minutes, 50 secondsSo we're going to display something very similar uh to the first one to exporting. So let's just go ahead and
5:25:585 hours, 25 minutes, 58 secondscopy this entire thing here and let's just paste it here. Instead of loader icon, it will have X circle icon. It
5:26:075 hours, 26 minutes, 7 secondswon't have animate spin. Instead, it will have text rows 500.
5:26:155 hours, 26 minutes, 15 secondsUh then for the paragraph, we're just going to say unable to export with text small and font medium.
5:26:255 hours, 26 minutes, 25 secondsAnd beneath that text extra small ball, text muted foreground and text center. Something went wrong. Please try again.
5:26:345 hours, 26 minutes, 34 secondsFor the button, it will have a size of small variant of outline with full. And this will be handle
5:26:415 hours, 26 minutes, 41 secondsreset export. So if the export fails, we're going to allow the user to trigger
5:26:495 hours, 26 minutes, 49 secondsa reset from here as well. So they can enter new information rather than just try the same thing again. All right. And
5:26:585 hours, 26 minutes, 58 secondsthen finally in the return we're going to go ahead and build our form. So let's
5:27:055 hours, 27 minutes, 5 secondsgo ahead and build form here with an onsubmit prevent default and form handle submit. Let's go ahead and add a space
5:27:135 hours, 27 minutes, 13 secondsY4 inside space Y1. Let's add a heading
5:27:205 hours, 27 minutes, 20 secondsexport to GitHub with font medium and text small. Beneath the heading, we have a paragraph text small and text muted
5:27:285 hours, 27 minutes, 28 secondsforeground. Export your project to a GitHub repository. Outside of that div, we're going to add our first form field
5:27:385 hours, 27 minutes, 38 secondswhich will be used to enter the repository name. Now to access the field property we use the following syntax and
5:27:465 hours, 27 minutes, 46 secondsthen in here what we can do is we can extract the is invalid into a constant by checking for field state meta is touched and field state meta is valid.
5:27:595 hours, 27 minutes, 59 secondsGreat. Then let's go ahead and actually return the field.
5:28:055 hours, 28 minutes, 5 secondsSo, we're going to use the field component and give it an accessibility attribute data is invalid.
5:28:135 hours, 28 minutes, 13 secondsWe're going to add it a label which says repository name and the accessibility HTML 4.
5:28:235 hours, 28 minutes, 23 secondsAnd let's go ahead and render the actual input with the ID of field name of field
5:28:305 hours, 28 minutes, 30 secondsname value of field state value on blur field handle blur on change field handle
5:28:385 hours, 28 minutes, 38 secondschange with event target value. Another accessibility attribute for is invalid and a placeholder indicating to the user
5:28:475 hours, 28 minutes, 47 secondshow they should name this project compatible with GitHub standards. And beneath that, let's go ahead and simply
5:28:555 hours, 28 minutes, 55 secondshandle any errors using the field error and the prop errors field state meta errors.
5:29:035 hours, 29 minutes, 3 secondsGreat. Uh now outside of that form field, let's go ahead and duplicate that and paste it here.
5:29:145 hours, 29 minutes, 14 secondsSo this one will be used for visibility.
5:29:185 hours, 29 minutes, 18 secondsAll right. In this case, we don't need the is invalid. We can immediately go ahead uh and return. So, we can remove
5:29:275 hours, 29 minutes, 27 secondsthe actually. I mean, we can keep it. It doesn't really matter. Um not too sure because this is a different component. Sorry, I am going to remove it actually.
5:29:365 hours, 29 minutes, 36 secondsUh so, the field label will simply say visibility and the prop here is not going to be an input. So, we can get rid
5:29:455 hours, 29 minutes, 45 secondsof that and the error too. And the prop will be select.
5:29:525 hours, 29 minutes, 52 secondsSo inside of this select, let's go ahead and give it value field state value.
5:29:585 hours, 29 minutes, 58 secondsLet's give it on value change which accepts value which is either public or private. And it calls field handle change and passes in the value.
5:30:095 hours, 30 minutes, 9 secondsThen in here, let's go ahead and do normal select composition select trigger with the ID it needs and select value with a placeholder select visibility.
5:30:225 hours, 30 minutes, 22 secondsBeneath the select trigger, we're going to render the select content with its select items, one for private and one
5:30:305 hours, 30 minutes, 30 secondsfor public. Make sure the value has the exact same value as you've defined everywhere else. public private in
5:30:385 hours, 30 minutes, 38 secondslowercase. So this needs to match what you've defined in your project's schema.
5:30:445 hours, 30 minutes, 44 secondsHere it is a casting public or private.
5:30:485 hours, 30 minutes, 48 secondsAll right. And then the last item that we need is the description item. For that again, you can copy the first one,
5:30:575 hours, 30 minutes, 57 secondsrepository name. I'm just going to go ahead and add it here. Change it to description.
5:31:065 hours, 31 minutes, 6 secondsThis field can stay the same. Change the field label to be description.
5:31:145 hours, 31 minutes, 14 secondsAnd instead of using the input, we render the text area. ID's field name stays the same. Value stays the same. On
5:31:235 hours, 31 minutes, 23 secondsblur stays the same, on change area invalid. The only thing we're going to change is the placeholder
5:31:315 hours, 31 minutes, 31 secondsas a short description of the project and rows to two. The error rendering
5:31:385 hours, 31 minutes, 38 secondsstays the same. What's left to do is the submit button. So outside of the last
5:31:445 hours, 31 minutes, 44 secondsform field render a form.subscribe with the usual selector of cansubmit and
5:31:525 hours, 31 minutes, 52 secondsis submitting. We can access those fields through a syntax like this.
5:31:585 hours, 31 minutes, 58 secondsAnd then simply render the button inside type of submit size small class name with full and disabled if you cannot
5:32:075 hours, 32 minutes, 7 secondssubmit or if you are submitting and if you are show a different label creating and the default label create repository.
5:32:185 hours, 32 minutes, 18 secondsGreat.
5:32:195 hours, 32 minutes, 19 secondsThen let's go ahead and create a function called get
5:32:265 hours, 32 minutes, 26 secondsstatus icon. So depending on the current status of the export, we are going to
5:32:335 hours, 32 minutes, 33 secondsdisplay different icons. For export status exporting, it's going to be an animated loader icon. In case it's
5:32:425 hours, 32 minutes, 42 secondscompleted, it's going to be a check check check icon with a specific emerald color. If it's failed, it's going to be X circle icon with a specific red color.
5:32:555 hours, 32 minutes, 55 secondsOtherwise, it's going to be a regular FA GitHub. All of them use the same size.
5:33:025 hours, 33 minutes, 2 secondsGreat. And now that we have that, there is only one more thing left to do. So, delete the entire dialogue here. And
5:33:105 hours, 33 minutes, 10 secondslet's do a very simple popover composition.
5:33:155 hours, 33 minutes, 15 secondsOpen and on. Open change. popover trigger as child. Let's go ahead and do
5:33:225 hours, 33 minutes, 22 secondsthe following. So uh the reason we are going to do this so we're going to create a div here with this class name
5:33:305 hours, 33 minutes, 30 secondsflex item center gap 1.5 height full px3
5:33:365 hours, 33 minutes, 36 secondscursor pointer text mute foreground border L hover bgx and 30 and inside
5:33:445 hours, 33 minutes, 44 secondswe're going to render get stat uh status icon and a span class name text small of
5:33:515 hours, 33 minutes, 51 secondsexport the reason we have this super specific class name is because this is that button. So I was just copying the styles of the tabs that we have, right?
5:34:055 hours, 34 minutes, 5 secondsThat's what I was doing right here.
5:34:075 hours, 34 minutes, 7 secondsThat's why we have this super specific class name. So yes, now when we render this, we're going to replace this old uh dummy export button, which currently
5:34:175 hours, 34 minutes, 17 secondsdoes nothing. And then outside of the popover trigger, all we ought to do is render the popover content with class in
5:34:255 hours, 34 minutes, 25 secondsV80 align start and executes the actual render content. Perfect. We are ready to wire this up.
5:34:355 hours, 34 minutes, 35 secondsFirst component we're going to add is the import dialogue. For that, we're going to go inside of source
5:34:435 hours, 34 minutes, 43 secondsfeatures, projects, components, and we're going to go inside of projects view.
5:34:515 hours, 34 minutes, 51 secondsLet's go ahead and add an import for import GitHub dialogue. We've developed it in the same folder, so we
5:35:005 hours, 35 minutescan use a very short path here. Then, let's go ahead and add a state here just beneath the command dialogue. import dialogue open. Set import dialogue open.
5:35:135 hours, 35 minutes, 13 secondsThen in the use effect here, so far we only check for a key uh of letter K. Now
5:35:215 hours, 35 minutes, 21 secondswe're also going to check for letter I, which will import the dialogue, which will open the import dialogue. My
5:35:295 hours, 35 minutes, 29 secondsapologies. Uh, okay. Make sure that we actually have the event listener. Let's
5:35:365 hours, 35 minutes, 36 secondsmake sure we actually close it. Um or maybe
5:35:435 hours, 35 minutes, 43 secondsOkay. No, I think this this is all just fine. Okay.
5:35:495 hours, 35 minutes, 49 secondsAnd now we have to render the import GitHub dialogue. We can do it just beneath the command dialogue with its
5:35:575 hours, 35 minutes, 57 secondsequivalent open import dialogue open and on open change set import dialogue open.
5:36:025 hours, 36 minutes, 2 secondsAnd while we can now open it with a shortcut, let's actually give this other empty button which fa GitHub
5:36:125 hours, 36 minutes, 12 secondsuh an on click right set import dialogue open. So right now if you go right here
5:36:205 hours, 36 minutes, 20 secondsand click on import it should show you import from GitHub. Enter a GitHub repository URL to import. A new project
5:36:295 hours, 36 minutes, 29 secondswill be created with the repository contents. Amazing. And if you try something stupid, you will see you get a
5:36:375 hours, 36 minutes, 37 secondsuh please enter a valid URL. Uh all right. So uh I will try this out. But I suggest that we try it out together.
5:36:465 hours, 36 minutes, 46 secondsLet's just finish wiring up the UI components. So one more place we have to visit is the source features projects
5:36:555 hours, 36 minutes, 55 secondscomponents project ID view. Let's go ahead and import the export popover
5:37:035 hours, 37 minutes, 3 secondswhich we've just created. It's right here in the same folder. And now let's go ahead and find the placeholder div that we have.
5:37:135 hours, 37 minutes, 13 secondsLet me find it. Here it is. So after find the tab with the label preview and
5:37:215 hours, 37 minutes, 21 secondsthen in here you will find this div class name flex one justify end. So that's good but this
5:37:295 hours, 37 minutes, 29 secondsthis is just a mock function. So go ahead and now you do you notice the
5:37:365 hours, 37 minutes, 36 secondsclass name? The class name is exactly what we've added here right it's the same class name. So we can now
5:37:455 hours, 37 minutes, 45 secondsdelete this and just render export popover with project ID. So let's quickly go into a random project just to
5:37:545 hours, 37 minutes, 54 secondssee if we can now open that popover which gives us prefilled repository name an option to change the visibility and a
5:38:025 hours, 38 minutes, 2 secondsdescription. Perfect. Now I'm going to go ahead and prepare a few repositories for us to test if there are any bugs.
5:38:115 hours, 38 minutes, 11 secondsSo I'm going to start with a random repository I have. This is a private repository. So I have to be logged in to
5:38:185 hours, 38 minutes, 18 secondstry this. So you can see the URL is github.com my name and then the repository name. And I would suggest
5:38:275 hours, 38 minutes, 27 secondsremoving forward three uh tree forward main. So you just have the repository name here. And let's click import. And now of course this is going to fail.
5:38:375 hours, 38 minutes, 37 secondsNow, uh the reason it's failing is because I don't even have injust running. My apologies.
5:38:455 hours, 38 minutes, 45 secondsSo, let me go ahead and uh well update if I need to and then we're going to see
5:38:525 hours, 38 minutes, 52 secondsuh exactly if it works or doesn't. So, I'm not sure. I think I have to import once again. There we go. Importing repository. And you can see it's already
5:39:005 hours, 39 minutescreating files. So, this is actually all working. I'm super impressed that we did this from the first try. And you can see
5:39:085 hours, 39 minutes, 8 secondsthe status is importing. And there we go. That's it. It was so fast and it worked so well that I'm in a and it's
5:39:185 hours, 39 minutes, 18 secondscompleted. There we go. So the first thing it did is it cleaned the project.
5:39:235 hours, 39 minutes, 23 secondsThen it fetched the repository. It created the folders public source and source components. And then it created
5:39:305 hours, 39 minutes, 30 secondsthe files and set the completed status and the project is finished. And in the preview here, I think we should be able
5:39:375 hours, 39 minutes, 37 secondsto also preview it. I think it's just a simple uh landing screen that I've uh generated with AI actually. Uh one thing
5:39:465 hours, 39 minutes, 46 secondswe didn't try is a binary file. So that's something that uh I'm yet to try.
5:39:525 hours, 39 minutes, 52 secondsI'm just going to create a random repository or I'm going to attempt to fetch some public repository.
5:39:595 hours, 39 minutes, 59 secondsAll right. So, I just waited so this installs. Yeah, you can see we can even preview it. And while we're here, we can
5:40:075 hours, 40 minutes, 7 secondstry exporting this or if you want to have some more fun, go ahead and create a a brand new one and simply, you know,
5:40:155 hours, 40 minutes, 15 secondsuh create a simple white plus react to-do app. Something like that. Wait for
5:40:235 hours, 40 minutes, 23 secondsit to be created and then we're going to try and export it.
5:40:275 hours, 40 minutes, 27 secondsNow that this project has been completed with AI and I have a simple to-do here, let's try exporting. So you can see that
5:40:355 hours, 40 minutes, 35 secondsthe name is already prefilled with my random project name. I'm going to set it to private and let's set the description to be uh test description and let's
5:40:445 hours, 40 minutes, 44 secondsclick create repository. So export has started and you can see that I have a cancel button if I ever want to stop it.
5:40:515 hours, 40 minutes, 51 secondsBut let's take a look at what's actually happening here. So we are getting the get GitHub user. We are creating repository. We are waiting for
5:40:595 hours, 40 minutes, 59 secondsrepository to initialize. Uh you can see it took a few attempt. Uh then we get the initial commit. We fetch project files. We create blobs. Create tree.
5:41:085 hours, 41 minutes, 8 secondsCreate commits. Update branch. Set completed status. And that's it. We successfully exported to GitHub. Let's
5:41:165 hours, 41 minutes, 16 secondsview this on GitHub. And here it is the exact file. And you can see initial commit from Polaris. The only thing I'm
5:41:245 hours, 41 minutes, 24 secondsnot seeing is the readme. Perhaps it still needs to be synced or maybe we made some mistake. We will see. But that's honestly the least important part
5:41:335 hours, 41 minutes, 33 secondsof this entire thing. It's that the files are actually in it. Perfect. So the only thing left to check is what's up with binary files.
5:41:445 hours, 41 minutes, 44 secondsSo what I've prepared is I've just uploaded a random image to one of my repositories here. I suggest you do that
5:41:535 hours, 41 minutes, 53 secondsas well. You can use upload files and just add an image. Uh, make sure it's JPEG, PNG. Basically, make sure it's not an SVG file because that's text, right?
5:42:035 hours, 42 minutes, 3 secondsMake sure it's JPEG or PNG or some other binary that you have. So, I'm just using a simple code with Antonio icon here,
5:42:115 hours, 42 minutes, 11 secondsright? And what I'm going to do is I'm going to copy the URL of this repository which has that and I'm just going to go
5:42:185 hours, 42 minutes, 18 secondsahead and import it here. So I'm going to paste it and I'm going to click import. So let's see what will happen.
5:42:265 hours, 42 minutes, 26 secondsUh will it succeed with that or not?
5:42:285 hours, 42 minutes, 28 secondsAlready I can see that there is something here. And when we click on it, we correctly see to-do implement binary
5:42:365 hours, 42 minutes, 36 secondspreview because we are not yet rendering this in any way. I'm more interested in what's here. So looks like this was
5:42:435 hours, 42 minutes, 43 secondssuccessful. It successfully created files. But let's take a look at the convex. So inside of my data here I have
5:42:525 hours, 42 minutes, 52 secondsfiles and I think that so far we shouldn't have a single file with a storage ID except one which is called images.jpeg.
5:43:045 hours, 43 minutes, 4 secondsAnd if I go inside of the actual files, this is representing your storage. You can see that inside I actually have one
5:43:125 hours, 43 minutes, 12 secondsfile. And if I go ahead and click on download here, uh I'm not sure what this is. I think this might be some mistake
5:43:225 hours, 43 minutes, 22 secondsbecause this does not look like the file I have added, but maybe it is. Maybe it's not. I'm not exactly sure. I think
5:43:305 hours, 43 minutes, 30 secondsit's because of this incorrect content type. I think something's wrong with the extension. Uh but looks like it was
5:43:375 hours, 43 minutes, 37 secondsuploaded. What I want to try now is try exporting it. So test file 1 2 3 or test
5:43:455 hours, 43 minutes, 45 secondsbinary. So I'm just exporting the exact same repository now which has images.jpeg
5:43:545 hours, 43 minutes, 54 secondsso I can see if the binary file was transferred. Perhaps there is some bug happening here. We'll leave that to the next chapter. Don't worry, it's already
5:44:025 hours, 44 minutes, 2 secondsbeen 2 hours. Uh but I just want to see if we're doing a mistake or not.
5:44:095 hours, 44 minutes, 9 secondsAll right. So I can now view the repository and I have it here and okay so it's perfectly fine the image was
5:44:185 hours, 44 minutes, 18 secondssuccessfully uploaded right so you can see that this is now test binary 123 and whatever the image was in this
5:44:275 hours, 44 minutes, 27 secondsuh repository where I've manually added it via upload it was preserved through the Polaris project through our file
5:44:365 hours, 44 minutes, 36 secondsstorage all the way to a new repository All right. So, let me go ahead. I'm not exactly sure why when I open it, it's in
5:44:445 hours, 44 minutes, 44 secondsthis weird format. Okay. When I open it on my laptop, it actually uh just opens a normal image. I should have just
5:44:525 hours, 44 minutes, 52 secondsopened it. So, everything is perfectly fine. We implemented everything correctly. Obviously, we don't have the actual preview here, but that's easy.
5:44:595 hours, 44 minutes, 59 secondsWe're just going to, you know, show an image or uh if we can't show content, we're going to say uh editor doesn't
5:45:065 hours, 45 minutes, 6 secondssupport this type of uh file. Amazing, amazing job. As you can see, when you export something, you can keep it in this state and it will even persist
5:45:145 hours, 45 minutes, 14 secondsthrough refresh, I believe. Yeah. But if you want to restart it, you can click close. Uh, and we have a bug. Okay. Oh,
5:45:235 hours, 45 minutes, 23 secondsyes. Yes. Yes. We moved those files. I forgot about that. So, inside of
5:45:305 hours, 45 minutes, 30 secondssource app API, GitHub export, we have cancel and reset.
5:45:365 hours, 45 minutes, 36 secondsOpen both of them. I think both of them should have errors. We have to give each of them
5:45:445 hours, 45 minutes, 44 secondsuh higher level. Okay, so we fixed that. Okay, easy fix.
5:45:525 hours, 45 minutes, 52 secondsI think we can now try again. Let me refresh.
5:45:575 hours, 45 minutes, 57 secondsAnd I probably have to rmrf.ext.
5:46:025 hours, 46 minutes, 2 secondsSo I clear cache and do npm rundev again.
5:46:075 hours, 46 minutes, 7 secondsand then restart because we just fixed both, right? Reset and cancel. I think it was just cache
5:46:165 hours, 46 minutes, 16 secondsthat was the problem. And if I try close now, there we go. You can see how it entirely resets.
5:46:245 hours, 46 minutes, 24 secondsAmazing. Amazing job. Let's go ahead and review and merge these changes. So
5:46:315 hours, 46 minutes, 31 secondschapter 15, I'm first going to do get checkout-b 15.
5:46:385 hours, 46 minutes, 38 secondsGitHub import export. Git add commit
5:46:445 hours, 46 minutes, 44 secondsGitHub import and export and then get push u origin 15 GitHub
5:46:545 hours, 46 minutes, 54 secondsimport export. Perfect. You can see that now we are on that branch here. And then I'm just going to go ahead onto the
5:47:035 hours, 47 minutes, 3 secondsPolaris repository. I'm going to open a pull request and let's review it.
5:47:115 hours, 47 minutes, 11 secondsAnd here is the summary by Code Rabbit.
5:47:155 hours, 47 minutes, 15 secondsNew features. We added import GitHub repositories directly into projects. We can export projects to GitHub with
5:47:235 hours, 47 minutes, 23 secondscustomizable repository settings. We have real-time status tracking for import and export operations and cancel
5:47:315 hours, 47 minutes, 31 secondsexport functionality with ability to reset export status. So let's take a look at the comments here. So the first comment is for the cleanup function.
5:47:415 hours, 47 minutes, 41 secondsRight now what we do is we simply load all the files in a project and we run them through a loop to delete them. Same
5:47:485 hours, 47 minutes, 48 secondswith their storage. But you can see that code rabbit reads the convex documentation and it knows that convex
5:47:565 hours, 47 minutes, 56 secondsenforces a 100,000 operation limit permutation that is reads and writes combined. So projects with under 50 thou
5:48:055 hours, 48 minutes, 5 secondswith over 50,000 files will fail. All right. So obviously the solution for
5:48:125 hours, 48 minutes, 12 secondsthis will be to implement batch cleanup as it said. Right now for our tutorial purposes this is perfectly fine but yes
5:48:215 hours, 48 minutes, 21 secondsyou should be aware that there are limits to convexes mutations. Same with uh wherever you deploy you know a normal
5:48:295 hours, 48 minutes, 29 secondsAPI route there are limits to how long it can run something. So perhaps this could be a job for a background job or
5:48:355 hours, 48 minutes, 35 secondsconvex workflows but for now this is okay but you should be aware that there
5:48:415 hours, 48 minutes, 41 secondsis a limit. You know, I try my best to uh bring this project as close to production as possible. I think you
5:48:505 hours, 48 minutes, 50 secondsnotice that. That's why you watch these types of videos, right? But I have to compromise here and there. Uh in this
5:48:575 hours, 48 minutes, 57 secondscase, I didn't create batching. So, I hope that when you run this project, if you do it in production, please be aware of that and of course, you know, fix it.
5:49:075 hours, 49 minutes, 7 secondsIt's a nice challenge for yourself.
5:49:105 hours, 49 minutes, 10 secondsGreat. In here, it's warning us about potential uh potentially u affected
5:49:195 hours, 49 minutes, 19 secondspeer dependencies of octokit. So, I'm not really aware of this, but yes, you could run npm audit to ensure that there
5:49:275 hours, 49 minutes, 27 secondsare no uh security issues. I think everything is mostly okay.
5:49:345 hours, 49 minutes, 34 secondsUh in here, it says the default values won't update when the project loads. Uh, but we've tested this and it does work
5:49:425 hours, 49 minutes, 42 secondscorrectly. So, I think it's confused because of our optional chaining here. I think that's what confuses it because
5:49:495 hours, 49 minutes, 49 secondsyes, uh, usually this wouldn't uh, update once it loads, but I think
5:49:565 hours, 49 minutes, 56 secondsours is already loaded at this time. So, perhaps we don't even need the optional chaining. Yes. Uh, and about this, I
5:50:045 hours, 50 minutes, 4 secondswill try to get more information in the next chapter if it's something serious, but I'm pretty sure it is not. All right.
5:50:145 hours, 50 minutes, 14 secondsAnd in here, it's basically telling us that we have a very broad catch here. So, we could mask any real errors.
5:50:235 hours, 50 minutes, 23 secondsAgain, for tutorial purposes, it's okay.
5:50:275 hours, 50 minutes, 27 secondsfor production. Yeah, you would probably want something uh a bit more
5:50:335 hours, 50 minutes, 33 secondshow do I exactly say well not so broad right because I don't even care why this failed this can fail because of the
5:50:415 hours, 50 minutes, 41 secondsbranch which is what we assume but it can also be a million other things it can be invalid owner invalid repo right
5:50:495 hours, 50 minutes, 49 secondsso that's what it's complaining about it's the fact that the moment this fails we just assume it's the branch but it can be other things. So in production
5:50:575 hours, 50 minutes, 57 secondsyou would probably check you know for the type of error and what the error returns and then do something. Same
5:51:035 hours, 51 minutes, 3 secondsthing here we do uh silent error handling. You can see the catch and just console error. So we don't really know
5:51:115 hours, 51 minutes, 11 secondswhich files have failed to error. We don't really keep track of anything. In here is a good opportunity to actually
5:51:185 hours, 51 minutes, 18 secondsuse Sentry logging for this. This could be very useful. So you can keep track of files that fail and perhaps you can then
5:51:265 hours, 51 minutes, 26 secondsextract if uh only binary files are failing or only a specific extension is failing. Right? This is where Sentry
5:51:335 hours, 51 minutes, 33 secondscould come in very very useful so you can analyze uh which problems which files cause problems the most. Other
5:51:415 hours, 51 minutes, 41 secondsthan that great great job. Let's go ahead and merge this pool request. Let's go ahead get checkout main. get pool
5:51:505 hours, 51 minutes, 50 secondsorigin main and there we go. So that marks the end of this chapter. Let's just confirm everything here is merged.
5:52:015 hours, 52 minutes, 1 secondLet's go ahead and check our graph. There we go. 14 and then 15. Perfect.
5:52:075 hours, 52 minutes, 7 secondsAnd yes, that is all. We've connected GitHub out via clerk. We built complete import system with binary file support.
5:52:155 hours, 52 minutes, 15 secondsWe created background export jobs using injust workflow. We implemented real-time status tracking with UI components and we handle repository creation and git API operations.
5:52:275 hours, 52 minutes, 27 secondsAmazing, amazing job and see you in the next chapter.
Chapter 5: 16 Billing Final Polish
5:52:315 hours, 52 minutes, 31 secondsThis is the final feature chapter before deployment. We'll add several polish features that make the app feel complete
5:52:385 hours, 52 minutes, 38 secondsand production ready. We will allow the user to trigger a new project dialogue with prompt input, allowing users to
5:52:455 hours, 52 minutes, 45 secondscreate new projects using natural language. We're going to improve our use mutation hooks with optimistic updates
5:52:535 hours, 52 minutes, 53 secondsfor instant UI feedback, making the app feel snappier and faster. We're going to implement billing, turning this project
5:53:005 hours, 53 minutesinto a real SAS, and you will learn how to protect certain premium features. In this example, we're going to protect
5:53:075 hours, 53 minutes, 7 secondsGitHub's import and export feature, but using that example, you can protect under a premium feature whatever you
5:53:145 hours, 53 minutes, 14 secondsdeem worthy of a premium tier. And then we're just going to create some uh nice warnings whenever a user tries to open a
5:53:235 hours, 53 minutes, 23 secondsbinary file, saying that we do not support the preview of that file. We can still, of course, have it in our database. We just don't support showing
5:53:305 hours, 53 minutes, 30 secondsit in the code editor. And lastly, we're going to do some AI element styling and interaction polishing.
5:53:375 hours, 53 minutes, 37 secondsSo, let's go ahead and make sure we have npm rundev running, npx convex dev, and
5:53:435 hours, 53 minutes, 43 secondsnpx inest cli latest dev. Then, let's go ahead and start by creating a convex
5:53:525 hours, 53 minutes, 52 secondssystem mutation. So, head inside of your convex folder and let's go inside of system.ds.
5:53:595 hours, 53 minutes, 59 secondsAnd at the bottom here, let's go ahead and add it as the last function. We're going to create a mutation that will be
5:54:075 hours, 54 minutes, 7 secondsused to create uh atomic creation of a project and its initial conversation. So
5:54:155 hours, 54 minutes, 15 secondsthe name will reflect that export const create project with conversation. It's
5:54:235 hours, 54 minutes, 23 secondsgoing to go be a mutation. It will accept some arguments. And let's just do a quick preparation of the handler. We
5:54:315 hours, 54 minutes, 31 secondsalready know the handler will have context and arguments. And those arguments are going to be as usual the
5:54:385 hours, 54 minutes, 38 secondsinternal key and then project name, conversation title and owner ID. Since
5:54:455 hours, 54 minutes, 45 secondsthis is a system mutation and we don't have authentication here, we have to validate the internal key to make sure
5:54:525 hours, 54 minutes, 52 secondsno uh malicious actors are trying to access this. Let's store the current date into a variable called now and
5:55:015 hours, 55 minutes, 1 secondlet's create a project by inserting into the project table with the project name owner ID and updated at to be now.
5:55:115 hours, 55 minutes, 11 secondsThen let's go ahead and create a conversation by inserting into the conversations
5:55:185 hours, 55 minutes, 18 secondstable, passing along the recently created project ID, title from the arguments, and repeating the updated at
5:55:255 hours, 55 minutes, 25 secondsvariable. Once we have those two, let's go ahead and return them all together so we can work with them since they are
5:55:325 hours, 55 minutes, 32 secondsrelated to one another. So this will be used to very simply create both the project and conversation related to that
5:55:405 hours, 55 minutes, 40 secondsproject from one function. Great. Once we have that, let's go ahead inside of
5:55:475 hours, 55 minutes, 47 secondssource app API folder. In here, let's create a new folder called projects. And then inside of the projects, let's create create with prompt.
5:55:595 hours, 55 minutes, 59 secondsAnd then in here, create a route.ts. TS let's go ahead and import everything we
5:56:065 hours, 56 minutes, 6 secondsneed zod next response from next server out and then from unique names generator
5:56:135 hours, 56 minutes, 13 secondsadjectives animals colors and unique names generator itself besides that we're going to need clients for ingest
5:56:205 hours, 56 minutes, 20 secondsand for convex make sure to import them from their paths respectively and we are going to need API from convex generated
5:56:295 hours, 56 minutes, 29 secondsAPI and we're going to need to find our default conversation title which I store in here. Let me show you in features conversations constants.
5:56:425 hours, 56 minutes, 42 secondsAll right. Now, let's go ahead and define what kind of request this API route will accept using ZOD. So, it's
5:56:495 hours, 56 minutes, 49 secondsjust going to accept a very simple prompt with a minimum length of one, meaning it's required. Let's export a post request from here. And inside of
5:56:595 hours, 56 minutes, 59 secondsthis post request, let's start with validation. So, are we currently logged in? Can we extract the user ID from clerk's out function? If we can't, let's
5:57:085 hours, 57 minutes, 8 secondsthrow an error. Then, let's go ahead and check if we have an internal key. So, we know that the environment trying to
5:57:155 hours, 57 minutes, 15 secondsaccess this convex uh mutation is a verified environment because we have no out for system queries. So, let me just
5:57:245 hours, 57 minutes, 24 secondsdouble check. Polaris convex internal key is the correct one. Great. If internal key is missing, throw 500
5:57:335 hours, 57 minutes, 33 secondsbecause this is something we should set up on the system. This isn't a user's error. This is truly an internal error if it happens. Let's go ahead and
5:57:415 hours, 57 minutes, 41 secondsextract the body and let's parse the contents of the body using the request schema zod object we've created above.
5:57:505 hours, 57 minutes, 50 secondsNow that we have a safely parsed prompt, we can go ahead and generate a random project name using the unique names
5:57:575 hours, 57 minutes, 57 secondsgenerator. So the project name will use unique names generator. I put these three dictionaries simply because this
5:58:045 hours, 58 minutes, 4 secondscombination and hyphen and three letters, I'm sorry, three words uh just create fun project names and we are consistent with all the other places
5:58:135 hours, 58 minutes, 13 secondswhere we use this. I think it's in projects view. I think it's exactly the same. Adjectives, animals, scholars, separator, adjectives, animals,
5:58:225 hours, 58 minutes, 22 secondsscholars. Yes, it's just being consistent. Now, let's go ahead and create both the project and the conversation together, which we can now
5:58:295 hours, 58 minutes, 29 secondsvery easily do by calling a specific convex mutation. Right? So, we already know we're going to return project ID
5:58:385 hours, 58 minutes, 38 secondsand conversation ID. So, let's await convex mutation API system create project with conversation. If you're not
5:58:465 hours, 58 minutes, 46 secondsgetting autocomplete here, take a look at your server here. For example, uh oh, I run npx convex. Whoops, I meant npx
5:58:555 hours, 58 minutes, 55 secondsconvex dev. So, let's go ahead and make sure you have npx convex dev running.
5:59:025 hours, 59 minutes, 2 secondsAnd you should see convex functions are ready. So, yes, in case you were having an underline here, it's because the function was not synchronized with
5:59:105 hours, 59 minutes, 10 secondsconvex. So, just make sure you have npx convex dev running.
5:59:155 hours, 59 minutes, 15 secondsNow, we have to add the JSON, right? The body. So, that's the internal key, the project name, the
5:59:245 hours, 59 minutes, 24 secondsconversation title, which we're going to just use the default conversation title, and the owner ID,
5:59:315 hours, 59 minutes, 31 secondswhich is user ID. Great. Now, we have to create the user message. Basically, uh
5:59:385 hours, 59 minutes, 38 secondswhat did the user prompt for this project? So we're going to call convex mutation API system create message. Uh
5:59:475 hours, 59 minutes, 47 secondswe have already used this a couple of times in the project specifically in API messages. So you definitely should have this in your system.ts in the convex
5:59:565 hours, 59 minutes, 56 secondsfolder. Pass along the internal key the conversation ID. This message is being stored into the project ID the role
6:00:046 hours, 4 secondswhich we can hardcode the user because right now we're just storing the prompt the natural language the user is using to explain what they want this project
6:00:126 hours, 12 secondsto be and then we immediately have to create the assistance message with a placeholder for the processing status
6:00:196 hours, 19 secondsand we should get the ID of that assistant message. So let's go ahead and prepare that
6:00:276 hours, 27 secondsby storing the assistant message ID and calling await convex.mmutation.
6:00:326 hours, 32 secondsLet's go ahead and call API dots system.create create message again just as we did above and let's pass in the
6:00:406 hours, 40 secondsinternal key the conversation ID the project ID role hardcoded to
6:00:476 hours, 47 secondsassistant content being empty and status being processing right we are about to
6:00:556 hours, 55 secondsprocess the prompt that the user just sent us and the assistant message ID will be the proper uh ID because the create message returns s the message ID.
6:01:076 hours, 1 minute, 7 secondsSo just make sure your does as well.
6:01:106 hours, 1 minute, 10 secondsGreat. Let's go back inside of the assistant message ID here. We've done that. And now what we have to do is we have to trigger the ingest job to
6:01:196 hours, 1 minute, 19 secondsprocess the message. Lucky for us, we've already developed that. So all we have to do is call the event messageward
6:01:286 hours, 1 minute, 28 secondsslash send and pass in the data. message ID being assistant message ID,
6:01:376 hours, 1 minute, 37 secondsconversation ID, project ID, and message being users prompt.
6:01:446 hours, 1 minute, 44 secondsAnd once we have that, let's return next response.json and pass in the project ID.
6:01:556 hours, 1 minute, 55 secondsSo what's important here is that you double check that you actually have this event in your project. You can see I this is the third time I'm referencing
6:02:046 hours, 2 minutes, 4 secondsthat event ID. So obviously it's the correct one. It's the processing me. It's the process message one in here.
6:02:116 hours, 2 minutes, 11 secondsWhat's important is please just check that this message event is correct. So message ID, conversation ID, project ID, message. Make sure that you don't
6:02:196 hours, 2 minutes, 19 secondsaccidentally misspell something here because there's nothing stopping you. As you can see, you can type whatever you want. It's not going to throw you an error. So be careful, okay?
6:02:306 hours, 2 minutes, 30 secondsbecause the bugs around this might be a little funny, right? Okay. So, now that we have that, let's go ahead and
6:02:386 hours, 2 minutes, 38 secondsimplement the UI for this dialogue so we can actually test it out. So, we're going to go inside of source features
6:02:456 hours, 2 minutes, 45 secondsprojects. Let's go inside of components and let's create a new file, new project dialogue.
6:02:536 hours, 2 minutes, 53 secondsDSX.
6:02:556 hours, 2 minutes, 55 secondsLet's go ahead and mark it as use client. Let's go ahead and import use effect use state KY toast and use router
6:03:046 hours, 3 minutes, 4 secondsfrom next navigation. Let's import dialogue dialogue content description header and title. And then from the
6:03:146 hours, 3 minutes, 14 secondsspecific components AI element prompt input which we've added by installing AI
6:03:206 hours, 3 minutes, 20 secondselements. Uh I'm not sure if that's actually we I think we run shad CN installation on it. But basically you
6:03:296 hours, 3 minutes, 29 secondsshould already have AI elements. If you don't you can just uh it is basically from AI SDK AI elements. We already have
6:03:386 hours, 3 minutes, 38 secondsthem in our projects because we have been using it in the chat sidebar. My apologies. Conversations sidebar.
6:03:456 hours, 3 minutes, 45 secondsSo let me just scroll up. There we go.
6:03:476 hours, 3 minutes, 47 secondsYou can see we already used AI elements conversations uh and AI elements message and prompt input and now we are again importing
6:03:566 hours, 3 minutes, 56 secondsfrom prompt input. So that's where we got that. Let's go ahead and prepare the ID from generated data model. Let's
6:04:046 hours, 4 minutes, 4 secondscreate the interface new project dialogue props which will accept open and onopen change. And then in here
6:04:126 hours, 4 minutes, 12 secondslet's go ahead and export the actual component.
6:04:166 hours, 4 minutes, 16 secondsSo this is the usual scenario right almost every dialogue popover has the open and unopen change that's simply because we are creating an abstraction
6:04:246 hours, 4 minutes, 24 secondsover the composition that shaten has given us which is al always having an
6:04:316 hours, 4 minutes, 31 secondsopen and unopen change prop. So let's go ahead and prepare the router hook so we can easily redirect once the uh project
6:04:396 hours, 4 minutes, 39 secondsis created. Let's prepare the user's input value here and let's go ahead and give them a little submitting state for
6:04:466 hours, 4 minutes, 46 secondsa nicer uh user experience. Now we have to develop the actual handle submit method. So that's going to be an asynchronous method and its message or
6:04:556 hours, 4 minutes, 55 secondsits value right its prop will be a type of prompt input message which we have imported as a type here from the prompt input. Now the handle submit will first
6:05:046 hours, 5 minutes, 4 secondscheck if there is no message.ext and if there isn't any it's just going to return. Then let's go ahead and set is
6:05:116 hours, 5 minutes, 11 secondssubmitting to true. And let's open a try and catch block.
6:05:166 hours, 5 minutes, 16 secondsInside of the try block, let's go ahead and call await ky.post
6:05:246 hours, 5 minutes, 24 secondsAPI projects create with prompt. So this
6:05:316 hours, 5 minutes, 31 secondsshould match 100% what you've written here. App folder API projects create with prompt. Make sure
6:05:406 hours, 5 minutes, 40 secondsthere are no misspellings in this folder name and no misspellings in here. Create with prompt and route.ts is a required
6:05:476 hours, 5 minutes, 47 secondsfile name. So make sure you didn't accidentally misspell any of that. We already know what we are going to extract from here. The project ID. So we
6:05:566 hours, 5 minutes, 56 secondscan prepare that. And then let's just go ahead and add some body to this post.
6:06:026 hours, 6 minutes, 2 secondsSo, we're going to be using JSON and we will pass along the prompt which is going to be message.ext and just trim
6:06:106 hours, 6 minutes, 10 secondsit. Great. And then we can go ahead and actually request JSON back. And to make it type safe, we can go ahead and cast a
6:06:206 hours, 6 minutes, 20 secondstype project ID to be a type of ID projects. And just like that, when you hover over project ID here, it has the
6:06:276 hours, 6 minutes, 27 secondscorrect type. And if you actually look in the route.ts DS of the create with prompt. You can see we do return the
6:06:356 hours, 6 minutes, 35 secondsproject ID. Perfect. So now our front end is completely synchronized with the back end. After that happens, we can go
6:06:426 hours, 6 minutes, 42 secondsahead and render a toast success project created. We can close the model. We can
6:06:496 hours, 6 minutes, 49 secondsset the input to be empty. And finally, we can push to projects project ID. If
6:06:576 hours, 6 minutes, 57 secondscatch happens, it's most likely because of an internal error or some invalid data. So let's just say unable to create
6:07:056 hours, 7 minutes, 5 secondsproject. And in the finally block set is submitting to false. So regardless if this fails or succeeds, it will be reset.
6:07:156 hours, 7 minutes, 15 secondsNow let's go ahead and actually uh do the composition of a dialogue. So we can render it. So using the dialogue component which we've imported above,
6:07:246 hours, 7 minutes, 24 secondslet's give it an open and unopen change prop. Then let's go ahead and write the
6:07:306 hours, 7 minutes, 30 secondsdialogue content with show close button being false and class name being on
6:07:396 hours, 7 minutes, 39 secondssmall, maximum width is large and padding is zero. Then let's go ahead and open a dialogue header. And I'm just
6:07:486 hours, 7 minutes, 48 secondsgoing to go ahead and give it a class name of hidden. But it's a good recommendation to still add the title and the description for accessibility.
6:07:576 hours, 7 minutes, 57 secondsSo screen readers can access it. So it's not going to be visible, but screen readers can say what this model is doing. Great. Now, outside of the
6:08:056 hours, 8 minutes, 5 secondsdialogue header, let's go ahead and create a prompt input. And let's give it an onsubmit of handle submit and a class
6:08:136 hours, 8 minutes, 13 secondsname border none with an exclamation point at the end marking it as important. Inside let's go ahead and
6:08:196 hours, 8 minutes, 19 secondsrender prompt input body. And then let's go ahead and render prompt input text area with a placeholder ask polaris to
6:08:286 hours, 8 minutes, 28 secondsbuild on change. Set the input to events target value. synchronize the value binding to input and disabled is
6:08:376 hours, 8 minutes, 37 secondssubmitting and then let's go ahead and open uh the prompt input footer. Let's go ahead and
6:08:466 hours, 8 minutes, 46 secondsrender the tools and finally the submit button which is going to be disabled if user didn't type anything or if we are
6:08:546 hours, 8 minutes, 54 secondsin the process of submitting so the user cannot spam. Uh, great. That is the UI component. And now let's wire it up so
6:09:026 hours, 9 minutes, 2 secondswe can test if it works. So we have to go inside of projects components and we have to find the projects view right here.
6:09:126 hours, 9 minutes, 12 secondsLet's start by adding the import first.
6:09:156 hours, 9 minutes, 15 secondsSo I'm just going to add new project dialogue.
6:09:196 hours, 9 minutes, 19 secondsAnd I'm just going to go ahead and render new project dialogue like we usually do.
6:09:266 hours, 9 minutes, 26 secondsand we need to have a state for it. So, new project dialogue set new project dialogue use state false. Let's go ahead
6:09:346 hours, 9 minutes, 34 secondsand create a little uh helper function here. Handle new project open change open set new project dialogue open.
6:09:456 hours, 9 minutes, 45 secondsAnd let's go ahead and add another if here if event.key is letter J. You can of course modify
6:09:526 hours, 9 minutes, 52 secondsthese hotkeys. Let's go ahead and prevent default and let's set new project dialogue to be true. So we can now open it the hotkey. Perfect.
6:10:066 hours, 10 minutes, 6 secondsAnd uh I'm not sure if we even need handle new project open change. I think this is simple enough.
6:10:136 hours, 10 minutes, 13 secondsSo in the new project dialogue here, let's add this to be open. and on open change uh set new project dialogue open.
6:10:246 hours, 10 minutes, 24 secondsAs simple as that. Great. Now what we have to do is we have to find a button which is this one which right now just
6:10:326 hours, 10 minutes, 32 secondscreates a new project. So that's actually not going to be the case anymore. Instead what's going to happen is set new project dialogue open will be
6:10:426 hours, 10 minutes, 42 secondsset to true. And I don't think we have to do anything else here. I think we can just test it out. Let me just see if we can
6:10:506 hours, 10 minutes, 50 secondsnow remove this import. Looks like we can. Perfect. We can remove use create project and the import. So, let's try it
6:10:596 hours, 10 minutes, 59 secondsout now. I think this should work just fine. Just make sure you have your ingest running. Make sure you have the necessary credits. Let's try a shortcut.
6:11:076 hours, 11 minutes, 7 secondsThere we go. So, ask Polaris to build a simple React Plus V to-do app. And once you click enter, it should redirect you
6:11:166 hours, 11 minutes, 16 secondsto that project. And you can see that a new conversation has already been established. The title has been created and the AI is currently thinking and it
6:11:246 hours, 11 minutes, 24 secondsshould start creating the code any moment.
6:11:286 hours, 11 minutes, 28 secondsAnd here we go. Just like that, we have kind of um improved the user experience so that
6:11:376 hours, 11 minutes, 37 secondsthey don't have to first create a new project. They can like immediately prompt it, right? And it's just a
6:11:436 hours, 11 minutes, 43 secondsregular to-do app. Uh great. So what we have to do uh next is um improve all of
6:11:536 hours, 11 minutes, 53 secondsthe missing optimistic updates. So I think when you search for to-do in your app you will see we have a bunch of
6:12:006 hours, 12 minutesthese optimistic mutation ones most of them instead of use files. So let's go instead of use files and see how we can
6:12:066 hours, 12 minutes, 6 secondsimprove that. Basically this isn't required. It will just make the app feel snappier right. So let's make sure we
6:12:156 hours, 12 minutes, 15 secondshave use mutation, use query ID, and API. We have all of that. And let's now add a little helper function, which
6:12:236 hours, 12 minutes, 23 secondswe're going to need since when we are optimistically updating, we have to simulate the same behavior as on the server. So we're going to implement a
6:12:326 hours, 12 minutes, 32 secondsfunction to sort files, folders first, then files alphabetically within each group. That's the logic we're going to
6:12:406 hours, 12 minutes, 40 secondsbe using. So let's go ahead and define uh sort files
6:12:466 hours, 12 minutes, 46 secondsand let's go ahead and prepare a type here. So t extends
6:12:566 hours, 12 minutes, 56 secondstype which can be either file or folder name which is a type of string. So
6:13:046 hours, 13 minutes, 4 secondsthat's where we're going to have files which are going to be an array of that type and we expect back an array of that
6:13:126 hours, 13 minutes, 12 secondstype. So inside of here, let's go ahead and return spread files
6:13:186 hours, 13 minutes, 18 secondssort them. So you have two files now. If first one is a type of folder and the
6:13:276 hours, 13 minutes, 27 secondssecond one is a type of file return minus one which will sort them folders first. If first one is a type of file
6:13:376 hours, 13 minutes, 37 secondsand the second one is a type of folder return one which will do the opposite meaning again sorting folders first and
6:13:466 hours, 13 minutes, 46 secondsfor the rest let's go ahead and do localal compare. So we sort
6:13:536 hours, 13 minutes, 53 secondsalphabetically within groups. Great. So a little helper functions here. So let's
6:13:586 hours, 13 minutes, 58 secondsstart by finding uh use delete file. So in here what we can do now in use
6:14:076 hours, 14 minutes, 7 secondsmutation is call with optimistic update. And in here we
6:14:146 hours, 14 minutes, 14 secondshave local store and we have the arguments.
6:14:226 hours, 14 minutes, 22 secondsAnd then what we're going to do is we're going to get the existing files from local store
6:14:316 hours, 14 minutes, 31 secondsget query API files get folder contents and in here pass in the project ID which
6:14:416 hours, 14 minutes, 41 secondswill be arguments project ID. Let's see if we have that or not. Uh looks like it doesn't accept that.
6:14:526 hours, 14 minutes, 52 secondsSo what we have to do is we have to extend use delete file. So let's go ahead and extend it by accepting project
6:15:006 hours, 15 minutesID and parent ID because the problem is in the arguments we only have the ID of the file itself. So in order to make the
6:15:096 hours, 15 minutes, 9 secondsoptimistic update work, we have to find a way to make the uh hook aware of the
6:15:176 hours, 15 minutes, 17 secondsproject ID and the parent ID. And that's kind of a problem. I'm going to show you why. So make sure parent ID is optional here. And let's now continue developing.
6:15:306 hours, 15 minutes, 30 secondsSo now we know what project ID is. We know what parent ID is. And now we can load the existing files. And now what
6:15:396 hours, 15 minutes, 39 secondswe're going to do is just check if existing files are not undefined, meaning they have loaded. Let's do local
6:15:486 hours, 15 minutes, 48 secondsstore set query and let's do API files get folder contents
6:15:576 hours, 15 minutes, 57 secondsproject ID parent ID existing files dot filter let me just
6:16:046 hours, 16 minutes, 4 secondsfix the typo existing files filter get the individual file and check if
6:16:126 hours, 16 minutes, 12 secondsfile ID matches arguments ID does not match arguments ID. All right.
6:16:196 hours, 16 minutes, 19 secondsSo what this is doing is it is simulating what the actual backend function this one delete file is going
6:16:286 hours, 16 minutes, 28 secondsto do. But it is just simulating that, right? But you can already see that this might not be the greatest of examples
6:16:366 hours, 16 minutes, 36 secondssimply because um we should also kind of hide all its recursive children elements
6:16:446 hours, 16 minutes, 44 secondswhich isn't too big of a problem because on the front end I think the UI immediately hides that but uh let's actually try it out to see the example
6:16:536 hours, 16 minutes, 53 secondsand why you would want optimistic update or maybe you prefer not doing it. So the first kind of uh caveat is that you have to complicate the developer experience.
6:17:046 hours, 17 minutes, 4 secondsSo if you search for use delete file in your project, you will find that you use it inside of tree.tsx.
6:17:116 hours, 17 minutes, 11 secondsSo let's go ahead and add it here. You can see that now I have an error here because I have to extend it with the project ID and the parent ID item. ID.
6:17:226 hours, 17 minutes, 22 secondsSo let's see the difference. For example, let me open one of the existing projects here. And you can see that now when I delete it is instant and I mean
6:17:316 hours, 17 minutes, 31 secondsinstant absolutely instant faster than the actual uh back end. So let's see the difference. So let's try you know commenting with optimistic update out.
6:17:446 hours, 17 minutes, 44 secondsIt's still going to be fast because convex is fast right? Let me refresh just in case. But you will see like a
6:17:506 hours, 17 minutes, 50 secondsvery slight delay. See it's very very small but it is visible. Whereas vit
6:17:586 hours, 17 minutes, 58 secondsoptimistic update is absolutely instant but that's not the only thing. So for example let's say uh that we want to
6:18:076 hours, 18 minutes, 7 secondsthrow an error if whoops if true. So let's simulate this. Let's always throw an error. What
6:18:166 hours, 18 minutes, 16 secondshappens then? Still optimistic update will immediately delete it but then it should bring it back. You can see that's
6:18:236 hours, 18 minutes, 23 secondswhat happens. That's the power of optimistic update. So it tells the it gives the user an idea of what was supposed to happen but it has the ability to roll back if it goes wrong.
6:18:346 hours, 18 minutes, 34 secondsSo it's up to you if you want this compromise or not. I personally think optimistic updates really really make
6:18:416 hours, 18 minutes, 41 secondsthe appear faster uh because it for the user it's almost like there's there are no network requests right for the user
6:18:496 hours, 18 minutes, 49 secondsthe moment you hit it it happens instantly now when it actually happens might be 5 seconds from now right the user doesn't even know that your app is
6:18:586 hours, 18 minutes, 58 secondsslow simply because you've done a good job with optimistic updates but the caveat is that we can see you kind of have a more complicated ated example here.
6:19:096 hours, 19 minutes, 9 secondsUh so if you want to, you can uh follow along to see me develop the rest of these. So rename file. I'm going to extend it with the exact same props
6:19:176 hours, 19 minutes, 17 secondshere. And I'm going to go back inside of uh use files here. And I will add the exact same props here. So project ID and
6:19:266 hours, 19 minutes, 26 secondsparent ID, which is optional. And I'm going to go ahead and do the exact same extension local store and arguments.
6:19:386 hours, 19 minutes, 38 secondsWe're going to fetch the existing files.
6:19:416 hours, 19 minutes, 41 secondsBut first, let's just check instead of arguments. Okay, so we only have ID and new name. Sometimes you don't even need to pass these simply because you have
6:19:486 hours, 19 minutes, 48 secondsthem in arguments. But in this case, we do need to pass them.
6:19:526 hours, 19 minutes, 52 secondsAnd now what we're doing here is again checking if the existing files have loaded. Since uh in convex the result is
6:20:006 hours, 20 minutesnever undefined. It's either a result or null. If it's undefined, it means it's loading. So now let's go ahead and go uh
6:20:096 hours, 20 minutes, 9 secondsupdate our files. So we're just going to go ahead and go over existing files and when we find our file with the ID, let's
6:20:196 hours, 20 minutes, 19 secondssimply change the name using arguments new name. And for for all other files just return their current state. And
6:20:286 hours, 20 minutes, 28 secondsonce we have the updated files, we can simply add it to the local store using set query API files get folder contents
6:20:366 hours, 20 minutes, 36 secondswith project ID and parent ID. And very important, you now have to sort files again because you can change the
6:20:426 hours, 20 minutes, 42 secondsalphabetic order, right? So that's kind of the complexity that we have to do here. Okay, let me see if I'm forgetting
6:20:516 hours, 20 minutes, 51 secondsuh to close something. We have this. We have this.
6:20:596 hours, 20 minutes, 59 secondsAm I missing something? Let me see. Expression is expected.
6:21:066 hours, 21 minutes, 6 secondsSo, okay, let me just check why this is throwing.
6:21:126 hours, 21 minutes, 12 secondsI'm probably missing some something. Well, definitely missing something. Let's see. Use mutation API
6:21:206 hours, 21 minutes, 20 secondsfile is renamed file with optimistic update. This seems to end correctly. And then we open this. That seems to end
6:21:306 hours, 21 minutes, 30 secondscorrectly too. Local story local store get query API.files.get
6:21:376 hours, 21 minutes, 37 secondsfolder contents. Is that maybe problematic? I don't think it is.
6:21:426 hours, 21 minutes, 42 secondsThat seems to end as well. Then we have this. We have this dot map. Let me see
6:21:496 hours, 21 minutes, 49 secondsif the dot map might be problematic. Uh, are we maybe missing something here? No.
6:21:586 hours, 21 minutes, 58 secondsH I'm trying to figure out what's the error.
6:22:056 hours, 22 minutes, 5 secondsLet me see if the error is even in this file.
6:22:096 hours, 22 minutes, 9 secondsIt is definitely. Okay. Oh, I should not add a semicolon there.
6:22:166 hours, 22 minutes, 16 secondsGreat. So now the rename is also instant, right? So if I change this to instant, you can see it's immediately
6:22:246 hours, 22 minutes, 24 secondsrenamed. If I go ahead and change it to alphabetically, you can see it's immediately sorted to the top much faster than if you were to
6:22:326 hours, 22 minutes, 32 secondswait for a request to happen. Right? So that's the gist of optimistic updates.
6:22:376 hours, 22 minutes, 37 secondsThey miss basically make your appear faster than they actually are. So a few more places to do this. Uh delete uh
6:22:466 hours, 22 minutes, 46 secondslet's see create file. Yes. So project ID and parent ID. Save that. Let's go inside of use create file. Let's go ahead and prepare the props here.
6:22:566 hours, 22 minutes, 56 secondsProject ID and parent ID. And let's go ahead and prepare the width optimistic m uh mutation.
6:23:086 hours, 23 minutes, 8 secondsOkay, let's check what we have in the arguments. So, for example, in here we have the project ID in the arguments.
6:23:166 hours, 23 minutes, 16 secondsSo, we actually don't need to pass it here, which kind of simplifies things on this end, but we still don't have the
6:23:236 hours, 23 minutes, 23 secondsparent ID. Yes, I as I said, I mean, the the developer experience is a little bit worse, but it might be worth it. And
6:23:326 hours, 23 minutes, 32 secondsthen here for the project ID, you're just going to use arguments.p project ID because you can
6:23:396 hours, 23 minutes, 39 secondsuh okay. And now that we have the existing files here, let's go ahead and again check if the existing files have
6:23:476 hours, 23 minutes, 47 secondsactually loaded. And we're just going to simulate creating a new file now. So
6:23:536 hours, 23 minutes, 53 secondslet's go ahead and create an object for the new file. Let's go ahead and mock a
6:24:006 hours, 24 minutesrandom ID. Let's mock random creation time. Uh project ID.
6:24:096 hours, 24 minutes, 9 secondsUh oh, do we have parent ID in the arguments? Let me see. Oh, we also have parent ID. Great. So, we don't need any of them in the create file then. My bad.
6:24:216 hours, 24 minutes, 21 secondsYeah, some of them work just the way they do. So, arguments parent ID. Great.
6:24:276 hours, 24 minutes, 27 secondsThat's even better. So, parent ID, let's go ahead and add name and content.
6:24:346 hours, 24 minutes, 34 secondsUh, let's make the type B file updated at now. And let's go ahead and fix this
6:24:426 hours, 24 minutes, 42 secondserror by adding slint disable next line react hooks purity and say optimistic
6:24:526 hours, 24 minutes, 52 secondsupdate callback runs on mutation not on render to explain why this is okay.
6:25:016 hours, 25 minutes, 1 secondGreat. And then let's just go ahead and update the local store with the new file. So local store set query project
6:25:106 hours, 25 minutes, 10 secondsID arguments project ID parent ID arguments parent ID and then make sure to sort files and just append the new
6:25:196 hours, 25 minutes, 19 secondsfile here. So then again you will see this works instantly too. If I go ahead here new file something ts instantly
6:25:276 hours, 25 minutes, 27 secondsadded right there's no uh question about it. It works super super fast. Uh great.
6:25:346 hours, 25 minutes, 34 secondsSo that's it for the use create file and it is almost identical to uh use create
6:25:436 hours, 25 minutes, 43 secondsfolder. Let me see inside of use files if I scroll down here create folder we have the parent ID and we have the
6:25:506 hours, 25 minutes, 50 secondsproject ID. So we don't have to extend this at all. Uh, in fact, I'm pretty sure we can just copy the entire width
6:26:006 hours, 26 minutesoptimistic update here and chain it here like so. We're just going to make it a little bit different. Uh, so the
6:26:086 hours, 26 minutes, 8 secondsexisting files all good. This is all good. Instead of new file, this should be called new
6:26:166 hours, 26 minutes, 16 secondsfolder just so we stay true to what we're actually developing. The type should be folder. there are there is no content and this should be new folder.
6:26:286 hours, 26 minutes, 28 secondsSo again the exact same behavior. Now if I go ahead and create a new folder super fast
6:26:356 hours, 26 minutes, 35 secondsimmediately created right and again uh the same is true if I for example go inside of files let me see create file.
6:26:436 hours, 26 minutes, 43 secondsIf I go here and if I decide to throw an error every single time you can see what happens. So new file.ts immediately it
6:26:526 hours, 26 minutes, 52 secondsgets created and then it's reverted right. So optimistic update from convex handles all of that. It really makes the
6:27:006 hours, 27 minutesapp feel just that much faster. All right. And here's what I would give you as a challenge now. Uh I mean if you
6:27:096 hours, 27 minutes, 9 secondswant to we can uh you can just watch me do it but try and do it for project creation. Right? if you want to. You can
6:27:176 hours, 27 minutes, 17 secondssee it takes like a second before it's created here. Uh but it's not terribly
6:27:246 hours, 27 minutes, 24 secondsimportant for it to exist here simply because you can see that even uh when it's created we actually get redirected there. Right? So it's not really
6:27:326 hours, 27 minutes, 32 secondsimportant that the user instantly sees it in here. So we would implement this
6:27:386 hours, 27 minutes, 38 secondsinside of conversations hooks use conversation. it would be uh use create
6:27:456 hours, 27 minutes, 45 secondsconversation and let's see uh so you just need to use the argument project ID so if you want to pause the screen and
6:27:536 hours, 27 minutes, 53 secondstry and implement optimistic mutation for use create conversation and then I'm going to show you the result
6:28:006 hours, 28 minutesokay so for those of you who want to see the result this is it uh so we will start by loading the existing
6:28:096 hours, 28 minutes, 9 secondsconversations we will map arguments project ID here the date. Now we can just copy whatever excuse we had from the use files, right?
6:28:206 hours, 28 minutes, 20 secondsSo we get rid of that like so. And we are just creating a new conversation object here. And again map the project ID as arguments project ID.
6:28:326 hours, 28 minutes, 32 secondsAnd you are updating the query get by project. Uh and don't feel discouraged if you didn't manage to get this
6:28:416 hours, 28 minutes, 41 secondsyourself. The truth is this would be way easier if we added these optimistic updates when we developed these hooks
6:28:496 hours, 28 minutes, 49 secondsbecause right now it's kind of hard to recall like why am I setting query in get by project? How are you supposed to
6:28:566 hours, 28 minutes, 56 secondsknow that? Yeah, I I now realize it's probably not that clear to you uh why we're doing this. Yes, obviously I
6:29:046 hours, 29 minutes, 4 secondshave access to the original source code so I can see how it's going to look like. But yes, uh I just hope you understood that you basically have to
6:29:126 hours, 29 minutes, 12 secondscreate a new conversation and set it to the local query in a very specific cache. In this case, it is get by project cache. That's the one uh we want.
6:29:226 hours, 29 minutes, 22 secondsSo actually what I showed you before was incorrect. This is the scenario when you click on uh plus it will immediately
6:29:316 hours, 29 minutes, 31 secondskind of appear here. As I said the optimistic mutation is not required everywhere, right? In some places it
6:29:386 hours, 29 minutes, 38 secondsmakes no sense to have it. For example, here I don't think anyone will will really see the benefit, but in the files
6:29:456 hours, 29 minutes, 45 secondsone in the file explorer, it really makes sense because it makes the app feel that much faster.
6:29:526 hours, 29 minutes, 52 secondsAll right, so let me see uh if we have anything here. Looks like we have another optimistic mutation. Here's an example of where we really don't need
6:30:006 hours, 30 minutesit. Update project settings. Really no need, right? I think actually the only ones that made sense here were use
6:30:076 hours, 30 minutes, 7 secondsfiles. Even this last one in use conversation which I told you to try and do yourself in my opinion. You can even decide to not do it. I don't think
6:30:166 hours, 30 minutes, 16 secondsthere's much benefit to it. It's just a good exercise but not much sense in my opinion. All right.
6:30:236 hours, 30 minutes, 23 secondsSo, uh what I want to do now is I want to try and find that project I had uh
6:30:316 hours, 30 minutes, 31 secondswhich featured an image. So right now I have this very kind of ugly uh to-do
6:30:396 hours, 30 minutes, 39 secondsimplement binary preview. So how about we just implement a nice error screen or a nice warning. So I'm just going to
6:30:476 hours, 30 minutes, 47 secondsclose everything here and I'm going to find editor view inside of features editor components editor view. And here
6:30:566 hours, 30 minutes, 56 secondsit is is active file binary. So what we're going to do is something uh much nicer. Let's go ahead and start with a
6:31:056 hours, 31 minutes, 5 secondscontainer. So, a div class name size full flex items center and justify center.
6:31:166 hours, 31 minutes, 16 secondsThen inside of here, another div with flex flex column items center gap 2.5 maximum width of medium and text center.
6:31:266 hours, 31 minutes, 26 secondsThen let's render an alert triangle icon from Lucid React with size 10 and text yellow 500 like this. And let's go ahead and display a paragraph below. Whoops.
6:31:406 hours, 31 minutes, 40 secondsSo below the triangle a paragraph with text small which will very simply say uh
6:31:486 hours, 31 minutes, 48 secondsthe file is not displayed in the text editor because it is either binary or
6:31:556 hours, 31 minutes, 55 secondsuses an unsupported text encoding like this. So just some warning to the user like hey this is why that is happening.
6:32:056 hours, 32 minutes, 5 secondsYou can of course tweak this to make it look better especially on smaller uh devices.
6:32:106 hours, 32 minutes, 10 secondsMaybe even make the triangle smaller, larger, however you prefer. Great. Now, it's time to add premium uh features.
6:32:196 hours, 32 minutes, 19 secondsRight now, this export functionality and the import functionality work just fine.
6:32:256 hours, 32 minutes, 25 secondsSo, what I want to do is I want to protect them. So, head to your clerk's dashboard and click on the billing tab
6:32:336 hours, 32 minutes, 33 secondsand let's click on get started. So in here, let's go ahead and click on enable user billing and see if we even have
6:32:416 hours, 32 minutes, 41 secondsthat available. And let's click save. Uh okay. So if this wasn't available for you, there's a chance it is because you
6:32:506 hours, 32 minutes, 50 secondsdon't allow um let me see user authentication. You don't allow sign up and sign in with email. So in order for billing to work, you need to allow signing in with email.
6:33:026 hours, 33 minutes, 2 secondsYou need to allow the required email address. So just look at my settings and make sure you have them like that. I mean the clerk will tell you that when
6:33:106 hours, 33 minutes, 10 secondsyou try to enable billing. Great. So once uh this is enabled, we have to create some subscription plans. They
6:33:196 hours, 33 minutes, 19 secondsalready created one for you which is the free tier.
6:33:236 hours, 33 minutes, 23 secondsAnd now we're just going to create a new one. And we're just going to call this pro. And let the key be pro. In the
6:33:316 hours, 33 minutes, 31 secondsdescription, we're going to say this is a pro plan unlocking
6:33:376 hours, 33 minutes, 37 secondspremium features of Polaris monthly base fee. Let's go ahead and set it to like $29.99. You can automatically create an
6:33:466 hours, 33 minutes, 46 secondsannual discount. Whoops, that is not the price I intended. You can automatically set a annual discount. So, for example,
6:33:546 hours, 33 minutes, 54 secondsif someone uh wants to pay a a year in advance, you can go
6:34:016 hours, 34 minutes, 1 secondahead and give them a different deal, right? You can also enable free trial if you want to as well. So, let's go ahead
6:34:106 hours, 34 minutes, 10 secondsand save that. You don't really need to add features for our use case, but if you want to, you could uh specify exactly what plan has what features.
6:34:206 hours, 34 minutes, 20 secondsAnd once you have at least one plan, it's important that you remember the key for this plan, which in our case is pro.
6:34:296 hours, 34 minutes, 29 secondsSo for example, let's go ahead and try something now. Once we have that enabled, let's go inside of import
6:34:366 hours, 34 minutes, 36 secondsroute. DS and in here, so far what we do is we just check for the user ID. But you can
6:34:456 hours, 34 minutes, 45 secondsalso extract has from here. So now let's go ahead and first check if we have the user ID and then let's do has pro to be
6:34:546 hours, 34 minutes, 54 secondshas plan pro. This is the key that's important and if the user doesn't have
6:35:016 hours, 35 minutes, 1 secondpro return next response JSON
6:35:096 hours, 35 minutes, 9 secondserror pro plan required with a status 403.
6:35:166 hours, 35 minutes, 16 secondsAs simple as that. So, I'm going to go ahead and try do that now. So, I'm going to I
6:35:246 hours, 35 minutes, 24 secondsthink it might be a good idea to just restart your app simply because we just enabled something in Clerk. So, just to make sure it still works. So, let's
6:35:326 hours, 35 minutes, 32 secondsrestart. Let's go ahead and try and clone something. github.com
6:35:396 hours, 35 minutes, 39 secondscode with Antonio Polaris. Let's click import. And you can see we have an error. unable to import repository and
6:35:476 hours, 35 minutes, 47 secondsyou can see the result is 403 that is because I should not be able to do that I don't have the pro plan right
6:35:576 hours, 35 minutes, 57 secondsso now let me just go ahead and also add this to one more feature so we can wrap up our backend coding let's just add it
6:36:056 hours, 36 minutes, 5 secondsto export for example right so after we check for that check for has and extract
6:36:136 hours, 36 minutes, 13 secondshas from await off and make sure you add it. So, as simple as that. And make sure you throw an error called pro plan
6:36:206 hours, 36 minutes, 20 secondsrequired because again, we're going to use that to check on the front end if we should tell to the user a specific thing. So now let's go inside of the
6:36:296 hours, 36 minutes, 29 secondsimport GitHub dialogue component. And in here we can catch errors, right? So we already catch if the error says GitHub uh not connected.
6:36:436 hours, 36 minutes, 43 secondsBut now let's go ahead and do prop plan required
6:36:496 hours, 36 minutes, 49 secondslike this. So if body error includes prop plan required and the body doesn't
6:36:566 hours, 36 minutes, 56 secondsneed the optional chain method. Let's throw toast error upgrade to import repositories.
6:37:066 hours, 37 minutes, 6 secondsAnd let's add an action label upgrade on click
6:37:136 hours, 37 minutes, 13 secondsopen user profile like so. And let's go ahead and call on
6:37:216 hours, 37 minutes, 21 secondsopen change set to false. And let's do an early return. So now we don't need to do this in an else if. So let's try it
6:37:306 hours, 37 minutes, 30 secondsout. Let's see what happens. If I try import now, you can see it says upgrade to import repositories. And then I have
6:37:386 hours, 37 minutes, 38 secondsto go inside of what I now have which is billing. And in here I have to switch plans. So for example, if I want to do
6:37:456 hours, 37 minutes, 45 secondsmonthly, it's 29. If I enable annually, it switches to 10. I can subscribe and I
6:37:526 hours, 37 minutes, 52 secondsimmediately have pay with test card mode right here. And just like that, payment was successful. If your hangs and it
6:38:016 hours, 38 minutes, 1 seconddoesn't work, it could be because you have an error here which will tell you that you don't have proper uh course set
6:38:096 hours, 38 minutes, 9 secondsup. This is why it was important for us to properly configure the next config to
6:38:166 hours, 38 minutes, 16 secondsuse credentialless because if you use uh require corp I think that's the other one then it will block stripe from being
6:38:256 hours, 38 minutes, 25 secondsable to work. So, make sure you put credentialless or if it's still not working, uh, try deleting the headers
6:38:326 hours, 38 minutes, 32 secondsentirely or or specifically maybe make them inside of projects like this. Then
6:38:396 hours, 38 minutes, 39 secondsit shouldn't matter which one you use because the upgrade one is on this one.
6:38:456 hours, 38 minutes, 45 secondsBut still, regardless of what you do here, I would recommend using credentials because you never know where the user might get the update prompt.
6:38:546 hours, 38 minutes, 54 secondsUh, great. So now this should work. Let me go ahead and try it. Um but since
6:39:026 hours, 39 minutes, 2 secondsthis is going to be a long action, I will open localhost 8288.
6:39:106 hours, 39 minutes, 10 secondsLet's try code with oops github.com code with Antonio Polaris. So I'm trying to
6:39:196 hours, 39 minutes, 19 secondsimport this very source code. You can see now it works and yeah. Okay, it's fetching the repo and I'm just going to cancel it because it's a big repository
6:39:286 hours, 39 minutes, 28 secondsso it's going to take a while for it to load. You can see it's trying to replicate all the folders already. Uh, great. But that works. Uh, let's see
6:39:366 hours, 39 minutes, 36 secondswhat's up with export, right? So export should also work. I'm just going to go ahead and create a random repository.
6:39:436 hours, 39 minutes, 43 secondsExporting to GitHub. And I'm not sure if it's going to export anything at all because we only have empty files here.
6:39:516 hours, 39 minutes, 51 secondsBut okay, it's it's unable to export because there are no real files.
6:39:546 hours, 39 minutes, 54 secondsEverything's empty. Uh but we didn't get an error, right? Whereas if you try with another account which doesn't have billing, which by the way, I think you
6:40:036 hours, 40 minutes, 3 secondscan also control through your users. You can you can like shut down their billing and stuff, uh then this action would still show you the prompt that you have
6:40:116 hours, 40 minutes, 11 secondsto upgrade. So it was that easy to turn this into a real SAS which is actually connected can be connected to your
6:40:186 hours, 40 minutes, 18 secondsstripe. If you go inside of billing and explore all the other things it can do in here you have the dashboard. You can see your monthly recurring revenue, your
6:40:266 hours, 40 minutes, 26 secondstotal revenue and your actual users here. So it's that easy to enable billing using clerk. I think this took us like 5 minutes to do. Amazing.
6:40:386 hours, 40 minutes, 38 secondsAbsolutely amazing. Uh, one thing we forgot to do.
6:40:436 hours, 40 minutes, 43 secondsSo, the same thing we just did for pro plan required. Let's copy that. And
6:40:506 hours, 40 minutes, 50 secondslet's go inside of export popover in here. And let's do the same thing right here.
6:41:016 hours, 41 minutes, 1 secondSo if prop plan is required set open to false and return and we can remove the optional chain for the body. Great.
6:41:136 hours, 41 minutes, 13 secondsSo now even in this export popover we're going to get the same toast to open user profile and to allow the user to upgrade.
6:41:226 hours, 41 minutes, 22 secondsGreat. So I think the only thing that's left before deployment uh is improving this conversation
6:41:306 hours, 41 minutes, 30 secondsbecause if I ask it something like create me a simple uh I don't know JSX snippet you will see that this is a very
6:41:406 hours, 41 minutes, 40 secondsweird color. It's barely visible against this background. And if we get a code snippet back you're going to see that it
6:41:486 hours, 41 minutes, 48 secondsjust looks bad. So what I want to do is I want to go inside of prompt input which you can find.
6:42:006 hours, 42 minutesLet me go ahead and see. You can find it inside of source app components AI
6:42:086 hours, 42 minutes, 8 secondselements prompt input. And in here we're just going to modify some classes. Uh
6:42:166 hours, 42 minutes, 16 secondsokay. So, hm, I want you to return the markdown
6:42:236 hours, 42 minutes, 23 secondsin here, not create a file. I'm trying to make it explain me some code in here and not just create me a file.
6:42:316 hours, 42 minutes, 31 secondsUh, anyway, let's go ahead and try and do something. So, let's go ahead and find a component called input group.
6:42:436 hours, 42 minutes, 43 secondsUh, input group. All right. So, input group right now only has overflow hidden.
6:42:546 hours, 42 minutes, 54 secondsLet me see if that is the file I'm looking for. Are there other instances of input group?
6:43:016 hours, 43 minutes, 1 secondSo, okay. So, find this one. Input group class name overflow hidden. And let's give it rounded large and exclamation
6:43:086 hours, 43 minutes, 8 secondspoint. All right. And that's going to make it a bit more rounded. Okay. That is step one. Okay. And we can finally get some snippets here. Perfect. You can see they look very bad.
6:43:206 hours, 43 minutes, 20 secondsOkay. Now, let's go ahead and find AI elements message.tsx.
6:43:296 hours, 43 minutes, 29 secondsAgain, inside of source components, AI elements message.tsx.
6:43:346 hours, 43 minutes, 34 secondsUh, I want to find some class names here. Maximum width.
6:43:416 hours, 43 minutes, 41 secondsSo, search for maximum width and change 95 to 80%, I think it just looks better for our use case. I mean, these are just
6:43:496 hours, 43 minutes, 49 secondstweaks. None of this is terribly important, right? And now, to make it look better against this background, let's go ahead and scroll down. And in
6:43:576 hours, 43 minutes, 57 secondshere, you're going to find this big class name for the message content.
6:44:026 hours, 44 minutes, 2 secondsAnd let's see. Uh, we should see uh BG secondary here. So group if is user it
6:44:116 hours, 44 minutes, 11 secondsuses BG secondary. I want to change that to BG accent. And I think that that already should massively improve. There
6:44:196 hours, 44 minutes, 19 secondswe go. You can see how nicer this looks now just by using BG accent instead of the other one. And I think what's left
6:44:286 hours, 44 minutes, 28 secondsis for us to fix the message response. Let's see.
6:44:346 hours, 44 minutes, 34 secondsScroll down and find message response. There's a lot of files here.
6:44:436 hours, 44 minutes, 43 secondsOkay, here it is. Message response.
6:44:466 hours, 44 minutes, 46 secondsAnd in here in the stream down, let's add
6:44:526 hours, 44 minutes, 52 secondsuh the theme to be one dark pro and one light as the alternative. that
6:45:006 hours, 45 minutesimmediately you can see fixes the look of the markdown.
6:45:056 hours, 45 minutes, 5 secondsAnd in here I do want to add some classes here.
6:45:106 hours, 45 minutes, 10 secondsSo let's do a target to inner div and use bg accent
6:45:196 hours, 45 minutes, 19 secondsand then another target to inner div and rounded medium. There we go. So just a
6:45:266 hours, 45 minutes, 26 secondsslight modification. It makes this that much more readable. Right there we go.
6:45:346 hours, 45 minutes, 34 secondsUh I don't think there's a need to edit anything else. But yeah, this is the place where you can basically tweak any
6:45:406 hours, 45 minutes, 40 secondsof those things. Perfect. So what I want to do now is just get a few more things
6:45:496 hours, 45 minutes, 49 secondsuh ready for deployment. Uh for example, you can see we just have a bunch of errors in this file right here. And there are probably some other files
6:45:576 hours, 45 minutes, 57 secondswhere we have errors. And kind of the easiest way to test that out is by running npm uh run build because this is
6:46:056 hours, 46 minutes, 5 secondswhat all of the deployment services we're going to use are going to run. So let's see can we locally build something
6:46:136 hours, 46 minutes, 13 secondswe this will now probably fail because we have some unresolved files. So let's see which files they are and if we can fix them.
6:46:236 hours, 46 minutes, 23 secondsAnd looks like the first problem is actually in our layout here, which is interesting because code rabbit actually warned us about this. Let's visit the
6:46:326 hours, 46 minutes, 32 secondslayout files that we have. Oh, looks like we only have one project ID. I think the problem is that we are defining the project ID to be an ID of
6:46:406 hours, 46 minutes, 40 secondsprojects when it's actually a string and instead we should cast it as the ID. I think just by doing that change, making
6:46:486 hours, 46 minutes, 48 secondssure that our params are not defined in funny ways, that should fix it. But now I'm worried. I think that we did this a
6:46:566 hours, 46 minutes, 56 secondslot of times. So let's see. Params promise.
6:47:016 hours, 47 minutes, 1 secondWe also do it in a page projects project ID. So open that page
6:47:076 hours, 47 minutes, 7 secondsapp projects project ID page. And let's go ahead and do the same thing here.
6:47:136 hours, 47 minutes, 13 secondsuh we're going to change this to be a string and then cast it as ID projects.
6:47:206 hours, 47 minutes, 20 secondsSo this way we won't have any problems with build. So let's go ahead and try build again and see what other files are failing.
6:47:306 hours, 47 minutes, 30 secondsAll right. So looks like we have as expected instead of AI elements we have some unused ts expect error directive.
6:47:396 hours, 47 minutes, 39 secondsUm I I was searching here if we can perhaps use lint instead of build but I I found it doesn't yield the same
6:47:476 hours, 47 minutes, 47 secondsresults. So let me see confirmation. DSX inside of AI elements here. Okay. DSXE
6:47:556 hours, 47 minutes, 55 secondserror. So if I remove it, it still has uh some errors here. So let's get rid of them.
6:48:056 hours, 48 minutes, 5 secondsSome more.
6:48:076 hours, 48 minutes, 7 secondsbasically just removing everything until it's satisfied. If you don't want to do this, there also is a solution for that.
6:48:136 hours, 48 minutes, 13 secondsYou can visit nextconfig.ts.
6:48:166 hours, 48 minutes, 16 secondsAnd inside of here, you can open TypeScript and you can add ignore build errors and set it to true. And this way, you won't
6:48:266 hours, 48 minutes, 26 secondshave to fix your uh build errors in order to build. But if you want to, you know, go along and fix this, let's go
6:48:336 hours, 48 minutes, 33 secondsahead and run npm run build until everything works. I assume it's mostly going to be fixing the AI elements files.
6:48:436 hours, 48 minutes, 43 secondsSo, as I expected, some more tsx error.
6:48:476 hours, 48 minutes, 47 secondsSo, maybe we can actually search through our codebase, well, specifically AI elements, and click find in folder and
6:48:556 hours, 48 minutes, 55 secondssearch through that. Okay, looks like those were the last one in tool.dsx DSX in the AI elements folder. So this
6:49:026 hours, 49 minutes, 2 secondscomment, let's just remove it wherever it is. And that seems to work. And I think while we are here, we can just
6:49:096 hours, 49 minutes, 9 secondsfocus on the AI elements folder. And let's like just try going over each file here and see if any of these turn red.
6:49:226 hours, 49 minutes, 22 secondsSo we know that there's a lint error inside of them. For example, inline citation of mine has an error here. And
6:49:316 hours, 49 minutes, 31 secondsI'm not going to fix it how the way it works. I will simply disable lint for this line for example simply because I
6:49:396 hours, 49 minutes, 39 secondsdidn't write these components. These were shhats and added. So I not want to accidentally mess up the way they work.
6:49:466 hours, 49 minutes, 46 secondsAll right. And that's kind of the way you can fix all of these components. Of course, for example, prompt input has some problems. Let's scroll down. a
6:49:546 hours, 49 minutes, 54 secondsbunch of Annies. So I'm going to quick fix and I will disable no explicit Annie for the entire file. Okay. Then I'm
6:50:026 hours, 50 minutes, 2 secondsgoing to scroll down again calling set state quick fix and
6:50:106 hours, 50 minutes, 10 secondsI'm going to disable that for the entire file as well. Looks like we still have some errors. So let's scroll up here to
6:50:176 hours, 50 minutes, 17 secondsfind it. Again I will click quick fix and disable that
6:50:246 hours, 50 minutes, 24 secondsrule for the entire file like that. Uh okay prompt input Q reasoning again some
6:50:326 hours, 50 minutes, 32 secondsproblems in the reasoning. I'm just going to go ahead and disable that rule.
6:50:376 hours, 50 minutes, 37 secondsRight. So I mean in production obviously you could take more care of these components but right now we just care about being able to deploy. And I want
6:50:466 hours, 50 minutes, 46 secondsto show you how you can go through these files and just add this asin disables so they allow you to properly build your app so that you can go ahead and focus
6:50:546 hours, 50 minutes, 54 secondson other things. And looks like that's it. Great. So all the chats and AI elements files are now fixed but we are
6:51:026 hours, 51 minutes, 2 secondsstill you know not fully ready because we still have uh components UI. Any of
6:51:096 hours, 51 minutes, 9 secondsthese could be problematic too. So now I'm going through them just to maybe be ahead of npm run build if it fails. And
6:51:176 hours, 51 minutes, 17 secondsthe fix is exactly the same. Or if you really notice that you're not using a specific component, you can also remove it. Just make sure there are no other components which use it as a dependency.
6:51:286 hours, 51 minutes, 28 secondsAll right, looking good so far. No errors. Item keyboard label menu bar.
6:51:376 hours, 51 minutes, 37 secondsWe really do have a lot of components. Obviously you can get rid of those.
6:51:416 hours, 51 minutes, 41 secondsyou're not using. But I always like to add all of them. It's easier to work that way. Sidebar, skeleton.
6:51:486 hours, 51 minutes, 48 secondsYeah, most of these look very good. Trying to find any that turns red.
6:51:576 hours, 51 minutes, 57 secondsHow about the resizable? Okay, resizable seems to be problematic.
6:52:026 hours, 52 minutes, 2 secondsIt's exactly the one this caught. And I think this is actually a problem in the version here. I think I saw it on
6:52:096 hours, 52 minutes, 9 secondsGitHub. Uh so I'm going to search if we actually use resizable anywhere.
6:52:166 hours, 52 minutes, 16 secondsWe don't because we use a lotment panels. We can just remove resizable in that case.
6:52:226 hours, 52 minutes, 22 secondsLet's try mpm run build again.
6:52:266 hours, 52 minutes, 26 secondsUh looks like we have some problems in components navbar use rename project.
6:52:316 hours, 52 minutes, 31 secondsLet's see what that's about. That's a component we haven't worked in in a while. So it is inside of projects components navbar and looks like when it
6:52:406 hours, 52 minutes, 40 secondscomes to use rename project uh we were passing project ID but we later decided we don't need to use
6:52:486 hours, 52 minutes, 48 secondsproject ID looks like everything works just well without it. So again npm run build until it works. It's a not a nice
6:52:576 hours, 52 minutes, 57 secondsprocess but yeah and sometimes it's different results on Versel and on other you know wherever you deploy it then it's uh in your local one. So yeah it's
6:53:066 hours, 53 minutes, 6 secondsreally fun to do but you know this is just to make sure you don't have any uh build breaking problems in your app.
6:53:136 hours, 53 minutes, 13 secondsMost of this you know the app would work just fine. It's just that for safety reasons type errors are very important.
6:53:216 hours, 53 minutes, 21 secondsAnd there we go. So this is how it looks like when it all goes well. Finished typescript and you will see your app.
6:53:306 hours, 53 minutes, 30 secondsAmazing. So let's go ahead and merge all of those final changes. So chapter 16 16 billing and final polish.
6:53:426 hours, 53 minutes, 42 secondsGet addit commit 16 billing and final polish.
6:53:496 hours, 53 minutes, 49 secondsand get push origin 16 billing and final polish.
6:53:586 hours, 53 minutes, 58 secondsThen let's go ahead and open a pull request like we usually do. So compare and pull request and let's see the changes we've did.
6:54:116 hours, 54 minutes, 11 secondsAnd here we have the summary of the last chapter. We created projects with AI powered prompt descriptions. We added
6:54:186 hours, 54 minutes, 18 secondsprop plan requirements check for GitHub import and export features. We enhanced message display with improved styling
6:54:256 hours, 54 minutes, 25 secondsand syntax highlighting. We improved binary file handling with informative messaging. We optimized file operation
6:54:336 hours, 54 minutes, 33 secondswith instant local feedback that's referring to optimistic mutations. And we refined project creation workflow with the new dialogue interface.
6:54:426 hours, 54 minutes, 42 secondsAmazing. We have two comments in the export popover uh in the toast error.
6:54:476 hours, 54 minutes, 47 secondsWhile I do tell the user to upgrade, I accidentally copied from the import one.
6:54:526 hours, 54 minutes, 52 secondsThis should say upgrade to export repositories. So, it's a minor issue, but yes, it's a mistake. And in here, uh
6:55:006 hours, 55 minuteswe used class name hidden where we should have used screen reader only or a component visually hidden to display
6:55:086 hours, 55 minutes, 8 secondsthis. So yes, uh go ahead and fix those two mistakes if you want. Uh other than that, let's go ahead and merge this pull
6:55:166 hours, 55 minutes, 16 secondsrequest. Amazing, amazing job. Let me go ahead and go back to the main branch.
6:55:216 hours, 55 minutes, 21 secondsGet pool origin main, which will now synchronize those changes. There we go.
6:55:276 hours, 55 minutes, 27 secondsWe can now build our project. And as always, I like to confirm with my graph here that everything's fine. So 15 and
6:55:356 hours, 55 minutes, 35 secondsnow 16. Amazing. So the only thing left is to deploy. Let's go ahead and see what we've done here. We created new
6:55:436 hours, 55 minutes, 43 secondsproject dialogue with prompt input. We implemented optimistic updates for instant UI feedback. We added pro plan billing gates for premium features.
6:55:526 hours, 55 minutes, 52 secondsCreated binary file preview warnings and polished all the AI elements. Amazing amazing job and see you in the next chapter.
Chapter 6: 17 Deployment
6:56:006 hours, 56 minutesIn this chapter, we're going to go ahead and deploy our project. We're going to start by creating a new project on Verscell, configuring Convex,
6:56:086 hours, 56 minutes, 8 secondsconfiguring ingest, and finally testing out if everything works. So using the link on the screen, you can visit Verscell or simply visit verscell.com.
6:56:176 hours, 56 minutes, 17 secondsAnd I would recommend creating an account or logging in with your GitHub.
6:56:206 hours, 56 minutes, 20 secondsSo all of your repositories are automatically synchronized. Once you log in, you will see a dashboard similar like this. And go ahead and click add
6:56:286 hours, 56 minutes, 28 secondsnew project. In here, you will see a list of your repositories. And here is our repository Polaris. Let's go ahead
6:56:346 hours, 56 minutes, 34 secondsand click import. Now, in here, the framework preset is already recognized, but we're going to have to do some modifications to the build command and
6:56:436 hours, 56 minutes, 43 secondsto the environment variables. So, for the environment variables, the first thing we're going to do is simply visit our environment variables right here.
6:56:526 hours, 56 minutes, 52 secondsLet's just copy all of them. That's always the easiest thing to do. And you can just paste them. And all of these will be added. Convex deployment next
6:57:006 hours, 57 minutespublic's convex url polaris convex internal key every single one of these here is going to be added but that's not
6:57:086 hours, 57 minutes, 8 secondsall we need so if you look at convex's documentation and head into production
6:57:156 hours, 57 minutes, 15 secondsversel in here they have the versel marketplace integration but since we already uh
6:57:236 hours, 57 minutes, 23 secondscreated our own convex team we are better off following these instructions so just scroll all a bit down basically until you see connect your convex
6:57:316 hours, 57 minutes, 31 secondsproject to Verscell. So we're just doing this right now. And what we have to do is we have to override the build command. So this is the command that's going to have to be the build command.
6:57:426 hours, 57 minutes, 42 secondsnpx convex deploy- cmd npm run build. So let's go ahead and open build and output settings and change the build command
6:57:506 hours, 57 minutes, 50 secondsinstead of next build to be npx convex deploy-command npm run build. All right. Uh let's see what else we have to do here.
6:58:036 hours, 58 minutes, 3 secondsSo we have to set up convex deploy key environment variable. So let's go inside of our project settings. So make sure
6:58:106 hours, 58 minutes, 10 secondsyou're inside of your project here. And in here you have your project settings and click generate production deploy key
6:58:176 hours, 58 minutes, 17 secondsto generate a production deploy key. So right now in here you will see that this
6:58:246 hours, 58 minutes, 24 secondsis a personal development convex right uh usually what you would do in production is you would switch from
6:58:326 hours, 58 minutes, 32 secondsdevelopment to production right here keep in mind that by doing this you also have to add all of the environment
6:58:396 hours, 58 minutes, 39 secondsvariables and this is basically a completely blank slate right so just because it's easier right now you can
6:58:466 hours, 58 minutes, 46 secondsstay in the development instance and in Here you have all of your environment variables. If you want to, you know, for
6:58:536 hours, 58 minutes, 53 secondsreal production cases later on, uh you would obviously want all new environment variables. You wouldn't actually reuse any of these. All of these should be
6:59:016 hours, 59 minutes, 1 secondlocal, right? But if you want to, they offer you an easy copy all which you can then add in your uh production. But for now, let's stay in development. And then
6:59:096 hours, 59 minutes, 9 secondslet's go ahead inside of URL and deploy key. Click show development credentials.
6:59:136 hours, 59 minutes, 13 secondsAnd let's click on generate uh development deploy key. So the name for the deploy key, I'm just going to call this Polaris.
6:59:236 hours, 59 minutes, 23 secondsLet's go ahead and click save. And here it is. This is our key. So just go ahead and copy it. And let's see under what uh
6:59:316 hours, 59 minutes, 31 secondskey do we store it. So we store it under convex deploy key. So let's add one more
6:59:386 hours, 59 minutes, 38 secondsconvex deploy key. And let's paste that in here. All right. So that's it for the
6:59:466 hours, 59 minutes, 46 secondsconvex. We are also have to set up ingest, but uh it's easier to do that after we deploy. So for now, let's just hit deploy with all of these things
6:59:546 hours, 59 minutes, 54 secondshere. And we're just going to see if it fails, if something goes wrong. So this is why we tested the build command locally so we don't have to watch it
7:00:037 hours, 3 secondsfail here. But still, it's possible to fail. So let's just uh see if it succeeds or not.
7:00:097 hours, 9 secondsAnd as we can see, my project was successfully deployed. uh though we need we're not ready yet, right? So what we
7:00:187 hours, 18 secondshave to do now is we have to visit inest and we have to create an account because so far we've only been using it uh in
7:00:257 hours, 25 secondsgeneral, right? So I'm going to go ahead uh and log in. Once you create an account, I would recommend clicking down
7:00:337 hours, 33 secondshere and clicking on switch organization uh and click on create new organization.
7:00:387 hours, 38 secondsThis way everything you do for this project is isolated. So, I'm going to call this Polaris and click create organization. And let me go ahead and just try Polaris and some unique slug.
7:00:517 hours, 51 secondsThere we go. Now, we have a new organization. And what we're going to have to do now is we're going to have to
7:00:587 hours, 58 secondsuh integrate Inest with Versell. So, click on integrations and find Versel and click connect. So, let's go ahead
7:01:077 hours, 1 minute, 7 secondsand let me just zoom out a bit so I can see. There we go. So click connect Verscel to ingest and this will open
7:01:157 hours, 1 minute, 15 secondsredirect to Verscell. Click add integration here. If you want to you can add it to all projects or you can choose specific projects.
7:01:237 hours, 1 minute, 23 secondsAll right. So make sure to select your organization where you have it here and then go ahead and continue.
7:01:337 hours, 1 minute, 33 secondsSo if you used inest with Versell previously, there is a chance you're not seeing your project here. For example, right now I cannot see my project. I
7:01:427 hours, 1 minute, 42 secondseven tried creating a completely new account on INS to see if it was because of that. I tried clicking this again and again. You can see I already have it
7:01:507 hours, 1 minute, 50 secondsinstalled here, right? But it still uh didn't load my Polaris project. You can see it only loads my old project. So I
7:01:587 hours, 1 minute, 58 secondsfound out that if I go inside of Versell and click on integrations in here, I can now see inest and I can go ahead and
7:02:057 hours, 2 minutes, 5 secondsclick manage manage access. And now I can select Polaris from here. I can even remove my old project or I can simply
7:02:127 hours, 2 minutes, 12 secondschoose all projects. But for example, let me just add Polaris and click save.
7:02:177 hours, 2 minutes, 17 secondsAnd now that I have that, I'm going to go ahead and try refreshing this a few more times to see if now it's going to
7:02:247 hours, 2 minutes, 24 secondsappear. So I'm going to connect to Verscell again. Click here where it's already installed and we're going to
7:02:337 hours, 2 minutes, 33 secondssee. There we go. Now it works. So let me go ahead and click Polaris and save configuration.
7:02:407 hours, 2 minutes, 40 secondsSo now this will automatically add inest signing key and inest event key to our environment variables. So you can see
7:02:497 hours, 2 minutes, 49 secondsthat Polaris is now enabled. Let me just click configure here to see what else we have to do. And I think that we can also take a look inside of our versel.
7:03:007 hours, 3 minutesLet me try and find my projects. Here is Polaris. And in Polaris here, uh, let me try and find the environment variables.
7:03:107 hours, 3 minutes, 10 secondsUh, just a second. They've changed, uh, their sidebar. So, I'm confused a bit.
7:03:197 hours, 3 minutes, 19 secondsSwitch to old navigation. Let me try and find. Okay. So, here settings, I can find environment variables.
7:03:297 hours, 3 minutes, 29 secondsAnd you can see we have inest event key and ingest signing key. All right. I mean yeah we were just confirming
7:03:377 hours, 3 minutes, 37 secondswhether they are there or not. And in here we have a warning where cell deployment protection might block syncing. Use the deployment protection
7:03:457 hours, 3 minutes, 45 secondskey option below to bypass. So let's go ahead and try and learn more about that because I think this will improve the
7:03:527 hours, 3 minutes, 52 secondsway this works. So basically just click on your project here, right? Click on Polaris.
7:03:597 hours, 3 minutes, 59 secondsLet me go ahead and see how we can find this app back.
7:04:067 hours, 4 minutes, 6 secondsOkay, no syncs found. Uh I think once these two have been added, we also have to
7:04:157 hours, 4 minutes, 15 secondswait until uh the deployment finishes. I forgot about that. Yes, this also automatically triggered a rebuild of
7:04:227 hours, 4 minutes, 22 secondsyour app. So whether you are on the new navigation on or old navigation simply find your uh deployments and you should
7:04:307 hours, 4 minutes, 30 secondsprobably see another deployment happening here like this and once that is finished. There we go. So successful
7:04:397 hours, 4 minutes, 39 secondsagain and now it should be found. There we go.
7:04:457 hours, 4 minutes, 45 secondsSo something is happening but it is failing probably because of that thing.
7:04:527 hours, 4 minutes, 52 secondsuh it warned us about that's uh Versel might be blocking it. So we have to fix that protection URL. I'm just trying to
7:05:017 hours, 5 minutes, 1 secondfind my way uh back here. So you can always go to integrations, click on versel manage and in here. There we go.
7:05:087 hours, 5 minutes, 8 secondsYou have Polaris project. So let's click configure here again and let's see what's up now. So okay, still that
7:05:167 hours, 5 minutes, 16 secondswarning. So I'm going to click learn more under the deployment protection key here.
7:05:217 hours, 5 minutes, 21 secondsAnd let's go ahead and see what we have to do. So we shouldn't do this. We should configure protection
7:05:307 hours, 5 minutes, 30 secondsuh bypass. Keep in mind that this may or may not be available depending on the pricing plan, but I think it should be available. Uh so to enable this, you
7:05:387 hours, 5 minutes, 38 secondswill need to leverage your cell's protection bypass for automation feature. So, let's go ahead and enable
7:05:467 hours, 5 minutes, 46 secondsit. Protect bypass for automation. So, we're going to go into cell here. Uh, make sure to select your project. Let's
7:05:547 hours, 5 minutes, 54 secondsgo into settings. And what was the name of that feature? Protection bypass for automation. Here it is. Let's
7:06:027 hours, 6 minutes, 2 secondsgo ahead and click add.
7:06:077 hours, 6 minutes, 7 secondsAnd I'm just going to give this a name inest. And I will leave this blank. So it generates a secret. Great. Then I'm
7:06:157 hours, 6 minutes, 15 secondsgoing to go ahead and copy that secret here. And I will add it here. And click save configuration like that. And that
7:06:247 hours, 6 minutes, 24 secondsshould fix this uh problem with uh Versel blocking the sync. I think we just have to wait a second to see if it starts to work. API ines is correct.
7:06:367 hours, 6 minutes, 36 secondsAnd okay, let's just go back and see if maybe this will now start to work. At this point, we can already visit our app
7:06:457 hours, 6 minutes, 45 secondsto see if something else might be broken. So, when it comes to your app's domain, uh make sure to use this one.
7:06:537 hours, 6 minutes, 53 secondsThere's a difference between a deployment URL and your actual uh domain for the project. So, let's go ahead and start with this one. As expected, we are
7:07:017 hours, 7 minutes, 1 secondunauthorized. And now, we have to log in. Now, we're just going to go ahead and log in with GitHub here. And looks
7:07:107 hours, 7 minutes, 10 secondslike I have my project here. So, let me go ahead and create a new one. And I will try and do a simple React plus V
7:07:177 hours, 7 minutes, 17 secondsto-do app. So, this will be interesting because we have to see whether uh it will actually start doing this or not.
7:07:257 hours, 7 minutes, 25 secondsSo, let me check my runs here. Looks like no runs are happening right now. So, perhaps it was not yet synchronized.
7:07:347 hours, 7 minutes, 34 secondsSo let's see checking the app help. So I'm going to go ahead and I will copy my
7:07:417 hours, 7 minutes, 41 secondsapp URL here. Paste it here. API ingest and I will click check.
7:07:477 hours, 7 minutes, 47 secondsNo issues found. So it looks like it can successfully connect to it.
7:07:527 hours, 7 minutes, 52 secondsAnd sometimes you just have to wait a bit until it starts to work.
7:07:577 hours, 7 minutes, 57 secondsLet me go ahead and find some details here.
7:08:027 hours, 8 minutes, 2 secondsPolaris, perhaps yours is already working. Maybe it's just mine that is stuck.
7:08:097 hours, 8 minutes, 9 secondsSo, okay, I'm trying to find maybe it's in a different environment.
7:08:207 hours, 8 minutes, 20 secondsYes, this is still not working just yet.
7:08:247 hours, 8 minutes, 24 secondsSo, I'm going to go back into my integrations here. I will go into cell and I will go back into Polaris to see what's going on.
7:08:387 hours, 8 minutes, 38 secondsOkay. Uh maybe I just have to restart it somehow. So let me try some things and see what works.
7:08:467 hours, 8 minutes, 46 secondsSo what I did just now is did another deployment. Perhaps after we enabled that deployment protection, we have to
7:08:547 hours, 8 minutes, 54 secondsredeploy. So, we're going to see if that maybe fixes it or helps in just recognize the app because still if I go
7:09:027 hours, 9 minutes, 2 secondsinto integrations here and select my versel, I think I still get that warning here as
7:09:107 hours, 9 minutes, 10 secondsif the deployment protection didn't work. I think once this is successfully synchronized, it should work. So, we're
7:09:187 hours, 9 minutes, 18 secondsgoing to see if it changes after the deployment.
7:09:227 hours, 9 minutes, 22 secondsAnd in case you don't know how to do a redeployment, you can just click on the last deployment that worked and click redeploy.
7:09:317 hours, 9 minutes, 31 secondsAnd looks like redeployment was the fix.
7:09:347 hours, 9 minutes, 34 secondsYou can see that now in my apps I can find polaris. So that's what I forgot to do. Uh they in fact instruct you to do
7:09:417 hours, 9 minutes, 41 secondsthat. I just didn't read thoroughly. Uh so before syncing with injust ensure that the latest version of your code is
7:09:487 hours, 9 minutes, 48 secondslive on your platform, right? And even in here, if you go inside of uh protection bypass for automation, they
7:09:567 hours, 9 minutes, 56 secondstell you that they actually add an environment variable, which is a clear indicator that we should have redeployed. And you can see that now I
7:10:047 hours, 10 minutes, 4 secondshave a uh synchronized Polaris app and all of these functions right here. So, let's go ahead and prepare the runs
7:10:127 hours, 10 minutes, 12 secondsscreen. Let me start a new app. Create a vit plus React to-do app. Let's go ahead
7:10:207 hours, 10 minutes, 20 secondsand run this and let's see if that will trigger a run or not. There we go. You
7:10:277 hours, 10 minutes, 27 secondscan see the run is now happening right here. And hopefully we will be able to see some project.
7:10:347 hours, 10 minutes, 34 secondsYou can see that the conversation has just been renamed. So the ingest is definitely working in production. We just have to see if the files and the communication uh with convex is working.
7:10:467 hours, 10 minutes, 46 secondsAnd here we have a real-time preview and a finished app in production. Amazing.
7:10:537 hours, 10 minutes, 53 secondsEverything works great. If there is one thing that's on my mind, perhaps uh it would be when we created the GitHub Oout
7:11:027 hours, 11 minutes, 2 secondsapp. We created Polaris. I I think uh and the homepage URL is set to localhost
7:11:107 hours, 11 minutes, 10 seconds3000. So perhaps you might want to change it to your new apps URL. But looks like that's not causing any problems. Uh I think this is what's
7:11:197 hours, 11 minutes, 19 secondsimportant, right? But this is completely independent because you get this from Clerk, not from our wherever our app is deployed. That's like a very cool thing
7:11:287 hours, 11 minutes, 28 secondsabout Clerk. Uh great. So yes, in case GitHub is causing you some problems, try changing the homepage URL to wherever
7:11:357 hours, 11 minutes, 35 secondsyour app is deployed and click update application, maybe redeploy. Amazing. I believe that marks the end of this chapter. We configured the project on
7:11:447 hours, 11 minutes, 44 secondsVerscell, configured convex, configured inest, and tested out the deployment.
7:11:487 hours, 11 minutes, 48 secondsAmazing, amazing job. Thank you so much for being with me through 17 chapters of this very long tutorial, and see you in the next one.

Sync to video time

