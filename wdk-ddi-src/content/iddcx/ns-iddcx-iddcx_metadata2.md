---
UID: NS:iddcx.IDDCX_METADATA2
tech.root: display
title: IDDCX_METADATA2
ms.date: 02/17/2026
targetos: Windows
description: Learn more about the IDDCX_METADATA2 structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, 26H1 (IddCx 1.11)
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_METADATA2
f1_keywords:
 - IDDCX_METADATA2
 - iddcx/IDDCX_METADATA2
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_METADATA2
---

## -description

**IDDCX_METADATA2** provides information about the current provided surface and what is displayed on it.

## -struct-fields

### -field Size

Total size of the structure, in bytes.

### -field ValidFlags

A bitwise-OR of [**IDDCX_METADATA2_VALID_FLAGS**](ne-iddcx-iddcx_metadata2_valid_flags.md) values that indicate which fields in this structure have valid content.

### -field PresentationFrameNumber

Presentation frame number of this surface.

### -field DirtyRectCount

Number of dirty rects for this frame. Call [**IddCxSwapChainGetDirtyRects**](nf-iddcx-iddcxswapchaingetdirtyrects.md) to get the dirty rects.

A **DirtyRectCount** of 1, where the single dirty rect has all values set to zero, indicates that there has not been any image updates from the previous frame. In this situation, the driver has the opportunity to re-encode the desktop image again to increase the visual quality. Once there are no more updates, the OS presents the same frame as many times as indicated by the [**IDDCX_ADAPTER_CAPS::StaticDesktopReencodeFrameCount**](ns-iddcx-iddcx_adapter_caps.md) value , then stops presenting until the next update.

### -field HwProtectedSurface

Indicates whether the provided surface is hardware protected.

### -field PresentDisplayQPCTime

System QPC time of when this surface should be displayed on the indirect display monitor.

### -field pSurface

Pointer to a [**IDXGIResource**](/windows/win32/api/dxgi/nn-dxgi-idxgiresource) DX surface that contains the image to encode and transmit. The driver can use this DX surface anytime until [**IddCxSwapChainReleaseAndAcquire**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md) is called again.

### -field SurfaceColorSpace

A [**DXGI_COLOR_SPACE_TYPE**](/windows/win32/api/dxgicommon/ne-dxgicommon-dxgi_color_space_type) value that indicates the color space of the provided surface. The color space typically matches that specified in the committed path.

### -field SdrWhiteLevel

The white level in nits for any SDR content; for example, the mouse cursor. This value always defaults to 80 nits for non-HDR modes.

### -field SystemBufferInfo

An [**IDDCX_SYSTEM_BUFFER_INFO**](ns-iddcx-iddcx_system_buffer_info.md) structure in which the resulting information from the [release and acquire operation](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
 is returned.

### -field Hdr10FrameMetaData

An [**IDDCX_HDR10_FRAME_METADATA**](ns-iddcx-iddcx_hdr10_frame_metadata.md) structure that contains the HDR10 metadata to use with this frame.

### -field pD3D12Surface

Pointer to an [**ID3D12Resource**](/windows/win32/api/d3d12/nn-d3d12-id3d12resource) that contains the image to encode and transmit. The driver can use this surface anytime until [IddCxSwapChainReleaseAndAcquireBuffer2](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md) is called again.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

When D3D12 swap chain surfaces are provided to a driver, there's some extra data that must be passed to the OS to ensure access to the surface is synchronized correctly with the OS. The [**ID3D12CommandQueue**](/windows/win32/api/d3d12/nn-d3d12-id3d12commandqueue) object the driver submits commands on that use the swap chain surface as an input must be indicated to the OS so it can correctly synchronize the driver reads with the OS writes.

At the point the driver calls [**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md), the OS uses this call as an indication that the driver is ready to submit work that uses the swap chain surface. If the driver submits other work to the same command queue, this could be delayed unnecessarily.

## -see-also

[**IDARG_OUT_RELEASEANDACQUIREBUFFER2**](ns-iddcx-idarg_out_releaseandacquirebuffer2.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
