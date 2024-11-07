# Forms and Tables

## Tables

Bootstrap can quickly turn your tables into very nice and even responsive ones! By default, though, Bootstrap doesn’t do much. 

Take a look at the following example:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Bootstrap Table Example</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta/css/bootstrap.min.css"
        integrity="sha384-/Y6pD6FV/Vv2HJnA6t+vslU6fwYXjCFtcEpHbNJ0lyAFsXTsjBbfaDjzALeQsN6M" crossorigin="anonymous">
</head>

<body>
    <div class="container">
        <h1>Animal Info</h1>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Animal Type</th>
                    <th>Age</th>
                    <th>Favorite Food</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Whiskey</td>
                    <td>Dog</td>
                    <td>4</td>
                    <td>Popcorn</td>
                </tr>
                <tr>
                    <td>Moxie</td>
                    <td>Cat</td>
                    <td>3</td>
                    <td>Fish</td>
                </tr>
                <tr>
                    <td>Boshi</td>
                    <td>Cat</td>
                    <td>9</td>
                    <td>Chicken</td>
                </tr>
                <tr>
                    <td>Bojack</td>
                    <td>50</td>
                    <td>Horse</td>
                    <td>Muffins</td>
                </tr>
            </tbody>
        </table>
    </div>
</body>

</html>
```

Let’s explore the classes that Bootstrap provides to help us style tables. Make the following changes to the code above and see what happens:

1. Give the `table` a class of `table`.
2. Add a second class to the `table`, called `table-inverse`. In other worse, your class attribute should have a value of "`table table-inverse`".
3. Remove the `table-inverse` class from the table, and add a class of `thead-inverse` to the `thead`.
4. Add a class of `table-striped` to the `table`. Now you should see alternating rows colored differently!
5. Add a class of `table-bordered` to the `table` to add borders around each table cell.
6. Add a class of `table-hover` to the `table` to add styles to the rows when you hover on them.
7. Add a class of `table-sm` to the `table`.
8. You can style table rows based on the color palettes we’ve seen for alerts and buttons! Try adding some contextual classes to your `trs`: for example, `table-primary`, `table-secondary`, `table-success`, and so on.

## Forms

Bootstrap also gives you a whole suite of classes for building forms, both horizontally and with a block layout. Here’s a basic example of a form styled with Bootstrap:

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
        <div class="container">
            <h1>Add an Animal!</h1>
            <form>
                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" class="form-control" id="name" placeholder="What's the name of the animal?">
                </div>
                <div class="form-group">
                    <label for="type">Animal Type</label>
                    <select class="form-control" id="type">
                        <option>Cat</option>
                        <option>Dog</option>
                        <option>Horse</option>
                        <option>Lemur</option>
                        <option>Other</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="age">Age</label>
                    <input type="number" class="form-control" id="age" placeholder="What's the age of the animal?" min="0"
                        max="100" step="1" value="0">
                </div>
                <div class="form-group">
                    <label for="fav-food">Favorite Food</label>
                    <input type="text" class="form-control" id="fav-food"
                        placeholder="What's the favorite food of the animal?">
                </div>
                <button type="submit" class="btn btn-primary">Submit</button>
            </form>
        </div>
    </body>

    </html>
```

The most important thing to remember when building forms with Bootstrap is to use the `form-group` for each part of the form. The elements used to collect information from the user (`input`, `select`, and so on) are also typically given a class of `form-control`.

You can also align form groups horizontally by giving the groups a class of `row`, and giving elements inside of the group `column` classes. For labels, you should also add the `col-form-label` class to ensure that the label is vertically aligned properly.

Here’s the same form as above, styled horizontally:

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
        <div class="container">
            <h1>Add an Animal!</h1>
            <form>
                <div class="form-group row">
                    <label for="name" class="col-3 col-form-label">Name</label>
                    <input type="text" class="form-control col-9" id="name" placeholder="What's the name of the animal?">
                </div>
                <div class="form-group row">
                    <label for="type" class="col-3 col-form-label">Animal Type</label>
                    <select class="form-control col-9" id="type">
                        <option>Cat</option>
                        <option>Dog</option>
                        <option>Horse</option>
                        <option>Lemur</option>
                        <option>Other</option>
                    </select>
                </div>
                <div class="form-group row">
                    <label for="age" class="col-3 col-form-label">Age</label>
                    <input type="number" class="form-control col-9" id="age" placeholder="What's the age of the animal?"
                        min="0" max="100" step="1" value="0">
                </div>
                <div class="form-group row">
                    <label for="fav-food" class="col-3 col-form-label">Favorite Food</label>
                    <input type="text" class="form-control col-9" id="fav-food"
                        placeholder="What's the favorite food of the animal?">
                </div>
                <button type="submit" class="btn btn-primary">Submit</button>
            </form>
        </div>
    </body>

    </html>
```

