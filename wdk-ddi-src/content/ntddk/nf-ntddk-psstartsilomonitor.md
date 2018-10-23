---
UID: NF:ntddk.PsStartSiloMonitor
title: PsStartSiloMonitor function
author: windows-driver-content
description: This routine tries to start the server silo monitor.
old-location: kernel\psstartsilomonitor.htm
tech.root: kernel
ms.assetid: 65828926-FDA7-4F65-AD55-B7E03639FA27
ms.date: 04/30/2018
ms.keywords: PsStartSiloMonitor, PsStartSiloMonitor routine [Kernel-Mode Driver Architecture], kernel.psstartsilomonitor, ntddk/PsStartSiloMonitor
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsStartSiloMonitor
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsStartSiloMonitor function


## -description


This routine tries to start the server silo monitor.


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
 



