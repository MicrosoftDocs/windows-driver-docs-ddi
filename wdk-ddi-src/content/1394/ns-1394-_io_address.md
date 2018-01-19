---
UID: NS:1394._IO_ADDRESS
title: _IO_ADDRESS
author: windows-driver-content
description: The IO_ADDRESS structure specifies the 1394 64-bit destination address for read, write and lock operations.
old-location: ieee\io_address.htm
old-project: IEEE
ms.assetid: db703d46-d37f-442a-a543-ce9e9c5ea3cb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _IO_ADDRESS, *PIO_ADDRESS, IO_ADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_ADDRESS
req.alt-loc: 1394.h
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
req.typenames: *PIO_ADDRESS, IO_ADDRESS
---

# _IO_ADDRESS structure



## -description
The IO_ADDRESS structure specifies the 1394 64-bit destination address for read, write and lock operations.



## -syntax

````
typedef struct _IO_ADDRESS {
  NODE_ADDRESS   IA_Destination_ID;
  ADDRESS_OFFSET IA_Destination_Offset;
} IO_ADDRESS, *PIO_ADDRESS;
````


## -struct-fields

### -field IA_Destination_ID

Holds a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537435">NODE_ADDRESS</a> containing the destination node address.


### -field IA_Destination_Offset

Holds a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536906">ADDRESS_OFFSET</a> that specifies the index of the 1394 address within the address array.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537642">REQUEST_GET_CONFIGURATION_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537633">REQUEST_ASYNC_LOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537634">REQUEST_ASYNC_READ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537636">REQUEST_ASYNC_WRITE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537435">NODE_ADDRESS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536906">ADDRESS_OFFSET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20IO_ADDRESS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

