# @artcom/react-three-arjs (DRAFT)

React components and hooks for creating [AR.js](https://github.com/AR-js-org/AR.js) applications with [react-three-fiber](https://github.com/pmndrs/react-three-fiber)


```
npm install @artcom/react-three-arjs
```

```
Example GIFSs
```

## Usage

### ARCanvas

```jsx
<ARCanvas
  arEnabled                                       // if false, it will render children into <Canvas /> without AR context
  patternRatio = 0.5                              // passed to arToolkit context¹
  detectionMode = "mono_and_matrix"               // passed to arToolkit context¹
  cameraParametersUrl = "data/camera_para.dat"    // passed to arToolkit context¹
  matrixCodeType = "3x3"                          // passed to arToolkit context¹
/>
```

¹https://ar-js-org.github.io/AR.js-Docs/marker-based/#threejs

### ARMarker

```jsx
<ARMarker
  children              // regular children
  type                  // arToolkit marker type, "barcode" or "pattern"
  barcodeValue          // if type="barcode", its algorithmic value
  patternUrl            // if type="pattern", a link to its pattern file
  params                // object which accepts all marker settings²
  onMarkerFound         // callback which will be invoked when marker has been found
  onMarkerLost          // callback which will be invoked when previously found marker has been lost
/>
```

²https://ar-js-org.github.io/AR.js-Docs/marker-based/#api-reference-for-marker-based)

## AR.js caveats
- AR.js cannot be bundled, since it exposes global variables.
- AR.js context requires [camera_para.dat](https://github.com/AR-js-org/AR.js/blob/master/data/data/camera_para.dat) file.
- Look at the [Example](./example) using webpack for bundling.
## ToDos
- [ ] Add example video/gif
- [ ] CI Build
- [ ] Use ar.js as module, depends on https://github.com/AR-js-org/AR.js/pull/116
