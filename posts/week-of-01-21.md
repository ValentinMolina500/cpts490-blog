---
title: 'Week of 1/17/22 to 1/21/22'
date: '2022-01-21'
---

I started off this week auditing some old Lambda cloud functions we are using for various data processing, RBAC and file storage tasks. The source code for these functions is written in plain JavaScript, so one of my tasks was to check if we used JSDocs (similar to Python's Docstrings) to document the data structures for any arguments these functions take and for return payloads. With some functions, especially the functions that do data processing logic, there is a concern with the size of the return payload. AWS has limits to the size in bytes (10mb with API Gateway) of what a Lambda can return through a network call. Thus another part of my task was adding a check to see if the return payload size has surpassed that limit, and if so, we have an alternative way to access that return payload instead of returning the payload directly. 

Also this week, I began working on adding some new functionality to an existing file list view component we are using. In accordance with the design mockups, folders should be expandable by clicking the expand icon and, when expanded, the files/folders located within the expanded folder should be visible. This is harder than it sounds since React does not play nice with deeply nested data structures such as a tree. Thus, I'm looking into alternatives to use a more flatter data structure to store files and folder hiearchy. Another complication is that information about the files/folders for a given folder is requested **on-demand**, which is to say we don't know what files/folders exist in a folder until we navigate to that folder.

Finally, I helped a fellow developer troubleshoot some authentication logic issues they were having on a project for the Space Force. Authentication can be finicky sometimes, and we discussed some methods of refreshing authentication state while using JWT's. 




