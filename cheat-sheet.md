# Ember.js Cheat Sheet

### Addons

```sh
ember install ember-cli-sass
```

### Generators

```sh
ember g -h
ember g acceptance-test index
ember g component <component-name> # Must contain a hyphen
```

### Tests

##### Acceptance Test Example

```javascript
test('visiting /', function(assert) {
  visit('/');

  andThen(function() {
    assert.equal(currentURL(), '/');
    assert.ok(find(':contains(l333t)').length, 'Show l333t somewhere');
  });
});
```

##### Acceptance: async safe test helpers

```javascript
// Return a promise
visit('/'); // visit(url);
fillIn('input[name=word]', 'bob'); // fillIn(selector, text);
click('.my-class:contains(a)'); // click(selector);
keyEvent('input[name=word]', 'keyup', 13); // keyEvent(selector, type, key);
triggerEvent(sel, type, opts);
```

##### Acceptance: sync test helpers 

```javascript
find(selector, content);
currentPath();
currentRouteName();
currentURL();

// Important: assert function must be placed in a andThen() function 
// to run at the right time.
// They are NOT async safe.
andThen(function() {
  assert.equal(currentURL(), '/');
  assert.ok(find(':contains(hello)').length, 'Show hello somewhere');
  assert.ok(find('.my-class:contains(a)').length, 'my class contain letter a');
});
```

##### Debug

```javascript
// From the test page in the browser (localhost:4200/tests), click on the test 
// you put the debugger and inspect with your browser dev inspector
debugger;
```
