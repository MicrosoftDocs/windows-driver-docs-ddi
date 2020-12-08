---
UID: NF:wdm.RtlTimeToTimeFields
title: RtlTimeToTimeFields function (wdm.h)
description: The RtlTimeToTimeFields routine converts system time into a TIME_FIELDS structure.
old-location: kernel\rtltimetotimefields.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlTimeToTimeFields function"]
ms.keywords: RtlTimeToTimeFields, RtlTimeToTimeFields routine [Kernel-Mode Driver Architecture], k109_574f7b2f-cbb5-447c-84d5-88179cbe4cb7.xml, kernel.rtltimetotimefields, wdm/RtlTimeToTimeFields
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: Any level (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlTimeToTimeFields
 - wdm/RtlTimeToTimeFields
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlTimeToTimeFields
---

# RtlTimeToTimeFields function


## -description

The RtlTimeToTimeFields routine converts system time into a <b>TIME_FIELDS</b> structure.

## -parameters

### -param Time 

[in]
Pointer to a buffer containing the absolute system time as a large integer, accurate to 100-nanosecond resolution.

### -param TimeFields 

[out]
Pointer to a caller-allocated buffer, which must be at least <b>sizeof</b>(<b>TIME_FIELDS</b>), to contain the returned information.

## -returns

None

## -remarks

Callers of <b>RtlTimeToTimeFields</b> can be running at any IRQL if both input buffers are resident.

For more info about the **TIME_FIELDS** structure, see [RtlTimeFieldsToTime function](./nf-wdm-rtltimefieldstotime.md).

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exlocaltimetosystemtime">ExLocalTimeToSystemTime</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsystemtimetolocaltime">ExSystemTimeToLocalTime</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerysystemtime">KeQuerySystemTime</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtltimefieldstotime">RtlTimeFieldsToTime</a>
