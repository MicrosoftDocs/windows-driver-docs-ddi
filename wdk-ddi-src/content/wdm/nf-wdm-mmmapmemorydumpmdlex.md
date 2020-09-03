---
UID: NF:wdm.MmMapMemoryDumpMdlEx
title: MmMapMemoryDumpMdlEx function
author: windows-driver-content
description: TBD
tech.root: kernel
ms.assetid: c4a12185-4c6f-43e9-87ba-6dc1b24fa6cf
ms.author: windowsdriverdev
ms.date: 03/01/2020
ms.topic: function
ms.keywords: MmMapMemoryDumpMdlEx
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - MmMapMemoryDumpMdlEx
product:
 - Windows
f1_keywords:
 - MmMapMemoryDumpMdlEx
 - wdm/MmMapMemoryDumpMdlEx
---

# MmMapMemoryDumpMdlEx function


## -description

Maps an MDL into a specified virtual address.  Only 1 MDL can be mapped at a time. For use by crash dump, hibernate and live dump routines only.

## -parameters

### -param Va

Supplies the VA to map.

### -param PageTotal

Supplies the total number of pages in the VA range.

### -param MemoryDumpMdl

Supplies the MDL to map.

### -param Flags

Supplies MM_DUMP_MAP_INVALIDATE to indicate the mapping PTEs should be zeroed and the local TB flushed.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

