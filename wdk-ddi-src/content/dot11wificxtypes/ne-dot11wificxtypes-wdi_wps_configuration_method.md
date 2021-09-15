---
UID: NE:dot11wificxtypes._WDI_WPS_CONFIGURATION_METHOD
tech.root: netvista
title: WDI_WPS_CONFIGURATION_METHOD (dot11wificxtypes.h)
ms.date: 09/15/2021
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

The **WDI_WPS_CONFIGURATION_METHOD** enumeration defines WPS configuration methods.

## -enum-fields

### -field WDI_WPS_CONFIGURATION_METHOD_NULL:0

WFDS.

### -field WDI_WPS_CONFIGURATION_METHOD_DISPLAY:0x0008

Pin display.

### -field WDI_WPS_CONFIGURATION_METHOD_NFC_TAG:0x0020

NFC tag.

### -field WDI_WPS_CONFIGURATION_METHOD_NFC_INTERFACE:0x0040

NFC interface.

### -field WDI_WPS_CONFIGURATION_METHOD_PUSHBUTTON:0x0080

Push button.

### -field WDI_WPS_CONFIGURATION_METHOD_KEYPAD:0x0100

Pin keypad.

### -field WDI_WPS_CONFIGURATION_METHOD_WFDS_DEFAULT:0x1000

WFDS.

### -field WDI_WPS_CONFIGURATION_METHOD_DUMMY_MAX_VALUE:0xFFFF

Reserved.

## -remarks

The **WDI_WPS_CONFIGURATION_METHOD** enum is a value in the [WDI_TLV_P2P_CONFIG_METHODS](/windows-hardware/drivers/netcx/wdi-tlv-p2p-config-methods) TLV. 

## -see-also

[WDI_TLV_P2P_CONFIG_METHODS](/windows-hardware/drivers/netcx/wdi-tlv-p2p-config-methods)