---
UID: NC:d3dkmddi.DXGKDDI_QUERYDEPENDENTENGINEGROUP
title: DXGKDDI_QUERYDEPENDENTENGINEGROUP (d3dkmddi.h)
description: Called by the display port driver's GPU scheduler to query dependencies of nodes in a physical display adapter.
old-location: display\dxgkddiquerydependentenginegroup.htm
ms.assetid: 42040ffc-40a3-4794-805c-7a165c47c8c9
ms.date: 05/10/2018
ms.keywords: DXGKDDI_QUERYDEPENDENTENGINEGROUP, DXGKDDI_QUERYDEPENDENTENGINEGROUP callback, DxgkDdiQueryDependentEngineGroup, DxgkDdiQueryDependentEngineGroup callback function [Display Devices], d3dkmddi/DxgkDdiQueryDependentEngineGroup, display.dxgkddiquerydependentenginegroup
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DxgkDdiQueryDependentEngineGroup"
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3dkmddi.h
api_name:
- DxgkDdiQueryDependentEngineGroup
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_QUERYDEPENDENTENGINEGROUP callback function


## -description


Called by the display port driver's GPU scheduler to query dependencies of nodes in a physical display adapter.


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.


### -param pQueryDependentEngineGroup [in, out]

A value of type  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_querydependentenginegroup">DXGKARG_QUERYDEPENDENTENGINEGROUP</a> that specifies all nodes that are affected by the reset operation.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



This function is used to describe all physical adapters (engines) that are affected by an engine reset request. It helps improve user experience on hardware architectures that have dependencies among multiple engines that can affect the reset process. Note that all affected nodes must have the same engine affinity value. (See engine affinity discussion in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/tdr-changes-in-windows-8">TDR changes in Windows 8</a>.)

The display port driver's GPU scheduler calls <i>DxgkDdiQueryDependentEngineGroup</i> every time it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_resetengine">DxgkDdiResetEngine</a> function. The GPU scheduler waits 500 milliseconds for the display miniport driver to complete preemption of all dependent engines. For any engines for which the driver cannot complete a preemption, the GPU scheduler calls the <i>DxgkDdiResetEngine</i> function sequentially based upon the engine ordinal value.

Here is an example of how to compute the bitmask in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_querydependentenginegroup">DXGKARG_QUERYDEPENDENTENGINEGROUP</a>.<b>DependentNodeOrdinalMask</b> member. If the original values of the <b>DXGKARG_QUERYDEPENDENTENGINEGROUP</b> structure's <b>NodeOrdinal</b> and <b>EngineOrdinal</b> members are 1 and 0, respectively, and additional nodes with identifiers 2 and 4 will also be reset when node 1 is reset, the driver should set the binary value of <b>DependentNodeOrdinalMask</b> to 10110, or 0x16 in hexadecimal notation. The index value <b>EngineOrdinal</b> is assumed to be identical for all dependent nodes. The node being reset is included in the <b>DependentNodeOrdinalMask</b> bit mask.

 This function should be made pageable, and it should always succeed.

The operating system guarantees that this function follows the first level synchronization mode as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-first-level">Threading and Synchronization First Level</a>.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/tdr-changes-in-windows-8">TDR changes in Windows 8</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_createcontext">DXGKARG_CREATECONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_querydependentenginegroup">DXGKARG_QUERYDEPENDENTENGINEGROUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_resetengine">DxgkDdiResetEngine</a>
 

 

