
#Intro to DOM and Events

##Learning Objectives

- Apply proper principles to select DOM elements using JavaScript.
- Demonstrate ability to bind events to single and multiple DOM elements.
- Build your first *web app*

Fork [this repo](https://github.com/wdi-sf-fall/dom_day_lab) and clone it.

**Excercise 1: (5 min)**

Fix the page.

###DOM Manipulation with JavaScript

**Review:** What is the DOM?

Go to Developer Console. Look at DOM in *Elements*, then look at the DOM in *Console*. The object 'document' represents the DOM in JavaScript. We can change the DOM, i.e. the page, by changing the **document object**.

Google "DOM document api", pick the MDN documentation. Inspect a few properties, for example:

	document.URL
	document.head
	document.links (what does it return?)
	
How to change the DOM? Select elements and manipulate them.

**Select by tag id:**

	var greeting_div = document.getElementById("greeting");
	
What's the greeting?
	
	greeting_div.innerHTML
	
Change it:

	greeting_div.innerHTML = "Wow, something changed."

Change styling:

	greeting_div.style.backgroundColor = "yellow"
	greeting_div.style.color = "red"
	greeting_div.style.height = "100px"
	etc.

	
Properties can be a getter and setter. What does this mean?

**Select by class**

	var content_div = document.getElementsByClassName("content");

Change it:
	
	content_div.innerHTML = "I can change,too";

Why is this not working?

**Exercise 2: (5 min)** 

Write JavaScript that changes the greeting text to "Hi Planet Earth". Make it part of your *web app*

Seems trivial. But it might not work as expected. Why?

**Select by tag name**

	all_li_elems = document.getElementsByTagName("li")

**Preferred: select using CSS selectors**
	
Get elements by tag name or class is very unspecific. You can go after specific CSS selectors, just like you would in stylesheets:

	document.querySelectorAll("li")
	document.querySelectorAll("li.selected")
	document.querySelectorAll("div#essentials > ul > li")
		
**Exercise 3: (15 min)**
		
Add JavaScript that renders *li* elements in "yellow". Put your code in a function and call it.

**Accessing and changing element attributes**

	document.querySelector("img").getAttribute("src")
	document.querySelector("img").setAttribute("src","./images/beer.jpeg")

##Events

Now that we know how to select DOM elements, we can attach events to them:

- Common Events:
	- change
	- click
	- mouseover
	- mouseout
	- keydown
	- keyup

#####"Shortcut" Method

```
document.getElementById("myDiv").onchange = function() { };

document.getElementById("myDiv").onclick = function() { };

document.getElementById("myDiv").onmouseover = function() { };
```

Let's attach a click handler to he image element. Try in console first.

#####addEventListener

```
document.getElementById("myDiv").addEventListener("click", function() {
	//Your code here
}
```

- Events can only be attached to specific elements. Therefore, when you return a collection such as the result of `document.querySelectorAll` you CANNOT simply do this:

```
document.querySelectorAll(".li").addEventListener("click", function() {
	console.log("Click worked");
}
```

**Exercise 6: 30 min** 

Improve your web app:

a) Loop through each *li* element and attach a click handler that sets the class attribute to "selected". Remember that you already have a function that loops over *li*  elements. Why not repurpose it?

b) How do we know which item was clicked? **this** is set to the DOM element that received the event. Print **this** out in console.

c) Change the image to reflect what was clicked.

d) Bonus: Add a "Reset" button that unselects all essentials and displays *panic.jpeg* image.





		
