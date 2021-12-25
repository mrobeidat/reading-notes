> # React 4

# Dynamic Routes

## Page Path Depends on External Data

**to create dynamic routes for blog posts:**

* We want each post to have the path /posts/(id), where (id) is the name of the markdown file under the top-level posts directory.
* Since we have ssg-ssr.md and pre-rendering.md, we’d like the paths to be /posts/ssg-ssr and /posts/pre-rendering.

## Implement getStaticPaths

**let’s set up the files:**

* Create a file called [id].js inside the pages/posts directory.
* Also, remove first-post.js inside the pages/posts directory — we’ll no longer use this.

***The returned list is not just an array of strings — it must be an array of objects. Each object must have the params key and contain an object with the id key (because we’re using [id] in the file name). Otherwise, getStaticPaths will fail.***

## Implement getStaticProps

**It will return the post data based on id:**

    export function getPostData(id) {
    const fullPath = path.join(postsDirectory, `${id}.md`)
    const fileContents = fs.readFileSync(fullPath, 'utf8')

    // Use gray-matter to parse the post metadata section
    const matterResult = matter(fileContents)

    // Combine the data with the id
    return {
        id,
        ...matterResult.data
    }
    }

**open pages/posts/[id].js and replace this line:**

    import { getAllPostIds } from '../../lib/posts'

**with the following code:**

    import { getAllPostIds, getPostData } from '../../lib/posts'

    export async function getStaticProps({ params }) {
    const postData = getPostData(params.id)
    return {
        props: {
        postData
        }
    }
    }

**let's update the Post component to use postData. In pages/posts/[id].js replace the exported Post component with the following code:**

    export default function Post({ postData }) {
    return (
        <Layout>
        {postData.title}
        <br />
        {postData.id}
        <br />
        {postData.date}
        </Layout>
    )
    }

## Render Markdown

**To render markdown content, we’ll use the remark library.**

    npm install remark@13 remark-html@13

**open lib/posts.js and add the following imports to the top of the file:**

    import remark from 'remark'
    import html from 'remark-html'

**update the getPostData() function in the same file as follows to use remark:**

    export async function getPostData(id) {
    const fullPath = path.join(postsDirectory, `${id}.md`)
    const fileContents = fs.readFileSync(fullPath, 'utf8')

    // Use gray-matter to parse the post metadata section
    const matterResult = matter(fileContents)

    // Use remark to convert markdown into HTML string
    const processedContent = await remark()
        .use(html)
        .process(matterResult.content)
    const contentHtml = processedContent.toString()

    // Combine the data with the id and contentHtml
    return {
        id,
        contentHtml,
        ...matterResult.data
    }
    }

**update the Post component in pages/posts/[id].js to render contentHtml using dangerouslySetInnerHTML:** 

    export default function Post({ postData }) {
    return (
        <Layout>
        {postData.title}
        <br />
        {postData.id}
        <br />
        {postData.date}
        <br />
        <div dangerouslySetInnerHTML={{ __html: postData.contentHtml }} />
        </Layout>
    )
    }

## Polishing the Post Page

***Adding title to the Post Page***

**In pages/posts/[id].js, let’s add the title tag using the post data.**

    // Add this import
    import Head from 'next/head'

    export default function Post({ postData }) {
    return (
        <Layout>
        {/* Add this <Head> tag */}
        <Head>
            <title>{postData.title}</title>
        </Head>

        {/* Keep the existing code here */}
        </Layout>
    )
    }

## Formatting the Date

    npm install date-fns

**create a file called components/date.js and add the following Date component:**

    import { parseISO, format } from 'date-fns'

    export default function Date({ dateString }) {
    const date = parseISO(dateString)
    return <time dateTime={dateString}>{format(date, 'LLLL d, yyyy')}</time>
    }

**open pages/posts/[id].js, add an import for the Date component at the top of the file, and use it over {postData.date}:**

    // Add this import
    import Date from '../../components/date'

    export default function Post({ postData }) {
    return (
        <Layout>
        {/* Keep the existing code here */}

        {/* Replace {postData.date} with this */}
        <Date dateString={postData.date} />

        {/* Keep the existing code here */}
        </Layout>
    )
    }

## Adding CSS

    // Add this import at the top of the file
    import utilStyles from '../../styles/utils.module.css'

    export default function Post({ postData }) {
    return (
        <Layout>
        <Head>
            <title>{postData.title}</title>
        </Head>
        <article>
            <h1 className={utilStyles.headingXl}>{postData.title}</h1>
            <div className={utilStyles.lightText}>
            <Date dateString={postData.date} />
            </div>
            <div dangerouslySetInnerHTML={{ __html: postData.contentHtml }} />
        </article>
        </Layout>
    )
    }

## Development v.s. Production

* In development (npm run dev or yarn dev), getStaticPaths runs on every request.
* In production, getStaticPaths runs at build time.

# Deployment

## Deploy to Vercel

**The easiest way to deploy Next.js to production is to use the Vercel platform developed by the creators of Next.js.**

**Vercel is a serverless platform for static and hybrid applications built to integrate with your headless content, commerce, or database. We make it easy for frontend teams to develop, preview, and ship delightful user experiences, where performance is the default. You can start using it for free — no credit card required.**

## Next.js and Vercel

**Vercel is made by the creators of Next.js and has first-class support for Next.js. When you deploy your Next.js app to Vercel, the following happens by default:**

* Pages that use Static Generation and assets (JS, CSS, images, fonts, etc) will automatically be served from the Vercel Edge Network, which is blazingly fast.
* Pages that use Server-Side Rendering and API routes will automatically become isolated Serverless Functions. This allows page rendering and API requests to scale infinitely.

**Vercel has many more features, such as:**

* Custom Domains: Once deployed on Vercel, you can assign a custom domain to your Next.js app.

* Environment Variables: You can also set environment variables on Vercel. 

* Automatic HTTPS: HTTPS is enabled by default (including custom domains) and doesn't require extra configuration. We auto-renew SSL certificates.

## Develop, Preview, Ship

* Develop: We’ve written code in Next.js and used the Next.js development server running to take advantage of its hot reloading feature.

* Preview: We’ve pushed changes to a branch on GitHub, and Vercel created a preview deployment that’s available via a URL.

* Ship: We’ve merged the pull request to main to ship to production.
