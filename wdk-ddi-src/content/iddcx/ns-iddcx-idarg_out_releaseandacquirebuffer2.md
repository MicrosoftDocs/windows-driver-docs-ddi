---
UID: NS:iddcx.IDARG_OUT_RELEASEANDACQUIREBUFFER2
tech.root: display
title: IDARG_OUT_RELEASEANDACQUIREBUFFER2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDARG_OUT_RELEASEANDACQUIREBUFFER2 structure.
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
 - IDARG_OUT_RELEASEANDACQUIREBUFFER2
f1_keywords:
 - IDARG_OUT_RELEASEANDACQUIREBUFFER2
 - iddcx/IDARG_OUT_RELEASEANDACQUIREBUFFER2
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_OUT_RELEASEANDACQUIREBUFFER2
---

## -description

The **IDARG_OUT_RELEASEANDACQUIREBUFFER2** structure contains output arguments for the [**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md) function.

## -struct-fields

### -field MetaData

[out] An [**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md) structure containing the metadata that accompanies the new buffer.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_IN_RELEASEANDACQUIREBUFFER2**](ns-iddcx-idarg_in_releaseandacquirebuffer2.md)

[**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
