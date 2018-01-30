---
UID: NF:ntddk.PsRegisterSiloMonitor
title: PsRegisterSiloMonitor function
author: windows-driver-content
description: This routine registers a server silo monitor that can receive notifications about server silo events.
old-location: kernel\psregistersilomonitor.htm
old-project: kernel
ms.assetid: C04F29FF-972C-44CC-8557-28C23827ADF0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.psregistersilomonitor, PsRegisterSiloMonitor, ntddk/PsRegisterSiloMonitor, PsRegisterSiloMonitor routine [Kernel-Mode Driver Architecture]
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
-	PsRegisterSiloMonitor
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsRegisterSiloMonitor function


## -description


This routine registers a server silo monitor that can receive notifications about server silo events.


<div class="alert"><b>Note</b>  To start receiving notifications, call the <a href="..\ntddk\nf-ntddk-psstartsilomonitor.md">PsStartSiloMonitor</a> routine.</div>
<div> </div>



## -syntax


````
NTSTATUS PsRegisterSiloMonitor(
  _In_  PSILO_MONITOR_REGISTRATION Registration,
  _Out_ PSILO_MONITOR              *ReturnedMonitor
);
````


## -parameters




### -param Registration [in]

Specifies the server silo monitor to be registered, of type <a href="..\ntddk\ns-ntddk-_silo_monitor_registration.md">SILO_MONITOR_REGISTRATION</a>. 


### -param ReturnedMonitor [out]

Receives a pointer to the monitor. This pointer is used to make further monitor-related calls.


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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The version specified in <b>ntddk.h</b> does not match <b>SILO_MONITOR_REGISTRATION_VERSION</b>, the component name is not specified, or the terminate callback is not supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEDGE_NOT_HELD</b></dt>
</dl>
</td>
<td width="60%">
The routine is called in a silo.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is no memory to register a silo monitor or there is no available silo slot.

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


