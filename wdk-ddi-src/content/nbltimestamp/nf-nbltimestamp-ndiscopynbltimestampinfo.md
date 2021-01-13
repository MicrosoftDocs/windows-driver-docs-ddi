---
UID: NF:nbltimestamp.NdisCopyNblTimestampInfo
title: NdisCopyNblTimestampInfo
ms.date: 01/31/2021
ms.topic: language-reference
targetos: Windows
description: Call NdisCopyNblTimestampInfo to copy a software or hardware timestamp from a source NET_BUFFER_LIST to a destination NET_BUFFER_LIST.
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
 - NdisCopyNblTimestampInfo
f1_keywords:
 - NdisCopyNblTimestampInfo
 - nbltimestamp/NdisCopyNblTimestampInfo
dev_langs:
 - c++
---

# NdisCopyNblTimestampInfo function


## -description

Miniport drivers call the **NdisCopyNblTimestampInfo** function to copy a software or hardware timestamp from a source [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure to a destination **NET_BUFFER_LIST** structure.

## -parameters

### -param NblDest

[_Inout_]
A pointer to a previously allocated destination [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

### -param NblSrc

[_In_]
A pointer to a previously allocated source **NET_BUFFER_LIST** structure where the timestamp was stored.

## -remarks

Miniport drivers can use [**NdisSetNblTimestampInfo**](nf-nbltimestamp-ndissetnbltimestampinfo.md) and [**NdisGetNblTimestampInfo**](nf-nbltimestamp-ndisgetnbltimestampinfo.md) to set and retrieve timestamps.

For more information on generating hardware and software timestamps, see [Attaching timestamps to packets](/windows-hardware/drivers/network/attaching-timestamps-to-packets).

## -see-also

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

[**NET_BUFFER_LIST_TIMESTAMP**](ns-nbltimestamp-net_buffer_list_timestamp.md)

[**NdisSetNblTimestampInfo**](nf-nbltimestamp-ndissetnbltimestampinfo.md)

[**NdisGetNblTimestampInfo**](nf-nbltimestamp-ndisgetnbltimestampinfo.md)

[Overview of NDIS packet timestamping](/windows-hardware/drivers/network/overview-of-ndis-packet-timestamping)

[Attaching timestamps to packets](/windows-hardware/drivers/network/attaching-timestamps-to-packets)
