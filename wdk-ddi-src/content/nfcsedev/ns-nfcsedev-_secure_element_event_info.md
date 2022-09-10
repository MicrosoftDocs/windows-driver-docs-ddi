---
UID: NS:nfcsedev._SECURE_ELEMENT_EVENT_INFO
title: _SECURE_ELEMENT_EVENT_INFO (nfcsedev.h)
description: This structure provides information about a secure element event.
old-location: nfpdrivers\secure_element_event_info.htm
tech.root: nfpdrivers
ms.date: 08/02/2022
keywords: ["SECURE_ELEMENT_EVENT_INFO structure"]
ms.keywords: "*PSECURE_ELEMENT_EVENT_INFO, PSECURE_ELEMENT_EVENT_INFO, PSECURE_ELEMENT_EVENT_INFO structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_EVENT_INFO, SECURE_ELEMENT_EVENT_INFO structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_EVENT_INFO, nfcsedev/PSECURE_ELEMENT_EVENT_INFO, nfcsedev/SECURE_ELEMENT_EVENT_INFO, nfpdrivers.secure_element_event_info"
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: SECURE_ELEMENT_EVENT_INFO, *PSECURE_ELEMENT_EVENT_INFO
f1_keywords:
 - _SECURE_ELEMENT_EVENT_INFO
 - nfcsedev/_SECURE_ELEMENT_EVENT_INFO
 - PSECURE_ELEMENT_EVENT_INFO
 - nfcsedev/PSECURE_ELEMENT_EVENT_INFO
 - SECURE_ELEMENT_EVENT_INFO
 - nfcsedev/SECURE_ELEMENT_EVENT_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfcsedev.h
api_name:
 - _SECURE_ELEMENT_EVENT_INFO
 - PSECURE_ELEMENT_EVENT_INFO
 - SECURE_ELEMENT_EVENT_INFO
---

# _SECURE_ELEMENT_EVENT_INFO structure

## -description

This structure provides information about a secure element event.

## -struct-fields

### -field guidSecureElementId

This is a unique identifier for the secure element.

### -field eEventType

This is an event type. For more information about the types, see the [SECURE_ELEMENT_EVENT_TYPE](./ne-nfcsedev-_secure_element_event_type.md) enumeration topic.

### -field cbEventData

This is the amount of bytes for the pbEventData array.

### -field pbEventData[ANYSIZE_ARRAY]

This is the event data buffer. When **eEventType** is **HceActivated** or **HceDeactivated**, this member contains a pointer to a [SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD](./ns-nfcsedev-_secure_element_hce_activation_payload.md) structure. The **bConnectionId** member in that structure is the same ID value that's used in [SECURE_ELEMENT_HCE_DATA_PACKET](./ns-nfcsedev-_secure_element_hce_data_packet.md) to send and receive an HCE packet with [IOCTL_NFCSE_HCE_REMOTE_SEND](./ni-nfcsedev-ioctl_nfcse_hce_remote_send.md) and [IOCTL_NFCSE_HCE_REMOTE_RECV](./ni-nfcsedev-ioctl_nfcse_hce_remote_recv.md).

When **eEventType** is **ExternalReaderArrival** or **ExternalReaderDeparture**, **pbEventData** is empty and **cbEventData** is 0.

When **eEventType** is **Transaction**, **pbEventData** contains a list of parameters that is encoded in BER-TLV fields. This event is mapped to EVT_TRANSACTION.