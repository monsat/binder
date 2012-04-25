binder
======

simple template for JavaScript.

## USAGE
### h
```javascript
// a&amp;b
'a&b'.h();
```

### wrap / insert
```javascript
// [text]
'text'.wrap('[]');
'[]'.insert('text');
// <li>text</li>
'text'.wrap('<li></li>');
'<li></li>'.insert('text');
// [a&amp;b]
'a&b'.wrap('[]');
'[]'.insert('a&b');
```

```javascript
// <li class="cls">a&amp;b</li>
'a&b'.wrap('<li class="cls">$..</li>');
'<li class="cls">$..</li>'.insert('a&b');
// <li class="cls"><b>text</b></li>
'<b>text</b>'.wrap('<li class="cls">$__</li>');
'<li class="cls">$__</li>'.insert('<b>text</b>');
```

```javascript
var data = {one: 'a&b', two: '<b>text</b>'};
// <li>a&amp;b</li>
'<li>$.one.</li>'.insert(data);
// <li><b>text</b></li>
'<li>$_two_</li>'.insert(data);
```

```javascript
var data = [{body: 'one'}, {body: 'two'}];
// <li>one</li><li>two</li>
'<li>$.body.</li>'.insert(data);
```

```javascript
var data = ['one', 'two'];
// <li>one</li><li>two</li>
'<li>$..</li>'.insert(data);
```

```javascript
var data = {id: 'list'};
// <ul id="list"><li>one</li><li>two</li></ul>
'<li>$.body.</li>'.insert(data).wrap('<ul id="$.id.">$__</ul>', data);
```
## API
### String.h()
escape string

### String.wrap(wrapper, data, callback)
- wrapper (string)
- data (object / array) optional
- callback (function) optional

### String.insert(data, callback)
- data (string / object / array)
- callback (function) optional
