stack
=====

Show a stack of tools that are used to build your project. 

Built to be used in [Jekyll](http://jekyllrb.com/) with [Grunt](http://gruntjs.com/) and [Bower](http://bower.io/).

Install
-------

Add the following dependency to your bower.json file:

```"stack": "timble/stack"```

Run `bower install`

Use
---

- Use [grunt-contrib-copy](https://github.com/gruntjs/grunt-contrib-copy) (or similar) to automatically copy the following files from bower_components:
    - all logos to `images/stack` folder
    - `scss/_stack.scss` to your SCSS folder and make sure to include it in your main SCSS file
    - `template/stack.html` to `_includes`
    - `stack.json` to `_data/vendor`
- Create a `stack.json` file in your `_data` folder and add the tools you want
- Include the include file: `{% include stack.html %}` in your page
- Optionally add a button class: `{% include stack.html class="alternative--button" %}`

Examples
========

stack.json example
------------------

```
[
    {
        "title": "Application & Data",
        "type": "card",
        "data": [
            {
                "title": "nooku"
            },
            {
                "title": "jquery"
            },
            {
                "title": "sass"
            }
        ]
    },
    {
        "title": "Dev Ops",
        "type": "card",
        "data": [
            {
                "title": "bower"
            },
            {
                "title": "vagrant"
            }
        ]
    },
    {
        "title": "Other",
        "type": "simple",
        "data": [
            {
                "title": "select2"
            }
        ]
    }
]
```

The type (card or simple) represents a card with or without a logo.

Grunt contrib copy example (place in your gruntfile)
----------------------------------------------------

```
copy: {
    main: {
        files: [
            {
                expand: true,
                src: ['bower_components/stack/logos/*.*'],
                dest: 'images/stack/logos',
                flatten: true
            },
            {
                expand: true,
                src: ['bower_components/stack/scss/*.*'],
                dest: '_scss/_utilities',
                flatten: true
            },
            {
                expand: true,
                src: ['bower_components/stack/template/*.*'],
                dest: '_includes',
                flatten: true
            },
            {
                expand: true,
                src: ['bower_components/stack/json/*.*'],
                dest: '_data/vendor',
                flatten: true
            }
        ]
    }
}
```