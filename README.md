paylogic-ticketing-api
================

It includes polymer elements that encapsulate the functionality provided by the Paylogic Ticketing API.

## Getting Started

Import the template

```html
<link rel="import" href="paylogic-ticketing-api.html">
```

and add the element in your document

```html
<paylogic-ticketing-api></paylogic-ticketing-api>
```

You can then use the services of the Paylogic Ticketing API in the following way.

```javascript
document.addEventListener('polymer-ready', function() {
  var pta = document.querySelector('paylogic-ticketing-api');
  pta.addEventListener('init-ready', function() {
    pta.getEvent('32441a11f9024cd9bf1acdc5c3def80a');
  });
  pta.addEventListener('pta-event-loaded', function(e) {
    console.log(e.detail);
  });
});
```

For more info check the [demo](https://github.com/spirosikmd/paylogic-ticketing-api/blob/master/demo.html).
