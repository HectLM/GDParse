# GDParse
A JavaScript library for parsing, decoding and encoding Geometry Dash levels and game save files.

## Installation & Usage
Install using npm
```
npm install GDParse
```

Use in code
```js
// Import default
import gdparse from 'GDParse';

// Or import individually
import { parseLevel, serializeLevel, decodeGameSave, parseGameSave, serializeGameSave } from 'GDParse';
```

## Documentation

### Methods

#### `parseLevel (levelString: string)`
Converts a GD level string to a human-readable JS object format. Here's how it's structured:
```js
{
  info: Object // level settings
  data: Array<Object> // array containing all level objects
}
```

#### `serializeLevel (obj: Object)`
Converts a JS object back into the level string.

#### `decodeGameSave (gameSaveString: string)`
Decompresses the Geometry Dash save file into an xml format. By default, the save file is compressed and encrypted. Will throw an error, if the given game save is corrupted.

#### `parseGameSave (xmlString: string)`
Converts a decompressed Geometry Dash save file into a JS array with all the levels as objects. Will throw an error, if the given game save is corrupted.

#### `serializeGameSave (obj: any)`
Converts a JS array back into the XML string. Note that it does not need to be encrypted back into it's original form, since GD does that automatically when started.

### Structure

#### GDObject
Here are all the properties a Geometry Dash object could have. None of them are required, but `id`, `x` and `y` are necessary for an object to be displayed.
```js
{
  id: number,
  x: number,
  y: number,
  flipx: 0 | 1,
  flipy: 0 | 1,
  r: number,
  red: number,
  green: number,
  blue: number,
  duration: number,
  touchTriggered: 0 | 1,
  coin: number,
  checked: 0 | 1,
  tintGround: number,
  pCol1: number,
  pCol2: number,
  blending: number,
  layer: number,
  baseCol: number,
  decorCol: number,
  color: number,
  z: number,
  order: number,
  moveX: number,
  moveY: number,
  easing: number,
  text: string,
  scale: number,
  parent: number,
  opacity: number,
  isTrigger: 0 | 1,
  hsvEnabled1: 0 | 1,
  hsvEnabled2: 0 | 1,
  hsv1: string,
  hsv2: string,
  fadeIn: number,
  hold: number,
  fadeOut: number,
  pulseType: number,
  copiedHSV: string,
  copiedID: number,
  targetGroupID: number,
  targetPulseType: number,
  seperation: number,
  activateGroup: number,
  groups: Array<number>,
  followX: number,
  followY: number,
  copyOpacity: number,
  layer2: number,
  spawnTriggered: number,
  spawnDelay: number,
  dontFade: number,
  mainOnly: number,
  detailOnly: number,
  dontEnter: number,
  degrees: number,
  times360: number,
  lockRotation: number,
  followID: number,
  xFollow: number,
  yFollow: number,
  shakeStrength: number,
  animationID: number,
  count: number,
  subtractCount: number,
  pickupMode: number,
  itemA: number,
  holdMode: number,
  touchToggle: number,
  shakeInterval: number,
  easingRate: number,
  exclusive: number,
  multiTrigger: number,
  countComparison: number,
  dualMode: number,
  followSpeed: number,
  followDelay: number,
  followOffset: number,
  onExit: number,
  dynamic: number,
  itemB: number,
  noGlow: number,
  rotationSpeed: number,
  noRotate: number,
  multiActivate: number,
  useTarget: number,
  targetCoords: number,
  disabled: number,
  highDetail: number,
  followMaxSpeed: number,
  randomizeStart: number,
  animationSpeed: number,
  linkedGroup: number
}
```

### LevelSettings
Here are all the properties, a Geometry Dash level's settings object could have. Once again, none of them are required:
```js
{
    "gamemode": number,
    "speed": number,

    "bg": ColorID,
    "g": ColorID,
    "font": number,
    "songoffset": number,

    "mini": 0 | 1,
    "dual": 0 | 1,
    "startPos": number,
    "2p": 0 | 1,
    "flipgravity": 0 | 1,
    "guidelines": Array<{ timestamp: number, color: number }>,
    "songfadein": number,
    "songfadeout": number,
    "line": number,
    
    "colors": Array<Object>,

    // old color system (used only for backwards-compatibility)
  
    "bgr": number,
    "bgg": number,
    "bgb": number,

    "gr": number,
    "gg": number,
    "gb": number,

    "liner": number,
    "lineg": number,
    "linen": number,

    "objr": number,
    "objg": number,
    "objb": number,

    "1r": number,
    "1g": number,
    "1b": number,

    "1blend": number,

    "bgp": number,
    "gp": number,
    "linep": number,
    "objp": number,
    "1p": number,

    "bgc": number,
    "gc": number,
    "linec": number,
    "objc": number,
    "1c": number,
    "2c": number,
    "3c": number,
    "4c": number,
    "3dlc": number
}
```

## Contributing
All contribution is welcome! Feel free to leave an issue or submit a pull request on our [Github repo](https://github.com/HectLM/GDParse/)
