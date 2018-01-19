---
UID: NF:ntifs.CcRemapBcb
title: CcRemapBcb function
author: windows-driver-content
description: The CcRemapBcb routine maps a buffer control block (BCB) an additional time to preserve it through several calls that perform additional maps and unpins.
old-location: ifsk\ccremapbcb.htm
old-project: ifsk
ms.assetid: e8855baf-ce75-4a4c-bbbe-d1a7e5a65907
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcRemapBcb
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
req.alt-api: CcRemapBcb
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
req.irql: 
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
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcRemapBcb routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

