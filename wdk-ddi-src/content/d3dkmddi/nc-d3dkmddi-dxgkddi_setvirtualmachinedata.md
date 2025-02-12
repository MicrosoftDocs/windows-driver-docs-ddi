---
UID: NC:d3dkmddi.DXGKDDI_SETVIRTUALMACHINEDATA
title: DXGKDDI_SETVIRTUALMACHINEDATA (d3dkmddi.h)
description: Set the virtual machine data.
ms.date: 02/06/2025
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - DXGKDDI_SETVIRTUALMACHINEDATA
 - d3dkmddi/DXGKDDI_SETVIRTUALMACHINEDATA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SETVIRTUALMACHINEDATA
dev_langs:
 - c++
---

# DXGKDDI_SETVIRTUALMACHINEDATA callback function

## -description

*Dxgkrnl* calls **DxgkddiSetVirtualMachineData** to pass information about a virtual machine (VM) to the kernel-mode display driver (KMD).

## -parameters

### -param hAdapter

[in] The logical adapter for which to set VM data.

### -param Args

[in] Pointer to a [**DXGKARG_SETVIRTUALMACHINEDATA**](ns-d3dkmddi-_dxgkarg_setvirtualmachinedata.md) structure that contains arguments to set VM data.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Client GPU virtualization provides an isolation layer at the *Dxgkrnl* level for a particular process that runs in the context of a dedicated VM. For the purpose of GPU hardware scheduling, work submitted by the VM dedicated to such a process is simply treated as a separate GPU client process.

Server GPU virtualization provides much stronger isolation, where VMs are completely isolated from each other at the OS Hypervisor level and each VM is guaranteed a fixed GPU time slice, within which they run their own scheduling algorithm across priority bands, processes, and contexts.

For more information, see [GPU paravitualization](/windows-hardware/drivers/display/gpu-paravirtualization).

## -see-also

[**DXGKARG_SETVIRTUALMACHINEDATA**](ns-d3dkmddi-_dxgkarg_setvirtualmachinedata.md)
