---
UID: NE:ntifs._REFS_SMR_VOLUME_GC_STATE
title: REFS_SMR_VOLUME_GC_STATE (ntifs.h)
description: Learn more about the REFS_SMR_VOLUME_GC_STATE enumeration.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["REFS_SMR_VOLUME_GC_STATE enumeration"]
ms.keywords: "*PREFS_SMR_VOLUME_GC_STATE, PREFS_SMR_VOLUME_GC_STATE, REFS_SMR_VOLUME_GC_STATE, SmrGcStateActive, SmrGcStateActiveFullSpeed, SmrGcStateInactive, SmrGcStatePaused, _REFS_SMR_VOLUME_GC_STATE, ifsk.refs_smr_volume_gc_state, ntifs/PREFS_SMR_VOLUME_GC_STATE, ntifs/REFS_SMR_VOLUME_GC_STATE, ntifs/SmrGcStateActive, ntifs/SmrGcStateActiveFullSpeed, ntifs/SmrGcStateInactive, ntifs/SmrGcStatePaused"
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
req.typenames: REFS_SMR_VOLUME_GC_STATE, *PREFS_SMR_VOLUME_GC_STATE
f1_keywords:
 - _REFS_SMR_VOLUME_GC_STATE
 - ntifs/_REFS_SMR_VOLUME_GC_STATE
 - PREFS_SMR_VOLUME_GC_STATE
 - ntifs/PREFS_SMR_VOLUME_GC_STATE
 - REFS_SMR_VOLUME_GC_STATE
 - ntifs/REFS_SMR_VOLUME_GC_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntifs.h
api_name:
 - _REFS_SMR_VOLUME_GC_STATE
 - PREFS_SMR_VOLUME_GC_STATE
 - REFS_SMR_VOLUME_GC_STATE
---

# REFS_SMR_VOLUME_GC_STATE enumeration

## -description

The **REFS_SMR_VOLUME_GC_STATE** enum specifies the garbage collection's current state.

## -enum-fields

### -field SmrGcStateInactive:0

The garbage collection is inactive.

### -field SmrGcStatePaused:1

The garbage collection has been paused.

### -field SmrGcStateActive:2

The garbage collection is running.

### -field SmrGcStateActiveFullSpeed:3

The garbage collection is running at full speed.

## -see-also

[**REFS_SMR_VOLUME_INFO_OUTPUT**](ns-ntifs-_refs_smr_volume_info_output.md)
