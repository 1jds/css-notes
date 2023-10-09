# CSS Notes

## Kevin Powell Tips & Tricks

- ### How to set the number of lines visible in a paragraph (e.g. in a display card)
```css
.card__preview-text {
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;
  overflow: hidden;
}
```

This is the accompanying HTML from Kevin Powell's Codepen [HERE](https://codepen.io/kevinpowell/pen/JjeOvRZ?editors=1100)

```html
<div class="card">
        <img src="https://images.unsplash.com/photo-1665243066869-1f27e948de5f?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2NjYxMTQ0Nzc&ixlib=rb-1.2.1&q=80&w=700" alt="">
        <h2 class="card__title">A quick example</h2>
        <p class="card__preview-text">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Impedit officiis tempore dicta, sed illo sint nobis non odit soluta sit. amet consectetur adipisicing elit. Qui, doloribus.</p>
        <button>Continue reading</button>
      </div>
```

## Some Online Tools

### For Clip Paths
- See [THIS](https://unused-css.com/tools/clip-path-generator) website for producing clip-paths.
  
### For `clamp()`
- See [THIS](https://css-tricks.com/linearly-scale-font-size-with-css-clamp-based-on-the-viewport/) tool (scroll down to the end) for coming up with `clamp()` values more easily.
- Clamp is great for making text more responsive without having to use multiple media queries


## Things I've Found Out Through Building Things

### Use `:only-child` after `:first-child` and `:last-child` for dynamic content when there's only one element present
- If you don't do this, then the regular cascade will take over and the last declared rule will win out. For example:

```css
.specificBookComment:first-child {
  border-radius: 0.5rem 0.5rem 0 0;
}

.specificBookComment:last-child {
  border-radius: 0 0 0.5rem 0.5rem;
}
```

```css
.specificBookComment:last-child {
  border-radius: 0 0 0.5rem 0.5rem;
}

.specificBookComment:first-child {
  border-radius: 0.5rem 0.5rem 0 0;
}
```

```css
.specificBookComment:first-child {
  border-radius: 0.5rem 0.5rem 0 0;
}

.specificBookComment:last-child {
  border-radius: 0 0 0.5rem 0.5rem;
}

.specificBookComment:only-child {
  border-radius: 0.5rem;
}
```
