---
UID: NF:ntifs.IoStopTimer
title: IoStopTimer function (ntifs.h)
description: Learn more about the IoStopTimer routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["IoStopTimer function"]
ms.keywords: IoStopTimer, kernel.iostoptimer, wdm/IoStopTimer
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoStopTimer
 - ntifs/IoStopTimer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoStopTimer
---

# IoStopTimer function (ntifs.h)

## -description

The **IoStopTimer** routine disables the timer for a specified device object so the driver-supplied [**IoTimer**](../wdm/nc-wdm-io_timer_routine.md) routine is not called.

## -parameters

### -param DeviceObject [in]

Pointer to the device object with which the [**IoTimer**](../wdm/nc-wdm-io_timer_routine.md) routine is associated.

## -remarks

The driver-supplied [**IoTimer**](../wdm/nc-wdm-io_timer_routine.md) routine can be reenabled with a call to **IoStartTimer**.

Do not call **IoStopTimer** from within the **IoTimer** routine.

## -see-also

[**IoInitializeTimer**](../wdm/nf-wdm-ioinitializetimer.md)

[**IoStartTimer**](nf-ntifs-iostarttimer.md)
