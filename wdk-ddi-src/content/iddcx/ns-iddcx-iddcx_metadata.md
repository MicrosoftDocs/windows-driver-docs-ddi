---
UID: NS:iddcx.IDDCX_METADATA
title: IDDCX_METADATA (iddcx.h)
description: Gives information about the current provided surface and what is displayed on it.
old-location: display\iddcx_metadata.htm
tech.root: display
ms.assetid: 7128e49d-71e9-4014-9f08-591cfaeba363
ms.date: 05/10/2018
keywords: ["IDDCX_METADATA structure"]
ms.keywords: IDDCX_METADATA, IDDCX_METADATA structure, IDDCX_METADATA structure [Display Devices], IDDCX_METADATA structure pointer [Display Devices], IDDCX_METADATA structure structure [Display Devices], display.iddcx_metadata, iddcx/IDDCX_METADATA
req.header: iddcx.h
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
req.typenames: 
f1_keywords:
 - IDDCX_METADATA
 - iddcx/IDDCX_METADATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_METADATA
---

# IDDCX_METADATA structure


## -description

                 Gives information about the current provided surface and what is displayed on it.

## -struct-fields

### -field Size

                     Total size of the structure

### -field PresentationFrameNumber

                     Presentation frame number of this surface. If the frame number is the same as the previous frame, then it indicates that there has not been any image updates from the previous frame. This is an opportunity for the driver to re-encode the desktop image again to increase the visual quality. Once there are no more updates, the OS presents the same frame as many times indicated by the <a href="/windows-hardware/drivers/ddi/iddcx/ns-iddcx-iddcx_adapter_caps">IDDCX_ADAPTER_CAPS</a> value <b>StaticDesktopReencodeFrameCount</b> , then stops presenting until the next update

### -field DirtyRectCount

                      Number of dirty rects for this frame. Call <a href="/windows-hardware/drivers/ddi/iddcx/nf-iddcx-iddcxswapchaingetdirtyrects">IddCxSwapChainGetDirtyRects</a> to get the dirty rects
                 

<div class="alert"><b>Note</b>   A zero <b>DirtyRectCount</b> and <b>MoveRegionCount</b> value indicates there were no desktop updates and the
    PresentationFrameNumber is the same as last frame</div>
<div> </div>

### -field MoveRegionCount

                     Number of move regions in this frame, call <a href="/windows-hardware/drivers/ddi/iddcx/nf-iddcx-iddcxswapchaingetmoveregions">IddCxSwapChainGetMoveRegions</a> to get the move regions
                 

<div class="alert"><b>Note</b>   A zero <b>DirtyRectCount</b> and <b>MoveRegionCount</b> value indicates there were no desktop updates and the
    PresentationFrameNumber is the same as last frame</div>
<div> </div>

### -field HwProtectedSurface

                      Indicates if the provided surface is hardware protected or not

### -field PresentDisplayQPCTime

                     System QPC time of when this surface should be displayed on the indirect display monitor

### -field pSurface

                     DX surface that contains the image to encode and transmit. The driver can use this DX surface anytime until <a href="/windows-hardware/drivers/ddi/iddcx/nf-iddcx-iddcxswapchainreleaseandacquirebuffer">IddCxSwapChainReleaseAndAcquire</a> is called again

<div class="alert"><b>Note</b>  This surface is always a A8R8G8B8 formated surface</div>
<div> </div>