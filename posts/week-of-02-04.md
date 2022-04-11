---
title: 'Week of 1/31/22 to 2/4/22'
date: '2022-02-04'
---

This week I really doubled down on the file share list view component. To be sure, the original implementation left much to be desired. 

First of all, it did not maintain the UI state of the files or folders. This is a problem because files/folders should be able to be favorited (indicated by a star icon), expanded and selected. However, there was no way of tracking that associated state with a given item. This step was rather simple, it simply meant adding that UI state information when we fetch the files/folders from the network. 

The second thing, and this has been the thing that has cost me so much time, is the data structure that was previously used to store file/folder information *did not keep hiearchical information about files and folders*. This was a huge oversight, since there is certainly such a relationships between files and folders: files belong to folders, and folders can belong to other folders. The list view component is supposed to show a tree-like representation of files/folders on the network. But without that hiearchy, this is not possible. 

Much of this relationship of files/folders was encoded in a series of strings, requiring bug prone string dissections to get crucial information =such as "What is the parent folder of this file/folder?" In fact, while venturing through the vast code that relied on the previous implememention, I saw multiple instances of my fellow developers copying code to do such things. I was in awe at the hoops we had to jump through to get basic information about files/folders.

I think this is a lesson in planning your data structures to be the most efficient and elegant solution to a given problem. When I first set out on this journey, I wanted to minimize the amount of code I had to change. However, it became apparent I'd need to refactor the very way we stored file/folder infomation to complete my original task. Problem numero uno: **a lot of code already written relied on the original implementation with very little to no abstraction**. This meant that I have to go in and update all that logic to account for my changes. Truly horrific stuff. There is very little abstraction between the file/share structures and the Amazon Web Services DynamoDB database we are using. Should they ever need to change to something like MongoDB, SQl, or really anything, it's going to be a huge effort. 

I should add I'm still not done. But I'm happy with the abstractions and simplicity I've implemented already. This endeavor really has made me think about how a little planning will get you a long way. Hopefully by my next blog entry, I'm done with this!