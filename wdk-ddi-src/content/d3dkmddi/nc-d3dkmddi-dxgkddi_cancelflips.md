---
UID: NC:d3dkmddi.DXGKDDI_CANCELFLIPS
tech.root: display
title: DXGKDDI_CANCELFLIPS
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGKDDI_CANCELFLIPS callback function.
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
 - DXGKDDI_CANCELFLIPS
f1_keywords:
 - DXGKDDI_CANCELFLIPS
 - d3dkmddi/DXGKDDI_CANCELFLIPS
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_CANCELFLIPS
---

## -description

In the [hardware flip queue model](/windows-hardware/drivers/display/hardware-flip-queue), the OS calls a display miniport driver's **DXGKDDI_CANCELFLIPS** function to synchronously cancel previously queued flips.

## -parameters

### -param hAdapter

[in] Handle to a display adapter.

### -param pCancelFlips

[in/out] Pointer to a [**DXGKARG_CANCELFLIPS**](ns-d3dkmddi-dxgkarg_cancelflips.md) structure containing the parameters for this function.

## -returns

**DXGKDDI_CANCELFLIPS** returns an NTSTATUS code such as one of the following:

| Return value | Meaning |
| ------------ | ------- |
| STATUS_SUCCESS         | The routine completed successfully. |
| STATUS_NOT_IMPLEMENTED | The driver does not implement support for this operation. For this return status, the OS will follow up with a call to [**DxgkDdiCancelQueuedFlips**](nc-d3dkmddi-dxgkddi_cancelqueuedflips.md). |

## -remarks

Asynchronously cancelled PresentIds are reported via the [VSync interrupt mechanism](/windows-hardware/drivers/display/hardware-flip-queue#specifying-vsync-interrupt-behavior).

See [Cancelling interlocked flips on multiple planes](/windows-hardware/drivers/display/hardware-flip-queue#cancelling-interlocked-flips-on-multiple-planes) for more information.

## -see-also

[**DXGKARG_CANCELFLIPS**](ns-d3dkmddi-dxgkarg_cancelflips.md)
