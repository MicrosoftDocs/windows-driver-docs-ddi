---
UID: NS:wsk._WSK_CLIENT_STREAM_DISPATCH
title: _WSK_CLIENT_STREAM_DISPATCH (wsk.h)
description: The WSK_CLIENT_STREAM_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a stream socket.
old-location: netvista\wsk_client_stream_dispatch.htm
tech.root: netvista
ms.assetid: 7E682868-1D39-4677-A4EC-E7C9F841EC82
ms.date: 05/02/2018
ms.keywords: "*PWSK_CLIENT_STREAM_DISPATCH, PWSK_CLIENT_STREAM_DISPATCH, PWSK_CLIENT_STREAM_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_STREAM_DISPATCH, WSK_CLIENT_STREAM_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_STREAM_DISPATCH, netvista.wsk_client_stream_dispatch, wsk/PWSK_CLIENT_STREAM_DISPATCH, wsk/WSK_CLIENT_STREAM_DISPATCH"
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
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
- wsk.h
api_name:
- WSK_CLIENT_STREAM_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: WSK_CLIENT_STREAM_DISPATCH, *PWSK_CLIENT_STREAM_DISPATCH
---

# _WSK_CLIENT_STREAM_DISPATCH structure


## -description


The WSK_CLIENT_STREAM_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a stream socket. Because a stream socket can act either as a listening socket or a connection-oriented socket, this structure allows a stream socket to access the dispatch tables for both the WSK_CLIENT_LISTEN_DISPATCH structure and the WSK_CLIENT_CONNECTION_DISPATCH structure.
  


## -struct-fields




### -field Listen

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff571162">WSK_CLIENT_LISTEN_DISPATCH</a> structure, which specifies a WSK application's dispatch table of event
  callback functions for a stream socket which is acting as a listening socket.


### -field Connect

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff571156">WSK_CLIENT_CONNECTION_DISPATCH</a> structure, which specifies a WSK application's dispatch table of event
  callback functions for a stream socket which is acting as a connection-oriented socket.


## -remarks



A WSK application passes a pointer to a <b>WSK_CLIENT_STREAM_DISPATCH</b> structure to the WSK subsystem when
    the WSK application calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function to create a stream
    socket.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571156">WSK_CLIENT_CONNECTION_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571162">WSK_CLIENT_LISTEN_DISPATCH</a>



<a href="https://msdn.microsoft.com/A10B901E-9987-40E9-976B-4CD9455E0AEE">WSK_PROVIDER_STREAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>
 

 

