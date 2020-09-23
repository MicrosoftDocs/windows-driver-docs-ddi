---
UID: NS:d3dkmddi._DXGKARG_CONTROLINTERRUPT3
title: DXGKARG_CONTROLINTERRUPT3
ms.date: 03/24/2020
ms.topic: language-reference
ms.assetid: ff1212ad-d42f-4fb4-a9bd-3ce57bf73a98
targetos: Windows
tech.root: display
description: The DXGKARG_CONTROLINTERRUPT3 structure is used in DxgkDdi_ControlInterrupt3 calls to describe the state of interrupts.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_CONTROLINTERRUPT3
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_CONTROLINTERRUPT3
 - DXGKARG_CONTROLINTERRUPT3
f1_keywords:
 - _DXGKARG_CONTROLINTERRUPT3
 - d3dkmddi/_DXGKARG_CONTROLINTERRUPT3
 - DXGKARG_CONTROLINTERRUPT3
 - d3dkmddi/DXGKARG_CONTROLINTERRUPT3
dev_langs:
 - c++
---

## -description

The DXGKARG_CONTROLINTERRUPT3 structure is used in [**DxgkDdi_ControlInterrupt3**](./nc-d3dkmddi-dxgkddi_controlinterrupt3.md) calls to describe the state of interrupts.

## -struct-fields

### -field InterruptType

A [**DXGK_INTERRUPT_TYPE**](./ne-d3dkmddi-_dxgk_interrupt_type.md) enumeration indicating the type of interrupt.

### -field InterruptState

A [**DXGK_INTERRUPT_STATE**](./ne-d3dkmddi-_dxgk_interrupt_state.md) enumeration that indicates whether interrupts are enabled for the driver.

### -field CrtcVsyncState

A [**DXGK_CRTC_VSYNC_STATE**](./ne-d3dkmddi-_dxgk_crtc_vsync_state.md) enumeration that indicates whether VSYNCs are enabled if interrupts are also enabled for the driver.

### -field VidPnSourceId

The unique ID of the VidPnSource on which to control the VSync. This member only applies to VSync interrupts. **VidPnSourceId** can be one of the following values:

| Value | Meaning |
| ----- | ------- |
| 0 to (number of actual VidPnSources-1) | Identifies a particular VidPnSource |
| D3DDDI_ID_ALL | VSync is to be controlled on every VidPnSource of the adapter. The OS will set this value in certain scenarios where it cannot determine the particular VidPnSource to control, or in scenarios such as adapter termination where VSync needs to be disabled globally across all VidPnSources. |

## -remarks

**InterruptState** and **CrtcVsyncState** are members of a union.

## -see-also

[**DXGK_INTERRUPT_STATE**](./ne-d3dkmddi-_dxgk_interrupt_state.md)

[**DXGK_INTERRUPT_TYPE**](./ne-d3dkmddi-_dxgk_interrupt_type.md)

[**DxgkDdi_ControlInterrupt3**](./nc-d3dkmddi-dxgkddi_controlinterrupt3.md)