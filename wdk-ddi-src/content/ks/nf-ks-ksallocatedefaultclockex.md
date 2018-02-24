---
UID: NF:ks.KsAllocateDefaultClockEx
title: KsAllocateDefaultClockEx function
author: windows-driver-content
description: The KsAllocateDefaultClockEx function allocates and initializes the default clock structure.
old-location: stream\ksallocatedefaultclockex.htm
old-project: stream
ms.assetid: cad04f59-5312-4241-9524-aeabc27df92d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ksfunc_bace76db-468b-4d8e-bbc4-5a64f238308f.xml, ks/KsAllocateDefaultClockEx, KsAllocateDefaultClockEx, stream.ksallocatedefaultclockex, KsAllocateDefaultClockEx function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsAllocateDefaultClockEx
product: Windows
targetos: Windows
req.typenames: 
---

# KsAllocateDefaultClockEx function


## -description


The <b>KsAllocateDefaultClockEx</b> function allocates and initializes the default clock structure. 


## -syntax


````
NTSTATUS KsAllocateDefaultClockEx(
  _Out_          PKSDEFAULTCLOCK     *DefaultClock,
  _In_opt_       PVOID               Context,
  _In_opt_       PFNKSSETTIMER       SetTimer,
  _In_opt_       PFNKSCANCELTIMER    CancelTimer,
  _In_opt_       PFNKSCORRELATEDTIME CorrelatedTime,
  _In_opt_ const KSRESOLUTION        *Resolution,
  _In_           ULONG               Flags
);
````


## -parameters




### -param DefaultClock [out]

Specifies the caller-allocated shared default clock structure. The current time is set to zero and the state is set to KSSTATE_STOP. Upon successful completion of this routine, the structure indicated by this pointer will contain a reference to the default clock. The data returned should be treated as opaque and reserved for system use.


### -param Context [in, optional]

Optionally contains the context of the alternate time facilities. This must be set if a timer or correlated time function is used.


### -param SetTimer [in, optional]

Optionally contains a pointer to a driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff567203">KStrSetTimer</a> function to use to generate DPC timer callbacks based on a Presentation Time. If this is set, the function will be used to set timers based on deltas to the current Presentation Time in order to generate event notifications. If you supply a <i>KStrSetTimer</i> function to set timers, you must also supply a corresponding <a href="https://msdn.microsoft.com/library/windows/hardware/ff567156">KStrCancelTimer</a> function. Pass <b>NULL</b> in this parameter if the default <a href="..\wdm\nf-wdm-kesettimerex.md">KeSetTimerEx</a> function is to be used to approximate the next notification time. This parameter would normally be set only if a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567167">KStrCorrelatedTime</a> function was also being used. The <i>KStrSetTimer</i> function must have the same characteristics as <b>KeSetTimerEx</b>.


### -param CancelTimer [in, optional]

Optionally contains a pointer to a driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff567156">KStrCancelTimer</a> function to use to cancel outstanding timer callbacks. If you supply a <i>KStrCancelTimer</i> function to cancel timers, you must also supply a corresponding <a href="https://msdn.microsoft.com/library/windows/hardware/ff567203">KStrSetTimer</a> function. Pass <b>NULL</b> in this parameter if the default <a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a> function is to be used to cancel timers. The <i>KStrCancelTimer</i> function must have the same characteristics as <b>KeCancelTimer</b>.


### -param CorrelatedTime [in, optional]

Optionally contains a pointer to a driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff567167">KStrCorrelatedTime</a> function to retrieve both the Presentation and Physical Time in a correlated manner. This allows the clock owner to completely determine the current time. Pass <b>NULL</b> if the default <a href="..\ntifs\nf-ntifs-kequeryperformancecounter.md">KeQueryPerformanceCounter</a> function is to be used to regulate time progression.


### -param Resolution [in, optional]

Optionally contains an alternate Granularity and/or Error factor for the clock. This can only be used only if an alternate timer or correlated time function are being provided. An alternate Granularity may be specified if an alternate correlated time is being used, else the structure element must be zero. An alternate Error may be specified if an alternate timer is being used, else the structure element must be zero.


### -param Flags [in]

Reserved, set to zero.


## -returns



The <b>KsAllocateDefaultClockEx</b> function returns STATUS_SUCCESS if successful, or a memory error if unsuccessful.




## -remarks



The internal DefaultClock.ReferenceCount element is initialized to one by the <a href="..\ks\nf-ks-ksallocatedefaultclock.md">KsAllocateDefaultClock</a> function. The element is incremented and decremented as each notification DPC is queued and completed. When the structure is to be freed, the element is used to determine if the owner of the clock should free the structure or if a pending DPC should free it asynchronously. 




## -see-also

<a href="..\ks\nf-ks-ksfreedefaultclock.md">KsFreeDefaultClock</a>



<a href="..\ks\nf-ks-ksfreedefaultclock.md">KsFreeDefaultClock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567156">KStrCancelTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567156">KStrCancelTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567167">KStrCorrelatedTime</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsAllocateDefaultClockEx function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

