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

The services of the Paylogic Ticketing API can then be used in the following way.

```javascript
document.addEventListener('polymer-ready', function() {
  var pta = document.querySelector('paylogic-ticketing-api');

  // Initialization of privates is completed.
  pta.addEventListener('init-ready', function() {
    // Use the event uri to get a specific event.
    pta.events.get("<event_uri>");
    // Or use the event uri in the filter method. This has the same result as the previous example.
    pta.events.filter({"uri": "<event_uri>"})
  });

  // Event service has completed loading the event with the requested uid.
  pta.addEventListener('pta-event-loaded', function(e) {
    console.log(e.detail);
  });
});
```

For more info check the [demo](https://github.com/spirosikmd/paylogic-ticketing-api/blob/master/demo.html). Currently,
this will not work for the public, as basic authentication is required.
