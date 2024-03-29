---
UID: NS:d3dkmddi._DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
title: DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS (d3dkmddi.h)
description: The DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure indicates whether the display miniport driver provides a physical adapter mask in a call to the DxgkCbNotifyInterrupt function.
old-location: display\dxgkcb_notify_interrupt_data_flags.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure"]
ms.keywords: DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS, DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure [Display Devices], DmStructs_bfff264e-44a2-458c-ab0d-c103d4b76f71.xml, _DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS, d3dkmddi/DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS, display.dxgkcb_notify_interrupt_data_flags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
f1_keywords:
 - _DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
 - d3dkmddi/_DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
 - DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
 - d3dkmddi/DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
 - DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
---

# DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure

## -description

The **DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS** structure indicates whether the display miniport driver provides a physical adapter mask in a call to the [**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md) function.

## -struct-fields

### -field ValidPhysicalAdapterMask

A UINT value that specifies whether the driver provides a physical adapter mask. If this member is set, the driver provides a physical adapter mask in the **PhysicalAdapterMask** member of the **CrtcVsync** structure that is contained in the [**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) structure.

Setting this member is equivalent to setting the first bit of the 32-bit **Value** member (0x00000001).

### -field HsyncFlipCompletion

A UINT value that specifies whether the Hsync flip has been completed.

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit **Value** member to zeros.

### -field Value

The 32-bit value that indicates all of the flags set in the union.

## -see-also

[**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md)

[**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md)
