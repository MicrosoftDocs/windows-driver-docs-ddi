---
UID: NF:poll.NdisSetPollAffinity
tech.root: netvista
title: NdisSetPollAffinity
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: 
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

A miniport driver calls the **NdisSetPollAffinity** function to specify the CPU affinity of the miniport's poll routine.

## -parameters

### -param PollHandle

[_In_] The handle returned by [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md) that identifies the miniport's poll routine.

### -param PollAffinity

[_In_] A pointer to the [**PROCESSOR_NUMBER**](../miniport/ns-miniport-_processor_number.md) of the target processor. 

## -remarks

## -see-also

