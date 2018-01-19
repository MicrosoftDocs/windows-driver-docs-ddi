---
UID: NE:ucxendpoint._UCX_ENDPOINT_CHARACTERISTIC_TYPE
title: _UCX_ENDPOINT_CHARACTERISTIC_TYPE
author: windows-driver-content
description: Defines values that indicates the type of endpoint characteristic.
old-location: buses\ucx_endpoint_characteristic_type.htm
old-project: usbref
ms.assetid: 1F49C8CA-51CE-49B2-AC37-C114A688B1DB
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _UCX_ENDPOINT_CHARACTERISTIC_TYPE, UCX_ENDPOINT_CHARACTERISTIC_TYPE
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
req.alt-api: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.alt-loc: Ucxendpoint.h
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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ucxendpoint\ns-ucxendpoint-_ucx_endpoint_characteristic.md">UCX_ENDPOINT_CHARACTERISTIC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_ENDPOINT_CHARACTERISTIC_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

