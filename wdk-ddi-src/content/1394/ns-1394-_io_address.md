---
UID: NS:1394._IO_ADDRESS
title: _IO_ADDRESS (1394.h)
description: The IO_ADDRESS structure specifies the 1394 64-bit destination address for read, write and lock operations.
old-location: ieee\io_address.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["IO_ADDRESS structure"]
ms.keywords: "*PIO_ADDRESS, 1394/IO_ADDRESS, 1394/PIO_ADDRESS, 1394stct_1683915b-161d-4741-91b9-32f632b56e59.xml, IEEE.io_address, IO_ADDRESS, IO_ADDRESS structure [Buses], PIO_ADDRESS, PIO_ADDRESS structure pointer [Buses], _IO_ADDRESS"
req.header: 1394.h
req.include-header: 1394.h
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
targetos: Windows
req.typenames: IO_ADDRESS, *PIO_ADDRESS
f1_keywords:
 - _IO_ADDRESS
 - 1394/_IO_ADDRESS
 - PIO_ADDRESS
 - 1394/PIO_ADDRESS
 - IO_ADDRESS
 - 1394/IO_ADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - _IO_ADDRESS
 - PIO_ADDRESS
 - IO_ADDRESS
---

# _IO_ADDRESS structure


## -description

The IO_ADDRESS structure specifies the 1394 64-bit destination address for read, write and lock operations.

## -struct-fields

### -field IA_Destination_ID

Holds a structure of type <a href="/windows-hardware/drivers/ddi/1394/ns-1394-_node_address">NODE_ADDRESS</a> containing the destination node address.

### -field IA_Destination_Offset

Holds a structure of type <a href="/windows-hardware/drivers/ddi/1394/ns-1394-_address_offset">ADDRESS_OFFSET</a> that specifies the index of the 1394 address within the address array.

## -see-also

<a href="/windows-hardware/drivers/ddi/1394/ns-1394-_address_offset">ADDRESS_OFFSET</a>



<a href="/windows-hardware/drivers/ddi/1394/ns-1394-_node_address">NODE_ADDRESS</a>



<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ASYNC_LOCK</a>



<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ASYNC_READ</a>



<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ASYNC_WRITE</a>



<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_GET_CONFIGURATION_INFO</a>

