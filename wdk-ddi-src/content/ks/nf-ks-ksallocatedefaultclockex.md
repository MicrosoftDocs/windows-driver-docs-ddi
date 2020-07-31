---
UID: NF:ks.KsAllocateDefaultClockEx
title: KsAllocateDefaultClockEx function (ks.h)
description: The KsAllocateDefaultClockEx function allocates and initializes the default clock structure.
old-location: stream\ksallocatedefaultclockex.htm
tech.root: stream
ms.assetid: cad04f59-5312-4241-9524-aeabc27df92d
ms.date: 04/23/2018
keywords: ["KsAllocateDefaultClockEx function"]
ms.keywords: KsAllocateDefaultClockEx, KsAllocateDefaultClockEx function [Streaming Media Devices], ks/KsAllocateDefaultClockEx, ksfunc_bace76db-468b-4d8e-bbc4-5a64f238308f.xml, stream.ksallocatedefaultclockex
f1_keywords:
 - "ks/KsAllocateDefaultClockEx"
 - "KsAllocateDefaultClockEx"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsAllocateDefaultClockEx
targetos: Windows
req.typenames: 
---

# KsAllocateDefaultClockEx function


## -description


The <b>KsAllocateDefaultClockEx</b> function allocates and initializes the default clock structure. 


## -parameters




### -param DefaultClock [out]

Specifies the caller-allocated shared default clock structure. The current time is set to zero and the state is set to KSSTATE_STOP. Upon successful completion of this routine, the structure indicated by this pointer will contain a reference to the default clock. The data returned should be treated as opaque and reserved for system use.


### -param Context [in, optional]

Optionally contains the context of the alternate time facilities. This must be set if a timer or correlated time function is used.


### -param SetTimer [in, optional]

Optionally contains a pointer to a driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkssettimer">KStrSetTimer</a> function to use to generate DPC timer callbacks based on a Presentation Time. If this is set, the function will be used to set timers based on deltas to the current Presentation Time in order to generate event notifications. If you supply a <i>KStrSetTimer</i> function to set timers, you must also supply a corresponding <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscanceltimer">KStrCancelTimer</a> function. Pass <b>NULL</b> in this parameter if the default <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettimerex">KeSetTimerEx</a> function is to be used to approximate the next notification time. This parameter would normally be set only if a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscorrelatedtime">KStrCorrelatedTime</a> function was also being used. The <i>KStrSetTimer</i> function must have the same characteristics as <b>KeSetTimerEx</b>.


### -param CancelTimer [in, optional]

Optionally contains a pointer to a driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscanceltimer">KStrCancelTimer</a> function to use to cancel outstanding timer callbacks. If you supply a <i>KStrCancelTimer</i> function to cancel timers, you must also supply a corresponding <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkssettimer">KStrSetTimer</a> function. Pass <b>NULL</b> in this parameter if the default <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kecanceltimer">KeCancelTimer</a> function is to be used to cancel timers. The <i>KStrCancelTimer</i> function must have the same characteristics as <b>KeCancelTimer</b>.


### -param CorrelatedTime [in, optional]

Optionally contains a pointer to a driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscorrelatedtime">KStrCorrelatedTime</a> function to retrieve both the Presentation and Physical Time in a correlated manner. This allows the clock owner to completely determine the current time. Pass <b>NULL</b> if the default <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter">KeQueryPerformanceCounter</a> function is to be used to regulate time progression.


### -param Resolution [in, optional]

Optionally contains an alternate Granularity and/or Error factor for the clock. This can only be used only if an alternate timer or correlated time function are being provided. An alternate Granularity may be specified if an alternate correlated time is being used, else the structure element must be zero. An alternate Error may be specified if an alternate timer is being used, else the structure element must be zero.


### -param Flags [in]

Reserved, set to zero.


## -returns



The <b>KsAllocateDefaultClockEx</b> function returns STATUS_SUCCESS if successful, or a memory error if unsuccessful.




## -remarks



The internal DefaultClock.ReferenceCount element is initialized to one by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedefaultclock">KsAllocateDefaultClock</a> function. The element is incremented and decremented as each notification DPC is queued and completed. When the structure is to be freed, the element is used to determine if the owner of the clock should free the structure or if a pending DPC should free it asynchronously. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscanceltimer">KStrCancelTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkscorrelatedtime">KStrCorrelatedTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkssettimer">KStrSetTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksallocatedefaultclock">KsAllocateDefaultClock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfreedefaultclock">KsFreeDefaultClock</a>
 

 

