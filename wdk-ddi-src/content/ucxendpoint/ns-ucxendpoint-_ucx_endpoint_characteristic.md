---
UID: NS:ucxendpoint._UCX_ENDPOINT_CHARACTERISTIC
title: _UCX_ENDPOINT_CHARACTERISTIC
author: windows-driver-content
description: Stores the characteristics of an endpoint.
old-location: buses\ucx_endpoint_characteristic.htm
old-project: usbref
ms.assetid: 4785D94B-271C-4F8E-B95B-87401E32CE42
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PUCX_ENDPOINT_CHARACTERISTIC, *PUCX_ENDPOINT_CHARACTERISTIC, buses.ucx_endpoint_characteristic, ucxendpoint/UCX_ENDPOINT_CHARACTERISTIC, ucxendpoint/PUCX_ENDPOINT_CHARACTERISTIC, _UCX_ENDPOINT_CHARACTERISTIC, UCX_ENDPOINT_CHARACTERISTIC structure [Buses], UCX_ENDPOINT_CHARACTERISTIC, PUCX_ENDPOINT_CHARACTERISTIC structure pointer [Buses]
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ucxendpoint.h
apiname: 
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




### -field Priority

A <a href="..\ucxendpoint\ne-ucxendpoint-_ucx_endpoint_characteristic_priority.md">UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY</a>-typed value that indicates the priority of the endpoint.


### -field Size

Size of this structure.


### -field CharacteristicType

A <a href="..\ucxendpoint\ne-ucxendpoint-_ucx_endpoint_characteristic_type.md">UCX_ENDPOINT_CHARACTERISTIC_TYPE</a>-type value that indicates the type of endpoint characteristic.


## -see-also

<a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_set_characteristic.md">EVT_UCX_ENDPOINT_SET_CHARACTERISTIC</a>

<a href="..\ucxendpoint\ne-ucxendpoint-_ucx_endpoint_characteristic_priority.md">UCX_CONTROLLER_ENDPOINT_CHARACTERISTIC_PRIORITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_ENDPOINT_CHARACTERISTIC structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

