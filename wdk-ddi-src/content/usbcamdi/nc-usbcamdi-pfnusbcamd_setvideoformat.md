---
UID: NC:usbcamdi.PFNUSBCAMD_SetVideoFormat
title: PFNUSBCAMD_SetVideoFormat (usbcamdi.h)
description: The USBCAMD_SetVideoFormat service is used to notify USBCAMD that the video format has changed.
old-location: stream\usbcamd_setvideoformat.htm
tech.root: stream
ms.assetid: 84a63c69-0f27-42e4-ae10-e394dd8b715d
ms.date: 04/23/2018
ms.keywords: PFNUSBCAMD_SetVideoFormat, USBCAMD_SetVideoFormat, USBCAMD_SetVideoFormat routine [Streaming Media Devices], stream.usbcamd_setvideoformat, usbcamdi/USBCAMD_SetVideoFormat, usbcmdpr_c4209df8-d0e2-4727-b9f8-4b9b734be34c.xml
f1_keywords:
 - "usbcamdi/USBCAMD_SetVideoFormat"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- usbcamdi.h
api_name:
- USBCAMD_SetVideoFormat
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNUSBCAMD_SetVideoFormat callback function


## -description


The <b>USBCAMD_SetVideoFormat</b> service is used to notify USBCAMD that the video format has changed.


## -parameters




### -param DeviceContext [in]

Pointer to device-specific context.


### -param pSrb [in]

Pointer to a stream request block (SRB).


## -returns



<b>USBCAMD_SetVideoFormat</b> returns <b>TRUE</b> if the call was successful, otherwise it returns <b>FALSE</b> and sets <i>pSrb->Status</i> to one of the following error codes:

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
USBCAMD may return STATUS_INVALID_PARAMETER for a number of reasons, including:

Unknown video format

Arithmetic overflow when calculating the video info header size or format size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient resources to allocate the video info header.

</td>
</tr>
</table>
 




## -remarks



Note that this function returns <b>TRUE</b> to indicate success and not STATUS_SUCCESS.

Camera minidrivers must handle all SRBs related to video format. Camera minidrivers should use <b>USBCAMD_SetVideoFormat</b> to inform USBCAMD of a video format change. Typically, the camera minidriver calls <b>USBCAMD_SetVideoFormat</b> from within its SRB_SET_DATA_FORMAT handler.

<b>USBCAMD_SetVideoFormat</b> is not available in USBCAMD version 1.0.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-set-data-format">SRB_SET_DATA_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-usbcamd_interface">USBCAMD_INTERFACE</a>
 

 

