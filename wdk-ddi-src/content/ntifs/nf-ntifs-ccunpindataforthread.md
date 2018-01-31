---
UID: NF:ntifs.CcUnpinDataForThread
title: CcUnpinDataForThread function
author: windows-driver-content
description: The CcUnpinDataForThread routine releases pages of a cached file whose buffer control block (BCB) was modified by an earlier call to CcSetBcbOwnerPointer.
old-location: ifsk\ccunpindataforthread.htm
old-project: ifsk
ms.assetid: 9c29689c-ce5e-4b29-a17b-32d96f8f87e7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/CcUnpinDataForThread, CcUnpinDataForThread, ifsk.ccunpindataforthread, CcUnpinDataForThread routine [Installable File System Drivers], ccref_71102887-ef3b-44b1-8b1f-e2b07dea3392.xml
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcUnpinDataForThread
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcUnpinDataForThread function


## -description


The <b>CcUnpinDataForThread</b> routine releases pages of a cached file whose buffer control block (BCB) was modified by an earlier call to <a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a>.


## -syntax


````
VOID CcUnpinDataForThread(
  _In_ PVOID            Bcb,
  _In_ ERESOURCE_THREAD ResourceThreadId
);
````


## -parameters




#### - Bcb [in]

Pointer to the BCB for the pages to be released.


#### - ResourceThreadId [in]

Identifies the thread that originally acquired the BCB. Must match the owner pointer used in the call to <a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a>.


## -returns


None



## -remarks


<b>CcUnpinDataForThread</b> releases the BCB for the indicated thread and performs any other necessary cleanup.

Each call to <a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a> must be matched by a subsequent call to <b>CcUnpinDataForThread</b>.

<b>CcUnpinDataForThread</b> is functionally equivalent to <a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>, except that it also releases the BCB resource for the indicated thread.



## -see-also

<a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>

<a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcUnpinDataForThread routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

