---
UID: NC:d3dkmddi.DXGKCB_SIGNALEVENT
title: DXGKCB_SIGNALEVENT (d3dkmddi.h)
description: Learn more about the DXGKCB_SIGNALEVENT callback function.
ms.date: 02/06/2025
req.header: d3dkmddi.h
req.include-header: d3dkmddi.h
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809 (WDDM 2.5)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: See Remarks
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

A kernel-mode display driver (KMD) calls **DxgkCbSignalEvent** to signal an event.

## -parameters

### -param unnamedParam1

[in] Pointer to a [**DXGKARGCB_SIGNALEVENT**](ns-d3dkmddi-_dxgkargcb_signalevent.md) structure that contains arguments for this call.

## -returns

**DxgkCbSignalEvent** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

The driver must call **DxgkCbSignalEvent** with the **LastUse** flag during process or device cleanup.

During paravirtualization, KMD on the host can call **DxgkCbSignalEvent** to signal an event created on the guest. **DxgkCbSignalEvent** can also be used to signal events of the host processes as well.

In the case of [paravirtualization](/windows-hardware/drivers/display/gpu-paravirtualization), **DxgkCbSignalEvent** doesn't signal the event synchronously, so the event isn't signaled when the callback returns. Otherwise, the event is signaled synchronously.

The IRQL for **DxgkCbSignalEvent** is:

* <= DISPATCH_LEVEL when signaling events of a process in a virtual machine.
* < DISPATCH_LEVEL when signaling events of a local process.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_SIGNALEVENT**](ns-d3dkmddi-_dxgkargcb_signalevent.md) and then call **DxgkCbSignalEvent** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_SIGNALEVENT**](ns-d3dkmddi-_dxgkargcb_signalevent.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
