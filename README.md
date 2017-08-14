# SVG implementation examples

This repo contains sample HTML and CSS for implementing SVGs.

## `img` tag

Just as you would with any other image.

```html
<img src="freesample.svg" width="354" height="294">
```

## CSS `background-image`

It's best not to base64 encode them as it this will block the loading of the rest of the styles while it downloads.

```html
<span id="sample"></span>
```

```css
#sample {
    background-image: url(freesample.svg);
    background-size: contain;
    width: 354px;
    height: 294px;
    display: inline-block;
}
```

## `svg` tag

This can be used to embed an SVG fragment inside the current document. It has its own viewport and coordinate system.

```html
<svg class="sample" aria-hidden="true"><use href="symbols.svg#sample"></use></svg>
```

```svg
<svg xmlns="http://www.w3.org/2000/svg">
    <symbol id="sample" viewBox="0 0 472 392">
        <path...
    </symbol>
</svg>
```

```css
svg.sample {
    width: 354px;
    height: 294px;
    display: inline-block;
}
```