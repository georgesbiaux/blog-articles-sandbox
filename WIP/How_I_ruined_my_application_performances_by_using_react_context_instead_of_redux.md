# How I ruined my application performances by using React context instead of Redux

## TL;DR
- I used React contexts instead of Redux for centrilized states
- Without a selector system, my components where getting big objects as props, with a lot of properties unused to build the view
- Any change in these state object caused almost all my components to rerender
- I had thousands of useless rerenders at every user interraction
- Refactor all the application to use Redux and use the selector system to give each component only what it needed solved the problem

## A bit of context

At Theodo, we heavily use Scrum, which is great to manage a backlog sprint after sprint. But many of our projects had hard times maintaining a clear and evolutive release plan. We especialy had problems making visible the dependencies each of our EPICs had to external teams or services.

So, we decided to develop a tool to address those problems: Splane.

[Splane]: ./Splane1.png

As you can see, this is a trello-like Kanban board where each columns represents a sprint. The idea is that you have two distinct zones: the top one to organise your EPICs and to bottom one to manage your dependencies.

I chose React to develop the frontend part, but I made a big architectural mistake at the very begining of the project.

## Why I choosed to get rid of Redux and how I replaced it

We've been using Redux on all our React project for a long time, and Redux is part of our React boilerplate. But I've always found that Redux was quite a heavy and verbose system with all its reducers, action creators and selectors. And, on top of that, at that time, our boilerplate included Flow typing (we've moved to Typescript since), which made the whole thing even more verbose.

So, when the application needed its first centrilized state, I told myself "Let's make it much simpler, let's use React context instead of Redux".



## Why it was a huge mistake

## What I had to do to fix everything

## Conclusion
