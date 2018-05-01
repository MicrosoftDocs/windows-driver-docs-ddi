---
UID: NC:usbcamdi.PFNUSBCAMD_WaitOnDeviceEvent
title: PFNUSBCAMD_WaitOnDeviceEvent
author: windows-driver-content
description: The USBCAMD_WaitOnDeviceEvent service is used to perform a read from the interrupt pipe if the camera has an interrupt pipe for external event notifications.
old-location: stream\usbcamd_waitondeviceevent.htm
old-project: stream
ms.assetid: b9767479-3ad9-4b47-82d1-70b54329e7b8
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: PFNUSBCAMD_WaitOnDeviceEvent, USBCAMD_WaitOnDeviceEvent, USBCAMD_WaitOnDeviceEvent routine [Streaming Media Devices], stream.usbcamd_waitondeviceevent, usbcamdi/USBCAMD_WaitOnDeviceEvent, usbcmdpr_854c2d35-c023-4d7a-8c2e-3e56d3150e41.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbcamdi.h
api_name:
-	USBCAMD_WaitOnDeviceEvent
product: Windows
targetos: Windows
req.typenames: 
---

# PFNUSBCAMD_WaitOnDeviceEvent callback function


## -description


The <b>USBCAMD_WaitOnDeviceEvent</b> service is used to perform a read from the interrupt pipe if the camera has an interrupt pipe for external event notifications.


## -parameters




### -param DeviceContext [in]

A pointer to device-specific context.


### -param PipeIndex [in]

Specifies the index of the interrupt pipe.


### -param Buffer [in]

A pointer to the read buffer.


### -param BufferLength [in]

Length of the read buffer, in bytes.


### -param EventComplete [in]

Pointer to a camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a>, which is called when the interrupt read is completed This value can be <b>NULL</b>.


### -param EventContext [in]

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a>.


### -param LoopBack [in]

Specifies if USBCAMD is to resubmit another read request to the interrupt pipe every time an interrupt read is completed. Set to <b>TRUE</b>


## -returns



<b>USBCAMD_WaitOnDeviceEvent</b> returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_CLOSED</b></dt>
</dl>
</td>
<td width="60%">
The device has been removed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
USBCAMD may return STATUS_INVALID_PARAMETER for a number of reasons, including:

The value passed in the <i>PipeIndex</i> argument is invalid.

The type of the pipe specified by the <i>PipeIndex</i> argument represents an invalid type of pipe.

A bulk read/write request already exists.

The <i>Buffer</i> argument is <b>NULL</b>.

The length specified in the BufferLength argument is smaller than the maximum packet size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The event work item is deferred.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient resources to allocate a work item to read from the pipe.

</td>
</tr>
</table>
 




## -remarks



The typical usage scenario for this function is a camera with a snapshot button and an interrupt pipe associated with the button. When a user presses the snapshot button, the read request on the interrupt pipe is satisfied and the camera minidriver is called back. If the camera minidriver sets USBCAMD_CamControlFlag_EnableDeviceEvents in the <i>CamControlFlag</i> argument during the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568599">USBCAMD_InitializeNewInterface</a> call, the STI monitor also is notified of the snapshot event.

<b>USBCAMD_WaitOnDeviceEvent</b> is not available in USBCAMD version 1.0.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568605">USBCAMD_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568599">USBCAMD_InitializeNewInterface</a>
 

 

