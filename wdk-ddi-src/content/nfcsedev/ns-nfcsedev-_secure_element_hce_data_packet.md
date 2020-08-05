---
UID: NS:nfcsedev._SECURE_ELEMENT_HCE_DATA_PACKET
title: _SECURE_ELEMENT_HCE_DATA_PACKET (nfcsedev.h)
description: SECURE_ELEMENT_HCE_DATA_PACKET is an input buffer to IOCTL_NFCSE_HCE_REMOTE_SEND and output buffer for IOCTL_NFCSE_HCE_REMOTE_RECV.
old-location: nfpdrivers\_secure_element_hce_data_packet.htm
tech.root: nfpdrivers
ms.assetid: A287CBC7-BB22-487E-8E06-47702DF29DCE
ms.date: 02/15/2018
keywords: ["SECURE_ELEMENT_HCE_DATA_PACKET structure"]
ms.keywords: "*PSECURE_ELEMENT_HCE_DATA_PACKET, PSECURE_ELEMENT_HCE_DATA_PACKET, PSECURE_ELEMENT_HCE_DATA_PACKET structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_HCE_DATA_PACKET, SECURE_ELEMENT_HCE_DATA_PACKET structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_HCE_DATA_PACKET, nfcsedev/PSECURE_ELEMENT_HCE_DATA_PACKET, nfcsedev/_SECURE_ELEMENT_HCE_DATA_PACKET, nfpdrivers._secure_element_hce_data_packet"
f1_keywords:
 - "nfcsedev/SECURE_ELEMENT_HCE_DATA_PACKET"
 - "SECURE_ELEMENT_HCE_DATA_PACKET"
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
- SECURE_ELEMENT_HCE_DATA_PACKET
targetos: Windows
req.typenames: SECURE_ELEMENT_HCE_DATA_PACKET, *PSECURE_ELEMENT_HCE_DATA_PACKET
---

# _SECURE_ELEMENT_HCE_DATA_PACKET structure


## -description


<b>SECURE_ELEMENT_HCE_DATA_PACKET</b> is an input buffer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ni-nfcsedev-ioctl_nfcse_hce_remote_send">IOCTL_NFCSE_HCE_REMOTE_SEND</a> and output buffer for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ni-nfcsedev-ioctl_nfcse_hce_remote_recv">IOCTL_NFCSE_HCE_REMOTE_RECV</a>.


## -struct-fields




### -field bConnectionId

The ID of the connection established between the device and the smart card reader, on which to send and receive the HCE packet. This ID is also received from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ni-nfcsedev-ioctl_nfcse_get_next_event">IOCTL_NFCSE_GET_NEXT_EVENT</a> when the event type (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ne-nfcsedev-_secure_element_event_type">SECURE_ELEMENT_EVENT_TYPE</a>) is <b>HceActivated</b> or <b>HceDeactivated</b>. Then the <b>pbEventData</b> field of the returned <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ns-nfcsedev-_secure_element_event_info">SECURE_ELEMENT_EVENT_INFO</a> structure is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcsedev/ns-nfcsedev-_secure_element_hce_activation_payload">SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD</a> structure, which contains a <b>bConnectionId</b> member.


### -field cbPayload

Length of ISO 7816-4 APDU buffer.


### -field pbPayload

 




#### - pbPayload[ANYSIZE_ARRAY]

Buffer holding ISO 7816-4 APDU.

