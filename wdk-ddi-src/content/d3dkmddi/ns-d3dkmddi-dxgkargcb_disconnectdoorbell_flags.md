---
UID: NS:d3dkmddi._DXGKARGCB_DISCONNECTDOORBELL_FLAGS
tech.root: display
title: DXGKARGCB_DISCONNECTDOORBELL_FLAGS
ms.date: 04/08/2024
targetos: Windows
description: Learn more about the DXGKARGCB_DISCONNECTDOORBELL_FLAGS structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARGCB_DISCONNECTDOORBELL_FLAGS
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
 - _DXGKARGCB_DISCONNECTDOORBELL_FLAGS
 - DXGKARGCB_DISCONNECTDOORBELL_FLAGS
f1_keywords:
 - _DXGKARGCB_DISCONNECTDOORBELL_FLAGS
 - d3dkmddi/_DXGKARGCB_DISCONNECTDOORBELL_FLAGS
 - DXGKARGCB_DISCONNECTDOORBELL_FLAGS
 - d3dkmddi/DXGKARGCB_DISCONNECTDOORBELL_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARGCB_DISCONNECTDOORBELL_FLAGS
---

# DXGKARGCB_DISCONNECTDOORBELL_FLAGS structure (d3dkmddi.h)

## -description

The **DXGKARGCB_DISCONNECTDOORBELL_FLAGS** structure specifies doorbell disconnection flags for [**DxgkCbDisconnectDoorbell**](nc-d3dkmddi-dxgkcb_disconnectdoorbell.md).

## -struct-fields

### -field Reserved

Reserved; set to zero.

### -field Value

An alternative way to access the structure members.

## -remarks

For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission).

## -see-also

[**DXGKARGCB_DISCONNECTDOORBELL**](ns-d3dkmddi-dxgkargcb_disconnectdoorbell.md)

[**DxgkCbDisconnectDoorbell**](nc-d3dkmddi-dxgkcb_disconnectdoorbell.md)
