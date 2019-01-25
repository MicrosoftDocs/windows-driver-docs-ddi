---
UID: NE:wwan._WWAN_SAR_CONTROL_MODE
title: _WWAN_SAR_CONTROL_MODE (wwan.h)
description: The WWAN_SAR_CONTROL_MODE enumeration specifies how the SAR back off mechanism is controlled.
tech.root: netvista
ms.assetid: a951b293-b261-4daa-aeb6-7a037ea5fc47
ms.date: 08/20/2018
ms.topic: enum
ms.keywords: _WWAN_SAR_CONTROL_MODE, WWAN_SAR_CONTROL_MODE, *PWWAN_SAR_CONTROL_MODE, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_SAR_CONTROL_MODE, *PWWAN_SAR_CONTROL_MODE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wwan.h
api_name: 
-	_WWAN_SAR_CONTROL_MODE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _WWAN_SAR_CONTROL_MODE enumeration

## -description

The **WWAN_SAR_CONTROL_MODE** enumeration specifies how the SAR back off mechanism is controlled.

## -enum-fields

### -field WwanSarControlModeDevice

The SAR back off mechanism is controlled by the modem device directly.

### -field WwanSarControlModeOS

The SAR back off mechanism is controlled and managed by the operating system.

## -remarks

This enumeration is used in the [**WWAN_SAR_CONFIG_INFO**](ns-wwan-_wwan_sar_config_info.md) structure and the [**WWAN_SET_SAR_CONFIG**](ns-wwan-_wwan_set_sar_config.md) structure.

## -see-also

[MB SAR Platform Support](https://docs.microsoft.com/windows-hardware/drivers/network/mb-sar-platform-support)

[OID_WWAN_SAR_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-sar-config)

[**WWAN_SAR_CONFIG_INFO**](ns-wwan-_wwan_sar_config_info.md)

[**WWAN_SET_SAR_CONFIG**](ns-wwan-_wwan_set_sar_config.md)
