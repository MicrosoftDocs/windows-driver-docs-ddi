---
UID: NE:wwan._WWAN_DRX_PARAMS
tech.root: netvista
title: WWAN_DRX_PARAMS
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The **WWAN_DRX_PARAMS** enumeration lists Discontinuous Reception (DRX) settings.
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
 - _WWAN_DRX_PARAMS
 - WWAN_DRX_PARAMS
f1_keywords:
 - _WWAN_DRX_PARAMS
 - wwan/_WWAN_DRX_PARAMS
 - WWAN_DRX_PARAMS
 - wwan/WWAN_DRX_PARAMS
dev_langs:
 - c++
---

## -description

The **WWAN_DRX_PARAMS** enumeration lists Discontinuous Reception (DRX) settings.

## -enum-fields

### -field WwanDRXUnspecified

The DRX cycle is not specified. In [OID_WWAN_REGISTER_PARAMS](/windows-hardware/drivers/network/oid-wwan-register-params) set requests, **WwanDRXUnspecified** indicates that the host does not request that the modem use a specific DRX cycle. In set or query responses, **WwanDRXUnspecified** indicates that the device does not know the DRX cycle.

### -field WwanDRXNotSupported

The modem does not support setting a DRX cycle.

### -field WwanDRXCycle32

DRX cycle T=32

### -field WwanDRXCycle64

DRX cycle T=64

### -field WwanDRXCycle128

DRX cycle T=128

### -field WwanDRXCycle256

DRX cycle T=256

### -field WwanDRXCycleMax

Indicates an out-of-bound value for this enumeration. All values less than **WwanDRXCycleMax** are valid. All values larger than or equal to **WwanDRXCycleMax** are invalid.

## -remarks

## -see-also

[**WWAN_REGISTRATION_PARAMS_INFO**](ns-wwan-wwan_registration_params_info.md)

[OID_WWAN_REGISTER_PARAMS](/windows-hardware/drivers/network/oid-wwan-register-params) 
