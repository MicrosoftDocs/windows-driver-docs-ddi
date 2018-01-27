---
UID: NS:d3dkmddi._DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
title: _DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
author: windows-driver-content
description: A structure containing the flags that apply to a plane set by the driver.
old-location: display\dxgk_plane_specific_output_flags.htm
old-project: display
ms.assetid: 95D9C564-92F3-4165-8063-49D928F30475
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS, d3dkmddi/DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS, DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS structure [Display Devices], display.dxgk_plane_specific_output_flags, DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS
---

# _DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS structure


## -description


A structure containing the flags that apply to a plane set by the driver. 


## -syntax


````
typedef struct _DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS {
  union {
    struct {
      UINT FlipConvertedToImmediate  :1;
      UINT  PostPresentNeeded  :1;
      UINT HsyncInterruptCompletion  :1;
      UINT Reserved  :29;
    };
    UINT Value;
  };
} DXGK_PLANE_SPECIFIC_OUTPUT_FLAGS;
````


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


