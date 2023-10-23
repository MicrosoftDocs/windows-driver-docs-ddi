---
UID: NS:iddcx.IDDCX_WIRE_BITS_PER_COMPONENT
tech.root: display
title: IDDCX_WIRE_BITS_PER_COMPONENT
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_WIRE_BITS_PER_COMPONENT structure.
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
 - IDDCX_WIRE_BITS_PER_COMPONENT
f1_keywords:
 - IDDCX_WIRE_BITS_PER_COMPONENT
 - iddcx/IDDCX_WIRE_BITS_PER_COMPONENT
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_WIRE_BITS_PER_COMPONENT
---

## -description

The **IDDCX_WIRE_BITS_PER_COMPONENT** structure identifies the dithering support of a target.

## -struct-fields

### -field Rgb

An [**IDDCX_BITS_PER_COMPONENT**](ne-iddcx-iddcx_bits_per_component.md) value that describes the supported/requested pixel encoding using RGB sample format.

### -field YCbCr444

An [**IDDCX_BITS_PER_COMPONENT**](ne-iddcx-iddcx_bits_per_component.md) value that describes the supported/requested pixel encoding using YCbCr 4:4:4 sample format.

### -field YCbCr422

An [**IDDCX_BITS_PER_COMPONENT**](ne-iddcx-iddcx_bits_per_component.md) value that describes the supported/requested pixel encoding using YCbCr 4:2:2 sample format.

### -field YCbCr420

An [**IDDCX_BITS_PER_COMPONENT**](ne-iddcx-iddcx_bits_per_component.md) value that describes the supported/requested pixel encoding using YCbCr 4:2:0 sample format.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO**](nc-iddcx-evt_idd_cx_adapter_query_target_info.md)

[**IDARG_OUT_QUERYTARGET_INFO**](ns-iddcx-idarg_out_querytarget_info.md)
