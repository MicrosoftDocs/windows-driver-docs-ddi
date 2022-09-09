---
UID: NS:d3dkmddi._DXGKARG_SETALLOCATIONBACKINGSTORE
tech.root: display
title: DXGKARG_SETALLOCATIONBACKINGSTORE
ms.date: 09/08/2022
targetos: Windows
description: Learn more about the DXGKARG_SETALLOCATIONBACKINGSTORE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_SETALLOCATIONBACKINGSTORE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SETALLOCATIONBACKINGSTORE
 - DXGKARG_SETALLOCATIONBACKINGSTORE
f1_keywords:
 - _DXGKARG_SETALLOCATIONBACKINGSTORE
 - d3dkmddi/_DXGKARG_SETALLOCATIONBACKINGSTORE
 - DXGKARG_SETALLOCATIONBACKINGSTORE
 - d3dkmddi/DXGKARG_SETALLOCATIONBACKINGSTORE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_SETALLOCATIONBACKINGSTORE
---

## -description

The **DXGKARG_SETALLOCATIONBACKINGSTORE** structure contains the arguments used by the [**DXGKDDI_SETALLOCATIONBACKINGSTORE**](nc-d3dkmddi-dxgkddi_setallocationbackingstore.md) callback function to obtain the system space address to a graphics allocation backing store.

## -struct-fields

### -field hDriverAllocation

[in] Handle to the driver allocation object. This handle was returned from [**DXGKDDI_CREATEALLOCATION**](nc-d3dkmddi-dxgkddi_createallocation.md).

### -field pBackingStore

[in] Pointer to an address in system space for the allocation backing store. The address is valid until [**DXGKDDI_DESTROYALLOCATION**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_destroyallocation) is called.

## -remarks

See [Sharing the backing store with KMD](sharing-backing-store-with-kmd) for more information.

## -see-also

[**DXGKDDI_SETALLOCATIONBACKINGSTORE**](nc-d3dkmddi-dxgkddi_setallocationbackingstore.md)
