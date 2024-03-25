---
UID: NS:d3dkmthk._D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
title: D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 (d3dkmthk.h)
description: Learn more about the D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 structure.
ms.date: 10/05/2023
keywords: ["D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 structure"]
ms.keywords: _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3, D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3,
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
 - d3dkmthk/_D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
 - D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
 - d3dkmthk/D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
 - D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3
dev_langs:
 - c++
---

# D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3 structure

## -description

The **D3DKMT_CHECKMULTIPLANEOVERLAYSUPPORT3** structure is passed to [**D3DKMTCheckMultiPlaneOverlaySupport3**](nf-d3dkmthk-d3dkmtcheckmultiplaneoverlaysupport3.md) to check for multiplane overlay support.

## -struct-fields

### -field hAdapter

[in] A handle to the graphics adapter.

### -field hDevice

[in] A handle to the device.

### -field PlaneCount

[in] The number of overlay plane pointers that **ppOverlayPlanes** points to.

### -field ppOverlayPlanes

[in] Array of pointers to [**D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3**](ns-d3dkmthk-_d3dkmt_check_multiplane_overlay_plane3.md) structures that describe the overlay planes.

### -field PostCompositionCount

[in] The number of pointers that **ppPostComposition** points to.

### -field ppPostComposition

[in] Array of pointers to [**D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE**](ns-d3dkmthk-_d3dkmt_multiplane_overlay_post_composition_with_source.md) structures.

### -field Supported

[out] Boolean value that indicates support.

### -field ReturnInfo

[out] A [**D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO**](ns-d3dkmthk-d3dkmt_check_multiplane_overlay_support_return_info.md) structure in which details are returned when **Supported** is FALSE.

## -see-also

[**D3DKMTCheckMultiPlaneOverlaySupport3**](nf-d3dkmthk-d3dkmtcheckmultiplaneoverlaysupport3.md)
