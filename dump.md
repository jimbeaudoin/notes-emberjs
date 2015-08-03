##### Const
```javascript
import Ember from 'ember';

const {on, computed, observer} = Ember;
```

##### Components
```javascript
import Ember from 'ember';

export default Ember.Component.extend({
  tagName: 'span',
  classNames: ['sweet-component'],
  attributeBindings: ['some-attribute'],
  actions:  {
    save: function() {
      this.sendAction('save');
    }
  }
});
```
