binder
======

simple template for JavaScript.

## USAGE
### wrap / insert
```javascript
// [text]
'text'.wrap('[]');
'[]'.insert('text');
// <li>text</li>
'text'.wrap('<li></li>');
'<li></li>'.insert('text');
```

```javascript
// <li class="cls">text</li>
'text'.wrap('<li class="cls"><!-- $(.) --></li>');
'<li class="cls"><!-- $(.) --></li>'.insert('text');
// <li class="cls"><b>text</b></li>
'<b>text</b>'.wrap('<li class="cls"><!-- $(_) --></li>');
'<li class="cls"><!-- $(_) --></li>'.insert('<b>text</b>');
```

```javascript
var data = {one: 'a&b', two: '<b>text</b>'};
// <li>a&amp;b</li>
'<li><!-- $(.one) --></li>'.insert(data);
// <li><b>text</b></li>
'<li><!-- $(_two) --></li>'.insert(data);
```

```javascript
var data = [{body: 'one'}, {body: 'two'}];
// <li>one</li><li>two</li>
'<li><!-- $(.body) --></li>'.insert(data);
```

```javascript
var data = ['one', 'two'];
// <li>one</li><li>two</li>
'<li><!-- $(.) --></li>'.insert(data);
```

```javascript
var data = {id: 'list'};
// <ul id="list"><li>one</li><li>two</li></ul>
'<li><!-- $(.body) --></li>'.insert(data).wrap('<ul id="<!-- $(.id) -->"><!-- $(.) --></ul>', data);
```
## API
### String.wrap(wrapper, data, callback)
- wrapper (string)
- data (object / array) optional
- callback (function) optional

### String.insert(data, callback)
- data (string / object / array)
- callback (function) optional
