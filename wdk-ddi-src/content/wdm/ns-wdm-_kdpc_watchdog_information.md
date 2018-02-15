---
UID: NS:wdm._KDPC_WATCHDOG_INFORMATION
title: "_KDPC_WATCHDOG_INFORMATION"
author: windows-driver-content
description: The KDPC_WATCHDOG_INFORMATION structure holds time-out information about the current deferred procedure call (DPC).
old-location: kernel\dpc_watchdog_information.htm
old-project: kernel
ms.assetid: 8b0d3fd8-0952-4cfa-81e1-255145fd27dd
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/PKDPC_WATCHDOG_INFORMATION, PKDPC_WATCHDOG_INFORMATION, kernel.dpc_watchdog_information, KDPC_WATCHDOG_INFORMATION structure [Kernel-Mode Driver Architecture], _KDPC_WATCHDOG_INFORMATION, *PKDPC_WATCHDOG_INFORMATION, KDPC_WATCHDOG_INFORMATION, PKDPC_WATCHDOG_INFORMATION structure pointer [Kernel-Mode Driver Architecture], kstruct_a_22042f11-ce6d-481a-949a-d6370ab442ad.xml, wdm/KDPC_WATCHDOG_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	KDPC_WATCHDOG_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PKDPC_WATCHDOG_INFORMATION, KDPC_WATCHDOG_INFORMATION"
req.product: Windows 10 or later.
---

# _KDPC_WATCHDOG_INFORMATION structure


## -description


The <b>KDPC_WATCHDOG_INFORMATION</b> structure holds time-out information about the current deferred procedure call (DPC). 


## -syntax


````
typedef struct _KDPC_WATCHDOG_INFORMATION {
  ULONG DpcTimeLimit;
  ULONG DpcTimeCount;
  ULONG DpcWatchdogLimit;
  ULONG DpcWatchdogCount;
  ULONG Reserved;
} KDPC_WATCHDOG_INFORMATION, *PKDPC_WATCHDOG_INFORMATION;
````


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

<a href="..\wdm\nf-wdm-kequerydpcwatchdoginformation.md">KeQueryDpcWatchdogInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KDPC_WATCHDOG_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

