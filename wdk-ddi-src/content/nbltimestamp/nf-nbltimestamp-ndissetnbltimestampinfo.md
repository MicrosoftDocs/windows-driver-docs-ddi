---
UID: NF:nbltimestamp.NdisSetNblTimestampInfo
title: NdisSetNblTimestampInfo
ms.date: 01/31/2021
ms.topic: language-reference
targetos: Windows
description: Miniport drivers call NdisSetNblTimestampInfo to store a hardware or software timestamp in a NET_BUFFER_LIST (NBL).
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
 - NdisSetNblTimestampInfo
f1_keywords:
 - NdisSetNblTimestampInfo
 - nbltimestamp/NdisSetNblTimestampInfo
dev_langs:
 - c++
---

# NdisSetNblTimestampInfo function


## -description

Miniport drivers call **NdisSetNblTimestampInfo** to store a hardware or software timestamp in a [**NET\_BUFFER\_LIST**](../nbl/ns-nbl-net_buffer_list.md) (NBL) structure.

## -parameters

### -param Nbl

[_Inout_]
A pointer to a [**NET_BUFFER_LIST**] structure.

### -param NblTimestamp

[_In_]
A pointer to an initialized [**NET_BUFFER_LIST_TIMESTAMP**](ns-nbltimestamp-net_buffer_list_timestamp.md) structure.

## -remarks

The miniport driver can store a software or hardware timestamp in an NBL's **NetBufferListInfo** array. The driver fills the **Timestamp** field of the [**NET_BUFFER_LIST_TIMESTAMP**](ns-nbltimestamp-net_buffer_list_timestamp.md) structure and calls **NdisSetNblTimestampInfo**, passing in the structure.

For more information on generating hardware and software timestamps, see [Attaching timestamps to packets](/windows-hardware/drivers/network/attaching-timestamps-to-packets).

## -see-also

[**NET_BUFFER_LIST_TIMESTAMP**](ns-nbltimestamp-net_buffer_list_timestamp.md)

[**NdisGetNblTimestampInfo**](nf-nbltimestamp-ndisgetnbltimestampinfo.md)

[**NdisCopyNblTimestampInfo**](nf-nbltimestamp-ndiscopynbltimestampinfo.md)

[Overview of NDIS packet timestamping](/windows-hardware/drivers/network/overview-of-ndis-packet-timestamping)

[Attaching timestamps to packets](/windows-hardware/drivers/network/attaching-timestamps-to-packets)