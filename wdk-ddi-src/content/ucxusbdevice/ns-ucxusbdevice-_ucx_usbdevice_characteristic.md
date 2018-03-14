---
UID: NS:ucxusbdevice._UCX_USBDEVICE_CHARACTERISTIC
title: "_UCX_USBDEVICE_CHARACTERISTIC"
author: windows-driver-content
description: Stores the characteristics of an device.
old-location: buses\ucx_usbdevice_characteristic.htm
old-project: usbref
ms.assetid: 31BF5607-51EA-4FBF-A754-872FBD45915D
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCX_USBDEVICE_CHARACTERISTIC, PUCX_USBDEVICE_CHARACTERISTIC, PUCX_USBDEVICE_CHARACTERISTIC structure pointer [Buses], UCX_USBDEVICE_CHARACTERISTIC, UCX_USBDEVICE_CHARACTERISTIC structure [Buses], _UCX_USBDEVICE_CHARACTERISTIC, buses.ucx_usbdevice_characteristic, ucxusbdevice/PUCX_USBDEVICE_CHARACTERISTIC, ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucxusbdevice.h
api_name:
-	UCX_USBDEVICE_CHARACTERISTIC
product: Windows
targetos: Windows
req.typenames: UCX_USBDEVICE_CHARACTERISTIC, *PUCX_USBDEVICE_CHARACTERISTIC
req.product: Windows 10 or later.
---

# _UCX_USBDEVICE_CHARACTERISTIC structure


## -description


Stores the characteristics of an device. 


## -syntax


````
typedef struct _UCX_USBDEVICE_CHARACTERISTIC {
  ULONG                             Size;
  UCX_USBDEVICE_CHARACTERISTIC_TYPE CharacteristicType;
  union {
    UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY PathDelay;
  };
} UCX_USBDEVICE_CHARACTERISTIC, *PUCX_USBDEVICE_CHARACTERISTIC;
````


## -struct-fields




### -field Size

Size of this structure.


### -field CharacteristicType

A <a href="..\ucxusbdevice\ne-ucxusbdevice-_ucx_usbdevice_characteristic_type.md">UCX_USBDEVICE_CHARACTERISTIC_TYPE</a>-type value that indicates the type of device characteristic.


#### - PathDelay

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_ucx_usbdevice_characteristic_path_delay.md">UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY</a>-typed value that indicates the path delay values for the endpoint.


## -see-also

<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_get_characteristic.md">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a>



 

 


