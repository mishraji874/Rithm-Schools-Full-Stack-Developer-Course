# Typography and Buttons

## Typography

To help with responsive design, Bootstrap version 4 uses rem units for all typography. On the `body` tag, Bootstrap sets the `font-size` to 1rem, with a `line-height` of 1.5. You can also use classes like `lead` or `text-muted` simple, standardized styling of text that you may want to emphasize in different ways. There are also a number of `inline` text elements for additional modification.

## Buttons

Buttons are one of the most common elements you’ll be using with Bootstrap. You can use Bootstrap’s buttons to help build forms, style links, and, of course, create nice looking `button` elements.

Bootstrap has quite a few default colors and sizes for buttons. 

Check out this quick example:

```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Bootstrap Button Example</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta/css/bootstrap.min.css" integrity="sha384-/Y6pD6FV/Vv2HJnA6t+vslU6fwYXjCFtcEpHbNJ0lyAFsXTsjBbfaDjzALeQsN6M" crossorigin="anonymous">
    </head>
    <body>
        <div class="container">
            <section class="mb-5">
            <h1>Here are some buttons:</h1>
            <hr>
            <button>Button</button>
            <button class="btn">Default button</button>
            <button class="btn btn-primary">Primary button</button>
            <button class="btn btn-secondary">Secondary button</button>
            <button class="btn btn-success">Success button</button>
            <button class="btn btn-danger">Danger button</button>
            <button class="btn btn-warning">Warning button</button>
            <button class="btn btn-info">Info button</button>
            <button class="btn btn-light">Light button</button>
            <button class="btn btn-dark">Dark button</button>
            <button class="btn btn-link">Link button</button>
            </section>
            <section class="mb-5">
            <h1>Here are some more buttons:</h1>
            <hr>
            <button class="btn btn-outline-primary">Primary button</button>
            <button class="btn btn-outline-secondary">Secondary button</button>
            <button class="btn btn-outline-success">Success button</button>
            <button class="btn btn-outline-danger">Danger button</button>
            <button class="btn btn-outline-warning">Warning button</button>
            <button class="btn btn-outline-info">Info button</button>
            <button class="btn btn-outline-light">Light button</button>
            <button class="btn btn-outline-dark">Dark button</button>
            </section>
            <section class="mb-5">
            <h1>Here are some other elements styled as buttons:</h1>
            <hr>
            <input type="button" class="btn btn-primary" value="Primary Button">
            <a href="#" role="button" class="btn btn-success">Success button!</a>
            <input type="button" class="btn btn-warning" value="Warning Button">
            <a href="#" role="button" class="btn btn-danger">Danger button!</a>
            </section>
            <section class="mb-5">
            <h1>Here are some buttons at different sizes:</h1>
            <hr>
            <button class="btn btn-primary btn-lg">Large button</button>
            <button class="btn btn-primary btn-sm">Small button</button>
            </section>
            <section class="mb-5">
            <h1>Here's a block-level button</h1>
            <hr>
            <button class="btn btn-primary btn-block">Block-level button</button>
            </section>
        </div>
    </body>
    </html>
```

As you can see, there are quite a few different classes you can give to your buttons. The base styles come from the `btn` class, but you won’t really use this class in isolation: instead, you’ll typically combine it with one of the other classes, such as `btn-primary` or `btn-success`. This is very similar to the pattern we’ve seen with alerts.

Buttons also come with a family of outline classes, which can be helpful if you want to use color more sparingly in your design.

Also, note that you can add button classes to a few different elements, including `button`, `input`, and `a` tags. Adding button classes to a tags is really helpful if you want to make a link look like a button. Aside from this case, however, the Bootstrap documentation recommends that wherever possible, you should try to use the `button` element when using button styles (because of cross-browser compatibility issues).

Also, note that by default buttons are `inline-block` elements. If you want a block-level button, give it a class of `btn-block`. You can also change the default size of the button by using `btn-lg` or `btn-sm` classes. Note that Bootstrap 3 also had a `btn-xs` class, but this has been removed in version 4.