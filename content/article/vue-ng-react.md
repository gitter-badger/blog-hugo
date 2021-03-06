+++
categories = ["article"]
date = "2017-06-07T16:56:21+11:00"
title = "Angular vs React vs Vue"
tags = ["javascript"]
+++

>Angular, React, Vue as most popular JavaScript frameworks at present, we just discuss Angular 1.x, Angular 2 / 4, React 15+ (Redux), and Vue 2+ here. There is no Angular 3, if you have not noticed before.


## Client side is a battle field

In past 6–8 years, the Restful API has been accepted as one of standard web interfaces for most web applications, solution architect can simply add REST API on the top of existing web layer or business layer to provide REST API and support multiple client devices. So the developers can continue to develop or maintain system with their favorite programming language, framework or technical stacks.

On the contrary, it is a completely different story on the client-side, there are tons of variant JavaScript frameworks emerged in the last 10 years. It is good to have more options, but it is a nightmare for web developers who are working in such battle field, because they need to try a lot of different stuff to make a decision, especially when the project schedule is tight, it makes tech lead or architect quite stressed. Something becomes much worse is when the development team try to adopt new framework for the new project, it is not easy to work out which framework we should choose.

Don’t forget there is another big risk to adopt new programming language(ES 6 or Typescript) with the new framework, as well as new development, build and test tool, if the team has no enough skills or experience. As solution architect, they need to think it through for development team, and also consider if the team can really pick it up quickly. That is why we have to compare those frameworks here before we make a decision.

## Performance is not a priority or crucial criterion for choosing a framework

We can find lots of comparison between those frameworks, and so many of them are related to performance, programming language, design pattern, etc. Actually many web applications in the world are just small to median size web application, we don’t need to build the web application as Google, Facebook or Twitter. In my opinion, the performance of framework is the not critical benchmark, at lease it is not first priority which we need to consider if it is right for the team. Except performance, we have more concern on tech stacks, community and ecosystem involved with the framework, which have more impact on team’s productivity and system’s maintainability. 


## The difference of those framework

Let's look into the frameworks and list the difference of these frameworks.

### Basic tech stacks


Tech Stacks   |    Angular 1.x   | Angular 2 / 4 | React 1.5 (Redux)  | Vue 2   
----------------|-------------------| ---------------|---------------------|---------
Vanilla JS     |     Yes       |  Supported  |  Supported       | Supported
ES 6          |     1.5+          |  Supported  |  Yes            | Yes
TypeScript    |               |  Yes        |                | Supported |
MVC           |   1.2-1.4 |            | |
Component-Based |  1.5+ |  Yes   | Yes |  Yes 
Shadow DOM | | Yes | |
Virtual DOM| | | Yes | Yes
Immutable state  | | | Yes | Yes



* Yes:  Programming language which the framework uses.
* Supported: Programming language which the framework supports.


### Cool stuff is not always the best

We have seen so many cool stuff which are finally abandoned in the past, the Silverlight is one of such examples. We shouldn’t choose new framework because it looks cool or it is the latest one. We choose the new one because it really can solve our problem, improve our productivity and quality in the long run. Don’t forget there is always some cost to adopt new things. We need to balance the cost and outcome of the technical investment, and we need to work it out if it is right time to do it.


### Programming language is still the barrier


If we need to use new programming language, we have to evaluate with the existing development team. Even ES6 or TypeScript (TS) claims it is compatible to Vanilla JS, but when you start to look into new framework or sample project, which are coded with ES6 or TS, it still makes you so confused if you are not familiar with such syntax. It will significantly impact the efficiency of learning new framework. So there is always a learning curve, which we cannot ignore, to code something in a new programming language.


Someone complaints all those JS frameworks makes the build process much more complicated than the old web frameworks, because of the new programming language. Does it really matter? The short answer is Yes, but we are not going discuss the advantage in details here. If your team comes from .Net Web Form or Java MVC background, it would be a steep curve for the team to pick up ES6 or TypeScript and Component-based framework, not to mentioned new build and test tools.


No wonder a few .Net teams were struggling with Node stack integration on Visual Studio, especially when the team members have no Node.js experience. So we need the whole team to discuss the difficulties before we adopt new technology and framework. It is helpful to make sure the team has the same view, and it is also important to plan our training and decide how to transform development team step by step.


### Where to start 

For the team which comes with Web Form, with Vanilla JS background, we can start with Angular 1.x (Up to 1.4) on some small projects, or we can build something training project, because the MVC pattern is very similar to their previous coding experience.

