---
UID: NS:d3dkmddi._DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS
title: DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS (d3dkmddi.h)
description: Learn more about the DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure.
ms.date: 03/28/2024
keywords: ["DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure"]
req.header: d3dkmddi.h
req.construct-type: structure
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

# DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS structure (d3dkmddi.h)



## -description

The **DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS** structure indicates whether the display miniport driver provides a physical adapter mask in a call to the [**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md) function.

## -struct-fields

### -field ValidPhysicalAdapterMask

Specifies whether the driver provides a physical adapter mask. If this member is set, the driver provides a physical adapter mask in the **PhysicalAdapterMask** member of the **CrtcVsync** structure that is contained in the [**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) structure.

Setting this member is equivalent to setting the first bit of the 32-bit **Value** member (0x00000001).

### -field HsyncFlipCompletion

Specifies whether the Hsync flip has been completed.

### -field EvaluateLegacyMonitoredFences

When set, indicates to the OS to scan all waiters (legacy monitored fence waiter & native fence waiters). For more information, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects). Available starting with Windows 11, version 22H2 (WDDM 3.2).

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

An alternative way to access to bit fields of this structure.

## -see-also

[**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md)

[**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md)
