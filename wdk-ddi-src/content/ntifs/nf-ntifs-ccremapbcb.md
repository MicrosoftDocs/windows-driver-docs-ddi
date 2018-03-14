---
UID: NF:ntifs.CcRemapBcb
title: CcRemapBcb function
author: windows-driver-content
description: The CcRemapBcb routine maps a buffer control block (BCB) an additional time to preserve it through several calls that perform additional maps and unpins.
old-location: ifsk\ccremapbcb.htm
old-project: ifsk
ms.assetid: e8855baf-ce75-4a4c-bbbe-d1a7e5a65907
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CcRemapBcb, CcRemapBcb routine [Installable File System Drivers], ccref_64bd8036-ecdd-48bd-8894-fea7f28cc3be.xml, ifsk.ccremapbcb, ntifs/CcRemapBcb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows 2000 and later.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcRemapBcb
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcRemapBcb function


## -description


The <b>CcRemapBcb</b> routine maps a buffer control block (BCB) an additional time to preserve it through several calls that perform additional maps and unpins.


## -syntax


````
PVOID CcRemapBcb(
  _In_ PVOID Bcb
);
````


## -parameters




### -param Bcb [in]

Pointer to the BCB to be remapped.


## -returns



<b>CcRemapBcb</b> returns a pointer to the remapped BCB with a read-only indicator.




## -remarks



Like <a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>, <b>CcRemapBcb</b> maps data in a cached file for read access. Note that after <b>CcRemapBcb</b> is called, the data is mapped; but it is not pinned. This distinction is important. Data that is mapped but not pinned cannot safely be modified. To pin the data, use <a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>, <a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>, or <a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>



<a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>



<a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>



<a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>



<a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>



 

 


