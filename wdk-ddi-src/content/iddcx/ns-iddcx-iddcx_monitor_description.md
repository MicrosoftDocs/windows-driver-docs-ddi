---
UID: NS:iddcx.IDDCX_MONITOR_DESCRIPTION
title: IDDCX_MONITOR_DESCRIPTION (iddcx.h)
description: Gives information about the current monitor description.
prerelease: true
old-location: display\iddcx_monitor_description.htm
tech.root: display
ms.date: 02/17/2026
keywords: ["IDDCX_MONITOR_DESCRIPTION structure"]
ms.keywords: IDDCX_MONITOR_DESCRIPTION, IDDCX_MONITOR_DESCRIPTION structure [Display Devices], display.iddcx_monitor_description, iddcx/IDDCX_MONITOR_DESCRIPTION
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 11, 26H1 (IddCx 1.11)
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
 - IDDCX_MONITOR_DESCRIPTION
 - iddcx/IDDCX_MONITOR_DESCRIPTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_MONITOR_DESCRIPTION
---

# IDDCX_MONITOR_DESCRIPTION structure

## -description

A **IDDCX_MONITOR_DESCRIPTION** structure provides a monitor description.

## -struct-fields

### -field Size

Total size of the structure, in bytes.

### -field Type

A [**IDDCX_MONITOR_DESCRIPTION_TYPE**](ne-iddcx-iddcx_monitor_description_type.md) value that describes the monitor's type.

### -field DataSize

The size in bytes of the monitor description data that **pData** points to.

### -field pData

Pointer to the monitor description data. The data layout depends on **Type** as follows:

* If **Type** is IDDCX_MONITOR_DESCRIPTION_TYPE_EDID:
  * If **DataSize** > 0 and **pData** != NULL, **pData** points to an EDID data formatted monitor description.
  * If **DataSize** = 0 and **pData** = NULL, no monitor description is available.
* If **Type** is IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID_AND_EDID, the monitor description starts with a DisplayID description followed by EDID without any padding in between. The EDID format should contain all available data blocks and be present. The call to connect the monitor will fail if DisplayID is missing or invalid, or if EDID is missing.
* If **Type** is IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID, the monitor description data only contains a DisplayID descriptor. This type can be set by a driver when calling [**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md). It can also be set by the OS when calling [**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION**](nc-iddcx-evt_idd_cx_parse_monitor_description.md), [**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION2**](nc-iddcx-evt_idd_cx_parse_monitor_description2.md), [**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES**](nc-iddcx-evt_idd_cx_monitor_query_target_modes.md), or [**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md).

## -remarks

In order to support displays that only contain a DisplayID descriptor the **IDDCX_MONITOR_DESCRIPTION** structure has been updated. Specifically, a new IDDCX_MONITOR_DESCRIPTION_TYPE has been added to the [IDDCX_MONITOR_DESCRIPTION_TYPE](ne-iddcx-iddcx_monitor_description_type.md) enumeration.

Drivers must check for OS support for this functionality, that is, ensure IDDCX_DEVICE_FEATURES_1_11_DISPLAY_ID_ONLY is set in the data returned from a call to [**IddCxCheckOsFeatureSupport**](nf-iddcx-iddcxcheckosfeaturesupport.md). If the OS doesn't support this functionality, either because it doesn't support IddCx 1.11 or it supports 1.11 but the feature support isn't present, then sending DisplayID only descriptors is an error.

> [!NOTE]
> The **IDDCX_MONITOR_DESCRIPTION::pData** field isn't new, but the summary comments have been updated to reflect the new functionality.
## -see-also

[**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION**](nc-iddcx-evt_idd_cx_parse_monitor_description.md)

[**IddCxMonitorCreate**](nf-iddcx-iddcxmonitorcreate.md)
