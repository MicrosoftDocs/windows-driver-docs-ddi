---
UID: NS:iddcx.IDARG_IN_PARSEMONITORDESCRIPTION2
tech.root: display
title: IDARG_IN_PARSEMONITORDESCRIPTION2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDARG_IN_PARSEMONITORDESCRIPTION2 structure.
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
 - IDARG_IN_PARSEMONITORDESCRIPTION2
f1_keywords:
 - IDARG_IN_PARSEMONITORDESCRIPTION2
 - iddcx/IDARG_IN_PARSEMONITORDESCRIPTION2
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_IN_PARSEMONITORDESCRIPTION2
---

## -description

The **IDARG_IN_PARSEMONITORDESCRIPTION2** structure contains input arguments for the [**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2**](nc-iddcx-evt_idd_cx_parse_monitor_description2.md) callback function, which allows a driver to report extra information needed for HDR10 or WCG monitor modes.

## -struct-fields

### -field MonitorDescription

[in] An [**IDDCX_MONITOR_DESCRIPTION**](ns-iddcx-iddcx_monitor_description.md) structure that describes the monitor.

### -field MonitorModeBufferInputCount

[in] The number of monitor modes that the **pMonitorModes** buffer being passed into the driver can hold. A value of zero indicates that the driver shouldn't copy the monitor mode list into the buffer that **pMonitorModes** points to, and should instead set the [**MonitorModeBufferOutputCount**](ns-iddcx-idarg_out_parsemonitordescription.md) output value to indicate the size of buffer required to store the modes.

### -field pMonitorModes

[out] Pointer to a buffer of [**IDDCX_MONITOR_MODE2**](ns-iddcx-iddcx_monitor_mode2.md) structures in which the driver should copy the monitor modes to if the value is non-NULL. If **pMonitorModes** is NULL, the driver shouldn't copy the monitor mode list, and should instead set the [**MonitorModeBufferOutputCount**](ns-iddcx-idarg_out_parsemonitordescription.md) output value to indicate the size of buffer required to store the modes.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2**](nc-iddcx-evt_idd_cx_parse_monitor_description2.md)

[**IDARG_OUT_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_out_parsemonitordescription.md)

[**IDDCX_MONITOR_DESCRIPTION**](ns-iddcx-iddcx_monitor_description.md)

[**IDDCX_MONITOR_MODE2**](ns-iddcx-iddcx_monitor_mode2.md)
