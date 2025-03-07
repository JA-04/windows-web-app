# Middleware

Middleware are functions that run before or after particular actions, normally to perform an authentication action, or to add extra information. For a full explanation of middleware, we recommend reading the express documentation on [middleware](https://expressjs.com/en/guide/using-middleware.html).

Keystone includes some middleware automatically, to handle login and auth.

All of keystone' middleware aside from the `pre:render` middleware are intended to run only within keystone-specific routes, and are added to the express router after your own routes have been registered.

In keystone, there are a number of middleware that can be added globally, which will then be called at defined times during routing. These can be passed into the [set](/api/methods/set) method. These are:

name | call time
---|---
`pre:static` |
`pre:logger` |
`pre:bodyparser` |
`pre:session` |
`pre:admin` |	Installs Express middleware which is called before a Keystone admin UI route is executed. (i.e. routes starting with `/keystone`)
`pre:adminroutes` | Installs Express middleware which is called before the route handlers in the admin UI are executed (i.e. after the admin UI-specific middleware is configured but before routes are matched)
`pre:routes` | Installs Express middleware which is called before each developer defined route is executed. (i.e. the routes you define besides the `/keystone` generated ones)
`pre:render` | Called before a Keystone [view](/api/view) is rendered.
`updates` |
`signin` | Called before a user signs in to the Keystone admin UI and the user is returned a view.
`signout` | Called before a user signs out of the admin UI and the user is returned a view.
