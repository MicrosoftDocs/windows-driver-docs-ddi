---
UID: NS:mpiodisk._MPIO_DSM_Path_V2
title: _MPIO_DSM_Path_V2 (mpiodisk.h)
description: The MPIO_DSM_Path_V2 structure is used to represent the DSM's definition of a path. It is a superset of the previously existing MPIO_DSM_Path class.
old-location: storage\mpio_dsm_path_v2.htm
tech.root: storage
ms.assetid: 8ebbb4c0-c761-42a5-a41a-9d661a6126d9
ms.date: 03/29/2018
keywords: ["MPIO_DSM_Path_V2 structure"]
ms.keywords: "*PMPIO_DSM_Path_V2, MPIO_DSM_Path_V2, MPIO_DSM_Path_V2 structure [Storage Devices], PMPIO_DSM_Path_V2, PMPIO_DSM_Path_V2 structure pointer [Storage Devices], _MPIO_DSM_Path_V2, mpiodisk/MPIO_DSM_Path_V2, mpiodisk/PMPIO_DSM_Path_V2, storage.mpio_dsm_path_v2, structs-scsibus_e1d340a8-aa6a-4219-8bd4-c11fc3520f5d.xml"
req.header: mpiodisk.h
req.include-header: Mpiowmi.h
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
req.typenames: MPIO_DSM_Path_V2, *PMPIO_DSM_Path_V2
f1_keywords:
 - _MPIO_DSM_Path_V2
 - mpiodisk/_MPIO_DSM_Path_V2
 - PMPIO_DSM_Path_V2
 - mpiodisk/PMPIO_DSM_Path_V2
 - MPIO_DSM_Path_V2
 - mpiodisk/MPIO_DSM_Path_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mpiodisk.h
api_name:
 - MPIO_DSM_Path_V2
---

# _MPIO_DSM_Path_V2 structure


## -description

The MPIO_DSM_Path_V2 structure is used to represent the DSM's definition of a path. It is a superset of the previously existing MPIO_DSM_Path class.

## -struct-fields

### -field DsmPathId

An unsigned 64-bitfield that is used as a unique identifier to distinguish paths known to the DSM.

### -field Reserved

Should be zero.

### -field PathWeight

An unsigned 32-bitfield that holds the weight associated with the given path.

### -field PrimaryPath

An unsigned 32-bitfield that is used as a flag to indicate the path state when accessing a particular LUN.

### -field OptimizedPath

An unsigned 32-bitfield that is used in conjunction with <i>PrimaryPath</i> to indicate the path state for accessing a LUN.

### -field PreferredPath

An unsigned 32-bitfield that is used as a flag to indicate whether this is the preferred path for accessing the LUN.

### -field FailedPath

A 32-bit unsigned field that is used as a flag to indicate if the path has failed.

### -field TargetPortGroup_State

An unsigned 32-bitfield that is used to indicate the access state of the target port group to which this instance of the LUN belongs.

### -field ALUASupport

An unsigned 32-bitfield that returns the Asymmetrical Logical Unit Access (ALUA) state transition support that is indicated by the LUN.

### -field SymmetricLUA

An unsigned 8-bitfield that is used as a flag to indicate to the application if logical unit access is symmetric.

### -field TargetPortGroup_Preferred

An unsigned 8-bitfield that is used as a flag. This field indicates if the LUN's target port group that corresponds to this path is preferred for the LUN access.

### -field TargetPortGroup_Identifier

An unsigned 16-bitfield that contains the identifier of the LUN's target port group that corresponds to this path.

### -field TargetPort_Identifier

An unsigned 32-bitfield that contains the identifier of the target port that corresponds to this path through which the LUN has been exposed.

### -field Reserved32

Should be zero.

### -field Reserved64

Should be zero.

