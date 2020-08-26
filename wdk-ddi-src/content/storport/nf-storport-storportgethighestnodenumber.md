---
UID: NF:storport.StorPortGetHighestNodeNumber
title: StorPortGetHighestNodeNumber function (storport.h)
description: The StorPortGetHighestNodeNumber routine returns the largest possible node number on the system.
old-location: storage\storportgethighestnodenumber.htm
tech.root: storage
ms.assetid: 3e0b85f9-b6e4-4d53-b8dc-7f51e0f74be3
ms.date: 03/29/2018
keywords: ["StorPortGetHighestNodeNumber function"]
ms.keywords: StorPortGetHighestNodeNumber, StorPortGetHighestNodeNumber routine [Storage Devices], storage.storportgethighestnodenumber, storport/StorPortGetHighestNodeNumber, storprt_e9e942e1-6de3-4170-87ec-00660ce9925a.xml
f1_keywords:
 - "storport/StorPortGetHighestNodeNumber"
 - "StorPortGetHighestNodeNumber"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
- StorPortGetHighestNodeNumber
targetos: Windows
req.typenames: 
---

# StorPortGetHighestNodeNumber function


## -description


The <b>StorPortGetHighestNodeNumber</b> routine returns the largest possible node number on the system.


## -parameters




### -param HwDeviceExtension 
[in]
A pointer to the hardware device extension for the host bus adapter (HBA).


### -param HighestNode 
[out]
A pointer to a variable that holds the highest-numbered node.


## -returns



The <b>StorPortGetHighestNodeNumber</b>routine returns one of the following status codes:

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
The operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>HighestNode</i> is set to <b>NULL</b>.

</td>
</tr>
</table>
 



