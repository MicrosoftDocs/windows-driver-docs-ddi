---
UID: NS:iddcx.IDDCX_MONITOR_MODE
title: IDDCX_MONITOR_MODE (iddcx.h)
description: Gives information about the current monitor mode.
old-location: display\iddcx_monitor_mode.htm
tech.root: display
ms.date: 09/22/2023
keywords: ["IDDCX_MONITOR_MODE structure"]
ms.keywords: IDDCX_MONITOR_MODE, IDDCX_MONITOR_MODE structure [Display Devices], display.iddcx_monitor_mode, iddcx/IDDCX_MONITOR_MODE
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
 - IDDCX_MONITOR_MODE
 - iddcx/IDDCX_MONITOR_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_MONITOR_MODE
---

# IDDCX_MONITOR_MODE structure

## -description

A **IDDCX_MONITOR_MODE** structure provides information about the current monitor mode.

## -struct-fields

### -field Size

Total size in bytes of this structure.

### -field Origin

A [**IDDCX_MONITOR_MODE_ORIGIN**](ne-iddcx-iddcx_monitor_mode_origin.md) value from which the driver derived this mode.

### -field MonitorVideoSignalInfo

A [**DISPLAYCONFIG_VIDEO_SIGNAL_INFO**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info) structure that provides the details of the Monitor mode.

**MonitorVideoSignalInfo.AdditionalSignalInfo**'s union value of **vSyncFreqDivider** must be zero.

## -see-also

[**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION**](nc-iddcx-evt_idd_cx_parse_monitor_description.md)

[**IDARG_IN_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_in_parsemonitordescription.md)

[**IDARG_OUT_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_out_parsemonitordescription.md)
