---
UID: NC:d3dkmddi.DXGKDDI_CANCELQUEUEDFLIPS
tech.root: display
title: DXGKDDI_CANCELQUEUEDFLIPS
ms.date: 02/06/2023
targetos: Windows
description: Learn more about the DXGKDDI_CANCELQUEUEDFLIPS function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:  
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
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
 - DXGKDDI_CANCELQUEUEDFLIPS
f1_keywords:
 - DXGKDDI_CANCELQUEUEDFLIPS
 - d3dkmddi/DXGKDDI_CANCELQUEUEDFLIPS
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_CANCELQUEUEDFLIPS
---

## -description

In the [hardware flip queue model](/windows-hardware/drivers/display/hardware-flip-queue), the OS calls a display miniport driver's **DXGKDDI_CANCELQUEUEDFLIPS** function to synchronously cancel previously queued flips. This function was superseded by [**DXGKDDI_CANCELFLIPS**](nc-d3dkmddi-dxgkddi_cancelflips.md) starting in WDDM 3.0.

## -parameters

### -param hAdapter

[in] Handle to a display adapter.

### -param pCancelQueuedFlips

[in/out] Pointer to a [**DXGKARG_CANCELQUEUEDFLIPS**](ns-d3dkmddi-dxgkarg_cancelqueuedflips.md) structure containing the parameters for this function.

## -returns

**DXGKDDI_CANCELQUEUEDFLIPS** returns STATUS_SUCCESS. The driver should always return a success code.

## -remarks

Asynchronously cancelled PresentIds are reported via the [VSync interrupt mechanism](/windows-hardware/drivers/display/hardware-flip-queue#specifying-vsync-interrupt-behavior).

## -see-also

[**DXGKDDI_CANCELFLIPS**](nc-d3dkmddi-dxgkddi_cancelflips.md)
