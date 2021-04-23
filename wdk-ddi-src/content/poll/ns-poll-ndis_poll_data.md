---
UID: NS:poll._NDIS_POLL_DATA
tech.root: netvista
title: NDIS_POLL_DATA
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: poll.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: NDIS_POLL_DATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - poll.h
api_name:
 - _NDIS_POLL_DATA
 - NDIS_POLL_DATA
f1_keywords:
 - _NDIS_POLL_DATA
 - poll/_NDIS_POLL_DATA
 - NDIS_POLL_DATA
 - poll/NDIS_POLL_DATA
dev_langs:
 - c++
---

## -description

## -struct-fields

### -field Header

The [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header.md) structure for the **NDIS_POLL_DATA** structure. Set the members of this structure as follows:

- **Type** = NDIS_OBJECT_TYPE_DEFAULT
- **Revision** = NDIS_POLL_DATA_REVISION_1
- **Size** = NDIS_SIZEOF_NDIS_POLL_DATA_REVISION_1

### -field Transmit

A [**NDIS_POLL_TRANSMIT_DATA**](ns-poll-ndis_poll_transmit_data.md) structure.

### -field Receive

A [**NDIS_POLL_RECEIVE_DATA**](ns-poll-ndis_poll_receive_data.md) structure.

## -remarks

## -see-also

[**NDIS_POLL_TRANSMIT_DATA**](ns-poll-ndis_poll_transmit_data.md)

[**NDIS_POLL_RECEIVE_DATA**](ns-poll-ndis_poll_receive_data.md)