# Use Tailwind CSS For All Web-based Styling Needs

As an initial note, all current Central Advancement development projects render on the web, and this document only relates to
applications deployed to be rendered in a web browser.

[Tailwind CSS](https://tailwindcss.com/) is a very popular and growing CSS framework that allows you to "rapidly build modern websites 
without ever leaving your HTML".

## Status

This methodology has been accepted and used in the new CMS project. Furthermore, while exploring CMSes in different languages, Tailwind
allows for really simple migrations. Current, half-finished projects will need to be refactored.

The documentation has been updated in the following places:
- 

## Context

In early 2020, developers tested out creating a component library standardized on React and its ecosystem. Within that, Theme UI was
selected as the base to build the component library off of. While Theme UI uses the same "design spec" with "constraints" as Tailwind CSS,
you cannot use Theme UI code outside of React.

```jsx
// Theme UI add margin-top with fifth element of spacing array. Renders as a <div> tag.
<Box sx={{mt: 4}}></Box>

// Tailwind CSS plain HTML with plain CSS class that adds margin-top with fifth element of spacing array.
<div class="mt-4"></div>
```

As you can see, the syntax is nearly identical once you take the `sx` style object and convert to a string.

Another point is that Tailwind has built-in table and form support, whereas Theme UI is lacking in those areas. It is far easier to
find Tailwind examples on the internet that can be utilized in projects than it is to find Theme UI based answers. 

## Decision

Create starter templates and docs for adding Tailwind CSS to a project. The Tailwind site already has help in this area, and for
starters, some current code files can be used to explain how to add Tailwind within those languages and frameworks.

## Consequences

Because of this change, both the component library and giving-frontend projects will need to be refactored to drop Theme UI and
use Tailwind. However, the refactoring work is made trivial by the almost identical syntax.