---
layout: post
title:      "Reflecting on a Completed Program"
date:       2020-09-19 03:23:55 +0000
permalink:  reflecting_on_a_completed_program
---


It feels bittersweet to be writing this final blog post because I cannot believe that my time with Flatiron has come to an end. There were so many ups and downs throughout this journey that I really feel that I've learned more than I thought I ever could. 

Reflecting on the program and after learning so much, I've realized that I really enjoyed different components of every language that we've learned. I love the simple syntax of Ruby when writing methods: it's simple and clean. When it came to Rails, I loved the notion that everything felt like a 1:1 relationship. Each action had a view and each view was dedicated to rendering exactly the content provided by a controller method. 

JavaScript and React, however, presented their own challenges. I like the ability to quickly debug via a simple `console.log()` in the DOM. As for React, I loved the idea of a Virtual DOM that updates and renders content swiftly and intelligently. Components retain information and, with the power of Redux, render content quickly without needing to retain extensive logic within components. `this.props` and `this.state` allow for needed information to travel where necessary and I see this is the real power of the framework. 

In completing the React/Redux project, I wanted to share a neat trick that I used to allow the users of my app to "favorite" or "un-favorite" content. In my presentational component, I created the below function: 

`const favorite = () => {`
			`if (this.props.dish.favorite === true) {`
				`return fullHeart`
			`}`
			`else {`
				`return emptyHeart`
			`}`
		`}`
		
This function conditionally rendered, based on props, whether or not to return an empty or full heart. It used data from the back-end Rails API that I set up. Inside of the button: 

`<button className="heart">{favorite()}</button>`

That `favorite()` function allowed the correct heart icon to appear on the user interface without leveraging any external libraries. This was one of my favorite problems to solution during the creation of my project. 

All in all, I enjoyed learning all of the languages and frameworks that we learned from Ruby to Rails to React but I maintain that Ruby, Rails, and Sinatra, were my personal favorites. 
