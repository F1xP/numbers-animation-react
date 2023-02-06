# animate-numbers-react

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
import AnimatedNumber from "animate-numbers-react";

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
