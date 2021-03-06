# ember-keyboard-shortcuts

## Usage

### Install

In your ember-cli project:
```bash
npm install Skalar/ember-keyboard-shortcuts --save-dev
ember generate ember-keyboard-shortcuts
```

### Use in a route

```javascript
import KeyboardShortcuts from 'ember-keyboard-shortcuts/mixins/route';

export default Ember.Route.extend(
  KeyboardShortcuts,

  {
    actions: {
      cancel: function() {
        this.transitionTo('posts');
      }
    },

    keyboardShortcuts: {
      // trigger 'cancel' action when esc is pressed
      'esc' : 'cancel',

      'ctrl+c' : {
        action         : 'cancel' // action to trigger
        global         : false    // whether to trigger inside input (default: true)  
        preventDefault : true     // (default: true)
      }

      // trigger function when tab is pressed
      tab : function() {
        console.log('Tab pressed');
        return false; // preventDefault
      }
    }
  }
);
```

### Use in a view
```javascript
import KeyboardShortcuts from 'ember-keyboard-shortcuts/mixins/route';

export default Ember.View.extend(
  KeyboardShortcuts,

  {
    keyboardShortcuts: {
      'esc'    : 'cancel',
      'ctrl+s' : 'save'
    }
  }
);
```

## Development

### Installation

* `git clone` this repository
* `npm install`
* `bower install`

### Running

* `ember server`
* Visit your app at http://localhost:4200.

### Running Tests

* `ember test`
* `ember test --server`

### Building

* `ember build`

For more information on using ember-cli, visit [http://www.ember-cli.com/](http://www.ember-cli.com/).
