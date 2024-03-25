---
UID: NS:wdm.BATTERY_REPORTING_SCALE
title: BATTERY_REPORTING_SCALE (wdm.h)
description: Battery miniclass drivers fill in the BATTERY_REPORTING_SCALE (wdm.h) structure in response to certain BatteryMiniQueryInformation requests.
tech.root: battery
ms.date: 02/21/2023
keywords: ["BATTERY_REPORTING_SCALE structure"]
ms.keywords: "*PBATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE, BATTERY_REPORTING_SCALE structure [Battery Devices], PBATTERY_REPORTING_SCALE, PBATTERY_REPORTING_SCALE structure pointer [Battery Devices], bat-struct_6ecc4955-56b0-4c92-9ce2-46bcd7d6b273.xml, battery.battery_reporting_scale, ntpoapi/BATTERY_REPORTING_SCALE, ntpoapi/PBATTERY_REPORTING_SCALE"
req.header: wdm.h
req.include-header: Batclass.h, Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: BATTERY_REPORTING_SCALE, *PBATTERY_REPORTING_SCALE
f1_keywords:
 - PBATTERY_REPORTING_SCALE
 - wdm/PBATTERY_REPORTING_SCALE
 - BATTERY_REPORTING_SCALE
 - wdm/BATTERY_REPORTING_SCALE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntpoapi.h
api_name:
 - PBATTERY_REPORTING_SCALE
 - BATTERY_REPORTING_SCALE
---

## -description

Battery miniclass drivers fill in this structure in response to certain [BatteryMiniQueryInformation](/windows/win32/api/batclass/nc-batclass-bclass_query_information_callback) requests.

## -struct-fields

### -field Granularity

Specify the granularity of the **Capacity** value, in milliwatt-hours. For most batteries, this value describes a monotonically increasing scale of capacity. For lithium-ion batteries, this value describes one of two possible scales: a gross measure of battery capacity, with a large granularity, or a finer measure as the capacity approaches zero.

### -field Capacity

Specify the battery capacity described by the corresponding granularity, in milliwatt-hours.

## -see-also

[BatteryMiniQueryInformation](/windows/win32/api/batclass/nc-batclass-bclass_query_information_callback)
