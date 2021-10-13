---
UID: NC:d3dkmddi.DXGKCB_OPENPHYSICALMEMORYOBJECT
tech.root: display
title: DXGKCB_OPENPHYSICALMEMORYOBJECT
ms.date: 10/13/2021
targetos: Windows
description: DxgkCbOpenPhysicalMemoryObject opens a physical memory object and associates it with an adapter.
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
 - DXGKCB_OPENPHYSICALMEMORYOBJECT
f1_keywords:
 - DXGKCB_OPENPHYSICALMEMORYOBJECT
 - d3dkmddi/DXGKCB_OPENPHYSICALMEMORYOBJECT
dev_langs:
 - c++
---

## -description

A kernel-mode display miniport driver calls **DXGKCB_OPENPHYSICALMEMORYOBJECT** to open a physical memory object and associates it with an adapter.

## -parameters

### -param pArgs

[in/out] Pointer to a [**DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_open_physical_memory_object.md) structure that contains information about the physical memory object to open.

## -returns

**DXGKCB_OPENPHYSICALMEMORYOBJECT** returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

In order to create an address descriptor list (ADL) from a physical memory object, it must first be associated with an adapter. This is normally done when the physical memory object is created by specifying the **hAdapter** parameter in a call to [**DXGKCB_CREATEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md). However, in some cases, the adapter handle is not available at the time the memory was allocated (for example, early in the boot process). In this case, the driver must call **DXGKCB_OPENPHYSICALMEMORYOBJECT** to associate the physical memory object with an adapter prior to calling [**DXGKCB_ALLOCATEADL**](nc-d3dkmddi-dxgkcb_allocateadl.md).

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_open_physical_memory_object.md) and then call **DxgkCbOpenPhysicalMemoryObject** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_OPEN_PHYSICAL_MEMORY_OBJECT**](ns-d3dkmddi-dxgkargcb_open_physical_memory_object.md)

[**DXGKCB_ALLOCATEADL**](nc-d3dkmddi-dxgkcb_allocateadl.md)

[**DXGKCB_CLOSEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_closephysicalmemoryobject.md)

[**DXGKCB_CREATEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_createphysicalmemoryobject.md)
