---
UID: NC:d3dkmddi.DXGKDDI_UPDATEFLIPQUEUELOG
tech.root: display
title: DXGKDDI_UPDATEFLIPQUEUELOG
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGKDDI_UPDATEFLIPQUEUELOG callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: DIRQL
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
 - DXGKDDI_UPDATEFLIPQUEUELOG
f1_keywords:
 - DXGKDDI_UPDATEFLIPQUEUELOG
 - d3dkmddi/DXGKDDI_UPDATEFLIPQUEUELOG
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_UPDATEFLIPQUEUELOG
---

## -description

The OS calls **DXGKDDI_UPDATEFLIPQUEUELOG** to request that the display driver update the hardware flip queue log.

## -parameters

### -param hAdapter

[in] Handle to a display adapter.

### -param pUpdateFlipQueueLog

[in/out] Pointer to a [**DXGKARG_UPDATEFLIPQUEUELOG**](ns-d3dkmddi-dxgkarg_updateflipqueuelog.md) structure containing the parameters for this function.

## -returns

**DXGKDDI_UPDATEFLIPQUEUELOG** returns STATUS_SUCCESS. The driver should always return a success code.

## -remarks

See [Hardware flip queue](/windows-hardware/drivers/display/hardware-flip-queue) for more information.

## -see-also

[**DXGKARG_UPDATEFLIPQUEUELOG**](ns-d3dkmddi-dxgkarg_updateflipqueuelog.md)
