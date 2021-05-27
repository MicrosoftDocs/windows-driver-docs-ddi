---
UID: NE:wwan._WWAN_MICO_MODE
tech.root: netvista
title: WWAN_MICO_MODE
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The WWAN_MICO_MODE enumeration lists Mobile Initiated Connection modes.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_MICO_MODE
 - WWAN_MICO_MODE
f1_keywords:
 - _WWAN_MICO_MODE
 - wwan/_WWAN_MICO_MODE
 - WWAN_MICO_MODE
 - wwan/WWAN_MICO_MODE
dev_langs:
 - c++
---

## -description

The **WWAN_MICO_MODE** enumeration lists Mobile Initiated Connection modes.

## -enum-fields

### -field WwanMicoModeDisabled

MICO mode is disabled on the device.

### -field WwanMicoModeEnabled

MICO mode is enabled on the device.

### -field WwanMicoModeUnsupported

Used in [OID_WWAN_REGISTER_PARAMS](/windows-hardware/drivers/network/oid-wwan-register-params) set or query responses only. Indicates that the device does not support MICO mode.

### -field WwanMBIMMicoModeDefault

Used in [OID_WWAN_REGISTER_PARAMS](/windows-hardware/drivers/network/oid-wwan-register-params) set requests only. Indicates that the default MICO mode in the device (including no MICO mode support) should be used by the device in 5G registration.

### -field WwanMicoModeMax

Indicates an out-of-bound value for this enumeration. All values less than **WwanMicoModeMax** are valid. All values larger than or equal to **WwanMicoModeMax** are invalid.

## -remarks

## -see-also

[**WWAN_REGISTRATION_PARAMS_INFO**](ns-wwan-wwan_registration_params_info.md)

[OID_WWAN_REGISTER_PARAMS](/windows-hardware/drivers/network/oid-wwan-register-params)
