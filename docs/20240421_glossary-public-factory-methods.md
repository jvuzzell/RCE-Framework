# Public Factory Methods

Below are JavaScript code examples demonstrating how to use each of the public methods from the Factory module defined in your provided JavaScript file. These examples illustrate how you might interact with these methods in a practical scenario.

### Table of Contents

1. [`construct`](#1-construct)
1. [`registerComponent`](#2-registercomponent)
1. [`storeComponent`](#3-storecomponent)
1. [`getComponentByKey`](#4-getcomponentbykey)
1. [`getAllComponents`](#5-getallcomponents)
1. [`getComponentsByName`](#6-getcomponentsbyname)
1. [`getComponentByName`](#7-getcomponentbyname)
1. [`setEventSubscriptions`](#8-seteventsubscriptions)
1. [`setParentBus`](#9-setparentbus)
1. [`subscribeToAllEventNotifications`](#10-subscribetoalleventnotifications)
1. [`templateToHtml`](#11-templatetohtml)
1. [`setEventListeners`](#12-seteventlisteners)

---

## 1. `construct`
This function builds and initializes a component, returning an instance with public methods.

```javascript
let myComponentConfig = {
  state: { key: 'myComponentKey', componentName: 'MyComponent' },
  props: { isEnabled: true },
  template: '<div>Hello World!</div>'
};

let myComponent = Factory.construct(myComponentConfig);
```

## 2. `registerComponent`
Registers a component and potentially its subcomponents with configuration and templates.

```js
Factory.registerComponent(myComponentConfig);
```

## 3. `storeComponent`
Stores a component in the internal storage by key.

```js
Factory.storeComponent('myComponentKey', myComponent);
```

## 4. `getComponentByKey`
Retrieves a stored component by its key.

```js
let retrievedComponent = Factory.getComponentByKey('myComponentKey');
```

## 5. `getAllComponents`
Returns all stored components.

```js
let allComponents = Factory.getAllComponents();

```

## 6. `getComponentsByName`
Retrieves all components by a specified name.

```js
let componentsByName = Factory.getComponentsByName('MyComponent');
```

## 7. `getComponentByName`
Retrieves the first component that matches a specified name.

```js
let firstComponent = Factory.getComponentByName('MyComponent');
```

## 8. `setEventSubscriptions`
Sets up subscriptions for a component to other components or events.

```js
Factory.setEventSubscriptions('myComponentKey', {
  subscriptions: {
    'anotherEventBusId': ['otherComponentKey1', 'otherComponentKey2']
  }
});

```

## 9. `setParentBus`
Registers a component with specified event buses.

```js
Factory.setParentBus('myComponentKey', {
  eventBus: ['eventBus1', 'eventBus2']
});

```

## 10. `subscribeToAllEventNotifications`
Subscribes a component to all notifications from an event bus.

```js
Factory.subscribeToAllEventNotifications('myComponentKey', 'eventBus1');
```

## 11. `templateToHTML`
Converts a template string into HTML DOM nodes.

```js
let templateStr = '<div>Sample Template</div>';
let templateNode = Factory.templateToHTML(templateStr);
document.body.appendChild(templateNode); // Example usage
```

## 12. `setEventListeners`
Sets up event listeners based on a component's configuration.

```js
let componentConfig = {
  state: { key: 'myComponentKey' },
  props: {
    eventListeners: {
      click: {
        selector: 'button',
        listener: 'click',
        callback: function(event, component) {
          console.log('Button clicked!', component);
        }
      }
    }
  }
};
Factory.setEventListeners(componentConfig);
```