---
UID: NC:poll.NDIS_SET_POLL_NOTIFICATION
tech.root: netvista
title: NDIS_SET_POLL_NOTIFICATION
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
 - LibDef
api_location:
 - poll.h
api_name:
 - NDIS_SET_POLL_NOTIFICATION
f1_keywords:
 - NDIS_SET_POLL_NOTIFICATION
 - poll/NDIS_SET_POLL_NOTIFICATION
dev_langs:
 - c++
---

## -description

Miniport drivers implement the *NDIS_SET_POLL_NOTIFICATION* callback function to perform miniport-specific processing when new packets are received.

## -parameters

### -param Context

[_In_] A pointer to a context area.

### -param Notification

[_Inout_] A pointer to an [**NDIS_POLL_NOTIFICATION**](ns-poll-ndis_poll_notification.md) structure.

## -returns

## -remarks

## -see-also

[**NDIS_POLL_NOTIFICATION**](ns-poll-ndis_poll_notification.md)