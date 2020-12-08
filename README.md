# buefy-sidebar-error

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).

HOW TO REPRODUCE ERROR:

1. Open the nuxt project, install the dependencies and run the server with

```bash
$ npm run dev
```

2. The sidebar appears opened, check clicking on other parts of the page that the menu still there and no disappear.

3. Click on the upper icon to close the sidebar, then an event call changeMenu is thrown and the open prop of the sidebar is changed to false so the sidebar is closed.

4. Click again on the upper icon to open the sidebar.

5. Click at any part of the screen and realize that the sidebar disappear because the event close and update:open is called by the sidebar, don't know the reason.

That's all :)
