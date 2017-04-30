# Github inspired markdown styles

Created for [marked](https://github.com/chjj/marked), but will probably look equally good with others as well.

for rendered markdown, put `.markdown-view` on container element

for editing, put `.markdown-input` on container element

Also, [adam-p](https://github.com/adam-p) has a pretty amazing markdown syntax reference [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#code)

Using marked and want those wonderful checkboxes? use this wrapper function

```javascript
markdownFormatter(text) {
  if (text) {
    var a = marked(text, {break: true});
    a = a.replace(/<a/g, '<a target="_blank"') // Open links in new tab
         .replace(/<li>\[\s\]/g, '<li class="check-box"><input onclick="return false" type="checkbox">')
         .replace(/<li>\[x\]/g, '<li class="check-box"><input checked onclick="return false" type="checkbox">');
    return a;
  } else  {
    return text;
  }
}
```
Minified
```javascript
function markdownFormatter(e){if(e){var c=marked(e,{"break":!0});return c=c.replace(/<a/g,'<a target="_blank"').replace(/<li>\[\s\]/g,'<li class="check-box"><input onclick="return false" type="checkbox">').replace(/<li>\[x\]/g,'<li class="check-box"><input checked onclick="return false" type="checkbox">')}return e}
```
