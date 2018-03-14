---
UID: NE:wwan._WWAN_RADIO
title: "_WWAN_RADIO"
author: windows-driver-content
description: The WWAN_RADIO enumeration lists the different types of radio power modes that are supported by the MB device.
old-location: netvista\wwan_radio.htm
old-project: netvista
ms.assetid: f589180c-5379-4f50-876e-48d142b44be4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_RADIO, PWWAN_RADIO, PWWAN_RADIO enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_RADIO, WWAN_RADIO enumeration [Network Drivers Starting with Windows Vista], WwanRadioOff, WwanRadioOn, WwanRef_b864982c-e4b4-4a2e-b45b-ba6e534a1a71.xml, _WWAN_RADIO, netvista.wwan_radio, wwan/PWWAN_RADIO, wwan/WWAN_RADIO, wwan/WwanRadioOff, wwan/WwanRadioOn"
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
-	WWAN_RADIO
product: Windows
targetos: Windows
req.typenames: WWAN_RADIO, *PWWAN_RADIO
req.product: Windows 10 or later.
---

# _WWAN_RADIO enumeration


## -description


The WWAN_RADIO enumeration lists the different types of radio power modes that are supported by the
  MB device.


## -syntax


````
typedef enum _WWAN_RADIO { 
  WwanRadioOff  = 0,
  WwanRadioOn
} WWAN_RADIO, *PWWAN_RADIO;
````


## -enum-fields




### -field WwanRadioOff

The radio power is turned off.


### -field WwanRadioOn

The radio power is turned on.


## -see-also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_set_radio_state.md">NDIS_WWAN_SET_RADIO_STATE</a>



<a href="..\wwan\ns-wwan-_wwan_radio_state.md">WWAN_RADIO_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_RADIO enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

