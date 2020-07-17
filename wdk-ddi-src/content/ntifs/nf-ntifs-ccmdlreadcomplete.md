---
UID: NF:ntifs.CcMdlReadComplete
title: CcMdlReadComplete function (ntifs.h)
description: The CcMdlReadComplete routine frees the memory descriptor lists (MDL) created by CcMdlRead for a cached file.
old-location: ifsk\ccmdlreadcomplete.htm
tech.root: ifsk
ms.assetid: c1525604-3aee-464d-a7f5-a6a4739a2aa4
ms.date: 04/16/2018
keywords: ["CcMdlReadComplete function"]
ms.keywords: CcMdlReadComplete, CcMdlReadComplete routine [Installable File System Drivers], ccref_9739ef62-748c-43c6-ae79-ae54f2358368.xml, ifsk.ccmdlreadcomplete, ntifs/CcMdlReadComplete
f1_keywords:
 - "ntifs/CcMdlReadComplete"
 - "CcMdlReadComplete"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CcMdlReadComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcMdlReadComplete function


## -description


The <b>CcMdlReadComplete</b> routine frees the memory descriptor lists (MDL) created by <a href="https://docs.microsoft.com/previous-versions/ff539159(v=vs.85)">CcMdlRead</a> for a cached file.


## -parameters




### -param FileObject [in]

File object pointer that was passed to <a href="https://docs.microsoft.com/previous-versions/ff539159(v=vs.85)">CcMdlRead</a>.


### -param MdlChain [in]

Address of the MDL chain returned by <a href="https://docs.microsoft.com/previous-versions/ff539159(v=vs.85)">CcMdlRead</a>.


## -remarks



<b>CcMdlReadComplete</b> frees the memory descriptor lists (MDL) created by <a href="https://docs.microsoft.com/previous-versions/ff539159(v=vs.85)">CcMdlRead</a> for a cached file. All physical pages that were locked down are unlocked. Any pages that were mapped are unmapped.

Each call to <a href="https://docs.microsoft.com/previous-versions/ff539159(v=vs.85)">CcMdlRead</a> must be followed by a call to <b>CcMdlReadComplete</b>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff539159(v=vs.85)">CcMdlRead</a>
 

 

