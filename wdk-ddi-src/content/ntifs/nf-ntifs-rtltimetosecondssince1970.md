---
UID: NF:ntifs.RtlTimeToSecondsSince1970
title: RtlTimeToSecondsSince1970 function
author: windows-driver-content
description: The RtlTimeToSecondsSince1970 routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1970.
old-location: ifsk\rtltimetosecondssince1970.htm
old-project: ifsk
ms.assetid: 9f3e8592-b966-45c4-8931-dd5be0d75740
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlTimeToSecondsSince1970, RtlTimeToSecondsSince1970 routine [Installable File System Drivers], ifsk.rtltimetosecondssince1970, ntifs/RtlTimeToSecondsSince1970, rtlref_62b40f46-c3ee-480d-b671-0c107866f4e7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlTimeToSecondsSince1970
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlTimeToSecondsSince1970 function


## -description


The <b>RtlTimeToSecondsSince1970</b> routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1970. 


## -syntax


````
NTSYSAPIBOOLEAN RtlTimeToSecondsSince1970(
  _In_  PLARGE_INTEGER Time,
  _Out_ PULONG         ElapsedSeconds
);
````


## -parameters




### -param Time [in]

Pointer to a variable that specifies the system time value to be converted. The approximate valid range for this variable begins at 1970 and ends around 2105. 


### -param ElapsedSeconds [out]

Pointer to a caller-allocated variable that receives the corresponding number of seconds since midnight, December 31, 1969. 


## -returns



<b>RtlTimeToSecondsSince1970</b> returns <b>TRUE</b> if the input <i>Time</i> falls within a range that it can accurately convert to <i>ElapsedSeconds</i>. 




## -remarks



The basis for system time is the start of 1601. The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The value processed by <b>RtlTimeToSecondsSince1970</b> is truncated to one-millisecond resolution. 

For more information about converting time values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542994">Data Conversions</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlsecondssince1970totime.md">RtlSecondsSince1970ToTime</a>



<a href="..\wdm\nf-wdm-rtltimetotimefields.md">RtlTimeToTimeFields</a>



<a href="..\wdm\nf-wdm-rtltimefieldstotime.md">RtlTimeFieldsToTime</a>



<a href="..\ntifs\nf-ntifs-rtltimetosecondssince1980.md">RtlTimeToSecondsSince1980</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlTimeToSecondsSince1970 routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

