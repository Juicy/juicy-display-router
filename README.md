pj-display-router
=================

A Polymer Element to switch visible elements based on current window location

### Usage

```html

<pj-display-router>
  <pj-display-route match-url="/" display-selector="body pj-dashboard #container"></pj-display-route>
  <pj-display-route match-url="/\/launcher\/workspace\/([^\/]*)\//" display-selector="body pj-dashboard #workspaces .%1"></pj-display-route>
</pj-display-router>
```

### How it works

- For each **pj-display-route** in **pj-display-router**, the window location is checked against the regular expression provided in the `match-url` attribute. 
- If there is a match, the query in `display-selector` is performed against DOM and the first found element is set with `display: block`. 
- For every other route, the query in `display-selector` is performed against DOM and the first found element is set with `display: none`. 
