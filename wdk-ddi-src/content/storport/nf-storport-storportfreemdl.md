---
UID: NF:storport.StorPortFreeMdl
title: StorPortFreeMdl function (storport.h)
description: The StorPortFreeMdl routine frees a memory descriptor list (MDL) describing non-paged pool memory.
old-location: storage\storportfreemdl.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortFreeMdl function"]
ms.keywords: StorPortFreeMdl, StorPortFreeMdl routine [Storage Devices], storage.storportfreemdl, storport/StorPortFreeMdl, storprt_c7f2c49d-a04e-428c-8c94-4ba20526a1fe.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortFreeMdl
 - storport/StorPortFreeMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortFreeMdl
---

# StorPortFreeMdl function


## -description

The <b>StorPortFreeMdl</b> routine frees a memory descriptor list (MDL) describing non-paged pool memory.

## -parameters

### -param HwDeviceExtension [in]


A pointer to the hardware device extension for the host bus adapter (HBA).

### -param Mdl [in]


A pointer to the MDL to be freed.

## -returns

StorPortFreeMdl returns one of the following status codes:

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
Indicates that the MDL was freed successfully.

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

## -remarks

A miniport driver calls the <b>StorPortFreeMdl</b> routine to free the MDL that was allocated in a previous call to <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportallocatemdl">StorPortAllocateMdl</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportallocatemdl">StorPortAllocateMdl</a>
