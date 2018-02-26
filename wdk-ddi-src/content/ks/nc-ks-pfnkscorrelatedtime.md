---
UID: NC:ks.PFNKSCORRELATEDTIME
title: PFNKSCORRELATEDTIME
author: windows-driver-content
description: A streaming minidriver's KStrCorrelatedTime routine is called to retrieve both the presentation time and physical time in a correlated manner. This allows the clock owner to completely determine the current time.
old-location: stream\kstrcorrelatedtime.htm
old-project: stream
ms.assetid: 6f1b2e93-bc3a-4256-af7b-b015a874112b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrCorrelatedTime, KStrCorrelatedTime routine [Streaming Media Devices], PFNKSCORRELATEDTIME, ks/KStrCorrelatedTime, ksfunc_06af0f33-8ffd-4f9e-83ad-9f37f3b18f5d.xml, stream.kstrcorrelatedtime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	KStrCorrelatedTime
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSCORRELATEDTIME callback


## -description


A streaming minidriver's <i>KStrCorrelatedTime</i> routine is called to retrieve both the presentation time and physical time in a correlated manner. This allows the clock owner to completely determine the current time.


## -prototype


````
PFNKSCORRELATEDTIME KStrCorrelatedTime;

LONGLONG FASTCALL KStrCorrelatedTime(
  _In_  PVOID     Context,
  _Out_ PLONGLONG SystemTime
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to the minidriver-supplied information context. The minidriver passes the information context to <a href="..\ks\nf-ks-ksallocatedefaultclockex.md">KsAllocateDefaultClockEx</a> in the function's <i>DeferredContext</i> parameter when the minidriver allocates a custom DPC timer object.


### -param SystemTime [out]

Specifies a pointer to a variable that receives the performance counter frequency.


## -returns



Returns the value of the performance counter in units of ticks.




## -remarks



Typically, if a minidriver supplies a <i>KStrCorrelatedTime</i> callback function, the minidriver must also supply <a href="https://msdn.microsoft.com/library/windows/hardware/ff567203">KStrSetTimer</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567156">KStrCancelTimer</a> callback functions.

The minidriver-supplied <i>KStrCorrelatedTimer </i>must have the same characteristics as <a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>.




## -see-also

<a href="..\wdm\nf-wdm-kequeryperformancecounter.md">KeQueryPerformanceCounter</a>



<a href="..\ks\nf-ks-ksallocatedefaultclockex.md">KsAllocateDefaultClockEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567167">KStrCorrelatedTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567156">KStrCancelTimer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrCorrelatedTime routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

