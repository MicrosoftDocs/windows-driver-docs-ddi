---
UID: NS:nbltimestamp._NET_BUFFER_LIST_TIMESTAMP
title: NET_BUFFER_LIST_TIMESTAMP
ms.date: 01/31/2021
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_LIST_TIMESTAMP structure represents a timestamp that the NIC hardware generates on reception or transmission of a packet.
tech.root: netvista 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndis/nbltimestamp.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1. Supported in NDIS 6.82 and later.
req.target-min-winversvr:
req.target-type: 
req.typenames: NET_BUFFER_LIST_TIMESTAMP, *PNET_BUFFER_LIST_TIMESTAMP
req.umdf-ver: 
req.unicode-ansi: 
ms.custom: RS5
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nbltimestamp.h
api_name:
 - _NET_BUFFER_LIST_TIMESTAMP
 - PNET_BUFFER_LIST_TIMESTAMP
 - NET_BUFFER_LIST_TIMESTAMP
f1_keywords:
 - _NET_BUFFER_LIST_TIMESTAMP
 - nbltimestamp/_NET_BUFFER_LIST_TIMESTAMP
 - PNET_BUFFER_LIST_TIMESTAMP
 - nbltimestamp/PNET_BUFFER_LIST_TIMESTAMP
 - NET_BUFFER_LIST_TIMESTAMP
 - nbltimestamp/NET_BUFFER_LIST_TIMESTAMP
dev_langs:
 - c++
---

# _NET_BUFFER_LIST_TIMESTAMP structure


## -description

The **NET_BUFFER_LIST_TIMESTAMP** structure represents a software or hardware timestamp that is generated on reception or transmission of a packet.

## -struct-fields

### -field Timestamp

A 64-bit integer value that represents a software or hardware timestamp.

## -remarks

Miniport drivers can store a timestamp in the [**NET\_BUFFER\_LIST**](../nbl/ns-nbl-net_buffer_list.md) (NBL) structure's **NetBufferListInfo** array. Drivers can use the **NET_BUFFER_LIST_TIMESTAMP** structure to set the timestamp in the NBL's **NetBufferListInfo** field. The driver fills the **Timestamp** field of the **NET_BUFFER_LIST_TIMESTAMP** structure and calls  [**NdisSetNblTimestampInfo**](nf-nbltimestamp-ndissetnbltimestampinfo.md), passing in the structure.

Miniport drivers can use [**NdisGetNblTimestampInfo**](nf-nbltimestamp-ndisgetnbltimestampinfo.md) and [**NdisCopyNblTimestampInfo**](nf-nbltimestamp-ndiscopynbltimestampinfo.md) to retrieve and copy timestamps.

For more information on generating hardware and software timestamps, see [Attaching timestamps to packets](/windows-hardware/drivers/network/attaching-timestamps-to-packets).


## -see-also

[**NdisSetNblTimestampInfo**](nf-nbltimestamp-ndissetnbltimestampinfo.md)

[**NdisGetNblTimestampInfo**](nf-nbltimestamp-ndisgetnbltimestampinfo.md)

[**NdisCopyNblTimestampInfo**](nf-nbltimestamp-ndiscopynbltimestampinfo.md)

[Overview of NDIS packet timestamping](/windows-hardware/drivers/network/overview-of-ndis-packet-timestamping)

[Attaching timestamps to packets](/windows-hardware/drivers/network/attaching-timestamps-to-packets)

