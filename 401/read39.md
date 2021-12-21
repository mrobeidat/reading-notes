# NextJs

## Assets

***Next.js can serve static assets, like images, under the top-level public directory. Files inside public can be referenced from the root of the application similar to pages.***

***The public directory is also useful for robots.txt, Google Site Verification, and any other static assets.***

*let's retrieve profile picture.*

* Download your profile picture in .jpg format.
* Create an images directory inside of the public directory.
* Save the picture as profile.jpg in the public/images directory.
* The image size can be around 400px by 400px.
* You may remove the unused SVG logo file directly under the public directory.

### Unoptimized Image

*With regular HTML*

    <img src="/images/profile.jpg" alt="Your Name" />

*this means you have to manually handle:*

* Ensuring your image is responsive on different screen sizes
* Optimizing your images with a third-party tool or library
* Only loading images when they enter the viewport

### Image Component and Image Optimization

***next/image is an extension of the HTML (img) element, evolved for the modern web.***

***Next.js also has support for Image Optimization by default. This allows for resizing, optimizing, and serving images in modern formats like WebP when the browser supports it.***

***Automatic Image Optimization works with any image source. Even if the image is hosted by an external data source, like a CMS, it can still be optimized.***

### Using the Image Component

***Images are lazy loaded by default. That means your page speed isn't penalized for images outside the viewport. Images load as they are scrolled into viewport.***

    import Image from 'next/image'

    const YourComponent = () => (
    <Image
        src="/images/profile.jpg" // Route of the image file
        height={144} // Desired size with correct aspect ratio
        width={144} // Desired size with correct aspect ratio
        alt="Your Name"
    />
    )

## Metadata

***(title) is part of the (head) HTML tag, so let's dive into how we can modify the (head) tag in a Next.js page.***

### Adding Head to first-post.js 

*Open the pages/posts/first-post.js file and add an import for Head from next/head at the beginning of the file:*

    import Head from 'next/head'

*update the exported FirstPost component to include the Head component.*

    export default function FirstPost() {
    return (
        <>
        <Head>
            <title>First Post</title>
        </Head>
        <h1>First Post</h1>
        <h2>
            <Link href="/">
            <a>Back to home</a>
            </Link>
        </h2>
        </>
    )
    }

## CSS Styling

***Next.js has built-in support for styled-jsx, but you can also use other popular CSS-in-JS libraries such as styled-components or emotion.***

### Writing and Importing CSS

*Next.js has built-in support for CSS and Sass which allows you to import .css and .scss files.*

*Using popular CSS libraries like Tailwind CSS is also supported.*

### Global Styles

*CSS Modules are useful for component-level styles.*

### Adding Global CSS

*In Next.js, you can add global CSS files by importing them from pages/_app.js.*

*The reason that global CSS can't be imported outside of pages/_app.js is that global CSS affects all elements on the page.*

*can place the global CSS file anywhere and use any name. So let’s do the following:*

* Create a top-level styles directory and create global.css inside.
* Add the following content to styles/global.css. It resets some styles and changes the color of the a tag:

        html,
        body {
        padding: 0;
        margin: 0;
        font-family: -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, Oxygen, Ubuntu,
            Cantarell, Fira Sans, Droid Sans, Helvetica Neue, sans-serif;
        line-height: 1.6;
        font-size: 18px;
        }

        * {
        box-sizing: border-box;
        }

        a {
        color: #0070f3;
        text-decoration: none;
        }

        a:hover {
        text-decoration: underline;
        }

        img {
        max-width: 100%;
        display: block;
        }

*Finally, open pages/_app.js add import the CSS file like so:*

    import '../styles/global.css'

    export default function App({ Component, pageProps }) {
    return <Component {...pageProps} />
    }

## Styling Tips

### Using Sass 

*Next.js allows you to import Sass using both the .scss and .sass extensions.* 

    npm install sass

### Customizing PostCSS Config

*To customize PostCSS config, you can create a top-level file called postcss.config.js. This is useful if you’re using libraries like Tailwind CSS.*

    npm install tailwindcss postcss-preset-env postcss-flexbugs-fixes

# React Context for Beginners

## What is React context?

***React context allows us to pass down and use (consume) data in whatever component we need in our React app without using props.***

## When should you use React context?

***React context is great when you are passing data that can be used in any component in your application.***

*These types of data include:*

* Theme data.
* User data.
* Location-specific data.

***Data should be placed on React context that does not need to be updated often.***

## What problems does React context solve?

***React context helps us avoid the problem of props drilling.***

***Props drilling is a term to describe when you pass props down multiple levels to a nested component, through components that don't need it.***

## How do I use React context?

***Context is an API that is built into React, starting from React version 16.***

*There are four steps to using React context:*

1. Create context using the createContext method.
2. Take your created context and wrap the context provider around your component tree.
3. Put any value you like on your context provider using the value prop.
4. Read that value within any component by using the context consumer.

## What is the useContext hook?

***Another way of consuming context became available in React 16.8 with the arrival of React hooks. can now consume context with the useContext hook.***

***Instead of using render props, we can pass the entire context object to React.useContext() to consume context at the top of our component.***
