---
UID: NE:wwan._WWAN_DEVICE_TYPE
title: _WWAN_DEVICE_TYPE (wwan.h)
description: The WWAN_DEVICE_TYPE enumeration lists the different device types that describe the MB device.
old-location: netvista\wwan_device_type.htm
tech.root: netvista
ms.assetid: ad99b2b0-d62a-4e3e-a368-b9109f0fefb4
ms.date: 05/02/2018
ms.keywords: "*PWWAN_DEVICE_TYPE, PWWAN_DEVICE_TYPE, PWWAN_DEVICE_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_TYPE, WWAN_DEVICE_TYPE enumeration [Network Drivers Starting with Windows Vista], WwanDeviceTypeEmbedded, WwanDeviceTypeMax, WwanDeviceTypeRemote, WwanDeviceTypeRemovable, WwanDeviceTypeUnknown, WwanRef_7a7adc94-ea69-4327-b9b6-467a1c784979.xml, _WWAN_DEVICE_TYPE, netvista.wwan_device_type, wwan/PWWAN_DEVICE_TYPE, wwan/WWAN_DEVICE_TYPE, wwan/WwanDeviceTypeEmbedded, wwan/WwanDeviceTypeMax, wwan/WwanDeviceTypeRemote, wwan/WwanDeviceTypeRemovable, wwan/WwanDeviceTypeUnknown"
ms.topic: enum
f1_keywords:
 - "wwan/WWAN_DEVICE_TYPE"
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
- WWAN_DEVICE_TYPE
product:
- Windows
targetos: Windows
req.typenames: WWAN_DEVICE_TYPE, *PWWAN_DEVICE_TYPE
---

# _WWAN_DEVICE_TYPE enumeration


## -description


The WWAN_DEVICE_TYPE enumeration lists the different device types that describe the MB device.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>
 

 

