# React Spinners

[![npm version](https://badge.fury.io/js/@f1stnpm2/reprehenderit-libero-similique.svg)][npm_url]
[![downloads](https://img.shields.io/npm/dt/@f1stnpm2/reprehenderit-libero-similique.svg)][npm_url]
[![license](https://img.shields.io/npm/l/@f1stnpm2/reprehenderit-libero-similique.svg)][npm_url]

<!-- [![next version](https://badgen.net/npm/v/@f1stnpm2/reprehenderit-libero-similique/next)](https://www.npmjs.com/package/@f1stnpm2/reprehenderit-libero-similique/v/next) -->

[![Coverage Status](https://coveralls.io/repos/github/davidhu2000/@f1stnpm2/reprehenderit-libero-similique/badge.svg?branch=main)](https://coveralls.io/github/davidhu2000/@f1stnpm2/reprehenderit-libero-similique?branch=master)
![Dependency Count](https://badgen.net/bundlephobia/dependency-count/@f1stnpm2/reprehenderit-libero-similique)
![Types Included](https://badgen.net/npm/types/@f1stnpm2/reprehenderit-libero-similique)
![Tree Shaking Supported](https://badgen.net/bundlephobia/tree-shaking/@f1stnpm2/reprehenderit-libero-similique)

[npm_url]: https://www.npmjs.org/package/@f1stnpm2/reprehenderit-libero-similique

A collection of loading spinners with React.js based on [Halogen](https://github.com/yuanyan/halogen).

This package is bootstraped using [react-npm-boilerplate](https://github.com/juliancwirko/react-npm-boilerplate)

## Demo

[Demo Page](https://www.davidhu.io/@f1stnpm2/reprehenderit-libero-similique)

[Storybook](https://www.davidhu.io/@f1stnpm2/reprehenderit-libero-similique/storybook/)

## Installation

With Yarn:

```bash
yarn add @f1stnpm2/reprehenderit-libero-similique
```

With npm:

```bash
npm install --save @f1stnpm2/reprehenderit-libero-similique
```

## Usage

Each loader has their own default properties. You can overwrite the defaults by passing props into the loaders.

Each loader accepts a `loading` prop as a boolean. The loader will render `null` if `loading` is `false`.

### Example

```tsx
import { useState, CSSProperties } from "react";
import ClipLoader from "@f1stnpm2/reprehenderit-libero-similique/ClipLoader";

const override: CSSProperties = {
  display: "block",
  margin: "0 auto",
  borderColor: "red",
};

function App() {
  let [loading, setLoading] = useState(true);
  let [color, setColor] = useState("#ffffff");

  return (
    <div className="sweet-loading">
      <button onClick={() => setLoading(!loading)}>Toggle Loader</button>
      <input value={color} onChange={(input) => setColor(input.target.value)} placeholder="Color of the loader" />

      <ClipLoader
        color={color}
        loading={loading}
        cssOverride={override}
        size={150}
        aria-label="Loading Spinner"
        data-testid="loader"
      />
    </div>
  );
}

export default App;
```

<details><summary>Example using React Class</summary>

```tsx
import React from "react";
import ClipLoader from "@f1stnpm2/reprehenderit-libero-similique/ClipLoader";

const override: React.CSSProperties = {
  display: "block",
  margin: "0 auto",
  borderColor: "red",
};

class AwesomeComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      loading: true,
    };
  }

  render() {
    return (
      <div className="sweet-loading">
        <ClipLoader
          cssOverride={override}
          size={150}
          color={"#123abc"}
          loading={this.state.loading}
          speedMultiplier={1.5}
          aria-label="Loading Spinner"
          data-testid="loader"
        />
      </div>
    );
  }
}
```

</details>

## Available Loaders, PropTypes, and Default Values

Common default props for all loaders:

```
loading: true;
color: "#000000";
cssOverride: {}
speedMultiplier: 1;
```

All valid HTML props such as `aria-*` and `data-*` props are fully supported.

### `color` prop

`color` prop accepts a color hash in the format of `#XXXXXX` or `#XXX`. It also accepts basic colors listed below:

> maroon, red, orange, yellow, olive, green, purple, white,
> fuchsia, lime, teal, aqua, blue, navy, black, gray, silver

### `cssOverride` prop

The `cssOverride` prop is an object of camelCase styles used to create inline styles on the loaders. Any html css property is valid here.

### `size`, `height`, `width`, and `radius` props

The input to these props can be _number_ or _string_.

- If value is number, the loader will default to css unit `px`.
- If value is string, the loader will verify the unit against valid css units.
  - If unit is valid, return the original value
  - If unit is invalid, output warning console log and default to `px`.

The table below has the default values for each loader.

|            Loader | size | height | width | radius | margin |
| ----------------: | :--: | :----: | :---: | :----: | :----: |
|         BarLoader |      |  `4`   | `100` |        |
|        BeatLoader | `15` |        |       |        |  `2`   |
|      BounceLoader | `60` |        |       |        |
|      CircleLoader | `50` |        |       |        |
| ClimbingBoxLoader | `15` |        |       |        |
|        ClipLoader | `35` |        |       |        |
|       ClockLoader | `50` |        |       |        |
|         DotLoader | `60` |        |       |        |  `2`   |
|        FadeLoader |      |  `15`  |  `5`  |  `2`   |  `2`   |
|        GridLoader | `15` |        |       |        |
|        HashLoader | `50` |        |       |        |  `2`   |
|        MoonLoader | `60` |        |       |        |  `2`   |
|      PacmanLoader | `25` |        |       |        |  `2`   |
|   PropagateLoader | `15` |        |       |        |
|        PuffLoader | `60` |        |       |        |
|       PulseLoader | `15` |        |       |        |  `2`   |
|        RingLoader | `60` |        |       |        |  `2`   |
|        RiseLoader | `15` |        |       |        |  `2`   |
|      RotateLoader | `15` |        |       |        |  `2`   |
|       ScaleLoader |      |  `35`  |  `4`  |  `2`   |  `2`   |
|        SyncLoader | `15` |        |       |        |  `2`   |
