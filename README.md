# WaveShare Pico-LCD drivers for DeviceScript

Drivers for RPi Pico display hats by WaveShare.

### Pico-LCD-1.14

![Pico-LCD-1.14](assets/pico-lcd-114.png)

https://www.waveshare.com/pico-lcd-1.14.htm

## Setup

This projet uses GitHub releases, which you can also add to your package.json dependencies list.

```bash
npm install --save mmoskal/devicescript-waveshare-pico-lcd
```

## Usage

```ts
import { WaveSharePicoLCD114 } from "devicescript-waveshare-pico-lcd"

const board = new WaveSharePicoLCD114()

const gp = board.startGamepad()
const disp = await board.startDisplay()

for (let i = 1; i < 15; ++i)
    disp.image.print(`Hello world c=${i}`, 2, i * 10 - 8, i)
await disp.show()

gp.change.subscribe(btns => {
    if (btns & ds.GamepadButtons.Down) {
        // ...
    }
})
```

## Supported devices

PRs are welcome!
