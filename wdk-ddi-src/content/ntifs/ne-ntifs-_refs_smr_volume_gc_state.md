---
UID: NE:ntifs._REFS_SMR_VOLUME_GC_STATE
title: _REFS_SMR_VOLUME_GC_STATE (ntifs.h)
description: The REFS_SMR_VOLUME_GC_STATE enum specifies the garbage collection's current state.
old-location: ifsk\refs_smr_volume_gc_state.htm
tech.root: ifsk
ms.assetid: 9E75F65A-6E9C-485F-9437-30CB01A5F317
ms.date: 04/16/2018
ms.keywords: "*PREFS_SMR_VOLUME_GC_STATE, PREFS_SMR_VOLUME_GC_STATE, PREFS_SMR_VOLUME_GC_STATE enumeration pointer [Installable File System Drivers], REFS_SMR_VOLUME_GC_STATE, REFS_SMR_VOLUME_GC_STATE enumeration [Installable File System Drivers], SmrGcStateActive, SmrGcStateActiveFullSpeed, SmrGcStateInactive, SmrGcStatePaused, _REFS_SMR_VOLUME_GC_STATE, ifsk.refs_smr_volume_gc_state, ntifs/PREFS_SMR_VOLUME_GC_STATE, ntifs/REFS_SMR_VOLUME_GC_STATE, ntifs/SmrGcStateActive, ntifs/SmrGcStateActiveFullSpeed, ntifs/SmrGcStateInactive, ntifs/SmrGcStatePaused"
ms.topic: enum
f1_keywords:
 - "ntifs/REFS_SMR_VOLUME_GC_STATE"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
- Ntifs.h
api_name:
- REFS_SMR_VOLUME_GC_STATE
product:
- Windows
targetos: Windows
req.typenames: REFS_SMR_VOLUME_GC_STATE, *PREFS_SMR_VOLUME_GC_STATE
---

# _REFS_SMR_VOLUME_GC_STATE enumeration


## -description


The <b>REFS_SMR_VOLUME_GC_STATE</b> enum specifies the garbage collection's current state.


## -enum-fields




### -field SmrGcStateInactive

Specifies the garbage collection is inactive.


### -field SmrGcStatePaused

 Specifies the garbage collection has been paused.


### -field SmrGcStateActive

Specifies the garbage collection is running.


### -field SmrGcStateActiveFullSpeed

Specifies the garbage collection is running at full speed.

