---
UID: NS:iddcx.IDARG_IN_RELEASEANDACQUIREBUFFER2
tech.root: display
title: IDARG_IN_RELEASEANDACQUIREBUFFER2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDARG_IN_RELEASEANDACQUIREBUFFER2 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
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

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_OUT_RELEASEANDACQUIREBUFFER2**](ns-iddcx-idarg_out_releaseandacquirebuffer2.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
