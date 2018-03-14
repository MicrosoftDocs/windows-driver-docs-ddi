---
UID: NS:ucxendpoint._UCX_ENDPOINT_CHARACTERISTIC
title: "_UCX_ENDPOINT_CHARACTERISTIC"
author: windows-driver-content
description: Stores the characteristics of an endpoint.
old-location: buses\ucx_endpoint_characteristic.htm
old-project: usbref
ms.assetid: 4785D94B-271C-4F8E-B95B-87401E32CE42
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCX_ENDPOINT_CHARACTERISTIC, PUCX_ENDPOINT_CHARACTERISTIC, PUCX_ENDPOINT_CHARACTERISTIC structure pointer [Buses], UCX_ENDPOINT_CHARACTERISTIC, UCX_ENDPOINT_CHARACTERISTIC structure [Buses], _UCX_ENDPOINT_CHARACTERISTIC, buses.ucx_endpoint_characteristic, ucxendpoint/PUCX_ENDPOINT_CHARACTERISTIC, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucxendpoint.h
api_name:
-	UCX_ENDPOINT_CHARACTERISTIC
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC, *PUCX_ENDPOINT_CHARACTERISTIC
req.product: Windows 10 or later.
---

# _UCX_ENDPOINT_CHARACTERISTIC structure


## -description


Stores the characteristics of an endpoint. 


## -syntax


````
typedef struct _UCX_ENDPOINT_CHARACTERISTIC {
  ULONG                            Size;
  UCX_ENDPOINT_CHARACTERISTIC_TYPE CharacteristicType;
  union {
    UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY Priority;
  };
} UCX_ENDPOINT_CHARACTERISTIC, *PUCX_ENDPOINT_CHARACTERISTIC;
````


## -struct-fields




### -field Size

Size of this structure.


### -field CharacteristicType

A <a href="..\ucxendpoint\ne-ucxendpoint-_ucx_endpoint_characteristic_type.md">UCX_ENDPOINT_CHARACTERISTIC_TYPE</a>-type value that indicates the type of endpoint characteristic.


#### - Priority

A <a href="..\ucxendpoint\ne-ucxendpoint-_ucx_endpoint_characteristic_priority.md">UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY</a>-typed value that indicates the priority of the endpoint.


## -see-also

<a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_set_characteristic.md">EVT_UCX_ENDPOINT_SET_CHARACTERISTIC</a>



<a href="..\ucxendpoint\ne-ucxendpoint-_ucx_endpoint_characteristic_priority.md">UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY</a>



 

 


