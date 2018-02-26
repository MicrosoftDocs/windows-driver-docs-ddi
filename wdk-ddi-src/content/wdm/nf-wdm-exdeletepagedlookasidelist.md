---
UID: NF:wdm.ExDeletePagedLookasideList
title: ExDeletePagedLookasideList function
author: windows-driver-content
description: The ExDeletePagedLookasideList routine destroys a paged lookaside list.
old-location: kernel\exdeletepagedlookasidelist.htm
old-project: kernel
ms.assetid: da3784a8-6fc5-47cc-932e-52ec16392e49
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , D, E, ExDeletePagedLookasideList, ExDeletePagedLookasideList routine [Kernel-Mode Driver Architecture], L, P, a, d, e, g, i, k, k102_6e78a15a-e6e1-4282-a8de-a4f38f74ebc6.xml, kernel.exdeletepagedlookasidelist, l, o, s, t, wdm/ExDeletePagedLookasideList, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExDeletePagedLookasideList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExDeletePagedLookasideList function


## -description


The <b>ExDeletePagedLookasideList</b> routine destroys a paged lookaside list.


## -syntax


````
VOID ExDeletePagedLookasideList(
  _Inout_ PPAGED_LOOKASIDE_LIST Lookaside
);
````


## -parameters




### -param Lookaside [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a> structure for the lookaside list, which the caller already initialized with <a href="..\wdm\nf-wdm-exinitializepagedlookasidelist.md">ExInitializePagedLookasideList</a>, which the caller originally set up with <b>ExInitializePagedLookasideList</b>. 


## -returns



None




## -remarks



<b>ExDeletePagedLookasideList</b> is the reciprocal of <b>ExInitializePagedLookasideList</b>. It frees any remaining entries in the specified lookaside list and then removes the list from the system-wide set of active lookaside lists. 

The caller of <b>ExDeletePagedLookasideList</b> is responsible for subsequently releasing the memory that the caller provided to contain the list head.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a>



<a href="..\wdm\nf-wdm-exinitializepagedlookasidelist.md">ExInitializePagedLookasideList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExDeletePagedLookasideList routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

