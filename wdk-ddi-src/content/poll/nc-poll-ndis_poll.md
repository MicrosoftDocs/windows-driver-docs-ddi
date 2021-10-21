---
UID: NC:poll.NDIS_POLL
tech.root: netvista
title: NDIS_POLL
ms.date: 05/13/2021
targetos: Windows
description: Miniport drivers implement the NdisPoll callback to poll for receive indications and send completions.
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
 - NDIS_POLL
f1_keywords:
 - NDIS_POLL
 - poll/NDIS_POLL
dev_langs:
 - c++
---

## -description

Miniport drivers implement the *NdisPoll* callback function that NDIS will poll for receive indications and send completions.

## -parameters

### -param Context [_In_]

A pointer to the context information that the driver provided when it created the Poll object.

### -param PollData [_Inout_]

A pointer to an [**NDIS_POLL_DATA**](ns-poll-ndis_poll_data.md) structure that the driver should use to perform receive indications and send completions. It also contains details about how many NBLs need to be indicated.

## -returns

## -remarks

Miniport drivers register the *NdisPoll* callback during miniport adapter initialization. Drivers specify an entry point for the *NdisPoll* function at the **PollHandler** parameter of the [**NDIS_POLL_CHARACTERISTICS**](ns-poll-ndis_poll_characteristics.md) structure before calling [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md).

NDIS will first invoke the *NdisPoll* callback when the driver calls [**NdisRequestPoll**](nf-poll-ndisrequestpoll.md). NDIS will keep invoking *NdisPoll* while the driver is making forward progress on receive indications or transmit completions. 

The *NdisPoll* callback may be invoked at both PASSIVE_LEVEL and DISPATCH_LEVEL IRQL. The driver shouldn't make assumptions about which level it will be.

The driver must check the **receive** or **transmit** parameters of the [**NDIS_POLL_DATA**](ns-poll-ndis_poll_data.md) structure to get the maximum number of NBLs it can indicate or complete. 

For receive indications, the driver should:
1. Fetch up to the maximum number of Rx packets it can indicate.
1. Initialize the NBLs.
1. Add them to the NBL queue provided by the [**NDIS_POLL_RECEIVE_DATA**](ns-poll-ndis_poll_receive_data.md) structure (located in the [**NDIS_POLL_DATA**](ns-poll-ndis_poll_data.md) structure of the *NdisPoll* **PollData** parameter). 
1. Exit the callback. 

For transmit completions, the driver should:
1. Fetch up to the maximum number of Tx packets it can complete. 
1. Complete the NBLs.
1. Add them to the NBL queue provided by the [**NDIS_POLL_TRANSMIT_DATA**](ns-poll-ndis_poll_transmit_data.md) structure (located in the [**NDIS_POLL_DATA**](ns-poll-ndis_poll_data.md) structure of the *NdisPoll* **PollData** parameter).
1. Exit the callback. 

The driver should not enable the Poll object's interrupt before exiting the *NdisPoll* function. NDIS will keep polling the driver until it assesses that no forward progress is being made. At this point NDIS will stop polling and ask the driver to reenable the interrupt by invoking the [*NdisSetPollNotification*](nc-poll-ndis_set_poll_notification.md) callback.

## -see-also

[*NdisSetPollNotification*](nc-poll-ndis_set_poll_notification.md)

[**NDIS_POLL_CHARACTERISTICS**](ns-poll-ndis_poll_characteristics.md)

[**NDIS_POLL_DATA**](ns-poll-ndis_poll_data.md)

[**NDIS_POLL_RECEIVE_DATA**](ns-poll-ndis_poll_receive_data.md)

[**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md)

[**NdisRequestPoll**](nf-poll-ndisrequestpoll.md)
