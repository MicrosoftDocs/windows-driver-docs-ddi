---
UID: NS:poll._NDIS_POLL_CHARACTERISTICS
tech.root: netvista
title: NDIS_POLL_CHARACTERISTICS
ms.date: 05/13/2021
targetos: Windows
description: The NDIS_POLL_CHARACTERISTICS structure contains a Poll object’s NdisPoll and NdisSetPollNotification callback pointers.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: poll.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: NDIS_POLL_CHARACTERISTICS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - poll.h
api_name:
 - _NDIS_POLL_CHARACTERISTICS
 - NDIS_POLL_CHARACTERISTICS
f1_keywords:
 - _NDIS_POLL_CHARACTERISTICS
 - poll/_NDIS_POLL_CHARACTERISTICS
 - NDIS_POLL_CHARACTERISTICS
 - poll/NDIS_POLL_CHARACTERISTICS
dev_langs:
 - c++
---

## -description

The **NDIS_POLL_CHARACTERISTICS** structure contains a Poll object’s [*NdisPoll*](nc-poll-ndis_poll.md) and [*NdisSetPollNotification*](nc-poll-ndis_set_poll_notification.md) callback pointers.

## -struct-fields

### -field Header

The [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header.md) structure for the **NDIS_POLL_CHARACTERISTICS** structure. Set the members of this structure as follows: 

- **Type** = NDIS_OBJECT_TYPE_DEFAULT
- **Revision** = NDIS_POLL_CHARACTERISTICS_REVISION_1
- **Size** = NDIS_SIZEOF_NDIS_POLL_CHARACTERISTICS_REVISION_1

### -field SetPollNotificationHandler

An entry point for the [*NdisSetPollNotification*](nc-poll-ndis_set_poll_notification.md) callback function that NDIS invokes when it wants the driver to enable or disable interrupts.

### -field PollHandler

An entry point for the [*NdisPoll*](nc-poll-ndis_poll.md) callback function that NDIS invokes to poll the driver for receive indications and send completions.

## -remarks

Miniport drivers initialize the **NDIS_POLL_CHARACTERISTICS** structure and then pass it to NDIS when calling [**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md). 

## -see-also

[*NdisPoll*](nc-poll-ndis_poll.md) 

[*NdisSetPollNotification*](nc-poll-ndis_set_poll_notification.md)

[**NdisRegisterPoll**](nf-poll-ndisregisterpoll.md)