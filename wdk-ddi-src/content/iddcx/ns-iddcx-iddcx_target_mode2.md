---
UID: NS:iddcx.IDDCX_TARGET_MODE2
tech.root: display
title: IDDCX_TARGET_MODE2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_TARGET_MODE2 structure.
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
 - IDDCX_TARGET_MODE2
f1_keywords:
 - IDDCX_TARGET_MODE2
 - iddcx/IDDCX_TARGET_MODE2
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_TARGET_MODE2
---

## -description

**IDDCX_TARGET_MODE2** provides information about a target mode.

## -struct-fields

### -field Size

Size in bytes of this structure.

### -field TargetVideoSignalInfo

A [**DISPLAYCONFIG_TARGET_MODE**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_target_mode) structure that describes the display path target mode, including information about the video signal for the display.

### -field RequiredBandwidth

The display pipeline bandwidth required for this mode. The driver reports pipeline bandwidth in [**IDDCX_ADAPTER_CAPS**](nc-iddcx-iddcx_adapter_caps.md)**.MaxDisplayPipelineRate**. The OS will never pick a combination of modes across all targets that exceeds this value.

### -field BitsPerComponent

An [**IDDCX_WIRE_BITS_PER_COMPONENT**](ns-iddcx-iddcx_wire_bits_per_component.md) value that specifies how many bits per component can be used to send pixels of each format to a monitor.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md)

[**IDDCX_ADAPTER_CAPS**](ns-iddcx-iddcx_adapter_caps.md)

[**IddCxMonitorUpdateModes2**](nf-iddcx-iddcxmonitorupdatemodes2.md)
