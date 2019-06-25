---
UID: NF:ntifs.RtlTimeToSecondsSince1970
title: RtlTimeToSecondsSince1970 function (ntifs.h)
description: The RtlTimeToSecondsSince1970 routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1970.
old-location: ifsk\rtltimetosecondssince1970.htm
tech.root: ifsk
ms.assetid: 9f3e8592-b966-45c4-8931-dd5be0d75740
ms.date: 04/16/2018
ms.keywords: RtlTimeToSecondsSince1970, RtlTimeToSecondsSince1970 routine [Installable File System Drivers], ifsk.rtltimetosecondssince1970, ntifs/RtlTimeToSecondsSince1970, rtlref_62b40f46-c3ee-480d-b671-0c107866f4e7.xml
ms.topic: function
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlTimeToSecondsSince1970
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlTimeToSecondsSince1970 function


## -description


The <b>RtlTimeToSecondsSince1970</b> routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1970. 


## -parameters




### -param Time [in]

Pointer to a variable that specifies the system time value to be converted. The approximate valid range for this variable begins at 1970 and ends around 2105. 


### -param ElapsedSeconds [out]

Pointer to a caller-allocated variable that receives the corresponding number of seconds since midnight, December 31, 1969. 


## -returns



<b>RtlTimeToSecondsSince1970</b> returns <b>TRUE</b> if the input <i>Time</i> falls within a range that it can accurately convert to <i>ElapsedSeconds</i>. 




## -remarks



The basis for system time is the start of 1601. The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The value processed by <b>RtlTimeToSecondsSince1970</b> is truncated to one-millisecond resolution. 

For more information about converting time values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Data Conversions</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtlsecondssince1970totime">RtlSecondsSince1970ToTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtltimefieldstotime">RtlTimeFieldsToTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-rtltimetosecondssince1980">RtlTimeToSecondsSince1980</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtltimetotimefields">RtlTimeToTimeFields</a>
 

 

