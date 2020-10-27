* We can add background images to our project with:

```css
body {
    background-image: url('/background.jpg');
    background-size: 250px 160px;
    /* by default, if the image is smaller then the window, it'll repeat */
    background-repeat: no-repeat;

    /* we can also use cover: */
    background-size: cover;
}
```

* We can color our background with

```css
selector {
    background-color: white;
}
```

This property can be used in pretty much any tag.

* Backgrounds have an position property.
It can be _center_, _right_, _left_, _left-center_...

* Backgrounds have an attachment property.
It can be set to _scroll_ or _fixed_.
If it's _fixed_, the image will not change when you scroll.
If it's _scroll_, the image will change when you scroll.

* The shortcut looks like:

```css
selector {
    background: color image position/size repeat attachment;
}
```
