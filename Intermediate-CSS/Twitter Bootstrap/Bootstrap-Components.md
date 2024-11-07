# Bootstrap Components

## Icons and Other Components

Bootstrap provides support for styling a number of common components you’ll typically find on a page. We’ve already seen a number of these components, including alerts, buttons, and forms. But as you may have noticed if you’ve spent some time with the docs, Bootstrap has support for over twenty differennt components. While some of these components only involve CSS, others also require you to load some JavaScript files. In this section, we’ll take a look at some of the more advanced components, and we’ll also talk about icons.

## Icons

Before taking a look at some other Bootstrap components, let’s briefly talk about icons. Prior to version 4 of Bootstrap, the library came with a built in icon library callled **glyphicons**. However, this icon library has been removed in version 4, and instead you’re encouraged to use an external library for icons if you need it. The Bootstrap docs have a list of icon libraries that they recommend, including `Iconic`. One very popular library that they don’t mention is `Font Awesome`.

Regardless of the icon library you choose, the process of adding an icon to the page is very similar. Here’s an example that displays icons from both Iconic and Font Awesome:

```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta charset="UTF-8">
        <title>Bootstrap Form Example</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta/css/bootstrap.min.css"
            integrity="sha384-/Y6pD6FV/Vv2HJnA6t+vslU6fwYXjCFtcEpHbNJ0lyAFsXTsjBbfaDjzALeQsN6M" crossorigin="anonymous">
        <link href="https://cdnjs.cloudflare.com/ajax/libs/open-iconic/1.1.1/font/css/open-iconic-bootstrap.css"
            rel="stylesheet">
        <link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet"
            integrity="sha384-wvfXpqpZZVQGK6TAh5PVlGOfQNHSoD2xbE+QkPxCAFlNEevoEH3Sl0sibVcOQVnN" crossorigin="anonymous">
    </head>

    <body>
        <div class="container">
            <p>Here are some Iconic icons:</p>
            <ul>
                <li><span class="oi oi-thumb-up"></span></li>
                <li><span class="oi oi-person"></span></li>
                <li><span class="oi oi-lock-locked"></span></li>
            </ul>
            <p>Here are some Font Awesome icons:</p>
            <ul>
                <li><i class="fa fa-thumbs-up"></i></li>
                <li><i class="fa fa-user"></i></li>
                <li><i class="fa fa-lock"></i></li>
            </ul>
        </div>
    </body>

    </html>
```

Note that for both of these libraries, icons are displayed by adding classes to certain inline elements. For Iconic icons, every icon should have the oi class, plus an additional class for the specific icon, such as `oi-thumb-up` or `oi-person`. The pattern for Font Awesome is similar; the biggest difference is that the class prefixes are `fa` (for Font Awesome) instead of `oi`.

## Navbar

Bootstrap makes it very easy to add styled navigation to a website with its navbar component. You can see how it looks here (we’ve toned down the example from the docs a bit to make it easier to digest):

```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta charset="UTF-8">
        <title>Bootstrap Form Example</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta/css/bootstrap.min.css"
            integrity="sha384-/Y6pD6FV/Vv2HJnA6t+vslU6fwYXjCFtcEpHbNJ0lyAFsXTsjBbfaDjzALeQsN6M" crossorigin="anonymous">
    </head>

    <body>
        <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
            <a class="navbar-brand" href="#">My App</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsed-content">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="collapsed-content">
                <ul class="navbar-nav ml-auto">
                    <li class="nav-item active">
                        <a class="nav-link" href="#">About</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Contact</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Team</a>
                    </li>
                </ul>
                <form class="form-inline">
                    <input class="form-control mr-sm-2" type="text" placeholder="Username">
                    <input class="form-control mr-sm-2" type="text" placeholder="Password">
                    <button class="btn btn-outline-light" type="submit">Log In</button>
                </form>
            </div>
        </nav>
    </body>

    </html>
```

Some of these classes should look familiar. And even among the new ones, some common patterns exist. For example, even though the nav element has a lot of classes attached to it, the color options you have for nav bars are the same as the ones we’ve seen for things like alerts and buttons.

As this example shows, you can also add inline forms to your nav bars.

This navbar is responsive, but also broken. Notice that if you narrow the width of the screen, eventually everything inside of the div with a class of `navbar-collapse` disappears, and is replaced with a button on the right side of the nav. But if you click on the button, nothing happens! Here’s our first example that requires more than CSS: in order to use the responsive nav bar that Bootstrap provides, we need to include some JavaScript as well.

## Bootstrap JS

While Bootstrap is a CSS Framework, it comes with some handy JavaScript to add dynamic interactivity to your page. Fortunately, to get started with this you do not need to know any JavaScript (unless you would like to customize some of these things). However, you must know that bootstrap.js depends on two other libraries: jQuery and Popper.js. Therefore, we need to include both of these dependencies before loading the Bootstrap JavaScript file. Here’s what that looks like:

```javascript
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.11.0/umd/popper.min.js" integrity="sha384-b/U6ypiBEHpOf/4+1nzFpr53nxSS+GLCkfwBdFNTxtclqqenISfwAzpKaMNFNmj4" crossorigin="anonymous"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta/js/bootstrap.min.js" integrity="sha384-h0AbiXch4ZDo7tp9hKZ4TsHbi047NrKGLO3SEJAg45jXxnGIfYzk4Si90RDIqNm1" crossorigin="anonymous"></script>
```

If you add these script tags at the bottom of our nav bar example (right before the closing body tag), you should see that the button in the navbar works! On small screens, the navigation collapses, but you can expand it by clicking on the button.

## Other Components

Once you’ve included the JavaScript files that Bootstrap needs, there a number of other components you can use. These include `carousels`, `modals`, `popovers`, and `tooltips`. Try to get the code examples from the Bootstrap docs working in your own HTML files!

## Bootswatch

One of the downsides of using Bootstrap is that it’s very easy to identify sites that are styled with Bootstrap. Fortunately, Bootswatch is a wonderful open source set of themes for Bootstrap to add some more customization and flavor so that your page doesn’t look like every other Bootstrap page. You can think of Bootswatch themes as different skins for Bootstrap; the code you write will be the same regardless of the theme, but the end result on the page will look different. There are Bootswatch themes available for version 4 and version 3 of Bootstrap.