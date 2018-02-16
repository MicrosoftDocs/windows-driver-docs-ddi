---
UID: NS:d3dkmddi._DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
title: "_DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS"
author: windows-driver-content
description: A structure containing the set of flags needed to set the VidPN source address.
old-location: display\dxgk_setvidpnsourceaddress_input_flags.htm
old-project: display
ms.assetid: FBC661AA-B028-45AF-8E3C-7C2472652BD5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS, DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS structure [Display Devices], display.dxgk_setvidpnsourceaddress_input_flags, _DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS, d3dkmddi/DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
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
-	DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS
---

# _DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS structure


## -description


A structure containing the set of flags needed to set the VidPN source address.


## -syntax


````
typedef struct _DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS {
  union {
    struct {
      UINT FlipStereo  :1;
      UINT FlipStereoTemporaryMono  :1;
      UINT FlipStereoPreferRight   :1;
      UINT RetryAtLowerIrql  :1;
      UINT Reserved  :28;
    };
    UINT Value;
  };
} DXGK_SETVIDPNSOURCEADDRESS_INPUT_FLAGS;
````


## -struct-fields




### -field FlipStereo

Specifies whether the driver flips both left and right images of a stereo allocation.

If the FlipOnNextVSync member of the DXGK_PLANE_SPECIFIC_INPUT_FLAGS structure is set, the driver completes the flip to the left image on the next VSync and then completes the flip to the right image on the following VSync.

If the FlipImmediate member of the DXGK_PLANE_SPECIFIC_INPUT_FLAGS structure is set, the driver immediately starts to scan out from the new allocation. For example, if the driver was scanning a right image, it starts the new scan from the same relative offset in the right image of the new allocation.

<div class="alert"><b>Note</b>  The FlipStereo and FlipStereoTemporaryMono members cannot both be set at the same time.</div>
<div> </div>

### -field FlipStereoTemporaryMono

Specifies whether the driver uses the left image of a stereo allocation for the right and left portions of a stereo frame. The driver performs the same present operation as with FlipStereo, except that it scans out only from the left image to produce both images of a stereo frame.

This member should be set only if the driver reports support for this option in the current display mode by setting the Type member of the D3DKMDT_VIDPN_SOURCE_MODE structure to D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN.


### -field FlipStereoPreferRight

Specifies that when the driver clones a stereo primary allocation to a mono monitor, it uses the right image.

<div class="alert"><b>Note</b>  The FlipStereoTemporaryMono and FlipStereoPreferRight members cannot both be set at the same time.</div>
<div> </div>

### -field RetryAtLowerIrql

The scheduler sets this flag if the call is made at PASSIVE_LEVEL. Hence, the driver can perform hardware changes in this call


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.


### -field Value

