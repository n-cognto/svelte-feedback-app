# Svelte Feedback App

A simple feedback collection application built with Svelte. Users can submit feedback with ratings and view/delete existing feedback items.

## Features

- **Add Feedback**: Submit new feedback with a rating (1-10) and text review
- **View Feedback**: Display all feedback items in a clean card layout
- **Delete Feedback**: Remove individual feedback items with a delete button
- **Responsive Design**: Clean, modern UI with a dark theme

## Project Structure

```
src/
├── App.svelte          # Main app component with feedback form and list
├── main.js             # Entry point that mounts the Svelte app
└── components/
    ├── Card.svelte     # Reusable card component for styling
    ├── FeedbackItem.svelte  # Individual feedback item display
    └── FeedbackList.svelte  # Container for all feedback items
```

## How It Works

### Components Overview

- **App.svelte**: Manages the feedback state and renders the form and feedback list
- **FeedbackList.svelte**: Iterates through feedback items and renders each one
- **FeedbackItem.svelte**: Displays individual feedback with rating badge and delete button
- **Card.svelte**: Provides consistent styling for content containers

### Key Concepts Demonstrated

- **Reactive Data**: Using Svelte's reactive statements to update the UI when data changes
- **Component Communication**: Passing data via props and emitting custom events
- **Event Handling**: Responding to user interactions like form submission and button clicks
- **Two-way Binding**: Using `bind:value` for form inputs
- **Slots**: Flexible content insertion in the Card component

## Getting Started

This is a project template for [Svelte](https://svelte.dev) apps. It lives at https://github.com/sveltejs/template.

To create a new project based on this template using [degit](https://github.com/Rich-Harris/degit):

```bash
npx degit sveltejs/template svelte-app
cd svelte-app
```

*Note that you will need to have [Node.js](https://nodejs.org) installed.*


## Get started

Install the dependencies...

```bash
cd svelte-app
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:8080](http://localhost:8080). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.

If you're using [Visual Studio Code](https://code.visualstudio.com/) we recommend installing the official extension [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). If you are using other editors you may need to install a plugin in order to get syntax highlighting and intellisense.

## Building and running in production mode

To create an optimised version of the app:

```bash
npm run build
```

You can run the newly built app with `npm run start`. This uses [sirv](https://github.com/lukeed/sirv), which is included in your package.json's `dependencies` so that the app will work when you deploy to platforms like [Heroku](https://heroku.com).


## Single-page app mode

By default, sirv will only respond to requests that match files in `public`. This is to maximise compatibility with static fileservers, allowing you to deploy your app anywhere.

If you're building a single-page app (SPA) with multiple routes, sirv needs to be able to respond to requests for *any* path. You can make it so by editing the `"start"` command in package.json:

```js
"start": "sirv public --single"
```

## Using TypeScript

This template comes with a script to set up a TypeScript development environment, you can run it immediately after cloning the template with:

```bash
node scripts/setupTypeScript.js
```

Or remove the script via:

```bash
rm scripts/setupTypeScript.js
```

If you want to use `baseUrl` or `path` aliases within your `tsconfig`, you need to set up `@rollup/plugin-alias` to tell Rollup to resolve the aliases. For more info, see [this StackOverflow question](https://stackoverflow.com/questions/63427935/setup-tsconfig-path-in-svelte).

## Deploying to the web

### With [Vercel](https://vercel.com)

Install `vercel` if you haven't already:

```bash
npm install -g vercel
```

Then, from within your project folder:

```bash
cd public
vercel deploy --name my-project
```

### With [surge](https://surge.sh/)

Install `surge` if you haven't already:

```bash
npm install -g surge
```

Then, from within your project folder:

```bash
npm run build
surge public my-project.surge.sh
```
