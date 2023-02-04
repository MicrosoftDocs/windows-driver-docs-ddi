---
UID: NC:d3dkmddi.DXGKDDI_SETFLIPQUEUELOGBUFFER
tech.root: display
title: DXGKDDI_SETFLIPQUEUELOGBUFFER
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGKDDI_SETFLIPQUEUELOGBUFFER callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SETFLIPQUEUELOGBUFFER
f1_keywords:
 - DXGKDDI_SETFLIPQUEUELOGBUFFER
 - d3dkmddi/DXGKDDI_SETFLIPQUEUELOGBUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_SETFLIPQUEUELOGBUFFER
---

## -description

In the [hardware flip queue model](/windows-hardware/drivers/display/hardware-flip-queue), the OS calls a display miniport driver's [**DXGKDDI_SETFLIPQUEUELOGBUFFER**](/windows-hardware/drivers/ddi/nc-d3dkmddi-dxgkddi_setflipqueuelogbuffe
r) function to provide the driver with the flip queue log.

## -parameters

### -param hAdapter

[in] Handle to a display adapter.

### -param pSetFlipQueueLogBuffer

[in] Pointer to a [**DXGKARG_SETFLIPQUEUELOGBUFFER**](ns-d3dkmddi-dxgkarg_setflipqueuelogbuffer.md) structure containing the parameters for this function.

## -returns

**DXGKDDI_CANCELFLIPS** returns STATUS_SUCCESS. The driver should always return a success code.

## -remarks

See [Obtaining present statistics for queued flips](/windows-hardware/drivers/display/hardware-flip-queue#obtaining-present-statistics-for-queued-flips) for more information.

## -see-also

[**DXGKARG_SETFLIPQUEUELOGBUFFER**](ns-d3dkmddi-dxgkarg_setflipqueuelogbuffer.md)
