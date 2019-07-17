---
UID: NE:wwan._WWAN_PIN_TYPE_EX
title: _WWAN_PIN_TYPE_EX (wwan.h)
description: The WWAN_PIN_TYPE_EX enumeration specifies the PIN type for a UICC application.
tech.root: netvista
ms.assetid: D4852EC3-AF5B-46BE-99A4-A006F71F5A24
ms.date: 04/10/2019
ms.topic: enum
f1_keywords:
 - "wwan/_WWAN_PIN_TYPE_EX"
ms.keywords: _WWAN_PIN_TYPE_EX WWAN_PIN_TYPE_EX *PWWAN_PIN_TYPE_EX 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10 version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: WWAN_PIN_TYPE_EX *PWWAN_PIN_TYPE_EX
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_PIN_TYPE_EX
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_PIN_TYPE_EX enumeration

## -description

The **WWAN_PIN_TYPE_EX** enumeration specifies the PIN type for a UICC application.

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

This enumeration is used in the [**WWAN_PIN_ACTION_EX2**](../wwan/ns-wwan-_wwan_pin_action_ex2.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_PIN_EX2](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-pin-ex2)

[**WWAN_PIN_ACTION_EX2**](../wwan/ns-wwan-_wwan_pin_action_ex2.md)
