---
UID: NE:dot11wificxtypes._WDI_WPS_CONFIGURATION_METHOD
tech.root: netvista
title: WDI_WPS_CONFIGURATION_METHOD (dot11wificxtypes.h)
ms.date: 06/18/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_WPS_CONFIGURATION_METHOD enum defines WPS configuration methods.
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
 - _WDI_WPS_CONFIGURATION_METHOD
 - WDI_WPS_CONFIGURATION_METHOD
f1_keywords:
 - _WDI_WPS_CONFIGURATION_METHOD
 - dot11wificxtypes/_WDI_WPS_CONFIGURATION_METHOD
 - WDI_WPS_CONFIGURATION_METHOD
 - dot11wificxtypes/WDI_WPS_CONFIGURATION_METHOD
dev_langs:
 - c++
---

## -description

The WDI_WPS_CONFIGURATION_METHOD enumeration defines WPS configuration methods.

## -enum-fields

### -field WDI_WPS_CONFIGURATION_METHOD_NULL

WFDS.

### -field WDI_WPS_CONFIGURATION_METHOD_DISPLAY

Pin display.

### -field WDI_WPS_CONFIGURATION_METHOD_NFC_TAG

NFC tag.

### -field WDI_WPS_CONFIGURATION_METHOD_NFC_INTERFACE

NFC interface.

### -field WDI_WPS_CONFIGURATION_METHOD_PUSHBUTTON

Push button.

### -field WDI_WPS_CONFIGURATION_METHOD_KEYPAD

Pin keypad.

### -field WDI_WPS_CONFIGURATION_METHOD_WFDS_DEFAULT

WFDS.

### -field WDI_WPS_CONFIGURATION_METHOD_DUMMY_MAX_VALUE

Reserved.

## -remarks

The **WDI_WPS_CONFIGURATION_METHOD** enum is a value in the [WDI_TLV_P2P_CONFIG_METHODS](/windows-hardware/drivers/netcx/wdi-tlv-p2p-config-methods) TLV. 

## -see-also

[WDI_TLV_P2P_CONFIG_METHODS](/windows-hardware/drivers/netcx/wdi-tlv-p2p-config-methods)