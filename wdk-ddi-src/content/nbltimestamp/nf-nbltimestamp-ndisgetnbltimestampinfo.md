---
UID: NF:nbltimestamp.NdisGetNblTimestampInfo
title: NdisGetNblTimestampInfo
ms.date: 01/31/2021
ms.topic: language-reference
targetos: Windows
description: NdisGetNblTimestampInfo retrieves a hardware or software timestamp stored in a NET_BUFFER_LIST.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis/nbltimestamp.h
req.idl: 
req.include-header: ndis.h
req.irql: 
req.kmdf-ver: 
req.lib: ndis.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1. Supported in NDIS 6.82 and later.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
ms.custom: RS5
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - nbltimestamp.h
api_name:
 - NdisGetNblTimestampInfo
f1_keywords:
 - NdisGetNblTimestampInfo
 - nbltimestamp/NdisGetNblTimestampInfo
dev_langs:
 - c++
---

# NdisGetNblTimestampInfo function


## -description

Miniport drivers call **NdisGetNblTimestampInfo** to retrieve a hardware or software timestamp stored in a  [**NET\_BUFFER\_LIST**](../nbl/ns-nbl-net_buffer_list.md) (NBL) structure.

## -parameters

### -param Nbl

[_In_]
A pointer to the NBL where the miniport stored the timestamp.

### -param NblTimestamp

[_Out_] 
A pointer to a [**NET_BUFFER_LIST_TIMESTAMP**](ns-nbltimestamp-net_buffer_list_timestamp.md) structure. When this function returns, this member contains the timestamp stored in the NBL.


## -remarks

Miniport drivers can use [**NdisSetNblTimestampInfo**](nf-nbltimestamp-ndissetnbltimestampinfo.md) and [**NdisCopyNblTimestampInfo**](nf-nbltimestamp-ndiscopynbltimestampinfo.md) to set and copy timestamps.

For more information on generating hardware and software timestamps, see [Attaching timestamps to packets](/windows-hardware/drivers/network/attaching-timestamps-to-packets).

## -see-also

[**NET_BUFFER_LIST_TIMESTAMP**](ns-nbltimestamp-net_buffer_list_timestamp.md)

[**NdisSetNblTimestampInfo**](nf-nbltimestamp-ndissetnbltimestampinfo.md)

[**NdisCopyNblTimestampInfo**](nf-nbltimestamp-ndiscopynbltimestampinfo.md)

[Overview of NDIS packet timestamping](/windows-hardware/drivers/network/overview-of-ndis-packet-timestamping)

[Attaching timestamps to packets](/windows-hardware/drivers/network/attaching-timestamps-to-packets)


