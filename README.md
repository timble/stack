stack
=====

Show a stack of tools that are used to build your project. 

Built to be used in Jekyll.

Install
-------

Add the following dependency to your bower.json file:

```"stack": "timble/stack"```

Run `bower install`

Use
---

- Copy `stack.json` to `_data` folder in your Jekyll installation
- Remove items that you are not using from stack.json file
- Use something like grunt-contrib-copy to copy the following:
    - all logos to `images/stack` folder
    - `scss/_stack.scss` to your SCSS folder
    - `template/stack.html` to `_includes`
- Include the include file: `{% include stack.html %}`
- Optionally add a button class: `{% include stack.html class="alternative--button" %}`