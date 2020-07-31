---
UID: NS:wwan._WWAN_PIN_LIST
title: _WWAN_PIN_LIST (wwan.h)
description: The WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers (PINs).
old-location: netvista\wwan_pin_list.htm
tech.root: netvista
ms.assetid: 7ddea69c-db40-4fae-9ca9-5eadc9b40b0c
ms.date: 05/02/2018
keywords: ["_WWAN_PIN_LIST structure"]
ms.keywords: "*PWWAN_PIN_LIST, PWWAN_PIN_LIST, PWWAN_PIN_LIST structure pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_LIST, WWAN_PIN_LIST structure [Network Drivers Starting with Windows Vista], WwanRef_b23c520d-20ea-4597-8dd2-2a1f9cd68938.xml, _WWAN_PIN_LIST, netvista.wwan_pin_list, wwan/PWWAN_PIN_LIST, wwan/WWAN_PIN_LIST"
f1_keywords:
 - "wwan/WWAN_PIN_LIST"
 - "WWAN_PIN_LIST"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_PIN_LIST
targetos: Windows
req.typenames: WWAN_PIN_LIST, *PWWAN_PIN_LIST
---

# _WWAN_PIN_LIST structure


## -description


The WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers
  (PINs).


## -struct-fields




### -field WwanPinDescPin1

Description for PIN1. For GSM-based devices, this is a Subscriber Identity Module (SIM) PIN. For
     CDMA-based devices, power-on device lock is reported as PIN1.


### -field WwanPinDescPin2

Description for PIN2. This is a SIM PIN2 that protects certain SIM functionality.


### -field WwanPinDescDeviceSimPin

Description for the device-to-SIM-card PIN. This is a PIN that locks the device to a specific
     SIM.


### -field WwanPinDescDeviceFirstSimPin

Description for the device-to-very-first-SIM-card PIN. This is a PIN that locks the device to the
     very first inserted SIM.


### -field WwanPinDescNetworkPin

Description for the network personalization PIN. This is a PIN that allows the device to be
     personalized to a network. For more information about this PIN type, see section 22.022 of the 3GPP
     specification.


### -field WwanPinDescNetworkSubsetPin

Description for network subset personalization PIN. This is a PIN that allows the device to be
     personalized to a subset of a network. For more information about this PIN type, see section 22.022 of
     the 3GPP specification.


### -field WwanPinDescSvcProviderPin

Description for Service Provider (SP) personalization PIN. This is a PIN that allows the device to
     be personalized to a service provider. For more information about this PIN type, see section 22.022 of
     the 3GPP specification.


### -field WwanPinDescCorporatePin

Description for corporate personalization PIN. This is a PIN that allows the device to be
     personalized to a specific company. For more information about this PIN type, see section 22.022 of the
     3GPP specification.


### -field WwanPinDescSubsidyLock

Description for subsidy unlock PIN. This is a PIN that allows the device to be restricted to
     operate on a specific network. For more information about this PIN type, see section 22.022 of the 3GPP
     specification.


### -field WwanPinDescCustom

Description for custom PIN. This is a custom vendor-defined PIN type. It is not included in the
     above list.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_pin_list">NDIS_WWAN_PIN_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_pin_desc">WWAN_PIN_DESC</a>
 

 

