---
UID: NC:d3dkmddi.DXGKDDI_SETALLOCATIONBACKINGSTORE
tech.root: display
title: DXGKDDI_SETALLOCATIONBACKINGSTORE
ms.date: 09/08/2022
targetos: Windows
description: Learn more about the DXGKDDI_SETALLOCATIONBACKINGSTORE function.
prerelease: false
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
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
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
 - DXGKDDI_SETALLOCATIONBACKINGSTORE
f1_keywords:
 - DXGKDDI_SETALLOCATIONBACKINGSTORE
 - d3dkmddi/DXGKDDI_SETALLOCATIONBACKINGSTORE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_SETALLOCATIONBACKINGSTORE
---

## -description

**DXGKDDI_SETALLOCATIONBACKINGSTORE** obtains the system space address to a graphics allocation backing store.

## -parameters

### -param hAdapter

[in] Handle to the miniport's context.

### -param pArgs

[in] Pointer to a [**DXGKARG_SETALLOCATIONBACKINGSTORE**](ns-d3dkmddi-dxgkarg_setallocationbackingstore.md) structure that contains additional arguments for this function.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

The address that **pBackingStore** points to is valid until the allocation is destroyed by [**DXGKDDI_DESTROYALLOCATION**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_destroyallocation).

**DXGKDDI_SETALLOCATIONBACKINGSTORE** is called during [**D3DKMTCreateAllocation**](/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreateallocation).

See [Sharing the backing store with KMD](/windows-hardware/drivers/display/sharing-backing-store-with-kmd) for more information.

## -see-also

[**DXGKARG_SETALLOCATIONBACKINGSTORE**](ns-d3dkmddi-dxgkarg_setallocationbackingstore.md)
