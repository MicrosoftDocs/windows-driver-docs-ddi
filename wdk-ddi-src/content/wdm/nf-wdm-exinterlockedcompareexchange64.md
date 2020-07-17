---
UID: NF:wdm.ExInterlockedCompareExchange64
title: ExInterlockedCompareExchange64 macro (wdm.h)
description: The ExInterlockedCompareExchange64 routine compares one integer variable to another and, if they are equal, sets the first variable to a caller-supplied value.
old-location: kernel\exinterlockedcompareexchange64.htm
tech.root: kernel
ms.assetid: 7d13ca70-e05a-49e0-8dd8-5ab47b4d8169
ms.date: 04/30/2018
keywords: ["ExInterlockedCompareExchange64 macro"]
ms.keywords: ExInterlockedCompareExchange64, ExInterlockedCompareExchange64 routine [Kernel-Mode Driver Architecture], k102_424c24f9-3965-40fd-b02b-f9bf1f7df4ec.xml, kernel.exinterlockedcompareexchange64, wdm/ExInterlockedCompareExchange64
f1_keywords:
 - "wdm/ExInterlockedCompareExchange64"
 - "ExInterlockedCompareExchange64"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExInterlockedCompareExchange64
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExInterlockedCompareExchange64 macro


## -description


The <b>ExInterlockedCompareExchange64</b> routine compares one integer variable to another and, if they are equal, sets the first variable to a caller-supplied value.


## -parameters




### -param Destination [in, out]

A pointer to an integer that will be compared and possibly replaced.


### -param Exchange [in]

A pointer to an integer that will replace the one at <i>Destination</i> if the comparison results in equality.


### -param Comperand

A pointer to an integer with which the value at <i>Destination</i> will be compared. 


### -param Lock [in]

A pointer to a caller-allocated spin-lock that is used if the host system does not support an 8-byte atomic compare-and-exchange operation. 



## -remarks

This macro wraps **InterlockedCompareExchange64** or **ExfInterlockedCompareExchange64** and assumes the return value of the type LONGLONG.


<b>ExInterlockedCompareExchange64</b> tests and, possibly, replaces the value of a given variable. For most underlying microprocessors, this routine is implemented inline by the compiler to execute as an atomic operation. If a spin lock is used, this routine can only be safely used on nonpaged parameters.

If the <i>Destination</i> and <i>Comparand</i> are unequal, <b>ExInterlockedCompareExchange64</b> simply returns the value of <i>Destination</i>.

<b>ExInterlockedCompareExchange64</b> is atomic only with respect to other <b>(Ex)Interlocked<i>Xxx</i></b> calls. 

Callers of <b>ExInterlockedCompareExchange64</b> can be running at any IRQL. The storage for the <i>Destination</i>, Comparand, and <i>Exchange</i> parameter and the list entries must be resident at all IRQLs.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedcompareexchange">InterlockedCompareExchange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedexchange">InterlockedExchange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-interlockedexchangeadd">InterlockedExchangeAdd</a>
 

 

