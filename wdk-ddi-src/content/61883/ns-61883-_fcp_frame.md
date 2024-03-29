---
UID: NS:61883._FCP_FRAME
title: _FCP_FRAME (61883.h)
description: The FCP_FRAME structure describes a function control protocol (FCP) request.
old-location: ieee\fcp_frame.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["FCP_FRAME structure"]
ms.keywords: "*PFCP_FRAME, 61883/FCP_FRAME, 61883/PFCP_FRAME, 61883_structures_760d5112-e681-4c00-b178-66aadbe95b62.xml, FCP_FRAME, FCP_FRAME structure [Buses], IEEE.fcp_frame, PFCP_FRAME, PFCP_FRAME structure pointer [Buses], _FCP_FRAME"
req.header: 61883.h
req.include-header: 61883.h
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
req.typenames: FCP_FRAME, *PFCP_FRAME
f1_keywords:
 - _FCP_FRAME
 - 61883/_FCP_FRAME
 - PFCP_FRAME
 - 61883/PFCP_FRAME
 - FCP_FRAME
 - 61883/FCP_FRAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 61883.h
api_name:
 - _FCP_FRAME
 - PFCP_FRAME
 - FCP_FRAME
---

# _FCP_FRAME structure


## -description

The FCP_FRAME structure describes a function control protocol (FCP) request.

## -struct-fields

### -field ctype

The command or response type as defined by the Command/Transaction Set (CTS) used for this request.

### -field cts

The CTS used for this FCP request. The CTS specifies the command set, the structure of the command/response field, and the rules of transactions used for sending FCP commands and responses.

### -field payload

The FCP request for this frame.

## -see-also

<a href="/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST structure</a>
