paylogic-ticketing-api
================

A polymer element which encapsulates the functionality provided by the
[Paylogic Ticketing API.](https://doc.sandbox.paylogic.com/)

## Setup

We only need to run

```bash
bower install
```

to install all the dependecies.

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
    pta.events.get("<event_uri>").then(function(response) {
      var events = JSON.parse(response);
      console.log(events);
    }, function(error) {
      console.error(error);
    });

    // Or use the event uri in the filter method. This has the same result as the previous example.
    pta.events.filter({"uri": "<event_uri>"}).then(function(response) {
      var events = JSON.parse(response);
      console.log(events);
    }, function(error) {
      console.error(error);
    });;

    // Get the products for a specific event.
    pta.products.filter({"event": "<event_uri>"}).then(function(response) {
      var products = JSON.parse(response);
      console.log(products);
    }, function(error) {
      console.error(error);
    });;
  });
});
```

For more info check the [demo](https://github.com/spirosikmd/paylogic-ticketing-api/blob/master/demo.html). Currently,
this will not work for the public, as basic authentication is required.
