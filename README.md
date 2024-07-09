This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

Basically this is just a walk through of the official documentation of Next.js 14.

## Routing

Next.js 14 uses **App Router**. By default, components insadie `app` are **React Server Components**.

Now, let's first understand these two kinds of components.

### Server Components

React Server Components allow you to write UI that can be rendered and optionally cached on the server.

There are lots of benificials. Checkout the website : https://nextjs.org/docs/app/building-your-application/rendering/server-components

#### How are Server Components rendered?

On the server, Next.js uses React's APIs to orchestrate rendering.

- React renders Server Components into a special data format called the React Server Component Payload (RSC Payload).
- Next.js uses the RSC Payload and Client Component JavaScript instructions to render HTML on the server. Next.js uses the RSC Payload and Client Component JavaScript instructions to render HTML on the server.

On the client,

- The HTML is used to immediately show a fast non-interactive preview of the route - this is for the initial page load only.
- The React Server Components Payload is used to reconcile the Client and Server Component trees, and update the DOM.
- The JavaScript instructions are used to hydrate Client Components and make the application interactive.

#### Server Rendering Strategies

- Static Rendering(Default)
- Dynamic Rendering
- Switching to Dynamic Rendering

### Client Components

Client Components allow you to write interactive UI that is prerendered on the server and can use client JavaScript to run in the browser.

- Interactivity: Client Components can use state, effects, and event listeners, meaning they can provide immediate feedback to the user and update the UI.
- Browser APIs: Client Components have access to browser APIs, like geolocation or localStorage.

#### How are Client Components rendered?

In Next.js, Client Components are rendered differently depending on whether the request is part of a full page load (an initial visit to your application or a page reload triggered by a browser refresh) or a subsequent navigation.

- Full page load :
  - React renders Server Components into a special data format called the React Server Component Payload (RSC Payload), which includes references to Client Components.
  - Next.js uses the RSC Payload and Client Component JavaScript instructions to render HTML for the route on the server.
  - The HTML is used to immediately show a fast non-interactive initial preview of the route.
  - The React Server Components Payload is used to reconcile the Client and Server Component trees, and update the DOM.
  - The JavaScript instructions are used to hydrate Client Components and make their UI interactive.
