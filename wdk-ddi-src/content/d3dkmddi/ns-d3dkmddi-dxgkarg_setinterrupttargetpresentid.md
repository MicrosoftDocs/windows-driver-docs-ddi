---
UID: NS:d3dkmddi._DXGKARG_SETINTERRUPTTARGETPRESENTID
tech.root: display
title: DXGKARG_SETINTERRUPTTARGETPRESENTID
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGKARG_SETINTERRUPTTARGETPRESENTID structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_SETINTERRUPTTARGETPRESENTID
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETINTERRUPTTARGETPRESENTID
 - DXGKARG_SETINTERRUPTTARGETPRESENTID
f1_keywords:
 - _DXGKARG_SETINTERRUPTTARGETPRESENTID
 - d3dkmddi/_DXGKARG_SETINTERRUPTTARGETPRESENTID
 - DXGKARG_SETINTERRUPTTARGETPRESENTID
 - d3dkmddi/DXGKARG_SETINTERRUPTTARGETPRESENTID
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_SETINTERRUPTTARGETPRESENTID
---

## -description

The **DXGKARG_SETINTERRUPTTARGETPRESENTID** structure contains parameters for the driver's [**DXGKDDI_SETINTERRUPTTARGETPRESENTID**](nc-d3dkmddi-dxgkddi_setinterrupttargetpresentid.md) callback function.

## -struct-fields

### -field VidPnSourceId

[in] A **D3DDDI_VIDEO_PRESENT_SOURCE_ID** value that identifies the VidPn source ID of the hardware flip queue.

### -field LayerIndex

[in] A zero-based index value that identifies the MPO plane index of the flip queue.

### -field InterruptTargetPresentId

[in] Value that identifies the PresentId that is required to raise a corresponding VSync or HSync interrupt when it's completed. **InterruptTargetPresentId** can be one of the following values:

| Value | Meaning |
| ----- | ------- |
| UINT64_MAX | No VSync interrupt is required going forward until the target present ID is changed again. |
| 0          | VSync interrupts are required for every interval regardless of whether any new flips are completed. |
| Any other value | Interrupts are raised if the currently scanned PresentId >= **InterruptTargetPresentId**. |

## -remarks

See [Specifying Vsync interrupt behavior](/windows-hardware/drivers/display/hardware-flip-queue#specifying-vsync-interrupt-behavior) for more information.

## -see-also

[**DXGKDDI_SETINTERRUPTTARGETPRESENTID**](nc-d3dkmddi-dxgkddi_setinterrupttargetpresentid.md)
