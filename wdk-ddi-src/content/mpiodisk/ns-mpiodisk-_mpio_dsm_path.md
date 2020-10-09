---
UID: NS:mpiodisk._MPIO_DSM_Path
title: _MPIO_DSM_Path (mpiodisk.h)
description: The MPIO_DSM_Path structure is used to represent the DSM's definition of a path.
old-location: storage\mpio_dsm_path.htm
tech.root: storage
ms.assetid: 17338526-d682-4d11-89b9-730b1a275870
ms.date: 03/29/2018
keywords: ["MPIO_DSM_Path structure"]
ms.keywords: "*PMPIO_DSM_Path, MPIO_DSM_Path, MPIO_DSM_Path structure [Storage Devices], PMPIO_DSM_Path, PMPIO_DSM_Path structure pointer [Storage Devices], _MPIO_DSM_Path, mpiodisk/MPIO_DSM_Path, mpiodisk/PMPIO_DSM_Path, storage.mpio_dsm_path, structs-scsibus_5232f48b-d34e-43a9-b2bf-fcc06317c450.xml"
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
req.typenames: MPIO_DSM_Path, *PMPIO_DSM_Path
f1_keywords:
 - _MPIO_DSM_Path
 - mpiodisk/_MPIO_DSM_Path
 - PMPIO_DSM_Path
 - mpiodisk/PMPIO_DSM_Path
 - MPIO_DSM_Path
 - mpiodisk/MPIO_DSM_Path
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mpiodisk.h
api_name:
 - MPIO_DSM_Path
---

# _MPIO_DSM_Path structure


## -description

The MPIO_DSM_Path structure is used to represent the DSM's definition of a path.

## -struct-fields

### -field DsmPathId

An unsigned 64-bitfield that is used as a unique identifier to distinguish paths that are known to the DSM.

### -field Reserved

Should be zero.

### -field PathWeight

An unsigned 32-bitfield that holds the weight associated with the given path. The assigned value determines the order in which the DSM will pick the paths if the load balance policy is set to Weighted Path. This means that a user can assign weights to each path that is available for a device and if the Load Balance Policy for the device is set as "Weighted Path," MPIO uses this PathWeight value to determine which path to use.

### -field PrimaryPath

An unsigned 32-bitfield that is used as a flag to indicate the path state when accessing a particular LUN.

