## 16 Jan 2022
I realised that writing CSS can be easier if I were to work outside-in. There were a few instances where I wanted to make some layout changes to an existing component, but even after some time experimenting I just couldn't get it the way I wanted. Eventually, I decided to in a sense start from scratch, copying chunks of code back step-by-step and making minor CSS tweaks along the way until it reached the state I wanted. This made sense because generally, the properties of parent elements will affect the layout of their children, and less of the other way around.

React does not make the DOM change; it compares the diffs, and modifies and replaces wherever necessary. Some CSS properties, such as 'animation' and 'transition', requires the element to be directly modified and not be swapped out and replaced with a new instance. Using components that are themselves defined inside another component will confuse React, leading to weird behaviour such as the entire element being swapped out, which then breaks CSS. Hence, it is best to define each component separately.


## 9 Jan 2022
At this point, the changes I were making to my code had effects that are so intertwined that it no longer made sense to commit to separate branches. Hence, I created a new 'develop' branch to work on these changes on, merging back with 'main' on every deployment.

The UI design of my app felt very inconsistent, and I had to spend a lot of time to tweak every small part such as every input field, and every button. I read up about CSS frameworks such as Bootstrap and the [mui](https://mui.com/getting-started/installation/) react library, and realised that it was what I needed to make my app more visually consistent.

I experimented with the mui library (see [test-material-ui](https://github.com/heyzec/cvwo-frontend/tree/test-material-ui)) to get a better understanding of the options it offers. Afterwards, I decided to create my own "framework" with material-inspired components for a more in-depth understanding of the underlying CSS.


## 4 Jan 2022
While researching on how to design the sign-in page, I came upon the concept of ["frictionless forms"](https://instapage.com/blog/sign-up-page). It is the idea of reducing the number of fields to ask the user during the sign-up process. I could relate to the few occasions whereby I encountered a sign-up page with many fields, and I would be feel lazy and also reluctant to give out so much information. The takeaway for an app developer is to remove as many unnecessary details required, and consider delaying getting non-essential info, instead allowing users to fill up in their own accord after they have created an account.

On Devise's GitHub page, it was recommended that beginners of Rails to not use Devise. ([see here](https://github.com/heartcombo/devise#starting-with-rails)). So, I followed tutorials online to do basic authentication from scratch.

## 27 Dec 2021
I've heard of the term _relational database_ but never actually understood what that meant. Today I learnt that this refers to relations between tables, such as one to many, one to one, many to many relationships, and they are represented by entity relationship diagrams.

If I were to use database relations, this means instead of storing for each task the ids of the tags attached to it, I'll need to create a separate table called Tasks2Tags which encapsulates the one to many relationship between the Tasks table and Tags table. As I forsee that adding user accounts into the mix may change the way my database is organised, decided to hold off this change for now.

From here on I'll be using the [functional version](https://reactjs.org/docs/hooks-reference.html#functional-updates) of useState hooks so the code will always receive the most updated value of the state, and this should reduce the chances of bugs.


## 25 Dec 2021
The frontend codebase was getting really messy and it was time for a refactor. There was just too much code in the main App.js file. Although components are meant to be reused, it made sense to split off different parts of the layout into their own component even though they will be used once in the app. 

The CSS was also getting unwieldly and after researching I realised I could compartmentalise the App.css file and each component can then import its own stylesheet. There were also many other ways to organise CSS, like using react modules or SASS scripting language instead. But I wanted to stick to the basics as much as possible.

There are also CSS naming conventions, such as [BEM](https://css-tricks.com/bem-101/) and [SMACSS](http://smacss.com/). BEM looked like it is a pretty straightforward convention so I chose to use it from here on.


## 22 Dec 2021
I changed my code to use a context object that holds helpers functions and values that need to be accessed by many components, such as the tags and tasks arrays. This one object is then passed to all components, and is similar to how [python telegram bots](https://github.com/python-telegram-bot/python-telegram-bot/tree/master/examples) are written. This method doesn't seem like it aligns with React's design principles, but it will do for now.

I also felt that I just didn't have the correct mental model of how CSS works. While [MDN Web Docs](https://developer.mozilla.org) and [css-tricks.com](https://css-tricks.com/) are both great resources on for CSS, I ended up spending the rest of the day delving into the official CSS specifications by W3C to try and get a better understanding.


## 18 Dec 2021
There were two more parts of the app that I wanted to work with - UI, specifically the header, and the tagging system. I decided to create two additional branches to the frontend repo so that I can switch between working on two features as it can be boring to work on one feature for too long.

I also deployed both frontend and backend, and ran into the CORS issue. I spent quite some time to fix it as I didn't want to just specify a wildcard for the origin header.


## 10 Dec 2021
Started on the journey to build a task manager app from scratch. At this stage, I'm watching many Rails and React tutorials on YouTube to get some sense of how all these works.
