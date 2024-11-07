# Introduction to Bootstrap

## Twitter Bootstrap

Twitter Bootstrap is a CSS framework built and maintained for free by Twitter. What does this mean? Put another way, it’s a collection of style rules and additional tools to help build responsive layouts faster. There are plenty of CSS frameworks out there, but Bootstrap is one of the most popular ones. However, many frameworks have very similar offerings, so once you are comfortable with one it is not very difficult to pick up another.

Twitter Bootstrap offers a responsive grid, many default styles for buttons, typography, tables, forms, and much more. It also has a small JavaScript library for interactive components like dropdowns, carousels and more.

## Including Twitter Bootstrap

You can include Bootstrap quite a few ways: you can download the code, use a CDN, or use a package manager (e.g. npm/bower) to install it. For now, we will be using the CDN as it is the easiest way to get started. If you head to http://getbootstrap.com/docs/4.0/getting-started/download/#bootstrap-cdn, you can copy and paste the CDN `link` tag into your HTML file and you will have Bootstrap right away! (For now, you don’t need to worry about the `script` tag with the JavaScript file; if you want to include it in your HTML, feel free, but for now we’ll focus on the CSS.) This is really no different than the way we linked our own CSS files in previous units. The difference now is that the CSS is hosted somewhere other than on our computer.

You’ve probably noticed that the `link` tag you copy from the Bootstrap site has some attributes we haven’t seen before: `integrity` and `crossorigin`. These attributes provide a layer of security when requesting files from a CDN, through a feature called Subresource Integrity.

As an aside, wondering what a CDN is? **CDN stands for Content Delivery Network**, and it’s essentially a network of servers that are used to deliver content to users around the globe. Having a network of servers makes that delivery faster, because you can deliver content from whichever server is geographically closest to the user. It also provides a safeguard in case one of the servers goes down.

