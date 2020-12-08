---
UID: NF:ntifs.IoStartTimer
title: IoStartTimer function (ntifs.h)
description: The IoStartTimer routine enables the timer associated with a given device object so the driver-supplied IoTimer routine is called once per second.
old-location: kernel\iostarttimer.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoStartTimer function"]
ms.keywords: IoStartTimer, IoStartTimer routine [Kernel-Mode Driver Architecture], k104_bca7aa97-41e1-48e4-96df-52dd6109cd51.xml, kernel.iostarttimer, wdm/IoStartTimer
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 2000.
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

The <b>IoStartTimer</b> routine enables the timer associated with a given device object so the driver-supplied <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_timer_routine">IoTimer</a> routine is called once per second.

## -parameters

### -param DeviceObject 

[in]
Pointer to a device object whose timer routine is to be called.

## -remarks

The driver must already have set up the IoTimer routine for the <i>DeviceObject</i> by calling <b>IoInitializeTimer</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializetimer">IoInitializeTimer</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostoptimer">IoStopTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_timer_routine">IoTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimer">KeInitializeTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimer">KeSetTimer</a>
