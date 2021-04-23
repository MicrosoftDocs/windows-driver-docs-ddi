---
UID: NS:poll._NDIS_POLL_RECEIVE_DATA
tech.root: netvista
title: NDIS_POLL_RECEIVE_DATA
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
req.typenames: NDIS_POLL_RECEIVE_DATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - poll.h
api_name:
 - _NDIS_POLL_RECEIVE_DATA
 - NDIS_POLL_RECEIVE_DATA
f1_keywords:
 - _NDIS_POLL_RECEIVE_DATA
 - poll/_NDIS_POLL_RECEIVE_DATA
 - NDIS_POLL_RECEIVE_DATA
 - poll/NDIS_POLL_RECEIVE_DATA
dev_langs:
 - c++
---

## -description

## -struct-fields

### -field MaxNblsToIndicate

The maximum number of [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structures that a miniport driver should include in a receive indication. If this value is NDIS_INDICATE_ALL_NBLS, the miniport can indicate all of the **NET_BUFFER_LIST** structures that it has.

### -field Reserved1

### -field IndicatedNblChain

A linked list of **NET_BUFFER_LIST** structures that the miniport driver indicated.

### -field NumberOfIndicatedNbls

Specifies the number of **NET_BUFFER_LIST** structures that the miniport driver indicated.

### -field NumberOfRemainingNbls

Specifies the number of **NET_BUFFER_LIST** structures remaining after the miniport driver processes the maximum number of structures that NDIS requested in the **MaxNblsToIndicate** member.

### -field Flags

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to **zero**.

### -field Reserved2

### -field Reserved3

## -remarks

## -see-also

[**NDIS_POLL_TRANSMIT_DATA**](ns-poll-ndis_poll_transmit_data.md)
