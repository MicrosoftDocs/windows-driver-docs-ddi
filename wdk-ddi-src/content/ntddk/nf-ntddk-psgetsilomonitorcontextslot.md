---
UID: NF:ntddk.PsGetSiloMonitorContextSlot
title: PsGetSiloMonitorContextSlot function (ntddk.h)
description: This routine returns the silo context slot that was allocated by the monitor during the registration.
old-location: kernel\psgetsilomonitorcontextslot.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PsGetSiloMonitorContextSlot function"]
ms.keywords: PsGetSiloMonitorContextSlot, PsGetSiloMonitorContextSlot routine [Kernel-Mode Driver Architecture], kernel.psgetsilomonitorcontextslot, ntddk/PsGetSiloMonitorContextSlot
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
 - PsGetSiloMonitorContextSlot
 - ntddk/PsGetSiloMonitorContextSlot
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsGetSiloMonitorContextSlot
---

# PsGetSiloMonitorContextSlot function


## -description

This routine returns the silo context slot that was allocated by the monitor during the registration.

## -parameters

### -param Monitor 

[in]
A pointer to the silo monitor.

## -returns

A valid silo context slot.

