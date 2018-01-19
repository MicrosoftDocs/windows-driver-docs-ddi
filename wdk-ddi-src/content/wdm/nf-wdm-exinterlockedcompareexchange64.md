---
UID: NF:wdm.ExInterlockedCompareExchange64
title: ExInterlockedCompareExchange64 macro
author: windows-driver-content
description: The ExInterlockedCompareExchange64 routine compares one integer variable to another and, if they are equal, sets the first variable to a caller-supplied value.
old-location: kernel\exinterlockedcompareexchange64.htm
old-project: kernel
ms.assetid: 7d13ca70-e05a-49e0-8dd8-5ab47b4d8169
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExInterlockedCompareExchange64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExInterlockedCompareExchange64
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExInterlockedCompareExchange64 macro



## -description
The <b>ExInterlockedCompareExchange64</b> routine compares one integer variable to another and, if they are equal, sets the first variable to a caller-supplied value.



## -syntax

````
LONGLONG ExInterlockedCompareExchange64(
  _Inout_ PLONGLONG   Destination,
  _In_    PLONGLONG   Exchange,
  _In_    PLONGLONG   Comparand,
  _In_    PKSPIN_LOCK Lock
);
````


## -parameters

### -param Destination [in, out]

A pointer to an integer that will be compared and possibly replaced.


### -param Exchange [in]

A pointer to an integer that will replace the one at <i>Destination</i> if the comparison results in equality.


### -param Comparand [in]

A pointer to an integer with which the value at <i>Destination</i> will be compared. 


### -param Lock [in]

A pointer to a caller-allocated spin-lock that is used if the host system does not support an 8-byte atomic compare-and-exchange operation. 


## -remarks
<b>ExInterlockedCompareExchange64</b> tests and, possibly, replaces the value of a given variable. For most underlying microprocessors, this routine is implemented inline by the compiler to execute as an atomic operation. If a spin lock is used, this routine can only be safely used on nonpaged parameters.

If the <i>Destination</i> and <i>Comparand</i> are unequal, <b>ExInterlockedCompareExchange64</b> simply returns the value of <i>Destination</i>.

<b>ExInterlockedCompareExchange64</b> is atomic only with respect to other <b>(Ex)Interlocked<i>Xxx</i></b> calls. 

Callers of <b>ExInterlockedCompareExchange64</b> can be running at any IRQL. The storage for the <i>Destination</i>, Comparand, and <i>Exchange</i> parameter and the list entries must be resident at all IRQLs.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-interlockedcompareexchange.md">InterlockedCompareExchange</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-interlockedexchange.md">InterlockedExchange</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-interlockedexchangeadd.md">InterlockedExchangeAdd</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedCompareExchange64 routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

