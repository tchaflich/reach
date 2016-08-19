# reach

JSONP made simple.

`reach.js` exists solely to send JSONP requests without the use of any other libraries or plugins.

### What is JSONP? Is it JSON?

JSONP stands for "JSON with Padding", and is a hack to get around cross-origin restrictions. Basically, you dynamically load a script from a completely separate website. You send variables using GET, so all variables are "stringified" via JSON.

### What are cross-origin restrictions? Why would I want to avoid them?

A client browser cannot send XMLHttpRequests to a server on a different origin (usually domain). This is a safety feature at heart, and prevents scripts from different websites from sending data back-and-forth easily from the client.

What you *can* do is load an entire script voluntarily from another site in a <script> tag (similar to direct-linking an image or loading a font directly from a hosting service's website). The server takes your GET parameters tacked onto the URL, uses them to load whatever data it needs from its servers, dynamically creates a javascript file (that calls your callback at the end), and echoes it back to the browser.

### Why can't the servers just talk to each other?

Sometimes you want to make sure data doesn't ever touch your server - for example, sensitive credit card data that you want to keep off to ensure PCI compliance.

### Why might I want to *not* use JSONP?

You must, by the nature of cross-domain requests, trust the site you are sending the request to. You are handing them information and allowing them to run a script on your client.

### How does this code help?

The `reach` class is a wrapper to automatically construct the <script> element and attach it to the document with a minimum of fuss. It easily handles multiple requests, automatic callback aliasing, and encoding the component arguments.

```todo example```








