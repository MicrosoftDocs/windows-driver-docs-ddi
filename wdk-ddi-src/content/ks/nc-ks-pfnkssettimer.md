---
UID: NC:ks.PFNKSSETTIMER
title: PFNKSSETTIMER
author: windows-driver-content
description: A streaming minidriver's KStrSetTimer routine is called to generate DPC timer callbacks based on presentation time.
old-location: stream\kstrsettimer.htm
old-project: stream
ms.assetid: c9150c02-a53e-4ffc-8cf1-ca668680cdd9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KStrSetTimer, KStrSetTimer routine [Streaming Media Devices], PFNKSSETTIMER, ks/KStrSetTimer, ksfunc_a1a590b8-ea16-45bd-8517-45e4bfc46ad3.xml, stream.kstrsettimer
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
-	KStrSetTimer
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSSETTIMER callback


## -description


A streaming minidriver's <i>KStrSetTimer</i> routine is called to generate DPC timer callbacks based on presentation time.


## -prototype


````
PFNKSSETTIMER KStrSetTimer;

BOOLEAN KStrSetTimer(
  _In_ PVOID         Context,
  _In_ PKTIMER       Timer,
  _In_ LARGE_INTEGER DueTime,
  _In_ PKDPC         Dpc
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to the minidriver-supplied information context. The minidriver passes the information context to <a href="..\ks\nf-ks-ksallocatedefaultclockex.md">KsAllocateDefaultClockEx</a> in the function's <i>DeferredContext</i> parameter when the minidriver allocates a custom DPC timer object.


### -param Timer [in]

Pointer to a timer object allocated by the minidriver.


### -param DueTime [in]

Specifies the absolute or relative time at which the timer is to expire. If the value of the <i>DueTime</i> parameter is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units (100-nanosecond intervals). Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.


### -param Dpc [in]

Pointer to a DPC object that the minidriver initialized using <a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>. This parameter is optional.


## -returns



Returns <b>TRUE</b> if the timer object was already in the system timer queue. Otherwise, returns <b>FALSE</b>.




## -remarks



Minidrivers can optionally supply a <i>KStrSetTimer</i> callback function as an argument to <a href="..\ks\nf-ks-ksallocatedefaultclockex.md">KsAllocateDefaultClockEx</a>.

Typically, if a minidriver supplies a <i>KStrCorrelatedTime</i> callback function, then the minidriver also supplies a <i>KStrSetTimer</i> callback function.

If minidrivers supply a <i>KStrSetTimer</i> callback function, the function must set timers, based on deltas, to the current presentation time in order to generate event notifications.

If a minidriver supplies a <i>KStrSetTimer</i> callback function, the minidriver must also supply a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567156">KStrCancelTimer</a> callback function to cancel the timer.

The minidriver supplied <i>KStrSetTimer</i> must have the same characteristics as <a href="..\wdm\nf-wdm-kesettimerex.md">KeSetTimerEx</a>.




## -see-also

<a href="..\ks\nf-ks-ksallocatedefaultclockex.md">KsAllocateDefaultClockEx</a>



<a href="..\wdm\nf-wdm-kesettimerex.md">KeSetTimerEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567156">KStrCancelTimer</a>



<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrSetTimer routine%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

