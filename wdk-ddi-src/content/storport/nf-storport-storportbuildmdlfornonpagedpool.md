---
UID: NF:storport.StorPortBuildMdlForNonPagedPool
title: StorPortBuildMdlForNonPagedPool function (storport.h)
description: The StorPortBuildMdlForNonPagedPool routine updates the MDL to describe the associated non-paged memory.
old-location: storage\storportbuildmdlfornonpagedpool.htm
tech.root: storage
ms.assetid: f22dbf1e-4b40-4294-bca5-3011f0a97644
ms.date: 03/29/2018
keywords: ["StorPortBuildMdlForNonPagedPool function"]
ms.keywords: StorPortBuildMdlForNonPagedPool, StorPortBuildMdlForNonPagedPool routine [Storage Devices], storage.storportbuildmdlfornonpagedpool, storport/StorPortBuildMdlForNonPagedPool, storprt_98151881-8a9f-4bf9-8365-ec50aecced4f.xml
f1_keywords:
 - "storport/StorPortBuildMdlForNonPagedPool"
 - "StorPortBuildMdlForNonPagedPool"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortBuildMdlForNonPagedPool
targetos: Windows
req.typenames: 
---

# StorPortBuildMdlForNonPagedPool function


## -description


The <b>StorPortBuildMdlForNonPagedPool</b> routine updates the MDL to describe the associated non-paged memory.


## -parameters




### -param HwDeviceExtension 
[in]
A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Mdl 
[in, out]
A pointer to the MDL that specifies the memory buffer.


## -returns



StorPortBuildMdlForNonPagedPool returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the MDL was updated successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer to the MDL is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The call was made at an invalid IRQL. 

</td>
</tr>
</table>
 



