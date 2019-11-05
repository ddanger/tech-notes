# Nuxt.js
Notes about Nuxt from [this Udemy course](https://www.udemy.com/course/nuxtjs-vuejs-on-steroids/) and [the docs](https://nuxtjs.org/guide/).

## Plugins
- Allows you to run code before your app is fully rendered/mounted
- bc you don't have access access to `main.js` like in a typical Vue app
- gives access to root Vue instance
- Uses:
  - any JS you want to run before the root Vue instance is mounted at app startup
  - add Vue filters `Vue.filter()`
  - globally import Vue components (a questionable practice)

### Creating a Plugin
- add a file for it in `/plugins`
- add it to the `plugins` section of `nuxt.config.js`

## Modules
- Extend your app with utility functions
- Easily add third party convenience features
- Many examples at [Awesome Nuxt](https://github.com/nuxt-community/awesome-nuxt#modules)

## Routing Middleware
- Functions that run before a route is loaded
- Similar in concept to middleware in Express (if you're familiar)

## Deployment / Generation
Three options:
- Universal
  - First view rendered dynamically on server, future views are SPA-like
- Single Page App
  - App starts after first load
- Static App (Prerendered)
  - Pre-built HTML/CSS loaded, there-after it's SPA-like
