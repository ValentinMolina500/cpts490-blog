---
title: 'Week of 1/24/22 to 1/28/22'
date: '2022-01-28'
---

I spent the majority of this week refactoring a file list view component to allows user to be able to expand folders and see the files contained in said folders. This turned out to be a much bigger lift than anticipated (unfortunately us develoeprs have a knack for this saying this I've heard). The way the list view component was originally implemented was not conducive to allowing this kind of functionality. So, I had to rewrite the core logic of the list view while perserving existing functionality. 

The time sink for this process was more in just understanding the existing logic. Much of the code for the list view was perplexing (I will not show code snippets out of respect for the programmers). Code comments would have went a long way explaining the esoteric way of storing file and folder paths and there was very little abstraction between the list view and Amazon Web Service S3 tool we were using to store files in the cloud for which this list view was getting its file/folder information from. 

Once a general understanding was cobbled together, I could begin the rewrite process. In general, we want to change as little code as possible to implement some new functionality, because any new code introduce new vectors for error and untested code. So I took great care to try to perseve as much as the old code as possible. I like to create a temporary file and add code from the old file as I go, only changing what is necessary. And while I was in there, I took the liberty to adding documentation on parts I thought were not self-explanatory, as I would have appreciated it when I was going through this code.

I'm not done with the list view component, and to be sure I'm not happy with how long its taking, but I want to make sure all is working before I created a pull request for my change.




