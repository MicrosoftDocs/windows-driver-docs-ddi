---
UID: NS:d3dkmddi._DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
tech.root: display
title: DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
ms.date: 04/01/2024
targetos: Windows
description: Learn more about the DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
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
 - _DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
 - DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
f1_keywords:
 - _DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
 - d3dkmddi/_DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
 - DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
 - d3dkmddi/DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT
---

# DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT structure (d3dkmddi.h)

## -description

The **DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT** structure contains the payload for a [**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md) call when **TdrType** is **DXGK_TDR_TYPE_VSYNC_TIMEOUT**.

## -struct-fields

### -field VidPnSourceId

[in] A **D3DDDI_VIDEO_PRESENT_SOURCE_ID** value that identifies the VidPn source that timed out.

### -field LayerIndex

[in] the MPO plane index that timed out.

### -field PresentId

[in] The PresentId that timed out.

## -remarks

For more information, see [TDR debuggability improvements](/windows-hardware/drivers/display/tdr-debuggability-improvements).

## -see-also

[**DXGK_TDR_TYPE**](ne-d3dkmddi-dxgk_tdr_type.md)

[**DXGKARG_COLLECTDBGINFO2**](ns-d3dkmddi-dxgkarg_collectdbginfo2.md)

[**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md)
