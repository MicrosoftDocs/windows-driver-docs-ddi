---
UID: NC:d3dkmddi.DXGKCB_CLOSEPHYSICALMEMORYOBJECT
tech.root: display
title: DXGKCB_CLOSEPHYSICALMEMORYOBJECT
ms.date: 06/24/2022
targetos: Windows
description: The DxgkCbClosePhysicalMemoryObject closes a physical memory object.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_CLOSEPHYSICALMEMORYOBJECT
f1_keywords:
 - DXGKCB_CLOSEPHYSICALMEMORYOBJECT
 - d3dkmddi/DXGKCB_CLOSEPHYSICALMEMORYOBJECT
dev_langs:
 - c++
---

## -description

**DXGKCB_CLOSEPHYSICALMEMORYOBJECT** closes a physical memory object.

## -parameters

### -param pArgs [in]

Pointer to a [**DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_close_physical_memory_object.md) structure that contains information about the physical memory object to close.

## -remarks

If the driver chooses to specify **hAdapterMemoryObject** as part of the [**DXGKCB_DESTROYPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md) call, then it is not necessary to close it via **DXGKCB_CLOSEPHYSICALMEMORYOBJECT** as well.

See [IOMMU DMA remapping](/windows-hardware/drivers/display/iommu-dma-remapping) for more information.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_ALLOCATEPAGESFORMDL**](ns-d3dkmddi-_dxgkargcb_allocatepagesformdl.md) and then call **DxgkCbClosePhysicalMemoryObject** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_close_physical_memory_object.md)

[**DXGKCB_DESTROYPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md)

[**DXGKCB_OPENPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
