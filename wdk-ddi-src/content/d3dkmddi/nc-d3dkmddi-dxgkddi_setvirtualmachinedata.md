---
UID: NC:d3dkmddi.DXGKDDI_SETVIRTUALMACHINEDATA
title: DXGKDDI_SETVIRTUALMACHINEDATA
author: windows-driver-content
description:
ms.assetid: 1fae41c4-5e88-4936-a6ea-f69668ba2bf1
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	apiref
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKDDI_SETVIRTUALMACHINEDATA
product: Windows
targetos: Windows
---

# DXGKDDI_SETVIRTUALMACHINEDATA callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Implemented by the client driver to set the virtual machine data.

## -prototype

```
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

## -parameters

### -param hAdapter

The logical adapter for which to set virtual machine data.

### -param Args:

Pointer to a [DXGKARG_SETVIRTUALMACHINEDATA](ns-d3dkmddi-_dxgkarg_setvirtualmachinedata.md) structure that contains arguments to set virtual machine data.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_SETVIRTUALMACHINEDATA and then calling DxgkddiSetVirtualMachineData.

Client GPU virtualization provides an isolation layer at the Dxgkrnl level for a particular process that runs in the context of a dedicated virtual machine. For the purpose of GPU hardware scheduling, work submitted by the virtual machine dedicated to such process is simply treated as a separate GPU client process.

Server GPU virtualization provides much stronger isolation, where virtual machines are completely isolated from each other at the OS Hypervisor level and each VM is guaranteed a fixed GPU time slice, within which they run their own scheduling algorithm across priority bands, processes, and contexts.

## -see-also