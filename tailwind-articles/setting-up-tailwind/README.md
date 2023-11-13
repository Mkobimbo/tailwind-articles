THE BEST WAY TO SET UP TAILWIND FOR VARIOUS JAVASCRIPT FRAMEWORKS USING VITE
PREREQUISITES

Basic knowledge of CSS

Knowledge of HTML

Basic command line interface skills

Setting up tailwind with a play CDN link tag

Let's first explore the basic way of installing tailwind.

First, let's open up VScode in a blank directory and create an “index.html” file. Inside the file, we can type in the exclamation mark “!” and then click “enter”.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

</body>
</html>
Here we have a basic scaffolding or boilerplate. For us to observe the changes in our dev server/ live server, let's add an “h1” tag with the text “hello world” to the body.
<body>
<h1>Hello World</h1>
</body>
We can now grab this link "https://cdn.tailwindcss.com", which is also available at the tailwindcss.com website. let's paste it inside the head of our HTML in a script tag.

<script src="https://cdn.tailwindcss.com"></script>

To open up the live server in a browser window, at the bottom right of our vscode window there is a text that says "Go live", click it. In our dev server/ live server notice how our font size and font family on the “hello world” text have changed. This shows us that our tailwind is working. You can add a few tailwind utility classes to our h1 tag just as a demo.

Note that using tailwind via the CDN is not the best choice, since we cannot customize the tailwind default theme, use any directives like @apply, enable additional variants, install third-party plugins, and can't tree shake unused styles. This all means that we can't control the output of this tailwind file. The CDN is mostly used to try tailwindcss as a demo.

Setting up TailwindCss using react with vite

Vite is a super fast frontend build tool that will take our index.html file as an entry point, run tailwind through PostCSS, and also give us a dev server that will update every time we make any changes.

You can create your react project with Vite by typing these two commands in your terminal,
npm create vite@latest my-project -- --template react
cd my-project
type these two commands to install tailwind to your project,
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
this will also generate a tailwind.config.js file and a postcss.config.js file for you. The tailwind.config file allows you to customize your designs.

Next, let's configure our template paths. Simply put "Imagine you're building a colorful LEGO castle, and you want to find the perfect pieces in your LEGO box. Configuring template paths in Tailwind CSS is like telling your friend exactly where to look in the box to find the right LEGO pieces for your castle. It helps Tailwind know where to find the styles it needs, making your website look just the way you want it!" To do that let's add this block of code to our tailwind.config file,
content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
Then we will have this,
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
let's locate an index.css file and these tailwind directives,
@tailwind base;
@tailwind components;
@tailwind utilities;
In your terminal, we can then type the command npm run dev to open up a dev server. Now you can add a few utility classes to your jsx.

And there you have it, we have successfully installed tailwindcss! You can now practice with any projects of your liking. Make sure to always use tailwindcss with a frontend build tool like Vite in order to get support for postcss. This will allow you to create your customized designs. Happy Coding!