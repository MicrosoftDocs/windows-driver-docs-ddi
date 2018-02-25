---
UID: NF:ntddk.IoGetActivityIdIrp
title: IoGetActivityIdIrp function
author: windows-driver-content
description: The IoGetActivityIdIrp routine retrieves the current activity ID associated with an IRP.
old-location: kernel\iogetactivityidirp.htm
old-project: kernel
ms.assetid: FAFF65EF-F1D8-4B54-B281-D5C4AC124E32
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, G, I, IoGetActivityIdIrp, IoGetActivityIdIrp routine [Kernel-Mode Driver Architecture], c, d, e, i, kernel.iogetactivityidirp, ntddk/IoGetActivityIdIrp, o, p, r, t, v, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetActivityIdIrp
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetActivityIdIrp function


## -description


The IoGetActivityIdIrp routine retrieves the current activity ID associated with an IRP.


## -syntax


````
NTSTATUS IoGetActivityIdIrp(
  _In_  PIRP   Irp,
  _Out_ LPGUID Guid
);
````


## -parameters




### -param Irp [in]

The IRP from which to retrieve the activity ID.


### -param Guid [out]

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
 



