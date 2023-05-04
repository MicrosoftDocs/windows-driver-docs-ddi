---
UID: NF:d3dkmthk.D3DKMTCreateDoorbell
tech.root: display
title: D3DKMTCreateDoorbell
ms.date: 05/05/2023
targetos: Windows
description: Learn more about the D3DKMTCreateDoorbell function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmthk.h
req.idl: 
req.include-header: 
req.irql: 
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
 - 
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMTCreateDoorbell
f1_keywords:
 - D3DKMTCreateDoorbell
 - d3dkmthk/D3DKMTCreateDoorbell
dev_langs:
 - c++
helpviewer_keywords:
 - D3DKMTCreateDoorbell
---

## -description

The **D3DKMTCreateDoorbell** function creates a GPU doorbell for a D3D hardware queue for user-mode submission.

## -parameters

### -param unnamedParam1

[in/out] Pointer to a [**D3DKMT_CREATE_DOORBELL**](ns-d3dkmthk-d3dkmt_create_doorbell.md) structure that describes the doorbell to create.

## -returns

**D3DKMTCreateDoorbell** returns STATUS_SUCCESS when the OS successfully creates a doorbell for this hardware queue that UMD can use for work submission. Any failure return code means that the doorbell was not created and the UMD can't use it for work submission.

## -remarks

**D3DKMTCreateDoorbell** creates a doorbell object that is initialized as disconnected. UMD must call [**D3DKMTConnectDoorbell**](nf-d3dkmthk-d3dkmtconnectdoorbell.md) before using this doorbell to submit commands on the hardware queue.

When UMD calls **D3DKMTCreateDoorbell**, the OS makes a corresponding call to KMD's [**DxgkDdiCreateDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdoorbell.md) callback in which KMD can initialize its doorbell state.

## -see-also

[**D3DKMTConnectDoorbell**](nf-d3dkmthk-d3dkmtconnectdoorbell.md)

[**D3DKMT_CREATE_DOORBELL**](ns-d3dkmthk-d3dkmt_create_doorbell.md)

[**DxgkDdiConnectDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_connectoorbell.md)

[**DxgkDdiCreateDoorbell**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdoorbell.md)

[**D3DKMTDestroyDoorbell**](nf-d3dkmthk-d3dkmtdestroydoorbell.md)
