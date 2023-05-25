---
UID: NS:d3dkmddi._DXGKARG_DISCONNECTDOORBELL
tech.root: display
title: DXGKARG_DISCONNECTDOORBELL
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the DXGKARG_DISCONNECTDOORBELL structure.
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
req.typenames: DXGKARG_DISCONNECTDOORBELL
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
 - _DXGKARG_DISCONNECTDOORBELL
 - DXGKARG_DISCONNECTDOORBELL
f1_keywords:
 - _DXGKARG_DISCONNECTDOORBELL
 - d3dkmddi/_DXGKARG_DISCONNECTDOORBELL
 - DXGKARG_DISCONNECTDOORBELL
 - d3dkmddi/DXGKARG_DISCONNECTDOORBELL
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_DISCONNECTDOORBELL
---

## -description

The **DXGKARG_DISCONNECTDOORBELL** structure contains parameters for [**DxgkDdiDisconnectDoorbell**](nc-d3dkmddi-dxgkddi_disconnectdoorbell.md).

## -struct-fields

### -field hDoorbell

[in] KMD handle to the doorbell object, which was previously created using [**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md).

### -field Flags

[in] A bit field of [**DXGKARG_DISCONNECTDOORBELL_FLAGS**](ns-d3dkmddi-dxgkarg_disconnectdoorbell_flags.md) values specifying the doorbell disconnection flags.

## -see-also

[**DXGKARG_DISCONNECTDOORBELL_FLAGS**](ns-d3dkmddi-dxgkarg_disconnectdoorbell_flags.md)

[**DxgkDdiCreateDoorbell**](nc-d3dkmddi-dxgkddi_createdoorbell.md)

[**DxgkDdiDisconnectDoorbell**](nc-d3dkmddi-dxgkddi_disconnectdoorbell.md)
