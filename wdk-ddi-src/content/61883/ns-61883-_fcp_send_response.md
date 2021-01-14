---
UID: NS:61883._FCP_SEND_RESPONSE
title: _FCP_SEND_RESPONSE (61883.h)
description: This structure is used for a send response.
old-location: ieee\fcp_send_response.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["FCP_SEND_RESPONSE structure"]
ms.keywords: "*PFCP_SEND_RESPONSE, 61883/FCP_SEND_RESPONSE, 61883/PFCP_SEND_RESPONSE, FCP_SEND_RESPONSE, FCP_SEND_RESPONSE structure [Buses], IEEE.fcp_send_response, PFCP_SEND_RESPONSE, PFCP_SEND_RESPONSE structure pointer [Buses], _FCP_SEND_RESPONSE"
req.header: 61883.h
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
req.typenames: FCP_SEND_RESPONSE, *PFCP_SEND_RESPONSE
f1_keywords:
 - _FCP_SEND_RESPONSE
 - 61883/_FCP_SEND_RESPONSE
 - PFCP_SEND_RESPONSE
 - 61883/PFCP_SEND_RESPONSE
 - FCP_SEND_RESPONSE
 - 61883/FCP_SEND_RESPONSE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 61883.h
api_name:
 - _FCP_SEND_RESPONSE
 - PFCP_SEND_RESPONSE
 - FCP_SEND_RESPONSE
---

# _FCP_SEND_RESPONSE structure


## -description

This structure is used for a send response. 

The request sends an FCP response to the device. The  request is used in conjunction with GetFcpRequest. A client driver should use SendFcpResponse to return an FCP response for a received FCP request. If the protocol driver is being used to represent a virtual device on the machine, the <b>NodeAddress</b> member from GetFcpRequest must be specified in the <b>NodeAddress</b> member of the FCP_SEND_RESPONSE structure. This information is required in order to route the response to the proper node on the 1394 bus.

If the protocol driver is being used to control a physical device, the 1394 bus driver determines the node address dynamically, and <b>NodeAddress</b> is not used.

## -struct-fields

### -field NodeAddress

On input, if the protocol driver is being used to control a virtual device, <b>NodeAddress</b> must contain the node address of the device that sent the FCP request obtained with GetFcpRequest so the 1394 bus driver can route the response to the correct device. 

If the protocol driver is being used to control a physical device, <b>NodeAddress</b> is not used.

### -field Length

On input, the length of the frame payload in bytes, including the FCP header.

### -field Frame

On input, a pointer to an <a href="/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_frame">FCP_FRAME</a> structure that contains the FCP response to send to the device.

## -remarks

If successful, the IEC-61883 protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

If the protocol driver is unable to allocate resources, it sets <b>Irp->IoStatus.Status </b>to STATUS_INSUFFICIENT_RESOURCES.

## -see-also

<a href="/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>

