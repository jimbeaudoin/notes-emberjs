# Tests

##### Component Integration Test
```javascript
test('it renders', function(assert) {
  assert.expect(2);

  // // Set any properties with this.set('myProperty', 'value');
  // // Handle any actions with this.on('myAction', function(val) { ... });

  this.render(hbs`{{login-box}}`);

  assert.equal(this.$().text().trim(), '', 'Show empty');

  // Template block usage:
  this.render(hbs`
    {{#login-box}}
      template block text
    {{/login-box}}
  `);

  assert.equal(this.$().text().trim(), 'template block text', 'Show with text');
  assert.equal(this.$().find('input[placeholder="Password"]').length, 1, "has one password placeholder");
});

test('it show title', function(assert) {
  // Template block usage:
  this.render(hbs`
    {{login-box title="test"}}
  `);

  assert.equal(this.$().find('.title').text(), 'test', 'Show correct title');
});

test('it show one identification input', function(assert) {
  // Template block usage:
  this.render(hbs`
    {{login-box title="test"}}
  `);

  assert.equal(this.$().find('input[type=text]').length, 1, 'has one identification input');
});
```


##### Acceptance Test Example

```javascript
test('visiting / & show Jimmy', function(assert) {
  visit('/');

  andThen(function() {
    assert.equal(currentURL(), '/');
    assert.ok(find(':contains(Jimmy)').length, 'Show Jimmy somewhere');
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
