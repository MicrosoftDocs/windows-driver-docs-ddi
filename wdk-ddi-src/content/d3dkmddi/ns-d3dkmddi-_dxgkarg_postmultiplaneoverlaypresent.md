---
UID: NS:d3dkmddi._DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
title: _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT (d3dkmddi.h)
description: Contains arguments for the DxgkDdiPostMultiPlaneOverlayPresent function.
old-location: display\dxgkarg_postmultiplaneoverlaypresent.htm
ms.date: 04/16/2018
keywords: ["DXGKARG_POSTMULTIPLANEOVERLAYPRESENT structure"]
ms.keywords: DXGKARG_POSTMULTIPLANEOVERLAYPRESENT, DXGKARG_POSTMULTIPLANEOVERLAYPRESENT structure [Display Devices], _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT, d3dkmddi/DXGKARG_POSTMULTIPLANEOVERLAYPRESENT, display.dxgkarg_postmultiplaneoverlaypresent
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
req.typenames: DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
f1_keywords:
 - _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
 - d3dkmddi/_DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
 - DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
 - d3dkmddi/DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
 - DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
---

# _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT structure


## -description

Contains arguments for the [DxgkDdiPostMultiPlaneOverlayPresent](nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md) function.

## -struct-fields

### -field VidPnTargetId [in]

The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs.

### -field PhysicalAdapterMask [in]

The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the ValidPhysicalAdapterMask bit-field flag in the Flags member.

### -field LayerIndex [in]

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.

### -field PresentID [in]

64 bit integer value representing each flip request for a particular MPO plane.

