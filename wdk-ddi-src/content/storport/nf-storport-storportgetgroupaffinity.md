---
UID: NF:storport.StorPortGetGroupAffinity
title: StorPortGetGroupAffinity function (storport.h)
description: The StorPortGetGroupAffinity routine constructs a mask of the active processors in a requested group.
old-location: storage\storportgetgroupaffinity.htm
tech.root: storage
ms.assetid: eec0c985-fb59-4190-afb8-5eb62ac1edea
ms.date: 03/29/2018
ms.keywords: StorPortGetGroupAffinity, StorPortGetGroupAffinity routine [Storage Devices], storage.storportgetgroupaffinity, storport/StorPortGetGroupAffinity, storprt_9fdfdc84-3e8f-4227-9799-4ccf08f802df.xml
ms.topic: function
f1_keywords:
 - "storport/StorPortGetGroupAffinity"
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
- StorPortGetGroupAffinity
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetGroupAffinity function


## -description


The <b>StorPortGetGroupAffinity</b> routine constructs a mask of the active processors in a requested group.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param GroupNumber [in]

The group from which to return the processor mask.


### -param GroupAffinityMask [out]

A pointer to a variable that holds the affinity mask of the given group.


## -returns



The <b>StorPortGetGroupAffinity</b> routine returns one of the following status codes:

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
The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>GroupAffinityMask</i> is set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>GroupNumber</i> is set to a value greater than the active group count.

</td>
</tr>
</table>
 



