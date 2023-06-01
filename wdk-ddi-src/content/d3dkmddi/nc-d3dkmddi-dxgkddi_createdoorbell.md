---
UID: NC:d3dkmddi.DXGKDDI_CREATEDOORBELL
tech.root: display
title: DXGKDDI_CREATEDOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKDDI_CREATEDOORBELL callback function.
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
 - DXGKDDI_CREATEDOORBELL
f1_keywords:
 - DXGKDDI_CREATEDOORBELL
 - d3dkmddi/DXGKDDI_CREATEDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_CREATEDOORBELL
---

## -description

The OS calls KMD's **DxgkDdiCreateDoorbell** callback function to create a doorbell for a hardware queue.

## -parameters

### -param pArgs

[in/out] Pointer to a [**DXGKARG_CREATEDOORBELL**](ns-d3dkmddi-dxgkarg_createdoorbell.md) structure that describes the doorbell.

## -returns

**DxgkDdiCreateDoorbell** returns STATUS_SUCCESS if KMD was able to successfully create its doorbell object for the specified hardware queue, and UMD can use this doorbell for work submission. Otherwise, it returns an appropriate NTSTATUS error code. UMD can't use the doorbell for work submission if KMD returns any failure code.

## -remarks

When UMD calls [**D3DKMTCreateDoorbell**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatedoorbell.md) to create a doorbell for a hardware queue, the OS makes a corresponding **DxgkDdiCreateDoorbell** call to KMD so that KMD can initialize its doorbell structures.

KMD's **DxgkDdiCreateDoorbell** function should only create and initialize its doorbell data structures. It should not assign a physical doorbell location to this doorbell object yet as that is done during a subsequent call to [**DxgkDdiConnectDoorbell**](nc-d3dkmddi-dxgkddi_connectdoorbell.md). This lazy assignment ensures that a physical doorbell is not used up during hardware queue and doorbell creation, only to go wasted in the event that UMD never submits commands to it or starts submitting commands at a later time. In this way, physical doorbells are used only when actually required.

## -see-also

[**DXGKARG_CREATEDOORBELL**](ns-d3dkmddi-dxgkarg_createdoorbell.md)

[**D3DKMTCreateDoorbell**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatedoorbell.md)

[**DxgkDdiConnectDoorbell**](nc-d3dkmddi-dxgkddi_connectdoorbell.md)

[**DxgkDdiDestroyDoorbell**](nc-d3dkmddi-dxgkddi_destroydoorbell.md)
