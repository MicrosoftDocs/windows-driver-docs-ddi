---
UID: NS:poll._NDIS_POLL_NOTIFICATION
tech.root: netvista
title: NDIS_POLL_NOTIFICATION
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: 
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



## -struct-fields

### -field Header

The [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md) structure for the **NDIS_POLL_NOTIFICATION** structure. Set the members of this structure as follows:

- **Type** = NDIS_OBJECT_TYPE_DEFAULT
- **Revision** = NDIS_POLL_NOTIFICATION_REVISION_1
- **Size** = NDIS_SIZEOF_NDIS_POLL_NOTIFICATION_REVISION_1

### -field Enabled

A value of **TRUE** requests that the miniport driver enable notifications for the execution context. A value of **FALSE** requests that the miniport driver disable notifications for the execution context.

## -remarks

## -see-also

