---
UID: NF:ntddk.IoGetActivityIdIrp
title: IoGetActivityIdIrp function (ntddk.h)
description: The IoGetActivityIdIrp routine retrieves the current activity ID associated with an IRP.
old-location: kernel\iogetactivityidirp.htm
tech.root: kernel
ms.assetid: FAFF65EF-F1D8-4B54-B281-D5C4AC124E32
ms.date: 04/30/2018
keywords: ["IoGetActivityIdIrp function"]
ms.keywords: IoGetActivityIdIrp, IoGetActivityIdIrp routine [Kernel-Mode Driver Architecture], kernel.iogetactivityidirp, ntddk/IoGetActivityIdIrp
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetActivityIdIrp
 - ntddk/IoGetActivityIdIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetActivityIdIrp
---

# IoGetActivityIdIrp function


## -description

The IoGetActivityIdIrp routine retrieves the current activity ID associated with an IRP.

## -parameters

### -param Irp 

[in]
The IRP from which to retrieve the activity ID.

### -param Guid 

[out]
A pointer to a location  to store the retrieved GUID.

## -returns

IoGetActivityIdIrp returns STATUS_SUCCESS if the call is successful. Possible error return values include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No activity ID is associated with the request.

</td>
</tr>
</table>

