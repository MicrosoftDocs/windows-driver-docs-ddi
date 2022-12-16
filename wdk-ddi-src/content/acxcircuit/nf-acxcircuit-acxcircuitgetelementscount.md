---
UID: NF:acxcircuit.AcxCircuitGetElementsCount
tech.root: audio
title: AcxCircuitGetElementsCount
ms.date: 12/14/2022
targetos: Windows
description: The AcxCircuitGetElementsCount function retrieves the number of elements attached to the specified ACX circuit.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
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
 - acxcircuit.h
api_name:
 - AcxCircuitGetElementsCount
f1_keywords:
 - AcxCircuitGetElementsCount
 - acxcircuit/AcxCircuitGetElementsCount
dev_langs:
 - c++
helpviewer_keywords:
 - AcxCircuitGetElementsCount
---

## -description

The **AcxCircuitGetElementsCount** function retrieves the number of elements attached to the specified ACX circuit.

## -parameters

### -param Circuit

The existing ACXCIRCUIT object from which to retrieve the elements count.

## -returns

The **AcxCircuitGetElementsCount** function returns the number of elements attached to the specified *Circuit*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.1

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
