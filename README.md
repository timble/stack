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
    - `./logos/` to `images/stack/vendor/` folder
    - `stack.html` to `_includes/vendor/`
    - `stack.json` to `_data/vendor/`
- Create a `stack.json` file in your `_data` folder and add the tools you want
- Include the include file: `{% include vendor/stack.html %}` in your page
- Optionally add a button class: `{% include vendor/stack.html class="alternative--button" %}`
- Make sure to `@import` the `_stack.scss` file to your main SCSS styles file

Examples
========

stack.json example
------------------

```
[
    {
        "title": "Application & Data",
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
        "data": [
            {
                "title": "select2"
            }
        ]
    }
]
```

Add your own tools
------------------

The best way to add your own tools is to create a branch and submit a pull request. However if you have a small tool that probably won't be useful to add to this repo you can add your own by adding the following to your json file:

```
{
    "title": "My own tool",
    "description": "My own tool description",
    "url": "My own tool url"
}
```

Just make sure you add both the 'description' and 'url' and add a 100x100 pixels PNG image to your `images/stack` folder (don't place within vendor folder).

No image/icon available? Add `"logo": "none"` to the item in the JSON file.

Grunt contrib copy example (place in your gruntfile)
----------------------------------------------------

```
copy: {
    main: {
        files: [
            {
                expand: true,
                src: ['bower_components/stack/logos/*.*'],
                dest: 'images/stack/vendor',
                flatten: true
            },
            {
                expand: true,
                src: ['bower_components/stack/template/*.*'],
                dest: '_includes/vendor',
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