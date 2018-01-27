---
UID: NF:ntifs.CcSetBcbOwnerPointer
title: CcSetBcbOwnerPointer function
author: windows-driver-content
description: The CcSetBcbOwnerPointer routine sets the owner thread pointer for a pinned buffer control block (BCB).
old-location: ifsk\ccsetbcbownerpointer.htm
old-project: ifsk
ms.assetid: fa99ebc4-72d3-42ef-9dda-dcfdd438f66f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcSetBcbOwnerPointer, ccref_9ad1d1a5-0600-4cfa-88d3-e4e5d2cd9df1.xml, ifsk.ccsetbcbownerpointer, CcSetBcbOwnerPointer routine [Installable File System Drivers], ntifs/CcSetBcbOwnerPointer
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
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	CcSetBcbOwnerPointer
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcSetBcbOwnerPointer function


## -description


The <b>CcSetBcbOwnerPointer</b> routine sets the owner thread pointer for a pinned buffer control block (BCB).


## -syntax


````
VOID CcSetBcbOwnerPointer(
  _In_ PVOID Bcb,
  _In_ PVOID OwnerPointer
);
````


## -parameters




### -param Bcb [in]

Pointer to a pinned BCB structure that is owned by the current thread.


### -param OwnerPointer [in]

A valid resource owner pointer, which means a pointer to an allocated system address, with the low-order two bits set. This address may not be deallocated until after the BCB is unpinned by a subsequent call to <a href="..\ntifs\nf-ntifs-ccunpindataforthread.md">CcUnpinDataForThread</a>.


## -returns


None



## -remarks


File systems call <b>CcSetBcbOwnerPointer</b> to set the resource owner for a pinned buffer control block (BCB), in cases where another thread will unpin the BCB and thus the current thread can exit.

Each call to <b>CcSetBcbOwnerPointer</b> must be matched by a subsequent call to <a href="..\ntifs\nf-ntifs-ccunpindataforthread.md">CcUnpinDataForThread</a>, which must be called with the same owner pointer.

BCBs that have been modified by <b>CcSetBcbOwnerPointer</b> cannot be unpinned by calling <a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>.



## -see-also

<a href="..\ntifs\nf-ntifs-ccunpindataforthread.md">CcUnpinDataForThread</a>

<a href="..\wdm\nf-wdm-exsetresourceownerpointer.md">ExSetResourceOwnerPointer</a>

<a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcSetBcbOwnerPointer routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

