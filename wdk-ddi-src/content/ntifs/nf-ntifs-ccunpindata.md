---
UID: NF:ntifs.CcUnpinData
title: CcUnpinData function
author: windows-driver-content
description: The CcUnpinData routine releases cached file data that was mapped or pinned by an earlier call to CcMapData, CcPinRead, or CcPreparePinWrite.
old-location: ifsk\ccunpindata.htm
old-project: ifsk
ms.assetid: a06bbe25-9841-4aeb-9d51-257dd1472027
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.ccunpindata, ntifs/CcUnpinData, CcUnpinData, CcUnpinData routine [Installable File System Drivers], ccref_ba560a38-4d3b-409f-b1ea-19c3a117615e.xml
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
-	CcUnpinData
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcUnpinData function


## -description


The <b>CcUnpinData</b> routine releases cached file data that was mapped or pinned by an earlier call to <a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>, <a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>, or <a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>.


## -syntax


````
VOID CcUnpinData(
  _In_ PVOID Bcb
);
````


## -parameters




### -param Bcb [in]

Pointer to a buffer control block (BCB) for the data to be released.


## -returns


None



## -remarks


<b>CcUnpinData</b> frees the BCB and performs any other necessary cleanup.

Every successful call to <a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>, <a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>, or <a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a> must be matched by a subsequent call to <b>CcUnpinData</b>. 

BCBs that have been modified by <a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a> cannot be unpinned by calling <b>CcUnpinData</b>. <a href="..\ntifs\nf-ntifs-ccunpindataforthread.md">CcUnpinDataForThread</a> must be called instead.



## -see-also

<a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>

<a href="..\ntifs\nf-ntifs-ccsetbcbownerpointer.md">CcSetBcbOwnerPointer</a>

<a href="..\ntifs\nf-ntifs-ccunpindataforthread.md">CcUnpinDataForThread</a>

<a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>

<a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcUnpinData routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

