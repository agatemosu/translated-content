---
title: GPUBindGroup
slug: Web/API/GPUBindGroup
l10n:
  sourceCommit: 5f226b6f08c5cff7f96b7cc49a164fdc43d11a0c
---

{{APIRef("WebGPU API")}}{{SecureContext_Header}}{{AvailableInWorkers}}

La interfaz **`GPUBindGroup`** de la {{domxref("WebGPU API", "API de WebGPU", "", "nocode")}} está basada en un {{domxref("GPUBindGroupLayout")}} y define un conjunto de recursos que se agrupan juntos en un grupo y cómo esos recursos son usados en las etapas del shader.

Una instancia del objeto `GPUBindGroup` se crea usando el método {{domxref("GPUDevice.createBindGroup()")}}.

{{InheritanceDiagram}}

## Propiedades de la instancia

- {{domxref("GPUBindGroup.label", "label")}}
  - : Una cadena de texto que proporciona una etiqueta que se puede usar para identificar al objeto, por ejemplo, en mensajes de {{domxref("GPUError")}} o advertencias en la consola.

## Ejemplos

> [!NOTE]
> Las [muestras de WebGPU](https://webgpu.github.io/webgpu-samples/) tienen muchos más ejemplos.

### Ejemplo básico

Nuestra [demo básica de cómputo](https://mdn.github.io/dom-examples/webgpu-compute-demo/) muestra un ejemplo de cómo crear una disposición de grupos de enlace y luego usarlo como plantilla para crear un grupos de enlace.

```js
// …

const bindGroupLayout = device.createBindGroupLayout({
  entries: [
    {
      binding: 0,
      visibility: GPUShaderStage.COMPUTE,
      buffer: {
        type: "storage",
      },
    },
  ],
});

const bindGroup = device.createBindGroup({
  layout: bindGroupLayout,
  entries: [
    {
      binding: 0,
      resource: {
        buffer: output,
      },
    },
  ],
});

// …
```

## Especificaciones

{{Specifications}}

## Compatibilidad con navegadores

{{Compat}}

## Véase también

- La [API de WebGPU](/es/docs/Web/API/WebGPU_API)
