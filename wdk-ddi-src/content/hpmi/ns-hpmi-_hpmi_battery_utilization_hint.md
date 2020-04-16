---
UID: NS:hpmi._HPMI_BATTERY_UTILIZATION_HINT
title: _HPMI_BATTERY_UTILIZATION_HINT (hpmi.h)
description: This hint indicates if the OEM Battery Manager should attempt to save as much charge as possible in the non-hot swappable batteries (i.e.
old-location: powermeter\hpmi_battery_utilization_hint.htm
tech.root: powermeter
ms.assetid: A974998F-C9AF-496E-88B1-510413C17C4A
ms.date: 05/08/2018
keywords: ["_HPMI_BATTERY_UTILIZATION_HINT structure"]
ms.keywords: "*PHPMI_BATTERY_UTILIZATION_HINT, HPMI_BATTERY_UTILIZATION_HINT, HPMI_BATTERY_UTILIZATION_HINT structure [Power Metering and Budgeting Devices], PHPMI_BATTERY_UTILIZATION_HINT, PHPMI_BATTERY_UTILIZATION_HINT structure pointer [Power Metering and Budgeting Devices], _HPMI_BATTERY_UTILIZATION_HINT, hpmi/HPMI_BATTERY_UTILIZATION_HINT, hpmi/PHPMI_BATTERY_UTILIZATION_HINT, powermeter.hpmi_battery_utilization_hint"
f1_keywords:
 - "hpmi/HPMI_BATTERY_UTILIZATION_HINT"
req.header: hpmi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hpmi.h
api_name:
- HPMI_BATTERY_UTILIZATION_HINT
product:
- Windows
targetos: Windows
req.typenames: HPMI_BATTERY_UTILIZATION_HINT, *PHPMI_BATTERY_UTILIZATION_HINT
---

# _HPMI_BATTERY_UTILIZATION_HINT structure

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

This hint indicates if the OEM Battery Manager should attempt to save as much charge as possible in the non-hot swappable batteries (i.e. the batteries are generally referred to as "internal batteries", these batteries cannot be removed while system is operational).


## -struct-fields

### -field Version

Set to HPMI_BATTERY_UTILIZATION_HINT_VERSION_1.

### -field PreserveNonHotSwappableBatteries

 Interpretation of values:

- HpmiBoolUnavailable: Battery utilization hint is unavailable at the moment.

- HpmiBoolFalse: It is not necessary to preserve charge in the internal batteries at the moment.

- HpmiBoolTrue: Every attempt should be made to save as much charge as possible in the internal batteries.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hpmi/ne-hpmi-_hpmi_hint_bool">HPMI_HINT_BOOL</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hpmi/ni-hpmi-ioctl_hpmi_battery_utilization_hint">IOCTL_HPMI_BATTERY_UTILIZATION_HINT</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hpmi/index">hpmi.h</a>
