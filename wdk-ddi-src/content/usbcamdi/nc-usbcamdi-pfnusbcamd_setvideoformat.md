---
UID: NC:usbcamdi.PFNUSBCAMD_SetVideoFormat
title: PFNUSBCAMD_SetVideoFormat
author: windows-driver-content
description: The USBCAMD_SetVideoFormat service is used to notify USBCAMD that the video format has changed.
old-location: stream\usbcamd_setvideoformat.htm
old-project: stream
ms.assetid: 84a63c69-0f27-42e4-ae10-e394dd8b715d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.usbcamd_setvideoformat, USBCAMD_SetVideoFormat routine [Streaming Media Devices], USBCAMD_SetVideoFormat, PFNUSBCAMD_SetVideoFormat, PFNUSBCAMD_SetVideoFormat, usbcamdi/USBCAMD_SetVideoFormat, usbcmdpr_c4209df8-d0e2-4727-b9f8-4b9b734be34c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbcamdi.h
apiname:
-	USBCAMD_SetVideoFormat
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PFNUSBCAMD_SetVideoFormat callback


## -description


The <b>USBCAMD_SetVideoFormat</b> service is used to notify USBCAMD that the video format has changed.


## -prototype


````
PFNUSBCAMD_SetVideoFormat USBCAMD_SetVideoFormat;

NTSTATUS APIENTRY USBCAMD_SetVideoFormat(
  _In_ PVOID                    DeviceContext,
  _In_ PHW_STREAM_REQUEST_BLOCK pSrb
)
{ ... }
````


## -parameters




### -param DeviceContext [in]

Pointer to device-specific context.


### -param pSrb [in]

Pointer to a stream request block (SRB).


## -returns



<b>USBCAMD_SetVideoFormat</b> returns <b>TRUE</b> if the call was successful, otherwise it returns <b>FALSE</b> and sets <i>pSrb-&gt;Status</i> to one of the following error codes:

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

<a href="..\usbcamdi\ns-usbcamdi-usbcamd_interface.md">USBCAMD_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568201">SRB_SET_DATA_FORMAT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_SetVideoFormat routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

