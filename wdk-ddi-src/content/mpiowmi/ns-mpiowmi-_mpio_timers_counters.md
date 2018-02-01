---
UID: NS:mpiowmi._MPIO_TIMERS_COUNTERS
title: "_MPIO_TIMERS_COUNTERS"
author: windows-driver-content
description: The MPIO_TIMERS_COUNTERS structure controls the timer counters that affect all devices whose controlling DSMs do not implement independent timer counter settings.
old-location: storage\mpio_timers_counters.htm
old-project: storage
ms.assetid: edbca8b0-53c1-4538-ac96-52238d75168d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: mpiowmi/PMPIO_TIMERS_COUNTERS, _MPIO_TIMERS_COUNTERS, PMPIO_TIMERS_COUNTERS, mpiowmi/MPIO_TIMERS_COUNTERS, MPIO_TIMERS_COUNTERS structure [Storage Devices], PMPIO_TIMERS_COUNTERS structure pointer [Storage Devices], MPIO_TIMERS_COUNTERS, storage.mpio_timers_counters, *PMPIO_TIMERS_COUNTERS, structs-scsibus_4e4255c8-94e3-4eb0-bf6b-e5c8cddba010.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mpiowmi.h
apiname:
-	MPIO_TIMERS_COUNTERS
product: Windows
targetos: Windows
req.typenames: "*PMPIO_TIMERS_COUNTERS, MPIO_TIMERS_COUNTERS"
---

# _MPIO_TIMERS_COUNTERS structure


## -description


The MPIO_TIMERS_COUNTERS structure controls the timer counters that affect all devices whose controlling DSMs do not implement independent timer counter settings. To query or set the global counters, the request must be directed to the MPIO control object by using its WMI instance name.


## -syntax


````
typedef struct _MPIO_TIMERS_COUNTERS {
  ULONG PathVerifyEnabled;
  ULONG PathVerificationPeriod;
  ULONG PDORemovePeriod;
  ULONG RetryCount;
  ULONG RetryInterval;
} MPIO_TIMERS_COUNTERS, *PMPIO_TIMERS_COUNTERS;
````


## -struct-fields




### -field PathVerifyEnabled

An unsigned 32-bitfield that is used as a flag. This field indicates whether path verification must be performed by MPIO on all paths periodically.


### -field PathVerificationPeriod

An unsigned 32-bitfield that is used to indicate the periodicity (in seconds) with which MPIO has been requested to perform path verification. This field is valid if <i>PathVerifyEnabled</i> is <b>TRUE</b>.


### -field PDORemovePeriod

An unsigned 32-bitfield that controls the amount of time (in seconds) that the pseudo-LUN remains in system memory, even after losing all its path information.


### -field RetryCount

An unsigned 32-bitfield that specifies the number of times a failed I/O can be retried.


### -field RetryInterval

An unsigned 32-bitfield that specifies the interval of time (in seconds) after which a failed request is retried.

