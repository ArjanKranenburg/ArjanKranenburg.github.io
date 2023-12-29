---
title: Model based testing
---

Model Based Testing (MBT) is a term frequently used these days. It sounds well and just from the words seems like a good thing to do. But is it really worth the hype?

The strict definition of Model Based Testing is when you base your testing on one or more models. This still sounds good, but not so much if you consider the following:

A model is a simplification of reality. So if your tests are solely based on one or more models, you’re bound to leave some paths untested.
If code is also generated from the same model, you’re testing the generation process in stead of the product or model. Even if the code was not generated automatically, but the developer also based his code on the model, it is not likely that many faults are found.
Models must be created or provided.
Models can contain faults as well.
But lately the term is also used for tests described by models. The model still describes the system, because every test case does, but the primary purpose of the model is to describe the test case. Describe what path is followed, what actions are to be taken, and what is to be expected. Although I don’t call this Model Based Testing, Test Case Modeling is perhaps a better term, I do see a great benefit of it.

In earlier, pre-Agile times long descriptions used to be made for every test case followed by another description of the next test case that was only different by a few (essential) words. Later, Excel was used to describe test cases by key- and action-words. Test Case Modeling can be the next step in the evolution of describing test cases and to visualize them with the best possible model-type.
