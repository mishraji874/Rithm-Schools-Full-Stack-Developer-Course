# Specifity

These weightings are not exact (10 element selectors does not equal a class selector), it is more an idea of showing you the magnitude of each kind of selector.


| Selector     |  Weighting  |
|:------------:|:-----------:|
| element      | 1           |
| class        |  10         |
| id           | 100         |
| inline-style | 1000        |
| !important   | 10000+      |

What this means is that a style rule on an `id` is weighed much more heavily than a style rule on a `class`. Similarly, a style rule on a `class` is weighed more heavily than a rule on an `element`. Put another way, `id` rules are more specific than `class` rules, and `class` rules are more specific than `element` rules.

This gives us another way to differentiate between `classes` and `ids`. Not only are `ids` meant to be `unique`, unlike `classes`, but also `ids` are more `specific`! This is also why the background color in our example is green: the id rule trumps the class rule, which in turn trumps the element rule. Cascading only applies when the rules have the same degree of `specificity`; in this case, rules about `specificity` determine the style, not rules about cascading.

We previously mentioned that using inline styling (a ```<style></style>``` tag) can have some unintended consequences. Strong `specificity` is one of them! Remember that inline styling is equal to 1000 points and is far more specific than any `id`, `class` or `element`! Even more, using `!important` will override ANY styling that you have (unless you have a more specific `!important`) so try your best to not use it. Not only does it make it more difficult to write future CSS, but it can get complicated quickly when working with other developers. If we catch you writing `!important` in your CSS, we’ll ask you to refactor immediately!