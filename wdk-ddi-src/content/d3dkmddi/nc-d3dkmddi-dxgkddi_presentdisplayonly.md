---
UID: NC:d3dkmddi.DXGKDDI_PRESENTDISPLAYONLY
title: DXGKDDI_PRESENTDISPLAYONLY
author: windows-driver-content
description: Presents the screen image to the display device of a kernel mode display-only driver (KMDOD).
old-location: display\dxgkddipresentdisplayonly.htm
old-project: display
ms.assetid: b68839e3-ad82-4fcc-8e5a-02dea5db08d9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiPresentDisplayOnly
req.alt-loc: D3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_PRESENTDISPLAYONLY callback



## -description
Presents the screen image to the display device of a kernel mode display-only driver (KMDOD).



## -prototype

````
DXGKDDI_PRESENTDISPLAYONLY DxgkDdiPresentDisplayOnly;

NTSTATUS APIENTRY DxgkDdiPresentDisplayOnly(
  _In_ const HANDLE                      hAdapter,
  _In_ const DXGKARG_PRESENT_DISPLAYONLY *pPresentDisplayOnly
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to the device context for the display adapter. The KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously returned this handle in the <i>MiniportDeviceContext</i> parameter.


### -param pPresentDisplayOnly [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present_displayonly.md">DXGKARG_PRESENT_DISPLAYONLY</a> structure that contains information about the present operation.


## -returns

      Returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
        The present operation completed successfully.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
        The present operation has been sent to the software or hardware queue to complete.

In this case, the KMDOD should use an interrupt and deferred procedure call (DPC) to report progress of the current present operation. Otherwise the operating system uses the <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a> process, which reports an error and requires the KMDOD to reinitialize itself and to reset the GPU.

 Note that this status code should not be returned for synchronous mode, as described in Remarks.

 

The driver can also return any other error status code defined in Ntstatus.h to indicate issues that have occurred with the present operation.


## -remarks
The KMDOD must complete all screen-to-screen moves before copying dirty rectangles. In addition, the KMDOD must complete each move/copy operation before beginning another move/copy operation.

The operating system supports two modes of KMDOD present operations: synchronous and asynchronous. Depending on hardware and driver implementation, the KMDOD can use either mode or switch between them at any time.



When the KMDOD receives a call to <i>DxgkDdiPresentDisplayOnly</i>, it prepares hardware commands, sends them to the hardware, and waits for the commands to complete. When the hardware has completed the present operation, depending on the hardware's status the KMDOD returns <b>STATUS_SUCCESS</b> or any other status code—except that the KMDOD should <i>not</i> return <b>STATUS_PENDING</b>, so that the operating system doesn't erroneously conclude that the present operation is in asynchronous mode.

When the KMDOD receives a call to <i>DxgkDdiPresentDisplayOnly</i>, it prepares hardware commands, sends them to the hardware, and immediately returns <b>STATUS_SUCCESS</b>. Later, when the KMDOD receives the interrupt notification of command completion, it should call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>, <a href="..\dispmprt\nc-dispmprt-dxgkcb_queue_dpc.md">DxgkCbQueueDpc</a>, and <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a> functions to notify the operating system about the progress of the current present operation. See Remarks of the <b>DxgkCbNotifyInterrupt</b> function on how to use these three functions with an interrupt service routine (ISR).

In this case, when the driver calls <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> in an ISR, it should specify the <b>InterruptType</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure as type <b>DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS</b>, and it should fill in the <b>DisplayOnlyPresentProgress</b> member with an appropriate value for the progress.

The operating system guarantees that for each VidPN source there is only one pending present operation.

The operating system guarantees that this function follows the  zero level  synchronization mode as defined in <a href="https://msdn.microsoft.com/2baf91e8-fafb-40e2-a24c-cbf04fe45274">Threading and Synchronization Zero Level</a>.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present_displayonly.md">DXGKARG_PRESENT_DISPLAYONLY</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/8970246b-b46f-464f-93b2-973cc351ed07">DxgkCbPresentDisplayOnlyProgress</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_queue_dpc.md">DxgkCbQueueDpc</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_PRESENTDISPLAYONLY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

