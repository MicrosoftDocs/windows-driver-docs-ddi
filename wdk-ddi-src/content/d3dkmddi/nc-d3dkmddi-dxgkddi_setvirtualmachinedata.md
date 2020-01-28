---
UID: NC:d3dkmddi.DXGKDDI_SETVIRTUALMACHINEDATA
title: DXGKDDI_SETVIRTUALMACHINEDATA (d3dkmddi.h)
description: Set the virtual machine data.
ms.assetid: 1fae41c4-5e88-4936-a6ea-f69668ba2bf1
ms.date: 10/19/2018
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
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
 - "d3dkmddi/DXGKDDI_SETVIRTUALMACHINEDATA"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SETVIRTUALMACHINEDATA
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_SETVIRTUALMACHINEDATA callback function

## -description

Set the virtual machine data.

## -parameters

### -param hAdapter

The logical adapter for which to set virtual machine data.

### -param Args

Pointer to a [DXGKARG_SETVIRTUALMACHINEDATA](ns-d3dkmddi-_dxgkarg_setvirtualmachinedata.md) structure that contains arguments to set virtual machine data.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -prototype

```cpp
//Declaration

DXGKDDI_SETVIRTUALMACHINEDATA DxgkddiSetvirtualmachinedata;

// Definition

NTSTATUS DxgkddiSetvirtualmachinedata
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARG_SETVIRTUALMACHINEDATA Args
)
{...}

DXGKDDI_SETVIRTUALMACHINEDATA *PDXGKDDI_SETVIRTUALMACHINEDATA


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_SETVIRTUALMACHINEDATA and then calling DxgkddiSetVirtualMachineData.

Client GPU virtualization provides an isolation layer at the Dxgkrnl level for a particular process that runs in the context of a dedicated virtual machine. For the purpose of GPU hardware scheduling, work submitted by the virtual machine dedicated to such process is simply treated as a separate GPU client process.

Server GPU virtualization provides much stronger isolation, where virtual machines are completely isolated from each other at the OS Hypervisor level and each VM is guaranteed a fixed GPU time slice, within which they run their own scheduling algorithm across priority bands, processes, and contexts.

## -see-also

