---
UID: NF:wdm.ExDeleteLookasideListEx
title: ExDeleteLookasideListEx function
author: windows-driver-content
description: The ExDeleteLookasideListEx routine deletes a lookaside list.
old-location: kernel\exdeletelookasidelistex.htm
old-project: kernel
ms.assetid: b72187de-a2ac-446f-bb06-9ca380454122
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/ExDeleteLookasideListEx, k102_35b6c2b4-58a3-4900-b8dc-63ed0a53b80f.xml, ExDeleteLookasideListEx, ExDeleteLookasideListEx routine [Kernel-Mode Driver Architecture], kernel.exdeletelookasidelistex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExDeleteLookasideListEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExDeleteLookasideListEx function


## -description


The <b>ExDeleteLookasideListEx</b> routine deletes a lookaside list. 


## -syntax


````
VOID ExDeleteLookasideListEx(
  _Inout_ PLOOKASIDE_LIST_EX Lookaside
);
````


## -parameters




### -param Lookaside [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a> structure that describes a lookaside list. This structure was previously initialized by the <a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a> routine. 


## -returns


None



## -remarks


<b>ExDeleteLookasideListEx</b> is the reciprocal of the <b>ExInitializeLookasideListEx</b> routine. It frees any remaining entries in the specified lookaside list and then removes the list from the system-wide set of active lookaside lists.

On return from <b>ExDeleteLookasideListEx</b>, the caller is responsible for releasing, if necessary, the caller-supplied storage for the <b>LOOKASIDE_LIST_EX</b> structure.

For more information about lookaside lists, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554329">LOOKASIDE_LIST_EX</a>

<a href="..\wdm\nf-wdm-exinitializelookasidelistex.md">ExInitializeLookasideListEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExDeleteLookasideListEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

