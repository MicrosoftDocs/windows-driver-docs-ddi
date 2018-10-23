---
UID: NC:usbcamdi.PFNUSBCAMD_SetIsoPipeState
title: PFNUSBCAMD_SetIsoPipeState
author: windows-driver-content
description: The USBCAMD_SetIsoPipeState service permits the camera minidriver to control the streaming state on the isochronous pipe.
old-location: stream\usbcamd_setisopipestate.htm
tech.root: stream
ms.assetid: 6170c69d-f73d-4ba4-b7de-06257c8dd83c
ms.date: 04/23/2018
ms.keywords: PFNUSBCAMD_SetIsoPipeState, USBCAMD_SetIsoPipeState, USBCAMD_SetIsoPipeState routine [Streaming Media Devices], stream.usbcamd_setisopipestate, usbcamdi/USBCAMD_SetIsoPipeState, usbcmdpr_6643c631-6892-4955-8a1f-ae152fd155e4.xml
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
-	USBCAMD_SetIsoPipeState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNUSBCAMD_SetIsoPipeState callback function


## -description


The <b>USBCAMD_SetIsoPipeState</b> service permits the camera minidriver to control the streaming state on the isochronous pipe.


## -parameters




### -param DeviceContext [in]

Pointer to device-specific context.


### -param PipeStateFlags [in]

Specifies the isochronous pipe state. This argument should be set to either of the following values:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USBCAMD_STOP_STREAM

</td>
<td>
This flags indicates to stop streaming.

</td>
</tr>
<tr>
<td>
USBCAMD_START_STREAM

</td>
<td>
This flags indicates to start streaming.

</td>
</tr>
</table>
 


## -returns



<b>USBCAMD_SetIsoPipeState</b> returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The requested pipe state is the same as the current pipe state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The pipe state change is deferred.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient resources to allocate a work item to change the pipe state.

</td>
</tr>
</table>
 




## -remarks



Note that the streaming state on the isochronous pipe works differently from the streaming state in the stream class and in Microsoft DirectShow. It is possible to stop the isochronous pipe from streaming for a short period while the overall video capture graph is still in a Run state.

This function is used to enable dual-mode cameras. In a dual-mode camera, if there is a request to get still data while streaming is in progress, the stream must be stopped on the isochronous pipe. The still call is then serviced and then the isochronous stream must be restarted, all while the overall stream class/DirectShow graph is still in a <b>Run</b> state.

Using this function does not enable you to change the alternate setting within the USB video streaming interface or the channel bandwidth. The isochronous stream must be closed before the alternate setting is changed.

<b>USBCAMD_SetIsoPipeState</b> is not available in USBCAMD version 1.0.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568605">USBCAMD_INTERFACE</a>
 

 

