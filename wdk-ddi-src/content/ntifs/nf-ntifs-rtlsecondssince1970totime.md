---
UID: NF:ntifs.RtlSecondsSince1970ToTime
title: RtlSecondsSince1970ToTime function
author: windows-driver-content
description: The RtlSecondsSince1970ToTime routine converts the elapsed time, in seconds, since the beginning of 1970 to an absolute system time value.
old-location: ifsk\rtlsecondssince1970totime.htm
old-project: ifsk
ms.assetid: 8ec961c6-235c-4980-ac4c-60aa496e8a5d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/RtlSecondsSince1970ToTime, ifsk.rtlsecondssince1970totime, RtlSecondsSince1970ToTime routine [Installable File System Drivers], rtlref_ca1b3241-af9f-48e1-86e0-56f94c459c63.xml, RtlSecondsSince1970ToTime
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
-	RtlSecondsSince1970ToTime
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlSecondsSince1970ToTime function


## -description


The <b>RtlSecondsSince1970ToTime</b> routine converts the elapsed time, in seconds, since the beginning of 1970 to an absolute system time value. 


## -syntax


````
VOID RtlSecondsSince1970ToTime(
  _In_  ULONG          ElapsedSeconds,
  _Out_ PLARGE_INTEGER Time
);
````


## -parameters




### -param ElapsedSeconds [in]

Number of seconds from midnight, December 31, 1969, to the current date and time. 


### -param Time [out]

Pointer to a caller-allocated variable that receives the corresponding current system time. 


## -returns


None



## -remarks


The basis for system time is the start of 1601. The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The value returned by <b>RtlSecondsSince1970ToTime</b> is truncated to one-millisecond resolution. 

For more information about converting time values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542994">Data Conversions</a>. 



## -see-also

<a href="..\ntifs\nf-ntifs-rtltimetosecondssince1970.md">RtlTimeToSecondsSince1970</a>

<a href="..\wdm\nf-wdm-rtltimefieldstotime.md">RtlTimeFieldsToTime</a>

<a href="..\wdm\nf-wdm-rtltimetotimefields.md">RtlTimeToTimeFields</a>

<a href="..\ntifs\nf-ntifs-rtlsecondssince1980totime.md">RtlSecondsSince1980ToTime</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSecondsSince1970ToTime routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

