---
UID: NS:ucxusbdevice._UCX_USBDEVICE_CHARACTERISTIC
title: _UCX_USBDEVICE_CHARACTERISTIC (ucxusbdevice.h)
description: Stores the characteristics of an device.
old-location: buses\ucx_usbdevice_characteristic.htm
tech.root: usbref
ms.assetid: 31BF5607-51EA-4FBF-A754-872FBD45915D
ms.date: 05/07/2018
keywords: ["UCX_USBDEVICE_CHARACTERISTIC structure"]
ms.keywords: "*PUCX_USBDEVICE_CHARACTERISTIC, PUCX_USBDEVICE_CHARACTERISTIC, PUCX_USBDEVICE_CHARACTERISTIC structure pointer [Buses], UCX_USBDEVICE_CHARACTERISTIC, UCX_USBDEVICE_CHARACTERISTIC structure [Buses], _UCX_USBDEVICE_CHARACTERISTIC, buses.ucx_usbdevice_characteristic, ucxusbdevice/PUCX_USBDEVICE_CHARACTERISTIC, ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC"
f1_keywords:
 - "ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC"
 - "UCX_USBDEVICE_CHARACTERISTIC"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ucxusbdevice.h
api_name:
- UCX_USBDEVICE_CHARACTERISTIC
targetos: Windows
req.typenames: UCX_USBDEVICE_CHARACTERISTIC, *PUCX_USBDEVICE_CHARACTERISTIC
---

# _UCX_USBDEVICE_CHARACTERISTIC structure


## -description


Stores the characteristics of an device. 


## -struct-fields




### -field Size

Size of this structure.


### -field CharacteristicType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ne-ucxusbdevice-_ucx_usbdevice_characteristic_type">UCX_USBDEVICE_CHARACTERISTIC_TYPE</a>-type value that indicates the type of device characteristic.


### -field PathDelay

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_ucx_usbdevice_characteristic_path_delay">UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY</a>-typed value that indicates the path delay values for the endpoint.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_get_characteristic">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a>
 

 

