---
UID: NF:storport.StorPortGetHighestNodeNumber
title: StorPortGetHighestNodeNumber function
author: windows-driver-content
description: The StorPortGetHighestNodeNumber routine returns the largest possible node number on the system.
old-location: storage\storportgethighestnodenumber.htm
old-project: storage
ms.assetid: 3e0b85f9-b6e4-4d53-b8dc-7f51e0f74be3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortGetHighestNodeNumber, storprt_e9e942e1-6de3-4170-87ec-00660ce9925a.xml, storport/StorPortGetHighestNodeNumber, storage.storportgethighestnodenumber, StorPortGetHighestNodeNumber routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	storport.h
apiname: 
-	StorPortGetHighestNodeNumber
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetHighestNodeNumber function


## -description


The <b>StorPortGetHighestNodeNumber</b> routine returns the largest possible node number on the system.


## -syntax


````
ULONG StorPortGetHighestNodeNumber(
  _In_  PVOID  HwDeviceExtension,
  _Out_ PULONG HighestNode
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param HighestNode [out]

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


