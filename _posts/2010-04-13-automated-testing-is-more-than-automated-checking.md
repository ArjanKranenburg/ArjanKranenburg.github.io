---
title: Automated testing is more than automated checking
---

I was involved in an interesting discussion on Twitter, the other day. It started with a tweet by @testingqa (Guy Mason): “Still of the opinion that ‘Automated Testing’ is a deceptive term,no testing is being performed,it should be called ‘Automated Checking’ #qa“. With that he probably refered to Michael Bolton’s blog that there is a [difference between testing and checking](https://developsense.com/blog/2009/08/testing-vs-checking).

After that blog lot’s of people, mainly automation sceptics, stated that Automated Testing should be called Automated Checking. Although I acknowledge and agree that there is a difference between Testing and Checking, I don’t think it should be called Automated Checking. I’ll explain below why not, but first the rest of the Twitter conversation:

I responded to @testingqa’s tweet with: “@testingqa but that’s not true either. Automated Testing is more than checks. There are actions as well.”

(@michaelbolton: “. @testingqa I agree, but I think @AdamPKnight expressed things well. He specified checking, so I read “automat[ion assist]ed tests”. #qa“)

@testingqa: “@ArjanKranenburg Yes, actions are taken which verify behaviour is consistent with expectations. But that’s still a check.”

@arjankranenburg: “@testingqa I meant actions before you can start checking. You have to tickle the SUT before verifying the response.”

@arjankranenburg: “. @testingqa and then there are preparations, cleanup, reporting, etc. Automated Tests is so much more than just Checks. #testing #qa”

@michaelbolton: “. @ArjanKranenburg @testingqa Test automation (any use of tools to support #testing) should be much more than checks. Alas, often, it isn’t.”

@arjankranenburg: “. @michaelbolton @testingqa I think it often is. E.g clicking a button is an action, verifying the response is a check. #testing #qa”

@arjankranenburg: “. @michaelbolton @testingqa I understand you don’t want to call anyting automated a test, but it’s more than a check. #testing #qa”

@michaelbolton: “. @ArjanKranenburg Your assertion that I want to call anything automated a check is incorrect. #testing #qa”

@michaelbolton: “. @ArjanKranenburg Something is a check when it doesn’t involve cognitive engagement. Tools can extend cognitive engagement. #testing #qa”

@michaelbolton: “. @ArjanKranenburg #Testing tool use turns into checking when it *displaces* cognitive engagement. #CultOfTheGreenBar #qa”

@michaelbolton: “. @ArjanKranenburg Note that risk identification, design, and programming–the preparation–are #testing activities, requiring sapience. #qa”

@michaelbolton: “. @ArjanKranenburg Verifying *one factor* of the response is a check. Checking focuses on output; #testing on outCOME. Beizer might agree.”

@testingqa: “@ArjanKranenburg Automation does gather info & does allow one to verify response but distinction remains that it only checks to verify…”

@testingqa: “@ArjanKranenburg …if it meets expected outcome (or not). Preparing/cleanup does not reveal new information though and reports based on…”

@testingqa: “@ArjanKranenburg … checks only verifies against expectations still. As @michaelbolton said it can be used for more, but most times do not.”

To summarize Michael’s blog, but please read all his [blog-series on testing vs checking](http://www.developsense.com/blog/category/testing-vs-checking/) because there is more to it, an important difference between testing and checking is that testing requires cognition to interpret the information revealed by one or more checks. But I’d like to extend that as I think testing is more than checking + interpretation.

And this becomes apparent when trying to automate a test. The base of a test consists of actions, checks and interpretation of the retrieved information. Most Systems Under Test (SUTs) need to be tickled before it responses. You need to click a button, send a request, press a key, etc. etc. In theory, the SUT can do things without an external stimulant, but in most cases it doesn’t.

Then the SUT responses and that response can be checked for certain aspects and the revealed information must be interpreted. If you state that Automated Testing should be called Automated Checking because the cognitive part can’t be automated, you’re ignoring the actions that can and often need to be done as well.

And there is more:

Before starting the actual test, you need to prepare the SUT to make sure it is in the correct state for the test to execute.
Automated TCs are often run in a batch, so it is good practice to restore the SUT to its original state.
Since interpretations of the results is still needed, the results need to be presented in a tester-friendly way. What and how you are reporting is very important.
etc. etc.
All these activities can be automated as well and are often included in the automated test script.

My point is, if you don’t want to use the term Automated Testing, call it Automation Assisted Testing (I like that), but Automated Checking simply doesn’t cover the activities done in Automated Testing.
