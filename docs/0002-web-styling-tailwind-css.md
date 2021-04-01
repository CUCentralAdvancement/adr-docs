# Use Utility-first CSS Frameworks For All Web-based Styling Needs

As an initial note, all current Central Advancement development projects render on the web, and this document only relates to
applications deployed to be rendered in a web browser.

[Tailwind CSS](https://tailwindcss.com/) is a very popular and growing CSS framework that allows you to "rapidly build modern websites 
without ever leaving your HTML". It exemplifies the "utility-first CSS" styling mentioned in the ADR title and will be used throughout 
the document as an example.

However, many of these utility-first CSS frameworks use the same syntax...

## Status

This methodology has been accepted and used in all the Digital Engagement web projects on Heroku. Furthermore, while exploring projects
across languages and frameworks, utility-first frameworks are on the rise. Tailwind CSS is quite popular and that's the main reason DE
developers recommended using Tailwind.

The documentation has been updated in the following places:

- Brief instructions on how to install and use Tailwind: https://github.com/CUCentralAdvancement/github-docs/blob/main/docs/frontend/tailwind.md

## Prior Art

When you go to style an element on a website you have many choices. One decision you have to make as a developer is where your main
styling rules will live: global or scoped/inline CSS. Digital Engagement developers were used to traditional, global CSS styling until
using some "utility-first CSS frameworks."

Rather than DE devs writing out the particular points of contrast in styles, you should read from the creators of Tailwind:

- Explanation of "utility-first" and the benefits: https://tailwindcss.com/docs/utility-first

TLDR;
- You aren't wasting energy inventing class names.
- Your CSS stops growing.
- Making changes feels safer than with global stying.
- Having constraints via the theme object forces more consistency in styles.
- Responsive design and hover, focus, etc. states easily fit inline.
- You can extract common utility class combinations into reusable components.

## Context

In early 2020, DE developers tested out creating a component library standardized on React and its ecosystem. Within that, Theme UI was
selected as the base to build the component library off of. While Theme UI uses the same "design spec" with "constraints" as Tailwind CSS,
you cannot use Theme UI code outside of React.

```jsx
// Theme UI add margin-top with fifth element of spacing array. Renders as a <div> tag.
// Medium breakpoint has a different amount of margin via array syntax.
<Box sx={{mt: [4, 2]}}></Box>

// Tailwind CSS plain HTML with plain CSS class that adds margin-top with fifth element of spacing array.
// Medium breakpoint has a different amount of margin via modifier prefix.
<div class="mt-4 md:mt-2"></div>
```

As you can see, the syntax is nearly identical once you take the `sx` style object and convert to a string. Also, the responsive styling
changes from positions in an array to a modifier prefix, which is a more descriptive and cleaner syntax.

To address the complaints of "ugly looking HTML" and style reuse, components can be abstracted and styling "hidden" inside them and exposed
via passed-in component props.

Another point is that Tailwind has built-in table and form support, whereas Theme UI is lacking in those areas. It is far easier to
find Tailwind examples on the internet that can be utilized in projects than it is to find Theme UI based answers. 

## Decision

Create starter templates and docs for adding Tailwind CSS to a project. The Tailwind site already has help in this area, and for
starters, some current code files can be used to explain how to add Tailwind within those languages and frameworks.

- Brief Intro - https://github.com/CUCentralAdvancement/github-docs/blob/main/docs/frontend/tailwind.md

## Consequences

Because of this change, both the component library and giving-frontend projects will need to be refactored to drop Theme UI and
use Tailwind. However, the refactoring work is made trivial by the almost identical syntax.
