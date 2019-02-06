---
UID: NS:netrxqueue._NET_RXQUEUE_BUFFER_LAYOUT_HINT
title: _NET_RXQUEUE_BUFFER_LAYOUT_HINT (netrxqueue.h)
description: The NET_RXQUEUE_BUFFER_LAYOUT_HINT structure represents receive buffer layout hints returned to a client driver from the upper layer.
tech.root: netvista
ms.assetid: e9d6b199-e950-4c70-9ac3-0bdf3bbf2616
ms.date: 02/09/2018
ms.topic: struct
ms.keywords: _NET_RXQUEUE_BUFFER_LAYOUT_HINT, *PNET_RXQUEUE_BUFFER_LAYOUT_HINT, NET_RXQUEUE_BUFFER_LAYOUT_HINT, 
req.header: netrxqueue.h
req.include-header: netadaptercx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.23
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_RXQUEUE_BUFFER_LAYOUT_HINT, *PNET_RXQUEUE_BUFFER_LAYOUT_HINT
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netrxqueue.h
apiname: 
-	NET_RXQUEUE_BUFFER_LAYOUT_HINT
product:
-	Windows
targetos: Windows
product:
- Windows
---

# _NET_RXQUEUE_BUFFER_LAYOUT_HINT structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1809.

The **NET_RXQUEUE_BUFFER_LAYOUT_HINT** structure represents receive buffer layout hints returned to a client driver from the upper layer.

## -struct-fields

### -field MinimumBackfillSize
The minimum space that should be unused in the beginning of the first fragment of the ring buffer.
 
### -field L3HeaderAlignment
The ideal alignment for the start of the L3 header. This member's value is in the form *N-1*, where *N* is the alignment. For example, TCP/IP performance is optimized with a 4-byte alignment boundary, so this member would be set to 3 in that case. You can use the **FILE_XXX_ALIGNMENT** constants, such as **FILE_QUAD_ALIGNMENT**, to name a specific alignment.

## -remarks
The information in this structure is set by the upper layer.



## -see-also
