---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAllocateResource
title: FsRtlAllocateResource function
author: windows-driver-content
description: Obsolete.
old-location: ifsk\fsrtlallocateresource.htm
old-project: ifsk
ms.assetid: a02f87ea-e7e5-48ff-94a2-a76b4f0cd04a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, F, FsRtlAllocateResource, FsRtlAllocateResource function [Installable File System Drivers], R, a, c, e, fsrtlref_7c0e205b-9e67-4fba-a70d-67e441cdcddf.xml, ifsk.fsrtlallocateresource, l, ntifs/FsRtlAllocateResource, o, r, s, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FsRtlAllocateResource
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAllocateResource function


## -description


The <b>FsRtlAllocateResource</b> routine is obsolete, but is exported to support existing driver binaries. Use <a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a> and <a href="..\wdm\nf-wdm-exinitializeresourcelite.md">ExInitializeResourceLite</a> instead.


## -syntax


````
  FsRtlAllocateResource(
    
);
````


## -parameters




### -param

TBD





