---
UID: NE:wwan._WWAN_PIN_TYPE
title: "_WWAN_PIN_TYPE"
author: windows-driver-content
description: The WWAN_PIN_TYPE enumeration lists the different types of Personal Identification Numbers (PINs) that are supported by the MB device.
old-location: netvista\wwan_pin_type.htm
old-project: netvista
ms.assetid: f6b8146e-dbe2-4c73-beb2-02868db9fb27
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWWAN_PIN_TYPE, PWWAN_PIN_TYPE, PWWAN_PIN_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_TYPE, WWAN_PIN_TYPE enumeration [Network Drivers Starting with Windows Vista], WwanPinTypeCorporatePin, WwanPinTypeCorporatePuk, WwanPinTypeCustom, WwanPinTypeDeviceFirstSimPin, WwanPinTypeDeviceFirstSimPuk, WwanPinTypeDeviceSimPin, WwanPinTypeMax, WwanPinTypeNetworkPin, WwanPinTypeNetworkPuk, WwanPinTypeNetworkSubsetPin, WwanPinTypeNetworkSubsetPuk, WwanPinTypeNone, WwanPinTypePin1, WwanPinTypePin2, WwanPinTypePuk1, WwanPinTypePuk2, WwanPinTypeSubsidyLock, WwanPinTypeSvcProviderPin, WwanPinTypeSvcProviderPuk, WwanRef_f94cf79e-63f3-47e9-bd40-beb9cd32f0b8.xml, _WWAN_PIN_TYPE, netvista.wwan_pin_type, wwan/PWWAN_PIN_TYPE, wwan/WWAN_PIN_TYPE, wwan/WwanPinTypeCorporatePin, wwan/WwanPinTypeCorporatePuk, wwan/WwanPinTypeCustom, wwan/WwanPinTypeDeviceFirstSimPin, wwan/WwanPinTypeDeviceFirstSimPuk, wwan/WwanPinTypeDeviceSimPin, wwan/WwanPinTypeMax, wwan/WwanPinTypeNetworkPin, wwan/WwanPinTypeNetworkPuk, wwan/WwanPinTypeNetworkSubsetPin, wwan/WwanPinTypeNetworkSubsetPuk, wwan/WwanPinTypeNone, wwan/WwanPinTypePin1, wwan/WwanPinTypePin2, wwan/WwanPinTypePuk1, wwan/WwanPinTypePuk2, wwan/WwanPinTypeSubsidyLock, wwan/WwanPinTypeSvcProviderPin, wwan/WwanPinTypeSvcProviderPuk"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_PIN_TYPE
product:
- Windows
targetos: Windows
req.typenames: WWAN_PIN_TYPE, *PWWAN_PIN_TYPE
---

# _WWAN_PIN_TYPE enumeration


## -description


The WWAN_PIN_TYPE enumeration lists the different types of Personal Identification Numbers (PINs)
  that are supported by the MB device.


## -enum-fields




### -field WwanPinTypeNone

No PIN is pending to be entered.


### -field WwanPinTypeCustom

The PIN type is a custom type and is none of the other PIN types listed in this
     enumeration.


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

The Personal Identification Number1 Unlock Key (PUK1).


### -field WwanPinTypePuk2

The Personal Identification Number2 Unlock Key (PUK2).


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


### -field WwanPinTypeAdm


### -field WwanPinTypeMax

The total number of supported PIN types.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571213">WWAN_PIN_ACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571216">WWAN_PIN_INFO</a>
 

 

