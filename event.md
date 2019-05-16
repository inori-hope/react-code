#### pooled


#### event combine scroll: normalizeScrollDataFromTarget
```js
{
    scrollTop: target.scrollTop,
    scrollLeft: target.scrollLeft,
    clientWidth: target.clientWidth,
    clientHeight: target.clientHeight,
    scrollHeight: target.scrollHeight,
    scrollWidth: target.scrollWidth
}
```


#### normalizeMouseWheelData
````js
function(nativeEvent) {
  var delta = 0;
  var deltaX = 0;
  var deltaY = 0;

  /* traditional scroll wheel data */
  if ( nativeEvent.wheelDelta ) { delta = nativeEvent.wheelDelta/120; }
  if ( nativeEvent.detail     ) { delta = -nativeEvent.detail/3; }

  /* Multidimensional scroll (touchpads) with deltas */
  deltaY = delta;

  /* Gecko based browsers */
  if (nativeEvent.axis !== undefined &&
      nativeEvent.axis === nativeEvent.HORIZONTAL_AXIS ) {
    deltaY = 0;
    deltaX = -delta;
  }

  /* Webkit based browsers */
  if (nativeEvent.wheelDeltaY !== undefined ) {
    deltaY = nativeEvent.wheelDeltaY/120;
  }
  if (nativeEvent.wheelDeltaX !== undefined ) {
    deltaX = -nativeEvent.wheelDeltaX/120;
  }

  return { delta: delta, deltaX: deltaX, deltaY: deltaY };
};

```