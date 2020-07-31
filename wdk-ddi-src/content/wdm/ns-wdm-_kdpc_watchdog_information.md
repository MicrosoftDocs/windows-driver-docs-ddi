---
UID: NS:wdm._KDPC_WATCHDOG_INFORMATION
title: _KDPC_WATCHDOG_INFORMATION (wdm.h)
description: The KDPC_WATCHDOG_INFORMATION structure holds time-out information about the current deferred procedure call (DPC).
old-location: kernel\dpc_watchdog_information.htm
tech.root: kernel
ms.assetid: 8b0d3fd8-0952-4cfa-81e1-255145fd27dd
ms.date: 04/30/2018
keywords: ["_KDPC_WATCHDOG_INFORMATION structure"]
ms.keywords: "*PKDPC_WATCHDOG_INFORMATION, KDPC_WATCHDOG_INFORMATION, KDPC_WATCHDOG_INFORMATION structure [Kernel-Mode Driver Architecture], PKDPC_WATCHDOG_INFORMATION, PKDPC_WATCHDOG_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KDPC_WATCHDOG_INFORMATION, kernel.dpc_watchdog_information, kstruct_a_22042f11-ce6d-481a-949a-d6370ab442ad.xml, wdm/KDPC_WATCHDOG_INFORMATION, wdm/PKDPC_WATCHDOG_INFORMATION"
f1_keywords:
 - "wdm/KDPC_WATCHDOG_INFORMATION"
 - "KDPC_WATCHDOG_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- KDPC_WATCHDOG_INFORMATION
targetos: Windows
req.typenames: KDPC_WATCHDOG_INFORMATION, *PKDPC_WATCHDOG_INFORMATION
---

# _KDPC_WATCHDOG_INFORMATION structure


## -description


The <b>KDPC_WATCHDOG_INFORMATION</b> structure holds time-out information about the current deferred procedure call (DPC). 


## -struct-fields




### -field DpcTimeLimit

Time limit for a single, current deferred procedure call. If DPC time-out has been disabled, this value is set to 0.


### -field DpcTimeCount

Time remaining for the current deferred procedure call, if DPC time-out has been enabled.


### -field DpcWatchdogLimit

Total time limit permitted for a sequence of deferred procedure calls. If DPC watchdog has been disabled, this value is set to zero.


### -field DpcWatchdogCount

Time value remaining for the current sequence of deferred procedure calls, if enabled.


### -field Reserved

Reserved for system use.


## -remarks



Time figures stored in each member are dimensionless.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerydpcwatchdoginformation">KeQueryDpcWatchdogInformation</a>
 

 

