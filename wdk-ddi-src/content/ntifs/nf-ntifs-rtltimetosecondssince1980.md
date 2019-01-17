---
UID: NF:ntifs.RtlTimeToSecondsSince1980
title: RtlTimeToSecondsSince1980 function
description: The RtlTimeToSecondsSince1980 routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1980.
old-location: ifsk\rtltimetosecondssince1980.htm
tech.root: ifsk
ms.assetid: 76a0fc34-a3e9-4f97-9c60-e7d179b1e6c3
ms.date: 04/16/2018
ms.keywords: RtlTimeToSecondsSince1980, RtlTimeToSecondsSince1980 routine [Installable File System Drivers], ifsk.rtltimetosecondssince1980, ntifs/RtlTimeToSecondsSince1980, rtlref_14f6e0b0-4291-46ce-aadc-ee8dc169a8cf.xml
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlTimeToSecondsSince1980
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlTimeToSecondsSince1980 function


## -description


The <b>RtlTimeToSecondsSince1980</b> routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1980. 


## -parameters




### -param Time [in]

Pointer to a variable that specifies the system time value to be converted. The approximate valid range for this variable begins at 1980 and ends around 2115. 


### -param ElapsedSeconds [out]

Pointer to a caller-allocated variable that receives the corresponding number of seconds since midnight, December 31, 1979. 


## -returns



<b>RtlTimeToSecondsSince1980</b> returns <b>TRUE</b> if the input <i>Time</i> falls within a range that it can accurately convert to <i>ElapsedSeconds</i>. 




## -remarks



The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The basis for system time is the start of 1601. The value that is processed by <b>RtlTimeToSecondsSince1980</b> is truncated to one-millisecond resolution. 

For more information about converting time values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542994">Data Conversions</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553210">RtlSecondsSince1980ToTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562879">RtlTimeFieldsToTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553241">RtlTimeToSecondsSince1970</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562884">RtlTimeToTimeFields</a>
 

 

