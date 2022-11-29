Phase 1 - Project 1 - Skilled e-Learning Landing Page

[![Netlify Status](https://api.netlify.com/api/v1/badges/ac66a00b-235b-41c5-8a72-aff5eae6a2f4/deploy-status)](https://app.netlify.com/sites/skilled-landing-page-parables/deploys)

## Intro

This is a project demonstrates my understanding of basic HTML and CSS.

## Features

### Immutability

#### Compose don't override (E.g:Tailwind)

It is a common practice to see CSS with some class names like `btn btn-primary btn-lg`. If you look under the hood of these class names, the base class `btn` might contain all the defaults and the other class names override the base class to create more specific rules.

While this approach is not entirely bad, it does have some serious downsides which should be taken into consideration especially if its a big project: it become very difficult to touch a class with breaking it for other elements using the same class.

A trivial solution to this downside is to add another class that overrides the existing properties set by previous classes. You may end up with a bloated stylesheet. Open up the browser dev tools and you will see the many properties which have no effect on the element simply because it inherited a bunch of useless properties from a super class.

Frameworks like TailwindCSS addresses such issues by providing low-level utility classes which allows you to compose your CSS rules.

If you seriously despise the idea of sprinkling your HTML with _a little amount of inline CSS_, then you should definitely split up those super class names into smaller explicit ones: a base `btn` class name that sets the properties that are common to all buttons, `btn-primary` that only sets the color of the button and `btn-lg` that only sets the size of the button.

> Spoiler alert: You may end up writing your own low-level utility CSS Framework like Tailwind you with the recommendation

#### No side effects/overriding base rules/styles

The flexibility you get using composable low-level CSS utility class names give you the freedom to fine-tune your design to meet the requirements.

Change that class without breaking it for others or create a new low-level utility class that you can reuse.

Save the browser the headache of having to go through that BLOB you call stylesheet just to render a single web page.

Save you fellow developers and the future you, the trouble of scrolling up and down the CSS file in order to track the dependencies of a class.

> I like my code to be elegant and efficient. The logic should be straightforward to make it hard for bugs to hide, the dependencies minimal to ease maintenance, error handling complete according to an articulated strategy, and performance close to optimal so as not to tempt people to make the code messy with unprincipled optimizations. Clean code does one thing well.
>
> Bjarne Stroustrup, inventor of C++ and author of The C++ Programming Language

#### Avoid className pollution/abuse

> CSS classes serve one purpose: to keep your CSS file DRY(Don't Repeat Yourself). It allows you to share and reuse the same rules with various element using the name of the class.

It is a sad thing to see beginner courses teach newbies to style elements by selecting it with a className.

> CSS classes are **NOT** the **ONLY** way to select element and apply some styling to it.

There are better, more advanced and highly readable [selectors in CSS]() that allows you to express your styles. If your reason for using a class is to style **an** element, I mean **a single element**, then you are better of using an `#id` selector instead.

If you finding yourself writing more class names, then its a clear indication that your HTML is really bad.

> The key to writing good CSS starts with writing good HTML.

Also keep the class names short, readable, self-explanatory and explicit enough to infer what the class is doing from just the name and avoid irregular casing in your class names. `.some-really__nasty-class-name` `.__dont-do__this-to` `.--your` `.future_self`

> Only use a class if that set of rules will be reused with various element.

#### Separation of concern - Split the BLOB into smaller explicit files

One thing I highly prioritized in this project is to have a clear boundary for my stylesheets to make it easy to write responsive styles for only one device without worrying about overriding styles for other devices.

By separating the styles for each device, I get small chunks of files which can be loaded by the browser faster than one huge gigantic BLOB CSS file. Thanks Webpack/Vite, I don't need you to split this code into chunks.

If you want to change something, you know exactly where to look. Modify your responsiveness without breaking it for other screens.

Touch your CSS with confidence.

> Clean code can be read, and enhanced by a developer other than its original author. It has unit and acceptance tests. It has meaningful names. It provides **one** way rather than many ways for doing one thing. It has minimal dependencies, which are explicitly defined, and provides a clear and minimal API.
>
> “Big” Dave Thomas, founder of OTI, godfather of the Eclipse strategy

#### Easy to understand

Following the idea of writing good HTML, make your CSS rules align with the markup they are selecting. Order your rules to follow a symmetric pattern to the HTML.

If you have a `nav` element insider a `header` element and you want to style both elements, start with the `header` and go depth-first into all the elements in the `header` before moving out of the `header` into other block elements.

Still on the subject of code readability, use the appropriate HTML semantic elements for the right job.

> It's an eyesore to see an HTML document where everything is a `div`

Communicate the intention of your code by using the right elements. A button to communicate a command/action intent, a link to navigate to other sections/pages, a div to group related elements in one block.

> Do consider everyone and make your code accessible to both humans and machines,

#### Easy to maintain

Change designs,make it responsive to various devices and implement new features, as requirements change with ease without breaking anything.

Test the critical business requirements. Give yourself a button you can push anytime you modify the code that ensures that nothing is breaking.

> I could list all of the qualities that I notice in clean code, but there is one overarching quality that leads to all of them. Clean code always looks like it was written by someone who cares. There is nothing obvious that you can do to make it better. All of those things were thought about by the code’s author, and if you try to imagine improvements, you’re led back to where you are, sitting in appreciation of the code someone left for you—code left by someone who cares deeply about the craft.
>
> Michael Feathers, author of Working Effectively with Legacy Code

## Improvement

- Accessibility: This project is accessible to everyone.
  To keep the project scope lean, accessibility was not implemented
  but adding it won't make it any worse but rather improve the whole User Experience.

- Testing: The benefit of having a button that you can push anytime to check if your requirements are being implemented is something that can't be over-pra

If this project is going live, then `a11y` is a _MUST have_

## Tools and Resources Used

- VS Code
- Color Names
- Variable Fonts
- Clean Code - A Handbook of Agile Software Craftsmanship By Robert C Martin
  The code used in this project were crafted with the principles taught by this book in mind and heart. The book has heavily influenced how I craft my codes and I highly recommend it

Quotes with the authors beneath them were sourced from the Book: Clean Code - A Handbook of Agile Software Craftsmanship By Robert C Martin
