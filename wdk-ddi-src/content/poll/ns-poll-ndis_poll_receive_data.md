---
UID: NS:poll._NDIS_POLL_RECEIVE_DATA
tech.root: netvista
title: NDIS_POLL_RECEIVE_DATA
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: Miniport drivers use the NDIS_POLL_RECEIVE_DATA structure to perform receive indications when using a Poll object. 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: poll.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
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

Miniport drivers use the **NDIS_POLL_RECEIVE_DATA** structure to perform receive indications when using a Poll object. 

## -struct-fields

### -field MaxNblsToIndicate

The maximum number of [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structures (NBLs) that a miniport driver should include in a receive indication. If this value is **NDIS_ANY_NUMBER_OF_NBLS**, the driver may indicate an unlimited number of NBLs.

### -field Reserved1

Reserved for future use, must be **zero**.

### -field IndicatedNblChain

A pointer that the miniport driver assigns to an NBL chain with the indicated receive packets.

### -field NumberOfIndicatedNbls

The number of NBLs that the driver placed in the **IndicatedNblChain**. The driver can set this value to **NDIS_ANY_NUMBER_OF_NBLS** if it wants NDIS to count the NBLs.

### -field NumberOfRemainingNbls

Specifies the number of NBLs thta remain to be indicated. A value of **zero** indicates that there are no more NBLs to indicate. A value of **NDIS_ANY_NUMBER_OF_NBLS** indicates that there is some unknown (but non-zero) number of NBLs remaining. The driver should only fill this field with a precise number if it is cheap to calculate.

### -field Flags

A combination of zero or more of the following flags: 

`NDIS_RECEIVE_FLAGS_SINGLE_ETHER_TYPE` 

`NDIS_RECEIVE_FLAGS_SINGLE_VLAN` 

`NDIS_RECEIVE_FLAGS_PERFECT_FILTERED` 

`NDIS_RECEIVE_FLAGS_SINGLE_QUEUE` 

`NDIS_RECEIVE_FLAGS_SHARED_MEMORY_VALID` 

### -field Reserved2

Reserved for future use, must be **zero**.

### -field Reserved3

Reserved for future use, must be **zero**.

## -remarks

An instance the **NDIS_POLL_RECEIVE_DATA** structure is contained in the [**NDIS_POLL_DATA**](ns-poll-ndis_poll_data.md) structure that NDIS passes to the miniport driver as a parameter to the [*NdisPoll*](nc-poll-ndis_poll.md) callback. 

## -see-also

[*NdisPoll*](nc-poll-ndis_poll.md) 

[**NDIS_POLL_DATA**](ns-poll-ndis_poll_data.md)

[**NDIS_POLL_TRANSMIT_DATA**](ns-poll-ndis_poll_transmit_data.md)