One more thing, I have to mention is the Angular 1.x application can be built without any Node.js tools, such as Gulp, Grunt, Webpack, etc. It makes the team feel comfortable to adopt it without prior experiences. Also, it gives the team some buffer to organize the training to pick up Node.js tools for the future.

For the team which has experience of Angular 1.2 ~ 1.4, they can choose to stay on later version of Angular 1.x, e.g. Angular 1.5+, and they can start to convert coding pattern from MVC to Component-based. After that, if the team is planning to move to Angular 2 / 4, it is better to do some TypeScript training. In my view, so far the ecosystem for Angular 2 / 4 is still under development. It is a bit risky to use Angular 2 / 4 to build the real-world production. There are quite many gotchas which you have to figure out on your own.

For the team which has TypeScript or ES6 experience, they can choose what they prefer. They can spend more time on UI integration. There are a few customized UI package for bespoke framework. That is what we are going to discuss in the next.



### Responsive UI library support

To build a real-world application, we need to integrate some popular responsive UI libraries instead of building all styles on our own. Let’s take a look the support of Bootstrap or Material-Design for different frameworks.


 UI library   |    Angular 1.x     | Angular 2 / 4 | React 1.5 (Redux)  | Vue 2   
--------------|------------------- | ---------------|------------------|---------
Bootstrap 3  | ui-bootstrap (Very Good) |            | react-bootstrap(Very Good) | VueStrap* (Very Good)
Bootstrap 4  |                          | ui-bootstrap (Alpha) | In progress | BootstrapVue (Good) |
Material Design | Materialize (Good)   | Angular Material(Basic)  |  Material-UI (Good) | Vuetify (Very Good)



