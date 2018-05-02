---
UID: NC:d3dkmddi.DXGKDDI_QUERYDEPENDENTENGINEGROUP
title: DXGKDDI_QUERYDEPENDENTENGINEGROUP
author: windows-driver-content
description: Called by the display port driver's GPU scheduler to query dependencies of nodes in a physical display adapter.
old-location: display\dxgkddiquerydependentenginegroup.htm
old-project: display
ms.assetid: 42040ffc-40a3-4794-805c-7a165c47c8c9
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_QUERYDEPENDENTENGINEGROUP, DXGKDDI_QUERYDEPENDENTENGINEGROUP callback, DxgkDdiQueryDependentEngineGroup, DxgkDdiQueryDependentEngineGroup callback function [Display Devices], d3dkmddi/DxgkDdiQueryDependentEngineGroup, display.dxgkddiquerydependentenginegroup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkDdiQueryDependentEngineGroup
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_QUERYDEPENDENTENGINEGROUP callback function


## -description


Called by the display port driver's GPU scheduler to query dependencies of nodes in a physical display adapter.


## -parameters




### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pQueryDependentEngineGroup [in, out]

A value of type  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451294">DXGKARG_QUERYDEPENDENTENGINEGROUP</a> that specifies all nodes that are affected by the reset operation.


## -returns



Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



This function is used to describe all physical adapters (engines) that are affected by an engine reset request. It helps improve user experience on hardware architectures that have dependencies among multiple engines that can affect the reset process. Note that all affected nodes must have the same engine affinity value. (See engine affinity discussion in <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.)

The display port driver's GPU scheduler calls <i>DxgkDdiQueryDependentEngineGroup</i> every time it calls the <a href="https://msdn.microsoft.com/9c2097b2-5742-422c-a650-7efff2484970">DxgkDdiResetEngine</a> function. The GPU scheduler waits 500 milliseconds for the display miniport driver to complete preemption of all dependent engines. For any engines for which the driver cannot complete a preemption, the GPU scheduler calls the <i>DxgkDdiResetEngine</i> function sequentially based upon the engine ordinal value.

Here is an example of how to compute the bitmask in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451294">DXGKARG_QUERYDEPENDENTENGINEGROUP</a>.<b>DependentNodeOrdinalMask</b> member. If the original values of the <b>DXGKARG_QUERYDEPENDENTENGINEGROUP</b> structure's <b>NodeOrdinal</b> and <b>EngineOrdinal</b> members are 1 and 0, respectively, and additional nodes with identifiers 2 and 4 will also be reset when node 1 is reset, the driver should set the binary value of <b>DependentNodeOrdinalMask</b> to 10110, or 0x16 in hexadecimal notation. The index value <b>EngineOrdinal</b> is assumed to be identical for all dependent nodes. The node being reset is included in the <b>DependentNodeOrdinalMask</b> bit mask.

 This function should be made pageable, and it should always succeed.

The operating system guarantees that this function follows the first level synchronization mode as defined in <a href="https://msdn.microsoft.com/9fce6a18-2a66-4518-b05b-e85bdaa3951f">Threading and Synchronization First Level</a>.

For more information, see <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557567">DXGKARG_CREATECONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451294">DXGKARG_QUERYDEPENDENTENGINEGROUP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/9c2097b2-5742-422c-a650-7efff2484970">DxgkDdiResetEngine</a>
 

 

