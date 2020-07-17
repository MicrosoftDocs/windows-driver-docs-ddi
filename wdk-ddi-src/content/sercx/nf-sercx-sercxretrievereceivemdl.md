---
UID: NF:sercx.SerCxRetrieveReceiveMdl
title: SerCxRetrieveReceiveMdl function (sercx.h)
description: The SerCxRetrieveReceiveMdl method retrieves the MDL that describes the buffer to use to receive the next block of input data.
old-location: serports\sercxretrievereceivemdl.htm
tech.root: serports
ms.assetid: 7BC76F62-CA51-4C3F-BBF0-0B192EE871E6
ms.date: 04/23/2018
keywords: ["SerCxRetrieveReceiveMdl function"]
ms.keywords: 1/SerCxRetrieveReceiveMdl, SerCxRetrieveReceiveMdl, SerCxRetrieveReceiveMdl method [Serial Ports], serports.sercxretrievereceivemdl
f1_keywords:
 - "sercx/SerCxRetrieveReceiveMdl"
 - "SerCxRetrieveReceiveMdl"
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 1.0\Sercx.h
api_name:
- SerCxRetrieveReceiveMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCxRetrieveReceiveMdl function


## -description


The <b>SerCxRetrieveReceiveMdl</b> method retrieves the MDL that describes the buffer to use to receive the next block of input data.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param Mdl [out]

A pointer to a location into which the method writes a pointer to the MDL.


## -returns



<b>SerCxRetrieveReceiveMdl</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
This value is returned if one of the following occurs:

<ul>
<li>There is no outstanding receive request to get an MDL from.</li>
<li>The current number of bytes received (as reported by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxprogressreceive">SerCxProgressReceive</a> method) does not equal zero.</li>
<li>The buffer has already been retrieved (and the corresponding call to the <b>SerCxProgressReceive</b> method has not yet occurred).</li>
<li>The MDL has already been retrieved (and the corresponding call to the <b>SerCxProgressReceive</b> method has not yet occurred).</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



The serial controller driver calls this function to obtain an MDL to use for the current receive (read) operation. The MDL describes the buffer memory into which the driver is to transfer the received data. The driver is the exclusive owner of this MDL until it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxprogressreceive">SerCxProgressReceive</a> method, after which the MDL pointer is invalid and the driver must no longer try to access either the MDL or the buffer memory that the MDL describes.

For more information about MDLs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxprogressreceive">SerCxProgressReceive</a>
 

 

