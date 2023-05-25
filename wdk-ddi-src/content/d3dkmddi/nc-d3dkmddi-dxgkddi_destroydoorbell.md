---
UID: NC:d3dkmddi.DXGKDDI_DESTROYDOORBELL
tech.root: display
title: DXGKDDI_DESTROYDOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKDDI_DESTROYDOORBELL callback function.
prerelease: true
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
req.target-min-winverclnt: WIN11_FUTURE
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
 - DXGKDDI_DESTROYDOORBELL
f1_keywords:
 - DXGKDDI_DESTROYDOORBELL
 - d3dkmddi/DXGKDDI_DESTROYDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DESTROYDOORBELL
---

## -description

The **DxgkDdiDestroyDoorbell** function destroys a previously created doorbell object.

## -parameters

### -param pArgs

[in/out] Pointer to a [**DXGKARG_DESTROYDOORBELL**](ns-d3dkmddi-dxgkarg_destroydoorbell.md) structure that describes the doorbell to destroy.

## -returns

**DxgkDdiDestroyDoorbell** must succeed and return STATUS_SUCCESS.

## -remarks

The OS calls KMD's **DxgkDdiDestroyDoorbell** when UMD calls [**D3DKMTDestroyDoorbell**](../d3dkmthk/nf-d3dkmthk-d3dkmtdestroydoorbell.md).

KMD should disconnect the physical doorbell location and destroy its doorbell objects.

UMD must not use the handle after calling **D3DKMTDestroyDoorbell**.

## -see-also

[**DXGKARG_DESTROYDOORBELL**](ns-d3dkmddi-dxgkarg_destroydoorbell.md)

[**DxgkddiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md)
