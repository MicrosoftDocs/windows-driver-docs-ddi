---
UID: NE:wwan._WWAN_PIN_TYPE
title: _WWAN_PIN_TYPE (wwan.h)
description: The WWAN_PIN_TYPE enumeration specifies the PIN type for a UICC application.
tech.root: netvista
ms.date: 04/10/2019
keywords: ["WWAN_PIN_TYPE enumeration"]
ms.keywords: _WWAN_PIN_TYPE WWAN_PIN_TYPE *PWWAN_PIN_TYPE
req.header: wwan.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10 version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WWAN_PIN_TYPE *PWWAN_PIN_TYPE
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _WWAN_PIN_TYPE
 - wwan/_WWAN_PIN_TYPE
 - PWWAN_PIN_TYPE
 - wwan/PWWAN_PIN_TYPE
 - WWAN_PIN_TYPE
 - wwan/WWAN_PIN_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_PIN_TYPE
 - PWWAN_PIN_TYPE
 - WWAN_PIN_TYPE
---

# _WWAN_PIN_TYPE enumeration


## -description

The **WWAN_PIN_TYPE** enumeration specifies the PIN type for a UICC application.

## -enum-fields

### -field WwanPinTypeNone

No PIN is pending to be entered.

### -field WwanPinTypeCustom

The PIN type is a custom type and is none of the other PIN types listed in this enumeration.

### -field WwanPinTypePin1

The PIN1 key.

### -field WwanPinTypePin2

The PIN2 key.

### -field WwanPinTypeDeviceSimPin

The device to SIM key.

### -field WwanPinTypeDeviceFirstSimPin

The device to very first SIM key.

### -field WwanPinTypeNetworkPin

The network personalization key.

### -field WwanPinTypeNetworkSubsetPin

The network subset personalization key.

### -field WwanPinTypeSvcProviderPin

The service provider (SP) personalization key.

### -field WwanPinTypeCorporatePin

The corporate personalization key.

### -field WwanPinTypeSubsidyLock

The subsidy unlock key.

### -field WwanPinTypePuk1

The Personal Identification Number 1 Unlock Key (PUK1).

### -field WwanPinTypePuk2

The Personal Identification Number 2 Unlock Key (PUK2).

### -field WwanPinTypeDeviceFirstSimPuk

The device to very first SIM PIN unlock key.

### -field WwanPinTypeNetworkPuk

The network personalization unlock key.

### -field WwanPinTypeNetworkSubsetPuk

The network subset personalization unlock key.

### -field WwanPinTypeSvcProviderPuk

The service provider (SP) personalization unlock key.

### -field WwanPinTypeCorporatePuk

The corporate personalization unlock key.

### -field WwanPinTypeNev

The NEV key.

### -field WwanPinTypeAdm

The administrative key.

### -field WwanPinTypeMax

The maximum value for this enumeration.

## -remarks

This enumeration is used in the following structures:

- [**WWAN_PIN_INFO**](../wwan/ns-wwan-_wwan_pin_info.md)
- [**WWAN_PIN_ACTION**](../wwan/ns-wwan-_wwan_pin_action.md)
- [**WWAN_PIN_ACTION_EX2**](../wwan/ns-wwan-_wwan_pin_action_ex2.md)

## -see-also

[MB UICC application and file system access](/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_PIN_EX2](/windows-hardware/drivers/network/oid-wwan-pin-ex2)

[**WWAN_PIN_INFO**](../wwan/ns-wwan-_wwan_pin_info.md)

[**WWAN_PIN_ACTION**](../wwan/ns-wwan-_wwan_pin_action.md)

[**WWAN_PIN_ACTION_EX2**](../wwan/ns-wwan-_wwan_pin_action_ex2.md)

