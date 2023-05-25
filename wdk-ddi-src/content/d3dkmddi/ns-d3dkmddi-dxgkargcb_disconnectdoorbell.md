---
UID: NS:d3dkmddi._DXGKARGCB_DISCONNECTDOORBELL
tech.root: display
title: DXGKARGCB_DISCONNECTDOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKARGCB_DISCONNECTDOORBELL structure.
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
req.typenames: DXGKARGCB_DISCONNECTDOORBELL
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
 - _DXGKARGCB_DISCONNECTDOORBELL
 - DXGKARGCB_DISCONNECTDOORBELL
f1_keywords:
 - _DXGKARGCB_DISCONNECTDOORBELL
 - d3dkmddi/_DXGKARGCB_DISCONNECTDOORBELL
 - DXGKARGCB_DISCONNECTDOORBELL
 - d3dkmddi/DXGKARGCB_DISCONNECTDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARGCB_DISCONNECTDOORBELL
---

## -description

The **DXGKARGCB_DISCONNECTDOORBELL** structure contains parameters for [**DXGKCB_DISCONNECTDOORBELL**](nc-d3dkmddi-dxgkcb_disconnectdoorbell.md).

## -struct-fields

### -field hHwQueue

[in] KMD handle to the hardware queue object whose doorbell must be disconnected. This handle was previously created using [**D3DKMTCreateHwQueue**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatehwqueue.md).

### -field Flags

[in] A bit field of [**DXGKARGCB_DISCONNECTDOORBELL_FLAGS**](ns-d3dkmddi-dxgkargcb_disconnectdoorbell_flags.md) values specifying the doorbell disconnection flags.

### -field DisconnectReason

[in] A [**D3DDDI_DOORBELLSTATUS**](../d3dukmdt/ne-d3dukmdt-d3dddi_doorbellstatus.md) enumeration value that specifies the reason for the disconnection.

## -see-also

[**D3DDDI_DOORBELLSTATUS**](../d3dukmdt/ne-d3dukmdt-d3dddi_doorbellstatus.md)

[**DXGKARGCB_DISCONNECTDOORBELL_FLAGS**](ns-d3dkmddi-dxgkargcb_disconnectdoorbell_flags.md)

[**DXGKCB_DISCONNECTDOORBELL**](nc-d3dkmddi-dxgkcb_disconnectdoorbell.md)
