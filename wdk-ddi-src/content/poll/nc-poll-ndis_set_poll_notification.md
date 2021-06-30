---
UID: NC:poll.NDIS_SET_POLL_NOTIFICATION
tech.root: netvista
title: NDIS_SET_POLL_NOTIFICATION
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: Miniport drivers implement the NdisSetPollNotification callback function to enable/disable the interrupt associated with a Poll object.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: poll.h
req.idl: 
req.include-header: ndis.h
req.irql: <= DISPATCH_LEVEL
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

Miniport drivers implement the *NdisSetPollNotification* callback function to enable or disable the interrupt associated with a Poll object.

## -parameters

### -param Context

[_In_] A pointer to the context information that the driver provided when it created the Poll object.

### -param Notification

[_Inout_] A pointer to an [**NDIS_POLL_NOTIFICATION**](ns-poll-ndis_poll_notification.md) structure containing the interrupt state for the Poll object.

## -returns

## -remarks

Miniport drivers register the *NdisSetPollNotification* callback during miniport adapter initialization. Drivers specify an entry point for the *NdisSetPollNotification* function at the **SetPollNotificationHandler** parameter of the [**NDIS_POLL_CHARACTERISTICS**](ns-poll-ndis_poll_characteristics.md) structure before calling [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md).

NDIS typically invokes the *NdisSetPollNotification* callback when it detects that the miniport driver is not making forward progress in [*NdisPoll*](nc-poll-ndis_poll.md). NDIS uses *NdisSetPollNotification* to tell the driver that it will stop invoking *NdisPoll*. The driver should invoke [**NdisRequestPoll**](nf-poll-ndisrequestpoll.md) when new work is ready to be processed. 

## -see-also

[*NdisPoll*](nc-poll-ndis_poll.md)

[**NdisRequestPoll**](nf-poll-ndisrequestpoll.md)

[**NDIS_POLL_NOTIFICATION**](ns-poll-ndis_poll_notification.md)

[**NDIS_POLL_CHARACTERISTICS**](ns-poll-ndis_poll_characteristics.md)

[**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md)
