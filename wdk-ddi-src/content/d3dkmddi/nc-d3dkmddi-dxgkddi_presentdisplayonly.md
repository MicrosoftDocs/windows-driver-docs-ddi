---
UID: NC:d3dkmddi.DXGKDDI_PRESENTDISPLAYONLY
title: DXGKDDI_PRESENTDISPLAYONLY
author: windows-driver-content
description: Presents the screen image to the display device of a kernel mode display-only driver (KMDOD).
old-location: display\dxgkddipresentdisplayonly.htm
old-project: display
ms.assetid: b68839e3-ad82-4fcc-8e5a-02dea5db08d9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_PRESENTDISPLAYONLY, DxgkDdiPresentDisplayOnly, DxgkDdiPresentDisplayOnly callback function [Display Devices], d3dkmddi/DxgkDdiPresentDisplayOnly, display.dxgkddipresentdisplayonly
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkDdiPresentDisplayOnly
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_PRESENTDISPLAYONLY callback


## -description


Presents the screen image to the display device of a kernel mode display-only driver (KMDOD).


## -parameters




### -param hAdapter [in]

A handle to the device context for the display adapter. The KMDOD's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously returned this handle in the <i>MiniportDeviceContext</i> parameter.


### -param pPresentDisplayOnly [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451288">DXGKARG_PRESENT_DISPLAYONLY</a> structure that contains information about the present operation.


## -returns




      Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">

        The present operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">

        The present operation has been sent to the software or hardware queue to complete.

In this case, the KMDOD should use an interrupt and deferred procedure call (DPC) to report progress of the current present operation. Otherwise the operating system uses the <a href="https://msdn.microsoft.com/f410eec7-026f-41e0-8c60-72f651659ead">Timeout Detection and Recovery (TDR)</a> process, which reports an error and requires the KMDOD to reinitialize itself and to reset the GPU.

 Note that this status code should not be returned for synchronous mode, as described in Remarks.

</td>
</tr>
</table>
 

The driver can also return any other error status code defined in Ntstatus.h to indicate issues that have occurred with the present operation.




## -remarks



The KMDOD must complete all screen-to-screen moves before copying dirty rectangles. In addition, the KMDOD must complete each move/copy operation before beginning another move/copy operation.

The operating system supports two modes of KMDOD present operations: synchronous and asynchronous. Depending on hardware and driver implementation, the KMDOD can use either mode or switch between them at any time.



The operating system guarantees that this function follows the  zero level  synchronization mode as defined in <a href="https://msdn.microsoft.com/2baf91e8-fafb-40e2-a24c-cbf04fe45274">Threading and Synchronization Zero Level</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557538">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451288">DXGKARG_PRESENT_DISPLAYONLY</a>



<a href="https://msdn.microsoft.com/3df3f7d4-3721-46f5-b9e3-19bd3d870292">DxgkCbNotifyDpc</a>



<a href="https://msdn.microsoft.com/7968d26d-0195-463d-8954-e7ebef4f9dea">DxgkCbNotifyInterrupt</a>



<a href="https://msdn.microsoft.com/8970246b-b46f-464f-93b2-973cc351ed07">DxgkCbPresentDisplayOnlyProgress</a>



<a href="https://msdn.microsoft.com/c8c26675-8b87-4818-ad51-4e0a341965d0">DxgkCbQueueDpc</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>
 

 

