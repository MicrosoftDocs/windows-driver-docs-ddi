---
UID: NS:1394._ADDRESS_OFFSET
title: _ADDRESS_OFFSET (1394.h)
description: The ADDRESS_OFFSET structure specifies the 48-bit address within a device's IEEE 1394 address space.
old-location: ieee\address_offset.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["ADDRESS_OFFSET structure"]
ms.keywords: "*PADDRESS_OFFSET, 1394/ADDRESS_OFFSET, 1394/PADDRESS_OFFSET, 1394stct_7b2efd3c-fcd3-4a01-8ece-8a70975787b1.xml, ADDRESS_OFFSET, ADDRESS_OFFSET structure [Buses], IEEE.address_offset, PADDRESS_OFFSET, PADDRESS_OFFSET structure pointer [Buses], _ADDRESS_OFFSET"
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
req.typenames: ADDRESS_OFFSET, *PADDRESS_OFFSET
f1_keywords:
 - _ADDRESS_OFFSET
 - 1394/_ADDRESS_OFFSET
 - PADDRESS_OFFSET
 - 1394/PADDRESS_OFFSET
 - ADDRESS_OFFSET
 - 1394/ADDRESS_OFFSET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - _ADDRESS_OFFSET
 - PADDRESS_OFFSET
 - ADDRESS_OFFSET
---

# _ADDRESS_OFFSET structure


## -description

The ADDRESS_OFFSET structure specifies the 48-bit address within a device's IEEE 1394 address space.

## -struct-fields

### -field Off_High

Specifies the high order offset for a IEEE 1394 address.

### -field Off_Low

Specifies the low order offset for a IEEE 1394 address.

## -see-also

<a href="/windows-hardware/drivers/ddi/1394/ns-1394-_get_local_host_info6">GET_LOCAL_HOST_INFO6</a>



<a href="/windows-hardware/drivers/ddi/1394/ns-1394-_io_address">IO_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>

