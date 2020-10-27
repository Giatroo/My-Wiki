In CSS every element is like a box with many spaces around it.
There are the `margin`, then the `border`, then the `padding` and finaly the
element itself.

Each of these properties are used to space your elements appart, but the border
can be colorized and have some unique properties.

* You can select each side you want:

```css
margin-top: 5px;
margin-botton: 2px;
```
* You can use shortcuts:

```css
margin: top right bottom left;
margin: top&bottom right&left;
```

* `border` is the only of these that actually can be displayed:
```css
border: 4px;
border-style: solid;
border-color: rgb(255, 0, 0);
border-radius: 2px;

border: 4px dashed green;
```
