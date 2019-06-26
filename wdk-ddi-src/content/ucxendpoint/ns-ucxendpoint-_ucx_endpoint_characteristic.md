---
UID: NS:ucxendpoint._UCX_ENDPOINT_CHARACTERISTIC
title: _UCX_ENDPOINT_CHARACTERISTIC (ucxendpoint.h)
description: Stores the characteristics of an endpoint.
old-location: buses\ucx_endpoint_characteristic.htm
tech.root: usbref
ms.assetid: 4785D94B-271C-4F8E-B95B-87401E32CE42
ms.date: 05/07/2018
ms.keywords: "*PUCX_ENDPOINT_CHARACTERISTIC, PUCX_ENDPOINT_CHARACTERISTIC, PUCX_ENDPOINT_CHARACTERISTIC structure pointer [Buses], UCX_ENDPOINT_CHARACTERISTIC, UCX_ENDPOINT_CHARACTERISTIC structure [Buses], _UCX_ENDPOINT_CHARACTERISTIC, buses.ucx_endpoint_characteristic, ucxendpoint/PUCX_ENDPOINT_CHARACTERISTIC, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC"
ms.topic: struct
req.header: ucxendpoint.h
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
- Ucxendpoint.h
api_name:
- UCX_ENDPOINT_CHARACTERISTIC
product:
- Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC, *PUCX_ENDPOINT_CHARACTERISTIC
---

# _UCX_ENDPOINT_CHARACTERISTIC structure


## -description


Stores the characteristics of an endpoint. 


## -struct-fields




### -field Size

Size of this structure.


### -field CharacteristicType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/ne-ucxendpoint-_ucx_endpoint_characteristic_type">UCX_ENDPOINT_CHARACTERISTIC_TYPE</a>-type value that indicates the type of endpoint characteristic.


### -field Priority

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/ne-ucxendpoint-_ucx_endpoint_characteristic_priority">UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY</a>-typed value that indicates the priority of the endpoint.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/nc-ucxendpoint-evt_ucx_endpoint_set_characteristic">EVT_UCX_ENDPOINT_SET_CHARACTERISTIC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxendpoint/ne-ucxendpoint-_ucx_endpoint_characteristic_priority">UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY</a>
 

 

