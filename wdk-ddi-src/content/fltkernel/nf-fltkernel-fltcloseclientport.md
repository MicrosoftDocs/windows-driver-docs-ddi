---
UID: NF:fltkernel.FltCloseClientPort
title: FltCloseClientPort function
author: windows-driver-content
description: FltCloseClientPort closes a communication client port.
old-location: ifsk\fltcloseclientport.htm
old-project: ifsk
ms.assetid: 7a23b8f6-688f-4aa4-9bf3-f8bda0458566
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_0def0996-8190-4482-a7bb-018c79773eca.xml, FltCloseClientPort, FltCloseClientPort function [Installable File System Drivers], fltkernel/FltCloseClientPort, ifsk.fltcloseclientport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltCloseClientPort
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCloseClientPort function


## -description


<b>FltCloseClientPort</b> closes a communication client port. 


## -syntax


````
VOID FltCloseClientPort(
  _In_  PFLT_FILTER Filter,
  _Out_ PFLT_PORT   *ClientPort
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param ClientPort [out]

Pointer to a variable that contains the opaque port handle for the client port to be closed. On return, the variable receives <b>NULL</b>. This parameter is required and cannot be <b>NULL</b> on input. 


## -returns



None 




## -remarks



A minifilter driver normally calls <b>FltCloseClientPort</b> from the <i>DisconnectNotifyCallback</i> routine that it registered when it called <a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>. The Filter Manager calls the <i>DisconnectNotifyCallback</i> routine whenever the user-mode handle count for the client port reaches zero or when the minifilter driver is about to be unloaded. 

<b>FltCloseClientPort</b> closes a communication client port that was created by the minifilter driver's <i>ConnectNotifyCallback</i> routine. 

On input, the <i>ClientPort</i> parameter is a pointer to a variable containing the opaque handle for the client port to be closed. To ensure that any messages sent by <a href="..\fltkernel\nf-fltkernel-fltsendmessage.md">FltSendMessage</a> are synchronized properly when the communication client port is being closed, <b>FltCloseClientPort</b> sets this variable to <b>NULL</b>. 

This routine disconnects a specific connection from the minifilter driver. To close the handle for the minifilter driver's server port, which listens for incoming connections, use <a href="..\fltkernel\nf-fltkernel-fltclosecommunicationport.md">FltCloseCommunicationPort</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltsendmessage.md">FltSendMessage</a>



<a href="..\fltkernel\nf-fltkernel-fltclosecommunicationport.md">FltCloseCommunicationPort</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540460">FilterConnectCommunicationPort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCloseClientPort function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

