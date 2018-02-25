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
ms.keywords: ",  , *, *PFCP_FRAME, ,, 61883/FCP_FRAME, 61883/PFCP_FRAME, 61883_structures_760d5112-e681-4c00-b178-66aadbe95b62.xml, A, C, E, F, FCP_FRAME, FCP_FRAME structure [Buses], IEEE.fcp_frame, M, P, PFCP_FRAME, PFCP_FRAME structure pointer [Buses], R, _, _FCP_FRAME"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	61883.h
apiname:
-	FCP_FRAME
product: Windows
targetos: Windows
req.typenames: FCP_FRAME, *PFCP_FRAME
---

# _FCP_FRAME structure


## -description


The FCP_FRAME structure describes a function control protocol (FCP) request.


## -syntax


````
typedef struct _FCP_FRAME {
  UCHAR ctype  :4;
  UCHAR cts  :4;
  UCHAR payload[511];
} FCP_FRAME, *PFCP_FRAME;
````


## -struct-fields




### -field ctype

The command or response type as defined by the Command/Transaction Set (CTS) used for this request.


### -field cts

The CTS used for this FCP request. The CTS specifies the command set, the structure of the command/response field, and the rules of transactions used for sending FCP commands and responses.


### -field payload

The FCP request for this frame.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536992">Av61883_SendFcpResponse</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536989">Av61883_SendFcpRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536977">Av61883_GetFcpResponse</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536974">Av61883_GetFcpRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20FCP_FRAME structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

