# numbers-animation-react

## Props

| Name              | Type    | Default | Description                                                                                                      |
| ----------------- | ------- | ------- | ---------------------------------------------------------------------------------------------------------------- |
| value             | number  | none    | Value for the animation to end at                                                                                |
| startValue?       | number  | 0       | Animation starting value, if startValue is lower than value animation will increment otherwise it will decrement |
| duration?         | number  | 1000    | Duration for the animation (milliseconds)                                                                        |
| generateCommas?   | boolean | false   | Returns the number with commas                                                                                   |
| generateDecimals? | boolean | false   | Returns the number with 2 decimals                                                                               |

## Example

```js
import React from "react";
import AnimatedNumber from "numbers-animation-react";

function App() {
  return (
    <span>
      <AnimatedNumber
        value={10000}
        startValue={100000}
        duration={1000}
        generateCommas={true}
        generateDecimals={true}
      />
    </span>
  );
}

export default App;
```

## Example 2

```js
import React, { useState, useEffect } from "react";
import AnimatedNumber from "numbers-animation-react";

function App() {
  const [animateTo, setAnimateTo] = useState(0);
  const [animateFrom, setAnimateFrom] = useState(1000);

  useEffect(() => {
    /* 
    Set the animateFrom to the previous value of animateTo every time animateTo changes
    so it will increment / decrement based on a previous value rather than 0 or fixed specified value
    */
    setAnimateFrom(animateTo);
  }, [animateTo]);

  return (
    <span>
      <AnimatedNumber
        value={animateTo}
        startValue={animateFrom}
        duration={1000}
        generateCommas={true}
        generateDecimals={true}
      />
    </span>
  );
}

export default App;
```
