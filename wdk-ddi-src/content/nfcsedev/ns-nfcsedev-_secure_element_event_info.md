---
UID: NS:nfcsedev._SECURE_ELEMENT_EVENT_INFO
title: _SECURE_ELEMENT_EVENT_INFO (nfcsedev.h)
description: This structure provides information about a secure element event.
old-location: nfpdrivers\secure_element_event_info.htm
tech.root: nfpdrivers
ms.assetid: 72B31C26-89D3-49B2-A404-E6F096D0A334
ms.date: 02/15/2018
keywords: ["SECURE_ELEMENT_EVENT_INFO structure"]
ms.keywords: "*PSECURE_ELEMENT_EVENT_INFO, PSECURE_ELEMENT_EVENT_INFO, PSECURE_ELEMENT_EVENT_INFO structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_EVENT_INFO, SECURE_ELEMENT_EVENT_INFO structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_EVENT_INFO, nfcsedev/PSECURE_ELEMENT_EVENT_INFO, nfcsedev/SECURE_ELEMENT_EVENT_INFO, nfpdrivers.secure_element_event_info"
f1_keywords:
 - "nfcsedev/SECURE_ELEMENT_EVENT_INFO"
 - "SECURE_ELEMENT_EVENT_INFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- nfcsedev.h
api_name:
- SECURE_ELEMENT_EVENT_INFO
targetos: Windows
req.typenames: SECURE_ELEMENT_EVENT_INFO, *PSECURE_ELEMENT_EVENT_INFO
---

# _SECURE_ELEMENT_EVENT_INFO structure


## -description


This structure provides information about a secure element event.


## -struct-fields




### -field guidSecureElementId

This is a unique identifier for the secure element.


### -field eEventType

This is an event type. For more information about the types, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ne-nfcsedev-_secure_element_event_type">SECURE_ELEMENT_EVENT_TYPE</a> enumeration topic.


### -field cbEventData

This is the amount of bytes for the pbEventData array.


### -field pbEventData

 




#### - pbEventData[ANYSIZE_ARRAY]

This is the event data buffer. When <b>eEventType</b> is <b>HceActivated</b> or <b>HceDeactivated</b>, this member contains a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ns-nfcsedev-_secure_element_hce_activation_payload">SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD</a> structure. The <b>bConnectionId</b> member in that structure is the same ID value that’s used in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ns-nfcsedev-_secure_element_hce_data_packet">SECURE_ELEMENT_HCE_DATA_PACKET</a> to send and receive an HCE packet with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ni-nfcsedev-ioctl_nfcse_hce_remote_send">IOCTL_NFCSE_HCE_REMOTE_SEND</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ni-nfcsedev-ioctl_nfcse_hce_remote_recv">IOCTL_NFCSE_HCE_REMOTE_RECV</a>.

When <b>eEventType</b> is <b>ExternalReaderArrival</b> or <b>ExternalReaderDeparture</b>, <b>pbEventData</b> is empty and <b>cbEventData</b> is 0.

When <b>eEventType</b> is <b>Transaction</b>, <b>pbEventData</b> contains a list of parameters that is encoded in BER-TLV fields. This event is mapped to EVT_TRANSACTION.

