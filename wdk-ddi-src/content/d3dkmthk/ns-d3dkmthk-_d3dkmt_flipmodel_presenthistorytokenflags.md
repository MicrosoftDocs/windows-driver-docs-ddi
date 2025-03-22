---
UID: NS:d3dkmthk._D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
title: D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS (d3dkmthk.h)
description: Learn more about the D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure.
ms.date: 04/10/2024
keywords: ["D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure"]
req.header: d3dkmthk.h
req.construct-type: structure
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
f1_keywords:
 - _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
 - d3dkmthk/_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
 - D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
 - d3dkmthk/D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
 - D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
---

# D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure (d3dkmthk.h)



## -description

The **D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS** structure identifies attributes of a flip present-history operation.

## -struct-fields

### -field Video

A UINT value that specifies whether the flip operation is performed with video.

### -field RestrictedContent

A UINT value that specifies whether the flip operation is performed with restricted content.

### -field ClipToView

A UINT value that specifies whether the flip operation is clipped to the view surface.

### -field StereoPreferRight

A UINT value that specifies that when the driver clones a stereo primary allocation to a mono monitor, it should use the right image.

Supported starting with Windows 8.

### -field TemporaryMono

A UINT value that specifies whether the driver should use the left image of a stereo allocation for the right and left portions of a stereo frame.

This member should  be set only if the driver reports support for this option in the current display mode by setting the **Type** member of the [**D3DKMDT_VIDPN_SOURCE_MODE**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md) structure to D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN.

Supported starting with Windows 8.

### -field FlipRestart

A UINT value that specifies whether to restart a flip to a new surface.

Supported starting with Windows 8.

### -field HDRMetaDataChanged

### -field AlphaMode

A UINT value that specifies whether the DWM  should use alpha transparency information when it composes swap buffers.

Setting this member is equivalent to setting the    eighth and ninth bits of the 32-bit **Value** member (0x00000180).

Supported starting with Windows 8.

### -field SignalLimitOnTokenCompletion

 A UINT value that specifies the limit for the number of present operations that can be queued for the device after the GPU has finished processing the token.

Setting this member is equivalent to setting the    tenth bit of the 32-bit **Value** member (0x00000200).

Supported starting with Windows 8.

### -field YCbCrFlags

### -field IndependentFlip

### -field IndependentFlipStage

### -field IndependentFlipReleaseCount

### -field IndependentFlipForceNotifyDwm

### -field UseCustomDuration

### -field IndependentFlipRequestDwmConfirm

### -field IndependentFlipCandidate

### -field IndependentFlipCheckNeeded

### -field IndependentFlipTrueImmediate

### -field IndependentFlipRequestDwmExit

### -field IndependentFlipDoNotFlip

### -field CompSurfaceNotifiedEarly

### -field RequirePairedToken

Require a paired token.

### -field VariableRefreshOverrideEligible

### -field Reserved

Supported starting with Windows 8.

This member is reserved and should be set to zero.

### -field Value

An alternative way to access the bit-field flags.

## -see-also

[**D3DKMT_PRESENTHISTORYTOKEN**](ns-d3dkmthk-_d3dkmt_presenthistorytoken.md)
