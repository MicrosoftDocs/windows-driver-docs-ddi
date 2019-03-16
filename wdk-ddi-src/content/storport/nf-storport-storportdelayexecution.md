---
UID: NF:storport.StorPortDelayExecution
title: StorPortDelayExecution function (storport.h)
description: The StorPortDelayExecution function delays the current thread by the given amount of time, in microseconds. If the current IRQL is lower than DISPATCH_LEVEL then the current thread is simply put in the wait state and other threads are allowed to run. Otherwise, this routine performs a busy-wait.
ms.assetid: 77d6e5c0-ff4d-4a2c-8fdf-a89b1c2779b3
ms.date: 10/19/2018
ms.topic: function
ms.keywords: StorPortDelayExecution
req.header: storport.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location: 
- NtosKrnl.exe
api_name: 
- StorPortDelayExecution
product:
- Windows
targetos: Windows

---

# StorPortDelayExecution function


## -description

The **StorPortDelayExecution** function delays the current thread by the given amount of time, in microseconds. If the current IRQL is lower than DISPATCH_LEVEL then the current thread is simply put in the wait state and other threads are allowed to run. Otherwise, this routine performs a busy-wait.

## -parameters

### -param HwDeviceExtension

The miniport's device extension.

### -param DelayInMicroseconds

The delay, in microseconds.

## -returns

This function returns either a STOR_STATUS_SUCCESS or a STOR_STATUS_NOT_IMPLEMENTED.

## -remarks

## -see-also
