---
UID: NF:storport.StorPortGetActiveGroupCount
title: StorPortGetActiveGroupCount function
author: windows-driver-content
description: The StorPortGetActiveGroupCount routine returns the number of processor groups that are present in the system.
old-location: storage\storportgetactivegroupcount.htm
tech.root: storage
ms.assetid: 640dd836-a5f9-4a88-b2a3-038a66a50868
ms.date: 03/29/2018
ms.keywords: StorPortGetActiveGroupCount, StorPortGetActiveGroupCount routine [Storage Devices], storage.storportgetactivegroupcount, storport/StorPortGetActiveGroupCount, storprt_d26e001f-a43e-4d7e-9278-9ba48a74574a.xml
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
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortGetActiveGroupCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetActiveGroupCount function


## -description


The <b>StorPortGetActiveGroupCount</b> routine returns the number of processor groups that are present in the system.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param NumberGroups [out]

A pointer to a variable that holds the number of groups.


## -returns



The <b>StorPortGetActiveGroupCount</b> routine returns one of the following status codes:

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
</table>
 



