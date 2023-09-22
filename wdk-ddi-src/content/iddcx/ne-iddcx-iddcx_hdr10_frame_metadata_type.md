---
UID: NE:iddcx.IDDCX_HDR10_FRAME_METADATA_TYPE
tech.root: display
title: IDDCX_HDR10_FRAME_METADATA_TYPE
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_HDR10_FRAME_METADATA_TYPE enumeration.
prerelease: true
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
 - IDDCX_HDR10_FRAME_METADATA_TYPE
f1_keywords:
 - IDDCX_HDR10_FRAME_METADATA_TYPE
 - iddcx/IDDCX_HDR10_FRAME_METADATA_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_HDR10_FRAME_METADATA_TYPE
---

## -description

A **IDDCX_HDR10_FRAME_METADATA_TYPE** enumeration value tells the driver which type of HDR10 metadata to use with a frame.

## -enum-fields

### -field IDDCX_HDR10_FRAME_METADATA_TYPE_UNINITIALIZED:0

Indicates that an **IDDCX_HDR10_FRAME_METADATA_TYPE** variable has not yet been assigned a meaningful value.

### -field IDDCX_HDR10_FRAME_METADATA_TYPE_DEFAULT:1

Indicates that the driver should use the data last sent by the OS in a call to [**EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA**](nc-iddcx-evt_idd_cx_monitor_set_default_hdr_metadata.md) for the monitor associated with this swapchain.

### -field IDDCX_HDR10_FRAME_METADATA_TYPE_UNCHANGED:2

Indicates the driver should use the same HDR metadata that was used with the last frame (either default or new from the older frame).

### -field IDDCX_HDR10_FRAME_METADATA_TYPE_NEW:3

Indicates to the driver that the accompanying [**IDDCX_HDR10_FRAME_METADATA::NewMetaData**](ns-iddcx-iddcx_hdr10_frame_metadata.md) contains valid metadata to use with this frame. The driver must also keep this metadata in case the next **IDDCX_HDR10_FRAME_METADATA_TYPE** is **IDDCX_HDR10_FRAME_METADATA_TYPE_UNCHANGED**. This metadata should not replace the metadata sent in a call to [**EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA**](nc-iddcx-evt_idd_cx_monitor_set_default_hdr_metadata.md).

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_MONITOR_SET_DEFAULT_HDR_METADATA**](nc-iddcx-evt_idd_cx_monitor_set_default_hdr_metadata.md)

[**IDDCX_HDR10_FRAME_METADATA**](ns-iddcx-iddcx_hdr10_frame_metadata.md)

[**IDARG_OUT_RELEASEANDACQUIREBUFFER2**](ns-iddcx-idarg_out_releaseandacquirebuffer2.md)

[**IddCxSwapChainReleaseAndAcquireBuffer2**](nf-iddcx-iddcxswapchainreleaseandacquirebuffer2.md)
