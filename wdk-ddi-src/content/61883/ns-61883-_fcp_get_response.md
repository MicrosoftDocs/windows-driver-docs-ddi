---
UID: NS:61883._FCP_GET_RESPONSE
title: _FCP_GET_RESPONSE (61883.h)
description: The structure is used in a request yjsy retrieves the next FCP response from the queue of requests maintained by the IEC-61883 protocol driver.
old-location: ieee\fcp_get_response.htm
tech.root: IEEE
ms.assetid: 1CE962A4-7F99-4F81-8B85-265A4225B88A
ms.date: 02/15/2018
keywords: ["FCP_GET_RESPONSE structure"]
ms.keywords: "*PFCP_GET_RESPONSE, *PFCP_RESPONSE, 61883/FCP_GET_RESPONSE, 61883/PFCP_GET_RESPONSE, FCP_GET_RESPONSE, FCP_GET_RESPONSE structure [Buses], FCP_RESPONSE, IEEE.fcp_get_response, PFCP_GET_RESPONSE, PFCP_GET_RESPONSE structure pointer [Buses], _FCP_GET_RESPONSE"
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
req.typenames: FCP_RESPONSE, *PFCP_RESPONSE, FCP_GET_RESPONSE, *PFCP_GET_RESPONSE
f1_keywords:
 - _FCP_GET_RESPONSE
 - 61883/_FCP_GET_RESPONSE
 - PFCP_RESPONSE
 - 61883/PFCP_RESPONSE
 - FCP_GET_RESPONSE
 - 61883/FCP_GET_RESPONSE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 61883.h
api_name:
 - FCP_GET_RESPONSE
---

# _FCP_GET_RESPONSE structure


## -description

The structure is used in a request yjsy retrieves the next FCP response from the queue of requests maintained by the IEC-61883 protocol driver. FCP requests and responses from AV devices are routed to the IEC-61883 protocol driver, which queues the requests. Client drivers send <b>Av61883_GetFcpResponse</b> to retrieve an FCP response from the queue.

## -struct-fields

### -field NodeAddress

On output, if the protocol driver is being used to control a virtual device, the protocol driver supplies the node address of the device that sent the response obtained with this <b>Av61883_GetFcpResponse</b> IRP. If the protocol driver is being used to control a physical device, <b>NodeAddress</b> is not used.

### -field Length

On input, the maximum available length, in bytes, of the frame payload, including FCP header. 

On completion, this field will contain the actual length of the response in bytes.

### -field Frame

On input a pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_frame">FCP_FRAME</a> structure to receive the FCP response.

The FCP frame written to the caller-allocated FCP_FRAME structure by the protocol driver.

## -remarks

If successful, the IEC-61883 protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_SUCCESS. 

If the request is queued, the protocol driver sets a status of STATUS_PENDING. If the request has been previously canceled, the driver sets a status of STATUS_CANCELLED.

If an incorrect parameter is passed in, the protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>

