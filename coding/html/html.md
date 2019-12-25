# HTML

## Special characters

`&nbsp;` - Non-breaking space

```
Hello &nbsp; there!
```

`&times;` - HTML entity for close buttons. Alternative to the unicode ×

```javascript
// an example of the close button with React handler and Bootstrap styles
<button
  type='button'
  onClick={() => onRemove(id)}
  className='btn btn-outline-danger btn-sm'
>
  &times;
</button>
```
