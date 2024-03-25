---
UID: NS:iddcx.IDARG_OUT_PARSEMONITORDESCRIPTION
title: IDARG_OUT_PARSEMONITORDESCRIPTION (iddcx.h)
description: Learn more about the IDARG_OUT_PARSEMONITORDESCRIPTION structure.
tech.root: display
ms.date: 09/22/2023
keywords: ["IDARG_OUT_PARSEMONITORDESCRIPTION structure"]
ms.keywords: IDARG_OUT_PARSEMONITORDESCRIPTION, IDARG_OUT_PARSEMONITORDESCRIPTION structure [Display Devices], display.idarg_out_parsemonitordescription, iddcx/IDARG_OUT_PARSEMONITORDESCRIPTION
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDARG_OUT_PARSEMONITORDESCRIPTION
 - iddcx/IDARG_OUT_PARSEMONITORDESCRIPTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_OUT_PARSEMONITORDESCRIPTION
---

# IDARG_OUT_PARSEMONITORDESCRIPTION structure

## -description

The **IDARG_OUT_PARSEMONITORDESCRIPTION** structures provides information about the number of monitor modes and preferred monitor mode of a monitor.

## -struct-fields

### -field MonitorModeBufferOutputCount

[out] If the **pMonitorModes** value of [**IDARG_IN_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_in_parsemonitordescription.md) - or [**IDARG_IN_PARSEMONITORDESCRIPTION2**](ns-iddcx-idarg_in_parsemonitordescription2.md) for HDR support - is NULL, then the driver should set **MonitorModeBufferOutputCount** to the number of monitor modes the driver would generate for the specified monitor description. If **pMonitorModes** is non-NULL then **MonitorModeBufferOutputCount** specifies the count of the monitor modes that the driver copied to the buffer that **pMonitorModes** points to.

### -field PreferredMonitorModeIdx

[out] Index into the **pMonitorModes** array of the preferred mode monitor mode. The driver can set this value to **NO_PREFERRED_MODE** to indicate that there is no preferred monitor mode.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION**](nc-iddcx-evt_idd_cx_parse_monitor_description.md)

[**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2**](nc-iddcx-evt_idd_cx_parse_monitor_description2.md)

[**IDARG_IN_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_in_parsemonitordescription.md)

[**IDARG_IN_PARSEMONITORDESCRIPTION2**](ns-iddcx-idarg_in_parsemonitordescription2.md)
