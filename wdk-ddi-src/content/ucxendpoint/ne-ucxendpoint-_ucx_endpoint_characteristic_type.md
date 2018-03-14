---
UID: NE:ucxendpoint._UCX_ENDPOINT_CHARACTERISTIC_TYPE
title: "_UCX_ENDPOINT_CHARACTERISTIC_TYPE"
author: windows-driver-content
description: Defines values that indicates the type of endpoint characteristic.
old-location: buses\ucx_endpoint_characteristic_type.htm
old-project: usbref
ms.assetid: 1F49C8CA-51CE-49B2-AC37-C114A688B1DB
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCX_ENDPOINT_CHARACTERISTIC_TYPE, UCX_ENDPOINT_CHARACTERISTIC_TYPE enumeration [Buses], UCX_ENDPOINT_CHARACTERISTIC_TYPE_PRIORITY, _UCX_ENDPOINT_CHARACTERISTIC_TYPE, buses.ucx_endpoint_characteristic_type, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_TYPE, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC_TYPE_PRIORITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucxendpoint.h
api_name:
-	UCX_ENDPOINT_CHARACTERISTIC_TYPE
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# _UCX_ENDPOINT_CHARACTERISTIC_TYPE enumeration


## -description


Defines values that indicates the type of endpoint characteristic.


## -syntax


````
typedef enum _UCX_ENDPOINT_CHARACTERISTIC_TYPE { 
  UCX_ENDPOINT_CHARACTERISTIC_TYPE_PRIORITY  = 0x01
} UCX_ENDPOINT_CHARACTERISTIC_TYPE;
````


## -enum-fields




### -field UCX_ENDPOINT_CHARACTERISTIC_TYPE_PRIORITY

The type of characteristic of the endpoint.


## -see-also

<a href="..\ucxendpoint\ns-ucxendpoint-_ucx_endpoint_characteristic.md">UCX_ENDPOINT_CHARACTERISTIC</a>



 

 


