---
UID: NC:usbcamdi.PFNUSBCAMD_BulkReadWrite
title: PFNUSBCAMD_BulkReadWrite
author: windows-driver-content
description: The USBCAMD_BulkReadWrite service performs a read or write operation on the specified bulk pipe.
old-location: stream\usbcamd_bulkreadwrite.htm
old-project: stream
ms.assetid: 4888e6a7-be44-4ed9-80be-9dd7641653ef
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PFNUSBCAMD_BulkReadWrite, USBCAMD_BulkReadWrite, USBCAMD_BulkReadWrite routine [Streaming Media Devices], stream.usbcamd_bulkreadwrite, usbcamdi/USBCAMD_BulkReadWrite, usbcmdpr_6044cfed-1a8c-48a5-ac28-16c8ac151fcc.xml
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
-	USBCAMD_BulkReadWrite
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PFNUSBCAMD_BulkReadWrite callback


## -description


The <b>USBCAMD_BulkReadWrite</b> service performs a read or write operation on the specified bulk pipe.


## -parameters




### -param DeviceContext [in]

Pointer to the camera minidriver's device context.


### -param PipeIndex [in]

Specifies the index of the bulk pipe.


### -param Buffer [in]

Pointer to the read or write buffer. If this parameter is set to <b>NULL</b> for a read request, USBCAMD pulls a data SRB from the SRB read queue of the stream associated with this pipe. Write requests with a <b>NULL</b> buffer pointer are only permitted on the still pin if an SRB_WRITE_DATA request has been submitted to the still pin.


### -param BufferLength [in]

Specifies the length of the read/write buffer in bytes.


### -param CommandComplete [in]

Pointer to a camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a>, which is called when the bulk read or write is completed. This value can be <b>NULL</b>.


### -param CommandContext [in]

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a>.


## -returns



<b>USBCAMD_BulkReadWrite</b> returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

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

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient resources to schedule a transfer.

</td>
</tr>
</table>
 




## -remarks



USBCAMD can accept one read and one write request at a time.

<b>USBCAMD_BulkReadWrite</b> is not available in USBCAMD version 1.0.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568605">USBCAMD_INTERFACE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_BulkReadWrite routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

