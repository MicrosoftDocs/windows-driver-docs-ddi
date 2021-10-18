---
UID: NS:d3dkmddi._DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT
tech.root: display
title: DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT
ms.date: 10/13/2021
targetos: Windows
description: The DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT structure contains the information used by the DxgkCbClosePhysicalMemoryObject callback function to close a physical memory object.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022 (WDDM 2.9)
req.target-type: 
req.typenames: DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT
 - DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT
f1_keywords:
 - _DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT
 - d3dkmddi/_DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT
 - DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT
 - d3dkmddi/DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT
dev_langs:
 - c++
---

## -description

The **DXGKARGCB_CLOSE_PHYSICAL_MEMORY_OBJECT** structure contains the information used by the [**DXGKCB_CLOSEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_closephysicalmemoryobject.md) callback function to close a physical memory object.

## -struct-fields

### -field hAdapterMemoryObject

The adapter memory object to close.

## -remarks

If the driver chooses to specify **hAdapterMemoryObject** as part of the [**DXGKCB_DESTROYPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md) call, then it is not necessary to close it via **DXGKCB_CLOSEPHYSICALMEMORYOBJECT** as well.

## -see-also

[**DXGKCB_CLOSEPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_closephysicalmemoryobject.md)

[**DXGKCB_DESTROYPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_destroyphysicalmemoryobject.md)

[**DXGKCB_OPENPHYSICALMEMORYOBJECT**](nc-d3dkmddi-dxgkcb_openphysicalmemoryobject.md)
