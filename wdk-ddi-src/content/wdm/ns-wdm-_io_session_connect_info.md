---
UID: NS:wdm._IO_SESSION_CONNECT_INFO
title: "_IO_SESSION_CONNECT_INFO"
description: The IO_SESSION_CONNECT_INFO structure provides information about a user session.
old-location: kernel\io_session_connect_info.htm
tech.root: kernel
ms.assetid: f9d7ffae-aa9e-44d6-b659-cb5a9068f1d7
ms.date: 04/30/2018
ms.keywords: "*PIO_SESSION_CONNECT_INFO, IO_SESSION_CONNECT_INFO, IO_SESSION_CONNECT_INFO structure [Kernel-Mode Driver Architecture], PIO_SESSION_CONNECT_INFO, PIO_SESSION_CONNECT_INFO structure pointer [Kernel-Mode Driver Architecture], _IO_SESSION_CONNECT_INFO, kernel.io_session_connect_info, kstruct_b_ef736de7-23b2-4d43-837f-ea879d963ef8.xml, wdm/IO_SESSION_CONNECT_INFO, wdm/PIO_SESSION_CONNECT_INFO"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
-	Wdm.h
api_name:
-	IO_SESSION_CONNECT_INFO
product:
- Windows
targetos: Windows
req.typenames: IO_SESSION_CONNECT_INFO, *PIO_SESSION_CONNECT_INFO
---

# _IO_SESSION_CONNECT_INFO structure


## -description


The <b>IO_SESSION_CONNECT_INFO</b> structure provides information about a user session. 


## -struct-fields




### -field SessionId

Session ID. This member contains the <a href="https://go.microsoft.com/fwlink/p/?linkid=155045">Terminal Services</a> session identifier of the user session for which the driver is receiving this notification.


### -field LocalSession

Indicates whether the user session is a local session or a remote session. If <b>TRUE</b>, the user is logged on locally. If <b>FALSE</b>, the user is logged on remotely. 


## -remarks



If a driver is registered to receive notifications of events in a user session, and if this session enters the <i>connected</i> state, the I/O manager calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550626">IO_SESSION_NOTIFICATION_FUNCTION</a> function. For this call, the I/O manager sets the function's <i>Event</i> parameter to <b>IoSessionEventConnected</b>. Additionally, the I/O manager sets the function's <i>NotificationPayload</i> parameter to point to an <b>IO_SESSION_CONNECT_INFO</b> structure that contains information about the user session. For more information about <b>IoSessionEventConnected</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550623">IO_SESSION_EVENT</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550623">IO_SESSION_EVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550626">IO_SESSION_NOTIFICATION_FUNCTION</a>
 

 

