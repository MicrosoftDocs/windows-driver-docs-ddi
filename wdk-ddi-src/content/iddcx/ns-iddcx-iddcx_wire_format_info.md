---
UID: NS:iddcx.IDDCX_WIRE_FORMAT_INFO
tech.root: display
title: IDDCX_WIRE_FORMAT_INFO
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_WIRE_FORMAT_INFO structure.
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
 - IDDCX_WIRE_FORMAT_INFO
f1_keywords:
 - IDDCX_WIRE_FORMAT_INFO
 - iddcx/IDDCX_WIRE_FORMAT_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_WIRE_FORMAT_INFO
---

## -description

The **IDDCX_WIRE_FORMAT_INFO** structure contains details about the signal to send to the monitor.

## -struct-fields

### -field ColorSpace

An [**IDDCX_COLOR_SPACE**](ne-iddcx-iddcx_color_space.md) value that specifies the color space to use on the monitor.

### -field BitsPerComponent

An [**IDDCX_WIRE_BITS_PER_COMPONENT**](ns-iddcx-iddcx_wire_bits_per_component.md) value that specifies the number of bits per component and which pixel encoding to use on the monitor.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_ADAPTER_COMMIT_MODES2**](nc-iddcx-evt_idd_cx_adapter_commit_modes2.md)

[**IDARG_IN_COMMITMODES2**](ns-iddcx-idarg_in_commitmodes2.md)

[**IDDCX_PATH2**](ns-iddcx-iddcx_path2.md)
