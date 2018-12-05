---
UID: NC:netdispumdddi.PFN_START_MIRACAST_SESSION
title: PFN_START_MIRACAST_SESSION
author: windows-driver-content
description: Called by the operating system to start a Miracast connected session.
old-location: display\startmiracastsession.htm
tech.root: display
ms.assetid: 2778d9d0-7f97-416f-a5ae-3754b17e8a29
ms.date: 05/10/2018
ms.keywords: PFN_START_MIRACAST_SESSION, PFN_START_MIRACAST_SESSION callback, StartMiracastSession, StartMiracastSession callback function [Display Devices], display.startmiracastsession, netdispumdddi/StartMiracastSession
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Netdispumdddi.h
api_name:
-	StartMiracastSession
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_START_MIRACAST_SESSION callback function


## -description


Called by the operating system to start a Miracast connected session.


## -parameters




### -param pMiracastContext [in]

A pointer to a context associated with a display adapter.

The operating system obtained the context when it called the Miracast user-mode driver's <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.


### -param MiracastRTSPSocket [in]

The operating system-supplied network socket handle of the Real Time Streaming Protocol (RTSP). 

<div class="alert"><b>Note</b>  The Miracast user-mode driver should not close this socket. When the <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> function is called, the operating system will close this socket.</div>
<div> </div>

### -param *pWfdConnectionStats [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265482">MIRACAST_WFD_CONNECTION_STATS</a> structure that indicates the Wi-Fi Direct connection statistics.


### -param *pSessionInfo [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265478">MIRACAST_SESSION_INFO</a> structure that the Miracast user-mode driver should complete after it has obtained the capabilities of the Miracast sink.


## -returns



On success, this function returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header, including the following:

|Return code|Description|
|--- |--- |
|STATUS_DEVICE_INSUFFICIENT_RESOURCES|The current suggested encode rate cannot sustain a Miracast sink that supports more than 1024 x 768 pixels.|
 
## -remarks

When this function is called, the Miracast user-mode driver should start communicating with the Miracast sink using the Miracast protocol. The driver should  gather the capabilities of the sink and the attributes of the monitor that's connected to the sink.  The driver should perform enough of the negotiation with the sink to determine whether a monitor is connected to the sink or not. If the driver determines that a monitor is connected to the sink, it should also determine whether the current suggested bit rate is high enough to at least support the lowest sink supported mode of 1024 x 768 pixels.

The driver should also set the value of these members of <a href="https://msdn.microsoft.com/library/windows/hardware/dn265478">MIRACAST_SESSION_INFO</a> pointed to by <i>pSessionInfo</i> in these cases:




#### Thread Safety

The operating system guarantees that only one of the <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>, <a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>, <i>StartMiracastSession</i>, and <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> functions is called at a time.




## -see-also




<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>



<a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265478">MIRACAST_SESSION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265482">MIRACAST_WFD_CONNECTION_STATS</a>



<a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a>
 

 

