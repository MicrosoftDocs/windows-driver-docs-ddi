---
UID: NF:sercx.SerCxRetrieveTransmitMdl
title: SerCxRetrieveTransmitMdl function
author: windows-driver-content
description: The SerCxRetrieveTransmitMdl method retrieves the MDL that describes the buffer that contains the next block of output data to be transmitted.
old-location: serports\sercxretrievetransmitmdl.htm
old-project: serports
ms.assetid: C0FF3667-9641-4032-826E-7E297F57CDFA
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: 1/SerCxRetrieveTransmitMdl, SerCxRetrieveTransmitMdl, SerCxRetrieveTransmitMdl method [Serial Ports], serports.sercxretrievetransmitmdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	1.0\Sercx.h
api_name:
-	SerCxRetrieveTransmitMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCxRetrieveTransmitMdl function


## -description


The <b>SerCxRetrieveTransmitMdl</b> method retrieves the MDL that describes the buffer that contains the next block of output data to be transmitted.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param Mdl [out]

A pointer to a location into which the method writes a pointer to the MDL.


## -returns



<b>SerCxRetrieveTransmitMdl</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.

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
<li>There is no outstanding transmit request to get an MDL from.</li>
<li>The current number of bytes transmitted (as reported by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406715">SerCxProgressTransmit</a> method) does not equal zero.</li>
<li>The buffer has already been retrieved (and the corresponding call to the <b>SerCxProgressTransmit</b> method has not yet occurred).</li>
<li>The MDL has already been retrieved (and the corresponding call to the <b>SerCxProgressTransmit</b> method has not yet occurred).</li>
</ul>
</td>
</tr>
</table>
 




## -remarks



The serial controller driver calls this function to obtain an MDL to use for the current transmit (write) operation. The MDL describes the buffer memory from which the driver is to obtain the data to be transmitted. The driver is the exclusive owner of this MDL until it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406715">SerCxProgressTransmit</a> method, after which the MDL pointer is invalid and the driver must no longer try to access either the MDL or the buffer memory that the MDL describes.

For more information about MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406715">SerCxProgressTransmit</a>
 

 

