---
UID: NF:ntddk.PsStartSiloMonitor
title: PsStartSiloMonitor function
author: windows-driver-content
description: This routine tries to start the server silo monitor.
old-location: kernel\psstartsilomonitor.htm
old-project: kernel
ms.assetid: 65828926-FDA7-4F65-AD55-B7E03639FA27
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , M, P, PsStartSiloMonitor, PsStartSiloMonitor routine [Kernel-Mode Driver Architecture], S, a, i, kernel.psstartsilomonitor, l, n, ntddk/PsStartSiloMonitor, o, r, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsStartSiloMonitor
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsStartSiloMonitor function


## -description


This routine tries to start the server silo monitor.


## -syntax


````
NTSTATUS PsStartSiloMonitor(
  _In_ PSILO_MONITOR Monitor
);
````


## -parameters




### -param Monitor [in]

A pointer to the silo monitor.


## -returns



The following NT status codes are returned.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_ABORTED</b></dt>
</dl>
</td>
<td width="60%">
The monitor was not able to start.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The monitor does not allow existing silos and one was found in the system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
</table>
 



