---
UID: NF:ntifs.FsRtlAllocateResource
title: FsRtlAllocateResource function (ntifs.h)
description: Obsolete.
old-location: ifsk\fsrtlallocateresource.htm
tech.root: ifsk
ms.assetid: a02f87ea-e7e5-48ff-94a2-a76b4f0cd04a
ms.date: 04/16/2018
keywords: ["FsRtlAllocateResource function"]
ms.keywords: FsRtlAllocateResource, FsRtlAllocateResource function [Installable File System Drivers], fsrtlref_7c0e205b-9e67-4fba-a70d-67e441cdcddf.xml, ifsk.fsrtlallocateresource, ntifs/FsRtlAllocateResource
f1_keywords:
 - "ntifs/FsRtlAllocateResource"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FsRtlAllocateResource
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlAllocateResource function


## -description


The <b>FsRtlAllocateResource</b> routine is obsolete, but is exported to support existing driver binaries. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatefromnpagedlookasidelist">ExAllocateFromNPagedLookasideList</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializeresourcelite">ExInitializeResourceLite</a> instead.


## -parameters




### -param

<p>Reserved.</p>





