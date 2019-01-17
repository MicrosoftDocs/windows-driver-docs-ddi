---
UID: NE:portabledevice.tagWPD_DEVICE_TRANSPORTS
title: tagWPD_DEVICE_TRANSPORTS
description: The WPD_DEVICE_TRANSPORTS enumeration type describes the transport for the device that is currently connected. This enumeration is used by the WPD_DEVICE_TRANSPORT property.
old-location: wpddk\wpd_device_transports.htm
tech.root: wpd_dk
ms.assetid: fa29b986-3106-4f7d-b5c3-bcfe8b3bbbd2
ms.date: 02/15/2018
ms.keywords: WPD_DEVICE_TRANSPORTS, WPD_DEVICE_TRANSPORTS enumeration, WPD_DEVICE_TRANSPORT_BLUETOOTH, WPD_DEVICE_TRANSPORT_IP, WPD_DEVICE_TRANSPORT_UNSPECIFIED, WPD_DEVICE_TRANSPORT_USB, portabledevice/WPD_DEVICE_TRANSPORTS, portabledevice/WPD_DEVICE_TRANSPORT_BLUETOOTH, portabledevice/WPD_DEVICE_TRANSPORT_IP, portabledevice/WPD_DEVICE_TRANSPORT_UNSPECIFIED, portabledevice/WPD_DEVICE_TRANSPORT_USB, tagWPD_DEVICE_TRANSPORTS, wpddk.wpd_device_transports
ms.topic: enum
req.header: portabledevice.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	PortableDevice.h
api_name:
-	WPD_DEVICE_TRANSPORTS
product:
-	Windows
targetos: Windows
req.typenames: WPD_DEVICE_TRANSPORTS
ms.custom: RS5
---

# tagWPD_DEVICE_TRANSPORTS enumeration


## -description


The <b>WPD_DEVICE_TRANSPORTS</b> enumeration type describes the transport for the device that is currently connected. This enumeration is used by the <b>WPD_DEVICE_TRANSPORT</b> property.


## -enum-fields




### -field WPD_DEVICE_TRANSPORT_UNSPECIFIED

The transport type was not specified.


### -field WPD_DEVICE_TRANSPORT_USB

The device is connected through USB.


### -field WPD_DEVICE_TRANSPORT_IP

The device is connected through Internet Protocol (IP).


### -field WPD_DEVICE_TRANSPORT_BLUETOOTH

The device is connected through Bluetooth.

