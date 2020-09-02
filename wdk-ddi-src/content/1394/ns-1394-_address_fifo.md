---
UID: NS:1394._ADDRESS_FIFO
title: _ADDRESS_FIFO (1394.h)
description: The ADDRESS_FIFO structure is an entry in a singly-linked list of MDLs used by the REQUEST_ALLOCATE_ADDRESS_RANGE IEEE 1394 bus request.
old-location: ieee\address_fifo.htm
tech.root: IEEE
ms.assetid: df2b6438-271d-4ea2-a06b-49a83415ca7a
ms.date: 02/15/2018
keywords: ["ADDRESS_FIFO structure"]
ms.keywords: "*PADDRESS_FIFO, 1394/ADDRESS_FIFO, 1394/PADDRESS_FIFO, 1394stct_bf7f3e1b-88a4-4c37-88ee-cf5d69595988.xml, ADDRESS_FIFO, ADDRESS_FIFO structure [Buses], IEEE.address_fifo, PADDRESS_FIFO, PADDRESS_FIFO structure pointer [Buses], _ADDRESS_FIFO"
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
req.typenames: ADDRESS_FIFO, *PADDRESS_FIFO
f1_keywords:
 - _ADDRESS_FIFO
 - 1394/_ADDRESS_FIFO
 - PADDRESS_FIFO
 - 1394/PADDRESS_FIFO
 - ADDRESS_FIFO
 - 1394/ADDRESS_FIFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - ADDRESS_FIFO
---

# _ADDRESS_FIFO structure


## -description

The ADDRESS_FIFO structure is an entry in a singly-linked list of MDLs used by the REQUEST_ALLOCATE_ADDRESS_RANGE IEEE 1394 bus request.

## -struct-fields

### -field FifoList

Specifies the rest of the list. This is a singly linked list.

### -field FifoMdl

Specifies the MDL for the FIFO element described by this entry of the list.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/1394/ns-1394-_notification_info_w2k">NOTIFICATION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>

