---
title: "XRProjectionLayer: textureHeight property"
short-title: textureHeight
slug: Web/API/XRProjectionLayer/textureHeight
page-type: web-api-instance-property
status:
  - experimental
browser-compat: api.XRProjectionLayer.textureHeight
---

{{APIRef("WebXR Device API")}}{{SeeCompatTable}}

The read-only **`textureHeight`** property of the {{domxref("XRProjectionLayer")}} interface indicates the height in pixels of the color textures of this layer.

The projection layer's texture height is determined by the user agent or the device. It is reported in the {{domxref("XRSubImage")}}, which can only be accessed inside the frame loop. If you want to manage your own depth buffers and don't want to wait for first frame after layer creation to determine the required dimensions for those buffers, the `textureHeight` property allows access to layer texture height outside the frame loop. Allocation of these buffers can happen directly after layer creation.

## Value

A number indicating the height in pixels.

## Examples

### Using `textureHeight`

The `textureHeight` of a layer is useful when creating render buffers for a layer. See also {{domxref("WebGL2RenderingContext.renderbufferStorageMultisample()")}}.

```js
let glLayer = xrGLBinding.createProjectionLayer();

let color_rb = gl.createRenderbuffer();
gl.bindRenderbuffer(gl.RENDERBUFFER, color_rb);
gl.renderbufferStorageMultisample(gl.RENDERBUFFER, samples, gl.RGBA8,
                                  glLayer.textureWidth, glLayer.textureHeight);
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("XRWebGLBinding.createProjectionLayer()")}}
- {{domxref("WebGL2RenderingContext.renderbufferStorageMultisample()")}}
- {{domxref("XRSubImage")}}
