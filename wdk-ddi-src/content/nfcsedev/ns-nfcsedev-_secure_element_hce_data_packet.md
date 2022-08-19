---
UID: NS:nfcsedev._SECURE_ELEMENT_HCE_DATA_PACKET
title: _SECURE_ELEMENT_HCE_DATA_PACKET (nfcsedev.h)
description: SECURE_ELEMENT_HCE_DATA_PACKET is an input buffer to IOCTL_NFCSE_HCE_REMOTE_SEND and output buffer for IOCTL_NFCSE_HCE_REMOTE_RECV.
old-location: nfpdrivers\_secure_element_hce_data_packet.htm
tech.root: nfpdrivers
ms.date: 08/02/2022
keywords: ["SECURE_ELEMENT_HCE_DATA_PACKET structure"]
ms.keywords: "*PSECURE_ELEMENT_HCE_DATA_PACKET, PSECURE_ELEMENT_HCE_DATA_PACKET, PSECURE_ELEMENT_HCE_DATA_PACKET structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_HCE_DATA_PACKET, SECURE_ELEMENT_HCE_DATA_PACKET structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_HCE_DATA_PACKET, nfcsedev/PSECURE_ELEMENT_HCE_DATA_PACKET, nfcsedev/_SECURE_ELEMENT_HCE_DATA_PACKET, nfpdrivers._secure_element_hce_data_packet"
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
req.typenames: SECURE_ELEMENT_HCE_DATA_PACKET, *PSECURE_ELEMENT_HCE_DATA_PACKET
f1_keywords:
 - _SECURE_ELEMENT_HCE_DATA_PACKET
 - nfcsedev/_SECURE_ELEMENT_HCE_DATA_PACKET
 - PSECURE_ELEMENT_HCE_DATA_PACKET
 - nfcsedev/PSECURE_ELEMENT_HCE_DATA_PACKET
 - SECURE_ELEMENT_HCE_DATA_PACKET
 - nfcsedev/SECURE_ELEMENT_HCE_DATA_PACKET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfcsedev.h
api_name:
 - _SECURE_ELEMENT_HCE_DATA_PACKET
 - PSECURE_ELEMENT_HCE_DATA_PACKET
 - SECURE_ELEMENT_HCE_DATA_PACKET
---

# _SECURE_ELEMENT_HCE_DATA_PACKET structure

## -description

**SECURE_ELEMENT_HCE_DATA_PACKET** is an input buffer to [IOCTL_NFCSE_HCE_REMOTE_SEND](./ni-nfcsedev-ioctl_nfcse_hce_remote_send.md) and output buffer for [IOCTL_NFCSE_HCE_REMOTE_RECV](./ni-nfcsedev-ioctl_nfcse_hce_remote_recv.md).

## -struct-fields

### -field bConnectionId

The ID of the connection established between the device and the smart card reader, on which to send and receive the HCE packet. This ID is also received from [IOCTL_NFCSE_GET_NEXT_EVENT](./ni-nfcsedev-ioctl_nfcse_get_next_event.md) when the event type ([SECURE_ELEMENT_EVENT_TYPE](./ne-nfcsedev-_secure_element_event_type.md)) is **HceActivated** or **HceDeactivated**. Then the **pbEventData** field of the returned [SECURE_ELEMENT_EVENT_INFO](./ns-nfcsedev-_secure_element_event_info.md) structure is a [SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD](./ns-nfcsedev-_secure_element_hce_activation_payload.md) structure, which contains a **bConnectionId** member.

### -field cbPayload

Length of ISO 7816-4 APDU buffer.

### -field pbPayload[ANYSIZE_ARRAY]

Buffer holding ISO 7816-4 APDU.