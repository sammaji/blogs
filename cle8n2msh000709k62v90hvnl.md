# Introduction to Tailwind

Are you tired of writing CSS from scratch and spending hours tinkering with styles? Do you want to speed up your web development process without sacrificing customization? Look no further than Tailwind, the utility-first CSS framework that streamlines the styling process and puts control back in your hands. In this blog, we'll cover everything you need to know about Tailwind, from installation to customization, so you can start using it in your projects right away.

## Installation

The installation process is pretty straightforward. The [documentation](https://tailwindcss.com/docs/installation) for tailwind covers that pretty well. There's an official Tailwind [VSCode extension](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) that provides intellisense for tailwind classes. There's also a [prettier plugin](https://www.npmjs.com/package/prettier-plugin-tailwind) that helps to sort and reorder tailwind classes.

## What is Tailwind?

Tailwind is a library that allows you to style your elements in HTML itself. How does that work? Well, tailwind has some utility classes that have predefined styles. All you have to do is add those classes to your HTML elements.

## Examples

Let's say there's a button you want to style with some colors and some round borders. The CSS would look something like this:

```css
button  {
  color: green;
  background-color: greenyellow;
  padding: 1rem 1.25rem;
  border-radius: 4rem;
  border: green 2px solid;
}

button:hover {
  color: white;
  background-color: green;
}
```

Here's how you would do this in tailwind. First, let's add the colors. Now tailwind provides a. We'll choose the one that matches our style `lime-500`. To use the color as background color, just use `bg-lime-500`.

Now for margins and paddings, tailwind provides some convention. To add margin across all directions use `m-value`. For example, `m-4` will apply `1 rem` of margin across all directions. Use `mx-value` to apply margin-left and margin-right only. Similarly use `my-value` to apply margins across top and bottom directions. You can use `mt-value`, `mb-value`, `ml-value` and `mr-value` to apply margins across the top, bottom, left and right directions. (Padding works in a similar manner, just use `p-value` instead of `m-value` and so on.)

For border-radius, we'll use `rounded-full`. I highly recommend checking out the tailwind [docs](https://tailwindcss.com/docs) for reference. Here's what your tailwind style will look like.

```xml
<button class=
"px-5 py-4
 lime-500 bg-lime-500 text-lime-900
 border-2 border-lime-900 border-solid">
Styled with Tailwind
</button>
```

## Handling Pseudo Selectors

Tailwind makes it very easy to handle pseudo-selectors. All you need to do is to append the name of the pseudo selector followed by `:` before your class name. So `focus:bg-lime-900` would change the color of our button on focus and so on.

```xml
<button class=
"px-5 py-4
 lime-500 bg-lime-500 text-lime-900
 border-2 border-lime-900 border-solid
 hover:bg-lime-900 hover:text-neutral-50">
Styled with Tailwind
</button>
```

## Responsiveness

Adding some responsiveness to your website is easier than ever. Tailwind comes with 5 different screen sizes. These are `sm` (&lt;640px), `md` (&lt;768px), `lg` (&lt;1024px), `xl` (&lt;1280px) and `2xl` (&lt;1536px).

To change the color of the button when the screen size gets smaller than 640px, we can add `sm:bg-red-500`.

## Customizations

1. ### Spacing
    

Remember when I mentioned that `m-4` will apply 1 rem of margin across your element? Well, that is the default behavior. You can customize your spacing by modifying the tailwind config file. (If you don't have a tailwind config file, just create one: `tailwind.config.js` .

```javascript
/* tailwind.config.js */
module.exports = {
  theme: {
    spacing: { '2': '1rem', '4': '2rem' }
  }
}
```

Now `m-2`, `p-2` and so on will use 1 rem instead of 0.5 rem and `m-4`, `p-4` and so on will use 4 rem instead of 2 rem. You can use any CSS unit.

1. ### Colors
    

Similar to spacing, you can add your own colors too by modifying the tailwind config file. You can also specify weights as shown below.

```javascript
/* tailwind.config.js */
module.exports = {
  theme: {
    colors: {
      primary: '#F2921D',
      secondary: '#F2CD5C',
      accent: '#BFDB38',
      purple: {
        100: '#EBC7E6',  /* different */
        200: '#BFACE2',  /* shades of */
        300: '#A084DC',  /* purple */
        400: '#645CBB'
      }
    }
  }
};
```

Now we can use our colors in tailwind class names, like `bg-primary` or `text-purple-300` and so on.

1. ### Screens
    

You can modify the screen size for responsiveness as shown below:

```javascript
module.exports = {
  theme: {
    screens: {
      sm: '480px',
      md: '768px',
  }
};
```

You can customize other properties like border-radius, font family and so on. Refer to the [docs](https://tailwindcss.com/docs/theme).

![](https://images.unsplash.com/photo-1608389168343-ba8aa0cb3a63?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80 align="center")