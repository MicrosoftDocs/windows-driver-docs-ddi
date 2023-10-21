---
UID: NS:iddcx.IDDCX_HDR10_METADATA
tech.root: display
title: IDDCX_HDR10_METADATA
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_HDR10_METADATA structure.
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
 - IDDCX_HDR10_METADATA
f1_keywords:
 - IDDCX_HDR10_METADATA
 - iddcx/IDDCX_HDR10_METADATA
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_HDR10_METADATA
---

## -description

The **IDDCX_HDR10_METADATA** structure contains the HDR10 metadata.

## -struct-fields

### -field RedPrimary[2]

The chromaticity coordinates of the red value in the CIE1931 color space. Index 0 contains the X coordinate and index 1 contains the Y coordinate. The values are normalized to 50,000; that is, 1 == 0.00002.

### -field GreenPrimary[2]

The chromaticity coordinates of the green value in the CIE1931 color space. Index 0 contains the X coordinate and index 1 contains the Y coordinate. The values are normalized to 50,000; that is, 1 == 0.00002.

### -field BluePrimary[2]

The chromaticity coordinates of the blue value in the CIE1931 color space. Index 0 contains the X coordinate and index 1 contains the Y coordinate. The values are normalized to 50,000; that is, 1 == 0.00002.

### -field WhitePoint[2]

The chromaticity coordinates of the white point in the CIE1931 color space. Index 0 contains the X coordinate and index 1 contains the Y coordinate. The values are normalized to 50,000; that is, 1 == 0.00002.

### -field MaxMasteringLuminance

The maximum number of nits of the display used to master the content. This value is in whole nits.

### -field MinMasteringLuminance

The minimum number of nits of the display used to master the content. The value is normalized to 10,000, i.e. 1 == 0.0001.

### -field MaxContentLightLevel

The maximum content light level (MaxCLL). This is the nit value corresponding to the brightest pixel used anywhere in the content. This value is in whole nits.

### -field MaxFrameAverageLightLevel

The maximum frame average light level (MaxFALL). This is the nit value corresponding to the average luminance of the frame that has the brightest average luminance anywhere in the content. This value is in whole nits.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA**](ne-iddcx-evt_idd_cx_monitor_set_default_hdr_metadata.md)

[**IDARG_IN_MONITOR_SET_DEFAULT_HDR_METADATA**](ns-iddcx-idarg_in_monitor_set_default_hdr_metadata.md)

[**IDARG_OUT_RELEASEANDACQUIREBUFFER2**](ns-iddcx-idarg_out_releaseandacquirebuffer2.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
