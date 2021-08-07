## Dynamic Routes


### Page Path Depends on External Data

We can pre-render pages with paths that depends on external data
How to Statically Generate Pages with Dynamic Routes
We want each post to have the path /posts/, where is the name of the markdown file under the top-level posts directory.
Since we have ssg-ssr.md (Links to an external site.) and pre-rendering.md (Links to an external site.), we’d like the paths to be /posts/ssg-ssr and /posts/pre-rendering.
Implement getStaticPaths
Create a file called [id].js inside the pages/posts directory.
Also, remove first-post.js inside the pages/posts directory — we’ll no longer use this.
paths contains the array of known paths returned by getAllPostIds(), which include the params defined by pages/posts/- [id].js. Learn more in the paths key documentation.
Ignore fallback: false for now — we’ll explain that later.
Implement getStaticProps
We need to fetch necessary data to render the post with the given id.
Render Markdown
To render markdown content, we’ll use the remark library.
Polishing the Post Page
Adding title to the Post Page

In pages/posts/[id].js, let’s add the title tag using the post data. You’ll need to add an import for next/head at the top of the file and add the title tag by updating the Post component.
Formatting the Date
To format the date, we’ll use the date-fns library
### Adding CSS
Finally, let’s add some CSS using the file styles/utils.module.css we added before. Open pages/posts/[id].js, then add an import for the CSS file


***

### Polishing the Index Page
let’s update our index page (pages/index.js). We need to add links to each post page using the Link component.
Dynamic Routes Details
Fetch External API or Query Database

Like getStaticProps, getStaticPaths can fetch data from any data source. In our example, getAllPostIds (which is used by getStaticPaths) may fetch from an external API endpoint

****
### Development v.s. Production
In development (npm run dev or yarn dev), getStaticPaths runs on every request.
In production, getStaticPaths runs at build time.

****
## Deploying Your Next.js App


### Push to GitHub
Before we deploy, let’s push our Next.js app to GitHub if you haven’t done so already. This will make deployment easier.

On your personal GitHub account, create a new repository called nextjs-blog. The repository can be public or private. You do not need to initialize it with a README or other files. If you need help setting up your repo, take a look at this guide on GitHub. Then:

If you haven’t initialized the git repository locally for your Next.js app, do so now. Push the Next.js app to your GitHub repository.

****
### Deploy to Vercel
The easiest way to deploy Next.js to production is to use the Vercel platform developed by the creators of Next.js.

Vercel is a serverless platform for static and hybrid applications built to integrate with your headless content, commerce, or database. We make it easy for frontend teams to develop, preview, and ship delightful user experiences, where performance is the default. You can start using it for free — no credit card required.
******
### Import your nextjs-blog repository
Once you’re signed up, import your nextjs-blog repository on Vercel.

You’ll need to Install Vercel for GitHub. You can give it access to All Repositories. Once you’ve installed Vercel, import nextjs-blog. You can use default values for the following settings — no need to change anything. Vercel automatically detects that you have a Next.js app and chooses optimal build settings for you.

Project Name Root Directory Build Command Output Directory Development Command When you deploy, your Next.js app will start building. It should finish in under a minute.


****
### Preview Deployment for Every Push
Develop, Preview, Ship

We’ve just gone through the workflow we call DPS: Develop, Preview, and Ship.

Develop: We’ve written code in Next.js and used the Next.js development server running to take advantage of its hot reloading feature.
Preview: We’ve pushed changes to a branch on GitHub, and Vercel created a preview deployment that’s available via a URL. We can share this preview URL with others for feedback. In addition to doing code reviews, you can do deployment previews.
Ship: We’ve merged the pull request to main to ship to production.

