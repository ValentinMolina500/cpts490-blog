---
title: 'Week of 3/28/22 to 4/1/22'
date: '2022-04-01'
---

This week I took 2 days off for a couple of midterms I had so I didn't get much work done. I'm still working on the network diagram and I had good success with an auto placement algorithm the nodes using a regular polygon. I also began working on a way of opening one of our applications within another one. Using an `iframe` element, we can load HTML document within another one. That works okay, however the challenge is why want the child HTML document to change it's user interface it's opened within the parent HTML document. Also we want to communicate between the child and the parent, so we're looking into using various methods to do that communication. We have some ideas with HTML requests, but that might be too slow. We're currently looking into the `Broadcast` web API, which is based on websockets so it could be much smoother.