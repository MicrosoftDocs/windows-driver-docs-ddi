---
UID: NE:usbctypes._USBC_PARTNER
title: _USBC_PARTNER
author: windows-driver-content
description: Defines values for the type of connector partner detected on the USB Type-C connector.
ms.assetid: c5dd981e-327f-45d2-8d0a-507cd118b1ae
ms.date: 09/30/2018
ms.topic: enum
ms.keywords: _USBC_PARTNER, USBC_PARTNER, 
req.header: usbctypes.h
req.include-header: usbctypes.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.ddi-compliance:
req.max-support:
req.typenames: USBC_PARTNER
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	usbctypes.h
api_name: 
-	_USBC_PARTNER
product: Windows
targetos: Windows
---

# _USBC_PARTNER enumeration

## -description
Defines values for the type of connector partner detected on the USB Type-C connector.


## -enum-fields

### -field UsbCPartnerInvalid 
Invalid partner.

### -field UsbCPartnerUfp 
The partner is a UFP.

### -field UsbCPartnerDfp 
The partner is a DFP.

### -field UsbCPartnerPoweredCableNoUfp 
The partner is not a UFP when attached to powered cable.

### -field UsbCPartnerPoweredCableWithUfp
The partner is a UFP when attached to powered cable.

### -field UsbCPartnerAudioAccessory 
The partner is an audio adapter accessory. 

### -field UsbCPartnerDebugAccessory 
The partner is a debug adapter accessory.

## -remarks

## -see-also
