---
UID: NF:ntddk.PsUnregisterSiloMonitor
title: PsUnregisterSiloMonitor function
author: windows-driver-content
description: This routine unregisters a server silo monitor.
old-location: kernel\psunregistersilomonitor.htm
old-project: kernel
ms.assetid: B1B85AD5-F626-4177-8218-428B617A97F6
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PsUnregisterSiloMonitor, PsUnregisterSiloMonitor routine [Kernel-Mode Driver Architecture], kernel.psunregistersilomonitor, ntddk/PsUnregisterSiloMonitor
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
-	PsUnregisterSiloMonitor
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsUnregisterSiloMonitor function


## -description


This routine unregisters a server silo monitor.


## -syntax


````
void PsUnregisterSiloMonitor(
  _In_ _Post_invalid_ PSILO_MONITOR Monitor
);
````


## -parameters




### -param Monitor [in]

The server silo monitor to unregister.


## -returns



This routine does not return a value.




## -remarks



The monitor will not receive further notifications after this routine completes.
    
If the monitor allocated a silo context slot, this routine will not complete until all silo contexts have been removed from slot.



