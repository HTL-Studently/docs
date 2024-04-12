

## [@svelte-put/qr](https://svelte-put.vnphanquang.com/docs/qr)

The QR-Codes need to have the following form in order to be successfully read by banking apps:

````
BCD
001
1
SCT
KSPKAT2KXXX
Max Mustermann
AT123456789000063657
EUR0.00
```

After specifying the structure like this, the QR code is generated as such:

````
<QR
data={qrData}
moduleFill="white"
anchorOuterFill="white"
anchorInnerFill="white"
width="500"
height="500"
/>
```

This does not save the QR-Code into any file. It generates in the browser and does not need to be saved anywhere, as all data required for the generation is stored in the individual product instance.

## [@svelte-pdf](https://www.npmjs.com/package/svelte-pdf)

WIP - Not yet successfully implemented