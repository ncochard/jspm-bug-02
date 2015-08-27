I created this to illustrate what I think is a bug in the CSS bundle in JSPM.

To recreate this bug, follow these instructions.

    git clone https://github.com/ncochard/jspm-bug-02.git
    cd jspm-bug-02
    jspm bundle lib/index dist/bundle.js
    npm install serve -g
    serve

The bundle was generated in the "dist" folder. If you look at the end to the bundle.css, you will find that the reference to the bundle.css.map is incorrect.

Actual:   `/*# sourceMappingURL=dist/bundle.css.map*/`

Expected: `/*# sourceMappingURL=bundle.css.map*/`

This problem is illustrated if you right-click on an element in the browser and click on "Inspect Element".
