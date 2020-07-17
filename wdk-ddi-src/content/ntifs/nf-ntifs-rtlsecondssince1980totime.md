---
UID: NF:ntifs.RtlSecondsSince1980ToTime
title: RtlSecondsSince1980ToTime function (ntifs.h)
description: The RtlSecondsSince1980ToTime routine converts the elapsed time, in seconds, since the beginning of 1980 to an absolute system time value.
old-location: ifsk\rtlsecondssince1980totime.htm
tech.root: ifsk
ms.assetid: 2552df19-424e-43ba-9c8d-431123353d4a
ms.date: 04/16/2018
keywords: ["RtlSecondsSince1980ToTime function"]
ms.keywords: RtlSecondsSince1980ToTime, RtlSecondsSince1980ToTime routine [Installable File System Drivers], ifsk.rtlsecondssince1980totime, ntifs/RtlSecondsSince1980ToTime, rtlref_1896255f-11a2-445f-999a-95da533908d8.xml
f1_keywords:
 - "ntifs/RtlSecondsSince1980ToTime"
 - "RtlSecondsSince1980ToTime"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlSecondsSince1980ToTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlSecondsSince1980ToTime function


## -description


The <b>RtlSecondsSince1980ToTime</b> routine converts the elapsed time, in seconds, since the beginning of 1980 to an absolute system time value. 


## -parameters




### -param ElapsedSeconds [in]

Number of seconds from midnight, December 31, 1979, to the current date and time. 


### -param Time [out]

Pointer to a caller-allocated variable that receives the corresponding current system time. 


## -returns



None




## -remarks



The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The basis for system time is the start of 1601. The value returned by <b>RtlSecondsSince1980ToTime</b> is truncated to one-millisecond resolution. 

For more information about converting time values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Data Conversions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlsecondssince1970totime">RtlSecondsSince1970ToTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtltimefieldstotime">RtlTimeFieldsToTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtltimetosecondssince1980">RtlTimeToSecondsSince1980</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtltimetotimefields">RtlTimeToTimeFields</a>
 

 

