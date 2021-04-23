---
UID: NF:poll.NdisDeregisterPoll
tech.root: netvista
title: NdisDeregisterPoll
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
req.irql: PASSIVE_LEVEL
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
 - NdisDeregisterPoll
f1_keywords:
 - NdisDeregisterPoll
 - poll/NdisDeregisterPoll
dev_langs:
 - c++
---

## -description

A miniport driver calls the **NdisDeregisterPoll** function to release resources that it allocated with a previous call to the [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md) function.

## -parameters

### -param PollHandle

[_In_] The handle returned by [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md) that identifies the poll routine resources to be deregistered.

## -remarks



## -see-also

[**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md)
