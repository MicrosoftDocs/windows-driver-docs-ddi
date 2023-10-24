---
UID: NE:iddcx.IDDCX_METADATA2_VALID_FLAGS
tech.root: display
title: IDDCX_METADATA2_VALID_FLAGS
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_METADATA2_VALID_FLAGS enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_METADATA2_VALID_FLAGS
f1_keywords:
 - IDDCX_METADATA2_VALID_FLAGS
 - iddcx/IDDCX_METADATA2_VALID_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_METADATA2_VALID_FLAGS
---

## -description

A **IDDCX_METADATA2_VALID_FLAGS** enumeration value indicates which fields in an [**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md) structure have valid content.

## -enum-fields

### -field IDDCX_METADATA2_VALID_FLAGS_NONE:0

Indicates that none of the optional fields in **IDDCX_METADATA2** contain valid data and they should not be referenced.

### -field IDDCX_METADATA2_VALID_FLAGS_SYSTEMBUFFERINFO:0x1

When set, [**IDDCX_METADATA2::SystemBufferInfo**](ns-iddcx-iddcx_metadata2.md) contains valid data. The OS sets this flag in response to a driver setting [**IDARG_IN_RELEASEANDACQUIREBUFFER2::AcquireSystemMemoryBuffer**](ns-iddcx-idarg_in_releaseandacquirebuffer2.md) to TRUE.

### -field IDDCX_METADATA2_VALID_FLAGS_HDR10METADATA:0x2

When set, [**IDDCX_METADATA2::Hdr10FrameMetaData**](ns-iddcx-iddcx_metadata2.md) contains valid data.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_OUT_RELEASEANDACQUIREBUFFER2**](ns-iddcx-idarg_out_releaseandacquirebuffer2.md)

[**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
