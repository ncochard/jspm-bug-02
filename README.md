I created this to illustrate what I think is a bug in the CSS bundle in JSPM.

Track this issue at [https://github.com/jspm/jspm-cli/issues/1065](https://github.com/jspm/jspm-cli/issues/1065).

To recreate this bug, follow these instructions.

    git clone https://github.com/ncochard/jspm-bug-02.git
    cd jspm-bug-02
    jspm bundle lib/index dist/bundle.js --inject
    npm install serve -g
    serve

The bundle was generated in the "dist" folder. If you look at the end to the bundle.css, you will find that the reference to the bundle.css.map is incorrect.

Actual:   `/*# sourceMappingURL=dist/bundle.css.map*/`

Expected: `/*# sourceMappingURL=bundle.css.map*/`

This problem is illustrated if you right-click on an element in Chrome and click on "Inspect Element". You can see that the browser indicates that the styles are defined in the file 'bundle.css' rather than 'bootstrap.css'.
