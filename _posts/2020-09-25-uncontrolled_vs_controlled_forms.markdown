---
layout: post
title:      "Uncontrolled vs. Controlled Forms"
date:       2020-09-25 19:01:42 -0400
permalink:  uncontrolled_vs_controlled_forms
---


I wanted to write about the difference between uncontrolled and controlled forms as they pertain to React. React gives developers quite a bit of flexibility: we can pass different pieces of data through components and also give components the ability to "think for themselves" using their own local states. Redux takes this one step higher by removing data from parent components and having them interact with data via the "store". But what does this have to do with forms? 

When creating a form, especially in React where we use the HTML/JS hybrid JSX, we follow a similar pattern as we would in basic HTML:

* `<p>Name: <input type="text" name="name"/></p>`
* `<p><input type="submit"/></p>`

However, the key pieces come into play when I use the handler directly in the form to handle any changes to that form. 

* `<p>Name: <input type="text" name="name" onChange={this.handleChange}/></p>`
* `<p><input type="submit"/></p>`

In my class component, I must then build my `handleChange` method to set my component's state to whatever it is that the user has put into the field. If I only have a single field, such as in the case above, I can set state by specifying the field's name from the form field. However, more often than not, we need to generalize to ensure that multiple fields can use the same handleChange method. Therefore, our method becomes: 

`handleChange = event => {
		this.setState({
			[event.target.name]: event.target.value
		})
	}`

The key element of this setting of state is the usage of `event.target`. We use the `event.target.name` as a key in the state and set it to the value coming in from the user's typing as this is an onChange event. Once the user has completed typing, the above state would equal something like: 

`state = {name: "Aida"}`

In order to ensure that we see the values once state is changed, we finalize our form input field to be as follows: 

`<p>Name: <input type="text" name="name" onChange={this.handleChange} value={this.state.name}/></p>`
`<p><input type="submit"/></p>`

This is an example of a controlled form: it derives its input values from state. In short, it gives control over the form values to the component's state and renders them accordingly as a user interacts with the form through changes in state and allowing state to be the single source of truth. Controlled forms are generally preferred to uncontrolled forms.

Uncontrolled forms don't rely on state and require developers to engage directly with the DOM when it comes to input fields. Uncontrolled forms use `ref` tags and require a `defaultValue` to a controlled form's `value`. The `ref` tag is what is used to query the DOM for the value; it doesn't live in the state. 

In short, a controlled component relies on state for its inputs while an uncontrolled component relies on the DOM. Lastly, a component can be either controlled or uncontrolled but never both. 
