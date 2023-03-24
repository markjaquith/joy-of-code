---
title: Deploy A Full Stack SvelteKit App
description: Learn how to deploy a full stack SvelteKit app with a database and authentication for free.
slug: sveltekit-deployment
published: 2023-3-24
category: sveltekit
draft: true
---

# Deploy A Full Stack SvelteKit App

## Table of Contents

## Previously

This is part of a [SvelteKit series](https://www.youtube.com/watch?v=obmiLi3bhkQ&list=PLA9WiRZ-IS_zfHpxmztJQLeBISsQkh9-M) and while each part is meant to be self-contained here are the previous parts in case you want to catch up:
- [What is SvelteKit?](https://joyofcode.xyz/what-is-sveltekit)
- [SvelteKit Project Structure](https://joyofcode.xyz/sveltekit-project-structure)
- [SvelteKit Routing](https://joyofcode.xyz/sveltekit-routing)
- [SvelteKit API Endpoints And Loading Data For Pages](https://joyofcode.xyz/sveltekit-loading-data)
- [Working With Forms In SvelteKit](https://joyofcode.xyz/working-with-forms-in-sveltekit)
- [Using Advanced Layouts In SvelteKit](https://joyofcode.xyz/sveltekit-advanced-layouts)
- [Learn SvelteKit Hooks Through Example](https://joyofcode.xyz/sveltekit-hooks)

## Web Hosting Types

If you just want to learn how to host your SvelteKit project at no cost and don't care learning about the landscape of hosting I'm not going to take it personal, so skip to the [deploying your SvelteKit project](https://joyofcode.xyz/deploying-sveltekit/#deploying-a-sveltekit-project) section but I promise you it's worth your time.

There are several types of affordable web hosting you can use that is great for a beginner or small business:
- **Shared hosting** where multiple websites share the same server resources such as CPU, RAM, and disk space with not much customization (the hosting provider sets the limits on resource usage and what you can install and how you can configure the server)
- **Virtual Private Server** (VPS) hosting is similar to shared hosting but spins up a virtual machine on the same hardware that can be dedicated to you or shared with others but is more customizable (you can do whatever you want since you have control over everything from the operating system you use to allocating resources as you see fit)
- **Cloud hosting** is arguably the cheapest because you only pay for how much you use and it does the scaling for you because it works at a large scale and is very competitive

## Specialized Cloud Providers

{% img src="specialized.webp" alt="Specialized hosting solutions" %}

You might be familiar with some traditional hosting solutions but I'm going to refer to them as specialized hosting solutions because they're all cloud providers such as [Digital Ocean](https://www.digitalocean.com/), [Linode](https://www.linode.com/) or [Vultr](https://www.vultr.com/) which can get you started for a cool **$5**/month and have integrations with popular services.

This web hosting lore is mostly so we can understand things moving on and you shouldn't concern yourself with infrastructure and scaling because if scale ever becomes a problem for you then you're a more serious business that can afford to pay someone else to manage the infrastructure.

## Generalist Cloud Providers

{% img src="generalist.webp" alt="Generalist hosting solutions" %}

Besides the specialized cloud providers that are nice and easy to use because they're focused on consumers you have the giant generalist cloud providers such as [Amazon Web Services (AWS)](https://aws.amazon.com/), [Google Cloud Platform (GCP)](https://cloud.google.com/) or [Microsoft Azure](https://azure.microsoft.com/) that offer a lot more services and are aimed at large enterprise.

I don't blame you if you think this is irrelevant because generally it's not important but in this case it's going to help us understand how the next tier of hosting came to be.

## Serverless Platforms

{% img src="serverless.webp" alt="Serverless hosting solutions" %}

The problem with infrastructure as a service like AWS is that you need a degree to understand how to use it , so companies like [Vercel](https://vercel.com/) realized they could make an easy to use **CLI** around some of the **AWS offerings** like [AWS Lambda](https://aws.amazon.com/lambda/) and then provide you with an easy to use **frontend** and charge you money for it which makes everyone happy.

Some of the popular serverless hosts also include [Netlify](https://www.netlify.com/) and [Cloudflare Pages](https://pages.cloudflare.com/) which you might have heard of due to the popularity of [Jamstack](https://jamstack.org/) sites which there's no clear definition for but it's just an architecture where you use different APIs to make a site and it doesn't have to be static.

Another selling point is the built-in **continuous integration** (CI/CD) you get just for using such a service because you can focus on writing code and not think about infrastructure and deployment — when you push changes to [GitHub](https://github.com/) it's going to redeploy the site which is a great developer experience.

**Serverless is a misnomer** because it doesn't mean there are no servers but it means you don't have to provision and manage servers yourself but the scaling and monitoring is done for you.

In a traditional server-based environment you have a long running process in the background which is your server but if you only use it to send a newsletter once a week it's a waste of electricity but using serverless your code is split into functions that spin up when triggered by events and spin down once they're done.

If you think about the last paragraph this answers the question **"Why don't WebSockets work on Vercel?"** because they require a long running process but serverless functions are stateless and ephemeral.

I want to emphasize that **it's worth paying for things** but you might be just starting your web development journey or don't have an income and this means you can host your project at **no cost** on these services because they have a generous free tier without any gotchas like requiring a credit card to drain your wallet once you go over the limit.

The site you're on uses Vercel and I haven't paid anything so far and what's more awesome is if your project is open source and non-commercial [Vercel can sponsor your project](https://vercel.com/guides/can-vercel-sponsor-my-open-source-project). 

## Full Stack Platforms

{% img src="full-stack.webp" alt="Full stack platforms" %}

I could not think of a better name for these sort of hosting services, so I named them "full stack platforms".

You might have heard of [Heroku](https://www.heroku.com/) because they take the amazing developer experience of something like Vercel but do it for the entire stack by having instant deploys configured.

Heroku has fallen out of favor recently because of their changes to their business model but there's also a lot more alternative to take their place including [Railway](https://railway.app/), [Render](https://render.com/) and [Fly.io](https://fly.io/) which is unique because it deploys your app across the globe so it's close to your users.

The reason why I haven't picked one of these in this case is because they're more complicated because it involves Docker and some of them require a credit card to prevent abuse but it doesn't mean they're not awesome.

## Serverless Databases

{% img src="databases.webp" alt="Serverless databases" %}

Because serverless has it's unique set of problems there's a bunch of serverless database providers you can use including [Supabase](https://supabase.com/) (PostgreSQL), [PlanetScale](https://planetscale.com/) (MySQL) and [MongoDB Atlas](https://www.mongodb.com/atlas/database) (MongoDB) but in this case the important part is that they have a generous free tier and some of them offer a lot more like Supabase and you can't go wrong if you pick any of these serverless databases.

That being said I'm not a huge fan of [Firebase](https://firebase.google.com/) because to me the most important thing to look out for is that you don't use something proprietary that locks you and it's hard to move from because if any of these services bites the dust you can easily move to something else.

There's also other options like [Fauna](https://fauna.com/) and [Hasura](https://hasura.io/) which I haven't looked into because it seems tied to GraphQL but you might be interested in it and there's also some new and exciting databases like [Xata](https://xata.io/) (PostgreSQL) and [Upstash](https://upstash.com/) for serverless [Redis](https://redis.io/).

Another reason why the database you pick doesn't matter if it's SQL or MongoDB based is because the project I have prepared uses [Prisma](https://www.prisma.io/) which is awesome because instead of writing raw SQL or MongoDB you write a schema that looks like TypeScript and [you can use any of the supported database connectors](https://www.prisma.io/docs/concepts/database-connectors).

## Hosting Your Own Platform As A Service

If you want to have control over everything you can host your own platform as a service (PaaS) using [Coolify](https://coolify.io/) and [CapRover](https://caprover.com/) using a cheap $5/month VPS which gives you an awesome self-hosted alternative to Heroku with one-click installs.

## Deploying A SvelteKit Project

I have prepared a full stack [SvelteKit blog example](https://github.com/joysofcode/sveltekit-blog) that uses Prisma for the database with PostgreSQL and authentication because real projects are more complicated and it's not much harder to host compared to a static blog.

You're going to need to create these accounts:
- [GitHub](https://github.com/) account
- [Supabase](https://supabase.com/) account
- [Vercel](https://vercel.com/) account

You can use GitHub to log-in to the rest and Vercel is going to ask your permission to access GitHub anyhow when you add a project.

I'm going to use Supabase just to provision a PostgreSQL database to use with Prisma instead of using their [JavaScript Client Library](https://supabase.com/docs/reference/javascript/introduction) because we need the connection string for the database.

- [Go to projects in Supabase](https://app.supabase.com/projects) and create a new project you can name whatever but I'm going to name it **blog**
- Copy the password you generated
- On the right sidebar go straight to **settings** and pick **database** and scroll to the **connection string** section
- Select **URI** which starts with `postgresql://` and copy it then replace `[YOUR_PASSWORD]` including brackets with the generated password

> 🛑 **Do not** under any circumstance share your database **connection string** with anyone and make sure in your future projects you don't commit the **.env** file on accident but in case you do make sure to reset everything.


If you haven't create a new GitHub project and use `degit` to copy over the example project in a new project you created after which you should push it to your own repository you created.

```shell
pnpx degit joysofcode/sveltekit-deploy
```

- Install the dependencies with `pnpm i`
- Rename `.env.example` to `.env` and put your connection string inside `DATABASE_URL`
- Type `pnpx prisma db push` in your terminal and run it which is going to create the tables from your Prisma schema in Supabase

If you run the development server with `pnpm run dev` you should only see the **Latest Posts** title because we don't have any posts yet.

You can go to `http://localhost:5173/dashboard` and register an account and log in to start creating and adding posts inside the dashboard but it would be more awesome to host the SvelteKit app on Vercel.

SvelteKit has [official adapters](https://kit.svelte.dev/docs/adapters) for different platforms that are responsible for adapting your app to the deployment target. If you open `svelte.config.js` you're going to see the default adapter is `@sveltejs/adapter-auto` that outputs to Node.js if it can't detect a supported platform. If you deploy to Vercel it's going to pick it up and use `@sveltejs/adapter-vercel`.

Using the Vercel adapter is optional but they recommend you do it.

```shell
pnpm i -D @sveltejs/adapter-vercel
```

Then you just need to change the import.

```ts showLineNumbers
import adapter from '@sveltejs/adapter-vercel'
```

After you're done deploying is easy:

- [Create a new project on Vercel](https://vercel.com/new)
- Import your project from the list of Git repositories
- Under **environment variables** add **DATABASE_URL** as the **name** and the database connection string as the **value** and press **ADD**
- Press **Deploy**

The deploy should take under a minute and you can see what's going on in the **building** section. Don't let this freak you out because the output is the same thing if you were to run the build command but on someone else's computer. This is why it's important to read it if you get any errors during deployment.

> 🐿️ Before you deploy to Vercel run `pnpm run build` and `pnpm run preview` in development which helps surface some problems like TypeScript errors even if the environment isn't the same.

Congrats! 🎉

You just deployed a full stack SvelteKit application with a database and authentication you can share with friends or put on your resume.

You can stop here or continue reading the next section where I'm going to show you how to optimize your site.

## Optimizing Your Deployment

Our site looks fresh but did you notice it uses server-side rendering and if the database region you picked is close to you it's also super fast.

People assume that only a static site can be fast but it's not true and instead of having to rebuild your site when you make a typo the changes you make are going to be instant.

This doesn't mean we can't take advantage over things that make a static site fast like using Vercel's **content delivery network** (CDN) to cache the pages.

A CDN are just some computers around the globe that take the static assets like images, video and HTML and host them close to you, so when you make a request it's super fast.

{% img src="cdn.webp" alt="Content delivery network" %}

Going back to how SSR isn't slow because it's cheap to build a HTML page on the server but the expensive part and problem are the physics because of latency if you make a request to a database far away from you.

This is what [edge computing](https://en.wikipedia.org/wiki/Edge_computing) is trying to solve and you can think of it like a CDN but instead of static assets it moves data closer to you.

{% img src="edge.webp" alt="Edge computing" %}

You don't have to think about it because I'm going to show you something simpler and that's using regular [Cache-Control](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control) HTTP headers.

The reason why you want to use caching is because if you have a popular post each request means work for the server but if you use caching it can serve the post from the CDN instead of fetching the data and building the HTML page on each request. 

{% img src="blog.webp" alt="SvelteKit blog" %}

Let's think about how we want to cache individual routes of our site:
-  The `/` route can be cached for an hour because it's not important but maybe a minute is more reasonable
- The `/blog` route where you can search for posts can also be cached for an hour because it's not important
- The `/blog/[slug]` route can be cached for a minute because it's important but you can also cache older posts longer
- The `/dashboard` is the content management system and I always want fresh data, so we don't have to do anything here
- The `/about` route is never going to change so we can prerender it and even disable client-side navigation since it's not going to be viewed a lot
- The `/newsletter` route never changes but it uses SvelteKit actions, so you can't prerender it because it requires a server
- The `/rss.xml` route is also not important and we can cache it for an hour

Caching sounds complicated but it's not and it makes you think about your content. This kind of experience would not be possible with a pure static site and server-side rendering let's you do more and is fast enough to not even be noticeable.

The only thing you have to know is that we need to set `Cache-Control` headers with `max-age=0, s-maxage=60`.  The `max-age=0` directive says to never cache the content on disk and `s-maxage=60` let's a shared cache like a CDN know how long to cache something in seconds which is `60 seconds` here.

> 🐿️ If you're hosting a static site on Vercel or Netlify they set the cache control headers for you to `s-maxage=31536000` which is the maximum value of one year. If you need to bust the cache you have to redeploy.


I promise that's everything! You learn it once and you're set for life because you're using the web platform that's going to work the same in a hundred years if AI didn't replace us.

To set headers in SvelteKit you can use the `setHeaders` method you have access to in `+page.server.ts` and `+server.ts` files.

```ts showLineNumbers
// routes/+page.server.ts
export const load = async ({ setHeaders }) => {
  setHeaders({
    'Cache-Control': `max-age=0, s-maxage=${60 * 60}`,
  })

  // ...
}

// routes/blog/+page.server.ts
export const load = async ({ setHeaders }) => {
  setHeaders({
    'Cache-Control': `max-age=0, s-maxage=${60 * 60}`,
  })

  // ...
}

// routes/blog/[slug]/+page.server.ts
export const load = async ({ params, setHeaders }) => {
  setHeaders({
    'Cache-Control': `max-age=0, s-maxage=60`,
  })

  // ...
}

// routes/rss.xml/+server.ts
export const GET = async ({ url }) => {
  // ...

  return new Response(feed.xml({ indent: true }), {
    headers: {
      'Content-Type': 'application/xml',
      'Cache-Control': `max-age=0, s-maxage=${60 * 60}`,
    },
  })
}
```

For the `/about` page we can use [SvelteKit page options](https://kit.svelte.dev/docs/page-options) to prerender it and even disable server-side rendering since we don't need JavaScript.

```ts:routes/about/+page.ts showLineNumbers
// prerender page
export const prerender = true

// disable client-side routing
export const csr = false
```

If you push the changes you're going to see something magical. Vercel is going to redeploy your site when you push the code because it has built-in CI/CD with GitHub and this even works when you push a new branch if you want to preview a deploy before you push it to the main branch.

With some clever caching your site is more resilient and can withstand a lot more traffic which is great if you're using the already generous free tier — I hope you learned a lot and you're not afraid of server-side rendering because now you can make anything and you're not limited to one platform or type of rendering.

This concludes the SvelteKit series but there's a lot more to learn about Svelte and SvelteKit. The future of web development is bright and I'm excited for things to come and hope to see you there.