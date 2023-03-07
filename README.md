### JSDR 213

# Introduction to CSS

![css-image](https://www.tutorialrepublic.com/lib/images/css-illustration.png)

## Overview

So far we've learned how to set up and structure a HTML file. Now we'll make it look pretty! This an introductory lesson to CSS. We'll touch on very basic topics ranging from positioning to coloring. 


You will not be the DaVinci of CSS by the end of this lesson. But 12 weeks from now, when you are presenting your capstone project, you will be amazed at how much you are able to do and how much you have learned.



## Objectives

- Learn how to link stylesheets
- Learn how to position elements
- Learn parent child relationships
- Learn CSS specificity



## Getting Started

- Open the previous HTML lesson we worked on this morning in your code editor and web browser

## What Is CSS?

![Cascade](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2F31.media.tumblr.com%2Fcd2ca2396c0bd6251170ef25810ef755%2Ftumblr_mu1nvtnk9e1s85u2fo1_500.gif&f=1&nofb=1)

CSS stands for `cascading style sheets`. This means that when the file is read, it is being read from top to bottom. (We'll see how this works in just a bit)

> CSS describes how HTML elements are to be displayed on screen, paper, or in other media.
>
> CSS saves a lot of work. It can control the layout of multiple web pages all at once.

### Why CSS?

From W3Schools:

> HTML was NEVER intended to contain tags for formatting a web page!
>
> HTML was created to describe the content of a web page, like:
>
> - `<h1>This is a heading</h1>`
>
> - `<p>This is a paragraph.</p>`
>
> When tags like `<font>`, and color attributes were added to the HTML 3.2 specification, it started a nightmare for web developers. Development of large websites, where fonts and color information were added to every single page, became a long and expensive process.
>
> To solve this problem, the World Wide Web Consortium (W3C) created CSS.
>
> The style definitions are normally saved in external .css files.
>
> With an external stylesheet file, you can change the look of an entire website by changing just one file!

![Flair](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmedia.giphy.com%2Fmedia%2FV80llXf734WzK%2Fgiphy.gif&f=1&nofb=1)

## Applying Some Flair To Our HTML

You've been provided an `index.html` file, the contents may be familiar to you, we built it in the previous lesson!

First things first, let's create a `style.css` file in this lesson folder.
You can do this by either using the `touch` command:

`touch style.css`

Or by using the new file button in VSCode.

### Linking Our Stylesheet

In order for our `style.css` file to be used by our html file, we need to link the two of them together. We can accomplish this by using a `link` tag in our `index.html`.

Open your `index.html`, add the following to the head section in the HTML file:

```html
<link rel="stylesheet" href="./style.css" />
```

`rel` stands for *relationship*. The relationship of the linked file to our HTML page.

`href` stands for *hypertext reference*. The location of the file we're linking.

**NOTE**: Place this tag before the opening `title` tag in the HTML file.

Your `head` section should look like the following:

```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="./style.css" />
  <title>Document</title>
</head>
```

#### Discuss (5 min)

Quick Questions:

- Why do we link CSS files in the head section?
- Can you link multiple CSS files?
- Can you link external CSS files?

### Applying Styles

Open your `style.css` file and add in the following:

```css
body {
background-color: blue
}
```

Notice the syntax involved; we are grabbing an element, then targeting a property, then giving it a value. In this case, we are taking the background of the whole HTML body and making the background blue.

What do you think we'd need to do to make it Red instead?


Let's style the `nav` element. Add the following to your CSS file:

```css
nav {
  background-color: #b39ddb;
  padding: 10px
}
```
That color code is written in what is known as the "Hexidecimal" system, with 16 different characters (0-9, A-F) that we can use. The first 2 digits control the level of Red, the second 2 are for our Green values, and the last 2 control the Blue levels.  #000000 is the lowest value possibe - Black, while #FFFFFF is everything set to max - White. #FF0000 would be a strong Red, #0000FF would be a deep Blue


Now that we've discussed the code used for colors, notice the syntax for padding, this is shorthand for applying padding on an element. Padding is the space between the Content and the Border of the elements. We can use Pixels for this, as well as %'s, and more advanced methods such as vH, vW, em, and rem, which we will discuss more as we continue moving forward. 

The important thing is keeping our CSS syntax correct so that we are only working with the element that we want to target.

Lets add a margin to the Nav as well. Play with the margin and padding numbers and see what they do and how they interact with each other. 


### Styling Our Elements

You'll notice that our content is not very pretty, let's fix that.

Add in the following styles:

```css
ul {
  list-style: none;
}

li {
 color: green;
 letter-spacing: 5px
}
```

We separate each line of CSS in its respective block with a semi-colon. If we leave this out, it will not work. It is not required if we are only using one line of CSS, or if we are working on the final line. This will make much more sense as we continue working with it!


### Selecting Elements by Data Attributes


We have  2 data attributes in our html file, Class and Id. 

To target everything in a class, we use a . before the class name

To target an element with a specific ID, we use a #

Because CSS is "Cascading", it can become problematic when targets are selected in multiple ways. We usually want to work with the most general first, then specify more and more as we go down. Use the acronym ICE for this, Id Class Element, in terms of specifcity

We want to make all of our buttons a certain size, make only the login buttons green, and give a yellow border to our log out button

Lets first target all buttons, then only those of our login class, and finally our individual log in button

```

button {
height: 200px;
width: 350px
}

.login-button {
background-color: green
}

#logout {
border: 5px solid yellow
}

```


As you can see, some properties take only one argument, while others (Border) take multiple. Don't worry about memorizing all of these nuances yet, as we play and learn more with CSS they will make more sense to you.

We can use Height and Width to control the sizes of things like Images, Buttons, and Divs/Boxes. Try using the different measurements (px, %, em, rem) and see how they differ. 

Notice how all of our buttons have taken the respective sizes. However, only the two with the Login class changed color. And, only the one Log Out button has the border.

Can you think of any examples of something similar you have seen across the web?


Again, don't worry about memorizing every single CSS element, what matters more is finding out how to use them, and understanding the rules of the language.

Lets take a few more minutes to play with some text. In our HTML file, add this code wherever you'd like

```
<h3> I am a generic H3 </h3>
<h3 class="underlined"> I am an H3 with class </h3>
<h3 class="underlined" id="spaced"> I am an H3 with class and an ID </h3>

```

We have the ability to give as many attributes to each element that we want as long as we follow the rules. We also can assign multiple classes to elements with something called "Polymorphism" that we'll discuss later in our lesson on Object Oriented Programming


Lets style these H3's!

```
h3 {
font-size: 36px
}

.underlined {
text-decoration: underline;
color: #FF0033
}

#spaced {
letter-spacing: 10px
}

```

There is a lot that we can do with CSS! The best way to learn is to practice. Now, lets dive a bit deeper and find some more ways we can style up our content
 
 
## You Do - 20 minutes

There are hundreds of different properties we can use with our CSS. Lets explore https://www.w3schools.com/css/default.asp , search for at least 3 different propertiees to work with, and implement them onto your page.

Note - There are some (color, text-size, letter-spacing) that will only work on Text, while others (height, width, background-color) that will work on block elements, but not Text. It can difficult, but the more you practice, the more comfortable you'll feel with these!



- [Aligning Divs Side by Side](https://www.w3schools.com/cssref/pr_class_float.asp)
- [Aligning Text Center](https://www.w3schools.com/cssref/pr_text_text-align.ASP)
- [Applying Borders](https://www.w3schools.com/cssref/pr_border.asp)
- [Applying Background Colors](https://www.w3schools.com/cssref/pr_background-color.asp)

Keep in mind, class styling properties can be shared with multiple elements with the same class.

## Recap

In this lesson we touched on the basics of CSS. We linked our stylesheet and implemented some styling to our HTML.
Like our HTML elements and Terminal commands, we do **not** expect you to memorize and fully understand every single CSS property by the end of today, but as we continue on in this class, we want you to take note of which commands you are using the most, and which ones you find the most interesting.

## Resources

- [W3Schools CSS Reference](https://www.w3schools.com/cssref/default.asp)
- [W3Schools CSS Tutorial](https://www.w3schools.com/css/default.asp)

### FUN GAME TO LEARN CSS
- [CSS Defense](https://cssbattle.dev/)
