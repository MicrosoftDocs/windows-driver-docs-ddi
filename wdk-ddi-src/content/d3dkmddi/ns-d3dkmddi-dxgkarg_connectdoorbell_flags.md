---
UID: NS:d3dkmddi._DXGKARG_CONNECTDOORBELL_FLAGS
tech.root: display
title: DXGKARG_CONNECTDOORBELL_FLAGS
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKARG_CONNECTDOORBELL_FLAGS structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_FUTURE
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_CONNECTDOORBELL_FLAGS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_CONNECTDOORBELL_FLAGS
 - DXGKARG_CONNECTDOORBELL_FLAGS
f1_keywords:
 - _DXGKARG_CONNECTDOORBELL_FLAGS
 - d3dkmddi/_DXGKARG_CONNECTDOORBELL_FLAGS
 - DXGKARG_CONNECTDOORBELL_FLAGS
 - d3dkmddi/DXGKARG_CONNECTDOORBELL_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CONNECTDOORBELL_FLAGS
---

## -description

The **DXGKARG_CONNECTDOORBELL_FLAGS** structure specifies doorbell connection flags for [**DxgkDdiConnectDoorbell**](ns-d3dkmddi-dxgkddi_connectdoorbell.md).

## -struct-fields

### -field RequireSecondaryAddress

If UMD [created this doorbell](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatedoorbell.md) with the **RequireSecondaryCpuVA** flag, then *Dxgkrnl* sets this corresponding **RequireSecondaryAddress** flag to inform KMD that this doorbell requires two physical addresses.

### -field Reserved

Reserved; set to zero.

### -field Value

An alternative way to access the structure members.

## -see-also

[**D3DKMT_CREATE_DOORBELL**](nf-d3dkmthk-d3dkmtcreatedoorbell.md)

[**DXGKARG_CONNECTDOORBELL**](ns-d3dkmddi-dxgkarg_connectdoorbell.md)

[**DxgkDdiConnectDoorbell**](ns-d3dkmddi-dxgkddi_connectdoorbell.md)
