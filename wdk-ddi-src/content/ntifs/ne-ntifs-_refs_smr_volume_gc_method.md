---
UID: NE:ntifs._REFS_SMR_VOLUME_GC_METHOD
title: REFS_SMR_VOLUME_GC_METHOD (ntifs.h)
description: Learn more about the REFS_SMR_VOLUME_GC_METHOD enumeration.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["REFS_SMR_VOLUME_GC_METHOD enumeration"]
ms.keywords: "*PREFS_SMR_VOLUME_GC_METHOD, PREFS_SMR_VOLUME_GC_METHOD, REFS_SMR_VOLUME_GC_METHOD, SmrGcMethodCompaction, SmrGcMethodCompression, SmrGcMethodRotation, _REFS_SMR_VOLUME_GC_METHOD, ifsk.refs_smr_volume_gc_method, ntifs/PREFS_SMR_VOLUME_GC_METHOD, ntifs/REFS_SMR_VOLUME_GC_METHOD, ntifs/SmrGcMethodCompaction, ntifs/SmrGcMethodCompression, ntifs/SmrGcMethodRotation"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.typenames: REFS_SMR_VOLUME_GC_METHOD, *PREFS_SMR_VOLUME_GC_METHOD
f1_keywords:
 - _REFS_SMR_VOLUME_GC_METHOD
 - ntifs/_REFS_SMR_VOLUME_GC_METHOD
 - PREFS_SMR_VOLUME_GC_METHOD
 - ntifs/PREFS_SMR_VOLUME_GC_METHOD
 - REFS_SMR_VOLUME_GC_METHOD
 - ntifs/REFS_SMR_VOLUME_GC_METHOD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntifs.h
api_name:
 - _REFS_SMR_VOLUME_GC_METHOD
 - PREFS_SMR_VOLUME_GC_METHOD
 - REFS_SMR_VOLUME_GC_METHOD
---

# REFS_SMR_VOLUME_GC_METHOD enumeration

## -description

The **REFS_SMR_VOLUME_GC_METHOD** enum specifies the garbage collection method or strategy for [**FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS**](/windows-hardware/drivers/ifs/fsctl-set-refs-smr-volume-gc-parameters).

## -enum-fields

### -field SmrGcMethodCompaction:1

Specifies the use of the compaction method for garbage collection.

### -field SmrGcMethodCompression:2

Specifies the use of the compression method for garbage collection.

### -field SmrGcMethodRotation:3

Specifies the use of the rotation method for garbage collection. Moves data from one tier to another.

## -remarks

Currently the only supported value  is **SmrGcMethodCompaction**.

## -see-also

[**FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS**](/windows-hardware/drivers/ifs/fsctl-set-refs-smr-volume-gc-parameters)
