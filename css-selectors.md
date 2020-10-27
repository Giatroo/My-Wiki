# Selectors

Selectors are the thing we put before { in CSS. They are the way we say to CSS
what elements we want to style.

## Basics

The simpler selector we have are selecting by the HTML tags.

We have just use a single tag like:
```css
p {
    color: blue;
}

span {
    background-color: orange;
}
```

Or we can use
```css
div p {
    color: blue;
}
```

To specify we want to style paragraphs that are __inside__ divs.

One more thing we can use is comma to apply the same style to more than one
selector:

```css
div p,
header {
    color: blue;
}
```

## Classes and ids

One more really common thing is to use classes and ids as selectors.

To select an id, we use a hash in front of the id's name. And to select an
class, we use a doc in front of its name:

```css
.my-class {
    ...
}

#my-id {
    ...
}
```

## Child selectors

If we have the same class in different objects (like divs and sections) we can
specify what we want to apply the style just to the class whenever it's a class
of a div:

```css
div.my-class {
    ...
}
```

## Pseudo-classes

Pseudo classes are used to apply styles whenever an event occurs. If we want to
apply an style to a `p` tag just when the mouse cursor is over it, we can write:

```css
p:hover {
    color: blue;
}
```

Where are many, many pseudo-classes for each kind of element.

We can also make a little transitions between the styles of each state:

```css
p {
    color: red;
    transition: 200ms;
}
```

Now it will take 200 miliseconds to transition between the colors red and blue.

### Advanced pseudo classes

Pseudo classes indeed are so powerful that they alow us to select very specify
elements from our HTML. Supouse you get a list and want to apply a style to the
first element. You can do:

```css
li:first {
    text-weight: bold;
}
```

You can also do that using a function:

```css
li:nth-child(1) {
    ...
}
```

If you use:

```css
li:nth-child(2n) {
    color: blue;
}
```

it will make the second list item to be blue, then the forth, then the sixth...

## Pseudo-elements

One more advanced topic is pseudo-elements. Supouse you want to apply a style
just to the first line of a paragraph, or the first letter of a title. You can
do that using pseudo-elements:

```css
p::first-line {
}

h1::first-letter {
}
```

We can also add content before and after elements:
```css
li::before {
    content: "#"
}
p::after {
    content: '.'
}
```
