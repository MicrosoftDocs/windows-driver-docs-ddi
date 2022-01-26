---
UID: NF:wdm.RtlTimeFieldsToTime
title: RtlTimeFieldsToTime function (wdm.h)
description: The RtlTimeFieldsToTime routine converts TIME_FIELDS information to a system time value.
old-location: kernel\rtltimefieldstotime.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlTimeFieldsToTime function"]
ms.keywords: RtlTimeFieldsToTime, RtlTimeFieldsToTime routine [Kernel-Mode Driver Architecture], k109_9b5d67de-92c3-4fb7-bcd7-4e045ae9ada4.xml, kernel.rtltimefieldstotime, wdm/RtlTimeFieldsToTime
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlTimeFieldsToTime
 - wdm/RtlTimeFieldsToTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlTimeFieldsToTime
---

# RtlTimeFieldsToTime function

## -description

The <b>RtlTimeFieldsToTime</b> routine converts <b>TIME_FIELDS</b> information to a system time value.

## -parameters

### -param TimeFields [in]

Pointer to a structure of type [**TIME_FIELDS**](./ns-wdm-time_fields.md) that contains the time information to be converted:

### -param Time [out]

Pointer to a buffer, which is to contain the converted system time value as a large integer.

## -returns

<b>RtlTimeFieldsToTime</b> returns <b>TRUE</b> if the input <i>TimeFields</i> data was successfully converted.

## -remarks

<b>RtlTimeFieldsToTime</b> ignores the <b>Weekday</b> value in <i>TimeFields</i>.

Callers of <b>RtlTimeFieldsToTime</b> can be running at any IRQL if both input buffers are resident.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exlocaltimetosystemtime">ExLocalTimeToSystemTime</a>

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime">KeQuerySystemTime</a>

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtltimetotimefields">RtlTimeToTimeFields</a>

[**TIME_FIELDS** structure](./ns-wdm-time_fields.md)
