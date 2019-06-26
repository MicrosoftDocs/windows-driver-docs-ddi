---
UID: NC:netdispumdddi.PFN_STOP_MIRACAST_SESSION
title: PFN_STOP_MIRACAST_SESSION (netdispumdddi.h)
description: Called by the operating system to start a Miracast connected session that had earlier been started by a call to the StartMiracastSession function.
old-location: display\stopmiracastsession.htm
tech.root: display
ms.assetid: ab9ad8ee-9390-41a4-9a69-2e98579b2b77
ms.date: 05/10/2018
ms.keywords: PFN_STOP_MIRACAST_SESSION, PFN_STOP_MIRACAST_SESSION callback, StopMiracastSession, StopMiracastSession callback function [Display Devices], display.stopmiracastsession, netdispumdddi/StopMiracastSession
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Netdispumdddi.h
api_name:
- StopMiracastSession
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_STOP_MIRACAST_SESSION callback function


## -description


Called by the operating system to start a Miracast connected session that had earlier been started by a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a> function.


## -parameters




### -param pMiracastContext [in]

A pointer to a context associated with a display adapter.

The operating system obtained the context when it called the Miracast user-mode driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a> function.


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

The operating system guarantees that only one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_destroy_miracast_context">DestroyMiracastContext</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a>, and <i>StopMiracastSession</i> functions is called at a time.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_destroy_miracast_context">DestroyMiracastContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a>
 

 

