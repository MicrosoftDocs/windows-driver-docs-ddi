---
UID: NS:iddcx.IDDCX_MONITOR_MODE2
tech.root: display
title: IDDCX_MONITOR_MODE2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_MONITOR_MODE2 structure.
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
 - IDDCX_MONITOR_MODE2
f1_keywords:
 - IDDCX_MONITOR_MODE2
 - iddcx/IDDCX_MONITOR_MODE2
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_MONITOR_MODE2
---

## -description

The **IDDCX_MONITOR_MODE2** structure contains information about a monitor mode.

## -struct-fields

### -field Size

Size in bytes of this structure.

### -field Origin

An [**IDDCX_MONITOR_MODE_ORIGIN**](ne-iddcx-iddcx_monitor_mode_origin.md) value that identifies where the driver derived the mode from.

### -field MonitorVideoSignalInfo

A [**DISPLAYCONFIG_VIDEO_SIGNAL_INFO**](/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info) structure that contains details about the monitor mode. **AdditionalSignalInfo.vSyncFreqDivider** must be set to zero.

### -field BitsPerComponent

A [**IDDCX_WIRE_BITS_PER_COMPONENT**](ns-iddcx-iddcx_wire_bits_per_component.md) structure that specifies the number of bits per component that can be used to send pixels of each format to a monitor.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2**](nc-iddcx-evt_idd_cx_parse_monitor_description2.md)

[**IDARG_IN_PARSEMONITORDESCRIPTION2**](ns-iddcx-idarg_in_parsemonitordescription2.md)

[**IDARG_OUT_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_out_parsemonitordescription.md)