* VueStrap: Please use the [Willen's fork](https://github.com/wffranco/vue-strap) for Vue 2.
* Libraries in the table above has been tested or used in some projects.


From what we can see now, the Bootstrap 4 is similar to Material-Desgin. So it is good news for developer. They just need to pick their favor, and they will always get analogical effect.


Actually there are tons of UI libraries / CSS framework available on Github, so many are platform neutral framework, i.e. It can be integreated with Angular, React or Vue. Be honest, integration is always not easy, it will take you or your team some extra effort. Keep it in mind, to integrate platform neutral framework you need to take care of dependencies and build, test tools on your own, such as webpack or yarn.

### Stable API 

Against to Angular 1.x, the Angular 2 is completely a new animal. Angular 4 comes with some breaking changes, which breaks a few Angular 2 dependencies (third parties). Since the API of Angular 4 is still under active development, we cannot use it for production. According to Angular team’s announcement, they want to fix all Angular-2’s bugs and issues in Angular 4 and keep all built-in libraries sync to Angular 4. It will take a long while to get things ready. If your project uses Angular 1.2–1.4, I’d like to suggest you to keep it, until Angular 4 is finalized.

React-Redux is much more popular than React-Flux recently, but it doesn’t means it is better than React-Flux pattern. In my opinion, React-Flux is much more straight and close to original React design. If you ready use React-Flux, you have better to stick with it.

Vue 2 comes with some breaking changes. There is migration guide for Vue 1.x to Vue 2. It doesn’t seem very different. Vue 2 is ready for production.

### How to compare  

In order to compare those frameworks properly, I use those frameworks to create a small real-world web application, which has built-in authentication support for the back-end API service, and integrated with some responsive UI framework, e.g. Bootstrap or Material-Design.

You will find there is no project built on the Angular 1.x, because my team and me have done a lot real-world application upon Angular 1.x. We know Angular 1.x, inlcuding its ecosystem is quite reliable, which you replicate any web application with this framework.

On the other hand, Angular 1.x is built with Vanilla JS, i.e. you don’t need transpiler to build Angular 1.x app, so it is a bit unfair to compare with the framework which is coded with ES 6 or TypeScript, because the build tool and setup for Angular 1.x is easier than others. I mention the Angular 1.x here to remind them, actually there is other option for the team comes from traditional MVC stacks. It would be proper way to transform the team smoothly.


### Following are the projects and related screenshots


[Angular 4 CRM](/project/reetek-angular4-crm/)

![Screenshot-Angular4Crm](/img/ng4crm-screenshot-2.jpg)

[React CRM](/project/reetek-react-crm/)

![Screenshot-React-Crm](/img/rrcrm-screenshot-2.jpg)

[Vue 2 CRM](/project/reetek-vue2-crm/)

![Screenshot-Vue2crm](/img/v2crm-screenshot-2.jpg)



### Comparison of projects for different framework

Let’s go back to projects above and take a look. Basically they are implemented almost the same features as real-world simple CRM application.


__Features__

* Authentication & Token support for Restful API
* Customer CRUD functions
* Order CRUD functions
* Dashboard including two charts (Bar/Line/Doughnut)
* Integrate with Material Design (Angular project includes bootstrap)


|             |Angular 4 CRM   |  React Redux CRM  | Vue 2 CRM
--------------|-------------------|------------------|-------------
Dependencies |       22           |      13           |  9
Code Size    |     135KB          |     113KB         |  49KB
Effort       |     72 hrs         |    80 hrs         |    48hrs

* Dependencies: Any dependencies for test, distribute are excluded
* Code Size: It includes some customized CSS file, but image files are excluded
* Effort: The effort for learning curve has been eliminated, but R&D effort cannot be excluded. 


Firstly, I have to explain why React project took more effort than the other two projects. Comparing with React, the Angular 4 and Vue 2 are a bit new, i.e. there are more available packages or libraries for React on-line. As I mentioned before, it is not a good news. We need to try more different to figure out the pros and cons of different solutions. Unfortunately, we cannot exclude such R&D effort when we build these projects. 

According to above the dependencies, code size, we can see the project based on Vue.js is much simpler than other two projects.In my view, Vue 2 is my favor for next new project. It combines advantages of Angular and React. It also addresses some problems which we found in Angular and React.

Vue.js uses Virtual DOM, which avoids many dirty checking in Angular 1.x, and the complicated coding pattern (Observable & ReactiveJs, IMO) in Angular 2 / 4.

Vue.js makes the handling of immutable and mutable variables much easier than React. Its template is very handy and straight. It is the same as regular HTML, it is very easy to convert the mock-up HTML into Vue template, especially when you need to customize you styles. Vue’s template and directive is similar to Angular.

Vue.js is not just cool, it is elegant and simple. I am pretty sure if you have Angular or React background, you will pick it up in a couple hours or days. Once you start to use it, you won’t want to go back. Its official routing system is quite stable and easy to use. Compare with Angular-Router or React-Router, it is much more reliable.

Generally, Material-Design libraries for React is not handy as other customized version for Angular or Vue. The special coding style of JSX needs to convert all CSS and HTML into JSX format. To be honest, I am not so convinced by React’s JSX, because it is not straight as final HTML or CSS. Compare to other framework, it is a bit verbose and inconvenient. We cannot simply copy the style code from the browser’s dev tool when we debug it on the browser. i.e. You need to put more effort to make your page pretty.

Angular’s Material-Design library has very limit components. To build a real-world application you need to add another UI library to supplement the former missing components. Last but not least, the Vuetify is the best Material-Design so far we have found and tested.

Angular 4 CRM — https://github.com/harryho/ng4crm
React Redux CRM — https://github.com/harryho/react-crm
Vue 2 CRM — https://github.com/harryho/vue2crm

Update:

Angular Material Design App — https://github.com/harryho/ng-md-app
React Redux CRM — https://github.com/harryho/react-crm
Vue 2 CRM — https://github.com/harryho/vue2crm
Angular 4 CRM — https://github.com/harryho/ng4crm (It is no longer maintained to support latest Angular)

### Summary

Before we make any conclusion, we have to be aware the world keeps changing. Perhaps when I was writing this article, some problem of framework have been solved, or some small problem became worse and worse. We have to review the decision we made from time to time and correct them ASAP if we find the cost is overweight the outcome.

* Team with Web Form and Vanilla Js background should starts with Angular 1.4 and take some time to be familiar with Node.js tools

* Team with Vanilla Js background should start to learn ES 6 or TypeScript, since sooner or later all the browsers, including mobile devices, will support ES 6 or TypeScript.

* Teamwith ES6 /TypeScript background can choose any framework you prefer, the integration with other UI library will take you some time to make a judgement.

* Teamwith React-Flux can continue or switch to React-Redux. It maybe reduces some boiler code, but I don’t think it is a big deal.

* For the newcomer of React, I will recommand React-Redux, because it has better community support.

* In my opinion, if you continue to invest anything on Angular 2, it is a bit waste, because Angular team hopes you to move to Angular 4 as soon as possible once Angular 4 is ready for production, and they are planning to fix Angular 2’s issues in Angular 4.

* Angular 4 and its ecosystem are under active development, but please be careful if you want to use them in your production.

* Vue.js framework is a very nice one. Give a go on your next project.