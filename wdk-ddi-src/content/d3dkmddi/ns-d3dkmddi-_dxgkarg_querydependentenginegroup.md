---
UID: NS:d3dkmddi._DXGKARG_QUERYDEPENDENTENGINEGROUP
title: DXGKARG_QUERYDEPENDENTENGINEGROUP (d3dkmddi.h)
description: Learn more about the _DXGKARG_QUERYDEPENDENTENGINEGROUP structure.
ms.date: 10/17/2024
keywords: ["DXGKARG_QUERYDEPENDENTENGINEGROUP structure"]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
tech.root: display
req.typenames: DXGKARG_QUERYDEPENDENTENGINEGROUP
f1_keywords:
 - _DXGKARG_QUERYDEPENDENTENGINEGROUP
 - d3dkmddi/_DXGKARG_QUERYDEPENDENTENGINEGROUP
 - DXGKARG_QUERYDEPENDENTENGINEGROUP
 - d3dkmddi/DXGKARG_QUERYDEPENDENTENGINEGROUP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - _DXGKARG_QUERYDEPENDENTENGINEGROUP
 - DXGKARG_QUERYDEPENDENTENGINEGROUP
---

# DXGKARG_QUERYDEPENDENTENGINEGROUP structure

## -description

Describes all nodes on the physical display adapter (engine) that are to be queried when the display port driver's GPU scheduler calls the [**DxgkDdiQueryDependentEngineGroup**](nc-d3dkmddi-dxgkddi_querydependentenginegroup.md) function to query node dependencies.

## -struct-fields

### -field NodeOrdinal [in]

An index of a node within the physical adapter defined by   the **EngineOrdinal** member that is being queried in a call to [**DxgkDdiQueryDependentEngineGroup**](nc-d3dkmddi-dxgkddi_querydependentenginegroup.md).

### -field EngineOrdinal [in]

An index that defines the physical adapter in a linked display adapter (LDA) configuration that the node defined by **NodeOrdinal** belongs to.

### -field DependentNodeOrdinalMask [out]

The bitmask that describes all dependent nodes that will be affected by a reset operation.

## -remarks

The index value **EngineOrdinal** is assumed to be identical for all dependent nodes.

See Remarks of  [**DxgkDdiQueryDependentEngineGroup**](nc-d3dkmddi-dxgkddi_querydependentenginegroup.md) for a discussion of how to compute the bitmask in the **DependentNodeOrdinalMask** member.

For more information, see [TDR changes in Windows 8](/windows-hardware/drivers/display/tdr-changes-in-windows-8).

## -see-also

[**DxgkDdiQueryDependentEngineGroup**](nc-d3dkmddi-dxgkddi_querydependentenginegroup.md)

[**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md)
