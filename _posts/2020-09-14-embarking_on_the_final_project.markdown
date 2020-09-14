---
layout: post
title:      "Embarking on the Final Project"
date:       2020-09-14 05:19:48 +0000
permalink:  embarking_on_the_final_project
---


As I began thinking through my final project, I wanted to build something that would encompass as much of what we've learned as possible. I decided to build out a blog that would allow me to create recipes for different foods and drinks and give users the opportunity to comment on them. 

In order to accomplish what I set out to, I decided to create a Rails API that would house my blog posts and their associated information. Additionally, I decided to create a comments model that would act as my database for all of the comments. This would prove to be quite challenging as I would later discover. 

I spent a good amount of time ensuring that my database was set up properly and that my data was flowing through the React components appropriately. This also meant that I needed to validate that my store was my source of truth and my components would be, for the most part, stateless. 

Rendering the blog posts themselves wasn't the largest challenge as I needed to leverage the Thunk middleware to complete a synchronous request to my API using the fetch command. Once I received a response, I was able to push it into my reducer and add the necessary values in my state. Once the state was updated, I would be able to render the newly updated state, leveraging the best of React's quick-updating behavior, to the child components using the `mapStateToProps` functionality. 

The tricky part came into play when I needed to render comments and associate them with specific blog posts. This required me to ensure I passed some `post_id` value to my children components so that, upon dispatching, I would be sending through a comment value from my comment input component to the reducer. Upon accomplishing this, I realized that I would want all comments that were created to continuously appear - I didn't want them to disappear when the page re-rendered! 

With this thought process in mind, I decided to leverage my knowledge of submitting `POST` responses to my API to update my backend database each time a comment was created. Once this was done, with some heavy use of `console.log()` to debug, I figured out how to update my back-end database. With this out of the way, I realized that the last major functionality I needed to account for was ensuring that the existing comments would render once they were created. I realized that I needed to create yet another action, another dispatch, and another case in my reducer, to pull in the comments in a similar way that I had blog posts. Once this was complete, I could see all of my blog posts, associated comments, created new ones, and see them update alongside existing comments. 

Leveraging React and Redux, along with some Rails tricks, I was able to pull together a blog that brought the best of all of these frameworks and languages to light. CSS is another thing...
