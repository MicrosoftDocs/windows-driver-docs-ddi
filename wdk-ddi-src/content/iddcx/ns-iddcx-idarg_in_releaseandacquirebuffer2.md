---
UID: NS:iddcx.IDARG_IN_RELEASEANDACQUIREBUFFER2
tech.root: display
title: IDARG_IN_RELEASEANDACQUIREBUFFER2
ms.date: 02/17/2026
targetos: Windows
description: Learn more about the IDARG_IN_RELEASEANDACQUIREBUFFER2 structure.
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
 - IDARG_IN_RELEASEANDACQUIREBUFFER2
f1_keywords:
 - IDARG_IN_RELEASEANDACQUIREBUFFER2
 - iddcx/IDARG_IN_RELEASEANDACQUIREBUFFER2
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_IN_RELEASEANDACQUIREBUFFER2
---

## -description

The **IDARG_IN_RELEASEANDACQUIREBUFFER2** structure contains input arguments for the [**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md) function.

## -struct-fields

### -field Size

[in] Total size of this structure, in bytes.

### -field AcquireSystemMemoryBuffer

[in] Boolean value. When a driver sets this field to TRUE, the OS fills out an [**IDDCX_SYSTEM_BUFFER_INFO**](ns-iddcx-iddcx_system_buffer_info.md) structure in [**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md). This is equivalent to a pre-1.10 driver calling [**IddCxSwapChainReleaseAndAcquireSystemBuffer**](nf-iddcx-iddcxswapchainreleaseandacquiresystembuffer.md) instead of [**IddCxSwapChainReleaseAndAcquireBuffer**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer.md).

### -field pD3D12CommandQueue

Pointer to an [ID3D12CommandQueue] object used to submit commands that use the swap chain surface as input.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

In order to support D3D12, the **IDARG_IN_RELEASEANDACQUIREBUFFER2** structure used in calls to [**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md) has been extended. Drivers supporting D3D12 that passed an **ID3D12Device** in a call to [**IddCxSwapChainSetDevice2**](nf-iddcx-iddcxswapchainsetdevice2.md) must provide a **ID3D12CommandQueue** object that's used to read from the swap chain surface. The driver must also pass the extended [**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md) structure with the **IDDCX_METADATA2::Size** field set correctly so the OS can set a new valid flag and the new D3D12 surface field.

For more information about D3D12 support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.11-updates).

## -see-also

[**IDARG_OUT_RELEASEANDACQUIREBUFFER2**](ns-iddcx-idarg_out_releaseandacquirebuffer2.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
