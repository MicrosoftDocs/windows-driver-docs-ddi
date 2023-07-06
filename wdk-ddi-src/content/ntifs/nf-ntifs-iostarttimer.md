---
UID: NF:ntifs.IoStartTimer
title: IoStartTimer function (ntifs.h)
description: Learn more about the IoStartTimer routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["IoStartTimer function"]
ms.keywords: IoStartTimer, kernel.iostarttimer, wdm/IoStartTimer
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
 - IoStartTimer
 - ntifs/IoStartTimer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoStartTimer
---

# IoStartTimer function (ntifs.h)

## -description

The **IoStartTimer** routine enables the timer associated with a given device object so the driver-supplied [**IoTimer**](../wdm/nc-wdm-io_timer_routine.md) routine is called once per second.

## -parameters

### -param DeviceObject [in]

Pointer to a device object whose timer routine is to be called.

## -remarks

The driver must already have set up the IoTimer routine for the **DeviceObject** by calling **IoInitializeTimer**.

## -see-also

[**IoInitializeTimer**](../wdm/nf-wdm-ioinitializetimer.md)

[**IoStopTimer**](nf-ntifs-iostoptimer.md)

[**IoTimer**](../wdm/nc-wdm-io_timer_routine.md)

[**KeInitializeDpc**](../wdm/nf-wdm-keinitializedpc.md)

[**KeInitializeTimer**](../wdm/nf-wdm-keinitializetimer.md)

[**KeSetTimer**](../wdm/nf-wdm-kesettimer.md)
