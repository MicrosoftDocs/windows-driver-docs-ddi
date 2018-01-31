---
UID: NS:nfcsedev._SECURE_ELEMENT_HCE_DATA_PACKET
title: "_SECURE_ELEMENT_HCE_DATA_PACKET"
author: windows-driver-content
description: SECURE_ELEMENT_HCE_DATA_PACKET is an input buffer to IOCTL_NFCSE_HCE_REMOTE_SEND and output buffer for IOCTL_NFCSE_HCE_REMOTE_RECV.
old-location: nfpdrivers\_secure_element_hce_data_packet.htm
old-project: nfpdrivers
ms.assetid: A287CBC7-BB22-487E-8E06-47702DF29DCE
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: "*PSECURE_ELEMENT_HCE_DATA_PACKET, _SECURE_ELEMENT_HCE_DATA_PACKET, SECURE_ELEMENT_HCE_DATA_PACKET structure [Near-Field Proximity Drivers], PSECURE_ELEMENT_HCE_DATA_PACKET structure pointer [Near-Field Proximity Drivers], PSECURE_ELEMENT_HCE_DATA_PACKET, nfcsedev/PSECURE_ELEMENT_HCE_DATA_PACKET, nfcsedev/_SECURE_ELEMENT_HCE_DATA_PACKET, SECURE_ELEMENT_HCE_DATA_PACKET, nfpdrivers._secure_element_hce_data_packet"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfcsedev.h
apiname:
-	SECURE_ELEMENT_HCE_DATA_PACKET
product: Windows
targetos: Windows
req.typenames: "*PSECURE_ELEMENT_HCE_DATA_PACKET, SECURE_ELEMENT_HCE_DATA_PACKET"
---

# _SECURE_ELEMENT_HCE_DATA_PACKET structure


## -description


<b>SECURE_ELEMENT_HCE_DATA_PACKET</b> is an input buffer to <a href="..\nfcsedev\ni-nfcsedev-ioctl_nfcse_hce_remote_send.md">IOCTL_NFCSE_HCE_REMOTE_SEND</a> and output buffer for <a href="..\nfcsedev\ni-nfcsedev-ioctl_nfcse_hce_remote_recv.md">IOCTL_NFCSE_HCE_REMOTE_RECV</a>.


## -syntax


````
typedef struct _SECURE_ELEMENT_HCE_DATA_PACKET {
  USHORT                             bConnectionId;
  USHORT                             cbPayload;
  _Field_size_bytes_(cbPayload) BYTE pbPayload[ANYSIZE_ARRAY];
} SECURE_ELEMENT_HCE_DATA_PACKET, *PSECURE_ELEMENT_HCE_DATA_PACKET;
````


## -struct-fields




#### - bConnectionId

The ID of the connection established between the device and the smart card reader, on which to send and receive the HCE packet. This ID is also received from <a href="..\nfcsedev\ni-nfcsedev-ioctl_nfcse_get_next_event.md">IOCTL_NFCSE_GET_NEXT_EVENT</a> when the event type (<a href="..\nfcsedev\ne-nfcsedev-_secure_element_event_type.md">SECURE_ELEMENT_EVENT_TYPE</a>) is <b>HceActivated</b> or <b>HceDeactivated</b>. Then the <b>pbEventData</b> field of the returned <a href="..\nfcsedev\ns-nfcsedev-_secure_element_event_info.md">SECURE_ELEMENT_EVENT_INFO</a> structure is a <a href="..\nfcsedev\ns-nfcsedev-_secure_element_hce_activation_payload.md">SECURE_ELEMENT_HCE_ACTIVATION_PAYLOAD</a> structure, which contains a <b>bConnectionId</b> member.


#### - cbPayload

Length of ISO 7816-4 APDU buffer.


### -field pbPayload

 



#### - pbPayload[ANYSIZE_ARRAY]

Buffer holding ISO 7816-4 APDU.

