---
UID: NE:dot11wificxtypes._WDI_POWER_MODE_REASON_CODE
tech.root: netvista
title: WDI_POWER_MODE_REASON_CODE (dot11wificxtypes.h)
ms.date: 04/30/2021
targetos: Windows
<<<<<<< HEAD
description: The WDI_POWER_MODE_REASON_CODE enum defines the reasons for entering the Power Save state.
=======
description: "Microsoft reserves the WDI_POWER_MODE_REASON_CODE enumeration for internal use only. Don't use this enumeration in your code."
>>>>>>> main
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11Windows 11
>>>>>>> main
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
 - _WDI_POWER_MODE_REASON_CODE
 - WDI_POWER_MODE_REASON_CODE
f1_keywords:
 - _WDI_POWER_MODE_REASON_CODE
 - dot11wificxtypes/_WDI_POWER_MODE_REASON_CODE
 - WDI_POWER_MODE_REASON_CODE
 - dot11wificxtypes/WDI_POWER_MODE_REASON_CODE
dev_langs:
 - c++
---

## -description

The **WDI_POWER_MODE_REASON_CODE** enumeration defines the reasons for entering the Power Save state.

## -enum-fields

### -field WDI_POWER_MODE_REASON_CODE_NO_CHANGE:0

Device is initially in this state and has not changed since.

### -field WDI_POWER_MODE_REASON_CODE_NONCOMPLANT_AP:1

The connected AP didn't handle PSM correctly.

### -field WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE:2

WFD device is legacy.

### -field WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP:3

AP is compliant.

### -field WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE:4

All connected WFD device can do PSM.

### -field WDI_POWER_MODE_REASON_CODE_OTHERS:5

Other reason.

## -remarks

The **WDI_POWER_MODE_REASON_CODE** enumeration is a value in the [**WDI_TLV_GET_AUTO_POWER_SAVE**](/windows-hardware/drivers/netcx/wdi-tlv-get-auto-power-save) TLV.

## -see-also

[**WDI_TLV_GET_AUTO_POWER_SAVE**](/windows-hardware/drivers/netcx/wdi-tlv-get-auto-power-save)