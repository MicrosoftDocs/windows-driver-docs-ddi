---
UID: NS:d3dkmddi._DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
title: _DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS (d3dkmddi.h)
description: A structure containing the flags that apply to a plane set by the driver.
old-location: display\dxgk_plane_specific_output_flags.htm
ms.assetid: 95D9C564-92F3-4165-8063-49D928F30475
ms.date: 05/10/2018
keywords: ["DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS structure"]
ms.keywords: DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS, DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS structure [Display Devices], _DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS, d3dkmddi/DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS, display.dxgk_plane_specific_output_flags
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
req.typenames: DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
f1_keywords:
 - _DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
 - d3dkmddi/_DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
 - DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
 - d3dkmddi/DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
---

# _DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS structure


## -description

A structure containing the flags that apply to a plane set by the driver.

## -struct-fields

### -field FlipConvertedToImmediate

Indicates that the flip was converted to an immediate flip rather than a VSYNC flip. The driver sets FlipConvertedToImmediate when the current line is less than DXGK_MULTIPLANE_OVERLAY_PLANE3.MaxImmediateFlipLine.

### -field PostPresentNeeded

  Indicates that scheduler must call DXGDDI_POSTMULTIPLANEOVERLAYPRESENT for this specific plane. The driver must only set this flag for immediate flips.

### -field HsyncInterruptCompletion

Indicates that the scheduler should not assume that the immediate flip for this plane is completed upon the return from DdiSetVidPnSourceAddressWithMultiPlaneOverlay3 DDI. . Instead, the OS will only assume the immediate flip is completed when it receives a CrtcVsyncWithMultiPlaneOverlay2 interrupt notification with the PresentId greater or equal to pending immediate flip request. CrtcVsyncWithMultiPlaneOverlay2 interrupt notification for this flip may be an HsyncFlipCompletion, or it may be a regular VSync notification. The driver must only set this flag for immediate flips.

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 27 bits (0xFFFFFFE0) of the 32-bit <b>Value</b> member to zeros.

### -field Value

