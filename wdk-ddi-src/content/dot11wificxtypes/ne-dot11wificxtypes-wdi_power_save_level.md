---
UID: NE:dot11wificxtypes._WDI_POWER_SAVE_LEVEL
tech.root: netvista
title: WDI_POWER_SAVE_LEVEL (dot11wificxtypes.h)
ms.date: 07/23/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_POWER_SAVE_LEVEL enum defines the power save levels.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_POWER_SAVE_LEVEL
 - WDI_POWER_SAVE_LEVEL
f1_keywords:
 - _WDI_POWER_SAVE_LEVEL
 - dot11wificxtypes/_WDI_POWER_SAVE_LEVEL
 - WDI_POWER_SAVE_LEVEL
 - dot11wificxtypes/WDI_POWER_SAVE_LEVEL
dev_langs:
 - c++
---

## -description

The **WDI_POWER_SAVE_LEVEL** enumeration defines the power save levels.

## -enum-fields

### -field WDI_POWER_SAVE_LEVEL_NO_POWER_SAVE:0

No power saving.

### -field WDI_POWER_SAVE_LEVEL_FAST_PSP:8

Fast PSP.

### -field WDI_POWER_SAVE_LEVEL_MAX_PSP:16

Maximum PSP.

### -field WDI_POWER_SAVE_LEVEL_MAXIMUM_LEVEL:24

Maximum power saving level.

## -remarks

The **WDI_POWER_SAVE_LEVEL** enumeration is a value in the [**WDI_TLV_GET_AUTO_POWER_SAVE**](/windows-hardware/drivers/netcx/wdi-tlv-get-auto-power-save) TLV.

## -see-also

[**WDI_TLV_GET_AUTO_POWER_SAVE**](/windows-hardware/drivers/netcx/wdi-tlv-get-auto-power-save)