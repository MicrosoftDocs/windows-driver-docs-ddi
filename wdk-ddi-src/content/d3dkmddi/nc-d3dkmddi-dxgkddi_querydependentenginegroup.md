---
UID: NC:d3dkmddi.DXGKDDI_QUERYDEPENDENTENGINEGROUP
title: DXGKDDI_QUERYDEPENDENTENGINEGROUP (d3dkmddi.h)
description: Called by the display port driver's GPU scheduler to query dependencies of nodes in a physical display adapter.
old-location: display\dxgkddiquerydependentenginegroup.htm
ms.date: 08/05/2020
keywords: ["DXGKDDI_QUERYDEPENDENTENGINEGROUP callback function"]
ms.keywords: DXGKDDI_QUERYDEPENDENTENGINEGROUP, DXGKDDI_QUERYDEPENDENTENGINEGROUP callback, DxgkDdiQueryDependentEngineGroup, DxgkDdiQueryDependentEngineGroup callback function [Display Devices], d3dkmddi/DxgkDdiQueryDependentEngineGroup, display.dxgkddiquerydependentenginegroup
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_QUERYDEPENDENTENGINEGROUP
 - d3dkmddi/DXGKDDI_QUERYDEPENDENTENGINEGROUP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKDDI_QUERYDEPENDENTENGINEGROUP
product:
 - Windows
---

# DXGKDDI_QUERYDEPENDENTENGINEGROUP callback function


## -description

**DXGKDDI_QUERYDEPENDENTENGINEGROUP** is called by the display port driver's GPU scheduler to query dependencies of nodes in a physical display adapter.

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pQueryDependentEngineGroup

A value of type [**DXGKARG_QUERYDEPENDENTENGINEGROUP**](ns-d3dkmddi-_dxgkarg_querydependentenginegroup.md) that specifies all nodes affected by the reset operation.

## -returns

Returns **STATUS_SUCCESS** if it succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

This function is used to describe all physical adapters (engines) that are affected by an engine reset request. It helps improve user experience on hardware architectures that have dependencies among multiple engines that can affect the reset process. Note that all affected nodes must have the same engine affinity value. (See the engine affinity discussion in [TDR changes in Windows 8](/windows-hardware/drivers/display/tdr-changes-in-windows-8).)

The display port driver's GPU scheduler calls **DxgkDdiQueryDependentEngineGroup** every time it calls the [**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md) function. The GPU scheduler waits 500 milliseconds for the display miniport driver to complete preemption of all dependent engines. For any engines for which the driver cannot complete a preemption, the GPU scheduler calls the **DxgkDdiResetEngine** function sequentially based upon the engine ordinal value.

Here is an example of how to compute the bitmask in the [**DXGKARG_QUERYDEPENDENTENGINEGROUP**](ns-d3dkmddi-_dxgkarg_querydependentenginegroup.md).**DependentNodeOrdinalMask** member. If the original values of the **DXGKARG_QUERYDEPENDENTENGINEGROUP** structure's **NodeOrdinal** and **EngineOrdinal** members are 1 and 0, respectively, and additional nodes with identifiers 2 and 4 will also be reset when node 1 is reset, the driver should set the binary value of **DependentNodeOrdinalMask** to 10110, or 0x16 in hexadecimal notation. The index value **EngineOrdinal** is assumed to be identical for all dependent nodes. The node being reset is included in the **DependentNodeOrdinalMask** bit mask.

This function should be made pageable, and it should always succeed.

The operating system guarantees that this function follows the first level synchronization mode as defined in [Threading and Synchronization First Level](/windows-hardware/drivers/display/threading-and-synchronization-first-level).

For more information, see [TDR changes in Windows 8](/windows-hardware/drivers/display/tdr-changes-in-windows-8).

## -see-also

[**DXGKARG_CREATECONTEXT**](ns-d3dkmddi-_dxgkarg_createcontext.md)

[**DXGKARG_QUERYDEPENDENTENGINEGROUP**](ns-d3dkmddi-_dxgkarg_querydependentenginegroup.md)

[**DXGK_DRIVERCAPS**](ns-d3dkmddi-_dxgk_drivercaps.md)

[**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md)

