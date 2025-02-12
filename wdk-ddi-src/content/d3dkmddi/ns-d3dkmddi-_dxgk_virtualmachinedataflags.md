---
UID: NS:d3dkmddi._DXGK_VIRTUALMACHINEDATAFLAGS
title: DXGK_VIRTUALMACHINEDATAFLAGS (d3dkmddi.h)
description: The virtual machine data flags.
ms.date: 02/06/2025
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_VIRTUALMACHINEDATAFLAGS
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGK_VIRTUALMACHINEDATAFLAGS
 - d3dkmddi/_DXGK_VIRTUALMACHINEDATAFLAGS
 - DXGK_VIRTUALMACHINEDATAFLAGS
 - d3dkmddi/DXGK_VIRTUALMACHINEDATAFLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_VIRTUALMACHINEDATAFLAGS
 - DXGK_VIRTUALMACHINEDATAFLAGS
---

# DXGK_VIRTUALMACHINEDATAFLAGS structure

## -description

The **DXGK_VIRTUALMACHINEDATAFLAGS** structure specifies attributes of the virtual machine (VM).

## -struct-fields

### -field SecureVirtualMachine

When set, specifies that the VM runs in secure mode.

### -field LinuxVirtualMachine

When set, specifies that the VM is Linux-based.

### -field Value

Use to reference bits in the union.

## -remarks

For more information, see [GPU paravitualization](/windows-hardware/drivers/display/gpu-paravirtualization).

## -see-also

[**DXGKARG_SETVIRTUALMACHINEDATA**](ns-d3dkmddi-_dxgkarg_setvirtualmachinedata.md)

[**DxgkddiSetVirtualMachineData**](nc-d3dkmddi-dxgkddi_setvirtualmachinedata.md)
