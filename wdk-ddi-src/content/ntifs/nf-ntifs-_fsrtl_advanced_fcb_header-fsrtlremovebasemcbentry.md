---
UID: NF:ntifs.FsRtlRemoveBaseMcbEntry
title: FsRtlRemoveBaseMcbEntry function (ntifs.h)
description: The FsRtlRemoveBaseMcbEntry function is the work routine for removing a large mcb entry.  It does so without taking out the mcb GuardedMutex.
tech.root: ifsk
ms.assetid: 36eaff6e-2bb7-4264-bef1-58ec28ef2ace
ms.date: 10/19/2018
keywords: ["FsRtlRemoveBaseMcbEntry function"]
ms.keywords: FsRtlRemoveBaseMcbEntry
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
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
ms.custom: RS5
f1_keywords:
 - FsRtlRemoveBaseMcbEntry
 - ntifs/FsRtlRemoveBaseMcbEntry
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlRemoveBaseMcbEntry
dev_langs:
 - c++
---

# FsRtlRemoveBaseMcbEntry function


## -description

The **FsRtlRemoveBaseMcbEntry** function is the work routine for removing a large map control block (MCB) entry.  It does so without taking out the mcb GuardedMutex.

## -parameters

### -param Mcb

Supplies the Mcb from which to remove the mapping.

### -param Vbn

Supplies the starting virtual block number (VBN) of the mappings to remove.

### -param SectorCount

Supplies the size of the mappings to remove, in sectors.

## -returns

This function returns TRUE if the MCB is removed.

## -remarks

## -see-also

