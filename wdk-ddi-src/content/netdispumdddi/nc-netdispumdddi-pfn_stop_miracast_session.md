---
UID: NC:netdispumdddi.PFN_STOP_MIRACAST_SESSION
title: PFN_STOP_MIRACAST_SESSION
author: windows-driver-content
description: Called by the operating system to start a Miracast connected session that had earlier been started by a call to the StartMiracastSession function.
old-location: display\stopmiracastsession.htm
old-project: display
ms.assetid: ab9ad8ee-9390-41a4-9a69-2e98579b2b77
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.stopmiracastsession, StopMiracastSession callback function [Display Devices], StopMiracastSession, PFN_STOP_MIRACAST_SESSION, PFN_STOP_MIRACAST_SESSION, netdispumdddi/StopMiracastSession
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	UserDefined
apilocation:
-	Netdispumdddi.h
apiname:
-	StopMiracastSession
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_STOP_MIRACAST_SESSION callback


## -description


Called by the operating system to start a Miracast connected session that had earlier been started by a call to the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a> function.


## -prototype


````
PFN_STOP_MIRACAST_SESSION StopMiracastSession;

VOID StopMiracastSession(
  _In_ PVOID pMiracastContext
)
{ ... }
````


## -parameters




### -param pMiracastContext [in]

A pointer to a context associated with a display adapter.

The operating system obtained the context when it called the Miracast user-mode driver's <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a> function.


## -returns



Does not return a value.




## -remarks



When this function is called, the Miracast user-mode driver should follow these procedures:

<ol>
<li>It should not notify the display miniport driver to remove the Miracast monitor unless it knows that the monitor has been physically removed from the remote side.</li>
<li>It should return as quickly as possible to avoid blocking system plug and play (PnP) or power operations.</li>
<li>It should stop all communications and close all sockets that it created, but it should not close the Real-Time Streaming Protocol (RTSP) socket that was passed by the operating system.</li>
</ol>
Also, after this function is called, the Miracast user-mode driver might still receive stream data that the display miniport driver generated. The user-mode driver should drop the stream.


#### Thread Safety

The operating system guarantees that only one of the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a>, <a href="..\netdispumdddi\nc-netdispumdddi-pfn_destroy_miracast_context.md">DestroyMiracastContext</a>, <a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a>, and <i>StopMiracastSession</i> functions is called at a time.




## -see-also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_destroy_miracast_context.md">DestroyMiracastContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_STOP_MIRACAST_SESSION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

