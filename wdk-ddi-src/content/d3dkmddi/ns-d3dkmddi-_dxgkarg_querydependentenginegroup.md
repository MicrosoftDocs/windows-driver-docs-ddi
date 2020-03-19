---
UID: NS:d3dkmddi._DXGKARG_QUERYDEPENDENTENGINEGROUP
title: _DXGKARG_QUERYDEPENDENTENGINEGROUP (d3dkmddi.h)
description: Describes all nodes on the physical display adapter (engine) that are to be queried when the display port driver's GPU scheduler calls the DxgkDdiQueryDependentEngineGroup function to query node dependencies.
old-location: display\dxgkarg_querydependentenginegroup.htm
ms.assetid: 6b1d6465-83bd-42c4-be1f-d7a2cfb74483
ms.date: 05/10/2018
keywords: ["_DXGKARG_QUERYDEPENDENTENGINEGROUP structure"]
ms.keywords: "*INOUT_DXGKARG_QUERYDEPENDENTENGINEGROUP, DXGKARG_QUERYDEPENDENTENGINEGROUP, DXGKARG_QUERYDEPENDENTENGINEGROUP structure [Display Devices], _DXGKARG_QUERYDEPENDENTENGINEGROUP, d3dkmddi/DXGKARG_QUERYDEPENDENTENGINEGROUP, display.dxgkarg_querydependentenginegroup"
f1_keywords:
 - "d3dkmddi/DXGKARG_QUERYDEPENDENTENGINEGROUP"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmddi.h
api_name:
- DXGKARG_QUERYDEPENDENTENGINEGROUP
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_QUERYDEPENDENTENGINEGROUP
---

# _DXGKARG_QUERYDEPENDENTENGINEGROUP structure


## -description


Describes all nodes on the physical display adapter (engine) that are to be queried when the display port driver's GPU scheduler calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_querydependentenginegroup">DxgkDdiQueryDependentEngineGroup</a> function to query node dependencies.


## -struct-fields




### -field NodeOrdinal

[in] An index of a node within the physical adapter defined by   the <b>EngineOrdinal</b> member that is being queried in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_querydependentenginegroup">DxgkDdiQueryDependentEngineGroup</a>.


### -field EngineOrdinal

[in] An index that defines the physical adapter in a linked display adapter (LDA) configuration that the node defined by <b>NodeOrdinal</b> belongs to.


### -field DependentNodeOrdinalMask

[out] The bitmask that describes all dependent nodes that will be affected by a reset operation.


## -remarks



The index value <b>EngineOrdinal</b> is assumed to be identical for all dependent nodes.

See Remarks of  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_querydependentenginegroup">DxgkDdiQueryDependentEngineGroup</a> for a discussion of how to compute the bitmask in the <b>DependentNodeOrdinalMask</b> member.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/tdr-changes-in-windows-8">TDR changes in Windows 8</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_querydependentenginegroup">DxgkDdiQueryDependentEngineGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_resetengine">DxgkDdiResetEngine</a>
 

 

