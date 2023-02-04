---
UID: NS:d3dkmddi._DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
title: DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS (d3dkmddi.h)
description: Learn more about the DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS structure.
ms.date: 02/03/2023
keywords: ["DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS structure"]
ms.keywords: DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS, DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS structure [Display Devices], _DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS, d3dkmddi/DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS, display.dxgk_setvidpnsourceaddress_input_flags
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
f1_keywords:
 - _DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
 - d3dkmddi/_DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
 - DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
 - d3dkmddi/DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
 - DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
---

# DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS structure

## -description

The **DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS** structure contains the set of flags needed to set the VidPN source address.

## -struct-fields

## -field FlipStereo

Specifies whether the driver flips both the left and right images of a stereo allocation.

If the **FlipOnNextVSync** member of the [**DXGK_PLANE_SPECIFIC_INPUT_FLAGS**](ns-d3dkmddi-_dxgk_plane_specific_input_flags.md) structure is set, the driver completes the flip to the left image on the next VSync and then completes the flip to the right image on the following VSync.

If the **FlipImmediate** member of **DXGK_PLANE_SPECIFIC_INPUT_FLAGS** is set, the driver immediately starts to scan out from the new allocation. For example, if the driver was scanning a right image, it starts the new scan from the same relative offset in the right image of the new allocation.

The **FlipStereo** and **FlipStereoTemporaryMono** members cannot both be set at the same time.

## -field FlipStereoTemporaryMono

Specifies whether the driver uses the left image of a stereo allocation for the right and left portions of a stereo frame. The driver performs the same present operation as with **FlipStereo**, except that it scans out only from the left image to produce both images of a stereo frame.

This member should be set only if the driver reports support for this option in the current display mode by setting the **Type** member of the [**D3DKMDT_VIDPN_SOURCE_MODE**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md) structure to **D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN**.

## -field FlipStereoPreferRight

Specifies that when the driver clones a stereo primary allocation to a mono monitor, it uses the right image.

The **FlipStereoTemporaryMono** and **FlipStereoPreferRight** members cannot both be set at the same time.

## -field RetryAtLowerIrql

The scheduler sets this flag if the call is made at PASSIVE_LEVEL. Hence, the driver can perform hardware changes in this call.

## -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF8) of the 32-bit **Value** member to zeros.

## -field Value

An alternative way to access the bits.

## -see-also

[**D3DKMDT_VIDPN_SOURCE_MODE**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md)

[**DXGK_PLANE_SPECIFIC_INPUT_FLAGS**](ns-d3dkmddi-_dxgk_plane_specific_input_flags.md)

[**DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](ns-d3dkmddi-_dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay3.md)

[**DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3**](nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md)
