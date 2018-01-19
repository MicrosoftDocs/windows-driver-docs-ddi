---
UID: NS:wsk._WSK_CLIENT_STREAM_DISPATCH
title: _WSK_CLIENT_STREAM_DISPATCH
author: windows-driver-content
description: The WSK_CLIENT_STREAM_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a stream socket.
old-location: netvista\wsk_client_stream_dispatch.htm
old-project: netvista
ms.assetid: 7E682868-1D39-4677-A4EC-E7C9F841EC82
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WSK_CLIENT_STREAM_DISPATCH, *PWSK_CLIENT_STREAM_DISPATCH, WSK_CLIENT_STREAM_DISPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WSK_CLIENT_STREAM_DISPATCH
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: *PWSK_CLIENT_STREAM_DISPATCH, WSK_CLIENT_STREAM_DISPATCH
req.product: Windows 10 or later.
---

# _WSK_CLIENT_STREAM_DISPATCH structure



## -description
The WSK_CLIENT_STREAM_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a stream socket. Because a stream socket can act either as a listening socket or a connection-oriented socket, this structure allows a stream socket to access the dispatch tables for both the WSK_CLIENT_LISTEN_DISPATCH structure and the WSK_CLIENT_CONNECTION_DISPATCH structure.
  



## -syntax

````
typedef struct _WSK_CLIENT_STREAM_DISPATCH {
  CONST WSK_CLIENT_LISTEN_DISPATCH*     Listen;
  CONST WSK_CLIENT_CONNECTION_DISPATCH* Connect;
} WSK_CLIENT_STREAM_DISPATCH, *PWSK_CLIENT_STREAM_DISPATCH;
````


## -struct-fields

### -field Listen

A pointer to a <a href="..\wsk\ns-wsk-_wsk_client_listen_dispatch.md">WSK_CLIENT_LISTEN_DISPATCH</a> structure, which specifies a WSK application's dispatch table of event
  callback functions for a stream socket which is acting as a listening socket.


### -field Connect

A pointer to a <a href="..\wsk\ns-wsk-_wsk_client_connection_dispatch.md">WSK_CLIENT_CONNECTION_DISPATCH</a> structure, which specifies a WSK application's dispatch table of event
  callback functions for a stream socket which is acting as a connection-oriented socket.


## -remarks
A WSK application passes a pointer to a <b>WSK_CLIENT_STREAM_DISPATCH</b> structure to the WSK subsystem when
    the WSK application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create a stream
    socket.


## -see-also
<dl>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_client_connection_dispatch.md">WSK_CLIENT_CONNECTION_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_client_listen_dispatch.md">WSK_CLIENT_LISTEN_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">WSK_PROVIDER_STREAM_DISPATCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_CLIENT_STREAM_DISPATCH structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

