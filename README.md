# Progressive Web App Code Lab

These are the resource files needed for the [Progressive Web App](https://codelabs.developers.google.com/codelabs/your-first-pwapp/)
code lab from Google.

This is a work in progress, if you find a mistake, please [file an issue](https://github.com/googlecodelabs/your-first-pwapp/issues). Thanks!

## Edge Cases not accounted for:

### Cache depends on updating the cache key for every change
For example this caching method requires you to update the cache key every time content is changed, otherwise, the cache will not be updated, and the old content will be served. So be sure to change the cache key with every change as you're working on your project!

### Requires everything to be redownloaded for every change
Another downside is that the entire cache is invalidated and needs to be re-downloaded every time a file changes. That means fixing a simple single character spelling mistake will invalidate the cache and require everything to be downloaded again. Not exactly efficient.

### Browser cache may prevent the service worker cache from updating
There's another important caveat here. It's crucial that the HTTPS request made during the install handler goes directly to the network and doesn't return a response from the browser's cache. Otherwise the browser may return the old, cached version, resulting in the service worker cache never actually updating!

### Beware of cache-first strategies in production
Our app uses a cache-first strategy, which results in a copy of any cached content being returned without consulting the network. While a cache-first strategy is easy to implement, it can cause challenges in the future. Once the copy of the host page and service worker registration is cached, it can be extremely difficult to change the configuration of the service worker (since the configuration depends on where it was defined), and you could find yourself deploying sites that are extremely difficult to update!



## What you’ll learn
* How to design and construct an app using the “app shell” method
* How to make your app work offline
* How to store data for use offline later

## What you’ll need
* Chrome 52 or above, though any browser that supports service workers and `cache.addAll()` will work
* [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb), or use your own web server of choice.
* The [sample code](https://github.com/googlecodelabs/your-first-pwapp/archive/master.zip)
* A text editor
* Basic knowledge of HTML, CSS and JavaScript
* (Optional) Node is required in the last step to deploy to Firebase
