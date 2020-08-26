---
UID: NS:mpiowmi._MPIO_TIMERS_COUNTERS
title: _MPIO_TIMERS_COUNTERS (mpiowmi.h)
description: The MPIO_TIMERS_COUNTERS structure controls the timer counters that affect all devices whose controlling DSMs do not implement independent timer counter settings.
old-location: storage\mpio_timers_counters.htm
tech.root: storage
ms.assetid: edbca8b0-53c1-4538-ac96-52238d75168d
ms.date: 03/29/2018
keywords: ["MPIO_TIMERS_COUNTERS structure"]
ms.keywords: "*PMPIO_TIMERS_COUNTERS, MPIO_TIMERS_COUNTERS, MPIO_TIMERS_COUNTERS structure [Storage Devices], PMPIO_TIMERS_COUNTERS, PMPIO_TIMERS_COUNTERS structure pointer [Storage Devices], _MPIO_TIMERS_COUNTERS, mpiowmi/MPIO_TIMERS_COUNTERS, mpiowmi/PMPIO_TIMERS_COUNTERS, storage.mpio_timers_counters, structs-scsibus_4e4255c8-94e3-4eb0-bf6b-e5c8cddba010.xml"
f1_keywords:
 - "mpiowmi/MPIO_TIMERS_COUNTERS"
 - "MPIO_TIMERS_COUNTERS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mpiowmi.h
api_name:
- MPIO_TIMERS_COUNTERS
targetos: Windows
req.typenames: MPIO_TIMERS_COUNTERS, *PMPIO_TIMERS_COUNTERS
---

# _MPIO_TIMERS_COUNTERS structure


## -description


The MPIO_TIMERS_COUNTERS structure controls the timer counters that affect all devices whose controlling DSMs do not implement independent timer counter settings. To query or set the global counters, the request must be directed to the MPIO control object by using its WMI instance name.


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

