---
UID: NF:ntifs.RtlSecondsSince1970ToTime
title: RtlSecondsSince1970ToTime function (ntifs.h)
description: The RtlSecondsSince1970ToTime routine converts the elapsed time, in seconds, since the beginning of 1970 to an absolute system time value.
old-location: ifsk\rtlsecondssince1970totime.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlSecondsSince1970ToTime function"]
ms.keywords: RtlSecondsSince1970ToTime, RtlSecondsSince1970ToTime routine [Installable File System Drivers], ifsk.rtlsecondssince1970totime, ntifs/RtlSecondsSince1970ToTime, rtlref_ca1b3241-af9f-48e1-86e0-56f94c459c63.xml
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
 - RtlSecondsSince1970ToTime
 - ntifs/RtlSecondsSince1970ToTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlSecondsSince1970ToTime
---

# RtlSecondsSince1970ToTime function


## -description

The <b>RtlSecondsSince1970ToTime</b> routine converts the elapsed time, in seconds, since the beginning of 1970 to an absolute system time value.

## -parameters

### -param ElapsedSeconds [in]


Number of seconds from midnight, December 31, 1969, to the current date and time.

### -param Time [out]


Pointer to a caller-allocated variable that receives the corresponding current system time.

## -returns

None

## -remarks

The basis for system time is the start of 1601. The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The value returned by <b>RtlSecondsSince1970ToTime</b> is truncated to one-millisecond resolution. 

For more information about converting time values, see <a href="/windows-hardware/drivers/ddi/_kernel/#data-conversions">Data Conversions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsecondssince1980totime">RtlSecondsSince1980ToTime</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtltimefieldstotime">RtlTimeFieldsToTime</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtltimetosecondssince1970">RtlTimeToSecondsSince1970</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtltimetotimefields">RtlTimeToTimeFields</a>
