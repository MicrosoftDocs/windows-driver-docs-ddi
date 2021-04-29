---
UID: NF:poll.NdisSetPollAffinity
tech.root: netvista
title: NdisSetPollAffinity
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The NdisSetPollAffinity function to locks an NdisPoll callback to a set of processors in a group. 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: poll.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - poll.h
api_name:
 - NdisSetPollAffinity
f1_keywords:
 - NdisSetPollAffinity
 - poll/NdisSetPollAffinity
dev_langs:
 - c++
---

## -description

A miniport driver calls the **NdisSetPollAffinity** function to lock an [*NdisPoll*](nc-poll-ndis_poll.md) callback to a set of processors in a group. 

## -parameters

### -param PollHandle

[_In_] A handle to the Poll object returned by a successful call to [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md).

### -param PollAffinity

[_In_] A pointer to a driver-initialized [**PROCESSOR_NUMBER**](../miniport/ns-miniport-_processor_number.md) structure that describes the cores on which the driver wants the [*NdisPoll*](nc-poll-ndis_poll.md) callback for this object to be called.

## -remarks

After **NdisSetPollAffinity** returns one poll iteration can still occur with the old affinity.

## -see-also

[*NdisPoll*](nc-poll-ndis_poll.md)

[**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md)