---
UID: NF:storport.StorPortQueryTimerMinInterval
tech.root: storage
title: StorPortQueryTimerMinInterval
ms.date: 05/13/2021
targetos: Windows
description: StorPortQueryTimerMinInterval queries the minimum timer resolution that is supported by the system clock.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortQueryTimerMinInterval
f1_keywords:
 - StorPortQueryTimerMinInterval
 - storport/StorPortQueryTimerMinInterval
dev_langs:
 - c++
---

## -description

**StorPortQueryTimerMinInterval** queries the minimum timer resolution that is supported by the system clock.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the miniport's device extension.

### -param TimerMinInterval [out]

Pointer to a ULONG in which this function writes the minimum time interval, in 100-nanosecond units, between successive ticks of the system clock.

## -returns

This function returns one of the following status codes.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The timer minimum interval was successfully queried. |
| STOR_STATUS_INVALID_PARAMETER | A parameter is invalid. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal system reasons. |

## -remarks

A miniport can call this function to query the minimum timer resolution that is supported by the system clock, which can be helpful for implementing I/O polling.
