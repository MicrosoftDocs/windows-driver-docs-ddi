---
UID: NF:acxtargets.AcxTargetCircuitGetSymbolicLinkName
tech.root: audio
title: AcxTargetCircuitGetSymbolicLinkName
ms.date: 11/09/2022
targetos: Windows
description: The AcxTargetCircuitGetSymbolicLinkName function retrieves the symbolic link name for the specifies ACX target circuit.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxtargets.h
api_name:
 - AcxTargetCircuitGetSymbolicLinkName
f1_keywords:
 - AcxTargetCircuitGetSymbolicLinkName
 - acxtargets/AcxTargetCircuitGetSymbolicLinkName
dev_langs:
 - c++
helpviewer_keywords:
 - AcxTargetCircuitGetSymbolicLinkName
---

## -description

The **AcxTargetCircuitGetSymbolicLinkName** function retrieves the symbolic link name for the specifies ACX target circuit.

## -parameters

### -param TargetCircuit [in]

The ACX target circuit for which to retrieve the symbolic link name.

## -returns

Returns a string containing the symbolic link name for the ACX target circuit specified by the *TargetCircuit* parameter.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.1

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
