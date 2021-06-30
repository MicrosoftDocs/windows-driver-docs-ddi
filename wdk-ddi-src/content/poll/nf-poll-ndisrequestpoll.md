---
UID: NF:poll.NdisRequestPoll
tech.root: netvista
title: NdisRequestPoll
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: Miniport drivers call NdisRequestPoll to ask NDIS to execute the NdisPoll callback for this Poll object.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: poll.h
req.idl: 
req.include-header: ndis.h
req.irql: <= HIGH_LEVEL
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
 - NdisRequestPoll
f1_keywords:
 - NdisRequestPoll
 - poll/NdisRequestPoll
dev_langs:
 - c++
---

## -description

Miniport drivers call **NdisRequestPoll** to ask NDIS to execute the [*NdisPoll*](nc-poll-ndis_poll.md) callback for this Poll object.

## -parameters

### -param PollHandle

[_In_] A handle to the Poll object returned by a successful call to [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md).

### -param Reserved

[_Reserved_] Reserved for future use. The driver must set to **zero**.

## -remarks

A driver calls **NdisRequestPoll** to ask NDIS to execute the [*NdisPoll*](nc-poll-ndis_poll.md) callback for this Poll object. It is guaranteed that NDIS will invoke the *NdisPoll* callback at least once. **NdisRequestPoll** can be called from any IRQL, typically from interrupt handling routines. 

## -see-also

[*NdisPoll*](nc-poll-ndis_poll.md)

[**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md)
