---
UID: NC:usbcamdi.PFNUSBCAMD_CancelBulkReadWrite
title: PFNUSBCAMD_CancelBulkReadWrite (usbcamdi.h)
description: The USBCAMD_CancelBulkReadWrite service cancels a pending bulk read or write request.
old-location: stream\usbcamd_cancelbulkreadwrite.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PFNUSBCAMD_CancelBulkReadWrite callback function"]
ms.keywords: PFNUSBCAMD_CancelBulkReadWrite, USBCAMD_CancelBulkReadWrite, USBCAMD_CancelBulkReadWrite routine [Streaming Media Devices], stream.usbcamd_cancelbulkreadwrite, usbcamdi/USBCAMD_CancelBulkReadWrite, usbcmdpr_ba242b77-cda6-4b16-a7a1-297701108cd8.xml
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNUSBCAMD_CancelBulkReadWrite
 - usbcamdi/PFNUSBCAMD_CancelBulkReadWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PFNUSBCAMD_CancelBulkReadWrite
---

# PFNUSBCAMD_CancelBulkReadWrite callback function


## -description

The <b>USBCAMD_CancelBulkReadWrite</b> service cancels a pending bulk read or write request.

## -parameters

### -param DeviceContext 

[in]
Pointer to device-specific context.

### -param PipeIndex 

[in]
Specifies the index of the bulk pipe to cancel the read or write request.

## -returns

<b>USBCAMD_CancelBulkReadWrite</b> returns STATUS_SUCCESS if the call was successful. Other possible error codes include:

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

The value passed in the <i>PipeIndex</i> argument is invalid.

The type of the pipe specified by the <i>PipeIndex</i> argument represents an invalid type of pipe.

The current IRQL >= DISPATCH_LEVEL.

</td>
</tr>
</table>

## -remarks

<b>USBCAMD_CancelBulkReadWrite</b> is not available in USBCAMD version 1.0.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-usbcamd_interface">USBCAMD_INTERFACE</a>

