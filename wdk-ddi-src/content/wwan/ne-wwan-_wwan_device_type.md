---
UID: NE:wwan._WWAN_DEVICE_TYPE
title: "_WWAN_DEVICE_TYPE"
author: windows-driver-content
description: The WWAN_DEVICE_TYPE enumeration lists the different device types that describe the MB device.
old-location: netvista\wwan_device_type.htm
old-project: netvista
ms.assetid: ad99b2b0-d62a-4e3e-a368-b9109f0fefb4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WwanDeviceTypeRemote, PWWAN_DEVICE_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], netvista.wwan_device_type, WWAN_DEVICE_TYPE enumeration [Network Drivers Starting with Windows Vista], wwan/WwanDeviceTypeRemote, wwan/WwanDeviceTypeMax, wwan/WWAN_DEVICE_TYPE, PWWAN_DEVICE_TYPE, WwanDeviceTypeUnknown, wwan/WwanDeviceTypeUnknown, WwanDeviceTypeRemovable, wwan/WwanDeviceTypeRemovable, WwanDeviceTypeMax, WwanRef_7a7adc94-ea69-4327-b9b6-467a1c784979.xml, *PWWAN_DEVICE_TYPE, wwan/PWWAN_DEVICE_TYPE, WWAN_DEVICE_TYPE, WwanDeviceTypeEmbedded, wwan/WwanDeviceTypeEmbedded, _WWAN_DEVICE_TYPE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_DEVICE_TYPE
product: Windows
targetos: Windows
req.typenames: WWAN_DEVICE_TYPE, *PWWAN_DEVICE_TYPE
req.product: Windows 10 or later.
---

# _WWAN_DEVICE_TYPE enumeration


## -description


The WWAN_DEVICE_TYPE enumeration lists the different device types that describe the MB device.


## -syntax


````
typedef enum _WWAN_DEVICE_TYPE { 
  WwanDeviceTypeUnknown    = 0,
  WwanDeviceTypeEmbedded,
  WwanDeviceTypeRemovable,
  WwanDeviceTypeRemote,
  WwanDeviceTypeMax
} WWAN_DEVICE_TYPE, *PWWAN_DEVICE_TYPE;
````


## -enum-fields




### -field WwanDeviceTypeUnknown

The device type is unknown.


### -field WwanDeviceTypeEmbedded

The device type is embedded in the system.


### -field WwanDeviceTypeRemovable

The device type is removable.


### -field WwanDeviceTypeRemote

The device type is remote. For example, a tethered cellular phone modem.


### -field WwanDeviceTypeMax

The total number of supported device types.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_device_caps.md">WWAN_DEVICE_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_DEVICE_TYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

