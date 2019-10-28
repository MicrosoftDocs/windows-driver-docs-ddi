---
UID: NF:storport.StorPortGetDataInBufferSystemAddress
title: StorPortGetDataInBufferSystemAddress function (storport.h)
description: Returns the system address for the input data buffer of a SCSI request block (SRB).
old-location: storage\storportgetdatainbuffersystemaddress.htm
tech.root: storage
ms.assetid: 3FA48004-E96A-4ED7-935F-B7F58A74FB1F
ms.date: 03/29/2018
ms.keywords: StorPortGetDataInBufferSystemAddress, StorPortGetDataInBufferSystemAddress routine [Storage Devices], storage.storportgetdatainbuffersystemaddress, storport/StorPortGetDataInBufferSystemAddress
ms.topic: function
f1_keywords:
 - "storport/StorPortGetDataInBufferSystemAddress"
req.header: storport.h
req.include-header: Storport.h
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
req.lib: Storport.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortGetDataInBufferSystemAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetDataInBufferSystemAddress function


## -description


Returns the system address for the input data buffer  of a SCSI request block (SRB).


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

The request block to containing the input data buffer.


### -param SystemAddress [out]

A pointer to  a an  address  value to receive the system address for the input data buffer in <i>Srb</i>.


## -returns



A status value indicating the result of the notification. This can be one of these values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
A system address of the input data buffer for <i>Srb</i> was successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer value in <i>SystemAddress</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The current IRQL is > DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A system address can not be assigned.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetdatainbuffermdl">StorPortGetDataInBufferMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportgetdatainbufferscattergatherlist">StorPortGetDataInBufferScatterGatherList</a>
 

 

