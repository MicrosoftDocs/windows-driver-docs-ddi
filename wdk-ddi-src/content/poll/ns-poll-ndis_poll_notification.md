---
UID: NS:poll._NDIS_POLL_NOTIFICATION
tech.root: netvista
title: NDIS_POLL_NOTIFICATION
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The NDIS_POLL_NOTIFICATION structure contains the interrupt parameters for a Poll object.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: poll.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: NDIS_POLL_NOTIFICATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - poll.h
api_name:
 - _NDIS_POLL_NOTIFICATION
 - NDIS_POLL_NOTIFICATION
f1_keywords:
 - _NDIS_POLL_NOTIFICATION
 - poll/_NDIS_POLL_NOTIFICATION
 - NDIS_POLL_NOTIFICATION
 - poll/NDIS_POLL_NOTIFICATION
dev_langs:
 - c++
---

## -description

The **NDIS_POLL_NOTIFICATION** structure contains the interrupt state for a Poll object. 

## -struct-fields

### -field Header

The [**NDIS_OBJECT_HEADER**](../objectheader/ns-objectheader-ndis_object_header.md) structure for the **NDIS_POLL_NOTIFICATION** structure. Set the members of this structure as follows:

- **Type** = NDIS_OBJECT_TYPE_DEFAULT
- **Revision** = NDIS_POLL_NOTIFICATION_REVISION_1
- **Size** = NDIS_SIZEOF_NDIS_POLL_NOTIFICATION_REVISION_1

### -field Enabled

A value of **TRUE** requests that the miniport driver enable the interrupt associated with this Poll object. A value of **FALSE** requests that the miniport driver disable the interrupt.

## -remarks

NDIS passes a pointer to the **NDIS_POLL_NOTIFICATION** structure when invoking the miniport driver's [*NdisSetPollNotification*](nc-poll-ndis_set_poll_notification.md) callback. 

## -see-also

[*NdisSetPollNotification*](nc-poll-ndis_set_poll_notification.md)