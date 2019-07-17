---
UID: NE:wditypes._WDI_OS_POWER_MANAGEMENT_FLAGS
title: _WDI_OS_POWER_MANAGEMENT_FLAGS (wditypes.h)
description: The WDI_OS_POWER_MANAGEMENT_FLAGS enumeration defines supported enablement scenarios of the NIC Auto Power Saver (NAPS) OS power management feature.
tech.root: netvista
ms.assetid: 5caa9b1f-cafa-42d0-8402-86799fd8885f
ms.date: 03/30/2018
ms.topic: enum
f1_keywords:
 - "wditypes/_WDI_OS_POWER_MANAGEMENT_FLAGS"
ms.keywords: _WDI_OS_POWER_MANAGEMENT_FLAGS, WDI_OS_POWER_MANAGEMENT_FLAGS, 
req.header: wditypes.hpp
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WDI_OS_POWER_MANAGEMENT_FLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wditypes.hpp
api_name: 
- _WDI_OS_POWER_MANAGEMENT_FLAGS
product:
- Windows
targetos: Windows
---

# _WDI_OS_POWER_MANAGEMENT_FLAGS enumeration

## -description

The **WDI_OS_POWER_MANAGEMENT_FLAGS** enumeration defines supported enablement scenarios of the NIC Auto Power Saver (NAPS) OS power management feature.

## -enum-fields

### -field WDI_OS_POWER_MANAGEMENT_NONE 

Enable no OS NAPS power management features.

### -field WDI_OS_POWER_MANAGEMENT_ENABLE_STANDBY_NAPS 

Enable NAPS mode for screen off, modern standby (if supported by hardware).

### -field WDI_OS_POWER_MANAGEMENT_ENABLE_S0_NAPS 

Enable NAPS mode for screen on *S0* system power state (if supported by hardware).

## -remarks

This enumeration is used as the value type in [WDI_TLV_OS_POWER_MANAGEMENT_FEATURES](https://docs.microsoft.com/windows-hardware/drivers/network/wdi-tlv-os-power-management-features).

## -see-also
