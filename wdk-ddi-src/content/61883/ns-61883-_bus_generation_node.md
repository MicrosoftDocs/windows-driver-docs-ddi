---
UID: NS:61883._BUS_GENERATION_NODE
title: _BUS_GENERATION_NODE
author: windows-driver-content
description: The BUS_GENERATION_NODE structure is used in conjunction with the Av61883_GetUnitInfo request to retrieve bus characteristics.
old-location: ieee\bus_generation_node.htm
old-project: IEEE
ms.assetid: 8db151ca-6358-41b0-a96a-e69b9d6c2c95
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _BUS_GENERATION_NODE, *PBUS_GENERATION_NODE, BUS_GENERATION_NODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BUS_GENERATION_NODE
req.alt-loc: 61883.h
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
req.typenames: *PBUS_GENERATION_NODE, BUS_GENERATION_NODE
---

# _BUS_GENERATION_NODE structure



## -description
The BUS_GENERATION_NODE structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a> request to retrieve bus characteristics. 



## -syntax

````
typedef struct _BUS_GENERATION_NODE {
  ULONG        GenerationCount;
  NODE_ADDRESS LocalNodeAddress;
  NODE_ADDRESS DeviceNodeAddress;
} BUS_GENERATION_NODE, *PBUS_GENERATION_NODE;
````


## -struct-fields

### -field GenerationCount

The current bus generation count.


### -field LocalNodeAddress

The current node address of the local node.


### -field DeviceNodeAddress

The current node address of the device.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20BUS_GENERATION_NODE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

