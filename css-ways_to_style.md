# Ways to Style

There are three ways to style an attribute:

## Inline style

Pretty much whatever tag in HTML suports a attribute called _style_.

`<p style="">STYLE ME!</p>`

Inside that _style_ attribute we can embedde any css code to that especific
tag.

One thing to have um mind is that inline style has the highest _style weight_.
You can check [Style Weight](css-style_weights) to understand it better, but
basicly if you have a inline styled tag, that style _can't_ be replaced by
any other styling ways.

`<p style="color: blue">STYLE ME!</p>`

## Head style tag

We also can place a style tag in the head of the html:

```html
<head>
    ...
    <style type="text/css">
        p {
            color : blue;
            background: grey;
        }
    </style>
    ...
</head>
```

## External file (stylesheet)

As css is a very important part of our project, the style tag may be very,
very big. Therefore, it's good to have a external way to apply a style to a html
file.

To do so, we use stylesheets. We create a new file `filename.css` and link it in
the head of our html:

`<link rel="stylesheet" type="text/css" href="filename.css">`

A good practice is to have a `css` folder inside our project.

That's also good when we need to have the same style in many different pages.
