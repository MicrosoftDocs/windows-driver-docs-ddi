---
UID: NE:ucxusbdevice._UCX_USBDEVICE_CHARACTERISTIC_TYPE
title: "_UCX_USBDEVICE_CHARACTERISTIC_TYPE"
author: windows-driver-content
description: Defines values that indicates the type of device characteristic.
old-location: buses\ucx_usbdevice_characteristic_type.htm
old-project: usbref
ms.assetid: 86FA72CC-C23F-40B9-9FDD-80C3B0D5EA73
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PUCX_USBDEVICE_CHARACTERISTIC_TYPE, PUCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration pointer [Buses], UCX_USBDEVICE_CHARACTERISTIC_TYPE, UCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration [Buses], UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY, _UCX_USBDEVICE_CHARACTERISTIC_TYPE, buses.ucx_usbdevice_characteristic_type, ucxusbdevice/PUCX_USBDEVICE_CHARACTERISTIC_TYPE, ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC_TYPE, ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxusbdevice.h
api_name:
-	UCX_USBDEVICE_CHARACTERISTIC_TYPE
product: Windows
targetos: Windows
req.typenames: UCX_USBDEVICE_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# _UCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration


## -description


Defines values that indicates the type of device characteristic.


## -syntax


````
typedef enum _UCX_USBDEVICE_CHARACTERISTIC_TYPE { 
  UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY  = 0x01
} UCX_USBDEVICE_CHARACTERISTIC_TYPE, *PUCX_USBDEVICE_CHARACTERISTIC_TYPE;
````


## -enum-fields




### -field UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY

The type of characteristic of the device.


## -see-also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_ucx_usbdevice_characteristic.md">UCX_USBDEVICE_CHARACTERISTIC</a>



<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_get_characteristic.md">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a>



 

 


