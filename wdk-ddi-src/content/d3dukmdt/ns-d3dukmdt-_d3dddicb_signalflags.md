---
UID: NS:d3dukmdt._D3DDDICB_SIGNALFLAGS
title: D3DDDICB_SIGNALFLAGS (d3dukmdt.h)
description: Learn more about the D3DDDICB_SIGNALFLAGS structure.
tech.root: display
ms.date: 03/28/2023
keywords: ["D3DDDICB_SIGNALFLAGS structure"]
ms.keywords: D3DDDICB_SIGNALFLAGS, D3DDDICB_SIGNALFLAGS structure [Display Devices], D3D_other_Structs_3165168a-bcae-409c-8ca2-741675016ba8.xml, _D3DDDICB_SIGNALFLAGS, d3dukmdt/D3DDDICB_SIGNALFLAGS, display.d3dddicb_signalflags
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3DDDICB_SIGNALFLAGS
f1_keywords:
 - _D3DDDICB_SIGNALFLAGS
 - d3dukmdt/_D3DDDICB_SIGNALFLAGS
 - D3DDDICB_SIGNALFLAGS
 - d3dukmdt/D3DDDICB_SIGNALFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDICB_SIGNALFLAGS
 - D3DDDICB_SIGNALFLAGS
---

# D3DDDICB_SIGNALFLAGS structure

## -description

The **D3DDDICB_SIGNALFLAGS** structure describes signaling behavior in a call to the [**pfnSignalSynchronizationObjectCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md) or [**pfnSignalSynchronizationObject2Cb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md) functions.

## -struct-fields

### -field SignalAtSubmission

A UINT value that specifies whether a context should signal synchronization objects when the previously queued packet is submitted rather than completed (which is the default behavior).

Setting this member is equivalent to setting the first bit of the 32-bit  **Value** member (0x00000001).

### -field EnqueueCpuEvent

A UINT value that modifies the behavior of the [**pfnSignalSynchronizationObject2Cb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md) function.

When this member is set:

* The event specified by the **CpuEventHandle** member of the [**D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2**](../d3dumddi/ns-d3dumddi-_d3dddicb_signalsynchronizationobject2.md) structure is signaled when all contexts specified in  **D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2** process the signal command.

* Members of the [**D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2**](../d3dumddi/ns-d3dumddi-_d3dddicb_signalsynchronizationobject2.md) structure that the [**pfnSignalSynchronizationObject2Cb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md) function's **pData** parameter points to are restricted as follows:

  * **ObjectCount** must be zero.
  * **CpuEventHandle** must be a valid event handle.

Setting this member is equivalent to setting the second bit of the 32-bit  **Value** member (0x00000002).

Supported starting with Windows 8.

### -field AllowFenceRewind

A UINT value that indicates whether an intentional fence rewind is allowed. When set TRUE, the fence can be rewound to a queued fence that is behind the current one.

Supported starting with Windows 10 (WDDM 2.0).

### -field DXGK_SIGNAL_FLAG_INTERNAL0

This member is reserved and should be set to zero.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

A member in the union that is contained in **D3DDDICB_SIGNALFLAGS** that can hold one 32-bit value that identifies signaling behavior.

## -see-also

[**D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT**](../d3dumddi/ns-d3dumddi-_d3dddicb_signalsynchronizationobject.md)

[**D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2**](../d3dumddi/ns-d3dumddi-_d3dddicb_signalsynchronizationobject2.md)

[**pfnSignalSynchronizationObject2Cb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md)

[**pfnSignalSynchronizationObjectCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md)
