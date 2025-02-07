---
UID: NS:d3dkmddi._DXGKARG_SETVIRTUALMACHINEDATA
title: DXGKARG_SETVIRTUALMACHINEDATA (d3dkmddi.h)
description: Arguments used to set virtual machine data.
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
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARG_SETVIRTUALMACHINEDATA
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _DXGKARG_SETVIRTUALMACHINEDATA
 - d3dkmddi/_DXGKARG_SETVIRTUALMACHINEDATA
 - DXGKARG_SETVIRTUALMACHINEDATA
 - d3dkmddi/DXGKARG_SETVIRTUALMACHINEDATA
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETVIRTUALMACHINEDATA
 - DXGKARG_SETVIRTUALMACHINEDATA
dev_langs:
 - c++
---

# DXGKARG_SETVIRTUALMACHINEDATA structure

## -description

The **DXGKARG_SETVIRTUALMACHINEDATA** structure contains arguments passed to [**DxgkddiSetVirtualMachineData**](nc-d3dkmddi-dxgkddi_setvirtualmachinedata.md).

## -struct-fields

### -field hKmdVmWorkerProcess

[in] Handle to the KMD process returned by [**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md)
 with [**VirtualMachineWorkerProcess**](ns-d3dkmddi-_dxgk_createprocessflags.md) set.

### -field pVmGuid

[in] Pointer to a GUID that uniquely identifies the VM. This GUID is provided for debugging purposes, so developers can attribute rendering to a specific VM when multiple VMs are running.

### -field Flags

[in] A [**DXGK_VIRTUALMACHINEDATAFLAGS**](ns-d3dkmddi-_dxgk_virtualmachinedataflags.md) structure that specifies attributes of the VM.

## -remarks

For more information, see [GPU paravitualization](/windows-hardware/drivers/display/gpu-paravirtualization).

## -see-also

[**DXGK_VIRTUALMACHINEDATAFLAGS**](ns-d3dkmddi-_dxgk_virtualmachinedataflags.md)

[**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md)

[**DxgkddiSetVirtualMachineData**](nc-d3dkmddi-dxgkddi_setvirtualmachinedata.md)
