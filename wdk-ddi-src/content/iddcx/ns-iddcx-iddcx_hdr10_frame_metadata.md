---
UID: NS:iddcx.IDDCX_HDR10_FRAME_METADATA
tech.root: display
title: IDDCX_HDR10_FRAME_METADATA
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_HDR10_FRAME_METADATA structure.
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
 - IDDCX_HDR10_FRAME_METADATA
f1_keywords:
 - IDDCX_HDR10_FRAME_METADATA
 - iddcx/IDDCX_HDR10_FRAME_METADATA
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_HDR10_FRAME_METADATA
---

## -description

The **IDDCX_HDR10_FRAME_METADATA** structure contains HDR10 metadata to use with a frame.

## -struct-fields

### -field Type

An [**IDDCX_HDR10_FRAME_METADATA_TYPE**](ne-iddcx-iddcx_hdr10_frame_metadata_type.md) value that tells the driver which type of HDR10 metadata to use with this frame.

### -field NewMetaData

If **Type** is **IDDCX_HDR10_FRAME_METADATA_TYPE_NEW**, **NewMetaData** is an [**IDDCX_HDR10_METADATA**](ns-iddcx-iddcx_hdr10_metadata.md) structure that contains the new metadata block to use with this frame.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDARG_OUT_RELEASEANDACQUIREBUFFER2**](ns-iddcx-idarg_out_releaseandacquirebuffer2.md)

[**IDDCX_HDR10_FRAME_METADATA_TYPE**](ne-iddcx-iddcx_hdr10_frame_metadata_type.md)

[**IDDCX_HDR10_METADATA**](ns-iddcx-iddcx_hdr10_metadata.md)

[**IDDCX_METADATA2**](ns-iddcx-iddcx_metadata2.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
