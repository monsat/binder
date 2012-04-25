binder
======

simple template engine for JavaScript.

## USAGE
### wrap / insert
```javascript
// [text]
'text'.wrap('[]');
'[]'.insert('text');
// <li>text</li>
'text'.wrap('<li></li>');
'<li></li>'.insert('text');
// <li class="cls">text</li>
'text'.wrap('<li class="cls"><!-- contents --></li>');
'<li class="cls"><!-- contents --></li>'.insert('text');
```

```javascript
var data = {one: 'a&b', two: '<b>text</b>'};
// <li>a&amp;b</li>
'<li><!-- $(.one) --></li>'.insert(data);
// <li><b>text</b></li>
'<li><!-- $(_two) --></li>'.insert(data);
```

```javascript
var data = [{body: 'a&b'}, {body: '<b>text</b>'}];
var data2 = {id: 'list'};
// <li>one</li><li>two</li>
'<li><!-- $(.body) --></li>'.insert(data);
// <ul id="list"><li>one</li><li>two</li></ul>
'<li><!-- $(.body) --></li>'.insert(data).wrap('<ul id="<!-- $(.id) -->"><!-- contents --></ul>', data2);
```

## API
### String.wrap(wrapper, data)
- wrapper (string)
- data (object / array)

### String.insert(data)
- data (string / object / array)
