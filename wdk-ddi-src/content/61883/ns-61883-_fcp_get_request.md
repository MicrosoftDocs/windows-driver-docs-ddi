---
UID: NS:61883._FCP_GET_REQUEST
title: _FCP_GET_REQUEST (61883.h)
description: This structure is used for a get request.
old-location: ieee\fcp_get_request.htm
tech.root: IEEE
ms.assetid: 4DD05230-E9CA-4067-984B-7F0540FE8079
ms.date: 02/15/2018
keywords: ["_FCP_GET_REQUEST structure"]
ms.keywords: "*PFCP_GET_REQUEST, 61883/FCP_GET_REQUEST, 61883/PFCP_GET_REQUEST, FCP_GET_REQUEST, FCP_GET_REQUEST structure [Buses], IEEE.fcp_get_request, PFCP_GET_REQUEST, PFCP_GET_REQUEST structure pointer [Buses], _FCP_GET_REQUEST"
f1_keywords:
 - "61883/FCP_GET_REQUEST"
 - "FCP_GET_REQUEST"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 61883.h
api_name:
- FCP_GET_REQUEST
targetos: Windows
req.typenames: FCP_GET_REQUEST, *PFCP_GET_REQUEST
---

# _FCP_GET_REQUEST structure


## -description


This structure is used for a get request.

The  request retrieves the next FCP request from the queue of requests maintained by the IEC-61883 protocol driver. FCP requests and responses from AV devices are routed to the IEC-61883 protocol driver, which queues the requests. Client drivers send  requests to retrieve an FCP request from the queue. 

For requests sent to a virtual device, the <b>NodeAddress</b> member of the output FCP_GET_REQUEST structure contains the node address of the device that sent the FCP request. The client driver must supply this node address with its response so the instance of the protocol driver that controls the virtual device can route the response correctly. 

For requests sent by a physical device, the 1394 bus driver determines the node address dynamically, and <b>NodeAddress</b> is not used.


## -struct-fields




### -field NodeAddress

On output, if the protocol driver is controlling a virtual device, <b>NodeAddress</b> contains the node address of the device that sent the FCP request obtained with this <b>Av61883_GetFcpRequest</b> IRP. The caller must use this node address in the FCP response sent so the 1394 bus driver can route the response to the correct device. 

If the protocol driver is being used to control a physical device, <b>NodeAddress</b> is not used.


### -field Length

On completion, this field will contain the actual length of the request.


### -field Frame

On input, a pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_fcp_frame">FCP_FRAME</a> structure to receive the FCP request. On output, the FCP frame written to the caller-allocated <b>FCP_FRAME</b> structure by the protocol driver.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>
 

 

