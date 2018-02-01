---
UID: NS:1394._IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT
title: "_IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT"
author: windows-driver-content
description: This structure contains the fields necessary to carry out a Get1394AddressFromDeviceObject request.
old-location: ieee\irb_req_get_1394_address_from_device_object.htm
old-project: IEEE
ms.assetid: 457E3A4E-6845-473C-AACD-7CC00080C34B
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT structure [Buses], IEEE.irb_req_get_1394_address_from_device_object, 1394/IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT, IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT, _IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT
product: Windows
targetos: Windows
req.typenames: IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT
---

# _IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT structure


## -description


This structure contains the fields necessary to carry out a Get1394AddressFromDeviceObject request.


## -syntax


````
typedef struct _IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT {
  ULONG        fulFlags;
  NODE_ADDRESS NodeAddress;
} IRB_REQ_GET_1394_ADDRESS_FROM_DEVICE_OBJECT;
````


## -struct-fields




### -field fulFlags

Specifies which device's node address we are querying. Zero indicates the calling device. USE_LOCAL_NODE indicates the local host controller.


### -field NodeAddress

Contains the NODE_ADDRESS structure describing the device's node address. In the case of virtual devices, the bus driver returns the node address of the host controller in the stack where the virtual device's device object is loaded. 

