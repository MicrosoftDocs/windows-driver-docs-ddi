---
UID: NF:ntifs.RtlTimeToSecondsSince1980
title: RtlTimeToSecondsSince1980 function (ntifs.h)
description: The RtlTimeToSecondsSince1980 routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1980.
old-location: ifsk\rtltimetosecondssince1980.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlTimeToSecondsSince1980 function"]
ms.keywords: RtlTimeToSecondsSince1980, RtlTimeToSecondsSince1980 routine [Installable File System Drivers], ifsk.rtltimetosecondssince1980, ntifs/RtlTimeToSecondsSince1980, rtlref_14f6e0b0-4291-46ce-aadc-ee8dc169a8cf.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlTimeToSecondsSince1980
 - ntifs/RtlTimeToSecondsSince1980
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlTimeToSecondsSince1980
---

# RtlTimeToSecondsSince1980 function


## -description

The <b>RtlTimeToSecondsSince1980</b> routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1980.

## -parameters

### -param Time 

[in]
Pointer to a variable that specifies the system time value to be converted. The approximate valid range for this variable begins at 1980 and ends around 2115.

### -param ElapsedSeconds 

[out]
Pointer to a caller-allocated variable that receives the corresponding number of seconds since midnight, December 31, 1979.

## -returns

<b>RtlTimeToSecondsSince1980</b> returns <b>TRUE</b> if the input <i>Time</i> falls within a range that it can accurately convert to <i>ElapsedSeconds</i>.

## -remarks

The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The basis for system time is the start of 1601. The value that is processed by <b>RtlTimeToSecondsSince1980</b> is truncated to one-millisecond resolution. 

For more information about converting time values, see <a href="/windows-hardware/drivers/ddi/_kernel/#data-conversions">Data Conversions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsecondssince1980totime">RtlSecondsSince1980ToTime</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtltimefieldstotime">RtlTimeFieldsToTime</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtltimetosecondssince1970">RtlTimeToSecondsSince1970</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtltimetotimefields">RtlTimeToTimeFields</a>
