stack
=====

Show a stack of tools that are used to build your project. 

Built to be used in Jekyll.

Install
-------

`$ bower install timble/stack`

Use
---

- Copy `stack.json` to `_data` folder in your Jekyll installation
- Remove items that you are not using fomr stack.json file
- Use something like grunt-contrib-copy to copy the following:
    - all logos to `images/stack` folder
    - `scss/_stack.scss` to your SCSS folder
    - `template/stack.html` to `_includes`