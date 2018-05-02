---
UID: NS:61883._FCP_FRAME
title: "_FCP_FRAME"
author: windows-driver-content
description: The FCP_FRAME structure describes a function control protocol (FCP) request.
old-location: ieee\fcp_frame.htm
old-project: IEEE
ms.assetid: 56a0e888-8048-4774-a46f-8a0beebfb9f2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PFCP_FRAME, 61883/FCP_FRAME, 61883/PFCP_FRAME, 61883_structures_760d5112-e681-4c00-b178-66aadbe95b62.xml, FCP_FRAME, FCP_FRAME structure [Buses], IEEE.fcp_frame, PFCP_FRAME, PFCP_FRAME structure pointer [Buses], _FCP_FRAME"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	FCP_FRAME
product:
- Windows
targetos: Windows
req.typenames: FCP_FRAME, *PFCP_FRAME
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536974">Av61883_GetFcpRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536977">Av61883_GetFcpResponse</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536989">Av61883_SendFcpRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536992">Av61883_SendFcpResponse</a>
 

 

