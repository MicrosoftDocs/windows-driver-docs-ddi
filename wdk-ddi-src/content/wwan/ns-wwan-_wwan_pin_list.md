---
UID: NS:wwan._WWAN_PIN_LIST
title: "_WWAN_PIN_LIST"
author: windows-driver-content
description: The WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers (PINs).
old-location: netvista\wwan_pin_list.htm
old-project: netvista
ms.assetid: 7ddea69c-db40-4fae-9ca9-5eadc9b40b0c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWWAN_PIN_LIST, PWWAN_PIN_LIST, PWWAN_PIN_LIST structure pointer [Network Drivers Starting with Windows Vista], WWAN_PIN_LIST, WWAN_PIN_LIST structure [Network Drivers Starting with Windows Vista], WwanRef_b23c520d-20ea-4597-8dd2-2a1f9cd68938.xml, _WWAN_PIN_LIST, netvista.wwan_pin_list, wwan/PWWAN_PIN_LIST, wwan/WWAN_PIN_LIST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	WWAN_PIN_LIST
product: Windows
targetos: Windows
req.typenames: WWAN_PIN_LIST, *PWWAN_PIN_LIST
req.product: Windows 10 or later.
---

# _WWAN_PIN_LIST structure


## -description


The WWAN_PIN_LIST structure represents a list of descriptions of Personal Identification Numbers
  (PINs).


## -syntax


````
typedef struct _WWAN_PIN_LIST {
  WWAN_PIN_DESC WwanPinDescPin1;
  WWAN_PIN_DESC WwanPinDescPin2;
  WWAN_PIN_DESC WwanPinDescDeviceSimPin;
  WWAN_PIN_DESC WwanPinDescDeviceFirstSimPin;
  WWAN_PIN_DESC WwanPinDescNetworkPin;
  WWAN_PIN_DESC WwanPinDescNetworkSubsetPin;
  WWAN_PIN_DESC WwanPinDescSvcProviderPin;
  WWAN_PIN_DESC WwanPinDescCorporatePin;
  WWAN_PIN_DESC WwanPinDescSubsidyLock;
  WWAN_PIN_DESC WwanPinDescCustom;
} WWAN_PIN_LIST, *PWWAN_PIN_LIST;
````


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

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_pin_list.md">NDIS_WWAN_PIN_LIST</a>



<a href="..\wwan\ns-wwan-_wwan_pin_desc.md">WWAN_PIN_DESC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PIN_LIST structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

