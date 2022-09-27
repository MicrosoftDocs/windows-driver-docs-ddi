---
UID: NC:d3dkmddi.DXGKCB_SIGNALEVENT
title: DXGKCB_SIGNALEVENT (d3dkmddi.h)
description: Learn more about the DXGKCB_SIGNALEVENT callback function.
ms.date: 09/22/2022
keywords: ["DXGKCB_SIGNALEVENT callback function"]
req.header: d3dkmddi.h
req.include-header: d3dkmddi.h
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809 (WDDM 2.5)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - DXGKCB_SIGNALEVENT
 - d3dkmddi/DXGKCB_SIGNALEVENT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_SIGNALEVENT
dev_langs:
 - c++
---

# DXGKCB_SIGNALEVENT callback function

## -description

**DXGKCB_SIGNALEVENT** signals an event.

## -parameters

### -param unnamedParam1

[in] Pointer to a [**DXGKARGCB_SIGNALEVENT**](ns-d3dkmddi-_dxgkargcb_signalevent.md) structure that contains arguments for this call.

## -returns

**DXGKCB_SIGNALEVENT** returns **STATUS_SUCCESS** if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

The driver must call **DXGKCB_SIGNALEVENT** with the **LastUse** flag during process or device cleanup.

A kernel-mode display miniport driver (KMD) on the host can call **DXGKCB_SIGNALEVENT** to signal an event, which is created on the guest during paravirtualization. This callback can also be used to signal events of the host processes as well.

In the case of paravirtualization, **DXGKCB_SIGNALEVENT** does not signal the event synchronously, so the event is not signaled when the callback returns. Otherwise, the event is signaled synchronously.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_SIGNALEVENT**](ns-d3dkmddi-_dxgkargcb_signalevent.md) and then call **DxgkCbSignalEvent** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_SIGNALEVENT**](ns-d3dkmddi-_dxgkargcb_signalevent.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
