---
UID: NS:storport._STOR_DPC_WATCHDOG_INFORMATION
tech.root: storage
title: STOR_DPC_WATCHDOG_INFORMATION
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_DPC_WATCHDOG_INFORMATION holds time-out information about the current deferred procedure call (DPC).
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_DPC_WATCHDOG_INFORMATION, *PSTOR_DPC_WATCHDOG_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_DPC_WATCHDOG_INFORMATION
 - PSTOR_DPC_WATCHDOG_INFORMATION
 - STOR_DPC_WATCHDOG_INFORMATION
f1_keywords:
 - _STOR_DPC_WATCHDOG_INFORMATION
 - storport/_STOR_DPC_WATCHDOG_INFORMATION
 - PSTOR_DPC_WATCHDOG_INFORMATION
 - storport/PSTOR_DPC_WATCHDOG_INFORMATION
 - STOR_DPC_WATCHDOG_INFORMATION
 - storport/STOR_DPC_WATCHDOG_INFORMATION
dev_langs:
 - c++
---

## -description

**STOR_DPC_WATCHDOG_INFORMATION** holds time-out information about the current deferred procedure call (DPC).

## -struct-fields

### -field DpcTimeLimit

Time limit (in ticks) for a single, current deferred procedure call. If DPC time-out has been disabled, this value is set to 0.

### -field DpcTimeCount

Time remaining (in ticks) for the current deferred procedure call, if DPC time-out has been enabled.

### -field DpcWatchdogLimit

Total time limit permitted for a sequence of deferred procedure calls. If DPC watchdog has been disabled, this value is set to zero.

### -field DpcWatchdogCount

Time value remaining (in ticks) for the current sequence of deferred procedure calls, if enabled.

### -field Reserved

Reserved for system use.

## -see-also

[**StorPortQueryDpcWatchdogInformation**](ns-storport-stor_dpc_watchdog_information.md)
