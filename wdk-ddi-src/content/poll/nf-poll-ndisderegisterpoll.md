---
UID: NF:poll.NdisDeregisterPoll
tech.root: netvista
title: NdisDeregisterPoll
ms.date: 05/13/2021
targetos: Windows
description: A miniport driver calls NdisDeregisterPoll to deregister a Poll object.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: poll.h
req.idl: 
req.include-header: ndis.h
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11
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
 - NdisDeregisterPoll
f1_keywords:
 - NdisDeregisterPoll
 - poll/NdisDeregisterPoll
dev_langs:
 - c++
---

## -description

A miniport driver calls the **NdisDeregisterPoll** function to deregister a Poll object it previously registered with a call to the [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md) function.

## -parameters

### -param PollHandle [_In_]

A handle to the Poll object returned by a successful call to [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md).

## -remarks

The **NdisDeregisterPoll** runs down any polling currently in progress.

Drivers typically call **NdisDeregisterPoll** from their [*MiniportHalt*](../ndis/nc-ndis-miniport_halt.md) function. 

## -see-also

[**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md)
