# CSS Notes

## Kevin Powell Tips & Tricks

- How to set the number of lines visible in a paragraph (e.g. in a display card)
```css
.card_preview-text {
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;
}
