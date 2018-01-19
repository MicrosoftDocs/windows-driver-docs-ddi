---
UID: NC:dispmprt.DXGKCB_QUEUE_DPC
title: DXGKCB_QUEUE_DPC
author: windows-driver-content
description: The DxgkCbQueueDpc function queues a deferred procedure call (DPC) for execution at IRQL DISPATCH_LEVEL.
old-location: display\dxgkcbqueuedpc.htm
old-project: display
ms.assetid: c8c26675-8b87-4818-ad51-4e0a341965d0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SYMBOL_INFO_EX, *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbQueueDpc
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: *PSYMBOL_INFO_EX, SYMBOL_INFO_EX
---

# DXGKCB_QUEUE_DPC callback



## -description
The <b>DxgkCbQueueDpc</b> function queues a deferred procedure call (DPC) for execution at IRQL  DISPATCH_LEVEL.



## -prototype

````
DXGKCB_QUEUE_DPC DxgkCbQueueDpc;

BOOLEAN DxgkCbQueueDpc(
  _In_ HANDLE DeviceHandle
)
{ ... }
````


## -parameters

### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.


## -returns
<b>DxgkCbQueueDpc</b> returns <b>TRUE</b> if the DPC is successfully queued; otherwise it returns <b>FALSE</b>.


## -remarks
This function queues a DPC object for the display miniport and calls the <a href="..\dispmprt\nc-dispmprt-dxgkddi_dpc_routine.md">DxgkDdiDpcRoutine</a> function when the interrupt service routine (ISR) requests it. 

There can only be one callback to this function scheduled per device at any one time. If a callback is already scheduled for a device, a second call to <b>DxgkCbQueueDpc</b> will not have any effect and will return <b>FALSE</b>.

For more information on the use of this function, see these topics:


## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_queue_dpc.md">DxgkCbQueueDpc</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_dpc_routine.md">DxgkDdiDpcRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_QUEUE_DPC callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

