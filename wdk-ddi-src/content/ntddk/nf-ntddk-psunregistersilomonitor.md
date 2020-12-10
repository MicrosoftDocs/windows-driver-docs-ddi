---
UID: NF:ntddk.PsUnregisterSiloMonitor
title: PsUnregisterSiloMonitor function (ntddk.h)
description: This routine unregisters a server silo monitor.
old-location: kernel\psunregistersilomonitor.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PsUnregisterSiloMonitor function"]
ms.keywords: PsUnregisterSiloMonitor, PsUnregisterSiloMonitor routine [Kernel-Mode Driver Architecture], kernel.psunregistersilomonitor, ntddk/PsUnregisterSiloMonitor
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PsUnregisterSiloMonitor
 - ntddk/PsUnregisterSiloMonitor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsUnregisterSiloMonitor
---

# PsUnregisterSiloMonitor function


## -description

This routine unregisters a server silo monitor.

## -parameters

### -param Monitor 

[in]
The server silo monitor to unregister.

## -remarks

The monitor will not receive further notifications after this routine completes.
    
If the monitor allocated a silo context slot, this routine will not complete until all silo contexts have been removed from slot.

