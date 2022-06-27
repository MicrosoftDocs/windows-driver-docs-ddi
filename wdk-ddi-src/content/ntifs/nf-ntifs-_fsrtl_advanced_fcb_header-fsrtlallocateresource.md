---
UID: NF:ntifs.FsRtlAllocateResource
title: FsRtlAllocateResource function (ntifs.h)
description: The FsRtlAllocateResource function is obsolete.
old-location: ifsk\fsrtlallocateresource.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["FsRtlAllocateResource function"]
ms.keywords: FsRtlAllocateResource, FsRtlAllocateResource function [Installable File System Drivers], fsrtlref_7c0e205b-9e67-4fba-a70d-67e441cdcddf.xml, ifsk.fsrtlallocateresource, ntifs/FsRtlAllocateResource
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlAllocateResource
 - ntifs/FsRtlAllocateResource
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FsRtlAllocateResource
---

# FsRtlAllocateResource function

## -description

The **FsRtlAllocateResource** routine is obsolete, but is exported to support existing driver binaries. Use [**ExAllocateFromNPagedLookasideList**](../wdm/nf-wdm-exallocatefromnpagedlookasidelist.md) and [**ExInitializeResourceLite**](../wdm/nf-wdm-exinitializeresourcelite.md) instead.

## -returns

Reserved.
