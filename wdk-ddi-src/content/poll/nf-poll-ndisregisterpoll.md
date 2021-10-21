---
UID: NF:poll.NdisRegisterPoll
tech.root: netvista
title: NdisRegisterPoll
ms.date: 05/13/2021
targetos: Windows
description: A miniport driver calls the NdisRegisterPoll function to register a Poll object with NDIS. 
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
 - NdisRegisterPoll
f1_keywords:
 - NdisRegisterPoll
 - poll/NdisRegisterPoll
dev_langs:
 - c++
---

## -description

A miniport driver calls the **NdisRegisterPoll** function to register a Poll object with NDIS. 

## -parameters

### -param NdisHandle [_In_]

An NDIS-supplied miniport handle given to the driver in their [*MiniportInitialize*](../ndis/nc-ndis-miniport_initialize.md) callback.

### -param Context [_In_opt_]

A pointer to a block of driver-allocated context that stores information about the Poll object. NDIS passes this context information in calls to [*NdisPoll*](nc-poll-ndis_poll.md) and [*NdisSetPollNotification*](nc-poll-ndis_set_poll_notification.md).

### -param Characteristics [_In_]

A pointer to a driver-initialized [**NDIS_POLL_CHARACTERISTICS**](ns-poll-ndis_poll_characteristics.md) structure.

### -param PollHandle [_Out_]

On a successful return this location contains a handle for the new Poll object.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

Drivers typically register one Poll object for each RSS processor in their [*MiniportInitialize*](../ndis/nc-ndis-miniport_initialize.md) callback.

Drivers should call the [**NdisDeregisterPoll**](nf-poll-ndisderegisterpoll.md) to deregister the Poll object.

## -see-also

[*NdisPoll*](nc-poll-ndis_poll.md)

[*NdisSetPollNotification*](nc-poll-ndis_set_poll_notification.md)

[**NDIS_POLL_CHARACTERISTICS**](ns-poll-ndis_poll_characteristics.md)

[**NdisDeregisterPoll**](nf-poll-ndisderegisterpoll.md)
