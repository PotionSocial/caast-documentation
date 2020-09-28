# Caast Emitter

Caast emitter is a pixel tracking javascript library allowing you to easily send purchased items on your purchase page. It will allow you to send qualified data to caast in order to properly identify your ROI.

## Getting started

```javascript
(function (c, a, A, s, t, j, S) {
  "caastEmitter" in c ||
    ((c.caastEmitter = function () {
      c.caastEmitter.q.push(arguments);
    }),
    (c.caastEmitter.q = []));
  (j = a.createElement(A)), (S = a.getElementsByTagName(A)[0]);
  j.src = s;
  j.async = 1;
  S.parentNode.insertBefore(j, S);
})(
  window,
  document,
  "script",
  "https://cdn.caast.tv/caast-latest/caastEmitter.js",
  "caastEmitter"
);
caastEmitter("init", {
  "APP-ID": "MY_APP_ID",
  "APP-KEY": "MY_APP_KEY",
});
```

## Track purchase

Once caastEmitter is instanciated

```javascript
caastEmitter("track", {
  total: 499,
  products: [
    { id: "1", quantity: 1, price: 100 },
    { id: "2", quantity: 1, price: 399 },
  ],
});
```

## Data properties

| Clé de propriété | Type de valeur   | Description du paramètre                                                                                                                                                                                                                                                                                                          |
| ---------------- | ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| products         | array of objects | Array of json objects with the unique product identifier referenced in caast's registered products, you can also specify `quantity` and `price`, price will refer to product price, not total price based on price \* quantity. _Obligatoire_: `id` et `quantity`. Exemple : `[{'id': 'ABC123', 'quantity': 2, 'price': 119.99}]` |
| total            | integer or float | Total value of the purchase operation                                                                                                                                                                                                                                                                                             |
| total_items      | integer          | Total items in the purchase                                                                                                                                                                                                                                                                                                       |