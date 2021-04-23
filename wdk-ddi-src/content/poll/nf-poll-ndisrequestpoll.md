---
UID: NF:poll.NdisRequestPoll
tech.root: netvista
title: NdisRequestPoll
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
req.irql: <= HIGH_LEVEL
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
 - NdisRequestPoll
f1_keywords:
 - NdisRequestPoll
 - poll/NdisRequestPoll
dev_langs:
 - c++
---

## -description

Miniport drivers call **NdisRequestPoll** to ask NDIS to start calling the miniport's poll routine.

## -parameters

### -param PollHandle

[_In_] The handle returned by [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md) that identifies the miniport's poll routine.

### -param Reserved

[_Reserved_] Reserved for system use.

## -remarks

## -see-also

