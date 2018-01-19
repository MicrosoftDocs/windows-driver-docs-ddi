---
UID: NF:ntddk.PsStartSiloMonitor
title: PsStartSiloMonitor function
author: windows-driver-content
description: This routine tries to start the server silo monitor.
old-location: kernel\psstartsilomonitor.htm
old-project: kernel
ms.assetid: 65828926-FDA7-4F65-AD55-B7E03639FA27
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsStartSiloMonitor
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
req.alt-api: PsStartSiloMonitor
req.alt-loc: ntddk.h
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
<dl>
<dt><b>STATUS_REQUEST_ABORTED</b></dt>
</dl>The monitor was not able to start.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The monitor does not allow existing silos and one was found in the system.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

 


## -remarks
