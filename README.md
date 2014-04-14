warpech-display-router
======================

A Polymer Element to switch visible elements based on current window location

### Usage

```html

<warpech-display-router>
  <warpech-display-route match-url="/" display-selector="body pj-dashboard #container"></warpech-display-route>
  <warpech-display-route match-url="/\/launcher\/workspace\/super-crm/" display-selector="body pj-dashboard #workspaces .SuperCRM"></warpech-display-route>
  <warpech-display-route match-url="/\/launcher\/workspace\/([^\/]*)\//" display-selector="body pj-dashboard #workspaces .%1"></warpech-display-route>
</warpech-display-router>
```

### How it works

- For each **warpech-display-route** in **warpech-display-router**, the window location is checked against the regular expression provided in the `match-url` attribute. 
- If there is a match, the query in `display-selector` is performed against DOM and the first found element is set with `display: block`. 
- For every other route, the query in `display-selector` is performed against DOM and the first found element is set with `display: none`. 

### Problems

For some apps, there is a 1:1 map between application's class name and the word used in the URL - e.g. `skyper`

For other apps, there is no patch - e.g. SuperCRM has a class name `SuperCRM` in the Launcher but is using `super-crm` in the URL.

The match wil be not made in that case, so a more explicit route needs to be provided.
